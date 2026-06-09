# __imp_load_SamOpenDomain

- ea: `0x180010239`
- end: `0x180010245`
- name: `__imp_load_SamOpenDomain`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010184`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x180010239`

## pseudocode

```c
__int64 load_SamOpenDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x180010239  lea     rax, __imp_SamOpenDomain
0x180010240  jmp     __tailMerge_samlib_dll
```
