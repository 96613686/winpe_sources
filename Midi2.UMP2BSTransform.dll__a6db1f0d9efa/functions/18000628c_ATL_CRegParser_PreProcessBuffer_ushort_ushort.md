# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000628c`
- end: `0x180006544`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000689c`

## callees

- `0x180001ef0`
- `0x1800046c0`
- `0x1800047f8`
- `0x18000628c`
- `0x1800088cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800063cd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800063cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064d3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006362`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006393`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006480`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800064a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006362`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006393`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006480`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800064a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006417`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006417`

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
0x18000628c  mov     [rsp-8+arg_8], rbx
0x180006291  mov     [rsp-8+arg_18], rsi
0x180006296  push    rbp
0x180006297  push    rdi
0x180006298  push    r12
0x18000629a  push    r14
0x18000629c  push    r15
0x18000629e  lea     rbp, [rsp-37h]
0x1800062a3  sub     rsp, 90h
0x1800062aa  mov     rax, cs:__security_cookie
0x1800062b1  xor     rax, rsp
0x1800062b4  mov     [rbp+57h+var_30], rax
0x1800062b8  mov     r15, r8
0x1800062bb  mov     rbx, rdx
0x1800062be  mov     r14, rcx
0x1800062c1  xor     r12d, r12d
0x1800062c4  test    rdx, rdx
0x1800062c7  jz      loc_1800064EB
0x1800062cd  test    r8, r8
0x1800062d0  jz      loc_1800064EB
0x1800062d6  mov     [r8], r12
0x1800062d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800062dd  inc     rax
0x1800062e0  cmp     [rdx+rax*2], r12w
0x1800062e5  jnz     short loc_1800062DD
0x1800062e7  add     eax, eax
0x1800062e9  mov     ecx, 3E8h
0x1800062ee  cmp     eax, 64h ; 'd'
0x1800062f1  cmovl   eax, ecx
0x1800062f4  mov     [rbp+57h+var_90], r12d
0x1800062f8  mov     [rbp+57h+var_8C], eax
0x1800062fb  mov     ecx, eax
0x1800062fd  add     rcx, rcx
0x180006300  mov     eax, 0FFFFFFFFh
0x180006305  cmp     rcx, rax
0x180006308  jbe     short loc_180006316
0x18000630a  mov     rax, r12
0x18000630d  mov     rdx, r12
0x180006310  mov     [rbp+57h+pv], rdx
0x180006314  jmp     short loc_18000632E
0x180006316  mov     ecx, ecx; cb
0x180006318  call    cs:__imp_CoTaskMemAlloc
0x18000631e  mov     rdx, rax
0x180006321  mov     [rbp+57h+pv], rax
0x180006325  test    rax, rax
0x180006328  jz      short loc_18000632E
0x18000632a  mov     [rax], r12w
0x18000632e  test    rax, rax
0x180006331  jnz     short loc_180006346
0x180006333  mov     rcx, rax; pv
0x180006336  call    cs:__imp_CoTaskMemFree
0x18000633c  mov     eax, 8007000Eh
0x180006341  jmp     loc_1800064F0
0x180006346  mov     [r14], rbx
0x180006349  movzx   eax, word ptr [rbx]
0x18000634c  test    ax, ax
0x18000634f  jz      loc_1800064C5
0x180006355  cmp     ax, 25h ; '%'
0x180006359  jnz     loc_180006490
0x18000635f  mov     rcx, rbx; lpsz
0x180006362  call    cs:__imp_CharNextW
0x180006368  mov     [r14], rax
0x18000636b  movzx   ecx, word ptr [rax]
0x18000636e  cmp     cx, 25h ; '%'
0x180006372  jnz     short loc_18000637C
0x180006374  mov     rdx, rax
0x180006377  jmp     loc_180006493
0x18000637c  test    rax, rax
0x18000637f  jz      loc_180006428
0x180006385  mov     rsi, r12
0x180006388  jmp     short loc_18000639C
0x18000638a  cmp     cx, 25h ; '%'
0x18000638e  jz      short loc_1800063A3
0x180006390  mov     rcx, rax; lpsz
0x180006393  call    cs:__imp_CharNextW
0x180006399  movzx   ecx, word ptr [rax]
0x18000639c  test    cx, cx
0x18000639f  jnz     short loc_18000638A
0x1800063a1  jmp     short loc_1800063A6
0x1800063a3  mov     rsi, rax
0x1800063a6  test    rsi, rsi
0x1800063a9  jz      short loc_180006428
0x1800063ab  mov     rax, rsi
0x1800063ae  sub     rax, [r14]
0x1800063b1  sar     rax, 1
0x1800063b4  cmp     rax, 1Fh
0x1800063b8  jg      loc_1800064DD
0x1800063be  movsxd  r9, eax
0x1800063c1  mov     r8, [r14]
0x1800063c4  mov     edx, 20h ; ' '
0x1800063c9  lea     rcx, [rbp+57h+String2]
0x1800063cd  call    cs:__imp__o_wcsncpy_s
0x1800063d3  test    eax, eax
0x1800063d5  jz      short loc_1800063FB
0x1800063d7  cmp     eax, 0Ch
0x1800063da  jz      loc_180006539
0x1800063e0  cmp     eax, 16h
0x1800063e3  jz      loc_18000652E
0x1800063e9  cmp     eax, 22h ; '"'
0x1800063ec  jz      loc_18000652E
0x1800063f2  cmp     eax, 50h ; 'P'
0x1800063f5  jnz     loc_180006523
0x1800063fb  mov     rdi, [r14+8]
0x1800063ff  mov     ebx, r12d
0x180006402  cmp     [rdi+18h], r12d
0x180006406  jle     short loc_180006428
0x180006408  movsxd  rax, ebx
0x18000640b  mov     rcx, [rdi+8]
0x18000640f  lea     rdx, [rbp+57h+String2]; lpString2
0x180006413  mov     rcx, [rcx+rax*8]; lpString1
0x180006417  call    cs:__imp_lstrcmpiW
0x18000641d  test    eax, eax
0x18000641f  jz      short loc_180006432
0x180006421  inc     ebx
0x180006423  cmp     ebx, [rdi+18h]
0x180006426  jl      short loc_180006408
0x180006428  mov     ebx, 80020009h
0x18000642d  jmp     loc_1800064CF
0x180006432  cmp     ebx, 0FFFFFFFFh
0x180006435  jz      short loc_180006428
0x180006437  test    ebx, ebx
0x180006439  js      loc_180006518
0x18000643f  cmp     ebx, [rdi+18h]
0x180006442  jge     loc_180006518
0x180006448  movsxd  rcx, ebx
0x18000644b  mov     rax, [rdi+10h]
0x18000644f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180006453  test    rdx, rdx
0x180006456  jz      short loc_180006428
0x180006458  mov     [rbp+57h+var_80], r12
0x18000645c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006460  inc     r8; int
0x180006463  cmp     [rdx+r8*2], r12w
0x180006468  jnz     short loc_180006460
0x18000646a  lea     rcx, [rbp+57h+var_90]; this
0x18000646e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006473  nop
0x180006474  test    eax, eax
0x180006476  jz      short loc_1800064E4
0x180006478  mov     rax, [r14]
0x18000647b  jmp     short loc_180006489
0x18000647d  mov     rcx, rax; lpsz
0x180006480  call    cs:__imp_CharNextW
0x180006486  mov     [r14], rax
0x180006489  cmp     rax, rsi
0x18000648c  jnz     short loc_18000647D
0x18000648e  jmp     short loc_1800064A6
0x180006490  mov     rdx, rbx; unsigned __int16 *
0x180006493  mov     r8d, 1; int
0x180006499  lea     rcx, [rbp+57h+var_90]; this
0x18000649d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800064a2  test    eax, eax
0x1800064a4  jz      short loc_1800064E4
0x1800064a6  mov     rcx, [r14]; lpsz
0x1800064a9  call    cs:__imp_CharNextW
0x1800064af  mov     rbx, rax
0x1800064b2  mov     [r14], rax
0x1800064b5  movzx   eax, word ptr [rax]
0x1800064b8  test    ax, ax
0x1800064bb  jnz     loc_180006355
0x1800064c1  mov     rdx, [rbp+57h+pv]
0x1800064c5  mov     ebx, r12d
0x1800064c8  mov     [rbp+57h+pv], r12
0x1800064cc  mov     [r15], rdx
0x1800064cf  mov     rcx, [rbp+57h+pv]; pv
0x1800064d3  call    cs:__imp_CoTaskMemFree
0x1800064d9  mov     eax, ebx
0x1800064db  jmp     short loc_1800064F0
0x1800064dd  mov     ebx, 80004005h
0x1800064e2  jmp     short loc_1800064CF
0x1800064e4  mov     ebx, 8007000Eh
0x1800064e9  jmp     short loc_1800064CF
0x1800064eb  mov     eax, 80004003h
0x1800064f0  mov     rcx, [rbp+57h+var_30]
0x1800064f4  xor     rcx, rsp; StackCookie
0x1800064f7  call    __security_check_cookie
0x1800064fc  lea     r11, [rsp+0B0h+var_20]
0x180006504  mov     rbx, [r11+38h]
0x180006508  mov     rsi, [r11+48h]
0x18000650c  mov     rsp, r11
0x18000650f  pop     r15
0x180006511  pop     r14
0x180006513  pop     r12
0x180006515  pop     rdi
0x180006516  pop     rbp
0x180006517  retn
0x180006518  mov     ecx, 0C000008Ch; unsigned int
0x18000651d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006522  int     3; Trap to Debugger
0x180006523  mov     ecx, 80004005h; int
0x180006528  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000652e  mov     ecx, 80070057h; int
0x180006533  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006539  mov     ecx, 8007000Eh; int
0x18000653e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
