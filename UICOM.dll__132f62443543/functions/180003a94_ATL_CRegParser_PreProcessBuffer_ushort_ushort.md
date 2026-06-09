# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003a94`
- end: `0x180003d32`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `670`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ea8`

## callees

- `0x180002bdc`
- `0x180003558`
- `0x180003a94`
- `0x180004e44`
- `0x180005f60`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003bbe`
- `msvcrt!wcsncpy_s` at `0x180003bbe`
- `KERNEL32!lstrcmpiW` at `0x180003c09`
- `KERNEL32!lstrcmpiW` at `0x180003c09`
- `USER32!CharNextW` at `0x180003b52`
- `USER32!CharNextW` at `0x180003b83`
- `USER32!CharNextW` at `0x180003c6e`
- `USER32!CharNextW` at `0x180003c98`
- `USER32!CharNextW` at `0x180003b52`
- `USER32!CharNextW` at `0x180003b83`
- `USER32!CharNextW` at `0x180003c6e`
- `USER32!CharNextW` at `0x180003c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc5`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rbp
  __int64 v17; // rax
  errno_t v18; // eax
  const wchar_t *v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_48:
    v22 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_49;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_45:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_46;
    }
    v13 = CharNextW(v4);
    *this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_45;
    }
    if ( !v13 )
      goto LABEL_32;
    v16 = 0;
    while ( v14 )
    {
      if ( v14 == 37 )
      {
        v16 = v13;
        break;
      }
      v13 = CharNextW(v13);
      v14 = *v13;
    }
    if ( !v16 )
    {
LABEL_32:
      v22 = -2147352567;
      goto LABEL_49;
    }
    v17 = v16 - *this;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_49;
    }
    v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
    if ( v18 )
    {
      if ( v18 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v18 == 22 || v18 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v18 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v19 = this[1];
    v20 = 0;
    if ( *((int *)v19 + 6) <= 0 )
      goto LABEL_32;
    while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
    {
      if ( ++v20 >= *((_DWORD *)v19 + 6) )
        goto LABEL_32;
    }
    if ( v20 == -1 )
      goto LABEL_32;
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
    if ( !v23 )
      goto LABEL_32;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
LABEL_46:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_48;
    }
  }
  v22 = -2147024882;
