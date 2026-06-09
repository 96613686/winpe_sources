# ATL::CSimpleStringT<char,0>::PrepareWrite2(int)

- ea: `0x180007028`
- end: `0x18000708a`
- name: `?PrepareWrite2@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800069b4`
- `0x180006f00`

## callees

- `0x180007028`
- `0x18000708c`
- `0x1800070d4`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<char,0>::PrepareWrite2(__int64 *a1, int a2)
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
    return ATL::CSimpleStringT<char,0>::Fork(a1, (unsigned int)v3);
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
    return ATL::CSimpleStringT<char,0>::Reallocate(a1, (unsigned int)v3);
  }
  return result;
}

```

## disassembly

```asm
0x180007028  sub     rsp, 28h
0x18000702c  mov     rax, [rcx]
0x18000702f  mov     r8d, edx
0x180007032  mov     r9, rcx
0x180007035  cmp     [rax-10h], edx
0x180007038  cmovg   r8d, [rax-10h]
0x18000703d  cmp     dword ptr [rax-8], 1
0x180007041  jle     short loc_18000704F
0x180007043  mov     edx, r8d
0x180007046  add     rsp, 28h
0x18000704a  jmp     ?Fork@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::Fork(int)
0x18000704f  cmp     [rax-0Ch], r8d
0x180007053  jge     short loc_180007085
0x180007055  lfence
0x180007058  mov     ecx, [rax-0Ch]
0x18000705b  cmp     ecx, 40000000h
0x180007061  jle     short loc_18000706A
0x180007063  mov     eax, 100000h
0x180007068  jmp     short loc_180007071
0x18000706a  mov     eax, ecx
0x18000706c  cdq
0x18000706d  sub     eax, edx
0x18000706f  sar     eax, 1
0x180007071  add     eax, ecx
0x180007073  mov     rcx, r9
0x180007076  cmp     eax, r8d
0x180007079  cmovge  r8d, eax
0x18000707d  mov     edx, r8d
0x180007080  call    ?Reallocate@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::Reallocate(int)
0x180007085  add     rsp, 28h
0x180007089  retn
```
