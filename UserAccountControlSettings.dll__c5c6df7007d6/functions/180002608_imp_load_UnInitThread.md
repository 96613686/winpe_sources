# __imp_load_UnInitThread

- ea: `0x180002608`
- end: `0x180002614`
- name: `__imp_load_UnInitThread`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024c3`

## import_xrefs

- `DUI70!UnInitThread` at `0x180002608`

## pseudocode

```c
__int64 load_UnInitThread()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002608  lea     rax, __imp_UnInitThread
0x18000260f  jmp     __tailMerge_dui70_dll
```
