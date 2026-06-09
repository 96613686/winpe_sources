# __imp_load_CMP_WaitNoPendingInstallEvents

- ea: `0x18000ac8c`
- end: `0x18000ac98`
- name: `__imp_load_CMP_WaitNoPendingInstallEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x18000ac8c`

## pseudocode

```c
__int64 load_CMP_WaitNoPendingInstallEvents()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ac8c  lea     rax, __imp_CMP_WaitNoPendingInstallEvents
0x18000ac93  jmp     __tailMerge_setupapi_dll
```
