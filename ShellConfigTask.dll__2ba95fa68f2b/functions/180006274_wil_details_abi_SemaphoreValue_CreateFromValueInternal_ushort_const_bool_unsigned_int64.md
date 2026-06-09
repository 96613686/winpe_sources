# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006274`
- end: `0x1800064ac`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `568`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a58`
- `0x180005e38`

## callees

- `0x180002590`
- `0x180006274`
- `0x180007c58`
- `0x18000ab14`
- `0x18000b680`
- `0x18000c5c4`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000639f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000643a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000639f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000643a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006423`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006338`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800063db`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006338`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800063db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000638e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000642e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000638e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000642e`

## string_xrefs

- `0x18000647a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000649a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v21; // r9
  unsigned __int64 v22; // rbp
  wil::details *v23; // rcx
  HANDLE v24; // rsi
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // ebp
  const char *v29; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
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
0x180006274  mov     [rsp+arg_8], rbx
0x180006279  mov     [rsp+arg_10], rbp
0x18000627e  push    rsi
0x18000627f  push    rdi
0x180006280  push    r12
0x180006282  push    r14
0x180006284  push    r15
0x180006286  sub     rsp, 250h
0x18000628d  mov     rax, cs:__security_cookie
0x180006294  xor     rax, rsp
0x180006297  mov     [rsp+278h+var_38], rax
0x18000629f  mov     rax, 0C000000000000000h
0x1800062a9  mov     rbp, r9
0x1800062ac  mov     r8, rdx
0x1800062af  mov     rbx, rcx
0x1800062b2  test    rax, r9
0x1800062b5  jnz     loc_18000648C
0x1800062bb  xor     r12d, r12d
0x1800062be  lea     rax, [rsp+278h+Name]
0x1800062c3  mov     ecx, 7FFFFFFEh
0x1800062c8  mov     edx, 104h
0x1800062cd  lea     esi, [r12+1]
0x1800062d2  test    rcx, rcx
0x1800062d5  jz      short loc_1800062F5
0x1800062d7  movzx   r9d, word ptr [r8]
0x1800062db  test    r9w, r9w
0x1800062df  jz      short loc_1800062F5
0x1800062e1  mov     [rax], r9w
0x1800062e5  add     r8, 2
0x1800062e9  add     rax, 2
0x1800062ed  sub     rcx, rsi
0x1800062f0  sub     rdx, rsi; unsigned __int64
0x1800062f3  jnz     short loc_1800062D2
0x1800062f5  test    rdx, rdx
0x1800062f8  lea     rcx, [rax-2]
0x1800062fc  lea     r8, aP0; "_p0"
0x180006303  cmovnz  rcx, rax
0x180006307  mov     [rcx], r12w
0x18000630b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006310  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006315  mov     edx, ebp
0x180006317  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000631f  and     edx, 7FFFFFFFh; lInitialCount
0x180006325  mov     [rsp+278h+dwFlags], r12d; int
0x18000632a  mov     r8d, esi
0x18000632d  lea     r9, [rsp+278h+Name]; lpName
0x180006332  cmova   r8d, edx; lMaximumCount
0x180006336  xor     ecx, ecx; lpSemaphoreAttributes
0x180006338  call    cs:__imp_CreateSemaphoreExW
0x18000633e  mov     r15, rax
0x180006341  test    rax, rax
0x180006344  jnz     short loc_180006374
0x180006346  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000634b  mov     edi, eax
0x18000634d  test    eax, eax
0x18000634f  jns     short loc_1800063A8
0x180006351  mov     rcx, [rsp+278h]; this
0x180006359  lea     r8, aWil; "wil"
0x180006360  mov     r9d, eax; char *
0x180006363  mov     edx, 8Bh; void *
0x180006368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000636d  mov     eax, edi
0x18000636f  jmp     loc_180006446
0x180006374  call    cs:__imp_GetLastError
0x18000637a  mov     rdi, [rbx]
0x18000637d  test    rdi, rdi
0x180006380  jz      short loc_1800063A5
0x180006382  call    cs:__imp_GetLastError
0x180006388  mov     rcx, rdi; hObject
0x18000638b  mov     r14d, eax
0x18000638e  call    cs:__imp_CloseHandle
0x180006394  test    eax, eax
0x180006396  jz      loc_180006492
0x18000639c  mov     ecx, r14d; dwErrCode
0x18000639f  call    cs:__imp_SetLastError
0x1800063a5  mov     [rbx], r15
0x1800063a8  lea     r8, asc_180035AE0; "h"
0x1800063af  shr     rbp, 1Fh
0x1800063b3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800063b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800063bd  test    ebp, ebp
0x1800063bf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800063c7  lea     r9, [rsp+278h+Name]; lpName
0x1800063cc  mov     [rsp+278h+dwFlags], r12d; int
0x1800063d1  cmovnz  esi, ebp
0x1800063d4  mov     edx, ebp; lInitialCount
0x1800063d6  mov     r8d, esi; lMaximumCount
0x1800063d9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800063db  call    cs:__imp_CreateSemaphoreExW
0x1800063e1  mov     rsi, rax
0x1800063e4  test    rax, rax
0x1800063e7  jnz     short loc_180006414
0x1800063e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800063ee  mov     ebx, eax
0x1800063f0  test    eax, eax
0x1800063f2  jns     short loc_180006444
0x1800063f4  mov     rcx, [rsp+278h]; this
0x1800063fc  lea     r8, aWil; "wil"
0x180006403  mov     r9d, eax; char *
0x180006406  mov     edx, 90h; void *
0x18000640b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006410  mov     eax, ebx
0x180006412  jmp     short loc_180006446
0x180006414  call    cs:__imp_GetLastError
0x18000641a  mov     rdi, [rbx+8]
0x18000641e  test    rdi, rdi
0x180006421  jz      short loc_180006440
0x180006423  call    cs:__imp_GetLastError
0x180006429  mov     rcx, rdi; hObject
0x18000642c  mov     ebp, eax
0x18000642e  call    cs:__imp_CloseHandle
0x180006434  test    eax, eax
0x180006436  jz      short loc_180006472
0x180006438  mov     ecx, ebp; dwErrCode
0x18000643a  call    cs:__imp_SetLastError
0x180006440  mov     [rbx+8], rsi
0x180006444  xor     eax, eax
0x180006446  mov     rcx, [rsp+278h+var_38]
0x18000644e  xor     rcx, rsp; StackCookie
0x180006451  call    __security_check_cookie
0x180006456  lea     r11, [rsp+278h+var_28]
0x18000645e  mov     rbx, [r11+38h]
0x180006462  mov     rbp, [r11+40h]
0x180006466  mov     rsp, r11
0x180006469  pop     r15
0x18000646b  pop     r14
0x18000646d  pop     r12
0x18000646f  pop     rdi
0x180006470  pop     rsi
0x180006471  retn
0x180006472  mov     rcx, [rsp+278h]; this
0x18000647a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006481  mov     edx, 0A0Bh; void *
0x180006486  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000648c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006492  mov     rcx, [rsp+278h]; this
0x18000649a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800064a1  mov     edx, 0A0Bh; void *
0x1800064a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
