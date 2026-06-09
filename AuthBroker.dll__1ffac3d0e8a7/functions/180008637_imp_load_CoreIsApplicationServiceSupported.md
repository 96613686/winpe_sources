# __imp_load_CoreIsApplicationServiceSupported

- ea: `0x180008637`
- end: `0x180008643`
- name: `__imp_load_CoreIsApplicationServiceSupported`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180008570`

## import_xrefs

- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180008637`

## pseudocode

```c
__int64 load_CoreIsApplicationServiceSupported()
{
  return _tailMerge_twinapi_appcore_dll();
}

```

## disassembly

```asm
0x180008637  lea     rax, __imp_CoreIsApplicationServiceSupported
0x18000863e  jmp     __tailMerge_twinapi_appcore_dll
```
