# __imp_load_WriteEncryptedFileRaw

- ea: `0x180001c44`
- end: `0x180001c50`
- name: `__imp_load_WriteEncryptedFileRaw`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001adb`

## import_xrefs

- `ADVAPI32!WriteEncryptedFileRaw` at `0x180001c44`

## pseudocode

```c
__int64 load_WriteEncryptedFileRaw()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180001c44  lea     rax, __imp_WriteEncryptedFileRaw
0x180001c4b  jmp     __tailMerge_advapi32_dll
```
