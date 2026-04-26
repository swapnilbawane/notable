# Notable — A Simple Microblog

A static blog. No build step. No framework. Just files.

---

## Setup on GitHub Pages

1. Create a new GitHub repo (e.g. `notable`)
2. Upload all these files into the repo root
3. Go to **Settings → Pages → Source → main branch / root**
4. Your blog will be live at `https://yourusername.github.io/notable/`

---

## How to write a post

### Step 1 — Create the post file

Create a new file in the `posts/` folder. Name it with a slug (no spaces, use hyphens):

```
posts/my-new-post.json
```

Paste and fill in this template:

```json
{
  "id": "my-new-post",
  "title": "Your post title here",
  "date": "2026-05-01",
  "tag": "learning",
  "image": "",
  "body": "First paragraph text here.\n\nSecond paragraph here.\n\nThird paragraph here."
}
```

**Fields:**
- `id` — same as the filename without `.json`
- `title` — shown on listing and post page
- `date` — format: `YYYY-MM-DD`
- `tag` — optional label (e.g. `learning`, `note`, `idea`). Leave as `""` to hide.
- `image` — optional. If you have a photo, put the filename here (e.g. `"my-photo.jpg"`). Upload the image to the `images/` folder. Leave as `""` for text-only posts.
- `body` — your full post text. Use `\n\n` (two newlines) to separate paragraphs.

### Step 2 — Add to the index

Open `posts/index.json` and add your post to the **top** of the list (newest first):

```json
[
  {
    "id": "my-new-post",
    "title": "Your post title here",
    "date": "2026-05-01",
    "tag": "learning",
    "excerpt": "First sentence or two of your post, for the listing preview.",
    "image": ""
  },
  ...existing posts...
]
```

### Step 3 — Commit and push

GitHub Pages will update automatically within a minute.

---

## Adding images

1. Upload your image to the `images/` folder
2. In the post JSON, set `"image": "your-filename.jpg"`
3. In `posts/index.json`, set the same `"image"` value to show a thumbnail on the listing

Recommended image size: 1200×800px or similar. It will be cropped and displayed responsively.

---

## Folder structure

```
/
├── index.html          ← Blog home (post listing)
├── post.html           ← Single post view (shared by all posts)
├── posts/
│   ├── index.json      ← Master list of posts (edit this when adding)
│   └── my-post.json    ← Individual post files
└── images/
    └── my-photo.jpg    ← Optional images for posts
```

---

That's it. No npm. No build. No config.
