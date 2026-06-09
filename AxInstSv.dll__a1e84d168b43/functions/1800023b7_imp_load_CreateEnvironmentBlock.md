# __imp_load_CreateEnvironmentBlock

- ea: `0x1800023b7`
- end: `0x1800023c3`
- name: `__imp_load_CreateEnvironmentBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002338`

## import_xrefs

- `USERENV!CreateEnvironmentBlock` at `0x1800023b7`

## pseudocode

```c
__int64 load_CreateEnvironmentBlock()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x1800023b7  lea     rax, __imp_CreateEnvironmentBlock
0x1800023be  jmp     __tailMerge_userenv_dll
```
