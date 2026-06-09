# LKRhash::CTypedHashTable<CNameToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x1800042f0`
- end: `0x18000431d`
- name: `?_EqualKeys@?$CTypedHashTable@VCNameToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z`
- size: `45`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000430c`
- `KERNEL32!CompareStringW` at `0x18000430c`

## pseudocode

```c
bool __fastcall LKRhash::CTypedHashTable<CNameToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_EqualKeys(
        PCNZWCH lpString1,
        PCNZWCH lpString2)
{
  return CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x1800042f0  sub     rsp, 38h
0x1800042f4  or      r9d, 0FFFFFFFFh; cchCount1
0x1800042f8  mov     r8, rcx; lpString1
0x1800042fb  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180004300  mov     [rsp+38h+lpString2], rdx; lpString2
0x180004305  lea     edx, [r9+2]; dwCmpFlags
0x180004309  lea     ecx, [rdx+7Eh]; Locale
0x18000430c  call    cs:__imp_CompareStringW
0x180004312  cmp     eax, 2
0x180004315  setz    al
0x180004318  add     rsp, 38h
0x18000431c  retn
```
