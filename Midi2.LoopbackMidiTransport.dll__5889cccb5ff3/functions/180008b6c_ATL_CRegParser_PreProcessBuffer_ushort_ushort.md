# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180008b6c`
- end: `0x180008e24`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000917c`

## callees

- `0x180004180`
- `0x180006f80`
- `0x1800070b8`
- `0x180008b6c`
- `0x18000b1ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180008cad`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180008cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008db3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008c42`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008c73`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008d60`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008d89`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008c42`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008c73`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008d60`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008d89`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008cf7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008cf7`

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
0x180008b6c  mov     [rsp-8+arg_8], rbx
0x180008b71  mov     [rsp-8+arg_18], rsi
0x180008b76  push    rbp
0x180008b77  push    rdi
0x180008b78  push    r12
0x180008b7a  push    r14
0x180008b7c  push    r15
0x180008b7e  lea     rbp, [rsp-37h]
0x180008b83  sub     rsp, 90h
0x180008b8a  mov     rax, cs:__security_cookie
0x180008b91  xor     rax, rsp
0x180008b94  mov     [rbp+57h+var_30], rax
0x180008b98  mov     r15, r8
0x180008b9b  mov     rbx, rdx
0x180008b9e  mov     r14, rcx
0x180008ba1  xor     r12d, r12d
0x180008ba4  test    rdx, rdx
0x180008ba7  jz      loc_180008DCB
0x180008bad  test    r8, r8
0x180008bb0  jz      loc_180008DCB
0x180008bb6  mov     [r8], r12
0x180008bb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008bbd  inc     rax
0x180008bc0  cmp     [rdx+rax*2], r12w
0x180008bc5  jnz     short loc_180008BBD
0x180008bc7  add     eax, eax
0x180008bc9  mov     ecx, 3E8h
0x180008bce  cmp     eax, 64h ; 'd'
0x180008bd1  cmovl   eax, ecx
0x180008bd4  mov     [rbp+57h+var_90], r12d
0x180008bd8  mov     [rbp+57h+var_8C], eax
0x180008bdb  mov     ecx, eax
0x180008bdd  add     rcx, rcx
0x180008be0  mov     eax, 0FFFFFFFFh
0x180008be5  cmp     rcx, rax
0x180008be8  jbe     short loc_180008BF6
0x180008bea  mov     rax, r12
0x180008bed  mov     rdx, r12
0x180008bf0  mov     [rbp+57h+pv], rdx
0x180008bf4  jmp     short loc_180008C0E
0x180008bf6  mov     ecx, ecx; cb
0x180008bf8  call    cs:__imp_CoTaskMemAlloc
0x180008bfe  mov     rdx, rax
0x180008c01  mov     [rbp+57h+pv], rax
0x180008c05  test    rax, rax
0x180008c08  jz      short loc_180008C0E
0x180008c0a  mov     [rax], r12w
0x180008c0e  test    rax, rax
0x180008c11  jnz     short loc_180008C26
0x180008c13  mov     rcx, rax; pv
0x180008c16  call    cs:__imp_CoTaskMemFree
0x180008c1c  mov     eax, 8007000Eh
0x180008c21  jmp     loc_180008DD0
0x180008c26  mov     [r14], rbx
0x180008c29  movzx   eax, word ptr [rbx]
0x180008c2c  test    ax, ax
0x180008c2f  jz      loc_180008DA5
0x180008c35  cmp     ax, 25h ; '%'
0x180008c39  jnz     loc_180008D70
0x180008c3f  mov     rcx, rbx; lpsz
0x180008c42  call    cs:__imp_CharNextW
0x180008c48  mov     [r14], rax
0x180008c4b  movzx   ecx, word ptr [rax]
0x180008c4e  cmp     cx, 25h ; '%'
0x180008c52  jnz     short loc_180008C5C
0x180008c54  mov     rdx, rax
0x180008c57  jmp     loc_180008D73
0x180008c5c  test    rax, rax
0x180008c5f  jz      loc_180008D08
0x180008c65  mov     rsi, r12
0x180008c68  jmp     short loc_180008C7C
0x180008c6a  cmp     cx, 25h ; '%'
0x180008c6e  jz      short loc_180008C83
0x180008c70  mov     rcx, rax; lpsz
0x180008c73  call    cs:__imp_CharNextW
0x180008c79  movzx   ecx, word ptr [rax]
0x180008c7c  test    cx, cx
0x180008c7f  jnz     short loc_180008C6A
0x180008c81  jmp     short loc_180008C86
0x180008c83  mov     rsi, rax
0x180008c86  test    rsi, rsi
0x180008c89  jz      short loc_180008D08
0x180008c8b  mov     rax, rsi
0x180008c8e  sub     rax, [r14]
0x180008c91  sar     rax, 1
0x180008c94  cmp     rax, 1Fh
0x180008c98  jg      loc_180008DBD
0x180008c9e  movsxd  r9, eax
0x180008ca1  mov     r8, [r14]
0x180008ca4  mov     edx, 20h ; ' '
0x180008ca9  lea     rcx, [rbp+57h+String2]
0x180008cad  call    cs:__imp__o_wcsncpy_s
0x180008cb3  test    eax, eax
0x180008cb5  jz      short loc_180008CDB
0x180008cb7  cmp     eax, 0Ch
0x180008cba  jz      loc_180008E19
0x180008cc0  cmp     eax, 16h
0x180008cc3  jz      loc_180008E0E
0x180008cc9  cmp     eax, 22h ; '"'
0x180008ccc  jz      loc_180008E0E
0x180008cd2  cmp     eax, 50h ; 'P'
0x180008cd5  jnz     loc_180008E03
0x180008cdb  mov     rdi, [r14+8]
0x180008cdf  mov     ebx, r12d
0x180008ce2  cmp     [rdi+18h], r12d
0x180008ce6  jle     short loc_180008D08
0x180008ce8  movsxd  rax, ebx
0x180008ceb  mov     rcx, [rdi+8]
0x180008cef  lea     rdx, [rbp+57h+String2]; lpString2
0x180008cf3  mov     rcx, [rcx+rax*8]; lpString1
0x180008cf7  call    cs:__imp_lstrcmpiW
0x180008cfd  test    eax, eax
0x180008cff  jz      short loc_180008D12
0x180008d01  inc     ebx
0x180008d03  cmp     ebx, [rdi+18h]
0x180008d06  jl      short loc_180008CE8
0x180008d08  mov     ebx, 80020009h
0x180008d0d  jmp     loc_180008DAF
0x180008d12  cmp     ebx, 0FFFFFFFFh
0x180008d15  jz      short loc_180008D08
0x180008d17  test    ebx, ebx
0x180008d19  js      loc_180008DF8
0x180008d1f  cmp     ebx, [rdi+18h]
0x180008d22  jge     loc_180008DF8
0x180008d28  movsxd  rcx, ebx
0x180008d2b  mov     rax, [rdi+10h]
0x180008d2f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180008d33  test    rdx, rdx
0x180008d36  jz      short loc_180008D08
0x180008d38  mov     [rbp+57h+var_80], r12
0x180008d3c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008d40  inc     r8; int
0x180008d43  cmp     [rdx+r8*2], r12w
0x180008d48  jnz     short loc_180008D40
0x180008d4a  lea     rcx, [rbp+57h+var_90]; this
0x180008d4e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008d53  nop
0x180008d54  test    eax, eax
0x180008d56  jz      short loc_180008DC4
0x180008d58  mov     rax, [r14]
0x180008d5b  jmp     short loc_180008D69
0x180008d5d  mov     rcx, rax; lpsz
0x180008d60  call    cs:__imp_CharNextW
0x180008d66  mov     [r14], rax
0x180008d69  cmp     rax, rsi
0x180008d6c  jnz     short loc_180008D5D
0x180008d6e  jmp     short loc_180008D86
0x180008d70  mov     rdx, rbx; unsigned __int16 *
0x180008d73  mov     r8d, 1; int
0x180008d79  lea     rcx, [rbp+57h+var_90]; this
0x180008d7d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008d82  test    eax, eax
0x180008d84  jz      short loc_180008DC4
0x180008d86  mov     rcx, [r14]; lpsz
0x180008d89  call    cs:__imp_CharNextW
0x180008d8f  mov     rbx, rax
0x180008d92  mov     [r14], rax
0x180008d95  movzx   eax, word ptr [rax]
0x180008d98  test    ax, ax
0x180008d9b  jnz     loc_180008C35
0x180008da1  mov     rdx, [rbp+57h+pv]
0x180008da5  mov     ebx, r12d
0x180008da8  mov     [rbp+57h+pv], r12
0x180008dac  mov     [r15], rdx
0x180008daf  mov     rcx, [rbp+57h+pv]; pv
0x180008db3  call    cs:__imp_CoTaskMemFree
0x180008db9  mov     eax, ebx
0x180008dbb  jmp     short loc_180008DD0
0x180008dbd  mov     ebx, 80004005h
0x180008dc2  jmp     short loc_180008DAF
0x180008dc4  mov     ebx, 8007000Eh
0x180008dc9  jmp     short loc_180008DAF
0x180008dcb  mov     eax, 80004003h
0x180008dd0  mov     rcx, [rbp+57h+var_30]
0x180008dd4  xor     rcx, rsp; StackCookie
0x180008dd7  call    __security_check_cookie
0x180008ddc  lea     r11, [rsp+0B0h+var_20]
0x180008de4  mov     rbx, [r11+38h]
0x180008de8  mov     rsi, [r11+48h]
0x180008dec  mov     rsp, r11
0x180008def  pop     r15
0x180008df1  pop     r14
0x180008df3  pop     r12
0x180008df5  pop     rdi
0x180008df6  pop     rbp
0x180008df7  retn
0x180008df8  mov     ecx, 0C000008Ch; unsigned int
0x180008dfd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180008e02  int     3; Trap to Debugger
0x180008e03  mov     ecx, 80004005h; int
0x180008e08  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008e0e  mov     ecx, 80070057h; int
0x180008e13  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008e19  mov     ecx, 8007000Eh; int
0x180008e1e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
