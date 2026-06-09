# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003e68`
- end: `0x180004075`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800036f4`
- `0x180003a98`

## callees

- `0x1800018e0`
- `0x180003e68`
- `0x180004be8`
- `0x180006ae0`
- `0x180006efc`
- `0x180007b2c`
- `0x180007b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f2c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003fc8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003f2c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004011`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004005`

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
0x180003e68  mov     [rsp+arg_8], rbx
0x180003e6d  mov     [rsp+arg_10], rbp
0x180003e72  push    rsi
0x180003e73  push    rdi
0x180003e74  push    r12
0x180003e76  push    r14
0x180003e78  push    r15
0x180003e7a  sub     rsp, 250h
0x180003e81  mov     rax, cs:__security_cookie
0x180003e88  xor     rax, rsp
0x180003e8b  mov     [rsp+278h+var_38], rax
0x180003e93  mov     rax, 0C000000000000000h
0x180003e9d  mov     rbp, r9
0x180003ea0  mov     r8, rdx
0x180003ea3  mov     rdi, rcx
0x180003ea6  test    rax, r9
0x180003ea9  jnz     loc_18000405C
0x180003eaf  xor     r12d, r12d
0x180003eb2  lea     rax, [rsp+278h+Name]
0x180003eb7  mov     ecx, 7FFFFFFEh
0x180003ebc  mov     edx, 104h
0x180003ec1  lea     esi, [r12+1]
0x180003ec6  test    rcx, rcx
0x180003ec9  jz      short loc_180003EE9
0x180003ecb  movzx   r9d, word ptr [r8]
0x180003ecf  test    r9w, r9w
0x180003ed3  jz      short loc_180003EE9
0x180003ed5  mov     [rax], r9w
0x180003ed9  add     r8, 2
0x180003edd  add     rax, 2
0x180003ee1  sub     rcx, rsi
0x180003ee4  sub     rdx, rsi; unsigned __int64
0x180003ee7  jnz     short loc_180003EC6
0x180003ee9  test    rdx, rdx
0x180003eec  lea     rcx, [rax-2]
0x180003ef0  lea     r8, aP0; "_p0"
0x180003ef7  cmovnz  rcx, rax
0x180003efb  mov     [rcx], r12w
0x180003eff  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003f04  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003f09  mov     edx, ebp
0x180003f0b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003f13  and     edx, 7FFFFFFFh; lInitialCount
0x180003f19  mov     [rsp+278h+dwFlags], r12d; int
0x180003f1e  mov     r8d, esi
0x180003f21  lea     r9, [rsp+278h+Name]; lpName
0x180003f26  cmova   r8d, edx; lMaximumCount
0x180003f2a  xor     ecx, ecx; lpSemaphoreAttributes
0x180003f2c  call    cs:__imp_CreateSemaphoreExW
0x180003f32  mov     r15, rax
0x180003f35  test    rax, rax
0x180003f38  jnz     short loc_180003F61
0x180003f3a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f3f  mov     ebx, eax
0x180003f41  test    eax, eax
0x180003f43  jns     short loc_180003F95
0x180003f45  mov     edx, 8Bh; void *
0x180003f4a  mov     rcx, [rsp+278h]; this
0x180003f52  mov     r9d, ebx; char *
0x180003f55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f5a  mov     eax, ebx
0x180003f5c  jmp     loc_18000401D
0x180003f61  call    cs:__imp_GetLastError
0x180003f67  mov     rbx, [rdi]
0x180003f6a  test    rbx, rbx
0x180003f6d  jz      short loc_180003F92
0x180003f6f  call    cs:__imp_GetLastError
0x180003f75  mov     rcx, rbx; hObject
0x180003f78  mov     r14d, eax
0x180003f7b  call    cs:__imp_CloseHandle
0x180003f81  test    eax, eax
0x180003f83  jz      loc_180004062
0x180003f89  mov     ecx, r14d; dwErrCode
0x180003f8c  call    cs:__imp_SetLastError
0x180003f92  mov     [rdi], r15
0x180003f95  lea     r8, asc_180029148; "h"
0x180003f9c  shr     rbp, 1Fh
0x180003fa0  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003fa5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003faa  test    ebp, ebp
0x180003fac  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003fb4  lea     r9, [rsp+278h+Name]; lpName
0x180003fb9  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003fbe  cmovnz  esi, ebp
0x180003fc1  mov     edx, ebp; lInitialCount
0x180003fc3  mov     r8d, esi; lMaximumCount
0x180003fc6  xor     ecx, ecx; lpSemaphoreAttributes
0x180003fc8  call    cs:__imp_CreateSemaphoreExW
0x180003fce  mov     rsi, rax
0x180003fd1  test    rax, rax
0x180003fd4  jnz     short loc_180003FEB
0x180003fd6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fdb  mov     ebx, eax
0x180003fdd  test    eax, eax
0x180003fdf  jns     short loc_18000401B
0x180003fe1  mov     edx, 90h
0x180003fe6  jmp     loc_180003F4A
0x180003feb  call    cs:__imp_GetLastError
0x180003ff1  mov     rbx, [rdi+8]
0x180003ff5  test    rbx, rbx
0x180003ff8  jz      short loc_180004017
0x180003ffa  call    cs:__imp_GetLastError
0x180004000  mov     rcx, rbx; hObject
0x180004003  mov     ebp, eax
0x180004005  call    cs:__imp_CloseHandle
0x18000400b  test    eax, eax
0x18000400d  jz      short loc_180004049
0x18000400f  mov     ecx, ebp; dwErrCode
0x180004011  call    cs:__imp_SetLastError
0x180004017  mov     [rdi+8], rsi
0x18000401b  xor     eax, eax
0x18000401d  mov     rcx, [rsp+278h+var_38]
0x180004025  xor     rcx, rsp; StackCookie
0x180004028  call    __security_check_cookie
0x18000402d  lea     r11, [rsp+278h+var_28]
0x180004035  mov     rbx, [r11+38h]
0x180004039  mov     rbp, [r11+40h]
0x18000403d  mov     rsp, r11
0x180004040  pop     r15
0x180004042  pop     r14
0x180004044  pop     r12
0x180004046  pop     rdi
0x180004047  pop     rsi
0x180004048  retn
0x180004049  mov     rcx, [rsp+278h]; this
0x180004051  mov     edx, 0A0Bh; void *
0x180004056  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000405c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004062  mov     rcx, [rsp+278h]; this
0x18000406a  mov     edx, 0A0Bh; void *
0x18000406f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
