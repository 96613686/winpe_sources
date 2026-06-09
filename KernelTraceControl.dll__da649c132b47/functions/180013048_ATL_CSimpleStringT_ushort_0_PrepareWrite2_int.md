# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180013048`
- end: `0x1800130a5`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `93`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d728`
- `0x18000d9bc`
- `0x18000e858`
- `0x180010510`
- `0x180010e6c`
- `0x180012df4`
- `0x1800130a8`
- `0x1800157a0`
- `0x180015a08`
- `0x180022440`

## callees

- `0x180012f28`
- `0x180012ff4`
- `0x180013048`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  __int64 result; // rax
  int v3; // r8d
  int v5; // ecx
  int v6; // eax
  int v7; // ecx

  result = *a1;
  v3 = a2;
  if ( *(_DWORD *)(*a1 - 16) > a2 )
    v3 = *(_DWORD *)(result - 16);
  if ( *(int *)(result - 8) > 1 )
    return ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v3);
  v5 = *(_DWORD *)(result - 12);
  if ( v5 < v3 )
  {
    if ( v5 <= 0x40000000 )
      v6 = v5 / 2;
    else
      v6 = 0x100000;
    v7 = v6 + v5;
    if ( v7 < v3 )
      v7 = v3;
    return ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)v7);
  }
  return result;
}

```

## disassembly

```asm
0x180013048  sub     rsp, 28h
0x18001304c  mov     rax, [rcx]
0x18001304f  mov     r8d, edx
0x180013052  mov     r9, rcx
0x180013055  cmp     [rax-10h], edx
0x180013058  cmovg   r8d, [rax-10h]
0x18001305d  cmp     dword ptr [rax-8], 1
0x180013061  jle     short loc_18001306F
0x180013063  mov     edx, r8d
0x180013066  add     rsp, 28h
0x18001306a  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18001306f  mov     ecx, [rax-0Ch]
0x180013072  cmp     ecx, r8d
0x180013075  jge     short loc_1800130A0
0x180013077  cmp     ecx, 40000000h
0x18001307d  jle     short loc_180013086
0x18001307f  mov     eax, 100000h
0x180013084  jmp     short loc_18001308D
0x180013086  mov     eax, ecx
0x180013088  cdq
0x180013089  sub     eax, edx
0x18001308b  sar     eax, 1
0x18001308d  add     ecx, eax
0x18001308f  cmp     ecx, r8d
0x180013092  cmovl   ecx, r8d
0x180013096  mov     edx, ecx
0x180013098  mov     rcx, r9
0x18001309b  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x1800130a0  add     rsp, 28h
0x1800130a4  retn
```
