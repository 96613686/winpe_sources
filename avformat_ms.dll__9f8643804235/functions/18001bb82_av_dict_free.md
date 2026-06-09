# av_dict_free

- ea: `0x18001bb82`
- end: `0x18001bb88`
- name: `av_dict_free`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001810`
- `0x18000219c`
- `0x180002268`
- `0x180006390`
- `0x180007900`
- `0x18000a920`
- `0x18000b4f8`
- `0x180010530`
- `0x180010550`
- `0x180012028`
- `0x180013478`
- `0x180018b68`

## import_xrefs

- `avutil_ms!av_dict_free` at `0x18001bb82`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_dict_free(__int64 a1)
{
  return __imp_av_dict_free(a1);
}

```

## disassembly

```asm
0x18001bb82  jmp     cs:__imp_av_dict_free
```
