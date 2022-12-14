# README


### How to create a new website repository?

1. Create a new repository with the name `website_xyz` and select `slds-lmu/website_template` as template repository. Alternatively, go to [the template](https://github.com/slds-lmu/website_template) and click `Use this template`. __Make sure that 'Include all branches' is checked.__
2. There should already be a `gh-pages` branch. If not, create it.
3. The `gh-pages` branch should already set as build branch. Therefore, check in `Settings -> Pages` if `gh-pages` is used as built branch.
4. Change all `website_template` entries in the `config.toml` file to your repository name `website_xyz` (this should happen in two places, line 1 the `baseURL` and line 56 the footer url). Also, change the lecture content repository in line 53.
5. The built of the website should already be available at `http://slds-lmu.github.io/website_xyz/`
6. [Optional] Add your website link to the description of the repository to make it accessible more easily.
7. Edit the team page. Remove people not affiliated with the lecture and add add relevant people.
8. Edit your files as described below.

### Edit the content of the website

- Directories and filenames have to be lowercase
- Chapters are ordered after filenames
- if no video is given or no pdf file is present: delete yaml param completely
- to include pdfs, use [pdfjs](https://github.com/anvithks/hugo-embed-pdf-shortcode):
  - __[PREFERRED]__ As URL: `{{< pdfjs file="https://github.com/slds-lmu/lecture_i2ml/blob/master/slides-pdf/slides-regression-losses.pdf" >}}`. If a URL is used, a download button is created instead a preview of the slides.
  - __[ALTERNATIVE]__ For Files: `{{< pdfjs file="slides-regression-losses.pdf" >}}`. The pdf has to be in the same directory as the md file.
- if you add a markdown or html link to a file that is in the same directory
  - you should use the shortcode `{{< fileurl file="cheatsheet_notation.pdf" >}}`
  - if you link to `../file.pdf` it will break in the index pages
- to include lecture video: `{{< video id = "Syrzezpj2FY" >}}`
  - the `video_id` is the last part of the youtube url, e.g. for `https://www.youtube.com/watch?v=BmSvhDCdJro` it is `BmSvhDCdJro`.
  - You can also embed videos from other platforms by changing `video_base_url` in `config.toml`
  - Or use a custom shortcode.
- mathjax enabled if `mathjax: true` in yaml-frontmatter
 - if mathjax should be supported in index page, add it to respective `_index.md` or enable it in `config.toml`
- make quizzes using https://github.com/bonartm/hugo-quiz
  - put `quizdown: true` in yaml-frontmatter
  - quizzes support mathjax without the `mathjax: true`
- in `_index.md` you can specify `show_in_index: (content|summary|none)`

### Merge changes from the template into your website repsitory



## License

[MIT LICENSE](LICENSE)
