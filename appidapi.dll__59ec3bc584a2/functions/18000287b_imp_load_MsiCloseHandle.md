# __imp_load_MsiCloseHandle

- ea: `0x18000287b`
- end: `0x180002887`
- name: `__imp_load_MsiCloseHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800027b4`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18000287b`

## pseudocode

```c
__int64 load_MsiCloseHandle()
{
  return _tailMerge_msi_dll();
}

```

## disassembly

```asm
0x18000287b  lea     rax, __imp_MsiCloseHandle
0x180002882  jmp     __tailMerge_msi_dll
```
