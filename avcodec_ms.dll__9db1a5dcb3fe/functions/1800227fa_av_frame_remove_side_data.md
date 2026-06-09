# av_frame_remove_side_data

- ea: `0x1800227fa`
- end: `0x180022800`
- name: `av_frame_remove_side_data`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180007740`

## import_xrefs

- `avutil_ms!av_frame_remove_side_data` at `0x1800227fa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_remove_side_data(__int64 a1, __int64 a2)
{
  return __imp_av_frame_remove_side_data(a1, a2);
}

```

## disassembly

```asm
0x1800227fa  jmp     cs:__imp_av_frame_remove_side_data
```
