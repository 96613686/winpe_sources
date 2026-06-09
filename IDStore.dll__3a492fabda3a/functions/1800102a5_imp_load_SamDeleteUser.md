# __imp_load_SamDeleteUser

- ea: `0x1800102a5`
- end: `0x1800102b1`
- name: `__imp_load_SamDeleteUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010184`

## import_xrefs

- `SAMLIB!SamDeleteUser` at `0x1800102a5`

## pseudocode

```c
__int64 load_SamDeleteUser()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x1800102a5  lea     rax, __imp_SamDeleteUser
0x1800102ac  jmp     __tailMerge_samlib_dll
```
