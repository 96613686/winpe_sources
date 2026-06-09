# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004ae4`
- end: `0x180004d0e`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800046d8`

## callees

- `0x180001620`
- `0x180004ae4`
- `0x180005638`
- `0x180006804`
- `0x180007200`
- `0x180007d0c`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ba8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004c4b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004ba8`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004c4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004caa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c9e`

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
0x180004ae4  mov     [rsp+arg_8], rbx
0x180004ae9  mov     [rsp+arg_10], rbp
0x180004aee  push    rsi
0x180004aef  push    rdi
0x180004af0  push    r12
0x180004af2  push    r14
0x180004af4  push    r15
0x180004af6  sub     rsp, 250h
0x180004afd  mov     rax, cs:__security_cookie
0x180004b04  xor     rax, rsp
0x180004b07  mov     [rsp+278h+var_38], rax
0x180004b0f  mov     rax, 0C000000000000000h
0x180004b19  mov     rbp, r9
0x180004b1c  mov     r8, rdx
0x180004b1f  mov     rbx, rcx
0x180004b22  test    rax, r9
0x180004b25  jnz     loc_180004CF5
0x180004b2b  xor     r12d, r12d
0x180004b2e  lea     rax, [rsp+278h+Name]
0x180004b33  mov     ecx, 7FFFFFFEh
0x180004b38  mov     edx, 104h
0x180004b3d  lea     esi, [r12+1]
0x180004b42  test    rcx, rcx
0x180004b45  jz      short loc_180004B65
0x180004b47  movzx   r9d, word ptr [r8]
0x180004b4b  test    r9w, r9w
0x180004b4f  jz      short loc_180004B65
0x180004b51  mov     [rax], r9w
0x180004b55  add     r8, 2
0x180004b59  add     rax, 2
0x180004b5d  sub     rcx, rsi
0x180004b60  sub     rdx, rsi; unsigned __int64
0x180004b63  jnz     short loc_180004B42
0x180004b65  test    rdx, rdx
0x180004b68  lea     rcx, [rax-2]
0x180004b6c  lea     r8, aP0; "_p0"
0x180004b73  cmovnz  rcx, rax
0x180004b77  mov     [rcx], r12w
0x180004b7b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004b80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004b85  mov     edx, ebp
0x180004b87  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004b8f  and     edx, 7FFFFFFFh; lInitialCount
0x180004b95  mov     [rsp+278h+dwFlags], r12d; int
0x180004b9a  mov     r8d, esi
0x180004b9d  lea     r9, [rsp+278h+Name]; lpName
0x180004ba2  cmova   r8d, edx; lMaximumCount
0x180004ba6  xor     ecx, ecx; lpSemaphoreAttributes
0x180004ba8  call    cs:__imp_CreateSemaphoreExW
0x180004bae  mov     r15, rax
0x180004bb1  test    rax, rax
0x180004bb4  jnz     short loc_180004BE4
0x180004bb6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004bbb  mov     edi, eax
0x180004bbd  test    eax, eax
0x180004bbf  jns     short loc_180004C18
0x180004bc1  mov     rcx, [rsp+278h]; this
0x180004bc9  lea     r8, aWil; "wil"
0x180004bd0  mov     r9d, eax; char *
0x180004bd3  mov     edx, 8Bh; void *
0x180004bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bdd  mov     eax, edi
0x180004bdf  jmp     loc_180004CB6
0x180004be4  call    cs:__imp_GetLastError
0x180004bea  mov     rdi, [rbx]
0x180004bed  test    rdi, rdi
0x180004bf0  jz      short loc_180004C15
0x180004bf2  call    cs:__imp_GetLastError
0x180004bf8  mov     rcx, rdi; hObject
0x180004bfb  mov     r14d, eax
0x180004bfe  call    cs:__imp_CloseHandle
0x180004c04  test    eax, eax
0x180004c06  jz      loc_180004CFB
0x180004c0c  mov     ecx, r14d; dwErrCode
0x180004c0f  call    cs:__imp_SetLastError
0x180004c15  mov     [rbx], r15
0x180004c18  lea     r8, asc_180010110; "h"
0x180004c1f  shr     rbp, 1Fh
0x180004c23  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004c28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004c2d  test    ebp, ebp
0x180004c2f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004c37  lea     r9, [rsp+278h+Name]; lpName
0x180004c3c  mov     [rsp+278h+dwFlags], r12d; int
0x180004c41  cmovnz  esi, ebp
0x180004c44  mov     edx, ebp; lInitialCount
0x180004c46  mov     r8d, esi; lMaximumCount
0x180004c49  xor     ecx, ecx; lpSemaphoreAttributes
0x180004c4b  call    cs:__imp_CreateSemaphoreExW
0x180004c51  mov     rsi, rax
0x180004c54  test    rax, rax
0x180004c57  jnz     short loc_180004C84
0x180004c59  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c5e  mov     ebx, eax
0x180004c60  test    eax, eax
0x180004c62  jns     short loc_180004CB4
0x180004c64  mov     rcx, [rsp+278h]; this
0x180004c6c  lea     r8, aWil; "wil"
0x180004c73  mov     r9d, eax; char *
0x180004c76  mov     edx, 90h; void *
0x180004c7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c80  mov     eax, ebx
0x180004c82  jmp     short loc_180004CB6
0x180004c84  call    cs:__imp_GetLastError
0x180004c8a  mov     rdi, [rbx+8]
0x180004c8e  test    rdi, rdi
0x180004c91  jz      short loc_180004CB0
0x180004c93  call    cs:__imp_GetLastError
0x180004c99  mov     rcx, rdi; hObject
0x180004c9c  mov     ebp, eax
0x180004c9e  call    cs:__imp_CloseHandle
0x180004ca4  test    eax, eax
0x180004ca6  jz      short loc_180004CE2
0x180004ca8  mov     ecx, ebp; dwErrCode
0x180004caa  call    cs:__imp_SetLastError
0x180004cb0  mov     [rbx+8], rsi
0x180004cb4  xor     eax, eax
0x180004cb6  mov     rcx, [rsp+278h+var_38]
0x180004cbe  xor     rcx, rsp; StackCookie
0x180004cc1  call    __security_check_cookie
0x180004cc6  lea     r11, [rsp+278h+var_28]
0x180004cce  mov     rbx, [r11+38h]
0x180004cd2  mov     rbp, [r11+40h]
0x180004cd6  mov     rsp, r11
0x180004cd9  pop     r15
0x180004cdb  pop     r14
0x180004cdd  pop     r12
0x180004cdf  pop     rdi
0x180004ce0  pop     rsi
0x180004ce1  retn
0x180004ce2  mov     rcx, [rsp+278h]; this
0x180004cea  mov     edx, 0A0Bh; void *
0x180004cef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004cf5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004cfb  mov     rcx, [rsp+278h]; this
0x180004d03  mov     edx, 0A0Bh; void *
0x180004d08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
