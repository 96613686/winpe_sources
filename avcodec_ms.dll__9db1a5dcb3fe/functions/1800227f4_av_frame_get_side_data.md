# av_frame_get_side_data

- ea: `0x1800227f4`
- end: `0x1800227fa`
- name: `av_frame_get_side_data`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180007740`
- `0x180007ad8`
- `0x1800084a8`
- `0x180008b54`
- `0x18000a128`

## import_xrefs

- `avutil_ms!av_frame_get_side_data` at `0x1800227f4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_get_side_data(__int64 a1, __int64 a2)
{
  return __imp_av_frame_get_side_data(a1, a2);
}

```

## disassembly

```asm
0x1800227f4  jmp     cs:__imp_av_frame_get_side_data
```
