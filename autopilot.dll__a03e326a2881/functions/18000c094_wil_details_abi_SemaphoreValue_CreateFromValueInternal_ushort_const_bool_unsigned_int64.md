# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000c094`
- end: `0x18000c2d3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b848`
- `0x18000bc20`

## callees

- `0x1800045b0`
- `0x18000c094`
- `0x18000d5a8`
- `0x1800105f4`
- `0x180011160`
- `0x180012104`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c15d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c203`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c15d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c24b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c24b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c1c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c1b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c256`

## string_xrefs

- `0x18000c2a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c2c1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000c094  mov     [rsp+arg_8], rbx
0x18000c099  push    rbp
0x18000c09a  push    rsi
0x18000c09b  push    rdi
0x18000c09c  push    r12
0x18000c09e  push    r13
0x18000c0a0  push    r14
0x18000c0a2  push    r15
0x18000c0a4  sub     rsp, 250h
0x18000c0ab  mov     rax, cs:__security_cookie
0x18000c0b2  xor     rax, rsp
0x18000c0b5  mov     [rsp+288h+var_48], rax
0x18000c0bd  mov     rax, 0C000000000000000h
0x18000c0c7  mov     rsi, r9
0x18000c0ca  mov     r8, rdx
0x18000c0cd  mov     rbx, rcx
0x18000c0d0  test    rax, r9
0x18000c0d3  jnz     loc_18000C2B3
0x18000c0d9  xor     r12d, r12d
0x18000c0dc  lea     rax, [rsp+288h+Name]
0x18000c0e1  mov     r13d, 104h
0x18000c0e7  mov     ecx, 7FFFFFFEh
0x18000c0ec  mov     edx, r13d
0x18000c0ef  lea     ebp, [r12+1]
0x18000c0f4  test    rcx, rcx
0x18000c0f7  jz      short loc_18000C117
0x18000c0f9  movzx   r9d, word ptr [r8]
0x18000c0fd  test    r9w, r9w
0x18000c101  jz      short loc_18000C117
0x18000c103  mov     [rax], r9w
0x18000c107  add     r8, 2
0x18000c10b  add     rax, 2
0x18000c10f  sub     rcx, rbp
0x18000c112  sub     rdx, rbp
0x18000c115  jnz     short loc_18000C0F4
0x18000c117  test    rdx, rdx
0x18000c11a  lea     rcx, [rax-2]
0x18000c11e  lea     r8, aP0; "_p0"
0x18000c125  mov     rdx, r13; unsigned __int64
0x18000c128  cmovnz  rcx, rax
0x18000c12c  mov     [rcx], r12w
0x18000c130  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000c135  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c13a  mov     edx, esi
0x18000c13c  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000c144  and     edx, 7FFFFFFFh; lInitialCount
0x18000c14a  mov     [rsp+288h+dwFlags], r12d; int
0x18000c14f  mov     r8d, ebp
0x18000c152  lea     r9, [rsp+288h+Name]; lpName
0x18000c157  cmova   r8d, edx; lMaximumCount
0x18000c15b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000c15d  call    cs:__imp_CreateSemaphoreExW
0x18000c163  mov     r15, rax
0x18000c166  test    rax, rax
0x18000c169  jnz     short loc_18000C199
0x18000c16b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c170  mov     edi, eax
0x18000c172  test    eax, eax
0x18000c174  jns     short loc_18000C1CD
0x18000c176  mov     rcx, [rsp+288h]; this
0x18000c17e  lea     r8, aWil; "wil"
0x18000c185  mov     r9d, eax; char *
0x18000c188  mov     edx, 8Bh; void *
0x18000c18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c192  mov     eax, edi
0x18000c194  jmp     loc_18000C26E
0x18000c199  call    cs:__imp_GetLastError
0x18000c19f  mov     rdi, [rbx]
0x18000c1a2  test    rdi, rdi
0x18000c1a5  jz      short loc_18000C1CA
0x18000c1a7  call    cs:__imp_GetLastError
0x18000c1ad  mov     rcx, rdi; hObject
0x18000c1b0  mov     r14d, eax
0x18000c1b3  call    cs:__imp_CloseHandle
0x18000c1b9  test    eax, eax
0x18000c1bb  jz      loc_18000C2B9
0x18000c1c1  mov     ecx, r14d; dwErrCode
0x18000c1c4  call    cs:__imp_SetLastError
0x18000c1ca  mov     [rbx], r15
0x18000c1cd  lea     r8, asc_180036368; "h"
0x18000c1d4  shr     rsi, 1Fh
0x18000c1d8  mov     rdx, r13; unsigned __int64
0x18000c1db  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000c1e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c1e5  test    esi, esi
0x18000c1e7  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000c1ef  lea     r9, [rsp+288h+Name]; lpName
0x18000c1f4  mov     [rsp+288h+dwFlags], r12d; int
0x18000c1f9  cmovnz  ebp, esi
0x18000c1fc  mov     edx, esi; lInitialCount
0x18000c1fe  mov     r8d, ebp; lMaximumCount
0x18000c201  xor     ecx, ecx; lpSemaphoreAttributes
0x18000c203  call    cs:__imp_CreateSemaphoreExW
0x18000c209  mov     rbp, rax
0x18000c20c  test    rax, rax
0x18000c20f  jnz     short loc_18000C23C
0x18000c211  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c216  mov     ebx, eax
0x18000c218  test    eax, eax
0x18000c21a  jns     short loc_18000C26C
0x18000c21c  mov     rcx, [rsp+288h]; this
0x18000c224  lea     r8, aWil; "wil"
0x18000c22b  mov     r9d, eax; char *
0x18000c22e  mov     edx, 90h; void *
0x18000c233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c238  mov     eax, ebx
0x18000c23a  jmp     short loc_18000C26E
0x18000c23c  call    cs:__imp_GetLastError
0x18000c242  mov     rdi, [rbx+8]
0x18000c246  test    rdi, rdi
0x18000c249  jz      short loc_18000C268
0x18000c24b  call    cs:__imp_GetLastError
0x18000c251  mov     rcx, rdi; hObject
0x18000c254  mov     esi, eax
0x18000c256  call    cs:__imp_CloseHandle
0x18000c25c  test    eax, eax
0x18000c25e  jz      short loc_18000C299
0x18000c260  mov     ecx, esi; dwErrCode
0x18000c262  call    cs:__imp_SetLastError
0x18000c268  mov     [rbx+8], rbp
0x18000c26c  xor     eax, eax
0x18000c26e  mov     rcx, [rsp+288h+var_48]
0x18000c276  xor     rcx, rsp; StackCookie
0x18000c279  call    __security_check_cookie
0x18000c27e  mov     rbx, [rsp+288h+arg_8]
0x18000c286  add     rsp, 250h
0x18000c28d  pop     r15
0x18000c28f  pop     r14
0x18000c291  pop     r13
0x18000c293  pop     r12
0x18000c295  pop     rdi
0x18000c296  pop     rsi
0x18000c297  pop     rbp
0x18000c298  retn
0x18000c299  mov     rcx, [rsp+288h]; this
0x18000c2a1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c2a8  mov     edx, 0A0Bh; void *
0x18000c2ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c2b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c2b9  mov     rcx, [rsp+288h]; this
0x18000c2c1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c2c8  mov     edx, 0A0Bh; void *
0x18000c2cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
