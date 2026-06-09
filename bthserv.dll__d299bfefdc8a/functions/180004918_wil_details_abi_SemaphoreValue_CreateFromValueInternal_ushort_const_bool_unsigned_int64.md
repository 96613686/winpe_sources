# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004918`
- end: `0x180004b42`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004148`
- `0x18000451c`

## callees

- `0x180001790`
- `0x180004918`
- `0x180005788`
- `0x180007be4`
- `0x180008628`
- `0x18000943c`
- `0x18000944c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a7f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800049dc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180004918  mov     [rsp+arg_8], rbx
0x18000491d  mov     [rsp+arg_10], rbp
0x180004922  push    rsi
0x180004923  push    rdi
0x180004924  push    r12
0x180004926  push    r14
0x180004928  push    r15
0x18000492a  sub     rsp, 250h
0x180004931  mov     rax, cs:__security_cookie
0x180004938  xor     rax, rsp
0x18000493b  mov     [rsp+278h+var_38], rax
0x180004943  mov     rax, 0C000000000000000h
0x18000494d  mov     rbp, r9
0x180004950  mov     r8, rdx
0x180004953  mov     rbx, rcx
0x180004956  test    rax, r9
0x180004959  jnz     loc_180004B29
0x18000495f  xor     r12d, r12d
0x180004962  lea     rax, [rsp+278h+Name]
0x180004967  mov     ecx, 7FFFFFFEh
0x18000496c  mov     edx, 104h
0x180004971  lea     esi, [r12+1]
0x180004976  test    rcx, rcx
0x180004979  jz      short loc_180004999
0x18000497b  movzx   r9d, word ptr [r8]
0x18000497f  test    r9w, r9w
0x180004983  jz      short loc_180004999
0x180004985  mov     [rax], r9w
0x180004989  add     r8, 2
0x18000498d  add     rax, 2
0x180004991  sub     rcx, rsi
0x180004994  sub     rdx, rsi; unsigned __int64
0x180004997  jnz     short loc_180004976
0x180004999  test    rdx, rdx
0x18000499c  lea     rcx, [rax-2]
0x1800049a0  lea     r8, aP0; "_p0"
0x1800049a7  cmovnz  rcx, rax
0x1800049ab  mov     [rcx], r12w
0x1800049af  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800049b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800049b9  mov     edx, ebp
0x1800049bb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800049c3  and     edx, 7FFFFFFFh; lInitialCount
0x1800049c9  mov     [rsp+278h+dwFlags], r12d; int
0x1800049ce  mov     r8d, esi
0x1800049d1  lea     r9, [rsp+278h+Name]; lpName
0x1800049d6  cmova   r8d, edx; lMaximumCount
0x1800049da  xor     ecx, ecx; lpSemaphoreAttributes
0x1800049dc  call    cs:__imp_CreateSemaphoreExW
0x1800049e2  mov     r15, rax
0x1800049e5  test    rax, rax
0x1800049e8  jnz     short loc_180004A18
0x1800049ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049ef  mov     edi, eax
0x1800049f1  test    eax, eax
0x1800049f3  jns     short loc_180004A4C
0x1800049f5  mov     rcx, [rsp+278h]; this
0x1800049fd  lea     r8, aWil; "wil"
0x180004a04  mov     r9d, eax; char *
0x180004a07  mov     edx, 8Bh; void *
0x180004a0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a11  mov     eax, edi
0x180004a13  jmp     loc_180004AEA
0x180004a18  call    cs:__imp_GetLastError
0x180004a1e  mov     rdi, [rbx]
0x180004a21  test    rdi, rdi
0x180004a24  jz      short loc_180004A49
0x180004a26  call    cs:__imp_GetLastError
0x180004a2c  mov     rcx, rdi; hObject
0x180004a2f  mov     r14d, eax
0x180004a32  call    cs:__imp_CloseHandle
0x180004a38  test    eax, eax
0x180004a3a  jz      loc_180004B2F
0x180004a40  mov     ecx, r14d; dwErrCode
0x180004a43  call    cs:__imp_SetLastError
0x180004a49  mov     [rbx], r15
0x180004a4c  lea     r8, asc_18003ACF8; "h"
0x180004a53  shr     rbp, 1Fh
0x180004a57  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004a5c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a61  test    ebp, ebp
0x180004a63  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004a6b  lea     r9, [rsp+278h+Name]; lpName
0x180004a70  mov     [rsp+278h+dwFlags], r12d; int
0x180004a75  cmovnz  esi, ebp
0x180004a78  mov     edx, ebp; lInitialCount
0x180004a7a  mov     r8d, esi; lMaximumCount
0x180004a7d  xor     ecx, ecx; lpSemaphoreAttributes
0x180004a7f  call    cs:__imp_CreateSemaphoreExW
0x180004a85  mov     rsi, rax
0x180004a88  test    rax, rax
0x180004a8b  jnz     short loc_180004AB8
0x180004a8d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004a92  mov     ebx, eax
0x180004a94  test    eax, eax
0x180004a96  jns     short loc_180004AE8
0x180004a98  mov     rcx, [rsp+278h]; this
0x180004aa0  lea     r8, aWil; "wil"
0x180004aa7  mov     r9d, eax; char *
0x180004aaa  mov     edx, 90h; void *
0x180004aaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ab4  mov     eax, ebx
0x180004ab6  jmp     short loc_180004AEA
0x180004ab8  call    cs:__imp_GetLastError
0x180004abe  mov     rdi, [rbx+8]
0x180004ac2  test    rdi, rdi
0x180004ac5  jz      short loc_180004AE4
0x180004ac7  call    cs:__imp_GetLastError
0x180004acd  mov     rcx, rdi; hObject
0x180004ad0  mov     ebp, eax
0x180004ad2  call    cs:__imp_CloseHandle
0x180004ad8  test    eax, eax
0x180004ada  jz      short loc_180004B16
0x180004adc  mov     ecx, ebp; dwErrCode
0x180004ade  call    cs:__imp_SetLastError
0x180004ae4  mov     [rbx+8], rsi
0x180004ae8  xor     eax, eax
0x180004aea  mov     rcx, [rsp+278h+var_38]
0x180004af2  xor     rcx, rsp; StackCookie
0x180004af5  call    __security_check_cookie
0x180004afa  lea     r11, [rsp+278h+var_28]
0x180004b02  mov     rbx, [r11+38h]
0x180004b06  mov     rbp, [r11+40h]
0x180004b0a  mov     rsp, r11
0x180004b0d  pop     r15
0x180004b0f  pop     r14
0x180004b11  pop     r12
0x180004b13  pop     rdi
0x180004b14  pop     rsi
0x180004b15  retn
0x180004b16  mov     rcx, [rsp+278h]; this
0x180004b1e  mov     edx, 0A0Bh; void *
0x180004b23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b29  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004b2f  mov     rcx, [rsp+278h]; this
0x180004b37  mov     edx, 0A0Bh; void *
0x180004b3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
