# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000b6ec`
- end: `0x18000b74d`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000ae58`
- `0x18000b590`
- `0x18000b7a8`
- `0x18000b9a8`

## callees

- `0x18000ad7c`
- `0x18000b6ec`
- `0x18000b754`

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
0x18000b6ec  sub     rsp, 28h
0x18000b6f0  mov     r9, rcx
0x18000b6f3  mov     r8d, edx
0x18000b6f6  mov     rcx, [rcx]
0x18000b6f9  cmp     [rcx-10h], edx
0x18000b6fc  cmovg   r8d, [rcx-10h]
0x18000b701  cmp     dword ptr [rcx-8], 1
0x18000b705  jle     short loc_18000B716
0x18000b707  mov     edx, r8d
0x18000b70a  mov     rcx, r9
0x18000b70d  add     rsp, 28h
0x18000b711  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000b716  mov     ecx, [rcx-0Ch]
0x18000b719  cmp     ecx, r8d
0x18000b71c  jge     short loc_18000B748
0x18000b71e  cmp     ecx, 40000000h
0x18000b724  jle     short loc_18000B72D
0x18000b726  mov     eax, 100000h
0x18000b72b  jmp     short loc_18000B734
0x18000b72d  mov     eax, ecx
0x18000b72f  cdq
0x18000b730  sub     eax, edx
0x18000b732  sar     eax, 1
0x18000b734  add     eax, ecx
0x18000b736  mov     rcx, r9
0x18000b739  cmp     eax, r8d
0x18000b73c  cmovge  r8d, eax
0x18000b740  mov     edx, r8d
0x18000b743  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000b748  add     rsp, 28h
0x18000b74c  retn
```
