# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180005310`
- end: `0x18000551f`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `527`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800044a8`
- `0x18000487c`

## callees

- `0x180005310`
- `0x1800067dc`
- `0x1800095c4`
- `0x180009f0c`
- `0x18000b3b8`
- `0x18000b3c8`
- `0x18000f5f0`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800053d4`
- `KERNEL32!CreateSemaphoreExW` at `0x180005479`
- `KERNEL32!CreateSemaphoreExW` at `0x1800053d4`
- `KERNEL32!CreateSemaphoreExW` at `0x180005479`
- `KERNEL32!CloseHandle` at `0x180005423`
- `KERNEL32!CloseHandle` at `0x1800054b6`
- `KERNEL32!CloseHandle` at `0x180005423`
- `KERNEL32!CloseHandle` at `0x1800054b6`
- `KERNEL32!SetLastError` at `0x18000543c`
- `KERNEL32!SetLastError` at `0x1800054ca`
- `KERNEL32!SetLastError` at `0x18000543c`
- `KERNEL32!SetLastError` at `0x1800054ca`
- `KERNEL32!GetLastError` at `0x180005409`
- `KERNEL32!GetLastError` at `0x180005417`
- `KERNEL32!GetLastError` at `0x18000549c`
- `KERNEL32!GetLastError` at `0x1800054ab`
- `KERNEL32!GetLastError` at `0x180005409`
- `KERNEL32!GetLastError` at `0x180005417`
- `KERNEL32!GetLastError` at `0x18000549c`
- `KERNEL32!GetLastError` at `0x1800054ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rax
  LONG v10; // esi
  WCHAR v11; // r9
  WCHAR *v12; // rcx
  LONG v13; // r8d
  wil::details *v14; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v16; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  void *v21; // rbx
  DWORD LastError; // r14d
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned __int64 v25; // rbp
  wil::details *v26; // rcx
  HANDLE v27; // rsi
  void *v28; // rbx
  DWORD v29; // ebp
  unsigned int v30; // r8d
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = 2147483646;
  v8 = 260;
  v9 = Name;
  v10 = 1;
  do
  {
    if ( !v7 )
      break;
    v11 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v9++ = v11;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  StringCchCatW(Name, v8, L"_p0");
  v13 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v13 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v13, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v21 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v25 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v25 )
    v10 = v25;
  v27 = CreateSemaphoreExW(0, v25, v10, Name, 0, 0x1F0003u);
  if ( v27 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v27;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005310  mov     [rsp+arg_8], rbx
0x180005315  mov     [rsp+arg_10], rbp
0x18000531a  push    rsi
0x18000531b  push    rdi
0x18000531c  push    r12
0x18000531e  push    r14
0x180005320  push    r15
0x180005322  sub     rsp, 250h
0x180005329  mov     rax, cs:__security_cookie
0x180005330  xor     rax, rsp
0x180005333  mov     [rsp+278h+var_38], rax
0x18000533b  mov     rbp, r9
0x18000533e  mov     r8, rdx
0x180005341  mov     rdi, rcx
0x180005344  mov     rax, 0C000000000000000h
0x18000534e  test    rax, r9
0x180005351  jnz     loc_18000550E
0x180005357  mov     ecx, 7FFFFFFEh
0x18000535c  mov     edx, 104h
0x180005361  lea     rax, [rsp+278h+Name]
0x180005366  xor     r12d, r12d
0x180005369  lea     esi, [r12+1]
0x18000536e  test    rcx, rcx
0x180005371  jz      short loc_180005391
0x180005373  movzx   r9d, word ptr [r8]
0x180005377  test    r9w, r9w
0x18000537b  jz      short loc_180005391
0x18000537d  add     r8, 2
0x180005381  mov     [rax], r9w
0x180005385  add     rax, 2
0x180005389  sub     rcx, rsi
0x18000538c  sub     rdx, rsi; unsigned __int64
0x18000538f  jnz     short loc_18000536E
0x180005391  lea     rcx, [rax-2]
0x180005395  test    rdx, rdx
0x180005398  cmovnz  rcx, rax
0x18000539c  mov     [rcx], r12w
0x1800053a0  lea     r8, aP0; "_p0"
0x1800053a7  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800053ac  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800053b1  mov     edx, ebp
0x1800053b3  and     edx, 7FFFFFFFh; lInitialCount
0x1800053b9  mov     r8d, esi
0x1800053bc  cmova   r8d, edx; lMaximumCount
0x1800053c0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800053c8  mov     [rsp+278h+dwFlags], r12d; int
0x1800053cd  lea     r9, [rsp+278h+Name]; lpName
0x1800053d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800053d4  call    cs:__imp_CreateSemaphoreExW
0x1800053da  mov     r15, rax
0x1800053dd  test    rax, rax
0x1800053e0  jnz     short loc_180005409
0x1800053e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800053e7  mov     ebx, eax
0x1800053e9  test    eax, eax
0x1800053eb  jns     short loc_180005446
0x1800053ed  mov     edx, 8Bh; void *
0x1800053f2  mov     r9d, ebx; char *
0x1800053f5  mov     rcx, [rsp+278h]; this
0x1800053fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005402  mov     eax, ebx
0x180005404  jmp     loc_1800054D7
0x180005409  call    cs:__imp_GetLastError
0x18000540f  mov     rbx, [rdi]
0x180005412  test    rbx, rbx
0x180005415  jz      short loc_180005443
0x180005417  call    cs:__imp_GetLastError
0x18000541d  mov     r14d, eax
0x180005420  mov     rcx, rbx; hObject
0x180005423  call    cs:__imp_CloseHandle
0x180005429  mov     rcx, [rsp+278h]; this
0x180005431  test    eax, eax
0x180005433  jz      loc_180005514
0x180005439  mov     ecx, r14d; dwErrCode
0x18000543c  call    cs:__imp_SetLastError
0x180005442  nop
0x180005443  mov     [rdi], r15
0x180005446  shr     rbp, 1Fh
0x18000544a  lea     r8, asc_180013090; "h"
0x180005451  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180005456  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000545b  test    ebp, ebp
0x18000545d  cmovnz  esi, ebp
0x180005460  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005468  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000546d  lea     r9, [rsp+278h+Name]; lpName
0x180005472  mov     r8d, esi; lMaximumCount
0x180005475  mov     edx, ebp; lInitialCount
0x180005477  xor     ecx, ecx; lpSemaphoreAttributes
0x180005479  call    cs:__imp_CreateSemaphoreExW
0x18000547f  mov     rsi, rax
0x180005482  test    rax, rax
0x180005485  jnz     short loc_18000549C
0x180005487  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000548c  mov     ebx, eax
0x18000548e  test    eax, eax
0x180005490  jns     short loc_1800054D5
0x180005492  mov     edx, 90h
0x180005497  jmp     loc_1800053F2
0x18000549c  call    cs:__imp_GetLastError
0x1800054a2  mov     rbx, [rdi+8]
0x1800054a6  test    rbx, rbx
0x1800054a9  jz      short loc_1800054D1
0x1800054ab  call    cs:__imp_GetLastError
0x1800054b1  mov     ebp, eax
0x1800054b3  mov     rcx, rbx; hObject
0x1800054b6  call    cs:__imp_CloseHandle
0x1800054bc  mov     rcx, [rsp+278h]; this
0x1800054c4  test    eax, eax
0x1800054c6  jz      short loc_180005503
0x1800054c8  mov     ecx, ebp; dwErrCode
0x1800054ca  call    cs:__imp_SetLastError
0x1800054d0  nop
0x1800054d1  mov     [rdi+8], rsi
0x1800054d5  xor     eax, eax
0x1800054d7  mov     rcx, [rsp+278h+var_38]
0x1800054df  xor     rcx, rsp; StackCookie
0x1800054e2  call    __security_check_cookie
0x1800054e7  lea     r11, [rsp+278h+var_28]
0x1800054ef  mov     rbx, [r11+38h]
0x1800054f3  mov     rbp, [r11+40h]
0x1800054f7  mov     rsp, r11
0x1800054fa  pop     r15
0x1800054fc  pop     r14
0x1800054fe  pop     r12
0x180005500  pop     rdi
0x180005501  pop     rsi
0x180005502  retn
0x180005503  mov     edx, 0A0Bh; void *
0x180005508  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000550e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005514  mov     edx, 0A0Bh; void *
0x180005519  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
