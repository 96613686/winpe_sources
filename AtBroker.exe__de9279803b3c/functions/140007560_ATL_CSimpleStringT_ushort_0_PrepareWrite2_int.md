# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x140007560`
- end: `0x1400075c1`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140003ea0`
- `0x140006d0c`
- `0x14000cb50`
- `0x14000d118`
- `0x140011204`
- `0x1400116c4`

## callees

- `0x1400056d4`
- `0x140007560`
- `0x140007bbc`

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
0x140007560  sub     rsp, 28h
0x140007564  mov     r9, rcx
0x140007567  mov     r8d, edx
0x14000756a  mov     rcx, [rcx]
0x14000756d  cmp     [rcx-10h], edx
0x140007570  cmovg   r8d, [rcx-10h]
0x140007575  cmp     dword ptr [rcx-8], 1
0x140007579  jle     short loc_14000758A
0x14000757b  mov     edx, r8d
0x14000757e  mov     rcx, r9
0x140007581  add     rsp, 28h
0x140007585  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x14000758a  mov     ecx, [rcx-0Ch]
0x14000758d  cmp     ecx, r8d
0x140007590  jge     short loc_1400075BC
0x140007592  cmp     ecx, 40000000h
0x140007598  jle     short loc_1400075A1
0x14000759a  mov     eax, 100000h
0x14000759f  jmp     short loc_1400075A8
0x1400075a1  mov     eax, ecx
0x1400075a3  cdq
0x1400075a4  sub     eax, edx
0x1400075a6  sar     eax, 1
0x1400075a8  add     eax, ecx
0x1400075aa  mov     rcx, r9
0x1400075ad  cmp     eax, r8d
0x1400075b0  cmovge  r8d, eax
0x1400075b4  mov     edx, r8d
0x1400075b7  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x1400075bc  add     rsp, 28h
0x1400075c0  retn
```
