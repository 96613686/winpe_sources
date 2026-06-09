# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000729c`
- end: `0x18000756a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800078f8`

## callees

- `0x18000604c`
- `0x180006764`
- `0x18000729c`
- `0x180008f7c`
- `0x180012e00`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800073d0`
- `msvcrt!wcsncpy_s` at `0x1800073d0`
- `KERNEL32!lstrcmpiW` at `0x180007425`
- `KERNEL32!lstrcmpiW` at `0x180007425`
- `KERNEL32!LeaveCriticalSection` at `0x18000743d`
- `KERNEL32!LeaveCriticalSection` at `0x18000743d`
- `KERNEL32!EnterCriticalSection` at `0x180007406`
- `KERNEL32!EnterCriticalSection` at `0x180007406`
- `ole32!CoTaskMemAlloc` at `0x18000732d`
- `ole32!CoTaskMemAlloc` at `0x18000732d`
- `ole32!CoTaskMemFree` at `0x18000731b`
- `ole32!CoTaskMemFree` at `0x1800074f1`
- `ole32!CoTaskMemFree` at `0x18000731b`
- `ole32!CoTaskMemFree` at `0x1800074f1`
- `USER32!CharNextW` at `0x180007360`
- `USER32!CharNextW` at `0x180007391`
- `USER32!CharNextW` at `0x18000749a`
- `USER32!CharNextW` at `0x1800074c4`
- `USER32!CharNextW` at `0x180007360`
- `USER32!CharNextW` at `0x180007391`
- `USER32!CharNextW` at `0x18000749a`
- `USER32!CharNextW` at `0x1800074c4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_49:
    v25 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_53;
