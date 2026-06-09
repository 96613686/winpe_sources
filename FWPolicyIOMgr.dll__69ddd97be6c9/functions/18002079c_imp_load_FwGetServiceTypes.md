# __imp_load_FwGetServiceTypes

- ea: `0x18002079c`
- end: `0x1800207a8`
- name: `__imp_load_FwGetServiceTypes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwGetServiceTypes` at `0x18002079c`

## pseudocode

```c
__int64 load_FwGetServiceTypes()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x18002079c  lea     rax, __imp_FwGetServiceTypes
0x1800207a3  jmp     __tailMerge_fwbase_dll
```
