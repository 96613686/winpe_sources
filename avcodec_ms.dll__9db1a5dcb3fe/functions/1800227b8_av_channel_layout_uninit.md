# av_channel_layout_uninit

- ea: `0x1800227b8`
- end: `0x1800227be`
- name: `av_channel_layout_uninit`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180006908`
- `0x18000af3c`
- `0x18000e790`
- `0x18000e838`
- `0x180015540`
- `0x1800158e0`

## import_xrefs

- `avutil_ms!av_channel_layout_uninit` at `0x1800227b8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_channel_layout_uninit(__int64 a1)
{
  return __imp_av_channel_layout_uninit(a1);
}

```

## disassembly

```asm
0x1800227b8  jmp     cs:__imp_av_channel_layout_uninit
```
