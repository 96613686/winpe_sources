# av_pix_fmt_desc_get

- ea: `0x1800226e0`
- end: `0x1800226e6`
- name: `av_pix_fmt_desc_get`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004860`
- `0x180006e20`
- `0x180008d8c`
- `0x180009d58`
- `0x1800124c0`
- `0x180012560`

## import_xrefs

- `avutil_ms!av_pix_fmt_desc_get` at `0x1800226e0`

## pseudocode

```c
// attributes: thunk
__int64 av_pix_fmt_desc_get()
{
  return __imp_av_pix_fmt_desc_get();
}

```

## disassembly

```asm
0x1800226e0  jmp     cs:__imp_av_pix_fmt_desc_get
```
