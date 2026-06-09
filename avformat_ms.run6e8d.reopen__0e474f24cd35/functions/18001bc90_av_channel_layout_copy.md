# av_channel_layout_copy

- ea: `0x18001bc90`
- end: `0x18001bc96`
- name: `av_channel_layout_copy`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a920`

## import_xrefs

- `avutil_ms!av_channel_layout_copy` at `0x18001bc90`

## pseudocode

```c
// attributes: thunk
__int64 av_channel_layout_copy()
{
  return __imp_av_channel_layout_copy();
}

```

## disassembly

```asm
0x18001bc90  jmp     cs:__imp_av_channel_layout_copy
```
