# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000823c`
- end: `0x18000829d`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800050b4`
- `0x1800061c8`
- `0x18000b64c`

## callees

- `0x180005e58`
- `0x18000823c`
- `0x18000af7c`

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
0x18000823c  sub     rsp, 28h
0x180008240  mov     r9, rcx
0x180008243  mov     r8d, edx
0x180008246  mov     rcx, [rcx]
0x180008249  cmp     [rcx-10h], edx
0x18000824c  cmovg   r8d, [rcx-10h]
0x180008251  cmp     dword ptr [rcx-8], 1
0x180008255  jle     short loc_180008266
0x180008257  mov     edx, r8d
0x18000825a  mov     rcx, r9
0x18000825d  add     rsp, 28h
0x180008261  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180008266  mov     ecx, [rcx-0Ch]
0x180008269  cmp     ecx, r8d
0x18000826c  jge     short loc_180008298
0x18000826e  cmp     ecx, 40000000h
0x180008274  jle     short loc_18000827D
0x180008276  mov     eax, 100000h
0x18000827b  jmp     short loc_180008284
0x18000827d  mov     eax, ecx
0x18000827f  cdq
0x180008280  sub     eax, edx
0x180008282  sar     eax, 1
0x180008284  add     eax, ecx
0x180008286  mov     rcx, r9
0x180008289  cmp     eax, r8d
0x18000828c  cmovge  r8d, eax
0x180008290  mov     edx, r8d
0x180008293  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180008298  add     rsp, 28h
0x18000829c  retn
```
