# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800081a0`
- end: `0x1800083ca`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007238`

## callees

- `0x180005020`
- `0x1800081a0`
- `0x180008f4c`
- `0x18000b394`
- `0x18000bd24`
- `0x18000c674`
- `0x18000c684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008307`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008264`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008366`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000834f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000834f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000835a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000835a`

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
0x1800081a0  mov     [rsp+arg_8], rbx
0x1800081a5  mov     [rsp+arg_10], rbp
0x1800081aa  push    rsi
0x1800081ab  push    rdi
0x1800081ac  push    r12
0x1800081ae  push    r14
0x1800081b0  push    r15
0x1800081b2  sub     rsp, 250h
0x1800081b9  mov     rax, cs:__security_cookie
0x1800081c0  xor     rax, rsp
0x1800081c3  mov     [rsp+278h+var_38], rax
0x1800081cb  mov     rax, 0C000000000000000h
0x1800081d5  mov     rbp, r9
0x1800081d8  mov     r8, rdx
0x1800081db  mov     rbx, rcx
0x1800081de  test    rax, r9
0x1800081e1  jnz     loc_1800083B1
0x1800081e7  xor     r12d, r12d
0x1800081ea  lea     rax, [rsp+278h+Name]
0x1800081ef  mov     ecx, 7FFFFFFEh
0x1800081f4  mov     edx, 104h
0x1800081f9  lea     esi, [r12+1]
0x1800081fe  test    rcx, rcx
0x180008201  jz      short loc_180008221
0x180008203  movzx   r9d, word ptr [r8]
0x180008207  test    r9w, r9w
0x18000820b  jz      short loc_180008221
0x18000820d  mov     [rax], r9w
0x180008211  add     r8, 2
0x180008215  add     rax, 2
0x180008219  sub     rcx, rsi
0x18000821c  sub     rdx, rsi; unsigned __int64
0x18000821f  jnz     short loc_1800081FE
0x180008221  test    rdx, rdx
0x180008224  lea     rcx, [rax-2]
0x180008228  lea     r8, aP0; "_p0"
0x18000822f  cmovnz  rcx, rax
0x180008233  mov     [rcx], r12w
0x180008237  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000823c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008241  mov     edx, ebp
0x180008243  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000824b  and     edx, 7FFFFFFFh; lInitialCount
0x180008251  mov     [rsp+278h+dwFlags], r12d; int
0x180008256  mov     r8d, esi
0x180008259  lea     r9, [rsp+278h+Name]; lpName
0x18000825e  cmova   r8d, edx; lMaximumCount
0x180008262  xor     ecx, ecx; lpSemaphoreAttributes
0x180008264  call    cs:__imp_CreateSemaphoreExW
0x18000826a  mov     r15, rax
0x18000826d  test    rax, rax
0x180008270  jnz     short loc_1800082A0
0x180008272  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008277  mov     edi, eax
0x180008279  test    eax, eax
0x18000827b  jns     short loc_1800082D4
0x18000827d  mov     rcx, [rsp+278h]; this
0x180008285  lea     r8, aWil; "wil"
0x18000828c  mov     r9d, eax; char *
0x18000828f  mov     edx, 8Bh; void *
0x180008294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008299  mov     eax, edi
0x18000829b  jmp     loc_180008372
0x1800082a0  call    cs:__imp_GetLastError
0x1800082a6  mov     rdi, [rbx]
0x1800082a9  test    rdi, rdi
0x1800082ac  jz      short loc_1800082D1
0x1800082ae  call    cs:__imp_GetLastError
0x1800082b4  mov     rcx, rdi; hObject
0x1800082b7  mov     r14d, eax
0x1800082ba  call    cs:__imp_CloseHandle
0x1800082c0  test    eax, eax
0x1800082c2  jz      loc_1800083B7
0x1800082c8  mov     ecx, r14d; dwErrCode
0x1800082cb  call    cs:__imp_SetLastError
0x1800082d1  mov     [rbx], r15
0x1800082d4  lea     r8, asc_18007E610; "h"
0x1800082db  shr     rbp, 1Fh
0x1800082df  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800082e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082e9  test    ebp, ebp
0x1800082eb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800082f3  lea     r9, [rsp+278h+Name]; lpName
0x1800082f8  mov     [rsp+278h+dwFlags], r12d; int
0x1800082fd  cmovnz  esi, ebp
0x180008300  mov     edx, ebp; lInitialCount
0x180008302  mov     r8d, esi; lMaximumCount
0x180008305  xor     ecx, ecx; lpSemaphoreAttributes
0x180008307  call    cs:__imp_CreateSemaphoreExW
0x18000830d  mov     rsi, rax
0x180008310  test    rax, rax
0x180008313  jnz     short loc_180008340
0x180008315  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000831a  mov     ebx, eax
0x18000831c  test    eax, eax
0x18000831e  jns     short loc_180008370
0x180008320  mov     rcx, [rsp+278h]; this
0x180008328  lea     r8, aWil; "wil"
0x18000832f  mov     r9d, eax; char *
0x180008332  mov     edx, 90h; void *
0x180008337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000833c  mov     eax, ebx
0x18000833e  jmp     short loc_180008372
0x180008340  call    cs:__imp_GetLastError
0x180008346  mov     rdi, [rbx+8]
0x18000834a  test    rdi, rdi
0x18000834d  jz      short loc_18000836C
0x18000834f  call    cs:__imp_GetLastError
0x180008355  mov     rcx, rdi; hObject
0x180008358  mov     ebp, eax
0x18000835a  call    cs:__imp_CloseHandle
0x180008360  test    eax, eax
0x180008362  jz      short loc_18000839E
0x180008364  mov     ecx, ebp; dwErrCode
0x180008366  call    cs:__imp_SetLastError
0x18000836c  mov     [rbx+8], rsi
0x180008370  xor     eax, eax
0x180008372  mov     rcx, [rsp+278h+var_38]
0x18000837a  xor     rcx, rsp; StackCookie
0x18000837d  call    __security_check_cookie
0x180008382  lea     r11, [rsp+278h+var_28]
0x18000838a  mov     rbx, [r11+38h]
0x18000838e  mov     rbp, [r11+40h]
0x180008392  mov     rsp, r11
0x180008395  pop     r15
0x180008397  pop     r14
0x180008399  pop     r12
0x18000839b  pop     rdi
0x18000839c  pop     rsi
0x18000839d  retn
0x18000839e  mov     rcx, [rsp+278h]; this
0x1800083a6  mov     edx, 0A0Bh; void *
0x1800083ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800083b1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800083b7  mov     rcx, [rsp+278h]; this
0x1800083bf  mov     edx, 0A0Bh; void *
0x1800083c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
