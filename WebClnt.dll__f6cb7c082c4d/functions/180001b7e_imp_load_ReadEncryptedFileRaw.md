# __imp_load_ReadEncryptedFileRaw

- ea: `0x180001b7e`
- end: `0x180001b8a`
- name: `__imp_load_ReadEncryptedFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001adb`

## import_xrefs

- `ADVAPI32!ReadEncryptedFileRaw` at `0x180001b7e`

## pseudocode

```c
__int64 load_ReadEncryptedFileRaw()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180001b7e  lea     rax, __imp_ReadEncryptedFileRaw
0x180001b85  jmp     __tailMerge_advapi32_dll
```
