# __imp_load_BiDeleteEvent

- ea: `0x180013a95`
- end: `0x180013aa1`
- name: `__imp_load_BiDeleteEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013a16`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiDeleteEvent` at `0x180013a95`

## pseudocode

```c
__int64 load_BiDeleteEvent()
{
  return _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll();
}

```

## disassembly

```asm
0x180013a95  lea     rax, __imp_BiDeleteEvent
0x180013a9c  jmp     __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll
```
