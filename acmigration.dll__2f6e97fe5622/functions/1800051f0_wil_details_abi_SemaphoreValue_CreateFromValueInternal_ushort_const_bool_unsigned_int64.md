# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800051f0`
- end: `0x180005421`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004a28`
- `0x180004df8`

## callees

- `0x180001cf0`
- `0x1800051f0`
- `0x1800060a0`
- `0x1800085bc`
- `0x180009ccc`
- `0x180009cdc`
- `0x18000a51c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000530f`
- `KERNEL32!CloseHandle` at `0x1800053b2`
- `KERNEL32!CloseHandle` at `0x18000530f`
- `KERNEL32!CloseHandle` at `0x1800053b2`
- `KERNEL32!GetLastError` at `0x1800052f5`
- `KERNEL32!GetLastError` at `0x180005303`
- `KERNEL32!GetLastError` at `0x180005398`
- `KERNEL32!GetLastError` at `0x1800053a7`
- `KERNEL32!GetLastError` at `0x1800052f5`
- `KERNEL32!GetLastError` at `0x180005303`
- `KERNEL32!GetLastError` at `0x180005398`
- `KERNEL32!GetLastError` at `0x1800053a7`
- `KERNEL32!SetLastError` at `0x180005320`
- `KERNEL32!SetLastError` at `0x1800053be`
- `KERNEL32!SetLastError` at `0x180005320`
- `KERNEL32!SetLastError` at `0x1800053be`
- `KERNEL32!CreateSemaphoreExW` at `0x1800052b9`
- `KERNEL32!CreateSemaphoreExW` at `0x18000535f`
- `KERNEL32!CreateSemaphoreExW` at `0x1800052b9`
- `KERNEL32!CreateSemaphoreExW` at `0x18000535f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        wchar_t *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // ebp
  wchar_t *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  wchar_t pszDest[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = pszDest;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, pszDest, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(pszDest, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, pszDest, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800051f0  mov     [rsp+arg_8], rbx
0x1800051f5  push    rbp
0x1800051f6  push    rsi
0x1800051f7  push    rdi
0x1800051f8  push    r12
0x1800051fa  push    r13
0x1800051fc  push    r14
0x1800051fe  push    r15
0x180005200  sub     rsp, 250h
0x180005207  mov     rax, cs:__security_cookie
0x18000520e  xor     rax, rsp
0x180005211  mov     [rsp+288h+var_48], rax
0x180005219  mov     rax, 0C000000000000000h
0x180005223  mov     rsi, r9
0x180005226  mov     r8, rdx
0x180005229  mov     rbx, rcx
0x18000522c  test    rax, r9
0x18000522f  jnz     loc_180005408
0x180005235  xor     r12d, r12d
0x180005238  lea     rax, [rsp+288h+pszDest]
0x18000523d  mov     r13d, 104h
0x180005243  mov     ecx, 7FFFFFFEh
0x180005248  mov     edx, r13d
0x18000524b  lea     ebp, [r12+1]
0x180005250  test    rcx, rcx
0x180005253  jz      short loc_180005273
0x180005255  movzx   r9d, word ptr [r8]
0x180005259  test    r9w, r9w
0x18000525d  jz      short loc_180005273
0x18000525f  mov     [rax], r9w
0x180005263  add     r8, 2
0x180005267  add     rax, 2
0x18000526b  sub     rcx, rbp
0x18000526e  sub     rdx, rbp
0x180005271  jnz     short loc_180005250
0x180005273  test    rdx, rdx
0x180005276  lea     rcx, [rax-2]
0x18000527a  lea     r8, aP0; "_p0"
0x180005281  mov     rdx, r13; cchDest
0x180005284  cmovnz  rcx, rax
0x180005288  mov     [rcx], r12w
0x18000528c  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180005291  call    StringCchCatW
0x180005296  mov     edx, esi
0x180005298  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800052a0  and     edx, 7FFFFFFFh; lInitialCount
0x1800052a6  mov     [rsp+288h+dwFlags], r12d; int
0x1800052ab  mov     r8d, ebp
0x1800052ae  lea     r9, [rsp+288h+pszDest]; lpName
0x1800052b3  cmova   r8d, edx; lMaximumCount
0x1800052b7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800052b9  call    cs:__imp_CreateSemaphoreExW
0x1800052bf  mov     r15, rax
0x1800052c2  test    rax, rax
0x1800052c5  jnz     short loc_1800052F5
0x1800052c7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800052cc  mov     edi, eax
0x1800052ce  test    eax, eax
0x1800052d0  jns     short loc_180005329
0x1800052d2  mov     rcx, [rsp+288h]; this
0x1800052da  lea     r8, aWil; "wil"
0x1800052e1  mov     r9d, eax; char *
0x1800052e4  mov     edx, 8Bh; void *
0x1800052e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052ee  mov     eax, edi
0x1800052f0  jmp     loc_1800053CA
0x1800052f5  call    cs:__imp_GetLastError
0x1800052fb  mov     rdi, [rbx]
0x1800052fe  test    rdi, rdi
0x180005301  jz      short loc_180005326
0x180005303  call    cs:__imp_GetLastError
0x180005309  mov     rcx, rdi; hObject
0x18000530c  mov     r14d, eax
0x18000530f  call    cs:__imp_CloseHandle
0x180005315  test    eax, eax
0x180005317  jz      loc_18000540E
0x18000531d  mov     ecx, r14d; dwErrCode
0x180005320  call    cs:__imp_SetLastError
0x180005326  mov     [rbx], r15
0x180005329  lea     r8, asc_18006E308; "h"
0x180005330  shr     rsi, 1Fh
0x180005334  mov     rdx, r13; cchDest
0x180005337  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18000533c  call    StringCchCatW
0x180005341  test    esi, esi
0x180005343  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000534b  lea     r9, [rsp+288h+pszDest]; lpName
0x180005350  mov     [rsp+288h+dwFlags], r12d; int
0x180005355  cmovnz  ebp, esi
0x180005358  mov     edx, esi; lInitialCount
0x18000535a  mov     r8d, ebp; lMaximumCount
0x18000535d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000535f  call    cs:__imp_CreateSemaphoreExW
0x180005365  mov     rbp, rax
0x180005368  test    rax, rax
0x18000536b  jnz     short loc_180005398
0x18000536d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005372  mov     ebx, eax
0x180005374  test    eax, eax
0x180005376  jns     short loc_1800053C8
0x180005378  mov     rcx, [rsp+288h]; this
0x180005380  lea     r8, aWil; "wil"
0x180005387  mov     r9d, eax; char *
0x18000538a  mov     edx, 90h; void *
0x18000538f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005394  mov     eax, ebx
0x180005396  jmp     short loc_1800053CA
0x180005398  call    cs:__imp_GetLastError
0x18000539e  mov     rdi, [rbx+8]
0x1800053a2  test    rdi, rdi
0x1800053a5  jz      short loc_1800053C4
0x1800053a7  call    cs:__imp_GetLastError
0x1800053ad  mov     rcx, rdi; hObject
0x1800053b0  mov     esi, eax
0x1800053b2  call    cs:__imp_CloseHandle
0x1800053b8  test    eax, eax
0x1800053ba  jz      short loc_1800053F5
0x1800053bc  mov     ecx, esi; dwErrCode
0x1800053be  call    cs:__imp_SetLastError
0x1800053c4  mov     [rbx+8], rbp
0x1800053c8  xor     eax, eax
0x1800053ca  mov     rcx, [rsp+288h+var_48]
0x1800053d2  xor     rcx, rsp; StackCookie
0x1800053d5  call    __security_check_cookie
0x1800053da  mov     rbx, [rsp+288h+arg_8]
0x1800053e2  add     rsp, 250h
0x1800053e9  pop     r15
0x1800053eb  pop     r14
0x1800053ed  pop     r13
0x1800053ef  pop     r12
0x1800053f1  pop     rdi
0x1800053f2  pop     rsi
0x1800053f3  pop     rbp
0x1800053f4  retn
0x1800053f5  mov     rcx, [rsp+288h]; this
0x1800053fd  mov     edx, 0A0Bh; void *
0x180005402  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005408  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000540e  mov     rcx, [rsp+288h]; this
0x180005416  mov     edx, 0A0Bh; void *
0x18000541b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
