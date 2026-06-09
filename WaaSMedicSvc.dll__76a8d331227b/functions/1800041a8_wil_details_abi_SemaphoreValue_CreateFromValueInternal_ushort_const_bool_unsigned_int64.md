# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800041a8`
- end: `0x1800043d2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003dd8`

## callees

- `0x180002200`
- `0x1800041a8`
- `0x180004a38`
- `0x180005984`
- `0x180006260`
- `0x1800067cc`
- `0x1800067dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000426c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000430f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000426c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000430f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000436e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000436e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004362`

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
0x1800041a8  mov     [rsp+arg_8], rbx
0x1800041ad  mov     [rsp+arg_10], rbp
0x1800041b2  push    rsi
0x1800041b3  push    rdi
0x1800041b4  push    r12
0x1800041b6  push    r14
0x1800041b8  push    r15
0x1800041ba  sub     rsp, 250h
0x1800041c1  mov     rax, cs:__security_cookie
0x1800041c8  xor     rax, rsp
0x1800041cb  mov     [rsp+278h+var_38], rax
0x1800041d3  mov     rax, 0C000000000000000h
0x1800041dd  mov     rbp, r9
0x1800041e0  mov     r8, rdx
0x1800041e3  mov     rbx, rcx
0x1800041e6  test    rax, r9
0x1800041e9  jnz     loc_1800043B9
0x1800041ef  xor     r12d, r12d
0x1800041f2  lea     rax, [rsp+278h+Name]
0x1800041f7  mov     ecx, 7FFFFFFEh
0x1800041fc  mov     edx, 104h
0x180004201  lea     esi, [r12+1]
0x180004206  test    rcx, rcx
0x180004209  jz      short loc_180004229
0x18000420b  movzx   r9d, word ptr [r8]
0x18000420f  test    r9w, r9w
0x180004213  jz      short loc_180004229
0x180004215  mov     [rax], r9w
0x180004219  add     r8, 2
0x18000421d  add     rax, 2
0x180004221  sub     rcx, rsi
0x180004224  sub     rdx, rsi; unsigned __int64
0x180004227  jnz     short loc_180004206
0x180004229  test    rdx, rdx
0x18000422c  lea     rcx, [rax-2]
0x180004230  lea     r8, aP0; "_p0"
0x180004237  cmovnz  rcx, rax
0x18000423b  mov     [rcx], r12w
0x18000423f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004244  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004249  mov     edx, ebp
0x18000424b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004253  and     edx, 7FFFFFFFh; lInitialCount
0x180004259  mov     [rsp+278h+dwFlags], r12d; int
0x18000425e  mov     r8d, esi
0x180004261  lea     r9, [rsp+278h+Name]; lpName
0x180004266  cmova   r8d, edx; lMaximumCount
0x18000426a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000426c  call    cs:__imp_CreateSemaphoreExW
0x180004272  mov     r15, rax
0x180004275  test    rax, rax
0x180004278  jnz     short loc_1800042A8
0x18000427a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000427f  mov     edi, eax
0x180004281  test    eax, eax
0x180004283  jns     short loc_1800042DC
0x180004285  mov     rcx, [rsp+278h]; this
0x18000428d  lea     r8, aWil; "wil"
0x180004294  mov     r9d, eax; char *
0x180004297  mov     edx, 8Bh; void *
0x18000429c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042a1  mov     eax, edi
0x1800042a3  jmp     loc_18000437A
0x1800042a8  call    cs:__imp_GetLastError
0x1800042ae  mov     rdi, [rbx]
0x1800042b1  test    rdi, rdi
0x1800042b4  jz      short loc_1800042D9
0x1800042b6  call    cs:__imp_GetLastError
0x1800042bc  mov     rcx, rdi; hObject
0x1800042bf  mov     r14d, eax
0x1800042c2  call    cs:__imp_CloseHandle
0x1800042c8  test    eax, eax
0x1800042ca  jz      loc_1800043BF
0x1800042d0  mov     ecx, r14d; dwErrCode
0x1800042d3  call    cs:__imp_SetLastError
0x1800042d9  mov     [rbx], r15
0x1800042dc  lea     r8, asc_18000EDD8; "h"
0x1800042e3  shr     rbp, 1Fh
0x1800042e7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800042ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800042f1  test    ebp, ebp
0x1800042f3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800042fb  lea     r9, [rsp+278h+Name]; lpName
0x180004300  mov     [rsp+278h+dwFlags], r12d; int
0x180004305  cmovnz  esi, ebp
0x180004308  mov     edx, ebp; lInitialCount
0x18000430a  mov     r8d, esi; lMaximumCount
0x18000430d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000430f  call    cs:__imp_CreateSemaphoreExW
0x180004315  mov     rsi, rax
0x180004318  test    rax, rax
0x18000431b  jnz     short loc_180004348
0x18000431d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004322  mov     ebx, eax
0x180004324  test    eax, eax
0x180004326  jns     short loc_180004378
0x180004328  mov     rcx, [rsp+278h]; this
0x180004330  lea     r8, aWil; "wil"
0x180004337  mov     r9d, eax; char *
0x18000433a  mov     edx, 90h; void *
0x18000433f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004344  mov     eax, ebx
0x180004346  jmp     short loc_18000437A
0x180004348  call    cs:__imp_GetLastError
0x18000434e  mov     rdi, [rbx+8]
0x180004352  test    rdi, rdi
0x180004355  jz      short loc_180004374
0x180004357  call    cs:__imp_GetLastError
0x18000435d  mov     rcx, rdi; hObject
0x180004360  mov     ebp, eax
0x180004362  call    cs:__imp_CloseHandle
0x180004368  test    eax, eax
0x18000436a  jz      short loc_1800043A6
0x18000436c  mov     ecx, ebp; dwErrCode
0x18000436e  call    cs:__imp_SetLastError
0x180004374  mov     [rbx+8], rsi
0x180004378  xor     eax, eax
0x18000437a  mov     rcx, [rsp+278h+var_38]
0x180004382  xor     rcx, rsp; StackCookie
0x180004385  call    __security_check_cookie
0x18000438a  lea     r11, [rsp+278h+var_28]
0x180004392  mov     rbx, [r11+38h]
0x180004396  mov     rbp, [r11+40h]
0x18000439a  mov     rsp, r11
0x18000439d  pop     r15
0x18000439f  pop     r14
0x1800043a1  pop     r12
0x1800043a3  pop     rdi
0x1800043a4  pop     rsi
0x1800043a5  retn
0x1800043a6  mov     rcx, [rsp+278h]; this
0x1800043ae  mov     edx, 0A0Bh; void *
0x1800043b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800043b9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800043bf  mov     rcx, [rsp+278h]; this
0x1800043c7  mov     edx, 0A0Bh; void *
0x1800043cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
