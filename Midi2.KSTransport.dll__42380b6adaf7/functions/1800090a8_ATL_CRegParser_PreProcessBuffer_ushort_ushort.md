# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800090a8`
- end: `0x180009360`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009954`

## callees

- `0x180004410`
- `0x180007400`
- `0x180007538`
- `0x1800090a8`
- `0x18000badc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800091e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800091e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009152`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009152`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800092ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009134`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000917e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800091af`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000929c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092c5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000917e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800091af`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000929c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009233`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009233`

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
0x1800090a8  mov     [rsp-8+arg_8], rbx
0x1800090ad  mov     [rsp-8+arg_18], rsi
0x1800090b2  push    rbp
0x1800090b3  push    rdi
0x1800090b4  push    r12
0x1800090b6  push    r14
0x1800090b8  push    r15
0x1800090ba  lea     rbp, [rsp-37h]
0x1800090bf  sub     rsp, 90h
0x1800090c6  mov     rax, cs:__security_cookie
0x1800090cd  xor     rax, rsp
0x1800090d0  mov     [rbp+57h+var_30], rax
0x1800090d4  mov     r15, r8
0x1800090d7  mov     rbx, rdx
0x1800090da  mov     r14, rcx
0x1800090dd  xor     r12d, r12d
0x1800090e0  test    rdx, rdx
0x1800090e3  jz      loc_180009307
0x1800090e9  test    r8, r8
0x1800090ec  jz      loc_180009307
0x1800090f2  mov     [r8], r12
0x1800090f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800090f9  inc     rax
0x1800090fc  cmp     [rdx+rax*2], r12w
0x180009101  jnz     short loc_1800090F9
0x180009103  add     eax, eax
0x180009105  mov     ecx, 3E8h
0x18000910a  cmp     eax, 64h ; 'd'
0x18000910d  cmovl   eax, ecx
0x180009110  mov     [rbp+57h+var_90], r12d
0x180009114  mov     [rbp+57h+var_8C], eax
0x180009117  mov     ecx, eax
0x180009119  add     rcx, rcx
0x18000911c  mov     eax, 0FFFFFFFFh
0x180009121  cmp     rcx, rax
0x180009124  jbe     short loc_180009132
0x180009126  mov     rax, r12
0x180009129  mov     rdx, r12
0x18000912c  mov     [rbp+57h+pv], rdx
0x180009130  jmp     short loc_18000914A
0x180009132  mov     ecx, ecx; cb
0x180009134  call    cs:__imp_CoTaskMemAlloc
0x18000913a  mov     rdx, rax
0x18000913d  mov     [rbp+57h+pv], rax
0x180009141  test    rax, rax
0x180009144  jz      short loc_18000914A
0x180009146  mov     [rax], r12w
0x18000914a  test    rax, rax
0x18000914d  jnz     short loc_180009162
0x18000914f  mov     rcx, rax; pv
0x180009152  call    cs:__imp_CoTaskMemFree
0x180009158  mov     eax, 8007000Eh
0x18000915d  jmp     loc_18000930C
0x180009162  mov     [r14], rbx
0x180009165  movzx   eax, word ptr [rbx]
0x180009168  test    ax, ax
0x18000916b  jz      loc_1800092E1
0x180009171  cmp     ax, 25h ; '%'
0x180009175  jnz     loc_1800092AC
0x18000917b  mov     rcx, rbx; lpsz
0x18000917e  call    cs:__imp_CharNextW
0x180009184  mov     [r14], rax
0x180009187  movzx   ecx, word ptr [rax]
0x18000918a  cmp     cx, 25h ; '%'
0x18000918e  jnz     short loc_180009198
0x180009190  mov     rdx, rax
0x180009193  jmp     loc_1800092AF
0x180009198  test    rax, rax
0x18000919b  jz      loc_180009244
0x1800091a1  mov     rsi, r12
0x1800091a4  jmp     short loc_1800091B8
0x1800091a6  cmp     cx, 25h ; '%'
0x1800091aa  jz      short loc_1800091BF
0x1800091ac  mov     rcx, rax; lpsz
0x1800091af  call    cs:__imp_CharNextW
0x1800091b5  movzx   ecx, word ptr [rax]
0x1800091b8  test    cx, cx
0x1800091bb  jnz     short loc_1800091A6
0x1800091bd  jmp     short loc_1800091C2
0x1800091bf  mov     rsi, rax
0x1800091c2  test    rsi, rsi
0x1800091c5  jz      short loc_180009244
0x1800091c7  mov     rax, rsi
0x1800091ca  sub     rax, [r14]
0x1800091cd  sar     rax, 1
0x1800091d0  cmp     rax, 1Fh
0x1800091d4  jg      loc_1800092F9
0x1800091da  movsxd  r9, eax
0x1800091dd  mov     r8, [r14]
0x1800091e0  mov     edx, 20h ; ' '
0x1800091e5  lea     rcx, [rbp+57h+String2]
0x1800091e9  call    cs:__imp__o_wcsncpy_s
0x1800091ef  test    eax, eax
0x1800091f1  jz      short loc_180009217
0x1800091f3  cmp     eax, 0Ch
0x1800091f6  jz      loc_180009355
0x1800091fc  cmp     eax, 16h
0x1800091ff  jz      loc_18000934A
0x180009205  cmp     eax, 22h ; '"'
0x180009208  jz      loc_18000934A
0x18000920e  cmp     eax, 50h ; 'P'
0x180009211  jnz     loc_18000933F
0x180009217  mov     rdi, [r14+8]
0x18000921b  mov     ebx, r12d
0x18000921e  cmp     [rdi+18h], r12d
0x180009222  jle     short loc_180009244
0x180009224  movsxd  rax, ebx
0x180009227  mov     rcx, [rdi+8]
0x18000922b  lea     rdx, [rbp+57h+String2]; lpString2
0x18000922f  mov     rcx, [rcx+rax*8]; lpString1
0x180009233  call    cs:__imp_lstrcmpiW
0x180009239  test    eax, eax
0x18000923b  jz      short loc_18000924E
0x18000923d  inc     ebx
0x18000923f  cmp     ebx, [rdi+18h]
0x180009242  jl      short loc_180009224
0x180009244  mov     ebx, 80020009h
0x180009249  jmp     loc_1800092EB
0x18000924e  cmp     ebx, 0FFFFFFFFh
0x180009251  jz      short loc_180009244
0x180009253  test    ebx, ebx
0x180009255  js      loc_180009334
0x18000925b  cmp     ebx, [rdi+18h]
0x18000925e  jge     loc_180009334
0x180009264  movsxd  rcx, ebx
0x180009267  mov     rax, [rdi+10h]
0x18000926b  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x18000926f  test    rdx, rdx
0x180009272  jz      short loc_180009244
0x180009274  mov     [rbp+57h+var_80], r12
0x180009278  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000927c  inc     r8; int
0x18000927f  cmp     [rdx+r8*2], r12w
0x180009284  jnz     short loc_18000927C
0x180009286  lea     rcx, [rbp+57h+var_90]; this
0x18000928a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000928f  nop
0x180009290  test    eax, eax
0x180009292  jz      short loc_180009300
0x180009294  mov     rax, [r14]
0x180009297  jmp     short loc_1800092A5
0x180009299  mov     rcx, rax; lpsz
0x18000929c  call    cs:__imp_CharNextW
0x1800092a2  mov     [r14], rax
0x1800092a5  cmp     rax, rsi
0x1800092a8  jnz     short loc_180009299
0x1800092aa  jmp     short loc_1800092C2
0x1800092ac  mov     rdx, rbx; unsigned __int16 *
0x1800092af  mov     r8d, 1; int
0x1800092b5  lea     rcx, [rbp+57h+var_90]; this
0x1800092b9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800092be  test    eax, eax
0x1800092c0  jz      short loc_180009300
0x1800092c2  mov     rcx, [r14]; lpsz
0x1800092c5  call    cs:__imp_CharNextW
0x1800092cb  mov     rbx, rax
0x1800092ce  mov     [r14], rax
0x1800092d1  movzx   eax, word ptr [rax]
0x1800092d4  test    ax, ax
0x1800092d7  jnz     loc_180009171
0x1800092dd  mov     rdx, [rbp+57h+pv]
0x1800092e1  mov     ebx, r12d
0x1800092e4  mov     [rbp+57h+pv], r12
0x1800092e8  mov     [r15], rdx
0x1800092eb  mov     rcx, [rbp+57h+pv]; pv
0x1800092ef  call    cs:__imp_CoTaskMemFree
0x1800092f5  mov     eax, ebx
0x1800092f7  jmp     short loc_18000930C
0x1800092f9  mov     ebx, 80004005h
0x1800092fe  jmp     short loc_1800092EB
0x180009300  mov     ebx, 8007000Eh
0x180009305  jmp     short loc_1800092EB
0x180009307  mov     eax, 80004003h
0x18000930c  mov     rcx, [rbp+57h+var_30]
0x180009310  xor     rcx, rsp; StackCookie
0x180009313  call    __security_check_cookie
0x180009318  lea     r11, [rsp+0B0h+var_20]
0x180009320  mov     rbx, [r11+38h]
0x180009324  mov     rsi, [r11+48h]
0x180009328  mov     rsp, r11
0x18000932b  pop     r15
0x18000932d  pop     r14
0x18000932f  pop     r12
0x180009331  pop     rdi
0x180009332  pop     rbp
0x180009333  retn
0x180009334  mov     ecx, 0C000008Ch; unsigned int
0x180009339  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000933e  int     3; Trap to Debugger
0x18000933f  mov     ecx, 80004005h; int
0x180009344  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000934a  mov     ecx, 80070057h; int
0x18000934f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009355  mov     ecx, 8007000Eh; int
0x18000935a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
