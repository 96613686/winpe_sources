# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000813c`
- end: `0x1800083f4`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000878c`

## callees

- `0x1800038f0`
- `0x180006570`
- `0x1800066a8`
- `0x18000813c`
- `0x18000a90c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000827d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000827d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800081c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800081c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008212`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008243`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008330`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008359`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008212`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008243`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008330`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008359`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800082c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800082c7`

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
0x18000813c  mov     [rsp-8+arg_8], rbx
0x180008141  mov     [rsp-8+arg_18], rsi
0x180008146  push    rbp
0x180008147  push    rdi
0x180008148  push    r12
0x18000814a  push    r14
0x18000814c  push    r15
0x18000814e  lea     rbp, [rsp-37h]
0x180008153  sub     rsp, 90h
0x18000815a  mov     rax, cs:__security_cookie
0x180008161  xor     rax, rsp
0x180008164  mov     [rbp+57h+var_30], rax
0x180008168  mov     r15, r8
0x18000816b  mov     rbx, rdx
0x18000816e  mov     r14, rcx
0x180008171  xor     r12d, r12d
0x180008174  test    rdx, rdx
0x180008177  jz      loc_18000839B
0x18000817d  test    r8, r8
0x180008180  jz      loc_18000839B
0x180008186  mov     [r8], r12
0x180008189  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000818d  inc     rax
0x180008190  cmp     [rdx+rax*2], r12w
0x180008195  jnz     short loc_18000818D
0x180008197  add     eax, eax
0x180008199  mov     ecx, 3E8h
0x18000819e  cmp     eax, 64h ; 'd'
0x1800081a1  cmovl   eax, ecx
0x1800081a4  mov     [rbp+57h+var_90], r12d
0x1800081a8  mov     [rbp+57h+var_8C], eax
0x1800081ab  mov     ecx, eax
0x1800081ad  add     rcx, rcx
0x1800081b0  mov     eax, 0FFFFFFFFh
0x1800081b5  cmp     rcx, rax
0x1800081b8  jbe     short loc_1800081C6
0x1800081ba  mov     rax, r12
0x1800081bd  mov     rdx, r12
0x1800081c0  mov     [rbp+57h+pv], rdx
0x1800081c4  jmp     short loc_1800081DE
0x1800081c6  mov     ecx, ecx; cb
0x1800081c8  call    cs:__imp_CoTaskMemAlloc
0x1800081ce  mov     rdx, rax
0x1800081d1  mov     [rbp+57h+pv], rax
0x1800081d5  test    rax, rax
0x1800081d8  jz      short loc_1800081DE
0x1800081da  mov     [rax], r12w
0x1800081de  test    rax, rax
0x1800081e1  jnz     short loc_1800081F6
0x1800081e3  mov     rcx, rax; pv
0x1800081e6  call    cs:__imp_CoTaskMemFree
0x1800081ec  mov     eax, 8007000Eh
0x1800081f1  jmp     loc_1800083A0
0x1800081f6  mov     [r14], rbx
0x1800081f9  movzx   eax, word ptr [rbx]
0x1800081fc  test    ax, ax
0x1800081ff  jz      loc_180008375
0x180008205  cmp     ax, 25h ; '%'
0x180008209  jnz     loc_180008340
0x18000820f  mov     rcx, rbx; lpsz
0x180008212  call    cs:__imp_CharNextW
0x180008218  mov     [r14], rax
0x18000821b  movzx   ecx, word ptr [rax]
0x18000821e  cmp     cx, 25h ; '%'
0x180008222  jnz     short loc_18000822C
0x180008224  mov     rdx, rax
0x180008227  jmp     loc_180008343
0x18000822c  test    rax, rax
0x18000822f  jz      loc_1800082D8
0x180008235  mov     rsi, r12
0x180008238  jmp     short loc_18000824C
0x18000823a  cmp     cx, 25h ; '%'
0x18000823e  jz      short loc_180008253
0x180008240  mov     rcx, rax; lpsz
0x180008243  call    cs:__imp_CharNextW
0x180008249  movzx   ecx, word ptr [rax]
0x18000824c  test    cx, cx
0x18000824f  jnz     short loc_18000823A
0x180008251  jmp     short loc_180008256
0x180008253  mov     rsi, rax
0x180008256  test    rsi, rsi
0x180008259  jz      short loc_1800082D8
0x18000825b  mov     rax, rsi
0x18000825e  sub     rax, [r14]
0x180008261  sar     rax, 1
0x180008264  cmp     rax, 1Fh
0x180008268  jg      loc_18000838D
0x18000826e  movsxd  r9, eax
0x180008271  mov     r8, [r14]
0x180008274  mov     edx, 20h ; ' '
0x180008279  lea     rcx, [rbp+57h+String2]
0x18000827d  call    cs:__imp__o_wcsncpy_s
0x180008283  test    eax, eax
0x180008285  jz      short loc_1800082AB
0x180008287  cmp     eax, 0Ch
0x18000828a  jz      loc_1800083E9
0x180008290  cmp     eax, 16h
0x180008293  jz      loc_1800083DE
0x180008299  cmp     eax, 22h ; '"'
0x18000829c  jz      loc_1800083DE
0x1800082a2  cmp     eax, 50h ; 'P'
0x1800082a5  jnz     loc_1800083D3
0x1800082ab  mov     rdi, [r14+8]
0x1800082af  mov     ebx, r12d
0x1800082b2  cmp     [rdi+18h], r12d
0x1800082b6  jle     short loc_1800082D8
0x1800082b8  movsxd  rax, ebx
0x1800082bb  mov     rcx, [rdi+8]
0x1800082bf  lea     rdx, [rbp+57h+String2]; lpString2
0x1800082c3  mov     rcx, [rcx+rax*8]; lpString1
0x1800082c7  call    cs:__imp_lstrcmpiW
0x1800082cd  test    eax, eax
0x1800082cf  jz      short loc_1800082E2
0x1800082d1  inc     ebx
0x1800082d3  cmp     ebx, [rdi+18h]
0x1800082d6  jl      short loc_1800082B8
0x1800082d8  mov     ebx, 80020009h
0x1800082dd  jmp     loc_18000837F
0x1800082e2  cmp     ebx, 0FFFFFFFFh
0x1800082e5  jz      short loc_1800082D8
0x1800082e7  test    ebx, ebx
0x1800082e9  js      loc_1800083C8
0x1800082ef  cmp     ebx, [rdi+18h]
0x1800082f2  jge     loc_1800083C8
0x1800082f8  movsxd  rcx, ebx
0x1800082fb  mov     rax, [rdi+10h]
0x1800082ff  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180008303  test    rdx, rdx
0x180008306  jz      short loc_1800082D8
0x180008308  mov     [rbp+57h+var_80], r12
0x18000830c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008310  inc     r8; int
0x180008313  cmp     [rdx+r8*2], r12w
0x180008318  jnz     short loc_180008310
0x18000831a  lea     rcx, [rbp+57h+var_90]; this
0x18000831e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008323  nop
0x180008324  test    eax, eax
0x180008326  jz      short loc_180008394
0x180008328  mov     rax, [r14]
0x18000832b  jmp     short loc_180008339
0x18000832d  mov     rcx, rax; lpsz
0x180008330  call    cs:__imp_CharNextW
0x180008336  mov     [r14], rax
0x180008339  cmp     rax, rsi
0x18000833c  jnz     short loc_18000832D
0x18000833e  jmp     short loc_180008356
0x180008340  mov     rdx, rbx; unsigned __int16 *
0x180008343  mov     r8d, 1; int
0x180008349  lea     rcx, [rbp+57h+var_90]; this
0x18000834d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008352  test    eax, eax
0x180008354  jz      short loc_180008394
0x180008356  mov     rcx, [r14]; lpsz
0x180008359  call    cs:__imp_CharNextW
0x18000835f  mov     rbx, rax
0x180008362  mov     [r14], rax
0x180008365  movzx   eax, word ptr [rax]
0x180008368  test    ax, ax
0x18000836b  jnz     loc_180008205
0x180008371  mov     rdx, [rbp+57h+pv]
0x180008375  mov     ebx, r12d
0x180008378  mov     [rbp+57h+pv], r12
0x18000837c  mov     [r15], rdx
0x18000837f  mov     rcx, [rbp+57h+pv]; pv
0x180008383  call    cs:__imp_CoTaskMemFree
0x180008389  mov     eax, ebx
0x18000838b  jmp     short loc_1800083A0
0x18000838d  mov     ebx, 80004005h
0x180008392  jmp     short loc_18000837F
0x180008394  mov     ebx, 8007000Eh
0x180008399  jmp     short loc_18000837F
0x18000839b  mov     eax, 80004003h
0x1800083a0  mov     rcx, [rbp+57h+var_30]
0x1800083a4  xor     rcx, rsp; StackCookie
0x1800083a7  call    __security_check_cookie
0x1800083ac  lea     r11, [rsp+0B0h+var_20]
0x1800083b4  mov     rbx, [r11+38h]
0x1800083b8  mov     rsi, [r11+48h]
0x1800083bc  mov     rsp, r11
0x1800083bf  pop     r15
0x1800083c1  pop     r14
0x1800083c3  pop     r12
0x1800083c5  pop     rdi
0x1800083c6  pop     rbp
0x1800083c7  retn
0x1800083c8  mov     ecx, 0C000008Ch; unsigned int
0x1800083cd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800083d2  int     3; Trap to Debugger
0x1800083d3  mov     ecx, 80004005h; int
0x1800083d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800083de  mov     ecx, 80070057h; int
0x1800083e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800083e9  mov     ecx, 8007000Eh; int
0x1800083ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
