# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000695c`
- end: `0x180006c14`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f6c`

## callees

- `0x180002470`
- `0x180004d80`
- `0x180004eb8`
- `0x18000695c`
- `0x180008fec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180006a9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180006a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800069e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800069e8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a32`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a63`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b50`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a32`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a63`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b50`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ae7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ae7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v28; // [rsp+30h] [rbp-29h]
  WCHAR String2[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
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
  v26[0] = 0;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_50:
    v22 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_51;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_47:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *(_QWORD *)this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_47;
    }
    if ( !v13 )
      goto LABEL_34;
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
LABEL_34:
      v22 = -2147352567;
      goto LABEL_51;
    }
    v17 = ((__int64)v16 - *(_QWORD *)this) >> 1;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_51;
    }
    v18 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v17);
    if ( v18 )
    {
      if ( v18 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v18 == 22 || v18 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v18 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v19 = *((_QWORD *)this + 1);
    v20 = 0;
    if ( *(int *)(v19 + 24) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(v19 + 8) + 8LL * v20), String2) )
    {
      if ( ++v20 >= *(_DWORD *)(v19 + 24) )
        goto LABEL_34;
    }
    if ( v20 == -1 )
      goto LABEL_34;
    if ( v20 < 0 || v20 >= *(_DWORD *)(v19 + 24) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*(_QWORD *)(v19 + 16) + 8LL * v20);
    if ( !v23 )
      goto LABEL_34;
    v28 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_50;
    }
  }
  v22 = -2147024882;
