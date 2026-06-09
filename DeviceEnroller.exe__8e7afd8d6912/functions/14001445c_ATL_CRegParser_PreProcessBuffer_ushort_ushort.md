# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x14001445c`
- end: `0x140014737`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140016420`

## callees

- `0x1400042f0`
- `0x140009140`
- `0x14000e410`
- `0x14000e548`
- `0x14001445c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001459f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14001459f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400145d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400145d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001460b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001460b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014530`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014561`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001466c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014695`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014530`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014561`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001466c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140014695`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400145f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400145f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400146c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400146c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400144e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400144e6`

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
  int v21; // edx
  unsigned int v22; // r8d
  const unsigned __int16 *v23; // rbx
  __int64 v24; // r8
  const WCHAR *i; // rax
  unsigned int v26; // ebx
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h]
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
  v27[0] = 0;
  v27[1] = v7;
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
    v26 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v15, 1) )
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
    v26 = -2147467259;
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
    v23 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v21, v22);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v23 )
  {
LABEL_54:
    v26 = -2147352567;
    goto LABEL_52;
  }
  v29 = 0;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v23, v24) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v26 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v26;
}

```

## disassembly

```asm
0x14001445c  mov     [rsp-8+arg_8], rbx
0x140014461  push    rbp
0x140014462  push    rsi
0x140014463  push    rdi
0x140014464  push    r12
0x140014466  push    r13
0x140014468  push    r14
0x14001446a  push    r15
0x14001446c  lea     rbp, [rsp-27h]
0x140014471  sub     rsp, 90h
0x140014478  mov     rax, cs:__security_cookie
0x14001447f  xor     rax, rsp
0x140014482  mov     [rbp+57h+var_40], rax
0x140014486  mov     r12, r8
0x140014489  mov     rbx, rdx
0x14001448c  mov     r14, rcx
0x14001448f  xor     r13d, r13d
0x140014492  test    rdx, rdx
0x140014495  jz      loc_1400146DF
0x14001449b  test    r8, r8
0x14001449e  jz      loc_1400146DF
0x1400144a4  mov     [r8], r13
0x1400144a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400144ab  inc     rax
0x1400144ae  cmp     [rdx+rax*2], r13w
0x1400144b3  jnz     short loc_1400144AB
0x1400144b5  add     eax, eax
0x1400144b7  mov     ecx, 3E8h
0x1400144bc  cmp     eax, 64h ; 'd'
0x1400144bf  cmovl   eax, ecx
0x1400144c2  mov     [rbp+57h+var_A0], r13d
0x1400144c6  mov     [rbp+57h+var_9C], eax
0x1400144c9  mov     ecx, eax
0x1400144cb  add     rcx, rcx
0x1400144ce  mov     eax, 0FFFFFFFFh
0x1400144d3  cmp     rcx, rax
0x1400144d6  jbe     short loc_1400144E4
0x1400144d8  mov     rax, r13
0x1400144db  mov     rdx, r13
0x1400144de  mov     [rbp+57h+pv], rdx
0x1400144e2  jmp     short loc_1400144FC
0x1400144e4  mov     ecx, ecx; cb
0x1400144e6  call    cs:__imp_CoTaskMemAlloc
0x1400144ec  mov     rdx, rax
0x1400144ef  mov     [rbp+57h+pv], rax
0x1400144f3  test    rax, rax
0x1400144f6  jz      short loc_1400144FC
0x1400144f8  mov     [rax], r13w
0x1400144fc  test    rax, rax
0x1400144ff  jnz     short loc_140014514
0x140014501  mov     rcx, rax; pv
0x140014504  call    cs:__imp_CoTaskMemFree
0x14001450a  mov     eax, 8007000Eh
0x14001450f  jmp     loc_1400146E4
0x140014514  mov     [r14], rbx
0x140014517  movzx   eax, word ptr [rbx]
0x14001451a  test    ax, ax
0x14001451d  jz      loc_1400146B1
0x140014523  cmp     ax, 25h ; '%'
0x140014527  jnz     loc_14001467C
0x14001452d  mov     rcx, rbx; lpsz
0x140014530  call    cs:__imp_CharNextW
0x140014536  mov     [r14], rax
0x140014539  movzx   ecx, word ptr [rax]
0x14001453c  cmp     cx, 25h ; '%'
0x140014540  jnz     short loc_14001454A
0x140014542  mov     rdx, rax
0x140014545  jmp     loc_14001467F
0x14001454a  test    rax, rax
0x14001454d  jz      loc_1400146D1
0x140014553  mov     rdi, r13
0x140014556  jmp     short loc_14001456A
0x140014558  cmp     cx, 25h ; '%'
0x14001455c  jz      short loc_140014571
0x14001455e  mov     rcx, rax; lpsz
0x140014561  call    cs:__imp_CharNextW
0x140014567  movzx   ecx, word ptr [rax]
0x14001456a  test    cx, cx
0x14001456d  jnz     short loc_140014558
0x14001456f  jmp     short loc_140014574
0x140014571  mov     rdi, rax
0x140014574  test    rdi, rdi
0x140014577  jz      loc_1400146D1
0x14001457d  mov     rax, rdi
0x140014580  sub     rax, [r14]
0x140014583  sar     rax, 1
0x140014586  cmp     rax, 1Fh
0x14001458a  jg      loc_1400146CA
0x140014590  movsxd  r9, eax
0x140014593  mov     r8, [r14]
0x140014596  mov     edx, 20h ; ' '
0x14001459b  lea     rcx, [rbp+57h+String2]
0x14001459f  call    cs:__imp__o_wcsncpy_s
0x1400145a5  test    eax, eax
0x1400145a7  jz      short loc_1400145CD
0x1400145a9  cmp     eax, 0Ch
0x1400145ac  jz      loc_14001472C
0x1400145b2  cmp     eax, 16h
0x1400145b5  jz      loc_140014721
0x1400145bb  cmp     eax, 22h ; '"'
0x1400145be  jz      loc_140014721
0x1400145c4  cmp     eax, 50h ; 'P'
0x1400145c7  jnz     loc_140014716
0x1400145cd  mov     rsi, [r14+8]
0x1400145d1  lea     rcx, [rsi+20h]; lpCriticalSection
0x1400145d5  call    cs:__imp_EnterCriticalSection
0x1400145db  mov     ebx, r13d
0x1400145de  cmp     [rsi+18h], r13d
0x1400145e2  jle     short loc_140014604
0x1400145e4  movsxd  rax, ebx
0x1400145e7  mov     rcx, [rsi+8]
0x1400145eb  lea     rdx, [rbp+57h+String2]; lpString2
0x1400145ef  mov     rcx, [rcx+rax*8]; lpString1
0x1400145f3  call    cs:__imp_lstrcmpiW
0x1400145f9  test    eax, eax
0x1400145fb  jz      short loc_140014646
0x1400145fd  inc     ebx
0x1400145ff  cmp     ebx, [rsi+18h]
0x140014602  jl      short loc_1400145E4
0x140014604  mov     rbx, r13
0x140014607  lea     rcx, [rsi+20h]; lpCriticalSection
0x14001460b  call    cs:__imp_LeaveCriticalSection
0x140014611  test    rbx, rbx
0x140014614  jz      loc_1400146D1
0x14001461a  mov     [rbp+57h+var_90], r13
0x14001461e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140014622  inc     r8; int
0x140014625  cmp     [rbx+r8*2], r13w
0x14001462a  jnz     short loc_140014622
0x14001462c  mov     rdx, rbx; unsigned __int16 *
0x14001462f  lea     rcx, [rbp+57h+var_A0]; this
0x140014633  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140014638  nop
0x140014639  test    eax, eax
0x14001463b  jz      loc_1400146D8
0x140014641  mov     rax, [r14]
0x140014644  jmp     short loc_140014675
0x140014646  cmp     ebx, 0FFFFFFFFh
0x140014649  jz      short loc_140014604
0x14001464b  test    ebx, ebx
0x14001464d  js      loc_14001470B
0x140014653  cmp     ebx, [rsi+18h]
0x140014656  jge     loc_14001470B
0x14001465c  movsxd  rcx, ebx
0x14001465f  mov     rax, [rsi+10h]
0x140014663  mov     rbx, [rax+rcx*8]
0x140014667  jmp     short loc_140014607
0x140014669  mov     rcx, rax; lpsz
0x14001466c  call    cs:__imp_CharNextW
0x140014672  mov     [r14], rax
0x140014675  cmp     rax, rdi
0x140014678  jnz     short loc_140014669
0x14001467a  jmp     short loc_140014692
0x14001467c  mov     rdx, rbx; unsigned __int16 *
0x14001467f  mov     r8d, 1; int
0x140014685  lea     rcx, [rbp+57h+var_A0]; this
0x140014689  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14001468e  test    eax, eax
0x140014690  jz      short loc_1400146D8
0x140014692  mov     rcx, [r14]; lpsz
0x140014695  call    cs:__imp_CharNextW
0x14001469b  mov     rbx, rax
0x14001469e  mov     [r14], rax
0x1400146a1  movzx   eax, word ptr [rax]
0x1400146a4  test    ax, ax
0x1400146a7  jnz     loc_140014523
0x1400146ad  mov     rdx, [rbp+57h+pv]
0x1400146b1  mov     ebx, r13d
0x1400146b4  mov     [rbp+57h+pv], r13
0x1400146b8  mov     [r12], rdx
0x1400146bc  mov     rcx, [rbp+57h+pv]; pv
0x1400146c0  call    cs:__imp_CoTaskMemFree
0x1400146c6  mov     eax, ebx
0x1400146c8  jmp     short loc_1400146E4
0x1400146ca  mov     ebx, 80004005h
0x1400146cf  jmp     short loc_1400146BC
0x1400146d1  mov     ebx, 80020009h
0x1400146d6  jmp     short loc_1400146BC
0x1400146d8  mov     ebx, 8007000Eh
0x1400146dd  jmp     short loc_1400146BC
0x1400146df  mov     eax, 80004003h
0x1400146e4  mov     rcx, [rbp+57h+var_40]
0x1400146e8  xor     rcx, rsp; StackCookie
0x1400146eb  call    __security_check_cookie
0x1400146f0  mov     rbx, [rsp+0C0h+arg_8]
0x1400146f8  add     rsp, 90h
0x1400146ff  pop     r15
0x140014701  pop     r14
0x140014703  pop     r13
0x140014705  pop     r12
0x140014707  pop     rdi
0x140014708  pop     rsi
0x140014709  pop     rbp
0x14001470a  retn
0x14001470b  mov     ecx, 0C000008Ch; this
0x140014710  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140014715  int     3; Trap to Debugger
0x140014716  mov     ecx, 80004005h; int
0x14001471b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140014721  mov     ecx, 80070057h; int
0x140014726  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001472c  mov     ecx, 8007000Eh; int
0x140014731  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
