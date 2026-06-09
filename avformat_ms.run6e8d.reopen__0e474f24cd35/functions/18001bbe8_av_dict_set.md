# av_dict_set

- ea: `0x18001bbe8`
- end: `0x18001bbee`
- name: `av_dict_set`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180003294`
- `0x1800035d4`
- `0x180006390`
- `0x18000b4f8`
- `0x18000c840`
- `0x18000f4c4`
- `0x180010cb8`
- `0x180010e4c`
- `0x1800119cc`
- `0x180011b7c`
- `0x180011cac`
- `0x180011e78`
- `0x180012028`
- `0x180013478`
- `0x1800184fc`
- `0x1800188e4`

## import_xrefs

- `avutil_ms!av_dict_set` at `0x18001bbe8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_dict_set(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return __imp_av_dict_set(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001bbe8  jmp     cs:__imp_av_dict_set
```
