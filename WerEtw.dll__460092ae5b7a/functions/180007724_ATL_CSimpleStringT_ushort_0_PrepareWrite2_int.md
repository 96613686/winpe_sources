# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180007724`
- end: `0x180007785`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045d4`
- `0x1800053a8`
- `0x180006c70`
- `0x180007da8`
- `0x18000d770`
- `0x18001154c`
- `0x180011630`
- `0x180011774`
- `0x180012058`
- `0x1800164e0`
- `0x180018228`

## callees

- `0x180005304`
- `0x180007724`
- `0x18000798c`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  int v3; // r8d
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // eax
  int v7; // eax

  v3 = a2;
  v4 = *a1;
  if ( *(_DWORD *)(v4 - 16) > a2 )
    v3 = *(_DWORD *)(v4 - 16);
  if ( *(int *)(v4 - 8) <= 1 )
  {
    v5 = *(_DWORD *)(v4 - 12);
    if ( v5 < v3 )
    {
      if ( v5 <= 0x40000000 )
        v6 = v5 / 2;
      else
        v6 = 0x100000;
      v7 = v5 + v6;
      if ( v7 >= v3 )
        v3 = v7;
      ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)v3);
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x180007724  sub     rsp, 28h
0x180007728  mov     r9, rcx
0x18000772b  mov     r8d, edx
0x18000772e  mov     rcx, [rcx]
0x180007731  cmp     [rcx-10h], edx
0x180007734  cmovg   r8d, [rcx-10h]
0x180007739  cmp     dword ptr [rcx-8], 1
0x18000773d  jle     short loc_18000774E
0x18000773f  mov     edx, r8d
0x180007742  mov     rcx, r9
0x180007745  add     rsp, 28h
0x180007749  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000774e  mov     ecx, [rcx-0Ch]
0x180007751  cmp     ecx, r8d
0x180007754  jge     short loc_180007780
0x180007756  cmp     ecx, 40000000h
0x18000775c  jle     short loc_180007765
0x18000775e  mov     eax, 100000h
0x180007763  jmp     short loc_18000776C
0x180007765  mov     eax, ecx
0x180007767  cdq
0x180007768  sub     eax, edx
0x18000776a  sar     eax, 1
0x18000776c  add     eax, ecx
0x18000776e  mov     rcx, r9
0x180007771  cmp     eax, r8d
0x180007774  cmovge  r8d, eax
0x180007778  mov     edx, r8d
0x18000777b  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180007780  add     rsp, 28h
0x180007784  retn
```
