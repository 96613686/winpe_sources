# __imp_load_OpenEncryptedFileRawW

- ea: `0x180001c56`
- end: `0x180001c62`
- name: `__imp_load_OpenEncryptedFileRawW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001adb`

## import_xrefs

- `ADVAPI32!OpenEncryptedFileRawW` at `0x180001c56`

## pseudocode

```c
__int64 load_OpenEncryptedFileRawW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180001c56  lea     rax, __imp_OpenEncryptedFileRawW
0x180001c5d  jmp     __tailMerge_advapi32_dll
```
