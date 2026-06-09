# __imp_load_PathFindFileNameW

- ea: `0x180025ace`
- end: `0x180025ada`
- name: `__imp_load_PathFindFileNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180025a54`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180025ace`

## pseudocode

```c
__int64 load_PathFindFileNameW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x180025ace  lea     rax, __imp_PathFindFileNameW
0x180025ad5  jmp     __tailMerge_shlwapi_dll
```
