# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180007be8`
- end: `0x180007e12`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007818`
- `0x1800187b4`

## callees

- `0x180003bb0`
- `0x180007be8`
- `0x180008578`
- `0x180009a54`
- `0x18000a4ac`
- `0x18000ab38`
- `0x18000ab48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007cac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007d4f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007cac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007da2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007da2`

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
0x180007be8  mov     [rsp+arg_8], rbx
0x180007bed  mov     [rsp+arg_10], rbp
0x180007bf2  push    rsi
0x180007bf3  push    rdi
0x180007bf4  push    r12
0x180007bf6  push    r14
0x180007bf8  push    r15
0x180007bfa  sub     rsp, 250h
0x180007c01  mov     rax, cs:__security_cookie
0x180007c08  xor     rax, rsp
0x180007c0b  mov     [rsp+278h+var_38], rax
0x180007c13  mov     rax, 0C000000000000000h
0x180007c1d  mov     rbp, r9
0x180007c20  mov     r8, rdx
0x180007c23  mov     rbx, rcx
0x180007c26  test    rax, r9
0x180007c29  jnz     loc_180007DF9
0x180007c2f  xor     r12d, r12d
0x180007c32  lea     rax, [rsp+278h+Name]
0x180007c37  mov     ecx, 7FFFFFFEh
0x180007c3c  mov     edx, 104h
0x180007c41  lea     esi, [r12+1]
0x180007c46  test    rcx, rcx
0x180007c49  jz      short loc_180007C69
0x180007c4b  movzx   r9d, word ptr [r8]
0x180007c4f  test    r9w, r9w
0x180007c53  jz      short loc_180007C69
0x180007c55  mov     [rax], r9w
0x180007c59  add     r8, 2
0x180007c5d  add     rax, 2
0x180007c61  sub     rcx, rsi
0x180007c64  sub     rdx, rsi; unsigned __int64
0x180007c67  jnz     short loc_180007C46
0x180007c69  test    rdx, rdx
0x180007c6c  lea     rcx, [rax-2]
0x180007c70  lea     r8, aP0; "_p0"
0x180007c77  cmovnz  rcx, rax
0x180007c7b  mov     [rcx], r12w
0x180007c7f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007c84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c89  mov     edx, ebp
0x180007c8b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007c93  and     edx, 7FFFFFFFh; lInitialCount
0x180007c99  mov     [rsp+278h+dwFlags], r12d; int
0x180007c9e  mov     r8d, esi
0x180007ca1  lea     r9, [rsp+278h+Name]; lpName
0x180007ca6  cmova   r8d, edx; lMaximumCount
0x180007caa  xor     ecx, ecx; lpSemaphoreAttributes
0x180007cac  call    cs:__imp_CreateSemaphoreExW
0x180007cb2  mov     r15, rax
0x180007cb5  test    rax, rax
0x180007cb8  jnz     short loc_180007CE8
0x180007cba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007cbf  mov     edi, eax
0x180007cc1  test    eax, eax
0x180007cc3  jns     short loc_180007D1C
0x180007cc5  mov     rcx, [rsp+278h]; this
0x180007ccd  lea     r8, aWil; "wil"
0x180007cd4  mov     r9d, eax; char *
0x180007cd7  mov     edx, 8Bh; void *
0x180007cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ce1  mov     eax, edi
0x180007ce3  jmp     loc_180007DBA
0x180007ce8  call    cs:__imp_GetLastError
0x180007cee  mov     rdi, [rbx]
0x180007cf1  test    rdi, rdi
0x180007cf4  jz      short loc_180007D19
0x180007cf6  call    cs:__imp_GetLastError
0x180007cfc  mov     rcx, rdi; hObject
0x180007cff  mov     r14d, eax
0x180007d02  call    cs:__imp_CloseHandle
0x180007d08  test    eax, eax
0x180007d0a  jz      loc_180007DFF
0x180007d10  mov     ecx, r14d; dwErrCode
0x180007d13  call    cs:__imp_SetLastError
0x180007d19  mov     [rbx], r15
0x180007d1c  lea     r8, asc_180067D30; "h"
0x180007d23  shr     rbp, 1Fh
0x180007d27  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180007d2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d31  test    ebp, ebp
0x180007d33  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007d3b  lea     r9, [rsp+278h+Name]; lpName
0x180007d40  mov     [rsp+278h+dwFlags], r12d; int
0x180007d45  cmovnz  esi, ebp
0x180007d48  mov     edx, ebp; lInitialCount
0x180007d4a  mov     r8d, esi; lMaximumCount
0x180007d4d  xor     ecx, ecx; lpSemaphoreAttributes
0x180007d4f  call    cs:__imp_CreateSemaphoreExW
0x180007d55  mov     rsi, rax
0x180007d58  test    rax, rax
0x180007d5b  jnz     short loc_180007D88
0x180007d5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007d62  mov     ebx, eax
0x180007d64  test    eax, eax
0x180007d66  jns     short loc_180007DB8
0x180007d68  mov     rcx, [rsp+278h]; this
0x180007d70  lea     r8, aWil; "wil"
0x180007d77  mov     r9d, eax; char *
0x180007d7a  mov     edx, 90h; void *
0x180007d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d84  mov     eax, ebx
0x180007d86  jmp     short loc_180007DBA
0x180007d88  call    cs:__imp_GetLastError
0x180007d8e  mov     rdi, [rbx+8]
0x180007d92  test    rdi, rdi
0x180007d95  jz      short loc_180007DB4
0x180007d97  call    cs:__imp_GetLastError
0x180007d9d  mov     rcx, rdi; hObject
0x180007da0  mov     ebp, eax
0x180007da2  call    cs:__imp_CloseHandle
0x180007da8  test    eax, eax
0x180007daa  jz      short loc_180007DE6
0x180007dac  mov     ecx, ebp; dwErrCode
0x180007dae  call    cs:__imp_SetLastError
0x180007db4  mov     [rbx+8], rsi
0x180007db8  xor     eax, eax
0x180007dba  mov     rcx, [rsp+278h+var_38]
0x180007dc2  xor     rcx, rsp; StackCookie
0x180007dc5  call    __security_check_cookie
0x180007dca  lea     r11, [rsp+278h+var_28]
0x180007dd2  mov     rbx, [r11+38h]
0x180007dd6  mov     rbp, [r11+40h]
0x180007dda  mov     rsp, r11
0x180007ddd  pop     r15
0x180007ddf  pop     r14
0x180007de1  pop     r12
0x180007de3  pop     rdi
0x180007de4  pop     rsi
0x180007de5  retn
0x180007de6  mov     rcx, [rsp+278h]; this
0x180007dee  mov     edx, 0A0Bh; void *
0x180007df3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007df9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007dff  mov     rcx, [rsp+278h]; this
0x180007e07  mov     edx, 0A0Bh; void *
0x180007e0c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
