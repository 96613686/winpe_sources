# __imp_load_EventWriteTransfer

- ea: `0x180025954`
- end: `0x180025960`
- name: `__imp_load_EventWriteTransfer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800258aa`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180025954`

## pseudocode

```c
__int64 load_EventWriteTransfer()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180025954  lea     rax, __imp_EventWriteTransfer
0x18002595b  jmp     __tailMerge_advapi32_dll
```
