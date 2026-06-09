# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004988`
- end: `0x180004bb2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800045b8`
- `0x18000896c`

## callees

- `0x180002bc0`
- `0x180004988`
- `0x1800052d8`
- `0x180006244`
- `0x180006b84`
- `0x180007198`
- `0x1800071a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a4c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004aef`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a4c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ab3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ab3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b42`

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
0x180004988  mov     [rsp+arg_8], rbx
0x18000498d  mov     [rsp+arg_10], rbp
0x180004992  push    rsi
0x180004993  push    rdi
0x180004994  push    r12
0x180004996  push    r14
0x180004998  push    r15
0x18000499a  sub     rsp, 250h
0x1800049a1  mov     rax, cs:__security_cookie
0x1800049a8  xor     rax, rsp
0x1800049ab  mov     [rsp+278h+var_38], rax
0x1800049b3  mov     rax, 0C000000000000000h
0x1800049bd  mov     rbp, r9
0x1800049c0  mov     r8, rdx
0x1800049c3  mov     rbx, rcx
0x1800049c6  test    rax, r9
0x1800049c9  jnz     loc_180004B99
0x1800049cf  xor     r12d, r12d
0x1800049d2  lea     rax, [rsp+278h+Name]
0x1800049d7  mov     ecx, 7FFFFFFEh
0x1800049dc  mov     edx, 104h
0x1800049e1  lea     esi, [r12+1]
0x1800049e6  test    rcx, rcx
0x1800049e9  jz      short loc_180004A09
0x1800049eb  movzx   r9d, word ptr [r8]
0x1800049ef  test    r9w, r9w
0x1800049f3  jz      short loc_180004A09
0x1800049f5  mov     [rax], r9w
0x1800049f9  add     r8, 2
0x1800049fd  add     rax, 2
0x180004a01  sub     rcx, rsi
0x180004a04  sub     rdx, rsi; unsigned __int64
0x180004a07  jnz     short loc_1800049E6
0x180004a09  test    rdx, rdx
0x180004a0c  lea     rcx, [rax-2]
0x180004a10  lea     r8, aP0; "_p0"
0x180004a17  cmovnz  rcx, rax
0x180004a1b  mov     [rcx], r12w
0x180004a1f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004a24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a29  mov     edx, ebp
0x180004a2b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a33  and     edx, 7FFFFFFFh; lInitialCount
0x180004a39  mov     [rsp+278h+dwFlags], r12d; int
0x180004a3e  mov     r8d, esi
0x180004a41  lea     r9, [rsp+278h+Name]; lpName
0x180004a46  cmova   r8d, edx; lMaximumCount
0x180004a4a  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a4c  call    cs:__imp_CreateSemaphoreExW
0x180004a52  mov     r15, rax
0x180004a55  test    rax, rax
0x180004a58  jnz     short loc_180004A88
0x180004a5a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a5f  mov     edi, eax
0x180004a61  test    eax, eax
0x180004a63  jns     short loc_180004ABC
0x180004a65  mov     rcx, [rsp+278h]; this
0x180004a6d  lea     r8, aWil; "wil"
0x180004a74  mov     r9d, eax; char *
0x180004a77  mov     edx, 8Bh; void *
0x180004a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a81  mov     eax, edi
0x180004a83  jmp     loc_180004B5A
0x180004a88  call    cs:__imp_GetLastError
0x180004a8e  mov     rdi, [rbx]
0x180004a91  test    rdi, rdi
0x180004a94  jz      short loc_180004AB9
0x180004a96  call    cs:__imp_GetLastError
0x180004a9c  mov     rcx, rdi; hObject
0x180004a9f  mov     r14d, eax
0x180004aa2  call    cs:__imp_CloseHandle
0x180004aa8  test    eax, eax
0x180004aaa  jz      loc_180004B9F
0x180004ab0  mov     ecx, r14d; dwErrCode
0x180004ab3  call    cs:__imp_SetLastError
0x180004ab9  mov     [rbx], r15
0x180004abc  lea     r8, asc_180013DD8; "h"
0x180004ac3  shr     rbp, 1Fh
0x180004ac7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004acc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004ad1  test    ebp, ebp
0x180004ad3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004adb  lea     r9, [rsp+278h+Name]; lpName
0x180004ae0  mov     [rsp+278h+dwFlags], r12d; int
0x180004ae5  cmovnz  esi, ebp
0x180004ae8  mov     edx, ebp; lInitialCount
0x180004aea  mov     r8d, esi; lMaximumCount
0x180004aed  xor     ecx, ecx; lpSemaphoreAttributes
0x180004aef  call    cs:__imp_CreateSemaphoreExW
0x180004af5  mov     rsi, rax
0x180004af8  test    rax, rax
0x180004afb  jnz     short loc_180004B28
0x180004afd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004b02  mov     ebx, eax
0x180004b04  test    eax, eax
0x180004b06  jns     short loc_180004B58
0x180004b08  mov     rcx, [rsp+278h]; this
0x180004b10  lea     r8, aWil; "wil"
0x180004b17  mov     r9d, eax; char *
0x180004b1a  mov     edx, 90h; void *
0x180004b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b24  mov     eax, ebx
0x180004b26  jmp     short loc_180004B5A
0x180004b28  call    cs:__imp_GetLastError
0x180004b2e  mov     rdi, [rbx+8]
0x180004b32  test    rdi, rdi
0x180004b35  jz      short loc_180004B54
0x180004b37  call    cs:__imp_GetLastError
0x180004b3d  mov     rcx, rdi; hObject
0x180004b40  mov     ebp, eax
0x180004b42  call    cs:__imp_CloseHandle
0x180004b48  test    eax, eax
0x180004b4a  jz      short loc_180004B86
0x180004b4c  mov     ecx, ebp; dwErrCode
0x180004b4e  call    cs:__imp_SetLastError
0x180004b54  mov     [rbx+8], rsi
0x180004b58  xor     eax, eax
0x180004b5a  mov     rcx, [rsp+278h+var_38]
0x180004b62  xor     rcx, rsp; StackCookie
0x180004b65  call    __security_check_cookie
0x180004b6a  lea     r11, [rsp+278h+var_28]
0x180004b72  mov     rbx, [r11+38h]
0x180004b76  mov     rbp, [r11+40h]
0x180004b7a  mov     rsp, r11
0x180004b7d  pop     r15
0x180004b7f  pop     r14
0x180004b81  pop     r12
0x180004b83  pop     rdi
0x180004b84  pop     rsi
0x180004b85  retn
0x180004b86  mov     rcx, [rsp+278h]; this
0x180004b8e  mov     edx, 0A0Bh; void *
0x180004b93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b99  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b9f  mov     rcx, [rsp+278h]; this
0x180004ba7  mov     edx, 0A0Bh; void *
0x180004bac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
