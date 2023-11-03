# NPM-Basics

1. NPM act as a repo to host the package that is uploaded by devs and these packages are low-level, fully optimized and tested so user do not have to rewrite from scratch.

2. NPM contains the minified Archived tar.gz file of packages not the code of packages.

3. NPM provide the cli to manage the packages on dev machine.

4. internally npm use javascript it cannot work without a js env and nodejs provide the js env that why we need nodejs to use npm.

5. You can get the nodejs a js runtime from
   following link - https://nodejs.org/

6. After the install we can check the version
   by executing "npm -v" in shell also for nodejs by executing "node -v" .

7. We can install and use multiple versions of node on a single machine this is helpful when we are working on
   legecy code base and also on a new project.
   sometimes the node packages can be system binary which has to be compiled using nodejs env (node-gyp) these binary can be node version dependent.

8. We can get multipal version of node by using "nvm" in any OS but package "n" is recommanded to be used on UNIX based os, by executing "sudo npm i -g n" we can install it globally and get latest node by executing "sudo n latest" and whenever our node is updated npm is also updated.

9. We can choose any node and npm version by executing "sudo n" and get the list of all node packages that are installed on machine.

10. We can get specific version of node by executing
    "sudo n x.x.x" x is version of node that we want.

11. For example when we install any package by npm
    first npm search in npm repo and then if available then fetch the tar file of package, extract it and palace it to node_modules folder and modules folder will be created in dir where we executed the command.

12. We will see the dir named by the package name in node_modules dir for example if we installed the lodash package then it will create a lodash dir in node_modules dir.

13. To get the info about any module or package we can just execute "npm view package_name" for example
    "npm view lodash".

14. when we install any package first it get the tarball url by view command as we discussed in 13 and then curl or wget the tarball url and get the zip file and extract to node_modules dir

15. we can manually download and extract the package but npm also verify the integrity of package by using shasum provided by view command.

16. package.json is used by npm to keep track of installed packages and dependencies of it , this file also contains the scripts to run build and deploy the project and also contains the.

17. We can create the package.json file manually but the preffred way to create the file is to run "npm init" and hit enter after providing value of required field and (the value in bracket is default value) or we can use "npm init -y" to avoid the field filling by us.

18. How to install a package =>
    npm install "package name" or npm i "package name" to install a "package"

19. How to remove a package => npm remove "package name"
    or npm uninstall "package name"

20. What are global packages and what is the diff b/w local and global =>> global packages are accesiable from anywhere in whole system but local packages are only limited to a dir where the installation command executed we can not access them outside of installed dir but it is not the case with global package.

21. we can install a package globally by passing the flag "-g" or "--global" when any package is installed.

22. To locate the dir where global package is installed we can execute the command " npm root -g".

23. NPM is itself a global package we can see it by executing "cd $(npm root -g) && ls | grep npm".

24. We can get latest version of npm by exec "npm -i -g npm@latest", here npm is installing npm package globally with latest version.

25. Packages follow semantic versioning
    here is the break Down of versioning

    MAJOR version when you make incompatible API changes<br>
    MINOR version when you add functionality in a backward compatible manner<br>
    PATCH version when you make backward compatible bug fixes<br>

26. We can check actual installed module/package version<br> by executing "ls node_modules/"package-name"/ && cat package.json | grep version".

27. The package-lock.json is needed for keep dependent package locked for a another package that use the dependent packages so if dependent packages indviually updated then main package will broke so all depend package only updated when main package is updated
    for ex if express installed then it requires the packages and install them and lock and the package installed for express will only updated when express updated not indvisually.

28. "^5.0.0" => 5.x.x both x place can be updated <br>
    "~5.0.0" => 5.0.x only x place updated <br>
    "5.0.0" => 5.0.0 stay exact same

29. What is dev dependencies? => dev deps are packages that are only needed for development related things not for production related. just only for devlopment.
    we can install dev deps by just adding "--save-dev".<br>
    ex "npm install package-name --save-dev".

30. We can pretend as a production server by <br>
    changing NODE_ENV="production" and now if we exec npm i or npm install then all dev dpens are skipped not installed, mostly dev deps are build tools.

31. Peer dependencies => we mostly need it when we creating our own packages.Peer dependencies are a special type of dependency that would only ever come up if you were publishing your own package.
    Having a peer dependency means that your package needs a dependency that is the same exact dependency as the person installing your package. This is useful for packages like react that need to have a single copy of react-dom that is also used by the person installing it.

32. NPM Scripts => <br>

    1. it is a object within the global object of package.json and hold key value pair.
    2. Script name as a key and value of the key will be a script(bash,python,powershell,nodejs)<br>
       ex. "dev" : "_bash command here_"<br>
    3. to run custom scripts we need place run before script name for ex. " npm _run_ scriptname"

33. What is NPX => <br>

    1. it allow us to run local binaries or packages and does not need the whole path.
    2. it allow us to run global npm packages or binaries from npm without installing them.

34. we can change root(global) dir for node package install globally by "npm config set prefix _path of dir_<br>
    for revert back to default "npm config set prefix /usr/local"

35. NPM cache is stored at "_~/.npm_" dir <br>
    to clean cache we can use command "npm cache clean" or by forcefully "npm cache clean --force"<br>
    but if you don't have any need please avoid to clean cache because npm is smart enough to maintain itself.

36. Run "_npm config ls -l_" to see the complete configuration of NPM.
