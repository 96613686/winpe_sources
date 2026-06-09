# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryPreviousKnownWithLocalName(ushort const *)

- ea: `0x180005684`
- end: `0x180005717`
- name: `?QueryPreviousKnownWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004f90`
- `0x18000c3b0`

## callees

- `0x180005684`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryPreviousKnownWithLocalName(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 i; // rdx

  if ( NavigationNodeBase::IsWildCardName(a2) )
    return (*(_QWORD *)(v2 + 64) - 56LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 64) - 48LL) < *(_DWORD *)(v2 + 8));
  if ( *(_QWORD *)(v2 + 16) == v3 && *(_QWORD *)(v2 + 72) )
    return (*(_QWORD *)(v2 + 80) - 72LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 80) - 64LL) < *(_DWORD *)(v2 + 8));
  for ( i = (*(_QWORD *)(v2 + 64) - 56LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(v2 + 64) - 48LL) < *(_DWORD *)(v2 + 8));
        i;
        i = (*(_QWORD *)(i + 64) - 56LL) & -(__int64)(*(_DWORD *)(*(_QWORD *)(i + 64) - 56LL + 8) < *(_DWORD *)(i + 8)) )
  {
    if ( *(_QWORD *)(i + 16) == v3 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x180005684  sub     rsp, 28h
0x180005688  mov     r8, rcx
0x18000568b  mov     r9, rdx
0x18000568e  mov     rcx, rdx; unsigned __int16 *
0x180005691  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x180005696  test    al, al
0x180005698  jz      short loc_1800056B1
0x18000569a  mov     rax, [r8+40h]
0x18000569e  mov     edx, [rax-30h]
0x1800056a1  lea     rcx, [rax-38h]
0x1800056a5  cmp     edx, [r8+8]
0x1800056a9  sbb     rax, rax
0x1800056ac  and     rax, rcx
0x1800056af  jmp     short loc_180005712
0x1800056b1  cmp     [r8+10h], r9
0x1800056b5  jnz     short loc_1800056D5
0x1800056b7  cmp     qword ptr [r8+48h], 0
0x1800056bc  jz      short loc_1800056D5
0x1800056be  mov     rax, [r8+50h]
0x1800056c2  mov     ecx, [rax-40h]
0x1800056c5  lea     rdx, [rax-48h]
0x1800056c9  cmp     ecx, [r8+8]
0x1800056cd  sbb     rax, rax
0x1800056d0  and     rax, rdx
0x1800056d3  jmp     short loc_180005712
0x1800056d5  mov     rax, [r8+40h]
0x1800056d9  mov     ecx, [rax-30h]
0x1800056dc  add     rax, 0FFFFFFFFFFFFFFC8h
0x1800056e0  cmp     ecx, [r8+8]
0x1800056e4  sbb     rdx, rdx
0x1800056e7  and     rdx, rax
0x1800056ea  test    rdx, rdx
0x1800056ed  jz      short loc_180005710
0x1800056ef  cmp     [rdx+10h], r9
0x1800056f3  jz      short loc_18000570B
0x1800056f5  mov     rcx, [rdx+40h]
0x1800056f9  mov     eax, [rdx+8]
0x1800056fc  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180005700  cmp     [rcx+8], eax
0x180005703  sbb     rdx, rdx
0x180005706  and     rdx, rcx
0x180005709  jmp     short loc_1800056EA
0x18000570b  mov     rax, rdx
0x18000570e  jmp     short loc_180005712
0x180005710  xor     eax, eax
0x180005712  add     rsp, 28h
0x180005716  retn
```
