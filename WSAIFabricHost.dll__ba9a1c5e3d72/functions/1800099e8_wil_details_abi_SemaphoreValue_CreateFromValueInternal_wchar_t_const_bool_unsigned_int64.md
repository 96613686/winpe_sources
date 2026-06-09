# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x1800099e8`
- end: `0x180009c27`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009608`
- `0x18000d264`

## callees

- `0x180004ca0`
- `0x1800099e8`
- `0x18000a348`
- `0x18000b064`
- `0x18000b9a4`
- `0x18000c008`
- `0x18000c018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009ab1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009b57`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009ab1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009baa`

## string_xrefs

- `0x180009bf5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009c15`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  const char *v20; // r9
  unsigned __int64 v21; // rsi
  wil::details *v22; // rcx
  HANDLE v23; // rbp
  int v24; // eax
  unsigned int v25; // ebx
  void *v26; // rdi
  DWORD v27; // esi
  const char *v28; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
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
  v21 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v21 )
    v10 = v21;
  v23 = CreateSemaphoreExW(0, v21, v10, Name, 0, 0x1F0003u);
  if ( v23 )
  {
    GetLastError();
    v26 = (void *)*((_QWORD *)this + 1);
    if ( v26 )
    {
      v27 = GetLastError();
      if ( !CloseHandle(v26) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      SetLastError(v27);
    }
    *((_QWORD *)this + 1) = v23;
  }
  else
  {
    v24 = wil::details::GetLastErrorFailHr(v22);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v24,
        dwFlagsa);
      return v25;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800099e8  mov     [rsp+arg_8], rbx
0x1800099ed  push    rbp
0x1800099ee  push    rsi
0x1800099ef  push    rdi
0x1800099f0  push    r12
0x1800099f2  push    r13
0x1800099f4  push    r14
0x1800099f6  push    r15
0x1800099f8  sub     rsp, 250h
0x1800099ff  mov     rax, cs:__security_cookie
0x180009a06  xor     rax, rsp
0x180009a09  mov     [rsp+288h+var_48], rax
0x180009a11  mov     rax, 0C000000000000000h
0x180009a1b  mov     rsi, r9
0x180009a1e  mov     r8, rdx
0x180009a21  mov     rbx, rcx
0x180009a24  test    rax, r9
0x180009a27  jnz     loc_180009C07
0x180009a2d  xor     r12d, r12d
0x180009a30  lea     rax, [rsp+288h+Name]
0x180009a35  mov     r13d, 104h
0x180009a3b  mov     ecx, 7FFFFFFEh
0x180009a40  mov     edx, r13d
0x180009a43  lea     ebp, [r12+1]
0x180009a48  test    rcx, rcx
0x180009a4b  jz      short loc_180009A6B
0x180009a4d  movzx   r9d, word ptr [r8]
0x180009a51  test    r9w, r9w
0x180009a55  jz      short loc_180009A6B
0x180009a57  mov     [rax], r9w
0x180009a5b  add     r8, 2
0x180009a5f  add     rax, 2
0x180009a63  sub     rcx, rbp
0x180009a66  sub     rdx, rbp
0x180009a69  jnz     short loc_180009A48
0x180009a6b  test    rdx, rdx
0x180009a6e  lea     rcx, [rax-2]
0x180009a72  lea     r8, aP0; "_p0"
0x180009a79  mov     rdx, r13; unsigned __int64
0x180009a7c  cmovnz  rcx, rax
0x180009a80  mov     [rcx], r12w
0x180009a84  lea     rcx, [rsp+288h+Name]; wchar_t *
0x180009a89  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009a8e  mov     edx, esi
0x180009a90  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009a98  and     edx, 7FFFFFFFh; lInitialCount
0x180009a9e  mov     [rsp+288h+dwFlags], r12d; int
0x180009aa3  mov     r8d, ebp
0x180009aa6  lea     r9, [rsp+288h+Name]; lpName
0x180009aab  cmova   r8d, edx; lMaximumCount
0x180009aaf  xor     ecx, ecx; lpSemaphoreAttributes
0x180009ab1  call    cs:__imp_CreateSemaphoreExW
0x180009ab7  mov     r15, rax
0x180009aba  test    rax, rax
0x180009abd  jnz     short loc_180009AED
0x180009abf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ac4  mov     edi, eax
0x180009ac6  test    eax, eax
0x180009ac8  jns     short loc_180009B21
0x180009aca  mov     rcx, [rsp+288h]; this
0x180009ad2  lea     r8, aWil; "wil"
0x180009ad9  mov     r9d, eax; char *
0x180009adc  mov     edx, 8Bh; void *
0x180009ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ae6  mov     eax, edi
0x180009ae8  jmp     loc_180009BC2
0x180009aed  call    cs:__imp_GetLastError
0x180009af3  mov     rdi, [rbx]
0x180009af6  test    rdi, rdi
0x180009af9  jz      short loc_180009B1E
0x180009afb  call    cs:__imp_GetLastError
0x180009b01  mov     rcx, rdi; hObject
0x180009b04  mov     r14d, eax
0x180009b07  call    cs:__imp_CloseHandle
0x180009b0d  test    eax, eax
0x180009b0f  jz      loc_180009C0D
0x180009b15  mov     ecx, r14d; dwErrCode
0x180009b18  call    cs:__imp_SetLastError
0x180009b1e  mov     [rbx], r15
0x180009b21  lea     r8, asc_18008E5C0; "h"
0x180009b28  shr     rsi, 1Fh
0x180009b2c  mov     rdx, r13; unsigned __int64
0x180009b2f  lea     rcx, [rsp+288h+Name]; wchar_t *
0x180009b34  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009b39  test    esi, esi
0x180009b3b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009b43  lea     r9, [rsp+288h+Name]; lpName
0x180009b48  mov     [rsp+288h+dwFlags], r12d; int
0x180009b4d  cmovnz  ebp, esi
0x180009b50  mov     edx, esi; lInitialCount
0x180009b52  mov     r8d, ebp; lMaximumCount
0x180009b55  xor     ecx, ecx; lpSemaphoreAttributes
0x180009b57  call    cs:__imp_CreateSemaphoreExW
0x180009b5d  mov     rbp, rax
0x180009b60  test    rax, rax
0x180009b63  jnz     short loc_180009B90
0x180009b65  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009b6a  mov     ebx, eax
0x180009b6c  test    eax, eax
0x180009b6e  jns     short loc_180009BC0
0x180009b70  mov     rcx, [rsp+288h]; this
0x180009b78  lea     r8, aWil; "wil"
0x180009b7f  mov     r9d, eax; char *
0x180009b82  mov     edx, 90h; void *
0x180009b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b8c  mov     eax, ebx
0x180009b8e  jmp     short loc_180009BC2
0x180009b90  call    cs:__imp_GetLastError
0x180009b96  mov     rdi, [rbx+8]
0x180009b9a  test    rdi, rdi
0x180009b9d  jz      short loc_180009BBC
0x180009b9f  call    cs:__imp_GetLastError
0x180009ba5  mov     rcx, rdi; hObject
0x180009ba8  mov     esi, eax
0x180009baa  call    cs:__imp_CloseHandle
0x180009bb0  test    eax, eax
0x180009bb2  jz      short loc_180009BED
0x180009bb4  mov     ecx, esi; dwErrCode
0x180009bb6  call    cs:__imp_SetLastError
0x180009bbc  mov     [rbx+8], rbp
0x180009bc0  xor     eax, eax
0x180009bc2  mov     rcx, [rsp+288h+var_48]
0x180009bca  xor     rcx, rsp; StackCookie
0x180009bcd  call    __security_check_cookie
0x180009bd2  mov     rbx, [rsp+288h+arg_8]
0x180009bda  add     rsp, 250h
0x180009be1  pop     r15
0x180009be3  pop     r14
0x180009be5  pop     r13
0x180009be7  pop     r12
0x180009be9  pop     rdi
0x180009bea  pop     rsi
0x180009beb  pop     rbp
0x180009bec  retn
0x180009bed  mov     rcx, [rsp+288h]; this
0x180009bf5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009bfc  mov     edx, 0A0Bh; void *
0x180009c01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009c0d  mov     rcx, [rsp+288h]; this
0x180009c15  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009c1c  mov     edx, 0A0Bh; void *
0x180009c21  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
