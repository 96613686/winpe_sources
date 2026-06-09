# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003d30`
- end: `0x140003f5a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003960`
- `0x140008710`

## callees

- `0x140003d30`
- `0x1400045a8`
- `0x140005474`
- `0x140005bf4`
- `0x140006234`
- `0x140006244`
- `0x14000e1c0`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140003df4`
- `KERNEL32!CreateSemaphoreExW` at `0x140003e97`
- `KERNEL32!CreateSemaphoreExW` at `0x140003df4`
- `KERNEL32!CreateSemaphoreExW` at `0x140003e97`
- `KERNEL32!SetLastError` at `0x140003e5b`
- `KERNEL32!SetLastError` at `0x140003ef6`
- `KERNEL32!SetLastError` at `0x140003e5b`
- `KERNEL32!SetLastError` at `0x140003ef6`
- `KERNEL32!GetLastError` at `0x140003e30`
- `KERNEL32!GetLastError` at `0x140003e3e`
- `KERNEL32!GetLastError` at `0x140003ed0`
- `KERNEL32!GetLastError` at `0x140003edf`
- `KERNEL32!GetLastError` at `0x140003e30`
- `KERNEL32!GetLastError` at `0x140003e3e`
- `KERNEL32!GetLastError` at `0x140003ed0`
- `KERNEL32!GetLastError` at `0x140003edf`
- `KERNEL32!CloseHandle` at `0x140003e4a`
- `KERNEL32!CloseHandle` at `0x140003eea`
- `KERNEL32!CloseHandle` at `0x140003e4a`
- `KERNEL32!CloseHandle` at `0x140003eea`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int64 v23; // rbp
  wil::details *v24; // rcx
  HANDLE v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  void *v28; // rdi
  DWORD v29; // ebp
  unsigned int v30; // r8d
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
0x140003d30  mov     [rsp+arg_8], rbx
0x140003d35  mov     [rsp+arg_10], rbp
0x140003d3a  push    rsi
0x140003d3b  push    rdi
0x140003d3c  push    r12
0x140003d3e  push    r14
0x140003d40  push    r15
0x140003d42  sub     rsp, 250h
0x140003d49  mov     rax, cs:__security_cookie
0x140003d50  xor     rax, rsp
0x140003d53  mov     [rsp+278h+var_38], rax
0x140003d5b  mov     rax, 0C000000000000000h
0x140003d65  mov     rbp, r9
0x140003d68  mov     r8, rdx
0x140003d6b  mov     rbx, rcx
0x140003d6e  test    rax, r9
0x140003d71  jnz     loc_140003F41
0x140003d77  xor     r12d, r12d
0x140003d7a  lea     rax, [rsp+278h+Name]
0x140003d7f  mov     ecx, 7FFFFFFEh
0x140003d84  mov     edx, 104h
0x140003d89  lea     esi, [r12+1]
0x140003d8e  test    rcx, rcx
0x140003d91  jz      short loc_140003DB1
0x140003d93  movzx   r9d, word ptr [r8]
0x140003d97  test    r9w, r9w
0x140003d9b  jz      short loc_140003DB1
0x140003d9d  mov     [rax], r9w
0x140003da1  add     r8, 2
0x140003da5  add     rax, 2
0x140003da9  sub     rcx, rsi
0x140003dac  sub     rdx, rsi; unsigned __int64
0x140003daf  jnz     short loc_140003D8E
0x140003db1  test    rdx, rdx
0x140003db4  lea     rcx, [rax-2]
0x140003db8  lea     r8, aP0; "_p0"
0x140003dbf  cmovnz  rcx, rax
0x140003dc3  mov     [rcx], r12w
0x140003dc7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003dcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003dd1  mov     edx, ebp
0x140003dd3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003ddb  and     edx, 7FFFFFFFh; lInitialCount
0x140003de1  mov     [rsp+278h+dwFlags], r12d; int
0x140003de6  mov     r8d, esi
0x140003de9  lea     r9, [rsp+278h+Name]; lpName
0x140003dee  cmova   r8d, edx; lMaximumCount
0x140003df2  xor     ecx, ecx; lpSemaphoreAttributes
0x140003df4  call    cs:__imp_CreateSemaphoreExW
0x140003dfa  mov     r15, rax
0x140003dfd  test    rax, rax
0x140003e00  jnz     short loc_140003E30
0x140003e02  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003e07  mov     edi, eax
0x140003e09  test    eax, eax
0x140003e0b  jns     short loc_140003E64
0x140003e0d  mov     rcx, [rsp+278h]; this
0x140003e15  lea     r8, aWil; "wil"
0x140003e1c  mov     r9d, eax; char *
0x140003e1f  mov     edx, 8Bh; void *
0x140003e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e29  mov     eax, edi
0x140003e2b  jmp     loc_140003F02
0x140003e30  call    cs:__imp_GetLastError
0x140003e36  mov     rdi, [rbx]
0x140003e39  test    rdi, rdi
0x140003e3c  jz      short loc_140003E61
0x140003e3e  call    cs:__imp_GetLastError
0x140003e44  mov     rcx, rdi; hObject
0x140003e47  mov     r14d, eax
0x140003e4a  call    cs:__imp_CloseHandle
0x140003e50  test    eax, eax
0x140003e52  jz      loc_140003F47
0x140003e58  mov     ecx, r14d; dwErrCode
0x140003e5b  call    cs:__imp_SetLastError
0x140003e61  mov     [rbx], r15
0x140003e64  lea     r8, asc_140013478; "h"
0x140003e6b  shr     rbp, 1Fh
0x140003e6f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003e74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003e79  test    ebp, ebp
0x140003e7b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003e83  lea     r9, [rsp+278h+Name]; lpName
0x140003e88  mov     [rsp+278h+dwFlags], r12d; int
0x140003e8d  cmovnz  esi, ebp
0x140003e90  mov     edx, ebp; lInitialCount
0x140003e92  mov     r8d, esi; lMaximumCount
0x140003e95  xor     ecx, ecx; lpSemaphoreAttributes
0x140003e97  call    cs:__imp_CreateSemaphoreExW
0x140003e9d  mov     rsi, rax
0x140003ea0  test    rax, rax
0x140003ea3  jnz     short loc_140003ED0
0x140003ea5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003eaa  mov     ebx, eax
0x140003eac  test    eax, eax
0x140003eae  jns     short loc_140003F00
0x140003eb0  mov     rcx, [rsp+278h]; this
0x140003eb8  lea     r8, aWil; "wil"
0x140003ebf  mov     r9d, eax; char *
0x140003ec2  mov     edx, 90h; void *
0x140003ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ecc  mov     eax, ebx
0x140003ece  jmp     short loc_140003F02
0x140003ed0  call    cs:__imp_GetLastError
0x140003ed6  mov     rdi, [rbx+8]
0x140003eda  test    rdi, rdi
0x140003edd  jz      short loc_140003EFC
0x140003edf  call    cs:__imp_GetLastError
0x140003ee5  mov     rcx, rdi; hObject
0x140003ee8  mov     ebp, eax
0x140003eea  call    cs:__imp_CloseHandle
0x140003ef0  test    eax, eax
0x140003ef2  jz      short loc_140003F2E
0x140003ef4  mov     ecx, ebp; dwErrCode
0x140003ef6  call    cs:__imp_SetLastError
0x140003efc  mov     [rbx+8], rsi
0x140003f00  xor     eax, eax
0x140003f02  mov     rcx, [rsp+278h+var_38]
0x140003f0a  xor     rcx, rsp; StackCookie
0x140003f0d  call    __security_check_cookie
0x140003f12  lea     r11, [rsp+278h+var_28]
0x140003f1a  mov     rbx, [r11+38h]
0x140003f1e  mov     rbp, [r11+40h]
0x140003f22  mov     rsp, r11
0x140003f25  pop     r15
0x140003f27  pop     r14
0x140003f29  pop     r12
0x140003f2b  pop     rdi
0x140003f2c  pop     rsi
0x140003f2d  retn
0x140003f2e  mov     rcx, [rsp+278h]; this
0x140003f36  mov     edx, 0A0Bh; void *
0x140003f3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f41  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003f47  mov     rcx, [rsp+278h]; this
0x140003f4f  mov     edx, 0A0Bh; void *
0x140003f54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
