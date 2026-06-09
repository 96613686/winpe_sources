# av_frame_side_data_clone

- ea: `0x180022806`
- end: `0x18002280c`
- name: `av_frame_side_data_clone`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180007ad8`
- `0x18001115c`

## import_xrefs

- `avutil_ms!av_frame_side_data_clone` at `0x180022806`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_side_data_clone(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return __imp_av_frame_side_data_clone(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180022806  jmp     cs:__imp_av_frame_side_data_clone
```
