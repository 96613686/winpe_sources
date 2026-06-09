# __imp_load_IUnknown_QueryService

- ea: `0x180002493`
- end: `0x18000249f`
- name: `__imp_load_IUnknown_QueryService`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800023f0`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180002493`

## pseudocode

```c
__int64 load_IUnknown_QueryService()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x180002493  lea     rax, __imp_IUnknown_QueryService
0x18000249a  jmp     __tailMerge_shlwapi_dll
```
