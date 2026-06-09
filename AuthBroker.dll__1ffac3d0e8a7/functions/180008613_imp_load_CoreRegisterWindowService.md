# __imp_load_CoreRegisterWindowService

- ea: `0x180008613`
- end: `0x18000861f`
- name: `__imp_load_CoreRegisterWindowService`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`

## import_xrefs

- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x180008613`

## pseudocode

```c
__int64 load_CoreRegisterWindowService()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x180008613  lea     rax, __imp_CoreRegisterWindowService
0x18000861a  jmp     __tailMerge_twinapi_appcore_dll
```
