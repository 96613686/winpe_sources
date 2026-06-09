# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a328`
- end: `0x18000a552`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009f58`
- `0x180011864`

## callees

- `0x1800050a0`
- `0x18000a328`
- `0x18000ac68`
- `0x18000bbd4`
- `0x18000c514`
- `0x18000cba8`
- `0x18000cbb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a3ec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a48f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a3ec`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a442`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4e2`

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
0x18000a328  mov     [rsp+arg_8], rbx
0x18000a32d  mov     [rsp+arg_10], rbp
0x18000a332  push    rsi
0x18000a333  push    rdi
0x18000a334  push    r12
0x18000a336  push    r14
0x18000a338  push    r15
0x18000a33a  sub     rsp, 250h
0x18000a341  mov     rax, cs:__security_cookie
0x18000a348  xor     rax, rsp
0x18000a34b  mov     [rsp+278h+var_38], rax
0x18000a353  mov     rax, 0C000000000000000h
0x18000a35d  mov     rbp, r9
0x18000a360  mov     r8, rdx
0x18000a363  mov     rbx, rcx
0x18000a366  test    rax, r9
0x18000a369  jnz     loc_18000A539
0x18000a36f  xor     r12d, r12d
0x18000a372  lea     rax, [rsp+278h+Name]
0x18000a377  mov     ecx, 7FFFFFFEh
0x18000a37c  mov     edx, 104h
0x18000a381  lea     esi, [r12+1]
0x18000a386  test    rcx, rcx
0x18000a389  jz      short loc_18000A3A9
0x18000a38b  movzx   r9d, word ptr [r8]
0x18000a38f  test    r9w, r9w
0x18000a393  jz      short loc_18000A3A9
0x18000a395  mov     [rax], r9w
0x18000a399  add     r8, 2
0x18000a39d  add     rax, 2
0x18000a3a1  sub     rcx, rsi
0x18000a3a4  sub     rdx, rsi; unsigned __int64
0x18000a3a7  jnz     short loc_18000A386
0x18000a3a9  test    rdx, rdx
0x18000a3ac  lea     rcx, [rax-2]
0x18000a3b0  lea     r8, aP0; "_p0"
0x18000a3b7  cmovnz  rcx, rax
0x18000a3bb  mov     [rcx], r12w
0x18000a3bf  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a3c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3c9  mov     edx, ebp
0x18000a3cb  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a3d3  and     edx, 7FFFFFFFh; lInitialCount
0x18000a3d9  mov     [rsp+278h+dwFlags], r12d; int
0x18000a3de  mov     r8d, esi
0x18000a3e1  lea     r9, [rsp+278h+Name]; lpName
0x18000a3e6  cmova   r8d, edx; lMaximumCount
0x18000a3ea  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a3ec  call    cs:__imp_CreateSemaphoreExW
0x18000a3f2  mov     r15, rax
0x18000a3f5  test    rax, rax
0x18000a3f8  jnz     short loc_18000A428
0x18000a3fa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a3ff  mov     edi, eax
0x18000a401  test    eax, eax
0x18000a403  jns     short loc_18000A45C
0x18000a405  mov     rcx, [rsp+278h]; this
0x18000a40d  lea     r8, aWil; "wil"
0x18000a414  mov     r9d, eax; char *
0x18000a417  mov     edx, 8Bh; void *
0x18000a41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a421  mov     eax, edi
0x18000a423  jmp     loc_18000A4FA
0x18000a428  call    cs:__imp_GetLastError
0x18000a42e  mov     rdi, [rbx]
0x18000a431  test    rdi, rdi
0x18000a434  jz      short loc_18000A459
0x18000a436  call    cs:__imp_GetLastError
0x18000a43c  mov     rcx, rdi; hObject
0x18000a43f  mov     r14d, eax
0x18000a442  call    cs:__imp_CloseHandle
0x18000a448  test    eax, eax
0x18000a44a  jz      loc_18000A53F
0x18000a450  mov     ecx, r14d; dwErrCode
0x18000a453  call    cs:__imp_SetLastError
0x18000a459  mov     [rbx], r15
0x18000a45c  lea     r8, asc_180072ED0; "h"
0x18000a463  shr     rbp, 1Fh
0x18000a467  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a46c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a471  test    ebp, ebp
0x18000a473  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a47b  lea     r9, [rsp+278h+Name]; lpName
0x18000a480  mov     [rsp+278h+dwFlags], r12d; int
0x18000a485  cmovnz  esi, ebp
0x18000a488  mov     edx, ebp; lInitialCount
0x18000a48a  mov     r8d, esi; lMaximumCount
0x18000a48d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a48f  call    cs:__imp_CreateSemaphoreExW
0x18000a495  mov     rsi, rax
0x18000a498  test    rax, rax
0x18000a49b  jnz     short loc_18000A4C8
0x18000a49d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a4a2  mov     ebx, eax
0x18000a4a4  test    eax, eax
0x18000a4a6  jns     short loc_18000A4F8
0x18000a4a8  mov     rcx, [rsp+278h]; this
0x18000a4b0  lea     r8, aWil; "wil"
0x18000a4b7  mov     r9d, eax; char *
0x18000a4ba  mov     edx, 90h; void *
0x18000a4bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4c4  mov     eax, ebx
0x18000a4c6  jmp     short loc_18000A4FA
0x18000a4c8  call    cs:__imp_GetLastError
0x18000a4ce  mov     rdi, [rbx+8]
0x18000a4d2  test    rdi, rdi
0x18000a4d5  jz      short loc_18000A4F4
0x18000a4d7  call    cs:__imp_GetLastError
0x18000a4dd  mov     rcx, rdi; hObject
0x18000a4e0  mov     ebp, eax
0x18000a4e2  call    cs:__imp_CloseHandle
0x18000a4e8  test    eax, eax
0x18000a4ea  jz      short loc_18000A526
0x18000a4ec  mov     ecx, ebp; dwErrCode
0x18000a4ee  call    cs:__imp_SetLastError
0x18000a4f4  mov     [rbx+8], rsi
0x18000a4f8  xor     eax, eax
0x18000a4fa  mov     rcx, [rsp+278h+var_38]
0x18000a502  xor     rcx, rsp; StackCookie
0x18000a505  call    __security_check_cookie
0x18000a50a  lea     r11, [rsp+278h+var_28]
0x18000a512  mov     rbx, [r11+38h]
0x18000a516  mov     rbp, [r11+40h]
0x18000a51a  mov     rsp, r11
0x18000a51d  pop     r15
0x18000a51f  pop     r14
0x18000a521  pop     r12
0x18000a523  pop     rdi
0x18000a524  pop     rsi
0x18000a525  retn
0x18000a526  mov     rcx, [rsp+278h]; this
0x18000a52e  mov     edx, 0A0Bh; void *
0x18000a533  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a539  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a53f  mov     rcx, [rsp+278h]; this
0x18000a547  mov     edx, 0A0Bh; void *
0x18000a54c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
