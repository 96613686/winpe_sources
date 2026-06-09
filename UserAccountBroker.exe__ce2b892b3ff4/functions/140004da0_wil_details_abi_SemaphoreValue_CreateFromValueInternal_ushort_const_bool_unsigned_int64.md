# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140004da0`
- end: `0x140004fca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400049d0`

## callees

- `0x140004da0`
- `0x140005698`
- `0x140006314`
- `0x1400065c4`
- `0x140006abc`
- `0x140006acc`
- `0x140006b90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004ea0`
- `KERNEL32!GetLastError` at `0x140004eae`
- `KERNEL32!GetLastError` at `0x140004f40`
- `KERNEL32!GetLastError` at `0x140004f4f`
- `KERNEL32!GetLastError` at `0x140004ea0`
- `KERNEL32!GetLastError` at `0x140004eae`
- `KERNEL32!GetLastError` at `0x140004f40`
- `KERNEL32!GetLastError` at `0x140004f4f`
- `KERNEL32!CloseHandle` at `0x140004eba`
- `KERNEL32!CloseHandle` at `0x140004f5a`
- `KERNEL32!CloseHandle` at `0x140004eba`
- `KERNEL32!CloseHandle` at `0x140004f5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004f66`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e64`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004f07`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004e64`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140004f07`

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
0x140004da0  mov     [rsp+arg_8], rbx
0x140004da5  mov     [rsp+arg_10], rbp
0x140004daa  push    rsi
0x140004dab  push    rdi
0x140004dac  push    r12
0x140004dae  push    r14
0x140004db0  push    r15
0x140004db2  sub     rsp, 250h
0x140004db9  mov     rax, cs:__security_cookie
0x140004dc0  xor     rax, rsp
0x140004dc3  mov     [rsp+278h+var_38], rax
0x140004dcb  mov     rax, 0C000000000000000h
0x140004dd5  mov     rbp, r9
0x140004dd8  mov     r8, rdx
0x140004ddb  mov     rbx, rcx
0x140004dde  test    rax, r9
0x140004de1  jnz     loc_140004FB1
0x140004de7  xor     r12d, r12d
0x140004dea  lea     rax, [rsp+278h+Name]
0x140004def  mov     ecx, 7FFFFFFEh
0x140004df4  mov     edx, 104h
0x140004df9  lea     esi, [r12+1]
0x140004dfe  test    rcx, rcx
0x140004e01  jz      short loc_140004E21
0x140004e03  movzx   r9d, word ptr [r8]
0x140004e07  test    r9w, r9w
0x140004e0b  jz      short loc_140004E21
0x140004e0d  mov     [rax], r9w
0x140004e11  add     r8, 2
0x140004e15  add     rax, 2
0x140004e19  sub     rcx, rsi
0x140004e1c  sub     rdx, rsi; unsigned __int64
0x140004e1f  jnz     short loc_140004DFE
0x140004e21  test    rdx, rdx
0x140004e24  lea     rcx, [rax-2]
0x140004e28  lea     r8, aP0; "_p0"
0x140004e2f  cmovnz  rcx, rax
0x140004e33  mov     [rcx], r12w
0x140004e37  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004e3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004e41  mov     edx, ebp
0x140004e43  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004e4b  and     edx, 7FFFFFFFh; lInitialCount
0x140004e51  mov     [rsp+278h+dwFlags], r12d; int
0x140004e56  mov     r8d, esi
0x140004e59  lea     r9, [rsp+278h+Name]; lpName
0x140004e5e  cmova   r8d, edx; lMaximumCount
0x140004e62  xor     ecx, ecx; lpSemaphoreAttributes
0x140004e64  call    cs:__imp_CreateSemaphoreExW
0x140004e6a  mov     r15, rax
0x140004e6d  test    rax, rax
0x140004e70  jnz     short loc_140004EA0
0x140004e72  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004e77  mov     edi, eax
0x140004e79  test    eax, eax
0x140004e7b  jns     short loc_140004ED4
0x140004e7d  mov     rcx, [rsp+278h]; this
0x140004e85  lea     r8, aWil; "wil"
0x140004e8c  mov     r9d, eax; char *
0x140004e8f  mov     edx, 8Bh; void *
0x140004e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e99  mov     eax, edi
0x140004e9b  jmp     loc_140004F72
0x140004ea0  call    cs:__imp_GetLastError
0x140004ea6  mov     rdi, [rbx]
0x140004ea9  test    rdi, rdi
0x140004eac  jz      short loc_140004ED1
0x140004eae  call    cs:__imp_GetLastError
0x140004eb4  mov     rcx, rdi; hObject
0x140004eb7  mov     r14d, eax
0x140004eba  call    cs:__imp_CloseHandle
0x140004ec0  test    eax, eax
0x140004ec2  jz      loc_140004FB7
0x140004ec8  mov     ecx, r14d; dwErrCode
0x140004ecb  call    cs:__imp_SetLastError
0x140004ed1  mov     [rbx], r15
0x140004ed4  lea     r8, asc_140009D10; "h"
0x140004edb  shr     rbp, 1Fh
0x140004edf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004ee4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004ee9  test    ebp, ebp
0x140004eeb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004ef3  lea     r9, [rsp+278h+Name]; lpName
0x140004ef8  mov     [rsp+278h+dwFlags], r12d; int
0x140004efd  cmovnz  esi, ebp
0x140004f00  mov     edx, ebp; lInitialCount
0x140004f02  mov     r8d, esi; lMaximumCount
0x140004f05  xor     ecx, ecx; lpSemaphoreAttributes
0x140004f07  call    cs:__imp_CreateSemaphoreExW
0x140004f0d  mov     rsi, rax
0x140004f10  test    rax, rax
0x140004f13  jnz     short loc_140004F40
0x140004f15  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004f1a  mov     ebx, eax
0x140004f1c  test    eax, eax
0x140004f1e  jns     short loc_140004F70
0x140004f20  mov     rcx, [rsp+278h]; this
0x140004f28  lea     r8, aWil; "wil"
0x140004f2f  mov     r9d, eax; char *
0x140004f32  mov     edx, 90h; void *
0x140004f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f3c  mov     eax, ebx
0x140004f3e  jmp     short loc_140004F72
0x140004f40  call    cs:__imp_GetLastError
0x140004f46  mov     rdi, [rbx+8]
0x140004f4a  test    rdi, rdi
0x140004f4d  jz      short loc_140004F6C
0x140004f4f  call    cs:__imp_GetLastError
0x140004f55  mov     rcx, rdi; hObject
0x140004f58  mov     ebp, eax
0x140004f5a  call    cs:__imp_CloseHandle
0x140004f60  test    eax, eax
0x140004f62  jz      short loc_140004F9E
0x140004f64  mov     ecx, ebp; dwErrCode
0x140004f66  call    cs:__imp_SetLastError
0x140004f6c  mov     [rbx+8], rsi
0x140004f70  xor     eax, eax
0x140004f72  mov     rcx, [rsp+278h+var_38]
0x140004f7a  xor     rcx, rsp; StackCookie
0x140004f7d  call    __security_check_cookie
0x140004f82  lea     r11, [rsp+278h+var_28]
0x140004f8a  mov     rbx, [r11+38h]
0x140004f8e  mov     rbp, [r11+40h]
0x140004f92  mov     rsp, r11
0x140004f95  pop     r15
0x140004f97  pop     r14
0x140004f99  pop     r12
0x140004f9b  pop     rdi
0x140004f9c  pop     rsi
0x140004f9d  retn
0x140004f9e  mov     rcx, [rsp+278h]; this
0x140004fa6  mov     edx, 0A0Bh; void *
0x140004fab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004fb1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004fb7  mov     rcx, [rsp+278h]; this
0x140004fbf  mov     edx, 0A0Bh; void *
0x140004fc4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
