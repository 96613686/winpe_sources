# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180007250`
- end: `0x1800072b1`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800039b4`
- `0x180004ee0`
- `0x18000663c`

## callees

- `0x180004e34`
- `0x180007250`
- `0x180007338`

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
0x180007250  sub     rsp, 28h
0x180007254  mov     r9, rcx
0x180007257  mov     r8d, edx
0x18000725a  mov     rcx, [rcx]
0x18000725d  cmp     [rcx-10h], edx
0x180007260  cmovg   r8d, [rcx-10h]
0x180007265  cmp     dword ptr [rcx-8], 1
0x180007269  jle     short loc_18000727A
0x18000726b  mov     edx, r8d
0x18000726e  mov     rcx, r9
0x180007271  add     rsp, 28h
0x180007275  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000727a  mov     ecx, [rcx-0Ch]
0x18000727d  cmp     ecx, r8d
0x180007280  jge     short loc_1800072AC
0x180007282  cmp     ecx, 40000000h
0x180007288  jle     short loc_180007291
0x18000728a  mov     eax, 100000h
0x18000728f  jmp     short loc_180007298
0x180007291  mov     eax, ecx
0x180007293  cdq
0x180007294  sub     eax, edx
0x180007296  sar     eax, 1
0x180007298  add     eax, ecx
0x18000729a  mov     rcx, r9
0x18000729d  cmp     eax, r8d
0x1800072a0  cmovge  r8d, eax
0x1800072a4  mov     edx, r8d
0x1800072a7  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x1800072ac  add     rsp, 28h
0x1800072b0  retn
```
