# __imp_load_WlanPrivateDeleteProfile

- ea: `0x18002ae21`
- end: `0x18002ae2d`
- name: `__imp_load_WlanPrivateDeleteProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002abfd`

## import_xrefs

- `wlanapi!WlanPrivateDeleteProfile` at `0x18002ae21`

## pseudocode

```c
__int64 load_WlanPrivateDeleteProfile()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x18002ae21  lea     rax, __imp_WlanPrivateDeleteProfile
0x18002ae28  jmp     __tailMerge_wlanapi_dll
```
