# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180022cf4`
- end: `0x180022ee5`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180020204`
- `0x18002476c`

## callees

- `0x180010db8`
- `0x180016440`
- `0x180019260`
- `0x180022cf4`
- `0x180035884`
- `0x180035890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180022d2a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180022d2a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180022da1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180022df0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180022da1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180022df0`

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
0x180022cf4  push    rbx
0x180022cf6  push    rbp
0x180022cf7  push    rsi
0x180022cf8  push    rdi
0x180022cf9  push    r14
0x180022cfb  sub     rsp, 20h
0x180022cff  mov     rbx, [rcx]
0x180022d02  mov     rbp, r8
0x180022d05  mov     rdi, rdx
0x180022d08  mov     rsi, rcx
0x180022d0b  xor     r14d, r14d
0x180022d0e  cmp     rbx, [rsi+8]
0x180022d12  jz      short loc_180022D64
0x180022d14  cmp     qword ptr [rbx+18h], 7
0x180022d19  jbe     short loc_180022D20
0x180022d1b  mov     rcx, [rbx]
0x180022d1e  jmp     short loc_180022D23
0x180022d20  mov     rcx, rbx
0x180022d23  mov     r8, [rbx+10h]
0x180022d27  mov     rdx, rdi
0x180022d2a  call    cs:__imp__o__wcsnicmp
0x180022d30  test    eax, eax
0x180022d32  jz      short loc_180022D3A
0x180022d34  add     rbx, 40h ; '@'
0x180022d38  jmp     short loc_180022D0E
0x180022d3a  mov     rax, [rbx+10h]
0x180022d3e  lea     r8, [rbx+20h]
0x180022d42  cmp     qword ptr [r8+18h], 7
0x180022d47  lea     r9, [rdi+rax*2]
0x180022d4b  jbe     short loc_180022D50
0x180022d4d  mov     r8, [r8]
0x180022d50  lea     rdx, aWsWs; "%ws%ws"
0x180022d57  mov     rcx, rbp
0x180022d5a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180022d5f  jmp     loc_180022ECD
0x180022d64  mov     rbx, [rsi+18h]
0x180022d68  cmp     rbx, [rsi+20h]
0x180022d6c  jz      short loc_180022D97
0x180022d6e  cmp     qword ptr [rbx+18h], 7
0x180022d73  jbe     short loc_180022D7A
0x180022d75  mov     rcx, [rbx]
0x180022d78  jmp     short loc_180022D7D
0x180022d7a  mov     rcx, rbx; String1
0x180022d7d  mov     r8d, [rbx+10h]; MaxCount
0x180022d81  mov     rdx, rdi; String2
0x180022d84  call    wcsncmp_0
0x180022d89  test    eax, eax
0x180022d8b  jz      loc_180022E4F
0x180022d91  add     rbx, 20h ; ' '
0x180022d95  jmp     short loc_180022D68
0x180022d97  mov     ebx, 5Ch ; '\'
0x180022d9c  mov     rcx, rdi; Str
0x180022d9f  mov     edx, ebx; Ch
0x180022da1  call    cs:__imp_wcschr
0x180022da7  test    rax, rax
0x180022daa  jnz     short loc_180022DD0
0x180022dac  cmp     [rsi+40h], r14
0x180022db0  jz      loc_180022EDA
0x180022db6  lea     r8, [rsi+30h]
0x180022dba  cmp     qword ptr [r8+18h], 7
0x180022dbf  jbe     short loc_180022DC4
0x180022dc1  mov     r8, [r8]
0x180022dc4  mov     r9, rdi
0x180022dc7  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x180022dce  jmp     short loc_180022D57
0x180022dd0  cmp     [rdi], bx
0x180022dd3  jnz     short loc_180022E12
0x180022dd5  cmp     word ptr [rdi+2], 3Bh ; ';'
0x180022dda  jnz     short loc_180022E12
0x180022ddc  cmp     [rdi+4], r14w
0x180022de1  jz      short loc_180022E12
0x180022de3  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180022de8  jnz     short loc_180022E12
0x180022dea  mov     edx, ebx; Ch
0x180022dec  lea     rcx, [rdi+8]; Str
0x180022df0  call    cs:__imp_wcschr
0x180022df6  test    rax, rax
0x180022df9  jz      short loc_180022E12
0x180022dfb  mov     r8, rax
0x180022dfe  lea     rdx, aWs; "\\%ws"
0x180022e05  mov     rcx, rbp
0x180022e08  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180022e0d  jmp     loc_180022ECD
0x180022e12  cmp     [rdi], r14w
0x180022e16  jz      loc_180022EB4
0x180022e1c  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180022e21  jz      loc_180022EB4
0x180022e27  cmp     [rsi+60h], r14
0x180022e2b  jz      loc_180022EDA
0x180022e31  cmp     [rdi], bx
0x180022e34  jnz     short loc_180022E9E
0x180022e36  mov     r8d, 8; MaxCount
0x180022e3c  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x180022e43  mov     rcx, rdi; String1
0x180022e46  call    wcsncmp_0
0x180022e4b  test    eax, eax
0x180022e4d  jnz     short loc_180022E65
0x180022e4f  xor     r8d, r8d
0x180022e52  lea     rdx, String2
0x180022e59  mov     rcx, rbp
0x180022e5c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180022e61  xor     al, al
0x180022e63  jmp     short loc_180022ECF
0x180022e65  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x180022e6c  mov     rcx, rdi; String1
0x180022e6f  call    wcscmp_0
0x180022e74  test    eax, eax
0x180022e76  jz      short loc_180022EB4
0x180022e78  add     rsi, 50h ; 'P'
0x180022e7c  cmp     qword ptr [rsi+18h], 7
0x180022e81  jbe     short loc_180022E86
0x180022e83  mov     rsi, [rsi]
0x180022e86  movzx   r8d, word ptr [rsi]
0x180022e8a  lea     rdx, aWcWs; "%wc:%ws"
0x180022e91  mov     r9, rdi
0x180022e94  mov     rcx, rbp
0x180022e97  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180022e9c  jmp     short loc_180022ECD
0x180022e9e  lea     r8, [rsi+50h]
0x180022ea2  cmp     qword ptr [r8+18h], 7
0x180022ea7  jbe     short loc_180022EAC
0x180022ea9  mov     r8, [r8]
0x180022eac  mov     r9, rdi
0x180022eaf  jmp     loc_180022D50
0x180022eb4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022eb8  inc     r8
0x180022ebb  cmp     [rdi+r8*2], r14w
0x180022ec0  jnz     short loc_180022EB8
0x180022ec2  mov     rdx, rdi
0x180022ec5  mov     rcx, rbp
0x180022ec8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180022ecd  mov     al, 1
0x180022ecf  add     rsp, 20h
0x180022ed3  pop     r14
0x180022ed5  pop     rdi
0x180022ed6  pop     rsi
0x180022ed7  pop     rbp
0x180022ed8  pop     rbx
0x180022ed9  retn
0x180022eda  mov     ecx, 8000FFFFh; int
0x180022edf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
