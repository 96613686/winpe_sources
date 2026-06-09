# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000cfac`
- end: `0x18000d1d6`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c450`
- `0x1800114d8`

## callees

- `0x18000cfac`
- `0x18000dbd0`
- `0x18000efec`
- `0x18000f29c`
- `0x18000f6e0`
- `0x18000f6f0`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d070`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d11b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d070`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000d11b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d0df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d17a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d0df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d16e`

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
  int LastErrorFailHr; // eax
  unsigned __int64 v17; // rdx
  unsigned int v18; // edi
  void *v20; // rdi
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  int v27; // eax
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // ebp
  unsigned int v31; // r8d
  const char *v32; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
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
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
    v18 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v18;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v17, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    v27 = wil::details::GetLastErrorFailHr(v25);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v27,
        dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cfac  mov     [rsp+arg_8], rbx
0x18000cfb1  mov     [rsp+arg_10], rbp
0x18000cfb6  push    rsi
0x18000cfb7  push    rdi
0x18000cfb8  push    r12
0x18000cfba  push    r14
0x18000cfbc  push    r15
0x18000cfbe  sub     rsp, 250h
0x18000cfc5  mov     rax, cs:__security_cookie
0x18000cfcc  xor     rax, rsp
0x18000cfcf  mov     [rsp+278h+var_38], rax
0x18000cfd7  mov     rbp, r9
0x18000cfda  mov     r8, rdx
0x18000cfdd  mov     rbx, rcx
0x18000cfe0  mov     rax, 0C000000000000000h
0x18000cfea  test    rax, r9
0x18000cfed  jnz     loc_18000D1C5
0x18000cff3  mov     ecx, 7FFFFFFEh
0x18000cff8  mov     edx, 104h
0x18000cffd  lea     rax, [rsp+278h+Name]
0x18000d002  xor     r12d, r12d
0x18000d005  lea     esi, [r12+1]
0x18000d00a  test    rcx, rcx
0x18000d00d  jz      short loc_18000D02D
0x18000d00f  movzx   r9d, word ptr [r8]
0x18000d013  test    r9w, r9w
0x18000d017  jz      short loc_18000D02D
0x18000d019  add     r8, 2
0x18000d01d  mov     [rax], r9w
0x18000d021  add     rax, 2
0x18000d025  sub     rcx, rsi
0x18000d028  sub     rdx, rsi; unsigned __int64
0x18000d02b  jnz     short loc_18000D00A
0x18000d02d  lea     rcx, [rax-2]
0x18000d031  test    rdx, rdx
0x18000d034  cmovnz  rcx, rax
0x18000d038  mov     [rcx], r12w
0x18000d03c  lea     r8, aP0; "_p0"
0x18000d043  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000d048  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d04d  mov     edx, ebp
0x18000d04f  and     edx, 7FFFFFFFh; lInitialCount
0x18000d055  mov     r8d, esi
0x18000d058  cmova   r8d, edx; lMaximumCount
0x18000d05c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000d064  mov     [rsp+278h+dwFlags], r12d; int
0x18000d069  lea     r9, [rsp+278h+Name]; lpName
0x18000d06e  xor     ecx, ecx; lpSemaphoreAttributes
0x18000d070  call    cs:__imp_CreateSemaphoreExW
0x18000d076  mov     r15, rax
0x18000d079  test    rax, rax
0x18000d07c  jnz     short loc_18000D0AC
0x18000d07e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d083  mov     edi, eax
0x18000d085  test    eax, eax
0x18000d087  jns     short loc_18000D0E8
0x18000d089  mov     rcx, [rsp+278h]; this
0x18000d091  mov     r9d, eax; char *
0x18000d094  lea     r8, aWil; "wil"
0x18000d09b  mov     edx, 8Bh; void *
0x18000d0a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0a5  mov     eax, edi
0x18000d0a7  jmp     loc_18000D186
0x18000d0ac  call    cs:__imp_GetLastError
0x18000d0b2  mov     rdi, [rbx]
0x18000d0b5  test    rdi, rdi
0x18000d0b8  jz      short loc_18000D0E5
0x18000d0ba  call    cs:__imp_GetLastError
0x18000d0c0  mov     r14d, eax
0x18000d0c3  mov     rcx, rdi; hObject
0x18000d0c6  call    cs:__imp_CloseHandle
0x18000d0cc  mov     rcx, [rsp+278h]; this
0x18000d0d4  test    eax, eax
0x18000d0d6  jz      loc_18000D1CB
0x18000d0dc  mov     ecx, r14d; dwErrCode
0x18000d0df  call    cs:__imp_SetLastError
0x18000d0e5  mov     [rbx], r15
0x18000d0e8  shr     rbp, 1Fh
0x18000d0ec  lea     r8, asc_18001F368; "h"
0x18000d0f3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000d0f8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d0fd  test    ebp, ebp
0x18000d0ff  cmovnz  esi, ebp
0x18000d102  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000d10a  mov     [rsp+278h+dwFlags], r12d; int
0x18000d10f  lea     r9, [rsp+278h+Name]; lpName
0x18000d114  mov     r8d, esi; lMaximumCount
0x18000d117  mov     edx, ebp; lInitialCount
0x18000d119  xor     ecx, ecx; lpSemaphoreAttributes
0x18000d11b  call    cs:__imp_CreateSemaphoreExW
0x18000d121  mov     rsi, rax
0x18000d124  test    rax, rax
0x18000d127  jnz     short loc_18000D154
0x18000d129  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d12e  mov     ebx, eax
0x18000d130  test    eax, eax
0x18000d132  jns     short loc_18000D184
0x18000d134  mov     rcx, [rsp+278h]; this
0x18000d13c  mov     r9d, eax; char *
0x18000d13f  lea     r8, aWil; "wil"
0x18000d146  mov     edx, 90h; void *
0x18000d14b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d150  mov     eax, ebx
0x18000d152  jmp     short loc_18000D186
0x18000d154  call    cs:__imp_GetLastError
0x18000d15a  mov     rdi, [rbx+8]
0x18000d15e  test    rdi, rdi
0x18000d161  jz      short loc_18000D180
0x18000d163  call    cs:__imp_GetLastError
0x18000d169  mov     ebp, eax
0x18000d16b  mov     rcx, rdi; hObject
0x18000d16e  call    cs:__imp_CloseHandle
0x18000d174  test    eax, eax
0x18000d176  jz      short loc_18000D1B2
0x18000d178  mov     ecx, ebp; dwErrCode
0x18000d17a  call    cs:__imp_SetLastError
0x18000d180  mov     [rbx+8], rsi
0x18000d184  xor     eax, eax
0x18000d186  mov     rcx, [rsp+278h+var_38]
0x18000d18e  xor     rcx, rsp; StackCookie
0x18000d191  call    __security_check_cookie
0x18000d196  lea     r11, [rsp+278h+var_28]
0x18000d19e  mov     rbx, [r11+38h]
0x18000d1a2  mov     rbp, [r11+40h]
0x18000d1a6  mov     rsp, r11
0x18000d1a9  pop     r15
0x18000d1ab  pop     r14
0x18000d1ad  pop     r12
0x18000d1af  pop     rdi
0x18000d1b0  pop     rsi
0x18000d1b1  retn
0x18000d1b2  mov     rcx, [rsp+278h]; this
0x18000d1ba  mov     edx, 0A0Bh; void *
0x18000d1bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d1c5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d1cb  mov     edx, 0A0Bh; void *
0x18000d1d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
