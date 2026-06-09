# av_frame_new_side_data

- ea: `0x1800227ee`
- end: `0x1800227f4`
- name: `av_frame_new_side_data`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180007740`
- `0x180008b54`

## import_xrefs

- `avutil_ms!av_frame_new_side_data` at `0x1800227ee`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_new_side_data(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_frame_new_side_data(a1, a2, a3);
}

```

## disassembly

```asm
0x1800227ee  jmp     cs:__imp_av_frame_new_side_data
```
