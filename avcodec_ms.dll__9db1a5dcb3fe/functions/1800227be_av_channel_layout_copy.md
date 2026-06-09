# av_channel_layout_copy

- ea: `0x1800227be`
- end: `0x1800227c4`
- name: `av_channel_layout_copy`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180006380`
- `0x1800064a0`
- `0x180006660`
- `0x180008918`
- `0x18000aa50`
- `0x180011810`
- `0x180015540`
- `0x1800158e0`

## import_xrefs

- `avutil_ms!av_channel_layout_copy` at `0x1800227be`

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
0x1800227be  jmp     cs:__imp_av_channel_layout_copy
```
