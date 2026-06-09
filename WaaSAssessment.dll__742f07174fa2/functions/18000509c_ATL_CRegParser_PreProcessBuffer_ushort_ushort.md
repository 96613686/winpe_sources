# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000509c`
- end: `0x180005377`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005528`

## callees

- `0x180003cac`
- `0x180004740`
- `0x18000509c`
- `0x1800069fc`
- `0x180019760`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800051df`
- `msvcrt!wcsncpy_s` at `0x1800051df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000524b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000524b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005126`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005170`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800051a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005170`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800051a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005233`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005233`

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
  errno_t v18; // eax
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
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v15, 1) )
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
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
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
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v23, v24) )
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
0x18000509c  mov     [rsp-8+arg_8], rbx
0x1800050a1  push    rbp
0x1800050a2  push    rsi
0x1800050a3  push    rdi
0x1800050a4  push    r12
0x1800050a6  push    r13
0x1800050a8  push    r14
0x1800050aa  push    r15
0x1800050ac  lea     rbp, [rsp-27h]
0x1800050b1  sub     rsp, 90h
0x1800050b8  mov     rax, cs:__security_cookie
0x1800050bf  xor     rax, rsp
0x1800050c2  mov     [rbp+57h+var_40], rax
0x1800050c6  mov     r12, r8
0x1800050c9  mov     rbx, rdx
0x1800050cc  mov     r14, rcx
0x1800050cf  xor     r13d, r13d
0x1800050d2  test    rdx, rdx
0x1800050d5  jz      loc_18000531F
0x1800050db  test    r8, r8
0x1800050de  jz      loc_18000531F
0x1800050e4  mov     [r8], r13
0x1800050e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800050eb  inc     rax
0x1800050ee  cmp     [rdx+rax*2], r13w
0x1800050f3  jnz     short loc_1800050EB
0x1800050f5  add     eax, eax
0x1800050f7  mov     ecx, 3E8h
0x1800050fc  cmp     eax, 64h ; 'd'
0x1800050ff  cmovl   eax, ecx
0x180005102  mov     [rbp+57h+var_A0], r13d
0x180005106  mov     [rbp+57h+var_9C], eax
0x180005109  mov     ecx, eax
0x18000510b  add     rcx, rcx
0x18000510e  mov     eax, 0FFFFFFFFh
0x180005113  cmp     rcx, rax
0x180005116  jbe     short loc_180005124
0x180005118  mov     rax, r13
0x18000511b  mov     rdx, r13
0x18000511e  mov     [rbp+57h+pv], rdx
0x180005122  jmp     short loc_18000513C
0x180005124  mov     ecx, ecx; cb
0x180005126  call    cs:__imp_CoTaskMemAlloc
0x18000512c  mov     rdx, rax
0x18000512f  mov     [rbp+57h+pv], rax
0x180005133  test    rax, rax
0x180005136  jz      short loc_18000513C
0x180005138  mov     [rax], r13w
0x18000513c  test    rax, rax
0x18000513f  jnz     short loc_180005154
0x180005141  mov     rcx, rax; pv
0x180005144  call    cs:__imp_CoTaskMemFree
0x18000514a  mov     eax, 8007000Eh
0x18000514f  jmp     loc_180005324
0x180005154  mov     [r14], rbx
0x180005157  movzx   eax, word ptr [rbx]
0x18000515a  test    ax, ax
0x18000515d  jz      loc_1800052F1
0x180005163  cmp     ax, 25h ; '%'
0x180005167  jnz     loc_1800052BC
0x18000516d  mov     rcx, rbx; lpsz
0x180005170  call    cs:__imp_CharNextW
0x180005176  mov     [r14], rax
0x180005179  movzx   ecx, word ptr [rax]
0x18000517c  cmp     cx, 25h ; '%'
0x180005180  jnz     short loc_18000518A
0x180005182  mov     rdx, rax
0x180005185  jmp     loc_1800052BF
0x18000518a  test    rax, rax
0x18000518d  jz      loc_180005311
0x180005193  mov     rdi, r13
0x180005196  jmp     short loc_1800051AA
0x180005198  cmp     cx, 25h ; '%'
0x18000519c  jz      short loc_1800051B1
0x18000519e  mov     rcx, rax; lpsz
0x1800051a1  call    cs:__imp_CharNextW
0x1800051a7  movzx   ecx, word ptr [rax]
0x1800051aa  test    cx, cx
0x1800051ad  jnz     short loc_180005198
0x1800051af  jmp     short loc_1800051B4
0x1800051b1  mov     rdi, rax
0x1800051b4  test    rdi, rdi
0x1800051b7  jz      loc_180005311
0x1800051bd  mov     rax, rdi
0x1800051c0  sub     rax, [r14]
0x1800051c3  sar     rax, 1
0x1800051c6  cmp     rax, 1Fh
0x1800051ca  jg      loc_18000530A
0x1800051d0  movsxd  r9, eax; MaxCount
0x1800051d3  mov     r8, [r14]; Source
0x1800051d6  mov     edx, 20h ; ' '; SizeInWords
0x1800051db  lea     rcx, [rbp+57h+Destination]; Destination
0x1800051df  call    cs:__imp_wcsncpy_s
0x1800051e5  test    eax, eax
0x1800051e7  jz      short loc_18000520D
0x1800051e9  cmp     eax, 0Ch
0x1800051ec  jz      loc_18000536C
0x1800051f2  cmp     eax, 16h
0x1800051f5  jz      loc_180005361
0x1800051fb  cmp     eax, 22h ; '"'
0x1800051fe  jz      loc_180005361
0x180005204  cmp     eax, 50h ; 'P'
0x180005207  jnz     loc_180005356
0x18000520d  mov     rsi, [r14+8]
0x180005211  lea     rcx, [rsi+20h]; lpCriticalSection
0x180005215  call    cs:__imp_EnterCriticalSection
0x18000521b  mov     ebx, r13d
0x18000521e  cmp     [rsi+18h], r13d
0x180005222  jle     short loc_180005244
0x180005224  movsxd  rax, ebx
0x180005227  mov     rcx, [rsi+8]
0x18000522b  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000522f  mov     rcx, [rcx+rax*8]; lpString1
0x180005233  call    cs:__imp_lstrcmpiW
0x180005239  test    eax, eax
0x18000523b  jz      short loc_180005286
0x18000523d  inc     ebx
0x18000523f  cmp     ebx, [rsi+18h]
0x180005242  jl      short loc_180005224
0x180005244  mov     rbx, r13
0x180005247  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000524b  call    cs:__imp_LeaveCriticalSection
0x180005251  test    rbx, rbx
0x180005254  jz      loc_180005311
0x18000525a  mov     [rbp+57h+var_90], r13
0x18000525e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005262  inc     r8; int
0x180005265  cmp     [rbx+r8*2], r13w
0x18000526a  jnz     short loc_180005262
0x18000526c  mov     rdx, rbx; unsigned __int16 *
0x18000526f  lea     rcx, [rbp+57h+var_A0]; this
0x180005273  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005278  nop
0x180005279  test    eax, eax
0x18000527b  jz      loc_180005318
0x180005281  mov     rax, [r14]
0x180005284  jmp     short loc_1800052B5
0x180005286  cmp     ebx, 0FFFFFFFFh
0x180005289  jz      short loc_180005244
0x18000528b  test    ebx, ebx
0x18000528d  js      loc_18000534B
0x180005293  cmp     ebx, [rsi+18h]
0x180005296  jge     loc_18000534B
0x18000529c  movsxd  rcx, ebx
0x18000529f  mov     rax, [rsi+10h]
0x1800052a3  mov     rbx, [rax+rcx*8]
0x1800052a7  jmp     short loc_180005247
0x1800052a9  mov     rcx, rax; lpsz
0x1800052ac  call    cs:__imp_CharNextW
0x1800052b2  mov     [r14], rax
0x1800052b5  cmp     rax, rdi
0x1800052b8  jnz     short loc_1800052A9
0x1800052ba  jmp     short loc_1800052D2
0x1800052bc  mov     rdx, rbx; unsigned __int16 *
0x1800052bf  mov     r8d, 1; int
0x1800052c5  lea     rcx, [rbp+57h+var_A0]; this
0x1800052c9  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800052ce  test    eax, eax
0x1800052d0  jz      short loc_180005318
0x1800052d2  mov     rcx, [r14]; lpsz
0x1800052d5  call    cs:__imp_CharNextW
0x1800052db  mov     rbx, rax
0x1800052de  mov     [r14], rax
0x1800052e1  movzx   eax, word ptr [rax]
0x1800052e4  test    ax, ax
0x1800052e7  jnz     loc_180005163
0x1800052ed  mov     rdx, [rbp+57h+pv]
0x1800052f1  mov     ebx, r13d
0x1800052f4  mov     [rbp+57h+pv], r13
0x1800052f8  mov     [r12], rdx
0x1800052fc  mov     rcx, [rbp+57h+pv]; pv
0x180005300  call    cs:__imp_CoTaskMemFree
0x180005306  mov     eax, ebx
0x180005308  jmp     short loc_180005324
0x18000530a  mov     ebx, 80004005h
0x18000530f  jmp     short loc_1800052FC
0x180005311  mov     ebx, 80020009h
0x180005316  jmp     short loc_1800052FC
0x180005318  mov     ebx, 8007000Eh
0x18000531d  jmp     short loc_1800052FC
0x18000531f  mov     eax, 80004003h
0x180005324  mov     rcx, [rbp+57h+var_40]
0x180005328  xor     rcx, rsp; StackCookie
0x18000532b  call    __security_check_cookie
0x180005330  mov     rbx, [rsp+0C0h+arg_8]
0x180005338  add     rsp, 90h
0x18000533f  pop     r15
0x180005341  pop     r14
0x180005343  pop     r13
0x180005345  pop     r12
0x180005347  pop     rdi
0x180005348  pop     rsi
0x180005349  pop     rbp
0x18000534a  retn
0x18000534b  mov     ecx, 0C000008Ch; this
0x180005350  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005355  int     3; Trap to Debugger
0x180005356  mov     ecx, 80004005h; int
0x18000535b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005361  mov     ecx, 80070057h; int
0x180005366  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000536c  mov     ecx, 8007000Eh; int
0x180005371  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
