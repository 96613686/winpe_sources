# __imp_load_NetpwPathCanonicalize

- ea: `0x180005424`
- end: `0x180005430`
- name: `__imp_load_NetpwPathCanonicalize`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800053a5`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x180005424`

## pseudocode

```c
__int64 load_NetpwPathCanonicalize()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x180005424  lea     rax, __imp_NetpwPathCanonicalize
0x18000542b  jmp     __tailMerge_netutils_dll
```
