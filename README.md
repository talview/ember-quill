# Ember-Quill

This project was created by forking ember-quill because they were using an older build of Quill Text Editor - Quill.js (1.3.6) which had a potential threat to reverse tabnabbing attacks. This project implements the latest build of Quill.js (1.3.7).
The develop branch of this project is being used to install ember-quill package with latest version of Quill.js

## Installation

* `ember install ember-quill`

## Component example
```javascript
import Ember from 'ember';

export default Ember.Component.extend({
  options: {
    theme: "snow",
    modules: {
      toolbar: [
        [{header: [2, 3, 4, false]}],
        ["bold", "italic", "underline", "strike"],
        [{"color": []}],
        [{"list": "ordered"}, {"list": "bullet"}],
        [{"indent": "-1"}, {"indent": "+1"}],
        [{"align": []}],
        ["link"],
        ["clean"]
      ]
    }
  },

  actions: {
    updateText(editor) {
      this.attrs.update(editor.root.innerHTML);
    }
  }
});

```

## Template example
```hbs
{{quill-editor value=value options=options textChange=(action "updateText")}}
```

## License
The `ember-quill` is under the Apache 2.0 license
