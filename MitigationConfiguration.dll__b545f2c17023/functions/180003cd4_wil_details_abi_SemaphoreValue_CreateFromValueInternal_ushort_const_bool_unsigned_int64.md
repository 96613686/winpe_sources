# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003cd4`
- end: `0x180003efe`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038c8`

## callees

- `0x180001c00`
- `0x180003cd4`
- `0x180004e78`
- `0x180005db4`
- `0x1800067a0`
- `0x180006e34`
- `0x180006e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d98`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003e3b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003d98`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e8e`

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
0x180003cd4  mov     [rsp+arg_8], rbx
0x180003cd9  mov     [rsp+arg_10], rbp
0x180003cde  push    rsi
0x180003cdf  push    rdi
0x180003ce0  push    r12
0x180003ce2  push    r14
0x180003ce4  push    r15
0x180003ce6  sub     rsp, 250h
0x180003ced  mov     rax, cs:__security_cookie
0x180003cf4  xor     rax, rsp
0x180003cf7  mov     [rsp+278h+var_38], rax
0x180003cff  mov     rax, 0C000000000000000h
0x180003d09  mov     rbp, r9
0x180003d0c  mov     r8, rdx
0x180003d0f  mov     rbx, rcx
0x180003d12  test    rax, r9
0x180003d15  jnz     loc_180003EE5
0x180003d1b  xor     r12d, r12d
0x180003d1e  lea     rax, [rsp+278h+Name]
0x180003d23  mov     ecx, 7FFFFFFEh
0x180003d28  mov     edx, 104h
0x180003d2d  lea     esi, [r12+1]
0x180003d32  test    rcx, rcx
0x180003d35  jz      short loc_180003D55
0x180003d37  movzx   r9d, word ptr [r8]
0x180003d3b  test    r9w, r9w
0x180003d3f  jz      short loc_180003D55
0x180003d41  mov     [rax], r9w
0x180003d45  add     r8, 2
0x180003d49  add     rax, 2
0x180003d4d  sub     rcx, rsi
0x180003d50  sub     rdx, rsi; unsigned __int64
0x180003d53  jnz     short loc_180003D32
0x180003d55  test    rdx, rdx
0x180003d58  lea     rcx, [rax-2]
0x180003d5c  lea     r8, aP0; "_p0"
0x180003d63  cmovnz  rcx, rax
0x180003d67  mov     [rcx], r12w
0x180003d6b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003d70  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003d75  mov     edx, ebp
0x180003d77  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003d7f  and     edx, 7FFFFFFFh; lInitialCount
0x180003d85  mov     [rsp+278h+dwFlags], r12d; int
0x180003d8a  mov     r8d, esi
0x180003d8d  lea     r9, [rsp+278h+Name]; lpName
0x180003d92  cmova   r8d, edx; lMaximumCount
0x180003d96  xor     ecx, ecx; lpSemaphoreAttributes
0x180003d98  call    cs:__imp_CreateSemaphoreExW
0x180003d9e  mov     r15, rax
0x180003da1  test    rax, rax
0x180003da4  jnz     short loc_180003DD4
0x180003da6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003dab  mov     edi, eax
0x180003dad  test    eax, eax
0x180003daf  jns     short loc_180003E08
0x180003db1  mov     rcx, [rsp+278h]; this
0x180003db9  lea     r8, aWil; "wil"
0x180003dc0  mov     r9d, eax; char *
0x180003dc3  mov     edx, 8Bh; void *
0x180003dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dcd  mov     eax, edi
0x180003dcf  jmp     loc_180003EA6
0x180003dd4  call    cs:__imp_GetLastError
0x180003dda  mov     rdi, [rbx]
0x180003ddd  test    rdi, rdi
0x180003de0  jz      short loc_180003E05
0x180003de2  call    cs:__imp_GetLastError
0x180003de8  mov     rcx, rdi; hObject
0x180003deb  mov     r14d, eax
0x180003dee  call    cs:__imp_CloseHandle
0x180003df4  test    eax, eax
0x180003df6  jz      loc_180003EEB
0x180003dfc  mov     ecx, r14d; dwErrCode
0x180003dff  call    cs:__imp_SetLastError
0x180003e05  mov     [rbx], r15
0x180003e08  lea     r8, asc_1800170C0; "h"
0x180003e0f  shr     rbp, 1Fh
0x180003e13  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003e18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e1d  test    ebp, ebp
0x180003e1f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003e27  lea     r9, [rsp+278h+Name]; lpName
0x180003e2c  mov     [rsp+278h+dwFlags], r12d; int
0x180003e31  cmovnz  esi, ebp
0x180003e34  mov     edx, ebp; lInitialCount
0x180003e36  mov     r8d, esi; lMaximumCount
0x180003e39  xor     ecx, ecx; lpSemaphoreAttributes
0x180003e3b  call    cs:__imp_CreateSemaphoreExW
0x180003e41  mov     rsi, rax
0x180003e44  test    rax, rax
0x180003e47  jnz     short loc_180003E74
0x180003e49  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e4e  mov     ebx, eax
0x180003e50  test    eax, eax
0x180003e52  jns     short loc_180003EA4
0x180003e54  mov     rcx, [rsp+278h]; this
0x180003e5c  lea     r8, aWil; "wil"
0x180003e63  mov     r9d, eax; char *
0x180003e66  mov     edx, 90h; void *
0x180003e6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e70  mov     eax, ebx
0x180003e72  jmp     short loc_180003EA6
0x180003e74  call    cs:__imp_GetLastError
0x180003e7a  mov     rdi, [rbx+8]
0x180003e7e  test    rdi, rdi
0x180003e81  jz      short loc_180003EA0
0x180003e83  call    cs:__imp_GetLastError
0x180003e89  mov     rcx, rdi; hObject
0x180003e8c  mov     ebp, eax
0x180003e8e  call    cs:__imp_CloseHandle
0x180003e94  test    eax, eax
0x180003e96  jz      short loc_180003ED2
0x180003e98  mov     ecx, ebp; dwErrCode
0x180003e9a  call    cs:__imp_SetLastError
0x180003ea0  mov     [rbx+8], rsi
0x180003ea4  xor     eax, eax
0x180003ea6  mov     rcx, [rsp+278h+var_38]
0x180003eae  xor     rcx, rsp; StackCookie
0x180003eb1  call    __security_check_cookie
0x180003eb6  lea     r11, [rsp+278h+var_28]
0x180003ebe  mov     rbx, [r11+38h]
0x180003ec2  mov     rbp, [r11+40h]
0x180003ec6  mov     rsp, r11
0x180003ec9  pop     r15
0x180003ecb  pop     r14
0x180003ecd  pop     r12
0x180003ecf  pop     rdi
0x180003ed0  pop     rsi
0x180003ed1  retn
0x180003ed2  mov     rcx, [rsp+278h]; this
0x180003eda  mov     edx, 0A0Bh; void *
0x180003edf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ee5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003eeb  mov     rcx, [rsp+278h]; this
0x180003ef3  mov     edx, 0A0Bh; void *
0x180003ef8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
