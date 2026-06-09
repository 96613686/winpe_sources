# __imp_load_CreateEnvBlock

- ea: `0x14000429a`
- end: `0x1400042a6`
- name: `__imp_load_CreateEnvBlock`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000421b`

## import_xrefs

- `profapi!__imp_CreateEnvBlock` at `0x14000429a`

## pseudocode

```c
__int64 load_CreateEnvBlock()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x14000429a  lea     rax, __imp_CreateEnvBlock
0x1400042a1  jmp     __tailMerge_profapi_dll
```
