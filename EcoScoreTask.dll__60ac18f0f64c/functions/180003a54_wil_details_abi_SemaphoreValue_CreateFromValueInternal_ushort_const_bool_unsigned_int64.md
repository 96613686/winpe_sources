# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003a54`
- end: `0x180003c7e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003648`

## callees

- `0x180003a54`
- `0x180004658`
- `0x180005e6c`
- `0x180006e20`
- `0x1800078e4`
- `0x1800078f4`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c03`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b18`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bbb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b18`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bbb`

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
0x180003a54  mov     [rsp+arg_8], rbx
0x180003a59  mov     [rsp+arg_10], rbp
0x180003a5e  push    rsi
0x180003a5f  push    rdi
0x180003a60  push    r12
0x180003a62  push    r14
0x180003a64  push    r15
0x180003a66  sub     rsp, 250h
0x180003a6d  mov     rax, cs:__security_cookie
0x180003a74  xor     rax, rsp
0x180003a77  mov     [rsp+278h+var_38], rax
0x180003a7f  mov     rax, 0C000000000000000h
0x180003a89  mov     rbp, r9
0x180003a8c  mov     r8, rdx
0x180003a8f  mov     rbx, rcx
0x180003a92  test    rax, r9
0x180003a95  jnz     loc_180003C65
0x180003a9b  xor     r12d, r12d
0x180003a9e  lea     rax, [rsp+278h+Name]
0x180003aa3  mov     ecx, 7FFFFFFEh
0x180003aa8  mov     edx, 104h
0x180003aad  lea     esi, [r12+1]
0x180003ab2  test    rcx, rcx
0x180003ab5  jz      short loc_180003AD5
0x180003ab7  movzx   r9d, word ptr [r8]
0x180003abb  test    r9w, r9w
0x180003abf  jz      short loc_180003AD5
0x180003ac1  mov     [rax], r9w
0x180003ac5  add     r8, 2
0x180003ac9  add     rax, 2
0x180003acd  sub     rcx, rsi
0x180003ad0  sub     rdx, rsi; unsigned __int64
0x180003ad3  jnz     short loc_180003AB2
0x180003ad5  test    rdx, rdx
0x180003ad8  lea     rcx, [rax-2]
0x180003adc  lea     r8, aP0; "_p0"
0x180003ae3  cmovnz  rcx, rax
0x180003ae7  mov     [rcx], r12w
0x180003aeb  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003af0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003af5  mov     edx, ebp
0x180003af7  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003aff  and     edx, 7FFFFFFFh; lInitialCount
0x180003b05  mov     [rsp+278h+dwFlags], r12d; int
0x180003b0a  mov     r8d, esi
0x180003b0d  lea     r9, [rsp+278h+Name]; lpName
0x180003b12  cmova   r8d, edx; lMaximumCount
0x180003b16  xor     ecx, ecx; lpSemaphoreAttributes
0x180003b18  call    cs:__imp_CreateSemaphoreExW
0x180003b1e  mov     r15, rax
0x180003b21  test    rax, rax
0x180003b24  jnz     short loc_180003B54
0x180003b26  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b2b  mov     edi, eax
0x180003b2d  test    eax, eax
0x180003b2f  jns     short loc_180003B88
0x180003b31  mov     rcx, [rsp+278h]; this
0x180003b39  lea     r8, aWil; "wil"
0x180003b40  mov     r9d, eax; char *
0x180003b43  mov     edx, 8Bh; void *
0x180003b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b4d  mov     eax, edi
0x180003b4f  jmp     loc_180003C26
0x180003b54  call    cs:__imp_GetLastError
0x180003b5a  mov     rdi, [rbx]
0x180003b5d  test    rdi, rdi
0x180003b60  jz      short loc_180003B85
0x180003b62  call    cs:__imp_GetLastError
0x180003b68  mov     rcx, rdi; hObject
0x180003b6b  mov     r14d, eax
0x180003b6e  call    cs:__imp_CloseHandle
0x180003b74  test    eax, eax
0x180003b76  jz      loc_180003C6B
0x180003b7c  mov     ecx, r14d; dwErrCode
0x180003b7f  call    cs:__imp_SetLastError
0x180003b85  mov     [rbx], r15
0x180003b88  lea     r8, asc_18000A908; "h"
0x180003b8f  shr     rbp, 1Fh
0x180003b93  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003b98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b9d  test    ebp, ebp
0x180003b9f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003ba7  lea     r9, [rsp+278h+Name]; lpName
0x180003bac  mov     [rsp+278h+dwFlags], r12d; int
0x180003bb1  cmovnz  esi, ebp
0x180003bb4  mov     edx, ebp; lInitialCount
0x180003bb6  mov     r8d, esi; lMaximumCount
0x180003bb9  xor     ecx, ecx; lpSemaphoreAttributes
0x180003bbb  call    cs:__imp_CreateSemaphoreExW
0x180003bc1  mov     rsi, rax
0x180003bc4  test    rax, rax
0x180003bc7  jnz     short loc_180003BF4
0x180003bc9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bce  mov     ebx, eax
0x180003bd0  test    eax, eax
0x180003bd2  jns     short loc_180003C24
0x180003bd4  mov     rcx, [rsp+278h]; this
0x180003bdc  lea     r8, aWil; "wil"
0x180003be3  mov     r9d, eax; char *
0x180003be6  mov     edx, 90h; void *
0x180003beb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bf0  mov     eax, ebx
0x180003bf2  jmp     short loc_180003C26
0x180003bf4  call    cs:__imp_GetLastError
0x180003bfa  mov     rdi, [rbx+8]
0x180003bfe  test    rdi, rdi
0x180003c01  jz      short loc_180003C20
0x180003c03  call    cs:__imp_GetLastError
0x180003c09  mov     rcx, rdi; hObject
0x180003c0c  mov     ebp, eax
0x180003c0e  call    cs:__imp_CloseHandle
0x180003c14  test    eax, eax
0x180003c16  jz      short loc_180003C52
0x180003c18  mov     ecx, ebp; dwErrCode
0x180003c1a  call    cs:__imp_SetLastError
0x180003c20  mov     [rbx+8], rsi
0x180003c24  xor     eax, eax
0x180003c26  mov     rcx, [rsp+278h+var_38]
0x180003c2e  xor     rcx, rsp; StackCookie
0x180003c31  call    __security_check_cookie
0x180003c36  lea     r11, [rsp+278h+var_28]
0x180003c3e  mov     rbx, [r11+38h]
0x180003c42  mov     rbp, [r11+40h]
0x180003c46  mov     rsp, r11
0x180003c49  pop     r15
0x180003c4b  pop     r14
0x180003c4d  pop     r12
0x180003c4f  pop     rdi
0x180003c50  pop     rsi
0x180003c51  retn
0x180003c52  mov     rcx, [rsp+278h]; this
0x180003c5a  mov     edx, 0A0Bh; void *
0x180003c5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c65  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c6b  mov     rcx, [rsp+278h]; this
0x180003c73  mov     edx, 0A0Bh; void *
0x180003c78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
