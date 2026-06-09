# av_frame_side_data_free

- ea: `0x180022770`
- end: `0x180022776`
- name: `av_frame_side_data_free`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1800050a4`
- `0x1800104dc`
- `0x18001115c`

## import_xrefs

- `avutil_ms!av_frame_side_data_free` at `0x180022770`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_side_data_free(__int64 a1, __int64 a2)
{
  return __imp_av_frame_side_data_free(a1, a2);
}

```

## disassembly

```asm
0x180022770  jmp     cs:__imp_av_frame_side_data_free
```
