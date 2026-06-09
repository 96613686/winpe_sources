# __imp_load_CoreQueryWindowService

- ea: `0x180008601`
- end: `0x18000860d`
- name: `__imp_load_CoreQueryWindowService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`

## import_xrefs

- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180008601`

## pseudocode

```c
__int64 load_CoreQueryWindowService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x180008601  lea     rax, __imp_CoreQueryWindowService
0x180008608  jmp     __tailMerge_twinapi_appcore_dll
```
