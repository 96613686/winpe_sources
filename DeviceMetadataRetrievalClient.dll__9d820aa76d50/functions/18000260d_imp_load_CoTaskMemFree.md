# __imp_load_CoTaskMemFree

- ea: `0x18000260d`
- end: `0x180002619`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002558`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000260d`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000260d  lea     rax, __imp_CoTaskMemFree
0x180002614  jmp     __tailMerge_ole32_dll
```
