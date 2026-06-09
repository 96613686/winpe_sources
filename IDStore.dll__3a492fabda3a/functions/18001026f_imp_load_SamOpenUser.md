# __imp_load_SamOpenUser

- ea: `0x18001026f`
- end: `0x18001027b`
- name: `__imp_load_SamOpenUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010184`

## import_xrefs

- `SAMLIB!SamOpenUser` at `0x18001026f`

## pseudocode

```c
__int64 load_SamOpenUser()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18001026f  lea     rax, __imp_SamOpenUser
0x180010276  jmp     __tailMerge_samlib_dll
```
