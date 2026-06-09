# __imp_load_OpenProvisioningPackageForRead

- ea: `0x14000215f`
- end: `0x14000216b`
- name: `__imp_load_OpenProvisioningPackageForRead`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1400020e0`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x14000215f`

## pseudocode

```c
__int64 load_OpenProvisioningPackageForRead()
{
  return _tailMerge_provpackageapidll_dll();
}

```

## disassembly

```asm
0x14000215f  lea     rax, __imp_OpenProvisioningPackageForRead
0x140002166  jmp     __tailMerge_provpackageapidll_dll
```
