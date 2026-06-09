# __imp_load_FwGetServices

- ea: `0x1800207ae`
- end: `0x1800207ba`
- name: `__imp_load_FwGetServices`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwGetServices` at `0x1800207ae`

## pseudocode

```c
__int64 load_FwGetServices()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800207ae  lea     rax, __imp_FwGetServices
0x1800207b5  jmp     __tailMerge_fwbase_dll
```
