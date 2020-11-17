# Prerequisites
0. Make sure [hugo](https://gohugo.io/getting-started/installing) is installed on your computer. The site is always built on the server against the latest version of hugo.

# Adding meeting minutes

1. Make a new branch off of main.
    + If you're trusted, work directly on main, and ignore steps 2 and 10, and 11. The site will be built upon push. 
2. Pull and checkout your branch.
3. Open in a terminal the directory `{REPO_ROOT}/tsuacm`
4. Create your minutes file with the command: `hugo new minutes/semester/meeting-title.md`
    + ***Never*** manually create the markdown files.
    + The file name sets the default title, but the path of the file has no effect on the final URL. See below.
5. Open the created markdown file to edit. Proper frontmatter should be added.
    + Note: Style all links to external sources with the following shortcode: `{{< externallink url="https://example.com" text="The Link Text" title="Hover Text" >}}`
        + `url` is the URL to link to
        + `text` is the text (or other HTML contents) of the link
        + `title` is optional and is the text shown on hover
    + To change the default template, edit `tsuacm/archetypes/minutes.md`
6. Put any static resources (images, other things that don't need to be processed) in the `static` folder.
    + Things in this folder are hosted starting from the site root.
    + For example, `static/images/myimage.png` is hosted at `https://mysite.com/images/myimage.png`
    + Link to these items with relative URLs from the site root: `/images/myimage.png`
7. Run the command `hugo server` to run the integrated test server.
    + If you want to show drafts as well, run `hugo server -D` instead.
    + A link to the test server will be shown, and it will update on any changes made.
8. Visit the meeting minutes to check their formatting. The permalink is always `BASE_URL/minutes/yyyy/mm/dd`
    + Ex: `https://localhost:1313/minutes/2020/11/16`
    + Ex: `https://tsuacm.github.io/minutes/2020/11/16`
    + You can alter this in the `config.json`
9.  When the changes are as you like them, commit and push to your branch. ***DO NOT BUILD THE SITE ON YOUR MACHINE WITH THE `hugo` COMMAND!*** The GitHub servers will do this for you.
10.  Create a PR from your branch to main. It will automatically run a build against your branch to make sure it works. An approval and successful build are required before a merge.
11.  Once approved, merge. You can also optionally delete your branch after it's merged. The site will be automatically built and deployed.
# Adding new content

1. Make a new branch off of main.
2. Pull and checkout your branch.
3. Open in a terminal the directory `{REPO_ROOT}/tsuacm`
4. Create your content with the command: `hugo new path/title.md`
    + Ex: New Top-Level Page: `hugo new my-page.md`
    + Ex: New blog post under "posts": `hugo new posts/my-title.md`
    + ***Never*** manually create the markdown files.
    + The type of the new content is inferred by the file path. Specify it manually with `hugo new -k type path/title.md`
5. Run the command `hugo server` to run the integrated test server.
    + If you want to show drafts as well, run `hugo server -D` instead.
    + A link to the test server will be shown, and it will update on any changes made.
6. Open the created markdown file to edit. Proper frontmatter should be added based on the type, although you can always change/add/remove it. See the Hugo documentation for more on this.
    + Note: Style all links to external sources with the following shortcode: `{{< externallink url="https://example.com" text="The Link Text" title="Hover Text" >}}`
        + `url` is the URL to link to
        + `text` is the text (or other HTML contents) of the link
        + `title` is optional and is the text shown on hover
7. Put any static resources (images, other things that don't need to be processed) in the `static` folder.
    + Things in this folder are hosted starting from the site root.
    + For example, `static/images/myimage.png` is hosted at `https://mysite.com/images/myimage.png`
    + Link to these items with relative URLs from the site root: `/images/myimage.png`
8. When the changes are as you like them, commit and push to your branch. ***DO NOT BUILD THE SITE ON YOUR MACHINE WITH THE `hugo` COMMAND!*** The GitHub servers will do this for you.
9.  Create a PR from your branch to main. It will automatically run a build against your branch to make sure it works. An approval and successful build are required before a merge.
10.  Once approved, merge. You can also optionally delete your branch after it's merged. The site will be automatically built and deployed.

# Editing content

1. Make a new branch off of main.
2. Pull and checkout your branch.
3. Open in a terminal the directory `{REPO_ROOT}/tsuacm`
4. Run the command `hugo server` to run the integrated test server.
    + If you want to show drafts as well, run `hugo server -D` instead.
    + A link to the test server will be shown, and it will update on any changes made.
5. Open the markdown file(s) you want to edit and do so.
    + Note: Style all links to external sources with the following shortcode: `{{< externallink url="https://example.com" text="The Link Text" title="Hover Text" >}}`
        + `url` is the URL to link to
        + `text` is the text (or other HTML contents) of the link
        + `title` is optional and is the text shown on hover
6. Put any static resources (images, other things that don't need to be processed) in the `static` folder.
    + Things in this folder are hosted starting from the site root.
    + For example, `static/images/myimage.png` is hosted at `https://mysite.com/images/myimage.png`
    + Link to these items with relative URLs from the site root: `/images/myimage.png`
7. When the changes are as you like them, commit and push to your branch. ***DO NOT BUILD THE SITE ON YOUR MACHINE WITH THE `hugo` COMMAND!*** The GitHub servers will do this for you.
8. Create a PR from your branch to main. It will automatically run a build against your branch to make sure it works. An approval and successful build are required before a merge.
9.  Once approved, merge. You can also optionally delete your branch after it's merged. The site will be automatically built and deployed.

# Adding new FontAwesome Icons

1. Download SVGs from https://github.com/FortAwesome/Font-Awesome/tree/master/svgs
2. Place them in the /fontawesome directory
3. Call them using the shortcode `{{% fontawesome name %}}` where `name` is the filename without the `.svg` extension.
