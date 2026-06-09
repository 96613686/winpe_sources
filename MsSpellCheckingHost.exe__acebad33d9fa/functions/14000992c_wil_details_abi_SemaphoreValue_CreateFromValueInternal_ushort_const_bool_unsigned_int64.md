# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x14000992c`
- end: `0x140009b39`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140009088`
- `0x14000942c`

## callees

- `0x14000992c`
- `0x14000a7c8`
- `0x14000d2a4`
- `0x14000dbd0`
- `0x14000ecd4`
- `0x14000ece4`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009abe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009a50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009ad5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009a50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009a3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009ac9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400099f0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009a8c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400099f0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140009a8c`

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
0x14000992c  mov     [rsp+arg_8], rbx
0x140009931  mov     [rsp+arg_10], rbp
0x140009936  push    rsi
0x140009937  push    rdi
0x140009938  push    r12
0x14000993a  push    r14
0x14000993c  push    r15
0x14000993e  sub     rsp, 250h
0x140009945  mov     rax, cs:__security_cookie
0x14000994c  xor     rax, rsp
0x14000994f  mov     [rsp+278h+var_38], rax
0x140009957  mov     rax, 0C000000000000000h
0x140009961  mov     rbp, r9
0x140009964  mov     r8, rdx
0x140009967  mov     rdi, rcx
0x14000996a  test    rax, r9
0x14000996d  jnz     loc_140009B20
0x140009973  xor     r12d, r12d
0x140009976  lea     rax, [rsp+278h+Name]
0x14000997b  mov     ecx, 7FFFFFFEh
0x140009980  mov     edx, 104h
0x140009985  lea     esi, [r12+1]
0x14000998a  test    rcx, rcx
0x14000998d  jz      short loc_1400099AD
0x14000998f  movzx   r9d, word ptr [r8]
0x140009993  test    r9w, r9w
0x140009997  jz      short loc_1400099AD
0x140009999  mov     [rax], r9w
0x14000999d  add     r8, 2
0x1400099a1  add     rax, 2
0x1400099a5  sub     rcx, rsi
0x1400099a8  sub     rdx, rsi; unsigned __int64
0x1400099ab  jnz     short loc_14000998A
0x1400099ad  test    rdx, rdx
0x1400099b0  lea     rcx, [rax-2]
0x1400099b4  lea     r8, aP0; "_p0"
0x1400099bb  cmovnz  rcx, rax
0x1400099bf  mov     [rcx], r12w
0x1400099c3  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400099c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400099cd  mov     edx, ebp
0x1400099cf  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400099d7  and     edx, 7FFFFFFFh; lInitialCount
0x1400099dd  mov     [rsp+278h+dwFlags], r12d; int
0x1400099e2  mov     r8d, esi
0x1400099e5  lea     r9, [rsp+278h+Name]; lpName
0x1400099ea  cmova   r8d, edx; lMaximumCount
0x1400099ee  xor     ecx, ecx; lpSemaphoreAttributes
0x1400099f0  call    cs:__imp_CreateSemaphoreExW
0x1400099f6  mov     r15, rax
0x1400099f9  test    rax, rax
0x1400099fc  jnz     short loc_140009A25
0x1400099fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009a03  mov     ebx, eax
0x140009a05  test    eax, eax
0x140009a07  jns     short loc_140009A59
0x140009a09  mov     edx, 8Bh; void *
0x140009a0e  mov     rcx, [rsp+278h]; this
0x140009a16  mov     r9d, ebx; char *
0x140009a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009a1e  mov     eax, ebx
0x140009a20  jmp     loc_140009AE1
0x140009a25  call    cs:__imp_GetLastError
0x140009a2b  mov     rbx, [rdi]
0x140009a2e  test    rbx, rbx
0x140009a31  jz      short loc_140009A56
0x140009a33  call    cs:__imp_GetLastError
0x140009a39  mov     rcx, rbx; hObject
0x140009a3c  mov     r14d, eax
0x140009a3f  call    cs:__imp_CloseHandle
0x140009a45  test    eax, eax
0x140009a47  jz      loc_140009B26
0x140009a4d  mov     ecx, r14d; dwErrCode
0x140009a50  call    cs:__imp_SetLastError
0x140009a56  mov     [rdi], r15
0x140009a59  lea     r8, asc_140016FF0; "h"
0x140009a60  shr     rbp, 1Fh
0x140009a64  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140009a69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009a6e  test    ebp, ebp
0x140009a70  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009a78  lea     r9, [rsp+278h+Name]; lpName
0x140009a7d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140009a82  cmovnz  esi, ebp
0x140009a85  mov     edx, ebp; lInitialCount
0x140009a87  mov     r8d, esi; lMaximumCount
0x140009a8a  xor     ecx, ecx; lpSemaphoreAttributes
0x140009a8c  call    cs:__imp_CreateSemaphoreExW
0x140009a92  mov     rsi, rax
0x140009a95  test    rax, rax
0x140009a98  jnz     short loc_140009AAF
0x140009a9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009a9f  mov     ebx, eax
0x140009aa1  test    eax, eax
0x140009aa3  jns     short loc_140009ADF
0x140009aa5  mov     edx, 90h
0x140009aaa  jmp     loc_140009A0E
0x140009aaf  call    cs:__imp_GetLastError
0x140009ab5  mov     rbx, [rdi+8]
0x140009ab9  test    rbx, rbx
0x140009abc  jz      short loc_140009ADB
0x140009abe  call    cs:__imp_GetLastError
0x140009ac4  mov     rcx, rbx; hObject
0x140009ac7  mov     ebp, eax
0x140009ac9  call    cs:__imp_CloseHandle
0x140009acf  test    eax, eax
0x140009ad1  jz      short loc_140009B0D
0x140009ad3  mov     ecx, ebp; dwErrCode
0x140009ad5  call    cs:__imp_SetLastError
0x140009adb  mov     [rdi+8], rsi
0x140009adf  xor     eax, eax
0x140009ae1  mov     rcx, [rsp+278h+var_38]
0x140009ae9  xor     rcx, rsp; StackCookie
0x140009aec  call    __security_check_cookie
0x140009af1  lea     r11, [rsp+278h+var_28]
0x140009af9  mov     rbx, [r11+38h]
0x140009afd  mov     rbp, [r11+40h]
0x140009b01  mov     rsp, r11
0x140009b04  pop     r15
0x140009b06  pop     r14
0x140009b08  pop     r12
0x140009b0a  pop     rdi
0x140009b0b  pop     rsi
0x140009b0c  retn
0x140009b0d  mov     rcx, [rsp+278h]; this
0x140009b15  mov     edx, 0A0Bh; void *
0x140009b1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009b20  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009b26  mov     rcx, [rsp+278h]; this
0x140009b2e  mov     edx, 0A0Bh; void *
0x140009b33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