LABEL_51:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x18000695c  mov     [rsp-8+arg_8], rbx
0x180006961  mov     [rsp-8+arg_18], rsi
0x180006966  push    rbp
0x180006967  push    rdi
0x180006968  push    r12
0x18000696a  push    r14
0x18000696c  push    r15
0x18000696e  lea     rbp, [rsp-37h]
0x180006973  sub     rsp, 90h
0x18000697a  mov     rax, cs:__security_cookie
0x180006981  xor     rax, rsp
0x180006984  mov     [rbp+57h+var_30], rax
0x180006988  mov     r15, r8
0x18000698b  mov     rbx, rdx
0x18000698e  mov     r14, rcx
0x180006991  xor     r12d, r12d
0x180006994  test    rdx, rdx
0x180006997  jz      loc_180006BBB
0x18000699d  test    r8, r8
0x1800069a0  jz      loc_180006BBB
0x1800069a6  mov     [r8], r12
0x1800069a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800069ad  inc     rax
0x1800069b0  cmp     [rdx+rax*2], r12w
0x1800069b5  jnz     short loc_1800069AD
0x1800069b7  add     eax, eax
0x1800069b9  mov     ecx, 3E8h
0x1800069be  cmp     eax, 64h ; 'd'
0x1800069c1  cmovl   eax, ecx
0x1800069c4  mov     [rbp+57h+var_90], r12d
0x1800069c8  mov     [rbp+57h+var_8C], eax
0x1800069cb  mov     ecx, eax
0x1800069cd  add     rcx, rcx
0x1800069d0  mov     eax, 0FFFFFFFFh
0x1800069d5  cmp     rcx, rax
0x1800069d8  jbe     short loc_1800069E6
0x1800069da  mov     rax, r12
0x1800069dd  mov     rdx, r12
0x1800069e0  mov     [rbp+57h+pv], rdx
0x1800069e4  jmp     short loc_1800069FE
0x1800069e6  mov     ecx, ecx; cb
0x1800069e8  call    cs:__imp_CoTaskMemAlloc
0x1800069ee  mov     rdx, rax
0x1800069f1  mov     [rbp+57h+pv], rax
0x1800069f5  test    rax, rax
0x1800069f8  jz      short loc_1800069FE
0x1800069fa  mov     [rax], r12w
0x1800069fe  test    rax, rax
0x180006a01  jnz     short loc_180006A16
0x180006a03  mov     rcx, rax; pv
0x180006a06  call    cs:__imp_CoTaskMemFree
0x180006a0c  mov     eax, 8007000Eh
0x180006a11  jmp     loc_180006BC0
0x180006a16  mov     [r14], rbx
0x180006a19  movzx   eax, word ptr [rbx]
0x180006a1c  test    ax, ax
0x180006a1f  jz      loc_180006B95
0x180006a25  cmp     ax, 25h ; '%'
0x180006a29  jnz     loc_180006B60
0x180006a2f  mov     rcx, rbx; lpsz
0x180006a32  call    cs:__imp_CharNextW
0x180006a38  mov     [r14], rax
0x180006a3b  movzx   ecx, word ptr [rax]
0x180006a3e  cmp     cx, 25h ; '%'
0x180006a42  jnz     short loc_180006A4C
0x180006a44  mov     rdx, rax
0x180006a47  jmp     loc_180006B63
0x180006a4c  test    rax, rax
0x180006a4f  jz      loc_180006AF8
0x180006a55  mov     rsi, r12
0x180006a58  jmp     short loc_180006A6C
0x180006a5a  cmp     cx, 25h ; '%'
0x180006a5e  jz      short loc_180006A73
0x180006a60  mov     rcx, rax; lpsz
0x180006a63  call    cs:__imp_CharNextW
0x180006a69  movzx   ecx, word ptr [rax]
0x180006a6c  test    cx, cx
0x180006a6f  jnz     short loc_180006A5A
0x180006a71  jmp     short loc_180006A76
0x180006a73  mov     rsi, rax
0x180006a76  test    rsi, rsi
0x180006a79  jz      short loc_180006AF8
0x180006a7b  mov     rax, rsi
0x180006a7e  sub     rax, [r14]
0x180006a81  sar     rax, 1
0x180006a84  cmp     rax, 1Fh
0x180006a88  jg      loc_180006BAD
0x180006a8e  movsxd  r9, eax
0x180006a91  mov     r8, [r14]
0x180006a94  mov     edx, 20h ; ' '
0x180006a99  lea     rcx, [rbp+57h+String2]
0x180006a9d  call    cs:__imp__o_wcsncpy_s
0x180006aa3  test    eax, eax
0x180006aa5  jz      short loc_180006ACB
0x180006aa7  cmp     eax, 0Ch
0x180006aaa  jz      loc_180006C09
0x180006ab0  cmp     eax, 16h
0x180006ab3  jz      loc_180006BFE
0x180006ab9  cmp     eax, 22h ; '"'
0x180006abc  jz      loc_180006BFE
0x180006ac2  cmp     eax, 50h ; 'P'
0x180006ac5  jnz     loc_180006BF3
0x180006acb  mov     rdi, [r14+8]
0x180006acf  mov     ebx, r12d
0x180006ad2  cmp     [rdi+18h], r12d
0x180006ad6  jle     short loc_180006AF8
0x180006ad8  movsxd  rax, ebx
0x180006adb  mov     rcx, [rdi+8]
0x180006adf  lea     rdx, [rbp+57h+String2]; lpString2
0x180006ae3  mov     rcx, [rcx+rax*8]; lpString1
0x180006ae7  call    cs:__imp_lstrcmpiW
0x180006aed  test    eax, eax
0x180006aef  jz      short loc_180006B02
0x180006af1  inc     ebx
0x180006af3  cmp     ebx, [rdi+18h]
0x180006af6  jl      short loc_180006AD8
0x180006af8  mov     ebx, 80020009h
0x180006afd  jmp     loc_180006B9F
0x180006b02  cmp     ebx, 0FFFFFFFFh
0x180006b05  jz      short loc_180006AF8
0x180006b07  test    ebx, ebx
0x180006b09  js      loc_180006BE8
0x180006b0f  cmp     ebx, [rdi+18h]
0x180006b12  jge     loc_180006BE8
0x180006b18  movsxd  rcx, ebx
0x180006b1b  mov     rax, [rdi+10h]
0x180006b1f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180006b23  test    rdx, rdx
0x180006b26  jz      short loc_180006AF8
0x180006b28  mov     [rbp+57h+var_80], r12
0x180006b2c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006b30  inc     r8; int
0x180006b33  cmp     [rdx+r8*2], r12w
0x180006b38  jnz     short loc_180006B30
0x180006b3a  lea     rcx, [rbp+57h+var_90]; this
0x180006b3e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006b43  nop
0x180006b44  test    eax, eax
0x180006b46  jz      short loc_180006BB4
0x180006b48  mov     rax, [r14]
0x180006b4b  jmp     short loc_180006B59
0x180006b4d  mov     rcx, rax; lpsz
0x180006b50  call    cs:__imp_CharNextW
0x180006b56  mov     [r14], rax
0x180006b59  cmp     rax, rsi
0x180006b5c  jnz     short loc_180006B4D
0x180006b5e  jmp     short loc_180006B76
0x180006b60  mov     rdx, rbx; unsigned __int16 *
0x180006b63  mov     r8d, 1; int
0x180006b69  lea     rcx, [rbp+57h+var_90]; this
0x180006b6d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006b72  test    eax, eax
0x180006b74  jz      short loc_180006BB4
0x180006b76  mov     rcx, [r14]; lpsz
0x180006b79  call    cs:__imp_CharNextW
0x180006b7f  mov     rbx, rax
0x180006b82  mov     [r14], rax
0x180006b85  movzx   eax, word ptr [rax]
0x180006b88  test    ax, ax
0x180006b8b  jnz     loc_180006A25
0x180006b91  mov     rdx, [rbp+57h+pv]
0x180006b95  mov     ebx, r12d
0x180006b98  mov     [rbp+57h+pv], r12
0x180006b9c  mov     [r15], rdx
0x180006b9f  mov     rcx, [rbp+57h+pv]; pv
0x180006ba3  call    cs:__imp_CoTaskMemFree
0x180006ba9  mov     eax, ebx
0x180006bab  jmp     short loc_180006BC0
0x180006bad  mov     ebx, 80004005h
0x180006bb2  jmp     short loc_180006B9F
0x180006bb4  mov     ebx, 8007000Eh
0x180006bb9  jmp     short loc_180006B9F
0x180006bbb  mov     eax, 80004003h
0x180006bc0  mov     rcx, [rbp+57h+var_30]
0x180006bc4  xor     rcx, rsp; StackCookie
0x180006bc7  call    __security_check_cookie
0x180006bcc  lea     r11, [rsp+0B0h+var_20]
0x180006bd4  mov     rbx, [r11+38h]
0x180006bd8  mov     rsi, [r11+48h]
0x180006bdc  mov     rsp, r11
0x180006bdf  pop     r15
0x180006be1  pop     r14
0x180006be3  pop     r12
0x180006be5  pop     rdi
0x180006be6  pop     rbp
0x180006be7  retn
0x180006be8  mov     ecx, 0C000008Ch; unsigned int
0x180006bed  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006bf2  int     3; Trap to Debugger
0x180006bf3  mov     ecx, 80004005h; int
0x180006bf8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006bfe  mov     ecx, 80070057h; int
0x180006c03  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006c09  mov     ecx, 8007000Eh; int
0x180006c0e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
