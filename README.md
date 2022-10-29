# Project 7 - WordPress Pen Testing

Time spent: **15** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pen Testing Report

### 1. WordPress 2.5-4.6 Authenticated Stored Cross-Site Scripting via Image FileName

- [X] Summary: 
  - Vulnerability types: Cross-Site Scripting XSS
  - Tested in version: 4.2
  - Fixed in version: 4.2.10
- [X] GIF Walkthrough:
- <img src='https://i.imgur.com/8oELbWd.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [X] Steps to recreate: Insert an image file with the title as: ```a<img src=a ONERROR=alert('pranked!!')>```. Now, viewing a page with that image will trigger a JS alert.
- [X] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2.2/src/wp-admin/includes/media.php)
  
### 2. Wordpress <= 4.2 Unauthenticated Stored Cross-Site Scripting

- [X] Summary:
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.2.1
- [X] GIF Walkthrough:
- <img src='https://i.imgur.com/Aaie6Bl.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [X] Steps to recreate: Write a javascript line onto a comment. In this case, we wrote ```<a title='x onmouseover=alert(unescape(/gonna%20hack%20u!!!!/.source)) iamsoswag``` as a comment. Hovering over the box triggers an alert.
- [X] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/wp-db.php)

### 3. WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds

- [X] Summary: 
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.2.13
- [X] GIF Walkthrough:
- <img src='https://i.imgur.com/7ZHZazd.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [X] Steps to recreate: Write the following line in the body of a page or post: [embed src='https://youtube.com/embed/42069\x3csvg onload=alert(420)\x3e'][/embed]
- [X] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/4.2/src/wp-includes/media.php)

### 4. WP < 6.0.3 - Data Exposure via REST Terms/Tags Endpoint

- [X] Summary: 
  - Vulnerability types: Information Exposure
  - Tested in version: 4.2
  - Fixed in version: 4.2.34
- [X] GIF Walkthrough:
- <img src='https://i.imgur.com/Zgt0wT1.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [X] Steps to recreate: Follow the link: http://wpdistillery.vm/wp-admin/js/  
- [X] Affected source code:
  - [Link 1](https://github.com/WordPress/wordpress-develop/commit/ebaac57a9ac0174485c65de3d32ea56de2330d8e)

### 5. (Optional) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough:
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with  ...
<!-- Recommended GIF Tools:
[Kap](https://getkap.co/) for macOS
[ScreenToGif](https://www.screentogif.com/) for Windows
[peek](https://github.com/phw/peek) for Linux. -->

## Notes

Describe any challenges encountered while doing the work
- Trying to find the vulnerabilities and a hint on where to start. Once I figured out part of the puzzle, it was clear what I should be doing.

## License

    Copyright [2022] [Rex Tabora]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
