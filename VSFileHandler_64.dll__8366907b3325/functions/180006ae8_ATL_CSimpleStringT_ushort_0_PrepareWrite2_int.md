# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180006ae8`
- end: `0x180006b4a`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b5c`
- `0x180006ce8`

## callees

- `0x180006ae8`
- `0x180006dec`
- `0x180006e34`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  __int64 result; // rax
  int v3; // r8d
  int v5; // ecx
  int v6; // eax
  int v7; // eax

  result = *a1;
  v3 = a2;
  if ( *(_DWORD *)(*a1 - 16) > a2 )
    v3 = *(_DWORD *)(result - 16);
  if ( *(int *)(result - 8) > 1 )
    return ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v3);
  if ( *(_DWORD *)(result - 12) < v3 )
  {
    _mm_lfence();
    v5 = *(_DWORD *)(result - 12);
    if ( v5 <= 0x40000000 )
      v6 = v5 / 2;
    else
      v6 = 0x100000;
    v7 = v5 + v6;
    if ( v7 >= v3 )
      v3 = v7;
    return ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)v3);
  }
  return result;
}

```

## disassembly

```asm
0x180006ae8  sub     rsp, 28h
0x180006aec  mov     rax, [rcx]
0x180006aef  mov     r8d, edx
0x180006af2  mov     r9, rcx
0x180006af5  cmp     [rax-10h], edx
0x180006af8  cmovg   r8d, [rax-10h]
0x180006afd  cmp     dword ptr [rax-8], 1
0x180006b01  jle     short loc_180006B0F
0x180006b03  mov     edx, r8d
0x180006b06  add     rsp, 28h
0x180006b0a  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180006b0f  cmp     [rax-0Ch], r8d
0x180006b13  jge     short loc_180006B45
0x180006b15  lfence
0x180006b18  mov     ecx, [rax-0Ch]
0x180006b1b  cmp     ecx, 40000000h
0x180006b21  jle     short loc_180006B2A
0x180006b23  mov     eax, 100000h
0x180006b28  jmp     short loc_180006B31
0x180006b2a  mov     eax, ecx
0x180006b2c  cdq
0x180006b2d  sub     eax, edx
0x180006b2f  sar     eax, 1
0x180006b31  add     eax, ecx
0x180006b33  mov     rcx, r9
0x180006b36  cmp     eax, r8d
0x180006b39  cmovge  r8d, eax
0x180006b3d  mov     edx, r8d
0x180006b40  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180006b45  add     rsp, 28h
0x180006b49  retn
```
