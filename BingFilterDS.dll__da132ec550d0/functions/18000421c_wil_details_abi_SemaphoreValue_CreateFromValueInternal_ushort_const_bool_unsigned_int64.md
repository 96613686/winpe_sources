# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000421c`
- end: `0x180004446`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x18000421c`
- `0x180004cd8`
- `0x180006264`
- `0x180006980`
- `0x1800070e4`
- `0x1800070f4`
- `0x18000c530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004383`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042e0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004383`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004347`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004347`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000431c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000431c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004336`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d6`

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
0x18000421c  mov     [rsp+arg_8], rbx
0x180004221  mov     [rsp+arg_10], rbp
0x180004226  push    rsi
0x180004227  push    rdi
0x180004228  push    r12
0x18000422a  push    r14
0x18000422c  push    r15
0x18000422e  sub     rsp, 250h
0x180004235  mov     rax, cs:__security_cookie
0x18000423c  xor     rax, rsp
0x18000423f  mov     [rsp+278h+var_38], rax
0x180004247  mov     rax, 0C000000000000000h
0x180004251  mov     rbp, r9
0x180004254  mov     r8, rdx
0x180004257  mov     rbx, rcx
0x18000425a  test    rax, r9
0x18000425d  jnz     loc_18000442D
0x180004263  xor     r12d, r12d
0x180004266  lea     rax, [rsp+278h+Name]
0x18000426b  mov     ecx, 7FFFFFFEh
0x180004270  mov     edx, 104h
0x180004275  lea     esi, [r12+1]
0x18000427a  test    rcx, rcx
0x18000427d  jz      short loc_18000429D
0x18000427f  movzx   r9d, word ptr [r8]
0x180004283  test    r9w, r9w
0x180004287  jz      short loc_18000429D
0x180004289  mov     [rax], r9w
0x18000428d  add     r8, 2
0x180004291  add     rax, 2
0x180004295  sub     rcx, rsi
0x180004298  sub     rdx, rsi; unsigned __int64
0x18000429b  jnz     short loc_18000427A
0x18000429d  test    rdx, rdx
0x1800042a0  lea     rcx, [rax-2]
0x1800042a4  lea     r8, aP0; "_p0"
0x1800042ab  cmovnz  rcx, rax
0x1800042af  mov     [rcx], r12w
0x1800042b3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800042b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800042bd  mov     edx, ebp
0x1800042bf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800042c7  and     edx, 7FFFFFFFh; lInitialCount
0x1800042cd  mov     [rsp+278h+dwFlags], r12d; int
0x1800042d2  mov     r8d, esi
0x1800042d5  lea     r9, [rsp+278h+Name]; lpName
0x1800042da  cmova   r8d, edx; lMaximumCount
0x1800042de  xor     ecx, ecx; lpSemaphoreAttributes
0x1800042e0  call    cs:__imp_CreateSemaphoreExW
0x1800042e6  mov     r15, rax
0x1800042e9  test    rax, rax
0x1800042ec  jnz     short loc_18000431C
0x1800042ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800042f3  mov     edi, eax
0x1800042f5  test    eax, eax
0x1800042f7  jns     short loc_180004350
0x1800042f9  mov     rcx, [rsp+278h]; this
0x180004301  lea     r8, aWil; "wil"
0x180004308  mov     r9d, eax; char *
0x18000430b  mov     edx, 8Bh; void *
0x180004310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004315  mov     eax, edi
0x180004317  jmp     loc_1800043EE
0x18000431c  call    cs:__imp_GetLastError
0x180004322  mov     rdi, [rbx]
0x180004325  test    rdi, rdi
0x180004328  jz      short loc_18000434D
0x18000432a  call    cs:__imp_GetLastError
0x180004330  mov     rcx, rdi; hObject
0x180004333  mov     r14d, eax
0x180004336  call    cs:__imp_CloseHandle
0x18000433c  test    eax, eax
0x18000433e  jz      loc_180004433
0x180004344  mov     ecx, r14d; dwErrCode
0x180004347  call    cs:__imp_SetLastError
0x18000434d  mov     [rbx], r15
0x180004350  lea     r8, asc_180011248; "h"
0x180004357  shr     rbp, 1Fh
0x18000435b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004360  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004365  test    ebp, ebp
0x180004367  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000436f  lea     r9, [rsp+278h+Name]; lpName
0x180004374  mov     [rsp+278h+dwFlags], r12d; int
0x180004379  cmovnz  esi, ebp
0x18000437c  mov     edx, ebp; lInitialCount
0x18000437e  mov     r8d, esi; lMaximumCount
0x180004381  xor     ecx, ecx; lpSemaphoreAttributes
0x180004383  call    cs:__imp_CreateSemaphoreExW
0x180004389  mov     rsi, rax
0x18000438c  test    rax, rax
0x18000438f  jnz     short loc_1800043BC
0x180004391  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004396  mov     ebx, eax
0x180004398  test    eax, eax
0x18000439a  jns     short loc_1800043EC
0x18000439c  mov     rcx, [rsp+278h]; this
0x1800043a4  lea     r8, aWil; "wil"
0x1800043ab  mov     r9d, eax; char *
0x1800043ae  mov     edx, 90h; void *
0x1800043b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043b8  mov     eax, ebx
0x1800043ba  jmp     short loc_1800043EE
0x1800043bc  call    cs:__imp_GetLastError
0x1800043c2  mov     rdi, [rbx+8]
0x1800043c6  test    rdi, rdi
0x1800043c9  jz      short loc_1800043E8
0x1800043cb  call    cs:__imp_GetLastError
0x1800043d1  mov     rcx, rdi; hObject
0x1800043d4  mov     ebp, eax
0x1800043d6  call    cs:__imp_CloseHandle
0x1800043dc  test    eax, eax
0x1800043de  jz      short loc_18000441A
0x1800043e0  mov     ecx, ebp; dwErrCode
0x1800043e2  call    cs:__imp_SetLastError
0x1800043e8  mov     [rbx+8], rsi
0x1800043ec  xor     eax, eax
0x1800043ee  mov     rcx, [rsp+278h+var_38]
0x1800043f6  xor     rcx, rsp; StackCookie
0x1800043f9  call    __security_check_cookie
0x1800043fe  lea     r11, [rsp+278h+var_28]
0x180004406  mov     rbx, [r11+38h]
0x18000440a  mov     rbp, [r11+40h]
0x18000440e  mov     rsp, r11
0x180004411  pop     r15
0x180004413  pop     r14
0x180004415  pop     r12
0x180004417  pop     rdi
0x180004418  pop     rsi
0x180004419  retn
0x18000441a  mov     rcx, [rsp+278h]; this
0x180004422  mov     edx, 0A0Bh; void *
0x180004427  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000442d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004433  mov     rcx, [rsp+278h]; this
0x18000443b  mov     edx, 0A0Bh; void *
0x180004440  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
