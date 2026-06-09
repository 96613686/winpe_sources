# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180006990`
- end: `0x180006bba`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800061c8`
- `0x180006598`

## callees

- `0x180003870`
- `0x180006990`
- `0x180007930`
- `0x18000a0f4`
- `0x18000ab70`
- `0x18000bf6c`
- `0x18000bf7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006a54`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006af7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006a54`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4a`

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
0x180006990  mov     [rsp+arg_8], rbx
0x180006995  mov     [rsp+arg_10], rbp
0x18000699a  push    rsi
0x18000699b  push    rdi
0x18000699c  push    r12
0x18000699e  push    r14
0x1800069a0  push    r15
0x1800069a2  sub     rsp, 250h
0x1800069a9  mov     rax, cs:__security_cookie
0x1800069b0  xor     rax, rsp
0x1800069b3  mov     [rsp+278h+var_38], rax
0x1800069bb  mov     rax, 0C000000000000000h
0x1800069c5  mov     rbp, r9
0x1800069c8  mov     r8, rdx
0x1800069cb  mov     rbx, rcx
0x1800069ce  test    rax, r9
0x1800069d1  jnz     loc_180006BA1
0x1800069d7  xor     r12d, r12d
0x1800069da  lea     rax, [rsp+278h+Name]
0x1800069df  mov     ecx, 7FFFFFFEh
0x1800069e4  mov     edx, 104h
0x1800069e9  lea     esi, [r12+1]
0x1800069ee  test    rcx, rcx
0x1800069f1  jz      short loc_180006A11
0x1800069f3  movzx   r9d, word ptr [r8]
0x1800069f7  test    r9w, r9w
0x1800069fb  jz      short loc_180006A11
0x1800069fd  mov     [rax], r9w
0x180006a01  add     r8, 2
0x180006a05  add     rax, 2
0x180006a09  sub     rcx, rsi
0x180006a0c  sub     rdx, rsi; unsigned __int64
0x180006a0f  jnz     short loc_1800069EE
0x180006a11  test    rdx, rdx
0x180006a14  lea     rcx, [rax-2]
0x180006a18  lea     r8, aP0; "_p0"
0x180006a1f  cmovnz  rcx, rax
0x180006a23  mov     [rcx], r12w
0x180006a27  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180006a2c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006a31  mov     edx, ebp
0x180006a33  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006a3b  and     edx, 7FFFFFFFh; lInitialCount
0x180006a41  mov     [rsp+278h+dwFlags], r12d; int
0x180006a46  mov     r8d, esi
0x180006a49  lea     r9, [rsp+278h+Name]; lpName
0x180006a4e  cmova   r8d, edx; lMaximumCount
0x180006a52  xor     ecx, ecx; lpSemaphoreAttributes
0x180006a54  call    cs:__imp_CreateSemaphoreExW
0x180006a5a  mov     r15, rax
0x180006a5d  test    rax, rax
0x180006a60  jnz     short loc_180006A90
0x180006a62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006a67  mov     edi, eax
0x180006a69  test    eax, eax
0x180006a6b  jns     short loc_180006AC4
0x180006a6d  mov     rcx, [rsp+278h]; this
0x180006a75  lea     r8, aWil; "wil"
0x180006a7c  mov     r9d, eax; char *
0x180006a7f  mov     edx, 8Bh; void *
0x180006a84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a89  mov     eax, edi
0x180006a8b  jmp     loc_180006B62
0x180006a90  call    cs:__imp_GetLastError
0x180006a96  mov     rdi, [rbx]
0x180006a99  test    rdi, rdi
0x180006a9c  jz      short loc_180006AC1
0x180006a9e  call    cs:__imp_GetLastError
0x180006aa4  mov     rcx, rdi; hObject
0x180006aa7  mov     r14d, eax
0x180006aaa  call    cs:__imp_CloseHandle
0x180006ab0  test    eax, eax
0x180006ab2  jz      loc_180006BA7
0x180006ab8  mov     ecx, r14d; dwErrCode
0x180006abb  call    cs:__imp_SetLastError
0x180006ac1  mov     [rbx], r15
0x180006ac4  lea     r8, asc_180036DD8; "h"
0x180006acb  shr     rbp, 1Fh
0x180006acf  lea     rcx, [rsp+278h+Name]; wchar_t *
0x180006ad4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180006ad9  test    ebp, ebp
0x180006adb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006ae3  lea     r9, [rsp+278h+Name]; lpName
0x180006ae8  mov     [rsp+278h+dwFlags], r12d; int
0x180006aed  cmovnz  esi, ebp
0x180006af0  mov     edx, ebp; lInitialCount
0x180006af2  mov     r8d, esi; lMaximumCount
0x180006af5  xor     ecx, ecx; lpSemaphoreAttributes
0x180006af7  call    cs:__imp_CreateSemaphoreExW
0x180006afd  mov     rsi, rax
0x180006b00  test    rax, rax
0x180006b03  jnz     short loc_180006B30
0x180006b05  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006b0a  mov     ebx, eax
0x180006b0c  test    eax, eax
0x180006b0e  jns     short loc_180006B60
0x180006b10  mov     rcx, [rsp+278h]; this
0x180006b18  lea     r8, aWil; "wil"
0x180006b1f  mov     r9d, eax; char *
0x180006b22  mov     edx, 90h; void *
0x180006b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b2c  mov     eax, ebx
0x180006b2e  jmp     short loc_180006B62
0x180006b30  call    cs:__imp_GetLastError
0x180006b36  mov     rdi, [rbx+8]
0x180006b3a  test    rdi, rdi
0x180006b3d  jz      short loc_180006B5C
0x180006b3f  call    cs:__imp_GetLastError
0x180006b45  mov     rcx, rdi; hObject
0x180006b48  mov     ebp, eax
0x180006b4a  call    cs:__imp_CloseHandle
0x180006b50  test    eax, eax
0x180006b52  jz      short loc_180006B8E
0x180006b54  mov     ecx, ebp; dwErrCode
0x180006b56  call    cs:__imp_SetLastError
0x180006b5c  mov     [rbx+8], rsi
0x180006b60  xor     eax, eax
0x180006b62  mov     rcx, [rsp+278h+var_38]
0x180006b6a  xor     rcx, rsp; StackCookie
0x180006b6d  call    __security_check_cookie
0x180006b72  lea     r11, [rsp+278h+var_28]
0x180006b7a  mov     rbx, [r11+38h]
0x180006b7e  mov     rbp, [r11+40h]
0x180006b82  mov     rsp, r11
0x180006b85  pop     r15
0x180006b87  pop     r14
0x180006b89  pop     r12
0x180006b8b  pop     rdi
0x180006b8c  pop     rsi
0x180006b8d  retn
0x180006b8e  mov     rcx, [rsp+278h]; this
0x180006b96  mov     edx, 0A0Bh; void *
0x180006b9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ba1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006ba7  mov     rcx, [rsp+278h]; this
0x180006baf  mov     edx, 0A0Bh; void *
0x180006bb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
