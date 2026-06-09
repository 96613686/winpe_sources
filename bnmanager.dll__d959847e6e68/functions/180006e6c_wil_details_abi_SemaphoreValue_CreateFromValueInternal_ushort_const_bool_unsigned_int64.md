# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180006e6c`
- end: `0x180007079`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005ad8`
- `0x180005e7c`

## callees

- `0x1800017c0`
- `0x180006e6c`
- `0x180008178`
- `0x18000a534`
- `0x18000af90`
- `0x18000bb7c`
- `0x18000bb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ffe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007009`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006f30`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006fcc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006f30`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006fcc`

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
0x180006e6c  mov     [rsp+arg_8], rbx
0x180006e71  mov     [rsp+arg_10], rbp
0x180006e76  push    rsi
0x180006e77  push    rdi
0x180006e78  push    r12
0x180006e7a  push    r14
0x180006e7c  push    r15
0x180006e7e  sub     rsp, 250h
0x180006e85  mov     rax, cs:__security_cookie
0x180006e8c  xor     rax, rsp
0x180006e8f  mov     [rsp+278h+var_38], rax
0x180006e97  mov     rax, 0C000000000000000h
0x180006ea1  mov     rbp, r9
0x180006ea4  mov     r8, rdx
0x180006ea7  mov     rdi, rcx
0x180006eaa  test    rax, r9
0x180006ead  jnz     loc_180007060
0x180006eb3  xor     r12d, r12d
0x180006eb6  lea     rax, [rsp+278h+Name]
0x180006ebb  mov     ecx, 7FFFFFFEh
0x180006ec0  mov     edx, 104h
0x180006ec5  lea     esi, [r12+1]
0x180006eca  test    rcx, rcx
0x180006ecd  jz      short loc_180006EED
0x180006ecf  movzx   r9d, word ptr [r8]
0x180006ed3  test    r9w, r9w
0x180006ed7  jz      short loc_180006EED
0x180006ed9  mov     [rax], r9w
0x180006edd  add     r8, 2
0x180006ee1  add     rax, 2
0x180006ee5  sub     rcx, rsi
0x180006ee8  sub     rdx, rsi; unsigned __int64
0x180006eeb  jnz     short loc_180006ECA
0x180006eed  test    rdx, rdx
0x180006ef0  lea     rcx, [rax-2]
0x180006ef4  lea     r8, aP0; "_p0"
0x180006efb  cmovnz  rcx, rax
0x180006eff  mov     [rcx], r12w
0x180006f03  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006f08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f0d  mov     edx, ebp
0x180006f0f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006f17  and     edx, 7FFFFFFFh; lInitialCount
0x180006f1d  mov     [rsp+278h+dwFlags], r12d; int
0x180006f22  mov     r8d, esi
0x180006f25  lea     r9, [rsp+278h+Name]; lpName
0x180006f2a  cmova   r8d, edx; lMaximumCount
0x180006f2e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006f30  call    cs:__imp_CreateSemaphoreExW
0x180006f36  mov     r15, rax
0x180006f39  test    rax, rax
0x180006f3c  jnz     short loc_180006F65
0x180006f3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006f43  mov     ebx, eax
0x180006f45  test    eax, eax
0x180006f47  jns     short loc_180006F99
0x180006f49  mov     edx, 8Bh; void *
0x180006f4e  mov     rcx, [rsp+278h]; this
0x180006f56  mov     r9d, ebx; char *
0x180006f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f5e  mov     eax, ebx
0x180006f60  jmp     loc_180007021
0x180006f65  call    cs:__imp_GetLastError
0x180006f6b  mov     rbx, [rdi]
0x180006f6e  test    rbx, rbx
0x180006f71  jz      short loc_180006F96
0x180006f73  call    cs:__imp_GetLastError
0x180006f79  mov     rcx, rbx; hObject
0x180006f7c  mov     r14d, eax
0x180006f7f  call    cs:__imp_CloseHandle
0x180006f85  test    eax, eax
0x180006f87  jz      loc_180007066
0x180006f8d  mov     ecx, r14d; dwErrCode
0x180006f90  call    cs:__imp_SetLastError
0x180006f96  mov     [rdi], r15
0x180006f99  lea     r8, asc_18000EC28; "h"
0x180006fa0  shr     rbp, 1Fh
0x180006fa4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180006fa9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006fae  test    ebp, ebp
0x180006fb0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006fb8  lea     r9, [rsp+278h+Name]; lpName
0x180006fbd  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180006fc2  cmovnz  esi, ebp
0x180006fc5  mov     edx, ebp; lInitialCount
0x180006fc7  mov     r8d, esi; lMaximumCount
0x180006fca  xor     ecx, ecx; lpSemaphoreAttributes
0x180006fcc  call    cs:__imp_CreateSemaphoreExW
0x180006fd2  mov     rsi, rax
0x180006fd5  test    rax, rax
0x180006fd8  jnz     short loc_180006FEF
0x180006fda  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006fdf  mov     ebx, eax
0x180006fe1  test    eax, eax
0x180006fe3  jns     short loc_18000701F
0x180006fe5  mov     edx, 90h
0x180006fea  jmp     loc_180006F4E
0x180006fef  call    cs:__imp_GetLastError
0x180006ff5  mov     rbx, [rdi+8]
0x180006ff9  test    rbx, rbx
0x180006ffc  jz      short loc_18000701B
0x180006ffe  call    cs:__imp_GetLastError
0x180007004  mov     rcx, rbx; hObject
0x180007007  mov     ebp, eax
0x180007009  call    cs:__imp_CloseHandle
0x18000700f  test    eax, eax
0x180007011  jz      short loc_18000704D
0x180007013  mov     ecx, ebp; dwErrCode
0x180007015  call    cs:__imp_SetLastError
0x18000701b  mov     [rdi+8], rsi
0x18000701f  xor     eax, eax
0x180007021  mov     rcx, [rsp+278h+var_38]
0x180007029  xor     rcx, rsp; StackCookie
0x18000702c  call    __security_check_cookie
0x180007031  lea     r11, [rsp+278h+var_28]
0x180007039  mov     rbx, [r11+38h]
0x18000703d  mov     rbp, [r11+40h]
0x180007041  mov     rsp, r11
0x180007044  pop     r15
0x180007046  pop     r14
0x180007048  pop     r12
0x18000704a  pop     rdi
0x18000704b  pop     rsi
0x18000704c  retn
0x18000704d  mov     rcx, [rsp+278h]; this
0x180007055  mov     edx, 0A0Bh; void *
0x18000705a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007060  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007066  mov     rcx, [rsp+278h]; this
0x18000706e  mov     edx, 0A0Bh; void *
0x180007073  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
