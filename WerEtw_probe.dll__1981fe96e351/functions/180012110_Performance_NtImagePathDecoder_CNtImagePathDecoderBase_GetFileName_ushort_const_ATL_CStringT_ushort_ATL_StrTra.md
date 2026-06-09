# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180012110`
- end: `0x180012301`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f5dc`
- `0x180013890`

## callees

- `0x180003bb8`
- `0x1800053a8`
- `0x180007da8`
- `0x180012110`
- `0x180027bd4`
- `0x180027be0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012146`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012146`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800121bd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001220c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800121bd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001220c`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *i; // rbx
  _QWORD *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  __int64 j; // rbx
  const wchar_t *v11; // rcx
  _QWORD *v12; // r8
  wchar_t *v13; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // r8

  for ( i = *(_QWORD **)a1; i != *(_QWORD **)(a1 + 8); i += 8 )
  {
    if ( i[3] <= 7u )
      v7 = i;
    else
      v7 = (_QWORD *)*i;
    if ( !(unsigned int)_o__wcsnicmp(v7, a2, i[2]) )
    {
      v8 = i + 4;
      v9 = a2 + 2LL * i[2];
      if ( i[7] > 7u )
        v8 = (_QWORD *)*v8;
      goto LABEL_10;
    }
  }
  for ( j = *(_QWORD *)(a1 + 24); j != *(_QWORD *)(a1 + 32); j += 32 )
  {
    if ( *(_QWORD *)(j + 24) <= 7u )
      v11 = (const wchar_t *)j;
    else
      v11 = *(const wchar_t **)j;
    if ( !wcsncmp_0(v11, (const wchar_t *)a2, *(unsigned int *)(j + 16)) )
      goto LABEL_35;
  }
  if ( !wcschr((const wchar_t *)a2, 0x5Cu) )
  {
    if ( *(_QWORD *)(a1 + 64) )
    {
      v12 = (_QWORD *)(a1 + 48);
      if ( *(_QWORD *)(a1 + 72) > 7u )
        v12 = (_QWORD *)*v12;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3,
        L"%ws\\drivers\\%ws",
        v12,
        a2);
      return 1;
    }
LABEL_47:
    ATL::AtlThrowImpl(-2147418113);
  }
  if ( *(_WORD *)a2 == 92
    && *(_WORD *)(a2 + 2) == 59
    && *(_WORD *)(a2 + 4)
    && *(_WORD *)(a2 + 6) == 58
    && (v13 = wcschr((const wchar_t *)(a2 + 8), 0x5Cu)) != 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a3,
      L"\\%ws",
      v13);
  }
  else
  {
    if ( *(_WORD *)a2 && *(_WORD *)(a2 + 2) != 58 )
    {
      if ( !*(_QWORD *)(a1 + 96) )
        goto LABEL_47;
      if ( *(_WORD *)a2 != 92 )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( *(_QWORD *)(a1 + 104) > 7u )
          v8 = (_QWORD *)*v8;
        v9 = a2;
LABEL_10:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%ws%ws",
          v8,
          v9);
        return 1;
      }
      if ( !wcsncmp_0(
              (const wchar_t *)a2,
              `Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName'::`35'::wchDevicePrefix,
              8u) )
      {
LABEL_35:
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &word_18002D338, 0);
        return 0;
      }
      if ( wcscmp_0((const wchar_t *)a2, L"\\FI_UNKNOWN") )
      {
        v15 = (unsigned __int16 *)(a1 + 80);
        if ( *((_QWORD *)v15 + 3) > 7u )
          v15 = *(unsigned __int16 **)v15;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%wc:%ws",
          *v15,
          a2);
        return 1;
      }
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(a2 + 2 * v16) );
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, a2, v16);
  }
  return 1;
}

