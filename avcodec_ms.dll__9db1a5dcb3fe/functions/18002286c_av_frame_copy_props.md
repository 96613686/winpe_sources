# av_frame_copy_props

- ea: `0x18002286c`
- end: `0x180022872`
- name: `av_frame_copy_props`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa50`

## import_xrefs

- `avutil_ms!av_frame_copy_props` at `0x18002286c`

## pseudocode

```c
// attributes: thunk
__int64 av_frame_copy_props()
{
  return __imp_av_frame_copy_props();
}

```

## disassembly

```asm
0x18002286c  jmp     cs:__imp_av_frame_copy_props
```
