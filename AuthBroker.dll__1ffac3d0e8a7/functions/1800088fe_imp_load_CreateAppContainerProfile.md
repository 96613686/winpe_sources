# __imp_load_CreateAppContainerProfile

- ea: `0x1800088fe`
- end: `0x18000890a`
- name: `__imp_load_CreateAppContainerProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008849`

## import_xrefs

- `USERENV!CreateAppContainerProfile` at `0x1800088fe`

## pseudocode

```c
__int64 load_CreateAppContainerProfile()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x1800088fe  lea     rax, __imp_CreateAppContainerProfile
0x180008905  jmp     __tailMerge_userenv_dll
```
