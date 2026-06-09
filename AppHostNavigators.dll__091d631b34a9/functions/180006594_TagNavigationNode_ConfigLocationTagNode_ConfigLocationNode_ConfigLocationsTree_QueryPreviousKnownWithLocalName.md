# TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryPreviousKnownWithLocalName(ushort const *)

- ea: `0x180006594`
- end: `0x180006627`
- name: `?QueryPreviousKnownWithLocalName@?$TagNavigationNode@VConfigLocationTagNode@@VConfigLocationNode@@VConfigLocationsTree@@@@AEAAPEAVConfigLocationTagNode@@PEBG@Z`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006200`
- `0x180009d54`
- `0x180009e80`

## callees

- `0x180006594`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigLocationTagNode,ConfigLocationNode,ConfigLocationsTree>::QueryPreviousKnownWithLocalName(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 i; // rdx

  if ( NavigationNodeBase::IsWildCardName(a2) )
    return (*(_QWORD *)(v2 + 48) - 40LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 48) - 32LL) < *(_DWORD *)(v2 + 8));
  if ( *(_QWORD *)(v2 + 16) == v3 && *(_QWORD *)(v2 + 56) )
    return (*(_QWORD *)(v2 + 64) - 56LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 64) - 48LL) < *(_DWORD *)(v2 + 8));
  for ( i = (*(_QWORD *)(v2 + 48) - 40LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 48) - 32LL) < *(_DWORD *)(v2 + 8));
        i;
        i = (*(_QWORD *)(i + 48) - 40LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(i + 48) - 40LL + 8) < *(_DWORD *)(i + 8)) )
  {
    if ( *(_QWORD *)(i + 16) == v3 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x180006594  sub     rsp, 28h
0x180006598  mov     r8, rcx
0x18000659b  mov     r9, rdx
0x18000659e  mov     rcx, rdx; unsigned __int16 *
0x1800065a1  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x1800065a6  test    al, al
0x1800065a8  jz      short loc_1800065C1
0x1800065aa  mov     rax, [r8+30h]
0x1800065ae  mov     edx, [rax-20h]
0x1800065b1  lea     rcx, [rax-28h]
0x1800065b5  cmp     edx, [r8+8]
0x1800065b9  sbb     rax, rax
0x1800065bc  and     rax, rcx
0x1800065bf  jmp     short loc_180006622
0x1800065c1  cmp     [r8+10h], r9
0x1800065c5  jnz     short loc_1800065E5
0x1800065c7  cmp     qword ptr [r8+38h], 0
0x1800065cc  jz      short loc_1800065E5
0x1800065ce  mov     rax, [r8+40h]
0x1800065d2  mov     ecx, [rax-30h]
0x1800065d5  lea     rdx, [rax-38h]
0x1800065d9  cmp     ecx, [r8+8]
0x1800065dd  sbb     rax, rax
0x1800065e0  and     rax, rdx
0x1800065e3  jmp     short loc_180006622
0x1800065e5  mov     rax, [r8+30h]
0x1800065e9  mov     ecx, [rax-20h]
0x1800065ec  add     rax, 0FFFFFFFFFFFFFFD8h
0x1800065f0  cmp     ecx, [r8+8]
0x1800065f4  sbb     rdx, rdx
0x1800065f7  and     rdx, rax
0x1800065fa  test    rdx, rdx
0x1800065fd  jz      short loc_180006620
0x1800065ff  cmp     [rdx+10h], r9
0x180006603  jz      short loc_18000661B
0x180006605  mov     rcx, [rdx+30h]
0x180006609  mov     eax, [rdx+8]
0x18000660c  add     rcx, 0FFFFFFFFFFFFFFD8h
0x180006610  cmp     [rcx+8], eax
0x180006613  sbb     rdx, rdx
0x180006616  and     rdx, rcx
0x180006619  jmp     short loc_1800065FA
0x18000661b  mov     rax, rdx
0x18000661e  jmp     short loc_180006622
0x180006620  xor     eax, eax
0x180006622  add     rsp, 28h
0x180006626  retn
```
