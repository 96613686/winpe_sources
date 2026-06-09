# __imp_load_FwGetService

- ea: `0x180020754`
- end: `0x180020760`
- name: `__imp_load_FwGetService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwGetService` at `0x180020754`

## pseudocode

```c
__int64 load_FwGetService()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020754  lea     rax, __imp_FwGetService
0x18002075b  jmp     __tailMerge_fwbase_dll
```
