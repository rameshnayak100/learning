# Project

For learning DevOps, let's do a project on something interesting.

## Tools

* Use Visual Studio Code
* Put repositories on GitHub
* Use AWS or Azure for infrastructure
* Use PowerShell or bash as much as possible (don't use the UI if you can use the shell)

## Project Plan

1. Create a website that has a static `index.html` page with the text "Hello, World!" on it. Check it into a repo called `budget-website` on GitHub.
2. Update the website on a branch called `change-greeting`, change the text to "Hello, Everyone!". Submit that branch as a pull request and add Michael as a reviewer of it. All pull requests from here on out should be reviewed by Michael.
3. Create a linux machine on AWS/Azure and set up nginx on it (google for setup instructions). The setup instructions should be documented in your `budget-website` `README.md` file, with branch, pull request, review, merge workflow.
4. Deploy your website to the nginx machine. You should be able to point people at the URL.
5. Add a chef cookbook called `budget_website_infrastructure` with the same named repository on GitHub. Put this in `C:\code\chef\cookbooks\budget_website_infrastructure` (or `~/code/chef/cookbooks/budgte_website_infrastructure`)
6. Make sure you can run Test Kitchen that brings up a linux machine, converges an empty recipe.
7. Make sure your cookbook matches linting (rubocop and foodcritic). Make sure you check the linting every time you check in.
7. Add nginx setup to your recipe. See if you can use the `nginx` cookbook to help you
8. Clone the website to your machine as a part of the recipe. At this point you should be able to have a fully built website
9. Create a chef account at manage.chef.io and make it so you can run knife on your local chef repo. Put the `.chef` folder in `C:\code\chef` with your knife information. Make sure you know the basic commands with knife.
10. Bootstrap your linux node with Chef, converge, and see that it runs
11. Make a code change, reconverge with Chef, and see that the website updates
12. On your local machine, create a jenkins server that uses your local machine as an agent
13. Configure a chef cookbook build with a rakefile and Jenkinsfile, as outlined in hedge-ops.com. It will be a little different because you're not using bitbucket, so simplify the solution for one that works.
14. The end of the build should push the cookbook to the Chef Server, which your site will use
15. Make sure `nano` is installed (through the `package` resource).
16. Write an inspec profile to make sure your website is functional and installed properly. Run against your website. This will be a github website.
17. Add a jenkins job that will test your website with your inspec profile.