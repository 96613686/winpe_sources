# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000639c`
- end: `0x180006654`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800069ac`

## callees

- `0x180002000`
- `0x1800047d0`
- `0x180004908`
- `0x18000639c`
- `0x1800089ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800064dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800064dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800065e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006472`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800064a3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006590`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800065b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006472`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800064a3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006590`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800065b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006527`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006527`

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
0x18000639c  mov     [rsp-8+arg_8], rbx
0x1800063a1  mov     [rsp-8+arg_18], rsi
0x1800063a6  push    rbp
0x1800063a7  push    rdi
0x1800063a8  push    r12
0x1800063aa  push    r14
0x1800063ac  push    r15
0x1800063ae  lea     rbp, [rsp-37h]
0x1800063b3  sub     rsp, 90h
0x1800063ba  mov     rax, cs:__security_cookie
0x1800063c1  xor     rax, rsp
0x1800063c4  mov     [rbp+57h+var_30], rax
0x1800063c8  mov     r15, r8
0x1800063cb  mov     rbx, rdx
0x1800063ce  mov     r14, rcx
0x1800063d1  xor     r12d, r12d
0x1800063d4  test    rdx, rdx
0x1800063d7  jz      loc_1800065FB
0x1800063dd  test    r8, r8
0x1800063e0  jz      loc_1800065FB
0x1800063e6  mov     [r8], r12
0x1800063e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800063ed  inc     rax
0x1800063f0  cmp     [rdx+rax*2], r12w
0x1800063f5  jnz     short loc_1800063ED
0x1800063f7  add     eax, eax
0x1800063f9  mov     ecx, 3E8h
0x1800063fe  cmp     eax, 64h ; 'd'
0x180006401  cmovl   eax, ecx
0x180006404  mov     [rbp+57h+var_90], r12d
0x180006408  mov     [rbp+57h+var_8C], eax
0x18000640b  mov     ecx, eax
0x18000640d  add     rcx, rcx
0x180006410  mov     eax, 0FFFFFFFFh
0x180006415  cmp     rcx, rax
0x180006418  jbe     short loc_180006426
0x18000641a  mov     rax, r12
0x18000641d  mov     rdx, r12
0x180006420  mov     [rbp+57h+pv], rdx
0x180006424  jmp     short loc_18000643E
0x180006426  mov     ecx, ecx; cb
0x180006428  call    cs:__imp_CoTaskMemAlloc
0x18000642e  mov     rdx, rax
0x180006431  mov     [rbp+57h+pv], rax
0x180006435  test    rax, rax
0x180006438  jz      short loc_18000643E
0x18000643a  mov     [rax], r12w
0x18000643e  test    rax, rax
0x180006441  jnz     short loc_180006456
0x180006443  mov     rcx, rax; pv
0x180006446  call    cs:__imp_CoTaskMemFree
0x18000644c  mov     eax, 8007000Eh
0x180006451  jmp     loc_180006600
0x180006456  mov     [r14], rbx
0x180006459  movzx   eax, word ptr [rbx]
0x18000645c  test    ax, ax
0x18000645f  jz      loc_1800065D5
0x180006465  cmp     ax, 25h ; '%'
0x180006469  jnz     loc_1800065A0
0x18000646f  mov     rcx, rbx; lpsz
0x180006472  call    cs:__imp_CharNextW
0x180006478  mov     [r14], rax
0x18000647b  movzx   ecx, word ptr [rax]
0x18000647e  cmp     cx, 25h ; '%'
0x180006482  jnz     short loc_18000648C
0x180006484  mov     rdx, rax
0x180006487  jmp     loc_1800065A3
0x18000648c  test    rax, rax
0x18000648f  jz      loc_180006538
0x180006495  mov     rsi, r12
0x180006498  jmp     short loc_1800064AC
0x18000649a  cmp     cx, 25h ; '%'
0x18000649e  jz      short loc_1800064B3
0x1800064a0  mov     rcx, rax; lpsz
0x1800064a3  call    cs:__imp_CharNextW
0x1800064a9  movzx   ecx, word ptr [rax]
0x1800064ac  test    cx, cx
0x1800064af  jnz     short loc_18000649A
0x1800064b1  jmp     short loc_1800064B6
0x1800064b3  mov     rsi, rax
0x1800064b6  test    rsi, rsi
0x1800064b9  jz      short loc_180006538
0x1800064bb  mov     rax, rsi
0x1800064be  sub     rax, [r14]
0x1800064c1  sar     rax, 1
0x1800064c4  cmp     rax, 1Fh
0x1800064c8  jg      loc_1800065ED
0x1800064ce  movsxd  r9, eax
0x1800064d1  mov     r8, [r14]
0x1800064d4  mov     edx, 20h ; ' '
0x1800064d9  lea     rcx, [rbp+57h+String2]
0x1800064dd  call    cs:__imp__o_wcsncpy_s
0x1800064e3  test    eax, eax
0x1800064e5  jz      short loc_18000650B
0x1800064e7  cmp     eax, 0Ch
0x1800064ea  jz      loc_180006649
0x1800064f0  cmp     eax, 16h
0x1800064f3  jz      loc_18000663E
0x1800064f9  cmp     eax, 22h ; '"'
0x1800064fc  jz      loc_18000663E
0x180006502  cmp     eax, 50h ; 'P'
0x180006505  jnz     loc_180006633
0x18000650b  mov     rdi, [r14+8]
0x18000650f  mov     ebx, r12d
0x180006512  cmp     [rdi+18h], r12d
0x180006516  jle     short loc_180006538
0x180006518  movsxd  rax, ebx
0x18000651b  mov     rcx, [rdi+8]
0x18000651f  lea     rdx, [rbp+57h+String2]; lpString2
0x180006523  mov     rcx, [rcx+rax*8]; lpString1
0x180006527  call    cs:__imp_lstrcmpiW
0x18000652d  test    eax, eax
0x18000652f  jz      short loc_180006542
0x180006531  inc     ebx
0x180006533  cmp     ebx, [rdi+18h]
0x180006536  jl      short loc_180006518
0x180006538  mov     ebx, 80020009h
0x18000653d  jmp     loc_1800065DF
0x180006542  cmp     ebx, 0FFFFFFFFh
0x180006545  jz      short loc_180006538
0x180006547  test    ebx, ebx
0x180006549  js      loc_180006628
0x18000654f  cmp     ebx, [rdi+18h]
0x180006552  jge     loc_180006628
0x180006558  movsxd  rcx, ebx
0x18000655b  mov     rax, [rdi+10h]
0x18000655f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180006563  test    rdx, rdx
0x180006566  jz      short loc_180006538
0x180006568  mov     [rbp+57h+var_80], r12
0x18000656c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006570  inc     r8; int
0x180006573  cmp     [rdx+r8*2], r12w
0x180006578  jnz     short loc_180006570
0x18000657a  lea     rcx, [rbp+57h+var_90]; this
0x18000657e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180006583  nop
0x180006584  test    eax, eax
0x180006586  jz      short loc_1800065F4
0x180006588  mov     rax, [r14]
0x18000658b  jmp     short loc_180006599
0x18000658d  mov     rcx, rax; lpsz
0x180006590  call    cs:__imp_CharNextW
0x180006596  mov     [r14], rax
0x180006599  cmp     rax, rsi
0x18000659c  jnz     short loc_18000658D
0x18000659e  jmp     short loc_1800065B6
0x1800065a0  mov     rdx, rbx; unsigned __int16 *
0x1800065a3  mov     r8d, 1; int
0x1800065a9  lea     rcx, [rbp+57h+var_90]; this
0x1800065ad  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800065b2  test    eax, eax
0x1800065b4  jz      short loc_1800065F4
0x1800065b6  mov     rcx, [r14]; lpsz
0x1800065b9  call    cs:__imp_CharNextW
0x1800065bf  mov     rbx, rax
0x1800065c2  mov     [r14], rax
0x1800065c5  movzx   eax, word ptr [rax]
0x1800065c8  test    ax, ax
0x1800065cb  jnz     loc_180006465
0x1800065d1  mov     rdx, [rbp+57h+pv]
0x1800065d5  mov     ebx, r12d
0x1800065d8  mov     [rbp+57h+pv], r12
0x1800065dc  mov     [r15], rdx
0x1800065df  mov     rcx, [rbp+57h+pv]; pv
0x1800065e3  call    cs:__imp_CoTaskMemFree
0x1800065e9  mov     eax, ebx
0x1800065eb  jmp     short loc_180006600
0x1800065ed  mov     ebx, 80004005h
0x1800065f2  jmp     short loc_1800065DF
0x1800065f4  mov     ebx, 8007000Eh
0x1800065f9  jmp     short loc_1800065DF
0x1800065fb  mov     eax, 80004003h
0x180006600  mov     rcx, [rbp+57h+var_30]
0x180006604  xor     rcx, rsp; StackCookie
0x180006607  call    __security_check_cookie
0x18000660c  lea     r11, [rsp+0B0h+var_20]
0x180006614  mov     rbx, [r11+38h]
0x180006618  mov     rsi, [r11+48h]
0x18000661c  mov     rsp, r11
0x18000661f  pop     r15
0x180006621  pop     r14
0x180006623  pop     r12
0x180006625  pop     rdi
0x180006626  pop     rbp
0x180006627  retn
0x180006628  mov     ecx, 0C000008Ch; unsigned int
0x18000662d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180006632  int     3; Trap to Debugger
0x180006633  mov     ecx, 80004005h; int
0x180006638  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000663e  mov     ecx, 80070057h; int
0x180006643  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006649  mov     ecx, 8007000Eh; int
0x18000664e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
