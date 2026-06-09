# CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete::Compare(char const * const &,char const * const &)

- ea: `0x14002ff48`
- end: `0x14002ffa0`
- name: `?Compare@CSusSortedArrayListItemOpsLPCSTRNoDelete@CCabDecompressor@@SAHAEBQEBD0@Z`
- size: `88`
- prototype: `__int64 __fastcall(PCNZCH *, PCNZCH *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002ef38`
- `0x14002ffa8`
- `0x14003022c`

## callees

- `0x14002ff48`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002ff6f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002ff6f`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CSusSortedArrayListItemOpsLPCSTRNoDelete::Compare(PCNZCH *a1, PCNZCH *a2)
{
  int v2; // eax

  if ( *a1 == *a2 )
    return 0;
  v2 = CompareStringA(0x7Fu, 1u, *a1, -1, *a2, -1);
  switch ( v2 )
  {
    case 1:
      return 0xFFFFFFFFLL;
    case 2:
      return 0;
    case 3:
      return 1;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x14002ff48  sub     rsp, 38h
0x14002ff4c  mov     rax, [rdx]
0x14002ff4f  cmp     [rcx], rax
0x14002ff52  jz      short loc_14002FF99
0x14002ff54  mov     r8, [rcx]; lpString1
0x14002ff57  or      r9d, 0FFFFFFFFh; cchCount1
0x14002ff5b  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002ff63  mov     [rsp+38h+lpString2], rax; lpString2
0x14002ff68  lea     edx, [r9+2]; dwCmpFlags
0x14002ff6c  lea     ecx, [rdx+7Eh]; Locale
0x14002ff6f  call    cs:__imp_CompareStringA
0x14002ff75  mov     ecx, eax
0x14002ff77  sub     ecx, 1
0x14002ff7a  jz      short loc_14002FF94
0x14002ff7c  sub     ecx, 1
0x14002ff7f  jz      short loc_14002FF99
0x14002ff81  cmp     ecx, 1
0x14002ff84  jz      short loc_14002FF8D
0x14002ff86  mov     eax, 0FFFFFFFEh
0x14002ff8b  jmp     short loc_14002FF9B
0x14002ff8d  mov     eax, 1
0x14002ff92  jmp     short loc_14002FF9B
0x14002ff94  or      eax, 0FFFFFFFFh
0x14002ff97  jmp     short loc_14002FF9B
0x14002ff99  xor     eax, eax
0x14002ff9b  add     rsp, 38h
0x14002ff9f  retn
```
