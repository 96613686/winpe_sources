# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003a9c`
- end: `0x180003ccd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003670`

## callees

- `0x180003a9c`
- `0x180004508`
- `0x180005644`
- `0x180005d60`
- `0x180006550`
- `0x180006560`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b65`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c0b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003b65`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c5e`

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
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  __int64 v29; // r8
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
0x180003a9c  mov     [rsp+arg_8], rbx
0x180003aa1  push    rbp
0x180003aa2  push    rsi
0x180003aa3  push    rdi
0x180003aa4  push    r12
0x180003aa6  push    r13
0x180003aa8  push    r14
0x180003aaa  push    r15
0x180003aac  sub     rsp, 250h
0x180003ab3  mov     rax, cs:__security_cookie
0x180003aba  xor     rax, rsp
0x180003abd  mov     [rsp+288h+var_48], rax
0x180003ac5  mov     rax, 0C000000000000000h
0x180003acf  mov     rsi, r9
0x180003ad2  mov     r8, rdx
0x180003ad5  mov     rbx, rcx
0x180003ad8  test    rax, r9
0x180003adb  jnz     loc_180003CB4
0x180003ae1  xor     r12d, r12d
0x180003ae4  lea     rax, [rsp+288h+Name]
0x180003ae9  mov     r13d, 104h
0x180003aef  mov     ecx, 7FFFFFFEh
0x180003af4  mov     edx, r13d
0x180003af7  lea     ebp, [r12+1]
0x180003afc  test    rcx, rcx
0x180003aff  jz      short loc_180003B1F
0x180003b01  movzx   r9d, word ptr [r8]
0x180003b05  test    r9w, r9w
0x180003b09  jz      short loc_180003B1F
0x180003b0b  mov     [rax], r9w
0x180003b0f  add     r8, 2
0x180003b13  add     rax, 2
0x180003b17  sub     rcx, rbp
0x180003b1a  sub     rdx, rbp
0x180003b1d  jnz     short loc_180003AFC
0x180003b1f  test    rdx, rdx
0x180003b22  lea     rcx, [rax-2]
0x180003b26  lea     r8, aP0; "_p0"
0x180003b2d  mov     rdx, r13; unsigned __int64
0x180003b30  cmovnz  rcx, rax
0x180003b34  mov     [rcx], r12w
0x180003b38  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003b3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b42  mov     edx, esi
0x180003b44  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003b4c  and     edx, 7FFFFFFFh; lInitialCount
0x180003b52  mov     [rsp+288h+dwFlags], r12d; int
0x180003b57  mov     r8d, ebp
0x180003b5a  lea     r9, [rsp+288h+Name]; lpName
0x180003b5f  cmova   r8d, edx; lMaximumCount
0x180003b63  xor     ecx, ecx; lpSemaphoreAttributes
0x180003b65  call    cs:__imp_CreateSemaphoreExW
0x180003b6b  mov     r15, rax
0x180003b6e  test    rax, rax
0x180003b71  jnz     short loc_180003BA1
0x180003b73  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b78  mov     edi, eax
0x180003b7a  test    eax, eax
0x180003b7c  jns     short loc_180003BD5
0x180003b7e  mov     rcx, [rsp+288h]; this
0x180003b86  lea     r8, aWil; "wil"
0x180003b8d  mov     r9d, eax; char *
0x180003b90  mov     edx, 8Bh; void *
0x180003b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b9a  mov     eax, edi
0x180003b9c  jmp     loc_180003C76
0x180003ba1  call    cs:__imp_GetLastError
0x180003ba7  mov     rdi, [rbx]
0x180003baa  test    rdi, rdi
0x180003bad  jz      short loc_180003BD2
0x180003baf  call    cs:__imp_GetLastError
0x180003bb5  mov     rcx, rdi; hObject
0x180003bb8  mov     r14d, eax
0x180003bbb  call    cs:__imp_CloseHandle
0x180003bc1  test    eax, eax
0x180003bc3  jz      loc_180003CBA
0x180003bc9  mov     ecx, r14d; dwErrCode
0x180003bcc  call    cs:__imp_SetLastError
0x180003bd2  mov     [rbx], r15
0x180003bd5  lea     r8, asc_180014238; "h"
0x180003bdc  shr     rsi, 1Fh
0x180003be0  mov     rdx, r13; unsigned __int64
0x180003be3  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x180003be8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003bed  test    esi, esi
0x180003bef  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003bf7  lea     r9, [rsp+288h+Name]; lpName
0x180003bfc  mov     [rsp+288h+dwFlags], r12d; int
0x180003c01  cmovnz  ebp, esi
0x180003c04  mov     edx, esi; lInitialCount
0x180003c06  mov     r8d, ebp; lMaximumCount
0x180003c09  xor     ecx, ecx; lpSemaphoreAttributes
0x180003c0b  call    cs:__imp_CreateSemaphoreExW
0x180003c11  mov     rbp, rax
0x180003c14  test    rax, rax
0x180003c17  jnz     short loc_180003C44
0x180003c19  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c1e  mov     ebx, eax
0x180003c20  test    eax, eax
0x180003c22  jns     short loc_180003C74
0x180003c24  mov     rcx, [rsp+288h]; this
0x180003c2c  lea     r8, aWil; "wil"
0x180003c33  mov     r9d, eax; char *
0x180003c36  mov     edx, 90h; void *
0x180003c3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c40  mov     eax, ebx
0x180003c42  jmp     short loc_180003C76
0x180003c44  call    cs:__imp_GetLastError
0x180003c4a  mov     rdi, [rbx+8]
0x180003c4e  test    rdi, rdi
0x180003c51  jz      short loc_180003C70
0x180003c53  call    cs:__imp_GetLastError
0x180003c59  mov     rcx, rdi; hObject
0x180003c5c  mov     esi, eax
0x180003c5e  call    cs:__imp_CloseHandle
0x180003c64  test    eax, eax
0x180003c66  jz      short loc_180003CA1
0x180003c68  mov     ecx, esi; dwErrCode
0x180003c6a  call    cs:__imp_SetLastError
0x180003c70  mov     [rbx+8], rbp
0x180003c74  xor     eax, eax
0x180003c76  mov     rcx, [rsp+288h+var_48]
0x180003c7e  xor     rcx, rsp; StackCookie
0x180003c81  call    __security_check_cookie
0x180003c86  mov     rbx, [rsp+288h+arg_8]
0x180003c8e  add     rsp, 250h
0x180003c95  pop     r15
0x180003c97  pop     r14
0x180003c99  pop     r13
0x180003c9b  pop     r12
0x180003c9d  pop     rdi
0x180003c9e  pop     rsi
0x180003c9f  pop     rbp
0x180003ca0  retn
0x180003ca1  mov     rcx, [rsp+288h]; this
0x180003ca9  mov     edx, 0A0Bh; void *
0x180003cae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003cba  mov     rcx, [rsp+288h]; this
0x180003cc2  mov     edx, 0A0Bh; void *
0x180003cc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
