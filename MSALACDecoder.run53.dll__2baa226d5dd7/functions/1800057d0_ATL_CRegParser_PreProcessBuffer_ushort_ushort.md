# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800057d0`
- end: `0x180005aab`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005d08`

## callees

- `0x180001550`
- `0x180004c3c`
- `0x180004e40`
- `0x1800057d0`
- `0x18000725c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005913`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005913`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000597f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000597f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005949`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000585a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000585a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800058a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800058d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800059e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a09`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800058a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800058d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800059e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005967`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005967`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v25 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
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
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_52;
  }
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x1800057d0  mov     [rsp-8+arg_8], rbx
0x1800057d5  push    rbp
0x1800057d6  push    rsi
0x1800057d7  push    rdi
0x1800057d8  push    r12
0x1800057da  push    r13
0x1800057dc  push    r14
0x1800057de  push    r15
0x1800057e0  lea     rbp, [rsp-27h]
0x1800057e5  sub     rsp, 90h
0x1800057ec  mov     rax, cs:__security_cookie
0x1800057f3  xor     rax, rsp
0x1800057f6  mov     [rbp+57h+var_40], rax
0x1800057fa  mov     r12, r8
0x1800057fd  mov     rbx, rdx
0x180005800  mov     r14, rcx
0x180005803  xor     r13d, r13d
0x180005806  test    rdx, rdx
0x180005809  jz      loc_180005A53
0x18000580f  test    r8, r8
0x180005812  jz      loc_180005A53
0x180005818  mov     [r8], r13
0x18000581b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000581f  inc     rax
0x180005822  cmp     [rdx+rax*2], r13w
0x180005827  jnz     short loc_18000581F
0x180005829  add     eax, eax
0x18000582b  mov     ecx, 3E8h
0x180005830  cmp     eax, 64h ; 'd'
0x180005833  cmovl   eax, ecx
0x180005836  mov     [rbp+57h+var_A0], r13d
0x18000583a  mov     [rbp+57h+var_9C], eax
0x18000583d  mov     ecx, eax
0x18000583f  add     rcx, rcx
0x180005842  mov     eax, 0FFFFFFFFh
0x180005847  cmp     rcx, rax
0x18000584a  jbe     short loc_180005858
0x18000584c  mov     rax, r13
0x18000584f  mov     rdx, r13
0x180005852  mov     [rbp+57h+pv], rdx
0x180005856  jmp     short loc_180005870
0x180005858  mov     ecx, ecx; cb
0x18000585a  call    cs:__imp_CoTaskMemAlloc
0x180005860  mov     rdx, rax
0x180005863  mov     [rbp+57h+pv], rax
0x180005867  test    rax, rax
0x18000586a  jz      short loc_180005870
0x18000586c  mov     [rax], r13w
0x180005870  test    rax, rax
0x180005873  jnz     short loc_180005888
0x180005875  mov     rcx, rax; pv
0x180005878  call    cs:__imp_CoTaskMemFree
0x18000587e  mov     eax, 8007000Eh
0x180005883  jmp     loc_180005A58
0x180005888  mov     [r14], rbx
0x18000588b  movzx   eax, word ptr [rbx]
0x18000588e  test    ax, ax
0x180005891  jz      loc_180005A25
0x180005897  cmp     ax, 25h ; '%'
0x18000589b  jnz     loc_1800059F0
0x1800058a1  mov     rcx, rbx; lpsz
0x1800058a4  call    cs:__imp_CharNextW
0x1800058aa  mov     [r14], rax
0x1800058ad  movzx   ecx, word ptr [rax]
0x1800058b0  cmp     cx, 25h ; '%'
0x1800058b4  jnz     short loc_1800058BE
0x1800058b6  mov     rdx, rax
0x1800058b9  jmp     loc_1800059F3
0x1800058be  test    rax, rax
0x1800058c1  jz      loc_180005A45
0x1800058c7  mov     rdi, r13
0x1800058ca  jmp     short loc_1800058DE
0x1800058cc  cmp     cx, 25h ; '%'
0x1800058d0  jz      short loc_1800058E5
0x1800058d2  mov     rcx, rax; lpsz
0x1800058d5  call    cs:__imp_CharNextW
0x1800058db  movzx   ecx, word ptr [rax]
0x1800058de  test    cx, cx
0x1800058e1  jnz     short loc_1800058CC
0x1800058e3  jmp     short loc_1800058E8
0x1800058e5  mov     rdi, rax
0x1800058e8  test    rdi, rdi
0x1800058eb  jz      loc_180005A45
0x1800058f1  mov     rax, rdi
0x1800058f4  sub     rax, [r14]
0x1800058f7  sar     rax, 1
0x1800058fa  cmp     rax, 1Fh
0x1800058fe  jg      loc_180005A3E
0x180005904  movsxd  r9, eax
0x180005907  mov     r8, [r14]
0x18000590a  mov     edx, 20h ; ' '
0x18000590f  lea     rcx, [rbp+57h+String2]
0x180005913  call    cs:__imp__o_wcsncpy_s
0x180005919  test    eax, eax
0x18000591b  jz      short loc_180005941
0x18000591d  cmp     eax, 0Ch
0x180005920  jz      loc_180005AA0
0x180005926  cmp     eax, 16h
0x180005929  jz      loc_180005A95
0x18000592f  cmp     eax, 22h ; '"'
0x180005932  jz      loc_180005A95
0x180005938  cmp     eax, 50h ; 'P'
0x18000593b  jnz     loc_180005A8A
0x180005941  mov     rsi, [r14+8]
0x180005945  lea     rcx, [rsi+20h]; lpCriticalSection
0x180005949  call    cs:__imp_EnterCriticalSection
0x18000594f  mov     ebx, r13d
0x180005952  cmp     [rsi+18h], r13d
0x180005956  jle     short loc_180005978
0x180005958  movsxd  rax, ebx
0x18000595b  mov     rcx, [rsi+8]
0x18000595f  lea     rdx, [rbp+57h+String2]; lpString2
0x180005963  mov     rcx, [rcx+rax*8]; lpString1
0x180005967  call    cs:__imp_lstrcmpiW
0x18000596d  test    eax, eax
0x18000596f  jz      short loc_1800059BA
0x180005971  inc     ebx
0x180005973  cmp     ebx, [rsi+18h]
0x180005976  jl      short loc_180005958
0x180005978  mov     rbx, r13
0x18000597b  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000597f  call    cs:__imp_LeaveCriticalSection
0x180005985  test    rbx, rbx
0x180005988  jz      loc_180005A45
0x18000598e  mov     [rbp+57h+var_90], r13
0x180005992  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005996  inc     r8; int
0x180005999  cmp     [rbx+r8*2], r13w
0x18000599e  jnz     short loc_180005996
0x1800059a0  mov     rdx, rbx; unsigned __int16 *
0x1800059a3  lea     rcx, [rbp+57h+var_A0]; this
0x1800059a7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800059ac  nop
0x1800059ad  test    eax, eax
0x1800059af  jz      loc_180005A4C
0x1800059b5  mov     rax, [r14]
0x1800059b8  jmp     short loc_1800059E9
0x1800059ba  cmp     ebx, 0FFFFFFFFh
0x1800059bd  jz      short loc_180005978
0x1800059bf  test    ebx, ebx
0x1800059c1  js      loc_180005A7F
0x1800059c7  cmp     ebx, [rsi+18h]
0x1800059ca  jge     loc_180005A7F
0x1800059d0  movsxd  rcx, ebx
0x1800059d3  mov     rax, [rsi+10h]
0x1800059d7  mov     rbx, [rax+rcx*8]
0x1800059db  jmp     short loc_18000597B
0x1800059dd  mov     rcx, rax; lpsz
0x1800059e0  call    cs:__imp_CharNextW
0x1800059e6  mov     [r14], rax
0x1800059e9  cmp     rax, rdi
0x1800059ec  jnz     short loc_1800059DD
0x1800059ee  jmp     short loc_180005A06
0x1800059f0  mov     rdx, rbx; unsigned __int16 *
0x1800059f3  mov     r8d, 1; int
0x1800059f9  lea     rcx, [rbp+57h+var_A0]; this
0x1800059fd  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005a02  test    eax, eax
0x180005a04  jz      short loc_180005A4C
0x180005a06  mov     rcx, [r14]; lpsz
0x180005a09  call    cs:__imp_CharNextW
0x180005a0f  mov     rbx, rax
0x180005a12  mov     [r14], rax
0x180005a15  movzx   eax, word ptr [rax]
0x180005a18  test    ax, ax
0x180005a1b  jnz     loc_180005897
0x180005a21  mov     rdx, [rbp+57h+pv]
0x180005a25  mov     ebx, r13d
0x180005a28  mov     [rbp+57h+pv], r13
0x180005a2c  mov     [r12], rdx
0x180005a30  mov     rcx, [rbp+57h+pv]; pv
0x180005a34  call    cs:__imp_CoTaskMemFree
0x180005a3a  mov     eax, ebx
0x180005a3c  jmp     short loc_180005A58
0x180005a3e  mov     ebx, 80004005h
0x180005a43  jmp     short loc_180005A30
0x180005a45  mov     ebx, 80020009h
0x180005a4a  jmp     short loc_180005A30
0x180005a4c  mov     ebx, 8007000Eh
0x180005a51  jmp     short loc_180005A30
0x180005a53  mov     eax, 80004003h
0x180005a58  mov     rcx, [rbp+57h+var_40]
0x180005a5c  xor     rcx, rsp; StackCookie
0x180005a5f  call    __security_check_cookie
0x180005a64  mov     rbx, [rsp+0C0h+arg_8]
0x180005a6c  add     rsp, 90h
0x180005a73  pop     r15
0x180005a75  pop     r14
0x180005a77  pop     r13
0x180005a79  pop     r12
0x180005a7b  pop     rdi
0x180005a7c  pop     rsi
0x180005a7d  pop     rbp
0x180005a7e  retn
0x180005a7f  mov     ecx, 0C000008Ch; unsigned int
0x180005a84  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180005a89  int     3; Trap to Debugger
0x180005a8a  mov     ecx, 80004005h; int
0x180005a8f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005a95  mov     ecx, 80070057h; int
0x180005a9a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005aa0  mov     ecx, 8007000Eh; int
0x180005aa5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
