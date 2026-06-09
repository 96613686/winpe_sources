# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180004258`
- end: `0x180004482`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e88`
- `0x180007c8c`

## callees

- `0x180002170`
- `0x180004258`
- `0x180004b98`
- `0x180005ad4`
- `0x180006414`
- `0x18000697c`
- `0x18000698c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000431c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043bf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000431c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800043bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004383`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000441e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004383`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000441e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004412`

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
0x180004258  mov     [rsp+arg_8], rbx
0x18000425d  mov     [rsp+arg_10], rbp
0x180004262  push    rsi
0x180004263  push    rdi
0x180004264  push    r12
0x180004266  push    r14
0x180004268  push    r15
0x18000426a  sub     rsp, 250h
0x180004271  mov     rax, cs:__security_cookie
0x180004278  xor     rax, rsp
0x18000427b  mov     [rsp+278h+var_38], rax
0x180004283  mov     rax, 0C000000000000000h
0x18000428d  mov     rbp, r9
0x180004290  mov     r8, rdx
0x180004293  mov     rbx, rcx
0x180004296  test    rax, r9
0x180004299  jnz     loc_180004469
0x18000429f  xor     r12d, r12d
0x1800042a2  lea     rax, [rsp+278h+Name]
0x1800042a7  mov     ecx, 7FFFFFFEh
0x1800042ac  mov     edx, 104h
0x1800042b1  lea     esi, [r12+1]
0x1800042b6  test    rcx, rcx
0x1800042b9  jz      short loc_1800042D9
0x1800042bb  movzx   r9d, word ptr [r8]
0x1800042bf  test    r9w, r9w
0x1800042c3  jz      short loc_1800042D9
0x1800042c5  mov     [rax], r9w
0x1800042c9  add     r8, 2
0x1800042cd  add     rax, 2
0x1800042d1  sub     rcx, rsi
0x1800042d4  sub     rdx, rsi; unsigned __int64
0x1800042d7  jnz     short loc_1800042B6
0x1800042d9  test    rdx, rdx
0x1800042dc  lea     rcx, [rax-2]
0x1800042e0  lea     r8, aP0; "_p0"
0x1800042e7  cmovnz  rcx, rax
0x1800042eb  mov     [rcx], r12w
0x1800042ef  lea     rcx, [rsp+278h+Name]; wchar_t *
0x1800042f4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800042f9  mov     edx, ebp
0x1800042fb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004303  and     edx, 7FFFFFFFh; lInitialCount
0x180004309  mov     [rsp+278h+dwFlags], r12d; int
0x18000430e  mov     r8d, esi
0x180004311  lea     r9, [rsp+278h+Name]; lpName
0x180004316  cmova   r8d, edx; lMaximumCount
0x18000431a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000431c  call    cs:__imp_CreateSemaphoreExW
0x180004322  mov     r15, rax
0x180004325  test    rax, rax
0x180004328  jnz     short loc_180004358
0x18000432a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000432f  mov     edi, eax
0x180004331  test    eax, eax
0x180004333  jns     short loc_18000438C
0x180004335  mov     rcx, [rsp+278h]; this
0x18000433d  lea     r8, aWil; "wil"
0x180004344  mov     r9d, eax; char *
0x180004347  mov     edx, 8Bh; void *
0x18000434c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004351  mov     eax, edi
0x180004353  jmp     loc_18000442A
0x180004358  call    cs:__imp_GetLastError
0x18000435e  mov     rdi, [rbx]
0x180004361  test    rdi, rdi
0x180004364  jz      short loc_180004389
0x180004366  call    cs:__imp_GetLastError
0x18000436c  mov     rcx, rdi; hObject
0x18000436f  mov     r14d, eax
0x180004372  call    cs:__imp_CloseHandle
0x180004378  test    eax, eax
0x18000437a  jz      loc_18000446F
0x180004380  mov     ecx, r14d; dwErrCode
0x180004383  call    cs:__imp_SetLastError
0x180004389  mov     [rbx], r15
0x18000438c  lea     r8, asc_1800113E0; "h"
0x180004393  shr     rbp, 1Fh
0x180004397  lea     rcx, [rsp+278h+Name]; wchar_t *
0x18000439c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800043a1  test    ebp, ebp
0x1800043a3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800043ab  lea     r9, [rsp+278h+Name]; lpName
0x1800043b0  mov     [rsp+278h+dwFlags], r12d; int
0x1800043b5  cmovnz  esi, ebp
0x1800043b8  mov     edx, ebp; lInitialCount
0x1800043ba  mov     r8d, esi; lMaximumCount
0x1800043bd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800043bf  call    cs:__imp_CreateSemaphoreExW
0x1800043c5  mov     rsi, rax
0x1800043c8  test    rax, rax
0x1800043cb  jnz     short loc_1800043F8
0x1800043cd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800043d2  mov     ebx, eax
0x1800043d4  test    eax, eax
0x1800043d6  jns     short loc_180004428
0x1800043d8  mov     rcx, [rsp+278h]; this
0x1800043e0  lea     r8, aWil; "wil"
0x1800043e7  mov     r9d, eax; char *
0x1800043ea  mov     edx, 90h; void *
0x1800043ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043f4  mov     eax, ebx
0x1800043f6  jmp     short loc_18000442A
0x1800043f8  call    cs:__imp_GetLastError
0x1800043fe  mov     rdi, [rbx+8]
0x180004402  test    rdi, rdi
0x180004405  jz      short loc_180004424
0x180004407  call    cs:__imp_GetLastError
0x18000440d  mov     rcx, rdi; hObject
0x180004410  mov     ebp, eax
0x180004412  call    cs:__imp_CloseHandle
0x180004418  test    eax, eax
0x18000441a  jz      short loc_180004456
0x18000441c  mov     ecx, ebp; dwErrCode
0x18000441e  call    cs:__imp_SetLastError
0x180004424  mov     [rbx+8], rsi
0x180004428  xor     eax, eax
0x18000442a  mov     rcx, [rsp+278h+var_38]
0x180004432  xor     rcx, rsp; StackCookie
0x180004435  call    __security_check_cookie
0x18000443a  lea     r11, [rsp+278h+var_28]
0x180004442  mov     rbx, [r11+38h]
0x180004446  mov     rbp, [r11+40h]
0x18000444a  mov     rsp, r11
0x18000444d  pop     r15
0x18000444f  pop     r14
0x180004451  pop     r12
0x180004453  pop     rdi
0x180004454  pop     rsi
0x180004455  retn
0x180004456  mov     rcx, [rsp+278h]; this
0x18000445e  mov     edx, 0A0Bh; void *
0x180004463  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004469  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000446f  mov     rcx, [rsp+278h]; this
0x180004477  mov     edx, 0A0Bh; void *
0x18000447c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
