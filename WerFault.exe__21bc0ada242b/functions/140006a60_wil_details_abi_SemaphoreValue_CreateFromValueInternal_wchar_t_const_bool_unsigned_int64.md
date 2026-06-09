# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x140006a60`
- end: `0x140006c91`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140006298`
- `0x140006668`

## callees

- `0x140002470`
- `0x140006a60`
- `0x140007e50`
- `0x14000a9c4`
- `0x14000b408`
- `0x14000c59c`
- `0x14000c5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140006b29`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140006bcf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140006b29`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140006bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006c22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006c22`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
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
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
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
0x140006a60  mov     [rsp+arg_8], rbx
0x140006a65  push    rbp
0x140006a66  push    rsi
0x140006a67  push    rdi
0x140006a68  push    r12
0x140006a6a  push    r13
0x140006a6c  push    r14
0x140006a6e  push    r15
0x140006a70  sub     rsp, 250h
0x140006a77  mov     rax, cs:__security_cookie
0x140006a7e  xor     rax, rsp
0x140006a81  mov     [rsp+288h+var_48], rax
0x140006a89  mov     rax, 0C000000000000000h
0x140006a93  mov     rsi, r9
0x140006a96  mov     r8, rdx
0x140006a99  mov     rbx, rcx
0x140006a9c  test    rax, r9
0x140006a9f  jnz     loc_140006C78
0x140006aa5  xor     r12d, r12d
0x140006aa8  lea     rax, [rsp+288h+Name]
0x140006aad  mov     r13d, 104h
0x140006ab3  mov     ecx, 7FFFFFFEh
0x140006ab8  mov     edx, r13d
0x140006abb  lea     ebp, [r12+1]
0x140006ac0  test    rcx, rcx
0x140006ac3  jz      short loc_140006AE3
0x140006ac5  movzx   r9d, word ptr [r8]
0x140006ac9  test    r9w, r9w
0x140006acd  jz      short loc_140006AE3
0x140006acf  mov     [rax], r9w
0x140006ad3  add     r8, 2
0x140006ad7  add     rax, 2
0x140006adb  sub     rcx, rbp
0x140006ade  sub     rdx, rbp
0x140006ae1  jnz     short loc_140006AC0
0x140006ae3  test    rdx, rdx
0x140006ae6  lea     rcx, [rax-2]
0x140006aea  lea     r8, aP0; "_p0"
0x140006af1  mov     rdx, r13; unsigned __int64
0x140006af4  cmovnz  rcx, rax
0x140006af8  mov     [rcx], r12w
0x140006afc  lea     rcx, [rsp+288h+Name]; wchar_t *
0x140006b01  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140006b06  mov     edx, esi
0x140006b08  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140006b10  and     edx, 7FFFFFFFh; lInitialCount
0x140006b16  mov     [rsp+288h+dwFlags], r12d; int
0x140006b1b  mov     r8d, ebp
0x140006b1e  lea     r9, [rsp+288h+Name]; lpName
0x140006b23  cmova   r8d, edx; lMaximumCount
0x140006b27  xor     ecx, ecx; lpSemaphoreAttributes
0x140006b29  call    cs:__imp_CreateSemaphoreExW
0x140006b2f  mov     r15, rax
0x140006b32  test    rax, rax
0x140006b35  jnz     short loc_140006B65
0x140006b37  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006b3c  mov     edi, eax
0x140006b3e  test    eax, eax
0x140006b40  jns     short loc_140006B99
0x140006b42  mov     rcx, [rsp+288h]; this
0x140006b4a  lea     r8, aWil; "wil"
0x140006b51  mov     r9d, eax; char *
0x140006b54  mov     edx, 8Bh; void *
0x140006b59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006b5e  mov     eax, edi
0x140006b60  jmp     loc_140006C3A
0x140006b65  call    cs:__imp_GetLastError
0x140006b6b  mov     rdi, [rbx]
0x140006b6e  test    rdi, rdi
0x140006b71  jz      short loc_140006B96
0x140006b73  call    cs:__imp_GetLastError
0x140006b79  mov     rcx, rdi; hObject
0x140006b7c  mov     r14d, eax
0x140006b7f  call    cs:__imp_CloseHandle
0x140006b85  test    eax, eax
0x140006b87  jz      loc_140006C7E
0x140006b8d  mov     ecx, r14d; dwErrCode
0x140006b90  call    cs:__imp_SetLastError
0x140006b96  mov     [rbx], r15
0x140006b99  lea     r8, asc_140062B58; "h"
0x140006ba0  shr     rsi, 1Fh
0x140006ba4  mov     rdx, r13; unsigned __int64
0x140006ba7  lea     rcx, [rsp+288h+Name]; wchar_t *
0x140006bac  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140006bb1  test    esi, esi
0x140006bb3  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140006bbb  lea     r9, [rsp+288h+Name]; lpName
0x140006bc0  mov     [rsp+288h+dwFlags], r12d; int
0x140006bc5  cmovnz  ebp, esi
0x140006bc8  mov     edx, esi; lInitialCount
0x140006bca  mov     r8d, ebp; lMaximumCount
0x140006bcd  xor     ecx, ecx; lpSemaphoreAttributes
0x140006bcf  call    cs:__imp_CreateSemaphoreExW
0x140006bd5  mov     rbp, rax
0x140006bd8  test    rax, rax
0x140006bdb  jnz     short loc_140006C08
0x140006bdd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140006be2  mov     ebx, eax
0x140006be4  test    eax, eax
0x140006be6  jns     short loc_140006C38
0x140006be8  mov     rcx, [rsp+288h]; this
0x140006bf0  lea     r8, aWil; "wil"
0x140006bf7  mov     r9d, eax; char *
0x140006bfa  mov     edx, 90h; void *
0x140006bff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006c04  mov     eax, ebx
0x140006c06  jmp     short loc_140006C3A
0x140006c08  call    cs:__imp_GetLastError
0x140006c0e  mov     rdi, [rbx+8]
0x140006c12  test    rdi, rdi
0x140006c15  jz      short loc_140006C34
0x140006c17  call    cs:__imp_GetLastError
0x140006c1d  mov     rcx, rdi; hObject
0x140006c20  mov     esi, eax
0x140006c22  call    cs:__imp_CloseHandle
0x140006c28  test    eax, eax
0x140006c2a  jz      short loc_140006C65
0x140006c2c  mov     ecx, esi; dwErrCode
0x140006c2e  call    cs:__imp_SetLastError
0x140006c34  mov     [rbx+8], rbp
0x140006c38  xor     eax, eax
0x140006c3a  mov     rcx, [rsp+288h+var_48]
0x140006c42  xor     rcx, rsp; StackCookie
0x140006c45  call    __security_check_cookie
0x140006c4a  mov     rbx, [rsp+288h+arg_8]
0x140006c52  add     rsp, 250h
0x140006c59  pop     r15
0x140006c5b  pop     r14
0x140006c5d  pop     r13
0x140006c5f  pop     r12
0x140006c61  pop     rdi
0x140006c62  pop     rsi
0x140006c63  pop     rbp
0x140006c64  retn
0x140006c65  mov     rcx, [rsp+288h]; this
0x140006c6d  mov     edx, 0A0Bh; void *
0x140006c72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006c78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006c7e  mov     rcx, [rsp+288h]; this
0x140006c86  mov     edx, 0A0Bh; void *
0x140006c8b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
