# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000422c`
- end: `0x180004439`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003ab8`
- `0x180003e5c`

## callees

- `0x1800016a0`
- `0x18000422c`
- `0x180004fa8`
- `0x1800070c4`
- `0x180007b08`
- `0x18000870c`
- `0x18000871c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042f0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000438c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800042f0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000438c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800043d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000433f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000433f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043c9`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x18000422c  mov     [rsp+arg_8], rbx
0x180004231  mov     [rsp+arg_10], rbp
0x180004236  push    rsi
0x180004237  push    rdi
0x180004238  push    r12
0x18000423a  push    r14
0x18000423c  push    r15
0x18000423e  sub     rsp, 250h
0x180004245  mov     rax, cs:__security_cookie
0x18000424c  xor     rax, rsp
0x18000424f  mov     [rsp+278h+var_38], rax
0x180004257  mov     rax, 0C000000000000000h
0x180004261  mov     rbp, r9
0x180004264  mov     r8, rdx
0x180004267  mov     rdi, rcx
0x18000426a  test    rax, r9
0x18000426d  jnz     loc_180004420
0x180004273  xor     r12d, r12d
0x180004276  lea     rax, [rsp+278h+Name]
0x18000427b  mov     ecx, 7FFFFFFEh
0x180004280  mov     edx, 104h
0x180004285  lea     esi, [r12+1]
0x18000428a  test    rcx, rcx
0x18000428d  jz      short loc_1800042AD
0x18000428f  movzx   r9d, word ptr [r8]
0x180004293  test    r9w, r9w
0x180004297  jz      short loc_1800042AD
0x180004299  mov     [rax], r9w
0x18000429d  add     r8, 2
0x1800042a1  add     rax, 2
0x1800042a5  sub     rcx, rsi
0x1800042a8  sub     rdx, rsi; unsigned __int64
0x1800042ab  jnz     short loc_18000428A
0x1800042ad  test    rdx, rdx
0x1800042b0  lea     rcx, [rax-2]
0x1800042b4  lea     r8, aP0; "_p0"
0x1800042bb  cmovnz  rcx, rax
0x1800042bf  mov     [rcx], r12w
0x1800042c3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800042c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800042cd  mov     edx, ebp
0x1800042cf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800042d7  and     edx, 7FFFFFFFh; lInitialCount
0x1800042dd  mov     [rsp+278h+dwFlags], r12d; int
0x1800042e2  mov     r8d, esi
0x1800042e5  lea     r9, [rsp+278h+Name]; lpName
0x1800042ea  cmova   r8d, edx; lMaximumCount
0x1800042ee  xor     ecx, ecx; lpSemaphoreAttributes
0x1800042f0  call    cs:__imp_CreateSemaphoreExW
0x1800042f6  mov     r15, rax
0x1800042f9  test    rax, rax
0x1800042fc  jnz     short loc_180004325
0x1800042fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004303  mov     ebx, eax
0x180004305  test    eax, eax
0x180004307  jns     short loc_180004359
0x180004309  mov     edx, 8Bh; void *
0x18000430e  mov     rcx, [rsp+278h]; this
0x180004316  mov     r9d, ebx; char *
0x180004319  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000431e  mov     eax, ebx
0x180004320  jmp     loc_1800043E1
0x180004325  call    cs:__imp_GetLastError
0x18000432b  mov     rbx, [rdi]
0x18000432e  test    rbx, rbx
0x180004331  jz      short loc_180004356
0x180004333  call    cs:__imp_GetLastError
0x180004339  mov     rcx, rbx; hObject
0x18000433c  mov     r14d, eax
0x18000433f  call    cs:__imp_CloseHandle
0x180004345  test    eax, eax
0x180004347  jz      loc_180004426
0x18000434d  mov     ecx, r14d; dwErrCode
0x180004350  call    cs:__imp_SetLastError
0x180004356  mov     [rdi], r15
0x180004359  lea     r8, asc_18000FEB0; "h"
0x180004360  shr     rbp, 1Fh
0x180004364  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004369  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000436e  test    ebp, ebp
0x180004370  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004378  lea     r9, [rsp+278h+Name]; lpName
0x18000437d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004382  cmovnz  esi, ebp
0x180004385  mov     edx, ebp; lInitialCount
0x180004387  mov     r8d, esi; lMaximumCount
0x18000438a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000438c  call    cs:__imp_CreateSemaphoreExW
0x180004392  mov     rsi, rax
0x180004395  test    rax, rax
0x180004398  jnz     short loc_1800043AF
0x18000439a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000439f  mov     ebx, eax
0x1800043a1  test    eax, eax
0x1800043a3  jns     short loc_1800043DF
0x1800043a5  mov     edx, 90h
0x1800043aa  jmp     loc_18000430E
0x1800043af  call    cs:__imp_GetLastError
0x1800043b5  mov     rbx, [rdi+8]
0x1800043b9  test    rbx, rbx
0x1800043bc  jz      short loc_1800043DB
0x1800043be  call    cs:__imp_GetLastError
0x1800043c4  mov     rcx, rbx; hObject
0x1800043c7  mov     ebp, eax
0x1800043c9  call    cs:__imp_CloseHandle
0x1800043cf  test    eax, eax
0x1800043d1  jz      short loc_18000440D
0x1800043d3  mov     ecx, ebp; dwErrCode
0x1800043d5  call    cs:__imp_SetLastError
0x1800043db  mov     [rdi+8], rsi
0x1800043df  xor     eax, eax
0x1800043e1  mov     rcx, [rsp+278h+var_38]
0x1800043e9  xor     rcx, rsp; StackCookie
0x1800043ec  call    __security_check_cookie
0x1800043f1  lea     r11, [rsp+278h+var_28]
0x1800043f9  mov     rbx, [r11+38h]
0x1800043fd  mov     rbp, [r11+40h]
0x180004401  mov     rsp, r11
0x180004404  pop     r15
0x180004406  pop     r14
0x180004408  pop     r12
0x18000440a  pop     rdi
0x18000440b  pop     rsi
0x18000440c  retn
0x18000440d  mov     rcx, [rsp+278h]; this
0x180004415  mov     edx, 0A0Bh; void *
0x18000441a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004420  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004426  mov     rcx, [rsp+278h]; this
0x18000442e  mov     edx, 0A0Bh; void *
0x180004433  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
