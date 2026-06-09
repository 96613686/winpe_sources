# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003b10`
- end: `0x180003d21`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `529`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037a8`

## callees

- `0x180001960`
- `0x180003b10`
- `0x18000438c`
- `0x1800052a8`
- `0x180005b90`
- `0x1800060bc`
- `0x1800060cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bd9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c77`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bd9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cc2`

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
  int v16; // r9d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  unsigned int v21; // edx
  const char *v22; // r8
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  int v27; // r9d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  unsigned int v31; // edx
  const char *v32; // r8
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF

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
    v19 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v21, v22);
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
        (wil::details::in1diag3 *)0x8B,
        (unsigned int)"wil",
        (wil::details *)(unsigned int)LastErrorFailHr,
        v16);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)0x90,
        (unsigned int)"wil",
        (wil::details *)(unsigned int)v26,
        v27);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003b10  mov     [rsp+arg_8], rbx
0x180003b15  push    rbp
0x180003b16  push    rsi
0x180003b17  push    rdi
0x180003b18  push    r12
0x180003b1a  push    r13
0x180003b1c  push    r14
0x180003b1e  push    r15
0x180003b20  sub     rsp, 250h
0x180003b27  mov     rax, cs:__security_cookie
0x180003b2e  xor     rax, rsp
0x180003b31  mov     [rsp+288h+var_48], rax
0x180003b39  mov     rax, 0C000000000000000h
0x180003b43  mov     rsi, r9
0x180003b46  mov     r8, rdx
0x180003b49  mov     rbx, rcx
0x180003b4c  test    rax, r9
0x180003b4f  jnz     loc_180003D10
0x180003b55  xor     r12d, r12d
0x180003b58  lea     rax, [rsp+288h+Name]
0x180003b5d  mov     r13d, 104h
0x180003b63  mov     ecx, 7FFFFFFEh
0x180003b68  mov     edx, r13d
0x180003b6b  lea     ebp, [r12+1]
0x180003b70  test    rcx, rcx
0x180003b73  jz      short loc_180003B93
0x180003b75  movzx   r9d, word ptr [r8]
0x180003b79  test    r9w, r9w
0x180003b7d  jz      short loc_180003B93
0x180003b7f  mov     [rax], r9w
0x180003b83  add     r8, 2
0x180003b87  add     rax, 2
0x180003b8b  sub     rcx, rbp
0x180003b8e  sub     rdx, rbp
0x180003b91  jnz     short loc_180003B70
0x180003b93  test    rdx, rdx
0x180003b96  lea     rcx, [rax-2]
0x180003b9a  lea     r8, aP0; "_p0"
0x180003ba1  mov     rdx, r13; unsigned __int64
0x180003ba4  cmovnz  rcx, rax
0x180003ba8  mov     [rcx], r12w
0x180003bac  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003bb1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003bb6  mov     edx, esi
0x180003bb8  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003bc0  and     edx, 7FFFFFFFh; lInitialCount
0x180003bc6  mov     [rsp+288h+dwFlags], r12d; dwFlags
0x180003bcb  mov     r8d, ebp
0x180003bce  lea     r9, [rsp+288h+Name]; lpName
0x180003bd3  cmova   r8d, edx; lMaximumCount
0x180003bd7  xor     ecx, ecx; lpSemaphoreAttributes
0x180003bd9  call    cs:__imp_CreateSemaphoreExW
0x180003bdf  mov     r15, rax
0x180003be2  test    rax, rax
0x180003be5  jnz     short loc_180003C0D
0x180003be7  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bec  mov     edi, eax
0x180003bee  test    eax, eax
0x180003bf0  jns     short loc_180003C41
0x180003bf2  mov     r8d, eax; wil::details *
0x180003bf5  lea     rdx, aWil; "wil"
0x180003bfc  mov     ecx, 8Bh; this
0x180003c01  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180003c06  mov     eax, edi
0x180003c08  jmp     loc_180003CDA
0x180003c0d  call    cs:__imp_GetLastError
0x180003c13  mov     rdi, [rbx]
0x180003c16  test    rdi, rdi
0x180003c19  jz      short loc_180003C3E
0x180003c1b  call    cs:__imp_GetLastError
0x180003c21  mov     rcx, rdi; hObject
0x180003c24  mov     r14d, eax
0x180003c27  call    cs:__imp_CloseHandle
0x180003c2d  test    eax, eax
0x180003c2f  jz      loc_180003D16
0x180003c35  mov     ecx, r14d; dwErrCode
0x180003c38  call    cs:__imp_SetLastError
0x180003c3e  mov     [rbx], r15
0x180003c41  lea     r8, asc_180015368; "h"
0x180003c48  shr     rsi, 1Fh
0x180003c4c  mov     rdx, r13; unsigned __int64
0x180003c4f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003c54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c59  test    esi, esi
0x180003c5b  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003c63  lea     r9, [rsp+288h+Name]; lpName
0x180003c68  mov     [rsp+288h+dwFlags], r12d; dwFlags
0x180003c6d  cmovnz  ebp, esi
0x180003c70  mov     edx, esi; lInitialCount
0x180003c72  mov     r8d, ebp; lMaximumCount
0x180003c75  xor     ecx, ecx; lpSemaphoreAttributes
0x180003c77  call    cs:__imp_CreateSemaphoreExW
0x180003c7d  mov     rbp, rax
0x180003c80  test    rax, rax
0x180003c83  jnz     short loc_180003CA8
0x180003c85  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c8a  mov     ebx, eax
0x180003c8c  test    eax, eax
0x180003c8e  jns     short loc_180003CD8
0x180003c90  mov     r8d, eax; wil::details *
0x180003c93  lea     rdx, aWil; "wil"
0x180003c9a  mov     ecx, 90h; this
0x180003c9f  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180003ca4  mov     eax, ebx
0x180003ca6  jmp     short loc_180003CDA
0x180003ca8  call    cs:__imp_GetLastError
0x180003cae  mov     rdi, [rbx+8]
0x180003cb2  test    rdi, rdi
0x180003cb5  jz      short loc_180003CD4
0x180003cb7  call    cs:__imp_GetLastError
0x180003cbd  mov     rcx, rdi; hObject
0x180003cc0  mov     esi, eax
0x180003cc2  call    cs:__imp_CloseHandle
0x180003cc8  test    eax, eax
0x180003cca  jz      short loc_180003D05
0x180003ccc  mov     ecx, esi; dwErrCode
0x180003cce  call    cs:__imp_SetLastError
0x180003cd4  mov     [rbx+8], rbp
0x180003cd8  xor     eax, eax
0x180003cda  mov     rcx, [rsp+288h+var_48]
0x180003ce2  xor     rcx, rsp; StackCookie
0x180003ce5  call    __security_check_cookie
0x180003cea  mov     rbx, [rsp+288h+arg_8]
0x180003cf2  add     rsp, 250h
0x180003cf9  pop     r15
0x180003cfb  pop     r14
0x180003cfd  pop     r13
0x180003cff  pop     r12
0x180003d01  pop     rdi
0x180003d02  pop     rsi
0x180003d03  pop     rbp
0x180003d04  retn
0x180003d05  mov     ecx, 0A0Bh; this
0x180003d0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003d10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003d16  mov     ecx, 0A0Bh; this
0x180003d1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
```
