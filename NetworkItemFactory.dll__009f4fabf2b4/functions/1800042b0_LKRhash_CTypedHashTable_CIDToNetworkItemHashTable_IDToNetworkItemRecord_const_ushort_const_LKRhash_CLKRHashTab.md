# LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,ushort const *,LKRhash::CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x1800042b0`
- end: `0x1800042db`
- name: `?_EqualKeys@?$CTypedHashTable@VCIDToNetworkItemHashTable@@$$CBVIDToNetworkItemRecord@@PEBGVCLKRHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z`
- size: `43`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800042ca`
- `KERNEL32!CompareStringW` at `0x1800042ca`

## pseudocode

```c
bool __fastcall LKRhash::CTypedHashTable<CIDToNetworkItemHashTable,IDToNetworkItemRecord const,unsigned short const *,LKRhash::CLKRHashTable>::_EqualKeys(
        PCNZWCH lpString1,
        PCNZWCH lpString2)
{
  return CompareStringW(0x7Fu, 0, lpString1, -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x1800042b0  sub     rsp, 38h
0x1800042b4  or      r9d, 0FFFFFFFFh; cchCount1
0x1800042b8  mov     r8, rcx; lpString1
0x1800042bb  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800042c0  mov     [rsp+38h+lpString2], rdx; lpString2
0x1800042c5  xor     edx, edx; dwCmpFlags
0x1800042c7  lea     ecx, [rdx+7Fh]; Locale
0x1800042ca  call    cs:__imp_CompareStringW
0x1800042d0  cmp     eax, 2
0x1800042d3  setz    al
0x1800042d6  add     rsp, 38h
0x1800042da  retn
```
