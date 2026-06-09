# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180023d60`
- end: `0x180023f64`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180021250`
- `0x1800258d4`

## callees

- `0x180011648`
- `0x180017000`
- `0x18001a030`
- `0x180023d60`
- `0x180037034`
- `0x180037040`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023d96`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023d96`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e13`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e68`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e13`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e68`

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
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &String2, 0);
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
0x180023d60  push    rbx
0x180023d62  push    rbp
0x180023d63  push    rsi
0x180023d64  push    rdi
0x180023d65  push    r14
0x180023d67  sub     rsp, 20h
0x180023d6b  mov     rbx, [rcx]
0x180023d6e  mov     rbp, r8
0x180023d71  mov     rdi, rdx
0x180023d74  mov     rsi, rcx
0x180023d77  xor     r14d, r14d
0x180023d7a  cmp     rbx, [rsi+8]
0x180023d7e  jz      short loc_180023DD6
0x180023d80  cmp     qword ptr [rbx+18h], 7
0x180023d85  jbe     short loc_180023D8C
0x180023d87  mov     rcx, [rbx]
0x180023d8a  jmp     short loc_180023D8F
0x180023d8c  mov     rcx, rbx
0x180023d8f  mov     r8, [rbx+10h]
0x180023d93  mov     rdx, rdi
0x180023d96  call    cs:__imp__o__wcsnicmp
0x180023d9d  nop     dword ptr [rax+rax+00h]
0x180023da2  test    eax, eax
0x180023da4  jz      short loc_180023DAC
0x180023da6  add     rbx, 40h ; '@'
0x180023daa  jmp     short loc_180023D7A
0x180023dac  mov     rax, [rbx+10h]
0x180023db0  lea     r8, [rbx+20h]
0x180023db4  cmp     qword ptr [r8+18h], 7
0x180023db9  lea     r9, [rdi+rax*2]
0x180023dbd  jbe     short loc_180023DC2
0x180023dbf  mov     r8, [r8]
0x180023dc2  lea     rdx, aWsWs; "%ws%ws"
0x180023dc9  mov     rcx, rbp
0x180023dcc  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180023dd1  jmp     loc_180023F4B
0x180023dd6  mov     rbx, [rsi+18h]
0x180023dda  cmp     rbx, [rsi+20h]
0x180023dde  jz      short loc_180023E09
0x180023de0  cmp     qword ptr [rbx+18h], 7
0x180023de5  jbe     short loc_180023DEC
0x180023de7  mov     rcx, [rbx]
0x180023dea  jmp     short loc_180023DEF
0x180023dec  mov     rcx, rbx; String1
0x180023def  mov     r8d, [rbx+10h]; MaxCount
0x180023df3  mov     rdx, rdi; String2
0x180023df6  call    wcsncmp_0
0x180023dfb  test    eax, eax
0x180023dfd  jz      loc_180023ECD
0x180023e03  add     rbx, 20h ; ' '
0x180023e07  jmp     short loc_180023DDA
0x180023e09  mov     ebx, 5Ch ; '\'
0x180023e0e  mov     rcx, rdi; Str
0x180023e11  mov     edx, ebx; Ch
0x180023e13  call    cs:__imp_wcschr
0x180023e1a  nop     dword ptr [rax+rax+00h]
0x180023e1f  test    rax, rax
0x180023e22  jnz     short loc_180023E48
0x180023e24  cmp     [rsi+40h], r14
0x180023e28  jz      loc_180023F59
0x180023e2e  lea     r8, [rsi+30h]
0x180023e32  cmp     qword ptr [r8+18h], 7
0x180023e37  jbe     short loc_180023E3C
0x180023e39  mov     r8, [r8]
0x180023e3c  mov     r9, rdi
0x180023e3f  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x180023e46  jmp     short loc_180023DC9
0x180023e48  cmp     [rdi], bx
0x180023e4b  jnz     short loc_180023E90
0x180023e4d  cmp     word ptr [rdi+2], 3Bh ; ';'
0x180023e52  jnz     short loc_180023E90
0x180023e54  cmp     [rdi+4], r14w
0x180023e59  jz      short loc_180023E90
0x180023e5b  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180023e60  jnz     short loc_180023E90
0x180023e62  mov     edx, ebx; Ch
0x180023e64  lea     rcx, [rdi+8]; Str
0x180023e68  call    cs:__imp_wcschr
0x180023e6f  nop     dword ptr [rax+rax+00h]
0x180023e74  test    rax, rax
0x180023e77  jz      short loc_180023E90
0x180023e79  mov     r8, rax
0x180023e7c  lea     rdx, aWs; "\\%ws"
0x180023e83  mov     rcx, rbp
0x180023e86  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180023e8b  jmp     loc_180023F4B
0x180023e90  cmp     [rdi], r14w
0x180023e94  jz      loc_180023F32
0x180023e9a  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180023e9f  jz      loc_180023F32
0x180023ea5  cmp     [rsi+60h], r14
0x180023ea9  jz      loc_180023F59
0x180023eaf  cmp     [rdi], bx
0x180023eb2  jnz     short loc_180023F1C
0x180023eb4  mov     r8d, 8; MaxCount
0x180023eba  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x180023ec1  mov     rcx, rdi; String1
0x180023ec4  call    wcsncmp_0
0x180023ec9  test    eax, eax
0x180023ecb  jnz     short loc_180023EE3
0x180023ecd  xor     r8d, r8d
0x180023ed0  lea     rdx, String2
0x180023ed7  mov     rcx, rbp
0x180023eda  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180023edf  xor     al, al
0x180023ee1  jmp     short loc_180023F4D
0x180023ee3  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x180023eea  mov     rcx, rdi; String1
0x180023eed  call    wcscmp_0
0x180023ef2  test    eax, eax
0x180023ef4  jz      short loc_180023F32
0x180023ef6  add     rsi, 50h ; 'P'
0x180023efa  cmp     qword ptr [rsi+18h], 7
0x180023eff  jbe     short loc_180023F04
0x180023f01  mov     rsi, [rsi]
0x180023f04  movzx   r8d, word ptr [rsi]
0x180023f08  lea     rdx, aWcWs; "%wc:%ws"
0x180023f0f  mov     r9, rdi
0x180023f12  mov     rcx, rbp
0x180023f15  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180023f1a  jmp     short loc_180023F4B
0x180023f1c  lea     r8, [rsi+50h]
0x180023f20  cmp     qword ptr [r8+18h], 7
0x180023f25  jbe     short loc_180023F2A
0x180023f27  mov     r8, [r8]
0x180023f2a  mov     r9, rdi
0x180023f2d  jmp     loc_180023DC2
0x180023f32  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023f36  inc     r8
0x180023f39  cmp     [rdi+r8*2], r14w
0x180023f3e  jnz     short loc_180023F36
0x180023f40  mov     rdx, rdi
0x180023f43  mov     rcx, rbp
0x180023f46  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180023f4b  mov     al, 1
0x180023f4d  add     rsp, 20h
0x180023f51  pop     r14
0x180023f53  pop     rdi
0x180023f54  pop     rsi
0x180023f55  pop     rbp
0x180023f56  pop     rbx
0x180023f57  retn
0x180023f59  mov     ecx, 8000FFFFh; int
0x180023f5e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
