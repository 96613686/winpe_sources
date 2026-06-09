# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180007aac`
- end: `0x180007d64`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800080bc`

## callees

- `0x1800033d0`
- `0x180005ee0`
- `0x180006018`
- `0x180007aac`
- `0x18000a0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180007bed`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180007bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cf3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007b82`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007bb3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ca0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007cc9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007b82`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007bb3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ca0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007cc9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007c37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007c37`

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
0x180007aac  mov     [rsp-8+arg_8], rbx
0x180007ab1  mov     [rsp-8+arg_18], rsi
0x180007ab6  push    rbp
0x180007ab7  push    rdi
0x180007ab8  push    r12
0x180007aba  push    r14
0x180007abc  push    r15
0x180007abe  lea     rbp, [rsp-37h]
0x180007ac3  sub     rsp, 90h
0x180007aca  mov     rax, cs:__security_cookie
0x180007ad1  xor     rax, rsp
0x180007ad4  mov     [rbp+57h+var_30], rax
0x180007ad8  mov     r15, r8
0x180007adb  mov     rbx, rdx
0x180007ade  mov     r14, rcx
0x180007ae1  xor     r12d, r12d
0x180007ae4  test    rdx, rdx
0x180007ae7  jz      loc_180007D0B
0x180007aed  test    r8, r8
0x180007af0  jz      loc_180007D0B
0x180007af6  mov     [r8], r12
0x180007af9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007afd  inc     rax
0x180007b00  cmp     [rdx+rax*2], r12w
0x180007b05  jnz     short loc_180007AFD
0x180007b07  add     eax, eax
0x180007b09  mov     ecx, 3E8h
0x180007b0e  cmp     eax, 64h ; 'd'
0x180007b11  cmovl   eax, ecx
0x180007b14  mov     [rbp+57h+var_90], r12d
0x180007b18  mov     [rbp+57h+var_8C], eax
0x180007b1b  mov     ecx, eax
0x180007b1d  add     rcx, rcx
0x180007b20  mov     eax, 0FFFFFFFFh
0x180007b25  cmp     rcx, rax
0x180007b28  jbe     short loc_180007B36
0x180007b2a  mov     rax, r12
0x180007b2d  mov     rdx, r12
0x180007b30  mov     [rbp+57h+pv], rdx
0x180007b34  jmp     short loc_180007B4E
0x180007b36  mov     ecx, ecx; cb
0x180007b38  call    cs:__imp_CoTaskMemAlloc
0x180007b3e  mov     rdx, rax
0x180007b41  mov     [rbp+57h+pv], rax
0x180007b45  test    rax, rax
0x180007b48  jz      short loc_180007B4E
0x180007b4a  mov     [rax], r12w
0x180007b4e  test    rax, rax
0x180007b51  jnz     short loc_180007B66
0x180007b53  mov     rcx, rax; pv
0x180007b56  call    cs:__imp_CoTaskMemFree
0x180007b5c  mov     eax, 8007000Eh
0x180007b61  jmp     loc_180007D10
0x180007b66  mov     [r14], rbx
0x180007b69  movzx   eax, word ptr [rbx]
0x180007b6c  test    ax, ax
0x180007b6f  jz      loc_180007CE5
0x180007b75  cmp     ax, 25h ; '%'
0x180007b79  jnz     loc_180007CB0
0x180007b7f  mov     rcx, rbx; lpsz
0x180007b82  call    cs:__imp_CharNextW
0x180007b88  mov     [r14], rax
0x180007b8b  movzx   ecx, word ptr [rax]
0x180007b8e  cmp     cx, 25h ; '%'
0x180007b92  jnz     short loc_180007B9C
0x180007b94  mov     rdx, rax
0x180007b97  jmp     loc_180007CB3
0x180007b9c  test    rax, rax
0x180007b9f  jz      loc_180007C48
0x180007ba5  mov     rsi, r12
0x180007ba8  jmp     short loc_180007BBC
0x180007baa  cmp     cx, 25h ; '%'
0x180007bae  jz      short loc_180007BC3
0x180007bb0  mov     rcx, rax; lpsz
0x180007bb3  call    cs:__imp_CharNextW
0x180007bb9  movzx   ecx, word ptr [rax]
0x180007bbc  test    cx, cx
0x180007bbf  jnz     short loc_180007BAA
0x180007bc1  jmp     short loc_180007BC6
0x180007bc3  mov     rsi, rax
0x180007bc6  test    rsi, rsi
0x180007bc9  jz      short loc_180007C48
0x180007bcb  mov     rax, rsi
0x180007bce  sub     rax, [r14]
0x180007bd1  sar     rax, 1
0x180007bd4  cmp     rax, 1Fh
0x180007bd8  jg      loc_180007CFD
0x180007bde  movsxd  r9, eax
0x180007be1  mov     r8, [r14]
0x180007be4  mov     edx, 20h ; ' '
0x180007be9  lea     rcx, [rbp+57h+String2]
0x180007bed  call    cs:__imp__o_wcsncpy_s
0x180007bf3  test    eax, eax
0x180007bf5  jz      short loc_180007C1B
0x180007bf7  cmp     eax, 0Ch
0x180007bfa  jz      loc_180007D59
0x180007c00  cmp     eax, 16h
0x180007c03  jz      loc_180007D4E
0x180007c09  cmp     eax, 22h ; '"'
0x180007c0c  jz      loc_180007D4E
0x180007c12  cmp     eax, 50h ; 'P'
0x180007c15  jnz     loc_180007D43
0x180007c1b  mov     rdi, [r14+8]
0x180007c1f  mov     ebx, r12d
0x180007c22  cmp     [rdi+18h], r12d
0x180007c26  jle     short loc_180007C48
0x180007c28  movsxd  rax, ebx
0x180007c2b  mov     rcx, [rdi+8]
0x180007c2f  lea     rdx, [rbp+57h+String2]; lpString2
0x180007c33  mov     rcx, [rcx+rax*8]; lpString1
0x180007c37  call    cs:__imp_lstrcmpiW
0x180007c3d  test    eax, eax
0x180007c3f  jz      short loc_180007C52
0x180007c41  inc     ebx
0x180007c43  cmp     ebx, [rdi+18h]
0x180007c46  jl      short loc_180007C28
0x180007c48  mov     ebx, 80020009h
0x180007c4d  jmp     loc_180007CEF
0x180007c52  cmp     ebx, 0FFFFFFFFh
0x180007c55  jz      short loc_180007C48
0x180007c57  test    ebx, ebx
0x180007c59  js      loc_180007D38
0x180007c5f  cmp     ebx, [rdi+18h]
0x180007c62  jge     loc_180007D38
0x180007c68  movsxd  rcx, ebx
0x180007c6b  mov     rax, [rdi+10h]
0x180007c6f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180007c73  test    rdx, rdx
0x180007c76  jz      short loc_180007C48
0x180007c78  mov     [rbp+57h+var_80], r12
0x180007c7c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007c80  inc     r8; int
0x180007c83  cmp     [rdx+r8*2], r12w
0x180007c88  jnz     short loc_180007C80
0x180007c8a  lea     rcx, [rbp+57h+var_90]; this
0x180007c8e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007c93  nop
0x180007c94  test    eax, eax
0x180007c96  jz      short loc_180007D04
0x180007c98  mov     rax, [r14]
0x180007c9b  jmp     short loc_180007CA9
0x180007c9d  mov     rcx, rax; lpsz
0x180007ca0  call    cs:__imp_CharNextW
0x180007ca6  mov     [r14], rax
0x180007ca9  cmp     rax, rsi
0x180007cac  jnz     short loc_180007C9D
0x180007cae  jmp     short loc_180007CC6
0x180007cb0  mov     rdx, rbx; unsigned __int16 *
0x180007cb3  mov     r8d, 1; int
0x180007cb9  lea     rcx, [rbp+57h+var_90]; this
0x180007cbd  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007cc2  test    eax, eax
0x180007cc4  jz      short loc_180007D04
0x180007cc6  mov     rcx, [r14]; lpsz
0x180007cc9  call    cs:__imp_CharNextW
0x180007ccf  mov     rbx, rax
0x180007cd2  mov     [r14], rax
0x180007cd5  movzx   eax, word ptr [rax]
0x180007cd8  test    ax, ax
0x180007cdb  jnz     loc_180007B75
0x180007ce1  mov     rdx, [rbp+57h+pv]
0x180007ce5  mov     ebx, r12d
0x180007ce8  mov     [rbp+57h+pv], r12
0x180007cec  mov     [r15], rdx
0x180007cef  mov     rcx, [rbp+57h+pv]; pv
0x180007cf3  call    cs:__imp_CoTaskMemFree
0x180007cf9  mov     eax, ebx
0x180007cfb  jmp     short loc_180007D10
0x180007cfd  mov     ebx, 80004005h
0x180007d02  jmp     short loc_180007CEF
0x180007d04  mov     ebx, 8007000Eh
0x180007d09  jmp     short loc_180007CEF
0x180007d0b  mov     eax, 80004003h
0x180007d10  mov     rcx, [rbp+57h+var_30]
0x180007d14  xor     rcx, rsp; StackCookie
0x180007d17  call    __security_check_cookie
0x180007d1c  lea     r11, [rsp+0B0h+var_20]
0x180007d24  mov     rbx, [r11+38h]
0x180007d28  mov     rsi, [r11+48h]
0x180007d2c  mov     rsp, r11
0x180007d2f  pop     r15
0x180007d31  pop     r14
0x180007d33  pop     r12
0x180007d35  pop     rdi
0x180007d36  pop     rbp
0x180007d37  retn
0x180007d38  mov     ecx, 0C000008Ch; unsigned int
0x180007d3d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180007d42  int     3; Trap to Debugger
0x180007d43  mov     ecx, 80004005h; int
0x180007d48  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007d4e  mov     ecx, 80070057h; int
0x180007d53  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007d59  mov     ecx, 8007000Eh; int
0x180007d5e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
