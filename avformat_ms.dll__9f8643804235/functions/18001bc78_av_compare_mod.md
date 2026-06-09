# av_compare_mod

- ea: `0x18001bc78`
- end: `0x18001bc7e`
- name: `av_compare_mod`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006060`

## import_xrefs

- `avutil_ms!av_compare_mod` at `0x18001bc78`

## pseudocode

```c
// attributes: thunk
__int64 av_compare_mod()
{
  return __imp_av_compare_mod();
}

```

## disassembly

```asm
0x18001bc78  jmp     cs:__imp_av_compare_mod
```
