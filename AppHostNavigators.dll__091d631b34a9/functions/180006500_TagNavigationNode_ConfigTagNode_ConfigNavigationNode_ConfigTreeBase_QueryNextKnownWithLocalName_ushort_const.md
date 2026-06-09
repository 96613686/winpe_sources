# TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(ushort const *)

- ea: `0x180006500`
- end: `0x18000658b`
- name: `?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@AEAAPEAVConfigTagNode@@PEBG@Z`
- size: `139`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800061a0`
- `0x180006360`
- `0x18000a080`
- `0x18000acd0`
- `0x18000aea0`
- `0x18000b6d0`

## callees

- `0x180006500`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::QueryNextKnownWithLocalName(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v5; // rcx
  bool v6; // cf
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 i; // rdx

  if ( NavigationNodeBase::IsWildCardName(a2) )
  {
    v4 = *(_QWORD *)(v2 + 40);
    v5 = v4 - 40;
    v6 = *(_DWORD *)(v2 + 8) < *(_DWORD *)(v4 - 32);
    return v5 & -(__int64)v6;
  }
  if ( *(_QWORD *)(v2 + 16) == v3 )
  {
    v8 = *(_QWORD *)(v2 + 56);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v8 - 48);
      v5 = v8 - 56;
      v6 = *(_DWORD *)(v2 + 8) < v9;
      return v5 & -(__int64)v6;
    }
  }
  for ( i = (*(_QWORD *)(v2 + 40) - 40LL) & -(__int64)(*(_DWORD *)(v2 + 8) < *(_DWORD *)(*(_QWORD *)(v2 + 40) - 32LL));
        i;
        i = (*(_QWORD *)(i + 40) - 40LL) & -(__int64)(*(_DWORD *)(i + 8) < *(_DWORD *)(*(_QWORD *)(i + 40) - 40LL + 8)) )
  {
    if ( *(_QWORD *)(i + 16) == v3 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x180006500  sub     rsp, 28h
0x180006504  mov     r8, rcx
0x180006507  mov     r9, rdx
0x18000650a  mov     rcx, rdx; unsigned __int16 *
0x18000650d  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x180006512  test    al, al
0x180006514  jz      short loc_18000652D
0x180006516  mov     rax, [r8+28h]
0x18000651a  mov     edx, [rax-20h]
0x18000651d  lea     rcx, [rax-28h]
0x180006521  cmp     [r8+8], edx
0x180006525  sbb     rax, rax
0x180006528  and     rax, rcx
0x18000652b  jmp     short loc_180006586
0x18000652d  cmp     [r8+10h], r9
0x180006531  jnz     short loc_180006549
0x180006533  mov     rcx, [r8+38h]
0x180006537  test    rcx, rcx
0x18000653a  jz      short loc_180006549
0x18000653c  mov     eax, [rcx-30h]
0x18000653f  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180006543  cmp     [r8+8], eax
0x180006547  jmp     short loc_180006525
0x180006549  mov     rax, [r8+28h]
0x18000654d  mov     ecx, [rax-20h]
0x180006550  add     rax, 0FFFFFFFFFFFFFFD8h
0x180006554  cmp     [r8+8], ecx
0x180006558  sbb     rdx, rdx
0x18000655b  and     rdx, rax
0x18000655e  test    rdx, rdx
0x180006561  jz      short loc_180006584
0x180006563  cmp     [rdx+10h], r9
0x180006567  jz      short loc_18000657F
0x180006569  mov     rcx, [rdx+28h]
0x18000656d  add     rcx, 0FFFFFFFFFFFFFFD8h
0x180006571  mov     eax, [rcx+8]
0x180006574  cmp     [rdx+8], eax
0x180006577  sbb     rdx, rdx
0x18000657a  and     rdx, rcx
0x18000657d  jmp     short loc_18000655E
0x18000657f  mov     rax, rdx
0x180006582  jmp     short loc_180006586
0x180006584  xor     eax, eax
0x180006586  add     rsp, 28h
0x18000658a  retn
```
