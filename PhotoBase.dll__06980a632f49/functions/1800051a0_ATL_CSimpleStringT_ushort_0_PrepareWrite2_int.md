# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x1800051a0`
- end: `0x180005201`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e70`

## callees

- `0x180003f30`
- `0x1800051a0`
- `0x1800054b4`

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
0x1800051a0  sub     rsp, 28h
0x1800051a4  mov     r9, rcx
0x1800051a7  mov     r8d, edx
0x1800051aa  mov     rcx, [rcx]
0x1800051ad  cmp     [rcx-10h], edx
0x1800051b0  cmovg   r8d, [rcx-10h]
0x1800051b5  cmp     dword ptr [rcx-8], 1
0x1800051b9  jle     short loc_1800051CA
0x1800051bb  mov     edx, r8d
0x1800051be  mov     rcx, r9
0x1800051c1  add     rsp, 28h
0x1800051c5  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800051ca  mov     ecx, [rcx-0Ch]
0x1800051cd  cmp     ecx, r8d
0x1800051d0  jge     short loc_1800051FC
0x1800051d2  cmp     ecx, 40000000h
0x1800051d8  jle     short loc_1800051E1
0x1800051da  mov     eax, 100000h
0x1800051df  jmp     short loc_1800051E8
0x1800051e1  mov     eax, ecx
0x1800051e3  cdq
0x1800051e4  sub     eax, edx
0x1800051e6  sar     eax, 1
0x1800051e8  add     eax, ecx
0x1800051ea  mov     rcx, r9
0x1800051ed  cmp     eax, r8d
0x1800051f0  cmovge  r8d, eax
0x1800051f4  mov     edx, r8d
0x1800051f7  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x1800051fc  add     rsp, 28h
0x180005200  retn
```
