# gloam-registry

Supplemental Khronos-style XML registry data for
[gloam](https://github.com/tycho/gloam), the C loader generator for
Vulkan, OpenGL, OpenGL ES, EGL, GLX, and WGL.

## xml/glsl_exts.xml

GL and GLES extensions that are documented in the OpenGL registry but are
absent from `gl.xml` because they only affect GLSL — they define no new API
commands or enums. A loader still wants their names in its extension table
so applications can detect them at runtime before compiling shaders that
require them.

Entries use the same `<extension name="..." supported="...">` form as
`gl.xml`; gloam merges this file as a supplemental document when parsing
the GL spec.

## Why a separate repository?

This data is versioned independently of gloam so that `gloam --fetch`
picks up newly added extensions immediately, without waiting for a gloam
release. Bundled copies inside gloam are refreshed from this repository by
the same mechanism used for the Khronos registries.

## License

MIT — see [LICENSE](LICENSE).
