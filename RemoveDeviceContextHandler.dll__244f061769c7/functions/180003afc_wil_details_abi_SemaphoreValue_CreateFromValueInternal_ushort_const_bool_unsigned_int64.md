# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003afc`
- end: `0x180003d09`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003758`

## callees

- `0x180003afc`
- `0x1800042a8`
- `0x180004dc4`
- `0x1800050dc`
- `0x180005678`
- `0x180005688`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bc0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c5c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003bc0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003c5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ca5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c99`

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
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
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
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
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
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003afc  mov     [rsp+arg_8], rbx
0x180003b01  mov     [rsp+arg_10], rbp
0x180003b06  push    rsi
0x180003b07  push    rdi
0x180003b08  push    r12
0x180003b0a  push    r14
0x180003b0c  push    r15
0x180003b0e  sub     rsp, 250h
0x180003b15  mov     rax, cs:__security_cookie
0x180003b1c  xor     rax, rsp
0x180003b1f  mov     [rsp+278h+var_38], rax
0x180003b27  mov     rax, 0C000000000000000h
0x180003b31  mov     rbp, r9
0x180003b34  mov     r8, rdx
0x180003b37  mov     rdi, rcx
0x180003b3a  test    rax, r9
0x180003b3d  jnz     loc_180003CF0
0x180003b43  xor     r12d, r12d
0x180003b46  lea     rax, [rsp+278h+Name]
0x180003b4b  mov     ecx, 7FFFFFFEh
0x180003b50  mov     edx, 104h
0x180003b55  lea     esi, [r12+1]
0x180003b5a  test    rcx, rcx
0x180003b5d  jz      short loc_180003B7D
0x180003b5f  movzx   r9d, word ptr [r8]
0x180003b63  test    r9w, r9w
0x180003b67  jz      short loc_180003B7D
0x180003b69  mov     [rax], r9w
0x180003b6d  add     r8, 2
0x180003b71  add     rax, 2
0x180003b75  sub     rcx, rsi
0x180003b78  sub     rdx, rsi; unsigned __int64
0x180003b7b  jnz     short loc_180003B5A
0x180003b7d  test    rdx, rdx
0x180003b80  lea     rcx, [rax-2]
0x180003b84  lea     r8, aP0; "_p0"
0x180003b8b  cmovnz  rcx, rax
0x180003b8f  mov     [rcx], r12w
0x180003b93  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003b98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003b9d  mov     edx, ebp
0x180003b9f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003ba7  and     edx, 7FFFFFFFh; lInitialCount
0x180003bad  mov     [rsp+278h+dwFlags], r12d; int
0x180003bb2  mov     r8d, esi
0x180003bb5  lea     r9, [rsp+278h+Name]; lpName
0x180003bba  cmova   r8d, edx; lMaximumCount
0x180003bbe  xor     ecx, ecx; lpSemaphoreAttributes
0x180003bc0  call    cs:__imp_CreateSemaphoreExW
0x180003bc6  mov     r15, rax
0x180003bc9  test    rax, rax
0x180003bcc  jnz     short loc_180003BF5
0x180003bce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003bd3  mov     ebx, eax
0x180003bd5  test    eax, eax
0x180003bd7  jns     short loc_180003C29
0x180003bd9  mov     edx, 8Bh; void *
0x180003bde  mov     rcx, [rsp+278h]; this
0x180003be6  mov     r9d, ebx; char *
0x180003be9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bee  mov     eax, ebx
0x180003bf0  jmp     loc_180003CB1
0x180003bf5  call    cs:__imp_GetLastError
0x180003bfb  mov     rbx, [rdi]
0x180003bfe  test    rbx, rbx
0x180003c01  jz      short loc_180003C26
0x180003c03  call    cs:__imp_GetLastError
0x180003c09  mov     rcx, rbx; hObject
0x180003c0c  mov     r14d, eax
0x180003c0f  call    cs:__imp_CloseHandle
0x180003c15  test    eax, eax
0x180003c17  jz      loc_180003CF6
0x180003c1d  mov     ecx, r14d; dwErrCode
0x180003c20  call    cs:__imp_SetLastError
0x180003c26  mov     [rdi], r15
0x180003c29  lea     r8, asc_1800100F0; "h"
0x180003c30  shr     rbp, 1Fh
0x180003c34  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003c39  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003c3e  test    ebp, ebp
0x180003c40  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003c48  lea     r9, [rsp+278h+Name]; lpName
0x180003c4d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003c52  cmovnz  esi, ebp
0x180003c55  mov     edx, ebp; lInitialCount
0x180003c57  mov     r8d, esi; lMaximumCount
0x180003c5a  xor     ecx, ecx; lpSemaphoreAttributes
0x180003c5c  call    cs:__imp_CreateSemaphoreExW
0x180003c62  mov     rsi, rax
0x180003c65  test    rax, rax
0x180003c68  jnz     short loc_180003C7F
0x180003c6a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c6f  mov     ebx, eax
0x180003c71  test    eax, eax
0x180003c73  jns     short loc_180003CAF
0x180003c75  mov     edx, 90h
0x180003c7a  jmp     loc_180003BDE
0x180003c7f  call    cs:__imp_GetLastError
0x180003c85  mov     rbx, [rdi+8]
0x180003c89  test    rbx, rbx
0x180003c8c  jz      short loc_180003CAB
0x180003c8e  call    cs:__imp_GetLastError
0x180003c94  mov     rcx, rbx; hObject
0x180003c97  mov     ebp, eax
0x180003c99  call    cs:__imp_CloseHandle
0x180003c9f  test    eax, eax
0x180003ca1  jz      short loc_180003CDD
0x180003ca3  mov     ecx, ebp; dwErrCode
0x180003ca5  call    cs:__imp_SetLastError
0x180003cab  mov     [rdi+8], rsi
0x180003caf  xor     eax, eax
0x180003cb1  mov     rcx, [rsp+278h+var_38]
0x180003cb9  xor     rcx, rsp; StackCookie
0x180003cbc  call    __security_check_cookie
0x180003cc1  lea     r11, [rsp+278h+var_28]
0x180003cc9  mov     rbx, [r11+38h]
0x180003ccd  mov     rbp, [r11+40h]
0x180003cd1  mov     rsp, r11
0x180003cd4  pop     r15
0x180003cd6  pop     r14
0x180003cd8  pop     r12
0x180003cda  pop     rdi
0x180003cdb  pop     rsi
0x180003cdc  retn
0x180003cdd  mov     rcx, [rsp+278h]; this
0x180003ce5  mov     edx, 0A0Bh; void *
0x180003cea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cf0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003cf6  mov     rcx, [rsp+278h]; this
0x180003cfe  mov     edx, 0A0Bh; void *
0x180003d03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
