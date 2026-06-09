# __imp_load_CoreQueryApplicationService

- ea: `0x1800085ef`
- end: `0x1800085fb`
- name: `__imp_load_CoreQueryApplicationService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`

## import_xrefs

- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800085ef`

## pseudocode

```c
__int64 load_CoreQueryApplicationService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x1800085ef  lea     rax, __imp_CoreQueryApplicationService
0x1800085f6  jmp     __tailMerge_twinapi_appcore_dll
```
