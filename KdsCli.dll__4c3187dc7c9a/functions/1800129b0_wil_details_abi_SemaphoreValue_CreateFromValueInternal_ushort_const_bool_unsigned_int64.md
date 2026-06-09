# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800129b0`
- end: `0x180012bbd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001223c`
- `0x1800125e0`

## callees

- `0x180001630`
- `0x1800129b0`
- `0x180013738`
- `0x180015630`
- `0x180015a4c`
- `0x1800165b8`
- `0x1800165c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b4d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012a74`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012b10`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012a74`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012b10`

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
0x1800129b0  mov     [rsp+arg_8], rbx
0x1800129b5  mov     [rsp+arg_10], rbp
0x1800129ba  push    rsi
0x1800129bb  push    rdi
0x1800129bc  push    r12
0x1800129be  push    r14
0x1800129c0  push    r15
0x1800129c2  sub     rsp, 250h
0x1800129c9  mov     rax, cs:__security_cookie
0x1800129d0  xor     rax, rsp
0x1800129d3  mov     [rsp+278h+var_38], rax
0x1800129db  mov     rax, 0C000000000000000h
0x1800129e5  mov     rbp, r9
0x1800129e8  mov     r8, rdx
0x1800129eb  mov     rdi, rcx
0x1800129ee  test    rax, r9
0x1800129f1  jnz     loc_180012BA4
0x1800129f7  xor     r12d, r12d
0x1800129fa  lea     rax, [rsp+278h+Name]
0x1800129ff  mov     ecx, 7FFFFFFEh
0x180012a04  mov     edx, 104h
0x180012a09  lea     esi, [r12+1]
0x180012a0e  test    rcx, rcx
0x180012a11  jz      short loc_180012A31
0x180012a13  movzx   r9d, word ptr [r8]
0x180012a17  test    r9w, r9w
0x180012a1b  jz      short loc_180012A31
0x180012a1d  mov     [rax], r9w
0x180012a21  add     r8, 2
0x180012a25  add     rax, 2
0x180012a29  sub     rcx, rsi
0x180012a2c  sub     rdx, rsi; unsigned __int64
0x180012a2f  jnz     short loc_180012A0E
0x180012a31  test    rdx, rdx
0x180012a34  lea     rcx, [rax-2]
0x180012a38  lea     r8, aP0; "_p0"
0x180012a3f  cmovnz  rcx, rax
0x180012a43  mov     [rcx], r12w
0x180012a47  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180012a4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012a51  mov     edx, ebp
0x180012a53  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180012a5b  and     edx, 7FFFFFFFh; lInitialCount
0x180012a61  mov     [rsp+278h+dwFlags], r12d; int
0x180012a66  mov     r8d, esi
0x180012a69  lea     r9, [rsp+278h+Name]; lpName
0x180012a6e  cmova   r8d, edx; lMaximumCount
0x180012a72  xor     ecx, ecx; lpSemaphoreAttributes
0x180012a74  call    cs:__imp_CreateSemaphoreExW
0x180012a7a  mov     r15, rax
0x180012a7d  test    rax, rax
0x180012a80  jnz     short loc_180012AA9
0x180012a82  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012a87  mov     ebx, eax
0x180012a89  test    eax, eax
0x180012a8b  jns     short loc_180012ADD
0x180012a8d  mov     edx, 8Bh; void *
0x180012a92  mov     rcx, [rsp+278h]; this
0x180012a9a  mov     r9d, ebx; char *
0x180012a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012aa2  mov     eax, ebx
0x180012aa4  jmp     loc_180012B65
0x180012aa9  call    cs:__imp_GetLastError
0x180012aaf  mov     rbx, [rdi]
0x180012ab2  test    rbx, rbx
0x180012ab5  jz      short loc_180012ADA
0x180012ab7  call    cs:__imp_GetLastError
0x180012abd  mov     rcx, rbx; hObject
0x180012ac0  mov     r14d, eax
0x180012ac3  call    cs:__imp_CloseHandle
0x180012ac9  test    eax, eax
0x180012acb  jz      loc_180012BAA
0x180012ad1  mov     ecx, r14d; dwErrCode
0x180012ad4  call    cs:__imp_SetLastError
0x180012ada  mov     [rdi], r15
0x180012add  lea     r8, asc_18001E380; "h"
0x180012ae4  shr     rbp, 1Fh
0x180012ae8  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180012aed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012af2  test    ebp, ebp
0x180012af4  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180012afc  lea     r9, [rsp+278h+Name]; lpName
0x180012b01  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180012b06  cmovnz  esi, ebp
0x180012b09  mov     edx, ebp; lInitialCount
0x180012b0b  mov     r8d, esi; lMaximumCount
0x180012b0e  xor     ecx, ecx; lpSemaphoreAttributes
0x180012b10  call    cs:__imp_CreateSemaphoreExW
0x180012b16  mov     rsi, rax
0x180012b19  test    rax, rax
0x180012b1c  jnz     short loc_180012B33
0x180012b1e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012b23  mov     ebx, eax
0x180012b25  test    eax, eax
0x180012b27  jns     short loc_180012B63
0x180012b29  mov     edx, 90h
0x180012b2e  jmp     loc_180012A92
0x180012b33  call    cs:__imp_GetLastError
0x180012b39  mov     rbx, [rdi+8]
0x180012b3d  test    rbx, rbx
0x180012b40  jz      short loc_180012B5F
0x180012b42  call    cs:__imp_GetLastError
0x180012b48  mov     rcx, rbx; hObject
0x180012b4b  mov     ebp, eax
0x180012b4d  call    cs:__imp_CloseHandle
0x180012b53  test    eax, eax
0x180012b55  jz      short loc_180012B91
0x180012b57  mov     ecx, ebp; dwErrCode
0x180012b59  call    cs:__imp_SetLastError
0x180012b5f  mov     [rdi+8], rsi
0x180012b63  xor     eax, eax
0x180012b65  mov     rcx, [rsp+278h+var_38]
0x180012b6d  xor     rcx, rsp; StackCookie
0x180012b70  call    __security_check_cookie
0x180012b75  lea     r11, [rsp+278h+var_28]
0x180012b7d  mov     rbx, [r11+38h]
0x180012b81  mov     rbp, [r11+40h]
0x180012b85  mov     rsp, r11
0x180012b88  pop     r15
0x180012b8a  pop     r14
0x180012b8c  pop     r12
0x180012b8e  pop     rdi
0x180012b8f  pop     rsi
0x180012b90  retn
0x180012b91  mov     rcx, [rsp+278h]; this
0x180012b99  mov     edx, 0A0Bh; void *
0x180012b9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012ba4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012baa  mov     rcx, [rsp+278h]; this
0x180012bb2  mov     edx, 0A0Bh; void *
0x180012bb7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