```

## disassembly

```asm
0x180012110  push    rbx
0x180012112  push    rbp
0x180012113  push    rsi
0x180012114  push    rdi
0x180012115  push    r14
0x180012117  sub     rsp, 20h
0x18001211b  mov     rbx, [rcx]
0x18001211e  mov     rbp, r8
0x180012121  mov     rdi, rdx
0x180012124  mov     rsi, rcx
0x180012127  xor     r14d, r14d
0x18001212a  cmp     rbx, [rsi+8]
0x18001212e  jz      short loc_180012180
0x180012130  cmp     qword ptr [rbx+18h], 7
0x180012135  jbe     short loc_18001213C
0x180012137  mov     rcx, [rbx]
0x18001213a  jmp     short loc_18001213F
0x18001213c  mov     rcx, rbx
0x18001213f  mov     r8, [rbx+10h]
0x180012143  mov     rdx, rdi
0x180012146  call    cs:__imp__o__wcsnicmp
0x18001214c  test    eax, eax
0x18001214e  jz      short loc_180012156
0x180012150  add     rbx, 40h ; '@'
0x180012154  jmp     short loc_18001212A
0x180012156  mov     rax, [rbx+10h]
0x18001215a  lea     r8, [rbx+20h]
0x18001215e  cmp     qword ptr [r8+18h], 7
0x180012163  lea     r9, [rdi+rax*2]
0x180012167  jbe     short loc_18001216C
0x180012169  mov     r8, [r8]
0x18001216c  lea     rdx, aWsWs; "%ws%ws"
0x180012173  mov     rcx, rbp
0x180012176  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001217b  jmp     loc_1800122E9
0x180012180  mov     rbx, [rsi+18h]
0x180012184  cmp     rbx, [rsi+20h]
0x180012188  jz      short loc_1800121B3
0x18001218a  cmp     qword ptr [rbx+18h], 7
0x18001218f  jbe     short loc_180012196
0x180012191  mov     rcx, [rbx]
0x180012194  jmp     short loc_180012199
0x180012196  mov     rcx, rbx; String1
0x180012199  mov     r8d, [rbx+10h]; MaxCount
0x18001219d  mov     rdx, rdi; String2
0x1800121a0  call    wcsncmp_0
0x1800121a5  test    eax, eax
0x1800121a7  jz      loc_18001226B
0x1800121ad  add     rbx, 20h ; ' '
0x1800121b1  jmp     short loc_180012184
0x1800121b3  mov     ebx, 5Ch ; '\'
0x1800121b8  mov     rcx, rdi; Str
0x1800121bb  mov     edx, ebx; Ch
0x1800121bd  call    cs:__imp_wcschr
0x1800121c3  test    rax, rax
0x1800121c6  jnz     short loc_1800121EC
0x1800121c8  cmp     [rsi+40h], r14
0x1800121cc  jz      loc_1800122F6
0x1800121d2  lea     r8, [rsi+30h]
0x1800121d6  cmp     qword ptr [r8+18h], 7
0x1800121db  jbe     short loc_1800121E0
0x1800121dd  mov     r8, [r8]
0x1800121e0  mov     r9, rdi
0x1800121e3  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x1800121ea  jmp     short loc_180012173
0x1800121ec  cmp     [rdi], bx
0x1800121ef  jnz     short loc_18001222E
0x1800121f1  cmp     word ptr [rdi+2], 3Bh ; ';'
0x1800121f6  jnz     short loc_18001222E
0x1800121f8  cmp     [rdi+4], r14w
0x1800121fd  jz      short loc_18001222E
0x1800121ff  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180012204  jnz     short loc_18001222E
0x180012206  mov     edx, ebx; Ch
0x180012208  lea     rcx, [rdi+8]; Str
0x18001220c  call    cs:__imp_wcschr
0x180012212  test    rax, rax
0x180012215  jz      short loc_18001222E
0x180012217  mov     r8, rax
0x18001221a  lea     rdx, aWs; "\\%ws"
0x180012221  mov     rcx, rbp
0x180012224  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012229  jmp     loc_1800122E9
0x18001222e  cmp     [rdi], r14w
0x180012232  jz      loc_1800122D0
0x180012238  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001223d  jz      loc_1800122D0
0x180012243  cmp     [rsi+60h], r14
0x180012247  jz      loc_1800122F6
0x18001224d  cmp     [rdi], bx
0x180012250  jnz     short loc_1800122BA
0x180012252  mov     r8d, 8; MaxCount
0x180012258  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x18001225f  mov     rcx, rdi; String1
0x180012262  call    wcsncmp_0
0x180012267  test    eax, eax
0x180012269  jnz     short loc_180012281
0x18001226b  xor     r8d, r8d
0x18001226e  lea     rdx, word_18002D338
0x180012275  mov     rcx, rbp
0x180012278  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001227d  xor     al, al
0x18001227f  jmp     short loc_1800122EB
0x180012281  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x180012288  mov     rcx, rdi; String1
0x18001228b  call    wcscmp_0
0x180012290  test    eax, eax
0x180012292  jz      short loc_1800122D0
0x180012294  add     rsi, 50h ; 'P'
0x180012298  cmp     qword ptr [rsi+18h], 7
0x18001229d  jbe     short loc_1800122A2
0x18001229f  mov     rsi, [rsi]
0x1800122a2  movzx   r8d, word ptr [rsi]
0x1800122a6  lea     rdx, aWcWs; "%wc:%ws"
0x1800122ad  mov     r9, rdi
0x1800122b0  mov     rcx, rbp
0x1800122b3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800122b8  jmp     short loc_1800122E9
0x1800122ba  lea     r8, [rsi+50h]
0x1800122be  cmp     qword ptr [r8+18h], 7
0x1800122c3  jbe     short loc_1800122C8
0x1800122c5  mov     r8, [r8]
0x1800122c8  mov     r9, rdi
0x1800122cb  jmp     loc_18001216C
0x1800122d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800122d4  inc     r8
0x1800122d7  cmp     [rdi+r8*2], r14w
0x1800122dc  jnz     short loc_1800122D4
0x1800122de  mov     rdx, rdi
0x1800122e1  mov     rcx, rbp
0x1800122e4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800122e9  mov     al, 1
0x1800122eb  add     rsp, 20h
0x1800122ef  pop     r14
0x1800122f1  pop     rdi
0x1800122f2  pop     rsi
0x1800122f3  pop     rbp
0x1800122f4  pop     rbx
0x1800122f5  retn
0x1800122f6  mov     ecx, 8000FFFFh; int
0x1800122fb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