LABEL_49:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180003a94  mov     [rsp+arg_8], rbx
0x180003a99  push    rbp
0x180003a9a  push    rsi
0x180003a9b  push    rdi
0x180003a9c  push    r14
0x180003a9e  push    r15
0x180003aa0  sub     rsp, 80h
0x180003aa7  mov     rax, cs:__security_cookie
0x180003aae  xor     rax, rsp
0x180003ab1  mov     [rsp+0A8h+var_38], rax
0x180003ab6  xor     r15d, r15d
0x180003ab9  mov     r14, r8
0x180003abc  mov     rbx, rdx
0x180003abf  mov     rsi, rcx
0x180003ac2  test    rdx, rdx
0x180003ac5  jz      loc_180003CDD
0x180003acb  test    r8, r8
0x180003ace  jz      loc_180003CDD
0x180003ad4  mov     [r8], r15
0x180003ad7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003adb  inc     rax
0x180003ade  cmp     [rdx+rax*2], r15w
0x180003ae3  jnz     short loc_180003ADB
0x180003ae5  add     eax, eax
0x180003ae7  mov     [rsp+0A8h+var_88], r15d
0x180003aec  cmp     eax, 64h ; 'd'
0x180003aef  mov     ecx, 3E8h
0x180003af4  cmovl   eax, ecx
0x180003af7  mov     ecx, eax
0x180003af9  mov     [rsp+0A8h+var_84], eax
0x180003afd  add     rcx, rcx
0x180003b00  mov     eax, 0FFFFFFFFh
0x180003b05  cmp     rcx, rax
0x180003b08  jbe     short loc_180003B1D
0x180003b0a  mov     rcx, r15; pv
0x180003b0d  call    cs:__imp_CoTaskMemFree
0x180003b13  mov     eax, 8007000Eh
0x180003b18  jmp     loc_180003CE2
0x180003b1d  mov     ecx, ecx; cb
0x180003b1f  call    cs:__imp_CoTaskMemAlloc
0x180003b25  mov     [rsp+0A8h+pv], rax
0x180003b2a  mov     rcx, rax
0x180003b2d  test    rax, rax
0x180003b30  jz      short loc_180003B0D
0x180003b32  mov     [rax], r15w
0x180003b36  mov     [rsi], rbx
0x180003b39  movzx   eax, word ptr [rbx]
0x180003b3c  test    ax, ax
0x180003b3f  jz      loc_180003CB5
0x180003b45  cmp     ax, 25h ; '%'
0x180003b49  jnz     loc_180003C7E
0x180003b4f  mov     rcx, rbx; lpsz
0x180003b52  call    cs:__imp_CharNextW
0x180003b58  mov     [rsi], rax
0x180003b5b  movzx   ecx, word ptr [rax]
0x180003b5e  cmp     cx, 25h ; '%'
0x180003b62  jnz     short loc_180003B6C
0x180003b64  mov     rdx, rax
0x180003b67  jmp     loc_180003C81
0x180003b6c  test    rax, rax
0x180003b6f  jz      loc_180003C1A
0x180003b75  mov     rbp, r15
0x180003b78  jmp     short loc_180003B8C
0x180003b7a  cmp     cx, 25h ; '%'
0x180003b7e  jz      short loc_180003B93
0x180003b80  mov     rcx, rax; lpsz
0x180003b83  call    cs:__imp_CharNextW
0x180003b89  movzx   ecx, word ptr [rax]
0x180003b8c  test    cx, cx
0x180003b8f  jnz     short loc_180003B7A
0x180003b91  jmp     short loc_180003B96
0x180003b93  mov     rbp, rax
0x180003b96  test    rbp, rbp
0x180003b99  jz      short loc_180003C1A
0x180003b9b  mov     rax, rbp
0x180003b9e  sub     rax, [rsi]
0x180003ba1  sar     rax, 1
0x180003ba4  cmp     rax, 1Fh
0x180003ba8  jg      loc_180003CCF
0x180003bae  mov     r8, [rsi]; Source
0x180003bb1  lea     rcx, [rsp+0A8h+Destination]; Destination
0x180003bb6  movsxd  r9, eax; MaxCount
0x180003bb9  mov     edx, 20h ; ' '; SizeInWords
0x180003bbe  call    cs:__imp_wcsncpy_s
0x180003bc4  test    eax, eax
0x180003bc6  jz      short loc_180003BEC
0x180003bc8  cmp     eax, 0Ch
0x180003bcb  jz      loc_180003D27
0x180003bd1  cmp     eax, 16h
0x180003bd4  jz      loc_180003D1C
0x180003bda  cmp     eax, 22h ; '"'
0x180003bdd  jz      loc_180003D1C
0x180003be3  cmp     eax, 50h ; 'P'
0x180003be6  jnz     loc_180003D11
0x180003bec  mov     rdi, [rsi+8]
0x180003bf0  mov     ebx, r15d
0x180003bf3  cmp     [rdi+18h], r15d
0x180003bf7  jle     short loc_180003C1A
0x180003bf9  mov     rcx, [rdi+8]
0x180003bfd  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x180003c02  movsxd  rax, ebx
0x180003c05  mov     rcx, [rcx+rax*8]; lpString1
0x180003c09  call    cs:__imp_lstrcmpiW
0x180003c0f  test    eax, eax
0x180003c11  jz      short loc_180003C24
0x180003c13  inc     ebx
0x180003c15  cmp     ebx, [rdi+18h]
0x180003c18  jl      short loc_180003BF9
0x180003c1a  mov     ebx, 80020009h
0x180003c1f  jmp     loc_180003CC0
0x180003c24  cmp     ebx, 0FFFFFFFFh
0x180003c27  jz      short loc_180003C1A
0x180003c29  test    ebx, ebx
0x180003c2b  js      loc_180003D06
0x180003c31  cmp     ebx, [rdi+18h]
0x180003c34  jge     loc_180003D06
0x180003c3a  mov     rax, [rdi+10h]
0x180003c3e  movsxd  rcx, ebx
0x180003c41  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180003c45  test    rdx, rdx
0x180003c48  jz      short loc_180003C1A
0x180003c4a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003c4e  inc     r8; int
0x180003c51  cmp     [rdx+r8*2], r15w
0x180003c56  jnz     short loc_180003C4E
0x180003c58  lea     rcx, [rsp+0A8h+var_88]; this
0x180003c5d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003c62  test    eax, eax
0x180003c64  jz      short loc_180003CD6
0x180003c66  mov     rax, [rsi]
0x180003c69  jmp     short loc_180003C77
0x180003c6b  mov     rcx, rax; lpsz
0x180003c6e  call    cs:__imp_CharNextW
0x180003c74  mov     [rsi], rax
0x180003c77  cmp     rax, rbp
0x180003c7a  jnz     short loc_180003C6B
0x180003c7c  jmp     short loc_180003C95
0x180003c7e  mov     rdx, rbx; unsigned __int16 *
0x180003c81  mov     r8d, 1; int
0x180003c87  lea     rcx, [rsp+0A8h+var_88]; this
0x180003c8c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003c91  test    eax, eax
0x180003c93  jz      short loc_180003CD6
0x180003c95  mov     rcx, [rsi]; lpsz
0x180003c98  call    cs:__imp_CharNextW
0x180003c9e  mov     rbx, rax
0x180003ca1  mov     [rsi], rax
0x180003ca4  movzx   eax, word ptr [rax]
0x180003ca7  test    ax, ax
0x180003caa  jnz     loc_180003B45
0x180003cb0  mov     rcx, [rsp+0A8h+pv]
0x180003cb5  mov     ebx, r15d
0x180003cb8  mov     [rsp+0A8h+pv], r15
0x180003cbd  mov     [r14], rcx
0x180003cc0  mov     rcx, [rsp+0A8h+pv]; pv
0x180003cc5  call    cs:__imp_CoTaskMemFree
0x180003ccb  mov     eax, ebx
0x180003ccd  jmp     short loc_180003CE2
0x180003ccf  mov     ebx, 80004005h
0x180003cd4  jmp     short loc_180003CC0
0x180003cd6  mov     ebx, 8007000Eh
0x180003cdb  jmp     short loc_180003CC0
0x180003cdd  mov     eax, 80004003h
0x180003ce2  mov     rcx, [rsp+0A8h+var_38]
0x180003ce7  xor     rcx, rsp; StackCookie
0x180003cea  call    __security_check_cookie
0x180003cef  mov     rbx, [rsp+0A8h+arg_8]
0x180003cf7  add     rsp, 80h
0x180003cfe  pop     r15
0x180003d00  pop     r14
0x180003d02  pop     rdi
0x180003d03  pop     rsi
0x180003d04  pop     rbp
0x180003d05  retn
0x180003d06  mov     ecx, 0C000008Ch; unsigned int
0x180003d0b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003d10  int     3; Trap to Debugger
0x180003d11  mov     ecx, 80004005h; int
0x180003d16  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003d1c  mov     ecx, 80070057h; int
0x180003d21  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003d27  mov     ecx, 8007000Eh; int
0x180003d2c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
