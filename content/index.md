```dataview
TABLE WITHOUT ID
file.link AS "제목",
file.overview AS "미리보기",
dateformat(file.mtime, "yyyy.MM.dd HH:m") AS "날짜"
FROM ""
WHERE file != this.file
SORT file.mtime DESC
LIMIT 25
```

```dataviewjs
dv.list(dv.pages()
.where(f => this.currentFilePath !== f.file.path)
.sort(f => f.mdate)
.map(p => p.file.link +  ' - ' + p.file.frontmatter.overview))
```
