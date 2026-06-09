# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800061fc`
- end: `0x1800064b4`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000680c`

## callees

- `0x180001e60`
- `0x180004630`
- `0x180004768`
- `0x1800061fc`
- `0x18000883c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000633d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000633d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006443`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006443`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006288`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800062d2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006303`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800063f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006419`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800062d2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006303`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800063f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006419`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006387`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006387`

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
0x1800061fc  mov     [rsp-8+arg_8], rbx
0x180006201  mov     [rsp-8+arg_18], rsi
0x180006206  push    rbp
0x180006207  push    rdi
0x180006208  push    r12
0x18000620a  push    r14
0x18000620c  push    r15
0x18000620e  lea     rbp, [rsp-37h]
0x180006213  sub     rsp, 90h
0x18000621a  mov     rax, cs:__security_cookie
0x180006221  xor     rax, rsp
0x180006224  mov     [rbp+57h+var_30], rax
0x180006228  mov     r15, r8
0x18000622b  mov     rbx, rdx
0x18000622e  mov     r14, rcx
0x180006231  xor     r12d, r12d
0x180006234  test    rdx, rdx
0x180006237  jz      loc_18000645B
0x18000623d  test    r8, r8
0x180006240  jz      loc_18000645B
0x180006246  mov     [r8], r12
0x180006249  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000624d  inc     rax
0x180006250  cmp     [rdx+rax*2], r12w
0x180006255  jnz     short loc_18000624D
0x180006257  add     eax, eax
0x180006259  mov     ecx, 3E8h
0x18000625e  cmp     eax, 64h ; 'd'
0x180006261  cmovl   eax, ecx
0x180006264  mov     [rbp+57h+var_90], r12d
0x180006268  mov     [rbp+57h+var_8C], eax
0x18000626b  mov     ecx, eax
0x18000626d  add     rcx, rcx
0x180006270  mov     eax, 0FFFFFFFFh
0x180006275  cmp     rcx, rax
0x180006278  jbe     short loc_180006286
0x18000627a  mov     rax, r12
0x18000627d  mov     rdx, r12
0x180006280  mov     [rbp+57h+pv], rdx
0x180006284  jmp     short loc_18000629E
0x180006286  mov     ecx, ecx; cb
0x180006288  call    cs:__imp_CoTaskMemAlloc
0x18000628e  mov     rdx, rax
0x180006291  mov     [rbp+57h+pv], rax
0x180006295  test    rax, rax
0x180006298  jz      short loc_18000629E
0x18000629a  mov     [rax], r12w
0x18000629e  test    rax, rax
0x1800062a1  jnz     short loc_1800062B6
0x1800062a3  mov     rcx, rax; pv
0x1800062a6  call    cs:__imp_CoTaskMemFree
0x1800062ac  mov     eax, 8007000Eh
0x1800062b1  jmp     loc_180006460
0x1800062b6  mov     [r14], rbx
0x1800062b9  movzx   eax, word ptr [rbx]
0x1800062bc  test    ax, ax
0x1800062bf  jz      loc_180006435
0x1800062c5  cmp     ax, 25h ; '%'
0x1800062c9  jnz     loc_180006400
0x1800062cf  mov     rcx, rbx; lpsz
0x1800062d2  call    cs:__imp_CharNextW
0x1800062d8  mov     [r14], rax
0x1800062db  movzx   ecx, word ptr [rax]
0x1800062de  cmp     cx, 25h ; '%'
0x1800062e2  jnz     short loc_1800062EC
0x1800062e4  mov     rdx, rax
0x1800062e7  jmp     loc_180006403
0x1800062ec  test    rax, rax
0x1800062ef  jz      loc_180006398
0x1800062f5  mov     rsi, r12
0x1800062f8  jmp     short loc_18000630C
0x1800062fa  cmp     cx, 25h ; '%'
0x1800062fe  jz      short loc_180006313
0x180006300  mov     rcx, rax; lpsz
0x180006303  call    cs:__imp_CharNextW
0x180006309  movzx   ecx, word ptr [rax]
0x18000630c  test    cx, cx
0x18000630f  jnz     short loc_1800062FA
0x180006311  jmp     short loc_180006316
0x180006313  mov     rsi, rax
0x180006316  test    rsi, rsi
0x180006319  jz      short loc_180006398
0x18000631b  mov     rax, rsi
0x18000631e  sub     rax, [r14]
0x180006321  sar     rax, 1
0x180006324  cmp     rax, 1Fh
0x180006328  jg      loc_18000644D
0x18000632e  movsxd  r9, eax
0x180006331  mov     r8, [r14]
0x180006334  mov     edx, 20h ; ' '
0x180006339  lea     rcx, [rbp+57h+String2]
0x18000633d  call    cs:__imp__o_wcsncpy_s
0x180006343  test    eax, eax
0x180006345  jz      short loc_18000636B
0x180006347  cmp     eax, 0Ch
0x18000634a  jz      loc_1800064A9
0x180006350  cmp     eax, 16h
0x180006353  jz      loc_18000649E
0x180006359  cmp     eax, 22h ; '"'
0x18000635c  jz      loc_18000649E
0x180006362  cmp     eax, 50h ; 'P'
0x180006365  jnz     loc_180006493
0x18000636b  mov     rdi, [r14+8]
0x18000636f  mov     ebx, r12d
0x180006372  cmp     [rdi+18h], r12d
0x180006376  jle     short loc_180006398
0x180006378  movsxd  rax, ebx
0x18000637b  mov     rcx, [rdi+8]
0x18000637f  lea     rdx, [rbp+57h+String2]; lpString2
0x180006383  mov     rcx, [rcx+rax*8]; lpString1
0x180006387  call    cs:__imp_lstrcmpiW
0x18000638d  test    eax, eax
0x18000638f  jz      short loc_1800063A2
0x180006391  inc     ebx
0x180006393  cmp     ebx, [rdi+18h]
0x180006396  jl      short loc_180006378
0x180006398  mov     ebx, 80020009h
0x18000639d  jmp     loc_18000643F
0x1800063a2  cmp     ebx, 0FFFFFFFFh
0x1800063a5  jz      short loc_180006398
0x1800063a7  test    ebx, ebx
0x1800063a9  js      loc_180006488
0x1800063af  cmp     ebx, [rdi+18h]
0x1800063b2  jge     loc_180006488
0x1800063b8  movsxd  rcx, ebx
0x1800063bb  mov     rax, [rdi+10h]
0x1800063bf  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x1800063c3  test    rdx, rdx
0x1800063c6  jz      short loc_180006398
0x1800063c8  mov     [rbp+57h+var_80], r12
0x1800063cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800063d0  inc     r8; int
0x1800063d3  cmp     [rdx+r8*2], r12w
0x1800063d8  jnz     short loc_1800063D0
0x1800063da  lea     rcx, [rbp+57h+var_90]; this
0x1800063de  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800063e3  nop
0x1800063e4  test    eax, eax
0x1800063e6  jz      short loc_180006454
0x1800063e8  mov     rax, [r14]
0x1800063eb  jmp     short loc_1800063F9
0x1800063ed  mov     rcx, rax; lpsz
0x1800063f0  call    cs:__imp_CharNextW
0x1800063f6  mov     [r14], rax
0x1800063f9  cmp     rax, rsi
0x1800063fc  jnz     short loc_1800063ED
0x1800063fe  jmp     short loc_180006416
0x180006400  mov     rdx, rbx; unsigned __int16 *
0x180006403  mov     r8d, 1; int
0x180006409  lea     rcx, [rbp+57h+var_90]; this
0x18000640d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006412  test    eax, eax
0x180006414  jz      short loc_180006454
0x180006416  mov     rcx, [r14]; lpsz
0x180006419  call    cs:__imp_CharNextW
0x18000641f  mov     rbx, rax
0x180006422  mov     [r14], rax
0x180006425  movzx   eax, word ptr [rax]
0x180006428  test    ax, ax
0x18000642b  jnz     loc_1800062C5
0x180006431  mov     rdx, [rbp+57h+pv]
0x180006435  mov     ebx, r12d
0x180006438  mov     [rbp+57h+pv], r12
0x18000643c  mov     [r15], rdx
0x18000643f  mov     rcx, [rbp+57h+pv]; pv
0x180006443  call    cs:__imp_CoTaskMemFree
0x180006449  mov     eax, ebx
0x18000644b  jmp     short loc_180006460
0x18000644d  mov     ebx, 80004005h
0x180006452  jmp     short loc_18000643F
0x180006454  mov     ebx, 8007000Eh
0x180006459  jmp     short loc_18000643F
0x18000645b  mov     eax, 80004003h
0x180006460  mov     rcx, [rbp+57h+var_30]
0x180006464  xor     rcx, rsp; StackCookie
0x180006467  call    __security_check_cookie
0x18000646c  lea     r11, [rsp+0B0h+var_20]
0x180006474  mov     rbx, [r11+38h]
0x180006478  mov     rsi, [r11+48h]
0x18000647c  mov     rsp, r11
0x18000647f  pop     r15
0x180006481  pop     r14
0x180006483  pop     r12
0x180006485  pop     rdi
0x180006486  pop     rbp
0x180006487  retn
0x180006488  mov     ecx, 0C000008Ch; unsigned int
0x18000648d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006492  int     3; Trap to Debugger
0x180006493  mov     ecx, 80004005h; int
0x180006498  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000649e  mov     ecx, 80070057h; int
0x1800064a3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800064a9  mov     ecx, 8007000Eh; int
0x1800064ae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
