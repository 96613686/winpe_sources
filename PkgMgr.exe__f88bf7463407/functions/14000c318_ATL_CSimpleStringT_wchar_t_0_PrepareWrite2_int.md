# ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)

- ea: `0x14000c318`
- end: `0x14000c37e`
- name: `?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c830`
- `0x14000cbd0`
- `0x14000dc5c`

## callees

- `0x14000bbe4`
- `0x14000c318`
- `0x14000c7ac`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(__int64 *a1, int a2)
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
      ATL::CSimpleStringT<wchar_t,0>::Reallocate(a1, (unsigned int)v3);
    }
  }
  else
  {
    ATL::CSimpleStringT<wchar_t,0>::Fork(a1, (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x14000c318  sub     rsp, 28h
0x14000c31c  mov     r9, rcx
0x14000c31f  mov     r8d, edx
0x14000c322  mov     rcx, [rcx]
0x14000c325  cmp     [rcx-10h], edx
0x14000c328  cmovg   r8d, [rcx-10h]
0x14000c32d  cmp     dword ptr [rcx-8], 1
0x14000c331  jle     short loc_14000C342
0x14000c333  mov     edx, r8d
0x14000c336  mov     rcx, r9
0x14000c339  add     rsp, 28h
0x14000c33d  jmp     ?Fork@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::Fork(int)
0x14000c342  mov     ecx, [rcx-0Ch]
0x14000c345  cmp     ecx, r8d
0x14000c348  jge     short loc_14000C379
0x14000c34a  cmp     ecx, 40000000h
0x14000c350  jle     short loc_14000C359
0x14000c352  mov     eax, 100000h
0x14000c357  jmp     short loc_14000C365
0x14000c359  mov     eax, ecx
0x14000c35b  mov     r10d, 2
0x14000c361  cdq
0x14000c362  idiv    r10d
0x14000c365  add     eax, ecx
0x14000c367  mov     rcx, r9
0x14000c36a  cmp     eax, r8d
0x14000c36d  cmovge  r8d, eax
0x14000c371  mov     edx, r8d
0x14000c374  call    ?Reallocate@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::Reallocate(int)
0x14000c379  add     rsp, 28h
0x14000c37d  retn
```
