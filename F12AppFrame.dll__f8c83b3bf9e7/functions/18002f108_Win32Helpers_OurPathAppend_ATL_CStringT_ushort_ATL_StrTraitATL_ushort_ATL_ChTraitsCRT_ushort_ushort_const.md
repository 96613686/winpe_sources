# Win32Helpers::OurPathAppend(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)

- ea: `0x18002f108`
- end: `0x18002f227`
- name: `?OurPathAppend@Win32Helpers@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `287`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004690`
- `0x180014210`
- `0x180014740`

## callees

- `0x180003858`
- `0x1800042a4`
- `0x1800045b4`
- `0x18002ec58`
- `0x18002f108`

## import_xrefs

- `SHLWAPI!PathGetCharTypeW` at `0x18002f183`
- `SHLWAPI!PathGetCharTypeW` at `0x18002f18e`
- `SHLWAPI!PathGetCharTypeW` at `0x18002f183`
- `SHLWAPI!PathGetCharTypeW` at `0x18002f18e`

## pseudocode

```c
__int64 __fastcall Win32Helpers::OurPathAppend(_QWORD *a1, WCHAR *a2)
{
  __int64 v2; // rbp
  __int64 v5; // r8
  __int64 result; // rax
  __int64 v7; // rax
  WCHAR v8; // bx
  UINT CharTypeW; // edi
  WCHAR *v10; // r15
  __int64 v11; // rdi
  int v12; // ebx

  v2 = -1;
  if ( !*(_DWORD *)(*a1 - 16LL) )
  {
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
    }
    else
    {
      v5 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2, v5);
  }
  result = -1;
  do
    ++result;
  while ( a2[result] );
  if ( result )
  {
    v7 = *(int *)(*a1 - 16LL);
    if ( (int)v7 - 1 >= 0 && (int)v7 - 1 <= (int)v7 )
    {
      v8 = *a2;
      CharTypeW = PathGetCharTypeW(*(_WORD *)(*a1 + 2 * v7 - 2));
      v10 = a2 + 1;
      if ( PathGetCharTypeW(v8) != 8 )
        v10 = a2;
      if ( CharTypeW == 8 )
        goto LABEL_20;
      v11 = *(unsigned int *)(*a1 - 16LL);
      v12 = v11 + 1;
      if ( (int)((*(_DWORD *)(*a1 - 12LL) - (v11 + 1)) | (1 - *(_DWORD *)(*a1 - 8LL))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1);
      *(_WORD *)(*a1 + 2 * v11) = 92;
      if ( v12 >= 0 && v12 <= *(_DWORD *)(*a1 - 12LL) )
      {
        *(_DWORD *)(*a1 - 16LL) = v12;
        *(_WORD *)(*a1 + 2LL * v12) = 0;
LABEL_20:
        if ( v10 )
        {
          do
            ++v2;
          while ( v10[v2] );
        }
        else
        {
          LODWORD(v2) = 0;
        }
        return ATL::CSimpleStringT<unsigned short,0>::Append(a1, v10, (unsigned int)v2);
      }
    }
    ATL::AtlThrowImpl(-2147024809);
  }
  return result;
}

```

## disassembly

```asm
0x18002f108  push    rbx
0x18002f10a  push    rbp
0x18002f10b  push    rsi
0x18002f10c  push    rdi
0x18002f10d  push    r12
0x18002f10f  push    r14
0x18002f111  push    r15
0x18002f113  sub     rsp, 20h
0x18002f117  mov     rax, [rcx]
0x18002f11a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002f11e  xor     r12d, r12d
0x18002f121  mov     r14, rdx
0x18002f124  mov     rsi, rcx
0x18002f127  cmp     [rax-10h], r12d
0x18002f12b  jnz     short loc_18002F149
0x18002f12d  test    rdx, rdx
0x18002f130  jnz     short loc_18002F137
0x18002f132  mov     r8d, r12d
0x18002f135  jmp     short loc_18002F144
0x18002f137  mov     r8, rbp
0x18002f13a  inc     r8
0x18002f13d  cmp     [rdx+r8*2], r12w
0x18002f142  jnz     short loc_18002F13A
0x18002f144  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002f149  mov     rax, rbp
0x18002f14c  inc     rax
0x18002f14f  cmp     [r14+rax*2], r12w
0x18002f154  jnz     short loc_18002F14C
0x18002f156  test    rax, rax
0x18002f159  jz      loc_18002F20D
0x18002f15f  mov     r8, [rsi]
0x18002f162  movsxd  rax, dword ptr [r8-10h]
0x18002f166  lea     edx, [rax-1]
0x18002f169  test    edx, edx
0x18002f16b  js      loc_18002F21C
0x18002f171  cmp     edx, eax
0x18002f173  jg      loc_18002F21C
0x18002f179  movzx   ecx, word ptr [r8+rax*2-2]; ch
0x18002f17f  movzx   ebx, word ptr [r14]
0x18002f183  call    cs:__imp_PathGetCharTypeW
0x18002f189  movzx   ecx, bx; ch
0x18002f18c  mov     edi, eax
0x18002f18e  call    cs:__imp_PathGetCharTypeW
0x18002f194  cmp     eax, 8
0x18002f197  lea     r15, [r14+2]
0x18002f19b  cmovnz  r15, r14
0x18002f19f  cmp     edi, 8
0x18002f1a2  jz      short loc_18002F1EB
0x18002f1a4  mov     rax, [rsi]
0x18002f1a7  mov     ecx, 1
0x18002f1ac  mov     edi, [rax-10h]
0x18002f1af  sub     ecx, [rax-8]
0x18002f1b2  mov     eax, [rax-0Ch]
0x18002f1b5  lea     ebx, [rdi+1]
0x18002f1b8  sub     eax, ebx
0x18002f1ba  or      ecx, eax
0x18002f1bc  jge     short loc_18002F1C8
0x18002f1be  mov     edx, ebx
0x18002f1c0  mov     rcx, rsi
0x18002f1c3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002f1c8  mov     rax, [rsi]
0x18002f1cb  mov     word ptr [rax+rdi*2], 5Ch ; '\'
0x18002f1d1  test    ebx, ebx
0x18002f1d3  js      short loc_18002F21C
0x18002f1d5  mov     rax, [rsi]
0x18002f1d8  cmp     ebx, [rax-0Ch]
0x18002f1db  jg      short loc_18002F21C
0x18002f1dd  mov     [rax-10h], ebx
0x18002f1e0  mov     rcx, [rsi]
0x18002f1e3  movsxd  rdx, ebx
0x18002f1e6  mov     [rcx+rdx*2], r12w
0x18002f1eb  test    r15, r15
0x18002f1ee  jnz     short loc_18002F1F5
0x18002f1f0  mov     ebp, r12d
0x18002f1f3  jmp     short loc_18002F1FF
0x18002f1f5  inc     rbp
0x18002f1f8  cmp     [r15+rbp*2], r12w
0x18002f1fd  jnz     short loc_18002F1F5
0x18002f1ff  mov     r8d, ebp
0x18002f202  mov     rdx, r15
0x18002f205  mov     rcx, rsi
0x18002f208  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002f20d  add     rsp, 20h
0x18002f211  pop     r15
0x18002f213  pop     r14
0x18002f215  pop     r12
0x18002f217  pop     rdi
0x18002f218  pop     rsi
0x18002f219  pop     rbp
0x18002f21a  pop     rbx
0x18002f21b  retn
0x18002f21c  mov     ecx, 80070057h; int
0x18002f221  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
