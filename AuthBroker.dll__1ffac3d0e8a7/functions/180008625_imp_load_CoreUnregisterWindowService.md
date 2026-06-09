# __imp_load_CoreUnregisterWindowService

- ea: `0x180008625`
- end: `0x180008631`
- name: `__imp_load_CoreUnregisterWindowService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`

## import_xrefs

- `twinapi.appcore!__imp_CoreUnregisterWindowService` at `0x180008625`

## pseudocode

```c
__int64 load_CoreUnregisterWindowService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x180008625  lea     rax, __imp_CoreUnregisterWindowService
0x18000862c  jmp     __tailMerge_twinapi_appcore_dll
```
