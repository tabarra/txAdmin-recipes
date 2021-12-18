# txAdmin-recipes 
This repository is the index for the popular txAdmin's Server Deployer Recipes!
Please check the **[Recipe Documentation Page](https://github.com/tabarra/txAdmin/blob/master/docs/recipe.md)** if you wanna know more.

## Popular recipes:
- [CFX Default](https://github.com/tabarra/CFX-Default-recipe)
- [QBCore Framework](https://github.com/qbcore-framework/txAdminRecipe)
- [ZAP-Hosting ESX Pack](https://github.com/zap-fivem/esx_12_recipe)

## Recipe-making Guidelines and Best Practices:
- Always start your recipe based on the CFX Default one;
- The recipe must "just work", without the user needing to edit anything before starting the server, like database credentials;
- Database stuff:
    - Preferable use the `{{dbConnectionString}}` placeholder in `server.cfg` instead of writing to some database config file;
    - Put the database stuff at the start of the recipes, as that is the most likely task to fail;
    - The recipe must accept the random database name generated by txAdmin instead of forcing a name like `es_extended`. If needed, you can perform a `replace_string` with the `{{dbName}}` variable;
    - When exporting the database, make sure to not also export player data like admins, bans and etc;
- Your `server.cfg` must contain the following placeholders: `{{maxClients}}`, `{{addPrincipalsMaster}}`, `{{serverEndpoints}}` and `{{svLicense}}`;
- Make sure your scripts/framework recognize users with the `admin` ACE group as script/framework admins. This can be done every time the player joins or even on his first join ([esx-legacy example](https://github.com/esx-framework/esx-legacy/commit/e265976561f6c72c9d95032861638c38b4505d20));
- On `download_github`, always use the reference parameter, preferably to a commit instead of a tag, since tags can change, bthis guarantees that no recipe-breaking change will be introduced in some random commit;
- When downloading, extracting and moving Zip files, group the 3 actions so it is easier to find it after;
- Recipes must be onesync compatible, even if just `legacy`;
- Always set `$onesync` to `on` if your recipe supports it;
- Considering that most people are not familiar with what your recipe is installing, guarantee a good onboarding experience with the following:
    - The loading screen must clearly state what that base is, and how to use it like keys to press and etc ([plume example](https://i.imgur.com/BREZLDW.png));
    - On important files like `server.cfg`, leave plenty of comments instructing the admin how to use or configure your base;
- Execute a `waste_time` with 10 seconds every 25 `download_github` actions, or 50 if setting the `ref` parameter. Too many GitHub requests in a short ammount of time will result in a 403 error;
- It is recommended the use semantic versioning for your version number, for example `v3.2.1` (3 major, 2 minor, 1 patch):
    - Major: multiple updates, chances of breaking something;
    - Minor: small updates, settings change and features added;
    - Patch: changing description, some minor text or something like that.
- Your recipe must not violate or facilitate violation of any license or copyright, so it should only contain resources that are open source (eg GPLv3/MIT/Apache) or sharable (eg Creative Commons). Please make sure it does not contain any leaked content. Although it is hard to find a scenario where a recipe could _directly_ violate any license, this is a headache that we must try to avoid;

****
<p align="center">
    <p align="center">
        <b>Do you have any questions? Things are looking too complicated? Join <code>#recipe-making</code> in our Discord!</b> <br>
        <a href="https://discord.gg/AFAAXzq"><img src="https://discordapp.com/api/guilds/577993482761928734/widget.png?style=banner2" alt="txadmin discord"></img></a>
    </p>
</p>
