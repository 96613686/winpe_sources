# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004cc8`
- end: `0x140004ef2`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400048f8`
- `0x14000c164`

## callees

- `0x140002a30`
- `0x140004cc8`
- `0x140005640`
- `0x14000644c`
- `0x140006db0`
- `0x1400073b0`
- `0x1400073c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004d8c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e2f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004d8c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004df3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004e8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004df3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004e8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004e82`

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
0x140004cc8  mov     [rsp+arg_8], rbx
0x140004ccd  mov     [rsp+arg_10], rbp
0x140004cd2  push    rsi
0x140004cd3  push    rdi
0x140004cd4  push    r12
0x140004cd6  push    r14
0x140004cd8  push    r15
0x140004cda  sub     rsp, 250h
0x140004ce1  mov     rax, cs:__security_cookie
0x140004ce8  xor     rax, rsp
0x140004ceb  mov     [rsp+278h+var_38], rax
0x140004cf3  mov     rax, 0C000000000000000h
0x140004cfd  mov     rbp, r9
0x140004d00  mov     r8, rdx
0x140004d03  mov     rbx, rcx
0x140004d06  test    rax, r9
0x140004d09  jnz     loc_140004ED9
0x140004d0f  xor     r12d, r12d
0x140004d12  lea     rax, [rsp+278h+Name]
0x140004d17  mov     ecx, 7FFFFFFEh
0x140004d1c  mov     edx, 104h
0x140004d21  lea     esi, [r12+1]
0x140004d26  test    rcx, rcx
0x140004d29  jz      short loc_140004D49
0x140004d2b  movzx   r9d, word ptr [r8]
0x140004d2f  test    r9w, r9w
0x140004d33  jz      short loc_140004D49
0x140004d35  mov     [rax], r9w
0x140004d39  add     r8, 2
0x140004d3d  add     rax, 2
0x140004d41  sub     rcx, rsi
0x140004d44  sub     rdx, rsi; unsigned __int64
0x140004d47  jnz     short loc_140004D26
0x140004d49  test    rdx, rdx
0x140004d4c  lea     rcx, [rax-2]
0x140004d50  lea     r8, aP0; "_p0"
0x140004d57  cmovnz  rcx, rax
0x140004d5b  mov     [rcx], r12w
0x140004d5f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004d64  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004d69  mov     edx, ebp
0x140004d6b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004d73  and     edx, 7FFFFFFFh; lInitialCount
0x140004d79  mov     [rsp+278h+dwFlags], r12d; int
0x140004d7e  mov     r8d, esi
0x140004d81  lea     r9, [rsp+278h+Name]; lpName
0x140004d86  cmova   r8d, edx; lMaximumCount
0x140004d8a  xor     ecx, ecx; lpSemaphoreAttributes
0x140004d8c  call    cs:__imp_CreateSemaphoreExW
0x140004d92  mov     r15, rax
0x140004d95  test    rax, rax
0x140004d98  jnz     short loc_140004DC8
0x140004d9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004d9f  mov     edi, eax
0x140004da1  test    eax, eax
0x140004da3  jns     short loc_140004DFC
0x140004da5  mov     rcx, [rsp+278h]; this
0x140004dad  lea     r8, aWil; "wil"
0x140004db4  mov     r9d, eax; char *
0x140004db7  mov     edx, 8Bh; void *
0x140004dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004dc1  mov     eax, edi
0x140004dc3  jmp     loc_140004E9A
0x140004dc8  call    cs:__imp_GetLastError
0x140004dce  mov     rdi, [rbx]
0x140004dd1  test    rdi, rdi
0x140004dd4  jz      short loc_140004DF9
0x140004dd6  call    cs:__imp_GetLastError
0x140004ddc  mov     rcx, rdi; hObject
0x140004ddf  mov     r14d, eax
0x140004de2  call    cs:__imp_CloseHandle
0x140004de8  test    eax, eax
0x140004dea  jz      loc_140004EDF
0x140004df0  mov     ecx, r14d; dwErrCode
0x140004df3  call    cs:__imp_SetLastError
0x140004df9  mov     [rbx], r15
0x140004dfc  lea     r8, asc_140015340; "h"
0x140004e03  shr     rbp, 1Fh
0x140004e07  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004e0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004e11  test    ebp, ebp
0x140004e13  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004e1b  lea     r9, [rsp+278h+Name]; lpName
0x140004e20  mov     [rsp+278h+dwFlags], r12d; int
0x140004e25  cmovnz  esi, ebp
0x140004e28  mov     edx, ebp; lInitialCount
0x140004e2a  mov     r8d, esi; lMaximumCount
0x140004e2d  xor     ecx, ecx; lpSemaphoreAttributes
0x140004e2f  call    cs:__imp_CreateSemaphoreExW
0x140004e35  mov     rsi, rax
0x140004e38  test    rax, rax
0x140004e3b  jnz     short loc_140004E68
0x140004e3d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004e42  mov     ebx, eax
0x140004e44  test    eax, eax
0x140004e46  jns     short loc_140004E98
0x140004e48  mov     rcx, [rsp+278h]; this
0x140004e50  lea     r8, aWil; "wil"
0x140004e57  mov     r9d, eax; char *
0x140004e5a  mov     edx, 90h; void *
0x140004e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e64  mov     eax, ebx
0x140004e66  jmp     short loc_140004E9A
0x140004e68  call    cs:__imp_GetLastError
0x140004e6e  mov     rdi, [rbx+8]
0x140004e72  test    rdi, rdi
0x140004e75  jz      short loc_140004E94
0x140004e77  call    cs:__imp_GetLastError
0x140004e7d  mov     rcx, rdi; hObject
0x140004e80  mov     ebp, eax
0x140004e82  call    cs:__imp_CloseHandle
0x140004e88  test    eax, eax
0x140004e8a  jz      short loc_140004EC6
0x140004e8c  mov     ecx, ebp; dwErrCode
0x140004e8e  call    cs:__imp_SetLastError
0x140004e94  mov     [rbx+8], rsi
0x140004e98  xor     eax, eax
0x140004e9a  mov     rcx, [rsp+278h+var_38]
0x140004ea2  xor     rcx, rsp; StackCookie
0x140004ea5  call    __security_check_cookie
0x140004eaa  lea     r11, [rsp+278h+var_28]
0x140004eb2  mov     rbx, [r11+38h]
0x140004eb6  mov     rbp, [r11+40h]
0x140004eba  mov     rsp, r11
0x140004ebd  pop     r15
0x140004ebf  pop     r14
0x140004ec1  pop     r12
0x140004ec3  pop     rdi
0x140004ec4  pop     rsi
0x140004ec5  retn
0x140004ec6  mov     rcx, [rsp+278h]; this
0x140004ece  mov     edx, 0A0Bh; void *
0x140004ed3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004ed9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004edf  mov     rcx, [rsp+278h]; this
0x140004ee7  mov     edx, 0A0Bh; void *
0x140004eec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
