# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006b30`
- end: `0x180006d3d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800064a8`
- `0x18000fa9c`

## callees

- `0x1800032a0`
- `0x180006b30`
- `0x180007a98`
- `0x180009434`
- `0x180009d74`
- `0x18000a8dc`
- `0x18000a8ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006bf4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006c90`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006bf4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006c90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180006b30  mov     [rsp+arg_8], rbx
0x180006b35  mov     [rsp+arg_10], rbp
0x180006b3a  push    rsi
0x180006b3b  push    rdi
0x180006b3c  push    r12
0x180006b3e  push    r14
0x180006b40  push    r15
0x180006b42  sub     rsp, 250h
0x180006b49  mov     rax, cs:__security_cookie
0x180006b50  xor     rax, rsp
0x180006b53  mov     [rsp+278h+var_38], rax
0x180006b5b  mov     rax, 0C000000000000000h
0x180006b65  mov     rbp, r9
0x180006b68  mov     r8, rdx
0x180006b6b  mov     rdi, rcx
0x180006b6e  test    rax, r9
0x180006b71  jnz     loc_180006D24
0x180006b77  xor     r12d, r12d
0x180006b7a  lea     rax, [rsp+278h+Name]
0x180006b7f  mov     ecx, 7FFFFFFEh
0x180006b84  mov     edx, 104h
0x180006b89  lea     esi, [r12+1]
0x180006b8e  test    rcx, rcx
0x180006b91  jz      short loc_180006BB1
0x180006b93  movzx   r9d, word ptr [r8]
0x180006b97  test    r9w, r9w
0x180006b9b  jz      short loc_180006BB1
0x180006b9d  mov     [rax], r9w
0x180006ba1  add     r8, 2
0x180006ba5  add     rax, 2
0x180006ba9  sub     rcx, rsi
0x180006bac  sub     rdx, rsi; unsigned __int64
0x180006baf  jnz     short loc_180006B8E
0x180006bb1  test    rdx, rdx
0x180006bb4  lea     rcx, [rax-2]
0x180006bb8  lea     r8, aP0; "_p0"
0x180006bbf  cmovnz  rcx, rax
0x180006bc3  mov     [rcx], r12w
0x180006bc7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006bcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006bd1  mov     edx, ebp
0x180006bd3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006bdb  and     edx, 7FFFFFFFh; lInitialCount
0x180006be1  mov     [rsp+278h+dwFlags], r12d; int
0x180006be6  mov     r8d, esi
0x180006be9  lea     r9, [rsp+278h+Name]; lpName
0x180006bee  cmova   r8d, edx; lMaximumCount
0x180006bf2  xor     ecx, ecx; lpSemaphoreAttributes
0x180006bf4  call    cs:__imp_CreateSemaphoreExW
0x180006bfa  mov     r15, rax
0x180006bfd  test    rax, rax
0x180006c00  jnz     short loc_180006C29
0x180006c02  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006c07  mov     ebx, eax
0x180006c09  test    eax, eax
0x180006c0b  jns     short loc_180006C5D
0x180006c0d  mov     edx, 8Bh; void *
0x180006c12  mov     rcx, [rsp+278h]; this
0x180006c1a  mov     r9d, ebx; char *
0x180006c1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c22  mov     eax, ebx
0x180006c24  jmp     loc_180006CE5
0x180006c29  call    cs:__imp_GetLastError
0x180006c2f  mov     rbx, [rdi]
0x180006c32  test    rbx, rbx
0x180006c35  jz      short loc_180006C5A
0x180006c37  call    cs:__imp_GetLastError
0x180006c3d  mov     rcx, rbx; hObject
0x180006c40  mov     r14d, eax
0x180006c43  call    cs:__imp_CloseHandle
0x180006c49  test    eax, eax
0x180006c4b  jz      loc_180006D2A
0x180006c51  mov     ecx, r14d; dwErrCode
0x180006c54  call    cs:__imp_SetLastError
0x180006c5a  mov     [rdi], r15
0x180006c5d  lea     r8, asc_180032320; "h"
0x180006c64  shr     rbp, 1Fh
0x180006c68  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006c6d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006c72  test    ebp, ebp
0x180006c74  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006c7c  lea     r9, [rsp+278h+Name]; lpName
0x180006c81  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180006c86  cmovnz  esi, ebp
0x180006c89  mov     edx, ebp; lInitialCount
0x180006c8b  mov     r8d, esi; lMaximumCount
0x180006c8e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006c90  call    cs:__imp_CreateSemaphoreExW
0x180006c96  mov     rsi, rax
0x180006c99  test    rax, rax
0x180006c9c  jnz     short loc_180006CB3
0x180006c9e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006ca3  mov     ebx, eax
0x180006ca5  test    eax, eax
0x180006ca7  jns     short loc_180006CE3
0x180006ca9  mov     edx, 90h
0x180006cae  jmp     loc_180006C12
0x180006cb3  call    cs:__imp_GetLastError
0x180006cb9  mov     rbx, [rdi+8]
0x180006cbd  test    rbx, rbx
0x180006cc0  jz      short loc_180006CDF
0x180006cc2  call    cs:__imp_GetLastError
0x180006cc8  mov     rcx, rbx; hObject
0x180006ccb  mov     ebp, eax
0x180006ccd  call    cs:__imp_CloseHandle
0x180006cd3  test    eax, eax
0x180006cd5  jz      short loc_180006D11
0x180006cd7  mov     ecx, ebp; dwErrCode
0x180006cd9  call    cs:__imp_SetLastError
0x180006cdf  mov     [rdi+8], rsi
0x180006ce3  xor     eax, eax
0x180006ce5  mov     rcx, [rsp+278h+var_38]
0x180006ced  xor     rcx, rsp; StackCookie
0x180006cf0  call    __security_check_cookie
0x180006cf5  lea     r11, [rsp+278h+var_28]
0x180006cfd  mov     rbx, [r11+38h]
0x180006d01  mov     rbp, [r11+40h]
0x180006d05  mov     rsp, r11
0x180006d08  pop     r15
0x180006d0a  pop     r14
0x180006d0c  pop     r12
0x180006d0e  pop     rdi
0x180006d0f  pop     rsi
0x180006d10  retn
0x180006d11  mov     rcx, [rsp+278h]; this
0x180006d19  mov     edx, 0A0Bh; void *
0x180006d1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006d24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006d2a  mov     rcx, [rsp+278h]; this
0x180006d32  mov     edx, 0A0Bh; void *
0x180006d37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
