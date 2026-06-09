# __imp_load_FwIcfAuthBypassServicesDestroy

- ea: `0x1800207c0`
- end: `0x1800207cc`
- name: `__imp_load_FwIcfAuthBypassServicesDestroy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwIcfAuthBypassServicesDestroy` at `0x1800207c0`

## pseudocode

```c
__int64 load_FwIcfAuthBypassServicesDestroy()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800207c0  lea     rax, __imp_FwIcfAuthBypassServicesDestroy
0x1800207c7  jmp     __tailMerge_fwbase_dll
```
