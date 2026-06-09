# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180009c28`
- end: `0x180009ee0`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a4d4`

## callees

- `0x180005020`
- `0x180007f80`
- `0x1800080b8`
- `0x180009c28`
- `0x18000c65c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180009d69`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180009d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e6f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009cfe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d2f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e1c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009cfe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009d2f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e1c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009e45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009db3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009db3`

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
0x180009c28  mov     [rsp-8+arg_8], rbx
0x180009c2d  mov     [rsp-8+arg_18], rsi
0x180009c32  push    rbp
0x180009c33  push    rdi
0x180009c34  push    r12
0x180009c36  push    r14
0x180009c38  push    r15
0x180009c3a  lea     rbp, [rsp-37h]
0x180009c3f  sub     rsp, 90h
0x180009c46  mov     rax, cs:__security_cookie
0x180009c4d  xor     rax, rsp
0x180009c50  mov     [rbp+57h+var_30], rax
0x180009c54  mov     r15, r8
0x180009c57  mov     rbx, rdx
0x180009c5a  mov     r14, rcx
0x180009c5d  xor     r12d, r12d
0x180009c60  test    rdx, rdx
0x180009c63  jz      loc_180009E87
0x180009c69  test    r8, r8
0x180009c6c  jz      loc_180009E87
0x180009c72  mov     [r8], r12
0x180009c75  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c79  inc     rax
0x180009c7c  cmp     [rdx+rax*2], r12w
0x180009c81  jnz     short loc_180009C79
0x180009c83  add     eax, eax
0x180009c85  mov     ecx, 3E8h
0x180009c8a  cmp     eax, 64h ; 'd'
0x180009c8d  cmovl   eax, ecx
0x180009c90  mov     [rbp+57h+var_90], r12d
0x180009c94  mov     [rbp+57h+var_8C], eax
0x180009c97  mov     ecx, eax
0x180009c99  add     rcx, rcx
0x180009c9c  mov     eax, 0FFFFFFFFh
0x180009ca1  cmp     rcx, rax
0x180009ca4  jbe     short loc_180009CB2
0x180009ca6  mov     rax, r12
0x180009ca9  mov     rdx, r12
0x180009cac  mov     [rbp+57h+pv], rdx
0x180009cb0  jmp     short loc_180009CCA
0x180009cb2  mov     ecx, ecx; cb
0x180009cb4  call    cs:__imp_CoTaskMemAlloc
0x180009cba  mov     rdx, rax
0x180009cbd  mov     [rbp+57h+pv], rax
0x180009cc1  test    rax, rax
0x180009cc4  jz      short loc_180009CCA
0x180009cc6  mov     [rax], r12w
0x180009cca  test    rax, rax
0x180009ccd  jnz     short loc_180009CE2
0x180009ccf  mov     rcx, rax; pv
0x180009cd2  call    cs:__imp_CoTaskMemFree
0x180009cd8  mov     eax, 8007000Eh
0x180009cdd  jmp     loc_180009E8C
0x180009ce2  mov     [r14], rbx
0x180009ce5  movzx   eax, word ptr [rbx]
0x180009ce8  test    ax, ax
0x180009ceb  jz      loc_180009E61
0x180009cf1  cmp     ax, 25h ; '%'
0x180009cf5  jnz     loc_180009E2C
0x180009cfb  mov     rcx, rbx; lpsz
0x180009cfe  call    cs:__imp_CharNextW
0x180009d04  mov     [r14], rax
0x180009d07  movzx   ecx, word ptr [rax]
0x180009d0a  cmp     cx, 25h ; '%'
0x180009d0e  jnz     short loc_180009D18
0x180009d10  mov     rdx, rax
0x180009d13  jmp     loc_180009E2F
0x180009d18  test    rax, rax
0x180009d1b  jz      loc_180009DC4
0x180009d21  mov     rsi, r12
0x180009d24  jmp     short loc_180009D38
0x180009d26  cmp     cx, 25h ; '%'
0x180009d2a  jz      short loc_180009D3F
0x180009d2c  mov     rcx, rax; lpsz
0x180009d2f  call    cs:__imp_CharNextW
0x180009d35  movzx   ecx, word ptr [rax]
0x180009d38  test    cx, cx
0x180009d3b  jnz     short loc_180009D26
0x180009d3d  jmp     short loc_180009D42
0x180009d3f  mov     rsi, rax
0x180009d42  test    rsi, rsi
0x180009d45  jz      short loc_180009DC4
0x180009d47  mov     rax, rsi
0x180009d4a  sub     rax, [r14]
0x180009d4d  sar     rax, 1
0x180009d50  cmp     rax, 1Fh
0x180009d54  jg      loc_180009E79
0x180009d5a  movsxd  r9, eax
0x180009d5d  mov     r8, [r14]
0x180009d60  mov     edx, 20h ; ' '
0x180009d65  lea     rcx, [rbp+57h+String2]
0x180009d69  call    cs:__imp__o_wcsncpy_s
0x180009d6f  test    eax, eax
0x180009d71  jz      short loc_180009D97
0x180009d73  cmp     eax, 0Ch
0x180009d76  jz      loc_180009ED5
0x180009d7c  cmp     eax, 16h
0x180009d7f  jz      loc_180009ECA
0x180009d85  cmp     eax, 22h ; '"'
0x180009d88  jz      loc_180009ECA
0x180009d8e  cmp     eax, 50h ; 'P'
0x180009d91  jnz     loc_180009EBF
0x180009d97  mov     rdi, [r14+8]
0x180009d9b  mov     ebx, r12d
0x180009d9e  cmp     [rdi+18h], r12d
0x180009da2  jle     short loc_180009DC4
0x180009da4  movsxd  rax, ebx
0x180009da7  mov     rcx, [rdi+8]
0x180009dab  lea     rdx, [rbp+57h+String2]; lpString2
0x180009daf  mov     rcx, [rcx+rax*8]; lpString1
0x180009db3  call    cs:__imp_lstrcmpiW
0x180009db9  test    eax, eax
0x180009dbb  jz      short loc_180009DCE
0x180009dbd  inc     ebx
0x180009dbf  cmp     ebx, [rdi+18h]
0x180009dc2  jl      short loc_180009DA4
0x180009dc4  mov     ebx, 80020009h
0x180009dc9  jmp     loc_180009E6B
0x180009dce  cmp     ebx, 0FFFFFFFFh
0x180009dd1  jz      short loc_180009DC4
0x180009dd3  test    ebx, ebx
0x180009dd5  js      loc_180009EB4
0x180009ddb  cmp     ebx, [rdi+18h]
0x180009dde  jge     loc_180009EB4
0x180009de4  movsxd  rcx, ebx
0x180009de7  mov     rax, [rdi+10h]
0x180009deb  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180009def  test    rdx, rdx
0x180009df2  jz      short loc_180009DC4
0x180009df4  mov     [rbp+57h+var_80], r12
0x180009df8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009dfc  inc     r8; int
0x180009dff  cmp     [rdx+r8*2], r12w
0x180009e04  jnz     short loc_180009DFC
0x180009e06  lea     rcx, [rbp+57h+var_90]; this
0x180009e0a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009e0f  nop
0x180009e10  test    eax, eax
0x180009e12  jz      short loc_180009E80
0x180009e14  mov     rax, [r14]
0x180009e17  jmp     short loc_180009E25
0x180009e19  mov     rcx, rax; lpsz
0x180009e1c  call    cs:__imp_CharNextW
0x180009e22  mov     [r14], rax
0x180009e25  cmp     rax, rsi
0x180009e28  jnz     short loc_180009E19
0x180009e2a  jmp     short loc_180009E42
0x180009e2c  mov     rdx, rbx; unsigned __int16 *
0x180009e2f  mov     r8d, 1; int
0x180009e35  lea     rcx, [rbp+57h+var_90]; this
0x180009e39  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180009e3e  test    eax, eax
0x180009e40  jz      short loc_180009E80
0x180009e42  mov     rcx, [r14]; lpsz
0x180009e45  call    cs:__imp_CharNextW
0x180009e4b  mov     rbx, rax
0x180009e4e  mov     [r14], rax
0x180009e51  movzx   eax, word ptr [rax]
0x180009e54  test    ax, ax
0x180009e57  jnz     loc_180009CF1
0x180009e5d  mov     rdx, [rbp+57h+pv]
0x180009e61  mov     ebx, r12d
0x180009e64  mov     [rbp+57h+pv], r12
0x180009e68  mov     [r15], rdx
0x180009e6b  mov     rcx, [rbp+57h+pv]; pv
0x180009e6f  call    cs:__imp_CoTaskMemFree
0x180009e75  mov     eax, ebx
0x180009e77  jmp     short loc_180009E8C
0x180009e79  mov     ebx, 80004005h
0x180009e7e  jmp     short loc_180009E6B
0x180009e80  mov     ebx, 8007000Eh
0x180009e85  jmp     short loc_180009E6B
0x180009e87  mov     eax, 80004003h
0x180009e8c  mov     rcx, [rbp+57h+var_30]
0x180009e90  xor     rcx, rsp; StackCookie
0x180009e93  call    __security_check_cookie
0x180009e98  lea     r11, [rsp+0B0h+var_20]
0x180009ea0  mov     rbx, [r11+38h]
0x180009ea4  mov     rsi, [r11+48h]
0x180009ea8  mov     rsp, r11
0x180009eab  pop     r15
0x180009ead  pop     r14
0x180009eaf  pop     r12
0x180009eb1  pop     rdi
0x180009eb2  pop     rbp
0x180009eb3  retn
0x180009eb4  mov     ecx, 0C000008Ch; unsigned int
0x180009eb9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180009ebe  int     3; Trap to Debugger
0x180009ebf  mov     ecx, 80004005h; int
0x180009ec4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009eca  mov     ecx, 80070057h; int
0x180009ecf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009ed5  mov     ecx, 8007000Eh; int
0x180009eda  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
