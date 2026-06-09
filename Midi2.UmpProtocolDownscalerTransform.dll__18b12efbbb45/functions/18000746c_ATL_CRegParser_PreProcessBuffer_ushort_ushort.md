# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000746c`
- end: `0x180007724`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007a7c`

## callees

- `0x180002e70`
- `0x1800058a0`
- `0x1800059d8`
- `0x18000746c`
- `0x180009aac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800075ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800075ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800074f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800074f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007542`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007573`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007660`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007689`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007542`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007573`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007660`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007689`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800075f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800075f7`

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
0x18000746c  mov     [rsp-8+arg_8], rbx
0x180007471  mov     [rsp-8+arg_18], rsi
0x180007476  push    rbp
0x180007477  push    rdi
0x180007478  push    r12
0x18000747a  push    r14
0x18000747c  push    r15
0x18000747e  lea     rbp, [rsp-37h]
0x180007483  sub     rsp, 90h
0x18000748a  mov     rax, cs:__security_cookie
0x180007491  xor     rax, rsp
0x180007494  mov     [rbp+57h+var_30], rax
0x180007498  mov     r15, r8
0x18000749b  mov     rbx, rdx
0x18000749e  mov     r14, rcx
0x1800074a1  xor     r12d, r12d
0x1800074a4  test    rdx, rdx
0x1800074a7  jz      loc_1800076CB
0x1800074ad  test    r8, r8
0x1800074b0  jz      loc_1800076CB
0x1800074b6  mov     [r8], r12
0x1800074b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800074bd  inc     rax
0x1800074c0  cmp     [rdx+rax*2], r12w
0x1800074c5  jnz     short loc_1800074BD
0x1800074c7  add     eax, eax
0x1800074c9  mov     ecx, 3E8h
0x1800074ce  cmp     eax, 64h ; 'd'
0x1800074d1  cmovl   eax, ecx
0x1800074d4  mov     [rbp+57h+var_90], r12d
0x1800074d8  mov     [rbp+57h+var_8C], eax
0x1800074db  mov     ecx, eax
0x1800074dd  add     rcx, rcx
0x1800074e0  mov     eax, 0FFFFFFFFh
0x1800074e5  cmp     rcx, rax
0x1800074e8  jbe     short loc_1800074F6
0x1800074ea  mov     rax, r12
0x1800074ed  mov     rdx, r12
0x1800074f0  mov     [rbp+57h+pv], rdx
0x1800074f4  jmp     short loc_18000750E
0x1800074f6  mov     ecx, ecx; cb
0x1800074f8  call    cs:__imp_CoTaskMemAlloc
0x1800074fe  mov     rdx, rax
0x180007501  mov     [rbp+57h+pv], rax
0x180007505  test    rax, rax
0x180007508  jz      short loc_18000750E
0x18000750a  mov     [rax], r12w
0x18000750e  test    rax, rax
0x180007511  jnz     short loc_180007526
0x180007513  mov     rcx, rax; pv
0x180007516  call    cs:__imp_CoTaskMemFree
0x18000751c  mov     eax, 8007000Eh
0x180007521  jmp     loc_1800076D0
0x180007526  mov     [r14], rbx
0x180007529  movzx   eax, word ptr [rbx]
0x18000752c  test    ax, ax
0x18000752f  jz      loc_1800076A5
0x180007535  cmp     ax, 25h ; '%'
0x180007539  jnz     loc_180007670
0x18000753f  mov     rcx, rbx; lpsz
0x180007542  call    cs:__imp_CharNextW
0x180007548  mov     [r14], rax
0x18000754b  movzx   ecx, word ptr [rax]
0x18000754e  cmp     cx, 25h ; '%'
0x180007552  jnz     short loc_18000755C
0x180007554  mov     rdx, rax
0x180007557  jmp     loc_180007673
0x18000755c  test    rax, rax
0x18000755f  jz      loc_180007608
0x180007565  mov     rsi, r12
0x180007568  jmp     short loc_18000757C
0x18000756a  cmp     cx, 25h ; '%'
0x18000756e  jz      short loc_180007583
0x180007570  mov     rcx, rax; lpsz
0x180007573  call    cs:__imp_CharNextW
0x180007579  movzx   ecx, word ptr [rax]
0x18000757c  test    cx, cx
0x18000757f  jnz     short loc_18000756A
0x180007581  jmp     short loc_180007586
0x180007583  mov     rsi, rax
0x180007586  test    rsi, rsi
0x180007589  jz      short loc_180007608
0x18000758b  mov     rax, rsi
0x18000758e  sub     rax, [r14]
0x180007591  sar     rax, 1
0x180007594  cmp     rax, 1Fh
0x180007598  jg      loc_1800076BD
0x18000759e  movsxd  r9, eax
0x1800075a1  mov     r8, [r14]
0x1800075a4  mov     edx, 20h ; ' '
0x1800075a9  lea     rcx, [rbp+57h+String2]
0x1800075ad  call    cs:__imp__o_wcsncpy_s
0x1800075b3  test    eax, eax
0x1800075b5  jz      short loc_1800075DB
0x1800075b7  cmp     eax, 0Ch
0x1800075ba  jz      loc_180007719
0x1800075c0  cmp     eax, 16h
0x1800075c3  jz      loc_18000770E
0x1800075c9  cmp     eax, 22h ; '"'
0x1800075cc  jz      loc_18000770E
0x1800075d2  cmp     eax, 50h ; 'P'
0x1800075d5  jnz     loc_180007703
0x1800075db  mov     rdi, [r14+8]
0x1800075df  mov     ebx, r12d
0x1800075e2  cmp     [rdi+18h], r12d
0x1800075e6  jle     short loc_180007608
0x1800075e8  movsxd  rax, ebx
0x1800075eb  mov     rcx, [rdi+8]
0x1800075ef  lea     rdx, [rbp+57h+String2]; lpString2
0x1800075f3  mov     rcx, [rcx+rax*8]; lpString1
0x1800075f7  call    cs:__imp_lstrcmpiW
0x1800075fd  test    eax, eax
0x1800075ff  jz      short loc_180007612
0x180007601  inc     ebx
0x180007603  cmp     ebx, [rdi+18h]
0x180007606  jl      short loc_1800075E8
0x180007608  mov     ebx, 80020009h
0x18000760d  jmp     loc_1800076AF
0x180007612  cmp     ebx, 0FFFFFFFFh
0x180007615  jz      short loc_180007608
0x180007617  test    ebx, ebx
0x180007619  js      loc_1800076F8
0x18000761f  cmp     ebx, [rdi+18h]
0x180007622  jge     loc_1800076F8
0x180007628  movsxd  rcx, ebx
0x18000762b  mov     rax, [rdi+10h]
0x18000762f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180007633  test    rdx, rdx
0x180007636  jz      short loc_180007608
0x180007638  mov     [rbp+57h+var_80], r12
0x18000763c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007640  inc     r8; int
0x180007643  cmp     [rdx+r8*2], r12w
0x180007648  jnz     short loc_180007640
0x18000764a  lea     rcx, [rbp+57h+var_90]; this
0x18000764e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007653  nop
0x180007654  test    eax, eax
0x180007656  jz      short loc_1800076C4
0x180007658  mov     rax, [r14]
0x18000765b  jmp     short loc_180007669
0x18000765d  mov     rcx, rax; lpsz
0x180007660  call    cs:__imp_CharNextW
0x180007666  mov     [r14], rax
0x180007669  cmp     rax, rsi
0x18000766c  jnz     short loc_18000765D
0x18000766e  jmp     short loc_180007686
0x180007670  mov     rdx, rbx; unsigned __int16 *
0x180007673  mov     r8d, 1; int
0x180007679  lea     rcx, [rbp+57h+var_90]; this
0x18000767d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007682  test    eax, eax
0x180007684  jz      short loc_1800076C4
0x180007686  mov     rcx, [r14]; lpsz
0x180007689  call    cs:__imp_CharNextW
0x18000768f  mov     rbx, rax
0x180007692  mov     [r14], rax
0x180007695  movzx   eax, word ptr [rax]
0x180007698  test    ax, ax
0x18000769b  jnz     loc_180007535
0x1800076a1  mov     rdx, [rbp+57h+pv]
0x1800076a5  mov     ebx, r12d
0x1800076a8  mov     [rbp+57h+pv], r12
0x1800076ac  mov     [r15], rdx
0x1800076af  mov     rcx, [rbp+57h+pv]; pv
0x1800076b3  call    cs:__imp_CoTaskMemFree
0x1800076b9  mov     eax, ebx
0x1800076bb  jmp     short loc_1800076D0
0x1800076bd  mov     ebx, 80004005h
0x1800076c2  jmp     short loc_1800076AF
0x1800076c4  mov     ebx, 8007000Eh
0x1800076c9  jmp     short loc_1800076AF
0x1800076cb  mov     eax, 80004003h
0x1800076d0  mov     rcx, [rbp+57h+var_30]
0x1800076d4  xor     rcx, rsp; StackCookie
0x1800076d7  call    __security_check_cookie
0x1800076dc  lea     r11, [rsp+0B0h+var_20]
0x1800076e4  mov     rbx, [r11+38h]
0x1800076e8  mov     rsi, [r11+48h]
0x1800076ec  mov     rsp, r11
0x1800076ef  pop     r15
0x1800076f1  pop     r14
0x1800076f3  pop     r12
0x1800076f5  pop     rdi
0x1800076f6  pop     rbp
0x1800076f7  retn
0x1800076f8  mov     ecx, 0C000008Ch; unsigned int
0x1800076fd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180007702  int     3; Trap to Debugger
0x180007703  mov     ecx, 80004005h; int
0x180007708  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000770e  mov     ecx, 80070057h; int
0x180007713  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007719  mov     ecx, 8007000Eh; int
0x18000771e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
