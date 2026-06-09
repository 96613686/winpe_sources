# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000f33c`
- end: `0x18000f57b`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `575`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ef68`
- `0x180012814`

## callees

- `0x1800026b0`
- `0x18000f33c`
- `0x18000fca8`
- `0x180010b84`
- `0x1800114c4`
- `0x180011aec`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f405`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f4ab`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f405`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f46c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f50a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f46c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4fe`

## string_xrefs

- `0x18000f549`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f569`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x18000f33c  mov     [rsp+arg_8], rbx
0x18000f341  push    rbp
0x18000f342  push    rsi
0x18000f343  push    rdi
0x18000f344  push    r12
0x18000f346  push    r13
0x18000f348  push    r14
0x18000f34a  push    r15
0x18000f34c  sub     rsp, 250h
0x18000f353  mov     rax, cs:__security_cookie
0x18000f35a  xor     rax, rsp
0x18000f35d  mov     [rsp+288h+var_48], rax
0x18000f365  mov     rax, 0C000000000000000h
0x18000f36f  mov     rsi, r9
0x18000f372  mov     r8, rdx
0x18000f375  mov     rbx, rcx
0x18000f378  test    rax, r9
0x18000f37b  jnz     loc_18000F55B
0x18000f381  xor     r12d, r12d
0x18000f384  lea     rax, [rsp+288h+Name]
0x18000f389  mov     r13d, 104h
0x18000f38f  mov     ecx, 7FFFFFFEh
0x18000f394  mov     edx, r13d
0x18000f397  lea     ebp, [r12+1]
0x18000f39c  test    rcx, rcx
0x18000f39f  jz      short loc_18000F3BF
0x18000f3a1  movzx   r9d, word ptr [r8]
0x18000f3a5  test    r9w, r9w
0x18000f3a9  jz      short loc_18000F3BF
0x18000f3ab  mov     [rax], r9w
0x18000f3af  add     r8, 2
0x18000f3b3  add     rax, 2
0x18000f3b7  sub     rcx, rbp
0x18000f3ba  sub     rdx, rbp
0x18000f3bd  jnz     short loc_18000F39C
0x18000f3bf  test    rdx, rdx
0x18000f3c2  lea     rcx, [rax-2]
0x18000f3c6  lea     r8, aP0; "_p0"
0x18000f3cd  mov     rdx, r13; unsigned __int64
0x18000f3d0  cmovnz  rcx, rax
0x18000f3d4  mov     [rcx], r12w
0x18000f3d8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000f3dd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f3e2  mov     edx, esi
0x18000f3e4  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000f3ec  and     edx, 7FFFFFFFh; lInitialCount
0x18000f3f2  mov     [rsp+288h+dwFlags], r12d; int
0x18000f3f7  mov     r8d, ebp
0x18000f3fa  lea     r9, [rsp+288h+Name]; lpName
0x18000f3ff  cmova   r8d, edx; lMaximumCount
0x18000f403  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f405  call    cs:__imp_CreateSemaphoreExW
0x18000f40b  mov     r15, rax
0x18000f40e  test    rax, rax
0x18000f411  jnz     short loc_18000F441
0x18000f413  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f418  mov     edi, eax
0x18000f41a  test    eax, eax
0x18000f41c  jns     short loc_18000F475
0x18000f41e  mov     rcx, [rsp+288h]; this
0x18000f426  lea     r8, aWil; "wil"
0x18000f42d  mov     r9d, eax; char *
0x18000f430  mov     edx, 8Bh; void *
0x18000f435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f43a  mov     eax, edi
0x18000f43c  jmp     loc_18000F516
0x18000f441  call    cs:__imp_GetLastError
0x18000f447  mov     rdi, [rbx]
0x18000f44a  test    rdi, rdi
0x18000f44d  jz      short loc_18000F472
0x18000f44f  call    cs:__imp_GetLastError
0x18000f455  mov     rcx, rdi; hObject
0x18000f458  mov     r14d, eax
0x18000f45b  call    cs:__imp_CloseHandle
0x18000f461  test    eax, eax
0x18000f463  jz      loc_18000F561
0x18000f469  mov     ecx, r14d; dwErrCode
0x18000f46c  call    cs:__imp_SetLastError
0x18000f472  mov     [rbx], r15
0x18000f475  lea     r8, asc_180053518; "h"
0x18000f47c  shr     rsi, 1Fh
0x18000f480  mov     rdx, r13; unsigned __int64
0x18000f483  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000f488  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f48d  test    esi, esi
0x18000f48f  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000f497  lea     r9, [rsp+288h+Name]; lpName
0x18000f49c  mov     [rsp+288h+dwFlags], r12d; int
0x18000f4a1  cmovnz  ebp, esi
0x18000f4a4  mov     edx, esi; lInitialCount
0x18000f4a6  mov     r8d, ebp; lMaximumCount
0x18000f4a9  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f4ab  call    cs:__imp_CreateSemaphoreExW
0x18000f4b1  mov     rbp, rax
0x18000f4b4  test    rax, rax
0x18000f4b7  jnz     short loc_18000F4E4
0x18000f4b9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f4be  mov     ebx, eax
0x18000f4c0  test    eax, eax
0x18000f4c2  jns     short loc_18000F514
0x18000f4c4  mov     rcx, [rsp+288h]; this
0x18000f4cc  lea     r8, aWil; "wil"
0x18000f4d3  mov     r9d, eax; char *
0x18000f4d6  mov     edx, 90h; void *
0x18000f4db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4e0  mov     eax, ebx
0x18000f4e2  jmp     short loc_18000F516
0x18000f4e4  call    cs:__imp_GetLastError
0x18000f4ea  mov     rdi, [rbx+8]
0x18000f4ee  test    rdi, rdi
0x18000f4f1  jz      short loc_18000F510
0x18000f4f3  call    cs:__imp_GetLastError
0x18000f4f9  mov     rcx, rdi; hObject
0x18000f4fc  mov     esi, eax
0x18000f4fe  call    cs:__imp_CloseHandle
0x18000f504  test    eax, eax
0x18000f506  jz      short loc_18000F541
0x18000f508  mov     ecx, esi; dwErrCode
0x18000f50a  call    cs:__imp_SetLastError
0x18000f510  mov     [rbx+8], rbp
0x18000f514  xor     eax, eax
0x18000f516  mov     rcx, [rsp+288h+var_48]
0x18000f51e  xor     rcx, rsp; StackCookie
0x18000f521  call    __security_check_cookie
0x18000f526  mov     rbx, [rsp+288h+arg_8]
0x18000f52e  add     rsp, 250h
0x18000f535  pop     r15
0x18000f537  pop     r14
0x18000f539  pop     r13
0x18000f53b  pop     r12
0x18000f53d  pop     rdi
0x18000f53e  pop     rsi
0x18000f53f  pop     rbp
0x18000f540  retn
0x18000f541  mov     rcx, [rsp+288h]; this
0x18000f549  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f550  mov     edx, 0A0Bh; void *
0x18000f555  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f55b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f561  mov     rcx, [rsp+288h]; this
0x18000f569  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f570  mov     edx, 0A0Bh; void *
0x18000f575  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
