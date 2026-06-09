# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180003990`
- end: `0x180003b9d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000321c`
- `0x1800035c0`

## callees

- `0x180003990`
- `0x1800047d8`
- `0x1800069d4`
- `0x180006f10`
- `0x180007c4c`
- `0x180007c5c`
- `0x18000c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a54`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003af0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003a54`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003aa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003aa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`

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
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
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
0x180003990  mov     [rsp+arg_8], rbx
0x180003995  mov     [rsp+arg_10], rbp
0x18000399a  push    rsi
0x18000399b  push    rdi
0x18000399c  push    r12
0x18000399e  push    r14
0x1800039a0  push    r15
0x1800039a2  sub     rsp, 250h
0x1800039a9  mov     rax, cs:__security_cookie
0x1800039b0  xor     rax, rsp
0x1800039b3  mov     [rsp+278h+var_38], rax
0x1800039bb  mov     rax, 0C000000000000000h
0x1800039c5  mov     rbp, r9
0x1800039c8  mov     r8, rdx
0x1800039cb  mov     rdi, rcx
0x1800039ce  test    rax, r9
0x1800039d1  jnz     loc_180003B84
0x1800039d7  xor     r12d, r12d
0x1800039da  lea     rax, [rsp+278h+Name]
0x1800039df  mov     ecx, 7FFFFFFEh
0x1800039e4  mov     edx, 104h
0x1800039e9  lea     esi, [r12+1]
0x1800039ee  test    rcx, rcx
0x1800039f1  jz      short loc_180003A11
0x1800039f3  movzx   r9d, word ptr [r8]
0x1800039f7  test    r9w, r9w
0x1800039fb  jz      short loc_180003A11
0x1800039fd  mov     [rax], r9w
0x180003a01  add     r8, 2
0x180003a05  add     rax, 2
0x180003a09  sub     rcx, rsi
0x180003a0c  sub     rdx, rsi; unsigned __int64
0x180003a0f  jnz     short loc_1800039EE
0x180003a11  test    rdx, rdx
0x180003a14  lea     rcx, [rax-2]
0x180003a18  lea     r8, aP0; "_p0"
0x180003a1f  cmovnz  rcx, rax
0x180003a23  mov     [rcx], r12w
0x180003a27  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003a2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003a31  mov     edx, ebp
0x180003a33  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003a3b  and     edx, 7FFFFFFFh; lInitialCount
0x180003a41  mov     [rsp+278h+dwFlags], r12d; int
0x180003a46  mov     r8d, esi
0x180003a49  lea     r9, [rsp+278h+Name]; lpName
0x180003a4e  cmova   r8d, edx; lMaximumCount
0x180003a52  xor     ecx, ecx; lpSemaphoreAttributes
0x180003a54  call    cs:__imp_CreateSemaphoreExW
0x180003a5a  mov     r15, rax
0x180003a5d  test    rax, rax
0x180003a60  jnz     short loc_180003A89
0x180003a62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a67  mov     ebx, eax
0x180003a69  test    eax, eax
0x180003a6b  jns     short loc_180003ABD
0x180003a6d  mov     edx, 8Bh; void *
0x180003a72  mov     rcx, [rsp+278h]; this
0x180003a7a  mov     r9d, ebx; char *
0x180003a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a82  mov     eax, ebx
0x180003a84  jmp     loc_180003B45
0x180003a89  call    cs:__imp_GetLastError
0x180003a8f  mov     rbx, [rdi]
0x180003a92  test    rbx, rbx
0x180003a95  jz      short loc_180003ABA
0x180003a97  call    cs:__imp_GetLastError
0x180003a9d  mov     rcx, rbx; hObject
0x180003aa0  mov     r14d, eax
0x180003aa3  call    cs:__imp_CloseHandle
0x180003aa9  test    eax, eax
0x180003aab  jz      loc_180003B8A
0x180003ab1  mov     ecx, r14d; dwErrCode
0x180003ab4  call    cs:__imp_SetLastError
0x180003aba  mov     [rdi], r15
0x180003abd  lea     r8, asc_18000EB40; "h"
0x180003ac4  shr     rbp, 1Fh
0x180003ac8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180003acd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003ad2  test    ebp, ebp
0x180003ad4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003adc  lea     r9, [rsp+278h+Name]; lpName
0x180003ae1  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180003ae6  cmovnz  esi, ebp
0x180003ae9  mov     edx, ebp; lInitialCount
0x180003aeb  mov     r8d, esi; lMaximumCount
0x180003aee  xor     ecx, ecx; lpSemaphoreAttributes
0x180003af0  call    cs:__imp_CreateSemaphoreExW
0x180003af6  mov     rsi, rax
0x180003af9  test    rax, rax
0x180003afc  jnz     short loc_180003B13
0x180003afe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b03  mov     ebx, eax
0x180003b05  test    eax, eax
0x180003b07  jns     short loc_180003B43
0x180003b09  mov     edx, 90h
0x180003b0e  jmp     loc_180003A72
0x180003b13  call    cs:__imp_GetLastError
0x180003b19  mov     rbx, [rdi+8]
0x180003b1d  test    rbx, rbx
0x180003b20  jz      short loc_180003B3F
0x180003b22  call    cs:__imp_GetLastError
0x180003b28  mov     rcx, rbx; hObject
0x180003b2b  mov     ebp, eax
0x180003b2d  call    cs:__imp_CloseHandle
0x180003b33  test    eax, eax
0x180003b35  jz      short loc_180003B71
0x180003b37  mov     ecx, ebp; dwErrCode
0x180003b39  call    cs:__imp_SetLastError
0x180003b3f  mov     [rdi+8], rsi
0x180003b43  xor     eax, eax
0x180003b45  mov     rcx, [rsp+278h+var_38]
0x180003b4d  xor     rcx, rsp; StackCookie
0x180003b50  call    __security_check_cookie
0x180003b55  lea     r11, [rsp+278h+var_28]
0x180003b5d  mov     rbx, [r11+38h]
0x180003b61  mov     rbp, [r11+40h]
0x180003b65  mov     rsp, r11
0x180003b68  pop     r15
0x180003b6a  pop     r14
0x180003b6c  pop     r12
0x180003b6e  pop     rdi
0x180003b6f  pop     rsi
0x180003b70  retn
0x180003b71  mov     rcx, [rsp+278h]; this
0x180003b79  mov     edx, 0A0Bh; void *
0x180003b7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b84  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003b8a  mov     rcx, [rsp+278h]; this
0x180003b92  mov     edx, 0A0Bh; void *
0x180003b97  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
