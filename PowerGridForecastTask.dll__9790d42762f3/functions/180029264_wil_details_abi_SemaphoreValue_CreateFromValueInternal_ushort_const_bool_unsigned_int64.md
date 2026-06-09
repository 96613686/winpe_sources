# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180029264`
- end: `0x18002948e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180028a60`
- `0x180028e30`

## callees

- `0x180029264`
- `0x18002aaa8`
- `0x18002dcd4`
- `0x18002ed40`
- `0x18002febc`
- `0x18002fecc`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002937e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002941e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002937e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002941e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029364`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029413`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002938f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002942a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002938f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002942a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180029328`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800293cb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180029328`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800293cb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  __int64 v30; // r8
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
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
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v17 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
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
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v26,
        dwFlagsa);
      return v27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029264  mov     [rsp+arg_8], rbx
0x180029269  mov     [rsp+arg_10], rbp
0x18002926e  push    rsi
0x18002926f  push    rdi
0x180029270  push    r12
0x180029272  push    r14
0x180029274  push    r15
0x180029276  sub     rsp, 250h
0x18002927d  mov     rax, cs:__security_cookie
0x180029284  xor     rax, rsp
0x180029287  mov     [rsp+278h+var_38], rax
0x18002928f  mov     rax, 0C000000000000000h
0x180029299  mov     rbp, r9
0x18002929c  mov     r8, rdx
0x18002929f  mov     rbx, rcx
0x1800292a2  test    rax, r9
0x1800292a5  jnz     loc_180029475
0x1800292ab  xor     r12d, r12d
0x1800292ae  lea     rax, [rsp+278h+Name]
0x1800292b3  mov     ecx, 7FFFFFFEh
0x1800292b8  mov     edx, 104h
0x1800292bd  lea     esi, [r12+1]
0x1800292c2  test    rcx, rcx
0x1800292c5  jz      short loc_1800292E5
0x1800292c7  movzx   r9d, word ptr [r8]
0x1800292cb  test    r9w, r9w
0x1800292cf  jz      short loc_1800292E5
0x1800292d1  mov     [rax], r9w
0x1800292d5  add     r8, 2
0x1800292d9  add     rax, 2
0x1800292dd  sub     rcx, rsi
0x1800292e0  sub     rdx, rsi; unsigned __int64
0x1800292e3  jnz     short loc_1800292C2
0x1800292e5  test    rdx, rdx
0x1800292e8  lea     rcx, [rax-2]
0x1800292ec  lea     r8, aP0; "_p0"
0x1800292f3  cmovnz  rcx, rax
0x1800292f7  mov     [rcx], r12w
0x1800292fb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180029300  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029305  mov     edx, ebp
0x180029307  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002930f  and     edx, 7FFFFFFFh; lInitialCount
0x180029315  mov     [rsp+278h+dwFlags], r12d; int
0x18002931a  mov     r8d, esi
0x18002931d  lea     r9, [rsp+278h+Name]; lpName
0x180029322  cmova   r8d, edx; lMaximumCount
0x180029326  xor     ecx, ecx; lpSemaphoreAttributes
0x180029328  call    cs:__imp_CreateSemaphoreExW
0x18002932e  mov     r15, rax
0x180029331  test    rax, rax
0x180029334  jnz     short loc_180029364
0x180029336  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002933b  mov     edi, eax
0x18002933d  test    eax, eax
0x18002933f  jns     short loc_180029398
0x180029341  mov     rcx, [rsp+278h]; this
0x180029349  lea     r8, aWil; "wil"
0x180029350  mov     r9d, eax; char *
0x180029353  mov     edx, 8Bh; void *
0x180029358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002935d  mov     eax, edi
0x18002935f  jmp     loc_180029436
0x180029364  call    cs:__imp_GetLastError
0x18002936a  mov     rdi, [rbx]
0x18002936d  test    rdi, rdi
0x180029370  jz      short loc_180029395
0x180029372  call    cs:__imp_GetLastError
0x180029378  mov     rcx, rdi; hObject
0x18002937b  mov     r14d, eax
0x18002937e  call    cs:__imp_CloseHandle
0x180029384  test    eax, eax
0x180029386  jz      loc_18002947B
0x18002938c  mov     ecx, r14d; dwErrCode
0x18002938f  call    cs:__imp_SetLastError
0x180029395  mov     [rbx], r15
0x180029398  lea     r8, asc_18003D418; "h"
0x18002939f  shr     rbp, 1Fh
0x1800293a3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800293a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800293ad  test    ebp, ebp
0x1800293af  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800293b7  lea     r9, [rsp+278h+Name]; lpName
0x1800293bc  mov     [rsp+278h+dwFlags], r12d; int
0x1800293c1  cmovnz  esi, ebp
0x1800293c4  mov     edx, ebp; lInitialCount
0x1800293c6  mov     r8d, esi; lMaximumCount
0x1800293c9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800293cb  call    cs:__imp_CreateSemaphoreExW
0x1800293d1  mov     rsi, rax
0x1800293d4  test    rax, rax
0x1800293d7  jnz     short loc_180029404
0x1800293d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800293de  mov     ebx, eax
0x1800293e0  test    eax, eax
0x1800293e2  jns     short loc_180029434
0x1800293e4  mov     rcx, [rsp+278h]; this
0x1800293ec  lea     r8, aWil; "wil"
0x1800293f3  mov     r9d, eax; char *
0x1800293f6  mov     edx, 90h; void *
0x1800293fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029400  mov     eax, ebx
0x180029402  jmp     short loc_180029436
0x180029404  call    cs:__imp_GetLastError
0x18002940a  mov     rdi, [rbx+8]
0x18002940e  test    rdi, rdi
0x180029411  jz      short loc_180029430
0x180029413  call    cs:__imp_GetLastError
0x180029419  mov     rcx, rdi; hObject
0x18002941c  mov     ebp, eax
0x18002941e  call    cs:__imp_CloseHandle
0x180029424  test    eax, eax
0x180029426  jz      short loc_180029462
0x180029428  mov     ecx, ebp; dwErrCode
0x18002942a  call    cs:__imp_SetLastError
0x180029430  mov     [rbx+8], rsi
0x180029434  xor     eax, eax
0x180029436  mov     rcx, [rsp+278h+var_38]
0x18002943e  xor     rcx, rsp; StackCookie
0x180029441  call    __security_check_cookie
0x180029446  lea     r11, [rsp+278h+var_28]
0x18002944e  mov     rbx, [r11+38h]
0x180029452  mov     rbp, [r11+40h]
0x180029456  mov     rsp, r11
0x180029459  pop     r15
0x18002945b  pop     r14
0x18002945d  pop     r12
0x18002945f  pop     rdi
0x180029460  pop     rsi
0x180029461  retn
0x180029462  mov     rcx, [rsp+278h]; this
0x18002946a  mov     edx, 0A0Bh; void *
0x18002946f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029475  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002947b  mov     rcx, [rsp+278h]; this
0x180029483  mov     edx, 0A0Bh; void *
0x180029488  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
