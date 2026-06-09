# __imp_load_?CHSPinYinHelper_CreateInstance@@YAJPEAPEAUICHSPinYinHelper@@@Z

- ea: `0x1800024a2`
- end: `0x1800024ae`
- name: `__imp_load_?CHSPinYinHelper_CreateInstance@@YAJPEAPEAUICHSPinYinHelper@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023c9`

## import_xrefs

- `UserDataLanguageUtil!CHSPinYinHelper_CreateInstance` at `0x1800024a2`

## pseudocode

```c
__int64 load__CHSPinYinHelper_CreateInstance__YAJPEAPEAUICHSPinYinHelper___Z()
{
  return _tailMerge_userdatalanguageutil_dll();
}

```

## disassembly

```asm
0x1800024a2  lea     rax, __imp_?CHSPinYinHelper_CreateInstance@@YAJPEAPEAUICHSPinYinHelper@@@Z; CHSPinYinHelper_CreateInstance(ICHSPinYinHelper * *)
0x1800024a9  jmp     __tailMerge_userdatalanguageutil_dll
```
