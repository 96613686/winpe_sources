# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180011cc0`
- end: `0x180011d26`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007880`
- `0x180011948`
- `0x180011a5c`
- `0x180011de8`

## callees

- `0x180011860`
- `0x180011cc0`
- `0x180011d2c`

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
0x180011cc0  sub     rsp, 28h
0x180011cc4  mov     r9, rcx
0x180011cc7  mov     r8d, edx
0x180011cca  mov     rcx, [rcx]
0x180011ccd  cmp     [rcx-10h], edx
0x180011cd0  cmovg   r8d, [rcx-10h]
0x180011cd5  cmp     dword ptr [rcx-8], 1
0x180011cd9  jle     short loc_180011CEA
0x180011cdb  mov     edx, r8d
0x180011cde  mov     rcx, r9
0x180011ce1  add     rsp, 28h
0x180011ce5  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180011cea  mov     ecx, [rcx-0Ch]
0x180011ced  cmp     ecx, r8d
0x180011cf0  jge     short loc_180011D21
0x180011cf2  cmp     ecx, 40000000h
0x180011cf8  jle     short loc_180011D01
0x180011cfa  mov     eax, 100000h
0x180011cff  jmp     short loc_180011D0D
0x180011d01  mov     eax, ecx
0x180011d03  mov     r10d, 2
0x180011d09  cdq
0x180011d0a  idiv    r10d
0x180011d0d  add     eax, ecx
0x180011d0f  mov     rcx, r9
0x180011d12  cmp     eax, r8d
0x180011d15  cmovge  r8d, eax
0x180011d19  mov     edx, r8d
0x180011d1c  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180011d21  add     rsp, 28h
0x180011d25  retn
```