LABEL_47:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_49;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_46;
  }
  if ( !v13 )
    goto LABEL_52;
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
    goto LABEL_52;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_50;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
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
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
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
LABEL_52:
    v25 = -2147352567;
    goto LABEL_50;
  }
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v25 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x18000729c  mov     [rsp+arg_8], rbx
0x1800072a1  mov     [rsp+arg_18], rbp
0x1800072a6  push    rsi
0x1800072a7  push    rdi
0x1800072a8  push    r12
0x1800072aa  push    r14
0x1800072ac  push    r15
0x1800072ae  sub     rsp, 80h
0x1800072b5  mov     rax, cs:__security_cookie
0x1800072bc  xor     rax, rsp
0x1800072bf  mov     [rsp+0A8h+var_38], rax
0x1800072c4  xor     r12d, r12d
0x1800072c7  mov     r15, r8
0x1800072ca  mov     rbx, rdx
0x1800072cd  mov     r14, rcx
0x1800072d0  test    rdx, rdx
0x1800072d3  jz      loc_180007510
0x1800072d9  test    r8, r8
0x1800072dc  jz      loc_180007510
0x1800072e2  mov     [r8], r12
0x1800072e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800072e9  inc     rax
0x1800072ec  cmp     [rdx+rax*2], r12w
0x1800072f1  jnz     short loc_1800072E9
0x1800072f3  add     eax, eax
0x1800072f5  mov     [rsp+0A8h+var_88], r12d
0x1800072fa  cmp     eax, 64h ; 'd'
0x1800072fd  mov     ecx, 3E8h
0x180007302  cmovl   eax, ecx
0x180007305  mov     ecx, eax
0x180007307  mov     [rsp+0A8h+var_84], eax
0x18000730b  add     rcx, rcx
0x18000730e  mov     eax, 0FFFFFFFFh
0x180007313  cmp     rcx, rax
0x180007316  jbe     short loc_18000732B
0x180007318  mov     rcx, r12; pv
0x18000731b  call    cs:__imp_CoTaskMemFree
0x180007321  mov     eax, 8007000Eh
0x180007326  jmp     loc_180007515
0x18000732b  mov     ecx, ecx; cb
0x18000732d  call    cs:__imp_CoTaskMemAlloc
0x180007333  mov     [rsp+0A8h+pv], rax
0x180007338  mov     rcx, rax
0x18000733b  test    rax, rax
0x18000733e  jz      short loc_18000731B
0x180007340  mov     [rax], r12w
0x180007344  mov     [r14], rbx
0x180007347  movzx   eax, word ptr [rbx]
0x18000734a  test    ax, ax
0x18000734d  jz      loc_1800074E1
0x180007353  cmp     ax, 25h ; '%'
0x180007357  jnz     loc_1800074AA
0x18000735d  mov     rcx, rbx; lpsz
0x180007360  call    cs:__imp_CharNextW
0x180007366  mov     [r14], rax
0x180007369  movzx   ecx, word ptr [rax]
0x18000736c  cmp     cx, 25h ; '%'
0x180007370  jnz     short loc_18000737A
0x180007372  mov     rdx, rax
0x180007375  jmp     loc_1800074AD
0x18000737a  test    rax, rax
0x18000737d  jz      loc_180007502
0x180007383  mov     rdi, r12
0x180007386  jmp     short loc_18000739A
0x180007388  cmp     cx, 25h ; '%'
0x18000738c  jz      short loc_1800073A1
0x18000738e  mov     rcx, rax; lpsz
0x180007391  call    cs:__imp_CharNextW
0x180007397  movzx   ecx, word ptr [rax]
0x18000739a  test    cx, cx
0x18000739d  jnz     short loc_180007388
0x18000739f  jmp     short loc_1800073A4
0x1800073a1  mov     rdi, rax
0x1800073a4  test    rdi, rdi
0x1800073a7  jz      loc_180007502
0x1800073ad  mov     rax, rdi
0x1800073b0  sub     rax, [r14]
0x1800073b3  sar     rax, 1
0x1800073b6  cmp     rax, 1Fh
0x1800073ba  jg      loc_1800074FB
0x1800073c0  mov     r8, [r14]; Source
0x1800073c3  lea     rcx, [rsp+0A8h+Destination]; Destination
0x1800073c8  movsxd  r9, eax; MaxCount
0x1800073cb  mov     edx, 20h ; ' '; SizeInWords
0x1800073d0  call    cs:__imp_wcsncpy_s
0x1800073d6  test    eax, eax
0x1800073d8  jz      short loc_1800073FE
0x1800073da  cmp     eax, 0Ch
0x1800073dd  jz      loc_18000755F
0x1800073e3  cmp     eax, 16h
0x1800073e6  jz      loc_180007554
0x1800073ec  cmp     eax, 22h ; '"'
0x1800073ef  jz      loc_180007554
0x1800073f5  cmp     eax, 50h ; 'P'
0x1800073f8  jnz     loc_180007549
0x1800073fe  mov     rsi, [r14+8]
0x180007402  lea     rcx, [rsi+20h]; lpCriticalSection
0x180007406  call    cs:__imp_EnterCriticalSection
0x18000740c  mov     ebx, r12d
0x18000740f  cmp     [rsi+18h], r12d
0x180007413  jle     short loc_180007436
0x180007415  mov     rcx, [rsi+8]
0x180007419  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000741e  movsxd  rax, ebx
0x180007421  mov     rcx, [rcx+rax*8]; lpString1
0x180007425  call    cs:__imp_lstrcmpiW
0x18000742b  test    eax, eax
0x18000742d  jz      short loc_180007474
0x18000742f  inc     ebx
0x180007431  cmp     ebx, [rsi+18h]
0x180007434  jl      short loc_180007415
0x180007436  mov     rbx, r12
0x180007439  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000743d  call    cs:__imp_LeaveCriticalSection
0x180007443  test    rbx, rbx
0x180007446  jz      loc_180007502
0x18000744c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007450  inc     r8; int
0x180007453  cmp     [rbx+r8*2], r12w
0x180007458  jnz     short loc_180007450
0x18000745a  mov     rdx, rbx; unsigned __int16 *
0x18000745d  lea     rcx, [rsp+0A8h+var_88]; this
0x180007462  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007467  test    eax, eax
0x180007469  jz      loc_180007509
0x18000746f  mov     rax, [r14]
0x180007472  jmp     short loc_1800074A3
0x180007474  cmp     ebx, 0FFFFFFFFh
0x180007477  jz      short loc_180007436
0x180007479  test    ebx, ebx
0x18000747b  js      loc_18000753E
0x180007481  cmp     ebx, [rsi+18h]
0x180007484  jge     loc_18000753E
0x18000748a  mov     rax, [rsi+10h]
0x18000748e  movsxd  rcx, ebx
0x180007491  mov     rbx, [rax+rcx*8]
0x180007495  jmp     short loc_180007439
0x180007497  mov     rcx, rax; lpsz
0x18000749a  call    cs:__imp_CharNextW
0x1800074a0  mov     [r14], rax
0x1800074a3  cmp     rax, rdi
0x1800074a6  jnz     short loc_180007497
0x1800074a8  jmp     short loc_1800074C1
0x1800074aa  mov     rdx, rbx; unsigned __int16 *
0x1800074ad  mov     r8d, 1; int
0x1800074b3  lea     rcx, [rsp+0A8h+var_88]; this
0x1800074b8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800074bd  test    eax, eax
0x1800074bf  jz      short loc_180007509
0x1800074c1  mov     rcx, [r14]; lpsz
0x1800074c4  call    cs:__imp_CharNextW
0x1800074ca  mov     rbx, rax
0x1800074cd  mov     [r14], rax
0x1800074d0  movzx   eax, word ptr [rax]
0x1800074d3  test    ax, ax
0x1800074d6  jnz     loc_180007353
0x1800074dc  mov     rcx, [rsp+0A8h+pv]
0x1800074e1  mov     ebx, r12d
0x1800074e4  mov     [rsp+0A8h+pv], r12
0x1800074e9  mov     [r15], rcx
0x1800074ec  mov     rcx, [rsp+0A8h+pv]; pv
0x1800074f1  call    cs:__imp_CoTaskMemFree
0x1800074f7  mov     eax, ebx
0x1800074f9  jmp     short loc_180007515
0x1800074fb  mov     ebx, 80004005h
0x180007500  jmp     short loc_1800074EC
0x180007502  mov     ebx, 80020009h
0x180007507  jmp     short loc_1800074EC
0x180007509  mov     ebx, 8007000Eh
0x18000750e  jmp     short loc_1800074EC
0x180007510  mov     eax, 80004003h
0x180007515  mov     rcx, [rsp+0A8h+var_38]
0x18000751a  xor     rcx, rsp; StackCookie
0x18000751d  call    __security_check_cookie
0x180007522  lea     r11, [rsp+0A8h+var_28]
0x18000752a  mov     rbx, [r11+38h]
0x18000752e  mov     rbp, [r11+48h]
0x180007532  mov     rsp, r11
0x180007535  pop     r15
0x180007537  pop     r14
0x180007539  pop     r12
0x18000753b  pop     rdi
0x18000753c  pop     rsi
0x18000753d  retn
0x18000753e  mov     ecx, 0C000008Ch; unsigned int
0x180007543  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180007548  int     3; Trap to Debugger
0x180007549  mov     ecx, 80004005h; int
0x18000754e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007554  mov     ecx, 80070057h; int
0x180007559  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000755f  mov     ecx, 8007000Eh; int
0x180007564  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
