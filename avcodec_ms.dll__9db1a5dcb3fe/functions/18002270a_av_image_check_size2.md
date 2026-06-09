# av_image_check_size2

- ea: `0x18002270a`
- end: `0x180022710`
- name: `av_image_check_size2`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004150`
- `0x1800084a8`
- `0x180009fb0`
- `0x180012c34`

## import_xrefs

- `avutil_ms!av_image_check_size2` at `0x18002270a`

## pseudocode

```c
// attributes: thunk
__int64 av_image_check_size2()
{
  return __imp_av_image_check_size2();
}

```

## disassembly

```asm
0x18002270a  jmp     cs:__imp_av_image_check_size2
```
