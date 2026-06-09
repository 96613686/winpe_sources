# __imp_load_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ

- ea: `0x180002252`
- end: `0x18000225e`
- name: `__imp_load_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002034`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180002252`

## pseudocode

```c
__int64 load__LCIEIsCurrentProcessUsingInPrivateComponents__YA_NXZ()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x180002252  lea     rax, __imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180002259  jmp     __tailMerge_iertutil_dll
```
