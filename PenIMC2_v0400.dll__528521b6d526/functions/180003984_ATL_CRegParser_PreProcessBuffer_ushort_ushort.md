# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003984`
- end: `0x180003d7c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `1016`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180005454`

## callees

- `0x180003828`
- `0x180003838`
- `0x180003984`
- `0x180004484`
- `0x18000cdb0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003c53`
- `KERNEL32!lstrcmpiW` at `0x180003c53`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x180003a68`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x180003a68`
- `ucrtbase_clr0400!wcsncpy_s` at `0x180003c09`
- `ucrtbase_clr0400!wcsncpy_s` at `0x180003c09`
- `ole32!CoTaskMemAlloc` at `0x180003a0c`
- `ole32!CoTaskMemAlloc` at `0x180003a0c`
- `ole32!CoTaskMemFree` at `0x180003d15`
- `ole32!CoTaskMemFree` at `0x180003d15`
- `USER32!CharNextW` at `0x180003a7b`
- `USER32!CharNextW` at `0x180003a87`
- `USER32!CharNextW` at `0x180003a93`
- `USER32!CharNextW` at `0x180003a9f`
- `USER32!CharNextW` at `0x180003aee`
- `USER32!CharNextW` at `0x180003b04`
- `USER32!CharNextW` at `0x180003b81`
- `USER32!CharNextW` at `0x180003bd0`
- `USER32!CharNextW` at `0x180003cc5`
- `USER32!CharNextW` at `0x180003cde`
- `USER32!CharNextW` at `0x180003a7b`
- `USER32!CharNextW` at `0x180003a87`
- `USER32!CharNextW` at `0x180003a93`
- `USER32!CharNextW` at `0x180003a9f`
- `USER32!CharNextW` at `0x180003aee`
- `USER32!CharNextW` at `0x180003b04`
- `USER32!CharNextW` at `0x180003b81`
- `USER32!CharNextW` at `0x180003bd0`
- `USER32!CharNextW` at `0x180003cc5`
- `USER32!CharNextW` at `0x180003cde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v3; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  bool v10; // al
  int v11; // r13d
  char v12; // r12
  char v13; // r15
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rdx
  LPWSTR v20; // rsi
  WCHAR v21; // ax
  __int64 v22; // rax
  errno_t v23; // eax
  LPCWSTR v24; // r15
  int v25; // r12d
  __int64 v26; // r14
  const unsigned __int16 *v27; // rdx
  __int64 v28; // r8
  LPWSTR v29; // rax
  unsigned __int16 *v30; // rcx
  char v32; // [rsp+20h] [rbp-69h]
  char v33; // [rsp+21h] [rbp-68h]
  bool v34; // [rsp+22h] [rbp-67h]
  __int64 v35; // [rsp+28h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-59h]
  unsigned __int16 **v37; // [rsp+38h] [rbp-51h]
  __int64 v38; // [rsp+40h] [rbp-49h]
  __int64 v39; // [rsp+48h] [rbp-41h]
  __int64 v40; // [rsp+50h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+60h] [rbp-29h] BYREF

  v37 = a3;
  v3 = a2;
  v5 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v35) = 0;
  HIDWORD(v35) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
LABEL_12:
    v5 = -2147024882;
    goto LABEL_69;
  }
  *this = v3;
  v10 = ATL::_AtlRegisterPerUser;
  v34 = ATL::_AtlRegisterPerUser;
  v11 = 0;
  v12 = 0;
  v33 = 0;
  v13 = 0;
  v32 = 0;
  if ( !*v3 )
  {
LABEL_68:
    v30 = (unsigned __int16 *)pv;
    pv = 0;
    v35 = 0;
    *v37 = v30;
    goto LABEL_69;
  }
  while ( 1 )
  {
    if ( !v10 )
      goto LABEL_35;
    if ( !v11 )
    {
      v14 = wcsstr(v3, L"HKCR");
      if ( v14 )
      {
        if ( v14 == *this )
        {
          v15 = CharNextW(*this);
          *this = v15;
          v16 = CharNextW(v15);
          *this = v16;
          v17 = CharNextW(v16);
          *this = v17;
          *this = CharNextW(v17);
          v38 = 0;
          if ( !ATL::CRegParser::CParseBuffer::Append(
                  (ATL::CRegParser::CParseBuffer *)&v35,
                  L"HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClasses",
                  31) )
            goto LABEL_12;
          v12 = 1;
          v33 = 1;
        }
      }
    }
    if ( **this == 39 )
    {
      if ( !v13 )
      {
        v13 = 1;
        v32 = 1;
        goto LABEL_35;
      }
      if ( *CharNextW(*this) == 39 )
      {
        v18 = CharNextW(*this);
        *this = v18;
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v35, v18, 1) )
          goto LABEL_12;
        goto LABEL_35;
      }
      v13 = 0;
      v32 = 0;
    }
    else if ( v13 )
    {
      goto LABEL_35;
    }
    if ( **this == 123 )
    {
      ++v11;
    }
    else if ( **this == 125 && !--v11 && v12 == 1 )
    {
      v39 = 0;
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v35, L"\r\n\t}\r\n}\r\n", 9) )
        goto LABEL_12;
      v12 = 0;
      v33 = 0;
    }
LABEL_35:
    v19 = *this;
    if ( **this != 37 )
      goto LABEL_38;
    v20 = CharNextW(*this);
    *this = v20;
    v21 = *v20;
    if ( *v20 != 37 )
      break;
    v19 = v20;
LABEL_38:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v35, v19, 1) )
      goto LABEL_12;
LABEL_65:
    v3 = CharNextW(*this);
    *this = v3;
    if ( !*v3 )
      goto LABEL_68;
    v10 = v34;
  }
  if ( v20 )
  {
    while ( v21 )
    {
      if ( v21 == 37 )
      {
        if ( !v20 )
          break;
        v22 = v20 - *this;
        if ( v22 > 31 )
        {
          v5 = -2147467259;
          goto LABEL_69;
        }
        v23 = wcsncpy_s(Destination, 0x20u, *this, (int)v22);
        if ( v23 )
        {
          if ( v23 == 12 )
            ATL::AtlThrowImpl(-2147024882);
          if ( v23 == 22 || v23 == 34 )
            ATL::AtlThrowImpl(-2147024809);
          if ( v23 != 80 )
            ATL::AtlThrowImpl(-2147467259);
        }
        v24 = this[1];
        v25 = 0;
        v26 = 0;
        if ( *((int *)v24 + 6) <= 0 )
          break;
        while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v24 + 1) + 8 * v26), Destination) )
        {
          ++v25;
          ++v26;
          if ( v25 >= *((_DWORD *)v24 + 6) )
            goto LABEL_54;
        }
        if ( v26 == -1 )
          break;
        if ( v26 < 0 || v25 >= *((_DWORD *)v24 + 6) )
        {
          ATL::_AtlRaiseException(0xC000008C, 1u);
          __debugbreak();
        }
        v27 = *(const unsigned __int16 **)(*((_QWORD *)v24 + 2) + 8 * v26);
        if ( !v27 )
          break;
        v40 = 0;
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] );
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v35, v27, v28) )
          goto LABEL_12;
        if ( *this != v20 )
        {
          do
          {
            v29 = CharNextW(*this);
            *this = v29;
          }
          while ( v29 != v20 );
        }
        v12 = v33;
        v13 = v32;
        goto LABEL_65;
      }
      v20 = CharNextW(v20);
      v21 = *v20;
    }
  }
LABEL_54:
  v5 = -2147352567;
LABEL_69:
  CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x180003984  mov     [rsp-8+arg_8], rbx
0x180003989  push    rbp
0x18000398a  push    rsi
0x18000398b  push    rdi
0x18000398c  push    r12
0x18000398e  push    r13
0x180003990  push    r14
0x180003992  push    r15
0x180003994  lea     rbp, [rsp-27h]
0x180003999  sub     rsp, 0B0h
0x1800039a0  mov     rax, cs:__security_cookie
0x1800039a7  xor     rax, rsp
0x1800039aa  mov     [rbp+57h+var_40], rax
0x1800039ae  mov     rax, r8
0x1800039b1  mov     [rbp+57h+var_A8], rax
0x1800039b5  mov     rsi, rdx
0x1800039b8  mov     rdi, rcx
0x1800039bb  xor     ebx, ebx
0x1800039bd  test    rdx, rdx
0x1800039c0  jz      loc_180003D1F
0x1800039c6  test    rax, rax
0x1800039c9  jz      loc_180003D1F
0x1800039cf  mov     [r8], rbx
0x1800039d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800039d6  inc     rax
0x1800039d9  cmp     [rdx+rax*2], bx
0x1800039dd  jnz     short loc_1800039D6
0x1800039df  add     eax, eax
0x1800039e1  mov     ecx, 3E8h
0x1800039e6  cmp     eax, 64h ; 'd'
0x1800039e9  cmovl   eax, ecx
0x1800039ec  mov     dword ptr [rbp+57h+var_B8], ebx
0x1800039ef  mov     dword ptr [rbp+57h+var_B8+4], eax
0x1800039f2  mov     ecx, eax
0x1800039f4  add     rcx, rcx
0x1800039f7  mov     eax, 0FFFFFFFFh
0x1800039fc  cmp     rcx, rax
0x1800039ff  jbe     short loc_180003A0A
0x180003a01  mov     rax, rbx
0x180003a04  mov     [rbp+57h+pv], rbx
0x180003a08  jmp     short loc_180003A1E
0x180003a0a  mov     ecx, ecx; cb
0x180003a0c  call    cs:__imp_CoTaskMemAlloc
0x180003a12  mov     [rbp+57h+pv], rax
0x180003a16  test    rax, rax
0x180003a19  jz      short loc_180003A1E
0x180003a1b  mov     [rax], bx
0x180003a1e  test    rax, rax
0x180003a21  jnz     short loc_180003A2D
0x180003a23  mov     ebx, 8007000Eh
0x180003a28  jmp     loc_180003D11
0x180003a2d  mov     [rdi], rsi
0x180003a30  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA
0x180003a36  mov     [rbp+57h+var_BE], al
0x180003a39  mov     r13d, ebx
0x180003a3c  mov     r12b, bl
0x180003a3f  mov     [rbp+57h+var_BF], bl
0x180003a42  mov     r15b, bl
0x180003a45  mov     [rbp+57h+var_C0], bl
0x180003a48  cmp     [rsi], bx
0x180003a4b  jz      loc_180003CFE
0x180003a51  cmp     al, 1
0x180003a53  jnz     loc_180003B75
0x180003a59  test    r13d, r13d
0x180003a5c  jnz     short loc_180003AD0
0x180003a5e  lea     rdx, aHkcr
0x180003a65  mov     rcx, rsi; Str
0x180003a68  call    cs:__imp_wcsstr
0x180003a6e  test    rax, rax
0x180003a71  jz      short loc_180003AD0
0x180003a73  cmp     rax, [rdi]
0x180003a76  jnz     short loc_180003AD0
0x180003a78  mov     rcx, [rdi]; lpsz
0x180003a7b  call    cs:__imp_CharNextW
0x180003a81  mov     [rdi], rax
0x180003a84  mov     rcx, rax; lpsz
0x180003a87  call    cs:__imp_CharNextW
0x180003a8d  mov     [rdi], rax
0x180003a90  mov     rcx, rax; lpsz
0x180003a93  call    cs:__imp_CharNextW
0x180003a99  mov     [rdi], rax
0x180003a9c  mov     rcx, rax; lpsz
0x180003a9f  call    cs:__imp_CharNextW
0x180003aa5  mov     [rdi], rax
0x180003aa8  mov     [rbp+57h+var_A0], rbx
0x180003aac  lea     r8d, [r13+1Fh]; int
0x180003ab0  lea     rdx, aHkcuSoftwareCl
0x180003ab7  lea     rcx, [rbp+57h+var_B8]; this
0x180003abb  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z
0x180003ac0  nop
0x180003ac1  test    eax, eax
0x180003ac3  jz      loc_180003A23
0x180003ac9  mov     r12b, 1
0x180003acc  mov     [rbp+57h+var_BF], r12b
0x180003ad0  mov     rcx, [rdi]; lpsz
0x180003ad3  mov     esi, 27h ; '''
0x180003ad8  cmp     si, [rcx]
0x180003adb  jnz     short loc_180003B29
0x180003add  test    r15b, r15b
0x180003ae0  jnz     short loc_180003AEE
0x180003ae2  mov     r15b, 1
0x180003ae5  mov     [rbp+57h+var_C0], r15b
0x180003ae9  jmp     loc_180003B75
0x180003aee  call    cs:__imp_CharNextW
0x180003af4  cmp     si, [rax]
0x180003af7  jz      short loc_180003B01
0x180003af9  mov     r15b, bl
0x180003afc  mov     [rbp+57h+var_C0], bl
0x180003aff  jmp     short loc_180003B2E
0x180003b01  mov     rcx, [rdi]; lpsz
0x180003b04  call    cs:__imp_CharNextW
0x180003b0a  mov     [rdi], rax
0x180003b0d  mov     r8d, 1; int
0x180003b13  mov     rdx, rax; unsigned __int16 *
0x180003b16  lea     rcx, [rbp+57h+var_B8]; this
0x180003b1a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z
0x180003b1f  test    eax, eax
0x180003b21  jz      loc_180003A23
0x180003b27  jmp     short loc_180003B75
0x180003b29  test    r15b, r15b
0x180003b2c  jnz     short loc_180003B75
0x180003b2e  mov     rax, [rdi]
0x180003b31  cmp     word ptr [rax], 7Bh ; '{'
0x180003b35  jnz     short loc_180003B3C
0x180003b37  inc     r13d
0x180003b3a  jmp     short loc_180003B75
0x180003b3c  cmp     word ptr [rax], 7Dh ; '}'
0x180003b40  jnz     short loc_180003B75
0x180003b42  sub     r13d, 1
0x180003b46  jnz     short loc_180003B75
0x180003b48  cmp     r12b, 1
0x180003b4c  jnz     short loc_180003B75
0x180003b4e  mov     [rbp+57h+var_98], rbx
0x180003b52  lea     r8d, [r13+9]; int
0x180003b56  lea     rdx, asc_180012D00
0x180003b5d  lea     rcx, [rbp+57h+var_B8]; this
0x180003b61  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z
0x180003b66  nop
0x180003b67  test    eax, eax
0x180003b69  jz      loc_180003A23
0x180003b6f  mov     r12b, bl
0x180003b72  mov     [rbp+57h+var_BF], bl
0x180003b75  mov     rdx, [rdi]
0x180003b78  cmp     word ptr [rdx], 25h ; '%'
0x180003b7c  jnz     short loc_180003B99
0x180003b7e  mov     rcx, rdx; lpsz
0x180003b81  call    cs:__imp_CharNextW
0x180003b87  mov     rsi, rax
0x180003b8a  mov     [rdi], rax
0x180003b8d  movzx   eax, word ptr [rax]
0x180003b90  cmp     ax, 25h ; '%'
0x180003b94  jnz     short loc_180003BB5
0x180003b96  mov     rdx, rsi; unsigned __int16 *
0x180003b99  mov     r8d, 1; int
0x180003b9f  lea     rcx, [rbp+57h+var_B8]; this
0x180003ba3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z
0x180003ba8  test    eax, eax
0x180003baa  jz      loc_180003A23
0x180003bb0  jmp     loc_180003CDB
0x180003bb5  test    rsi, rsi
0x180003bb8  jz      loc_180003C69
0x180003bbe  test    ax, ax
0x180003bc1  jz      loc_180003C69
0x180003bc7  cmp     ax, 25h ; '%'
0x180003bcb  jz      short loc_180003BDE
0x180003bcd  mov     rcx, rsi; lpsz
0x180003bd0  call    cs:__imp_CharNextW
0x180003bd6  mov     rsi, rax
0x180003bd9  movzx   eax, word ptr [rax]
0x180003bdc  jmp     short loc_180003BBE
0x180003bde  test    rsi, rsi
0x180003be1  jz      loc_180003C69
0x180003be7  mov     rax, rsi
0x180003bea  sub     rax, [rdi]
0x180003bed  sar     rax, 1
0x180003bf0  cmp     rax, 1Fh
0x180003bf4  jg      loc_180003CF7
0x180003bfa  movsxd  r9, eax; MaxCount
0x180003bfd  mov     r8, [rdi]; Source
0x180003c00  mov     edx, 20h ; ' '; SizeInWords
0x180003c05  lea     rcx, [rbp+57h+Destination]; Destination
0x180003c09  call    cs:__imp_wcsncpy_s
0x180003c0f  test    eax, eax
0x180003c11  jz      short loc_180003C37
0x180003c13  cmp     eax, 0Ch
0x180003c16  jz      loc_180003D71
0x180003c1c  cmp     eax, 16h
0x180003c1f  jz      loc_180003D66
0x180003c25  cmp     eax, 22h ; '"'
0x180003c28  jz      loc_180003D66
0x180003c2e  cmp     eax, 50h ; 'P'
0x180003c31  jnz     loc_180003D5B
0x180003c37  mov     r15, [rdi+8]
0x180003c3b  mov     r12d, ebx
0x180003c3e  mov     r14, rbx
0x180003c41  cmp     [r15+18h], ebx
0x180003c45  jle     short loc_180003C69
0x180003c47  mov     rax, [r15+8]
0x180003c4b  lea     rdx, [rbp+57h+Destination]; lpString2
0x180003c4f  mov     rcx, [rax+r14*8]; lpString1
0x180003c53  call    cs:__imp_lstrcmpiW
0x180003c59  test    eax, eax
0x180003c5b  jz      short loc_180003C73
0x180003c5d  inc     r12d
0x180003c60  inc     r14
0x180003c63  cmp     r12d, [r15+18h]
0x180003c67  jl      short loc_180003C47
0x180003c69  mov     ebx, 80020009h
0x180003c6e  jmp     loc_180003D11
0x180003c73  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180003c77  jz      short loc_180003C69
0x180003c79  test    r14, r14
0x180003c7c  js      loc_180003D4B
0x180003c82  cmp     r12d, [r15+18h]
0x180003c86  jge     loc_180003D4B
0x180003c8c  mov     rax, [r15+10h]
0x180003c90  mov     rdx, [rax+r14*8]; unsigned __int16 *
0x180003c94  test    rdx, rdx
0x180003c97  jz      short loc_180003C69
0x180003c99  mov     [rbp+57h+var_90], rbx
0x180003c9d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003ca1  inc     r8; int
0x180003ca4  cmp     [rdx+r8*2], bx
0x180003ca9  jnz     short loc_180003CA1
0x180003cab  lea     rcx, [rbp+57h+var_B8]; this
0x180003caf  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z
0x180003cb4  nop
0x180003cb5  test    eax, eax
0x180003cb7  jz      loc_180003A23
0x180003cbd  cmp     [rdi], rsi
0x180003cc0  jz      short loc_180003CD3
0x180003cc2  mov     rcx, [rdi]; lpsz
0x180003cc5  call    cs:__imp_CharNextW
0x180003ccb  mov     [rdi], rax
0x180003cce  cmp     rax, rsi
0x180003cd1  jnz     short loc_180003CC2
0x180003cd3  mov     r12b, [rbp+57h+var_BF]
0x180003cd7  mov     r15b, [rbp+57h+var_C0]
0x180003cdb  mov     rcx, [rdi]; lpsz
0x180003cde  call    cs:__imp_CharNextW
0x180003ce4  mov     rsi, rax
0x180003ce7  mov     [rdi], rax
0x180003cea  cmp     [rax], bx
0x180003ced  jz      short loc_180003CFE
0x180003cef  mov     al, [rbp+57h+var_BE]
0x180003cf2  jmp     loc_180003A51
0x180003cf7  mov     ebx, 80004005h
0x180003cfc  jmp     short loc_180003D11
0x180003cfe  mov     rcx, [rbp+57h+pv]
0x180003d02  mov     [rbp+57h+pv], rbx
0x180003d06  mov     [rbp+57h+var_B8], rbx
0x180003d0a  mov     rax, [rbp+57h+var_A8]
0x180003d0e  mov     [rax], rcx
0x180003d11  mov     rcx, [rbp+57h+pv]; pv
0x180003d15  call    cs:__imp_CoTaskMemFree
0x180003d1b  mov     eax, ebx
0x180003d1d  jmp     short loc_180003D24
0x180003d1f  mov     eax, 80004003h
0x180003d24  mov     rcx, [rbp+57h+var_40]
0x180003d28  xor     rcx, rsp; StackCookie
0x180003d2b  call    __security_check_cookie
0x180003d30  mov     rbx, [rsp+0E0h+arg_8]
0x180003d38  add     rsp, 0B0h
0x180003d3f  pop     r15
0x180003d41  pop     r14
0x180003d43  pop     r13
0x180003d45  pop     r12
0x180003d47  pop     rdi
0x180003d48  pop     rsi
0x180003d49  pop     rbp
0x180003d4a  retn
0x180003d4b  mov     edx, 1; unsigned int
0x180003d50  mov     ecx, 0C000008Ch; unsigned int
0x180003d55  call    ?_AtlRaiseException@ATL@@YAXKK@Z
0x180003d5a  int     3; Trap to Debugger
0x180003d5b  mov     ecx, 80004005h; int
0x180003d60  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x180003d66  mov     ecx, 80070057h; int
0x180003d6b  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x180003d71  mov     ecx, 8007000Eh; int
0x180003d76  call    ?AtlThrowImpl@ATL@@YAXJ@Z
```
