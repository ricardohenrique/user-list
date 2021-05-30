# orderbird Senior Frontend Tech Challenge

Hey Front End developer. Welcome. Your mission, should you decide to accept
it, is to carve out 3 hours and create a SPA using [Laravel][1], [Tailwind][2],
and your JavaScript library of preference.

[1]: https://laravel.com/
[2]: https://tailwindcss.com/

The objective of the challenge is to display a table of users. It has to be
sortable (both asc. and desc.) by first name, last name, and email address.

The table on the view must be responsive: it should be centered vertically and
horizontally on desktop and tablet, with a max. width of `768px`, but occupy
the entire screen on mobile devices. Allow horizontal scroll to prevent
breaking the rows only when necessary.

## Desired outcome

- It must be a Single Page Application
- Do not use jQuery
- Go all the way with the latest ECMAScript specs (you'll possibly need to
  update `webpack` config)
- Include tests (at least unit tests)
- Modularize whenever possible, avoid creating files with hundred of lines
- Your submission for this challenge runs without errors nor warnings

## Important!

We hope you can spend about three hours on this project. If you can finish
faster, great! If not, limit yourself and don't spend much longer.

You'll need to set `WWWUSER` and `WWWGROUP` env vars with your user id and
group in order grant the correct permissions for the docker containers. Either:
- export them from your shell (inline or in your .\*rc file):
  `export WWWUSER=$UID && export WWWGROUP=$(id -g)` or
- run `docker-compose` this way:
  `WWWUSER=$UID WWWGROUP=$(id -g) docker-compose <YOUR_SUBCOMMAND_HERE>`.

Right after `up`, the container `laravel.test` will error until you run
`composer install` from inside of the container. This is part of the
challenge. After you solve it, open [http://localhost/][3] in your browser.

[3]: http://localhost/

_Hint_: set the option `--user=$WWWUSER` when installing.

## Required steps for a valid solution

1. Create your own base branch, branch out from it by feature, and squash
   merge back into your base branch when you complete each feature
2. Run the containers for the development environment using `docker-compose`.
   Running the stack on a non-dockerized environment is not a valid approach,
   but you can use `sail` to make your life easier
3. Add Tailwind as a project dependency and use it on the views
4. Write a migration to create ten (10) users with: first name, last name and
   email address. The migration should be able to rollback
5. Write a seed to populate the users
6. Write a view to display the users data from the database in a table. Fetch
   the data from `/users`
7. Write a JavaScript solution to sort the users table by any of the fields:
   you can use any library (React, Vue, etc), but you **can't implement** a
   pre-made package with this functionality (e.g.
   [DataTables][4])

[4]: https://www.datatables.net/

## We'll take into consideration:

- Your git commit history:

  The log of the repository should follow [this guideline][5]. Please read at
  least [The Seven Rules][6] listed in the article and apply them.

[5]: https://chris.beams.io/posts/git-commit/
[6]: https://chris.beams.io/posts/git-commit/#seven-rules

- The quality of your code; keep it tidy, linted, and DRY:
  - Use *only* spaces for indentation (no tabs allowed): this repo contains an
    [editorconfig](https://editorconfig.org/) file, please use it in your
    editor/IDE 
  - **HTML/Blade**: indent the code with 2 spaces and avoid long lines in the
    code. You can set one HTML attribute per line (think React style for JSX)
    and split the values in multiple lines
  - **JavaScript**: use [eslint][7] with the config provided on this repo
  - **PHP**: follow the [PSR-12][8] coding style. [php-cs-fixer][9] can help
    you enforce this style
  - Keep files and folders unrelated to the project out of the repo: .idea,
    \*.swp, .vscode, .DS\_Store, vendor, etc. **should not** be commited.
    Update `.gitignore` if necessary

[7]: https://www.npmjs.com/package/eslint
[8]: https://www.php-fig.org/psr/psr-12/
[9]: https://github.com/FriendsOfPhp/PHP-CS-Fixer

## Nice to have

- Anything else you would like to add

## When you finish

Please send your solution as a zipped package to
[tech-challenge@orderbird.com][10], **including** your `.git` folder.

[10]: mailto:tech-challenge@orderbird.com
