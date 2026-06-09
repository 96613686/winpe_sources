# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryNextKnownWithLocalName(ushort const *)

- ea: `0x1800055f0`
- end: `0x18000567b`
- name: `?QueryNextKnownWithLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAPEAVConfigPathTagNode@@PEBG@Z`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004f20`
- `0x180005450`

## callees

- `0x1800055f0`
- `0x1800112e4`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::QueryNextKnownWithLocalName(
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
    v4 = *(_QWORD *)(v2 + 56);
    v5 = v4 - 56;
    v6 = *(_DWORD *)(v2 + 8) < *(_DWORD *)(v4 - 48);
    return v5 & -(__int64)v6;
  }
  if ( *(_QWORD *)(v2 + 16) == v3 )
  {
    v8 = *(_QWORD *)(v2 + 72);
    if ( v8 )
    {
      v9 = *(_DWORD *)(v8 - 64);
      v5 = v8 - 72;
      v6 = *(_DWORD *)(v2 + 8) < v9;
      return v5 & -(__int64)v6;
    }
  }
  for ( i = (*(_QWORD *)(v2 + 56) - 56LL) & -(__int64)(*(_DWORD *)(v2 + 8) < *(_DWORD *)(*(_QWORD *)(v2 + 56) - 48LL));
        i;
        i = (*(_QWORD *)(i + 56) - 56LL) & -(__int64)(*(_DWORD *)(i + 8) < *(_DWORD *)(*(_QWORD *)(i + 56) - 56LL + 8)) )
  {
    if ( *(_QWORD *)(i + 16) == v3 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x1800055f0  sub     rsp, 28h
0x1800055f4  mov     r8, rcx
0x1800055f7  mov     r9, rdx
0x1800055fa  mov     rcx, rdx; unsigned __int16 *
0x1800055fd  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x180005602  test    al, al
0x180005604  jz      short loc_18000561D
0x180005606  mov     rax, [r8+38h]
0x18000560a  mov     edx, [rax-30h]
0x18000560d  lea     rcx, [rax-38h]
0x180005611  cmp     [r8+8], edx
0x180005615  sbb     rax, rax
0x180005618  and     rax, rcx
0x18000561b  jmp     short loc_180005676
0x18000561d  cmp     [r8+10h], r9
0x180005621  jnz     short loc_180005639
0x180005623  mov     rcx, [r8+48h]
0x180005627  test    rcx, rcx
0x18000562a  jz      short loc_180005639
0x18000562c  mov     eax, [rcx-40h]
0x18000562f  add     rcx, 0FFFFFFFFFFFFFFB8h
0x180005633  cmp     [r8+8], eax
0x180005637  jmp     short loc_180005615
0x180005639  mov     rax, [r8+38h]
0x18000563d  mov     ecx, [rax-30h]
0x180005640  add     rax, 0FFFFFFFFFFFFFFC8h
0x180005644  cmp     [r8+8], ecx
0x180005648  sbb     rdx, rdx
0x18000564b  and     rdx, rax
0x18000564e  test    rdx, rdx
0x180005651  jz      short loc_180005674
0x180005653  cmp     [rdx+10h], r9
0x180005657  jz      short loc_18000566F
0x180005659  mov     rcx, [rdx+38h]
0x18000565d  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180005661  mov     eax, [rcx+8]
0x180005664  cmp     [rdx+8], eax
0x180005667  sbb     rdx, rdx
0x18000566a  and     rdx, rcx
0x18000566d  jmp     short loc_18000564E
0x18000566f  mov     rax, rdx
0x180005672  jmp     short loc_180005676
0x180005674  xor     eax, eax
0x180005676  add     rsp, 28h
0x18000567a  retn
```
