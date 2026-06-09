# __imp_load_PathFindFileNameW

- ea: `0x180002328`
- end: `0x180002334`
- name: `__imp_load_PathFindFileNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800022a9`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180002328`

## pseudocode

```c
__int64 load_PathFindFileNameW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x180002328  lea     rax, __imp_PathFindFileNameW
0x18000232f  jmp     __tailMerge_shlwapi_dll
```
