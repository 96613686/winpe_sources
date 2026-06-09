# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1400041ec`
- end: `0x1400043f9`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a78`
- `0x140003e1c`

## callees

- `0x1400016f0`
- `0x1400041ec`
- `0x140005038`
- `0x1400072e4`
- `0x140007d28`
- `0x140008aec`
- `0x140008afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400042b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000434c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400042b0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000434c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000436f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000437e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000436f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000437e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004310`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004310`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400042ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004389`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400041ec  mov     [rsp+arg_8], rbx
0x1400041f1  mov     [rsp+arg_10], rbp
0x1400041f6  push    rsi
0x1400041f7  push    rdi
0x1400041f8  push    r12
0x1400041fa  push    r14
0x1400041fc  push    r15
0x1400041fe  sub     rsp, 250h
0x140004205  mov     rax, cs:__security_cookie
0x14000420c  xor     rax, rsp
0x14000420f  mov     [rsp+278h+var_38], rax
0x140004217  mov     rax, 0C000000000000000h
0x140004221  mov     rbp, r9
0x140004224  mov     r8, rdx
0x140004227  mov     rdi, rcx
0x14000422a  test    rax, r9
0x14000422d  jnz     loc_1400043E0
0x140004233  xor     r12d, r12d
0x140004236  lea     rax, [rsp+278h+Name]
0x14000423b  mov     ecx, 7FFFFFFEh
0x140004240  mov     edx, 104h
0x140004245  lea     esi, [r12+1]
0x14000424a  test    rcx, rcx
0x14000424d  jz      short loc_14000426D
0x14000424f  movzx   r9d, word ptr [r8]
0x140004253  test    r9w, r9w
0x140004257  jz      short loc_14000426D
0x140004259  mov     [rax], r9w
0x14000425d  add     r8, 2
0x140004261  add     rax, 2
0x140004265  sub     rcx, rsi
0x140004268  sub     rdx, rsi; unsigned __int64
0x14000426b  jnz     short loc_14000424A
0x14000426d  test    rdx, rdx
0x140004270  lea     rcx, [rax-2]
0x140004274  lea     r8, aP0; "_p0"
0x14000427b  cmovnz  rcx, rax
0x14000427f  mov     [rcx], r12w
0x140004283  lea     rcx, [rsp+278h+Name]; wchar_t *
0x140004288  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000428d  mov     edx, ebp
0x14000428f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004297  and     edx, 7FFFFFFFh; lInitialCount
0x14000429d  mov     [rsp+278h+dwFlags], r12d; int
0x1400042a2  mov     r8d, esi
0x1400042a5  lea     r9, [rsp+278h+Name]; lpName
0x1400042aa  cmova   r8d, edx; lMaximumCount
0x1400042ae  xor     ecx, ecx; lpSemaphoreAttributes
0x1400042b0  call    cs:__imp_CreateSemaphoreExW
0x1400042b6  mov     r15, rax
0x1400042b9  test    rax, rax
0x1400042bc  jnz     short loc_1400042E5
0x1400042be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400042c3  mov     ebx, eax
0x1400042c5  test    eax, eax
0x1400042c7  jns     short loc_140004319
0x1400042c9  mov     edx, 8Bh; void *
0x1400042ce  mov     rcx, [rsp+278h]; this
0x1400042d6  mov     r9d, ebx; char *
0x1400042d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042de  mov     eax, ebx
0x1400042e0  jmp     loc_1400043A1
0x1400042e5  call    cs:__imp_GetLastError
0x1400042eb  mov     rbx, [rdi]
0x1400042ee  test    rbx, rbx
0x1400042f1  jz      short loc_140004316
0x1400042f3  call    cs:__imp_GetLastError
0x1400042f9  mov     rcx, rbx; hObject
0x1400042fc  mov     r14d, eax
0x1400042ff  call    cs:__imp_CloseHandle
0x140004305  test    eax, eax
0x140004307  jz      loc_1400043E6
0x14000430d  mov     ecx, r14d; dwErrCode
0x140004310  call    cs:__imp_SetLastError
0x140004316  mov     [rdi], r15
0x140004319  lea     r8, asc_14000DA80; "h"
0x140004320  shr     rbp, 1Fh
0x140004324  lea     rcx, [rsp+278h+Name]; wchar_t *
0x140004329  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000432e  test    ebp, ebp
0x140004330  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004338  lea     r9, [rsp+278h+Name]; lpName
0x14000433d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004342  cmovnz  esi, ebp
0x140004345  mov     edx, ebp; lInitialCount
0x140004347  mov     r8d, esi; lMaximumCount
0x14000434a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000434c  call    cs:__imp_CreateSemaphoreExW
0x140004352  mov     rsi, rax
0x140004355  test    rax, rax
0x140004358  jnz     short loc_14000436F
0x14000435a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000435f  mov     ebx, eax
0x140004361  test    eax, eax
0x140004363  jns     short loc_14000439F
0x140004365  mov     edx, 90h
0x14000436a  jmp     loc_1400042CE
0x14000436f  call    cs:__imp_GetLastError
0x140004375  mov     rbx, [rdi+8]
0x140004379  test    rbx, rbx
0x14000437c  jz      short loc_14000439B
0x14000437e  call    cs:__imp_GetLastError
0x140004384  mov     rcx, rbx; hObject
0x140004387  mov     ebp, eax
0x140004389  call    cs:__imp_CloseHandle
0x14000438f  test    eax, eax
0x140004391  jz      short loc_1400043CD
0x140004393  mov     ecx, ebp; dwErrCode
0x140004395  call    cs:__imp_SetLastError
0x14000439b  mov     [rdi+8], rsi
0x14000439f  xor     eax, eax
0x1400043a1  mov     rcx, [rsp+278h+var_38]
0x1400043a9  xor     rcx, rsp; StackCookie
0x1400043ac  call    __security_check_cookie
0x1400043b1  lea     r11, [rsp+278h+var_28]
0x1400043b9  mov     rbx, [r11+38h]
0x1400043bd  mov     rbp, [r11+40h]
0x1400043c1  mov     rsp, r11
0x1400043c4  pop     r15
0x1400043c6  pop     r14
0x1400043c8  pop     r12
0x1400043ca  pop     rdi
0x1400043cb  pop     rsi
0x1400043cc  retn
0x1400043cd  mov     rcx, [rsp+278h]; this
0x1400043d5  mov     edx, 0A0Bh; void *
0x1400043da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400043e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400043e6  mov     rcx, [rsp+278h]; this
0x1400043ee  mov     edx, 0A0Bh; void *
0x1400043f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
