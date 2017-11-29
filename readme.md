## Installation

```bash
npm install --save gulp-image-set-plus
```

## Usage

```bash
var gulp = require('gulp')
var imageSet = require('gulp-image-set-plus')

gulp.task('image-set', function () {
  return gulp.src('my-file.css')
    .pipe(imageSet())
    .pipe(gulp.dest('dist'))
})

gulp.task('default', ['image-set'])
```

### Input

```css
.bg-img {
  background-image: image-set(url('my-img.png') 4x);
}
```

### Output

```css
.bg-img {
  background-image: url('my-img@1x.png');
  background-image: image-set(url('my-img@1x.png') 1x,url('my-img@2x.png') 2x, url('my-img@3x.png') 3x, url('my-img.png') 4x);
}
```