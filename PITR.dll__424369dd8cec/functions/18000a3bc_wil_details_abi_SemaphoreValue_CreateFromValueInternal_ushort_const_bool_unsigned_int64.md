# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a3bc`
- end: `0x18000a5df`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007610`
- `0x1800079b4`

## callees

- `0x18000a3bc`
- `0x18000ea90`
- `0x18001b214`
- `0x18001c484`
- `0x18001dd64`
- `0x18001dd74`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a485`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a524`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a485`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a57c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a4e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a565`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a570`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // ebp
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v16; // r8d
  unsigned int v17; // edi
  void *v19; // rdi
  DWORD LastError; // r14d
  __int64 v21; // r8
  const char *v22; // r9
  unsigned __int64 v23; // rsi
  wil::details *v24; // rcx
  HANDLE v25; // rbp
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // ebx
  void *v29; // rdi
  DWORD v30; // esi
  __int64 v31; // r8
  const char *v32; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
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
        v16,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v17;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  v25 = CreateSemaphoreExW(0, v23, v10, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    v29 = (void *)*((_QWORD *)this + 1);
    if ( v29 )
    {
      v30 = GetLastError();
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      SetLastError(v30);
    }
    *((_QWORD *)this + 1) = v25;
  }
  else
  {
    v26 = wil::details::GetLastErrorFailHr(v24);
    v28 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v27, (const char *)(unsigned int)v26, dwFlagsa);
      return v28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a3bc  mov     [rsp+arg_8], rbx
0x18000a3c1  push    rbp
0x18000a3c2  push    rsi
0x18000a3c3  push    rdi
0x18000a3c4  push    r12
0x18000a3c6  push    r13
0x18000a3c8  push    r14
0x18000a3ca  push    r15
0x18000a3cc  sub     rsp, 250h
0x18000a3d3  mov     rax, cs:__security_cookie
0x18000a3da  xor     rax, rsp
0x18000a3dd  mov     [rsp+288h+var_48], rax
0x18000a3e5  mov     rax, 0C000000000000000h
0x18000a3ef  mov     rsi, r9
0x18000a3f2  mov     r8, rdx
0x18000a3f5  mov     rbx, rcx
0x18000a3f8  test    rax, r9
0x18000a3fb  jnz     loc_18000A5C6
0x18000a401  xor     r12d, r12d
0x18000a404  lea     rax, [rsp+288h+Name]
0x18000a409  mov     r13d, 104h
0x18000a40f  mov     ecx, 7FFFFFFEh
0x18000a414  mov     edx, r13d
0x18000a417  lea     ebp, [r12+1]
0x18000a41c  test    rcx, rcx
0x18000a41f  jz      short loc_18000A43F
0x18000a421  movzx   r9d, word ptr [r8]
0x18000a425  test    r9w, r9w
0x18000a429  jz      short loc_18000A43F
0x18000a42b  mov     [rax], r9w
0x18000a42f  add     r8, 2
0x18000a433  add     rax, 2
0x18000a437  sub     rcx, rbp
0x18000a43a  sub     rdx, rbp
0x18000a43d  jnz     short loc_18000A41C
0x18000a43f  test    rdx, rdx
0x18000a442  lea     rcx, [rax-2]
0x18000a446  lea     r8, aP0; "_p0"
0x18000a44d  mov     rdx, r13; unsigned __int64
0x18000a450  cmovnz  rcx, rax
0x18000a454  mov     [rcx], r12w
0x18000a458  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a45d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a462  mov     edx, esi
0x18000a464  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a46c  and     edx, 7FFFFFFFh; lInitialCount
0x18000a472  mov     [rsp+288h+dwFlags], r12d; int
0x18000a477  mov     r8d, ebp
0x18000a47a  lea     r9, [rsp+288h+Name]; lpName
0x18000a47f  cmova   r8d, edx; lMaximumCount
0x18000a483  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a485  call    cs:__imp_CreateSemaphoreExW
0x18000a48b  mov     r15, rax
0x18000a48e  test    rax, rax
0x18000a491  jnz     short loc_18000A4BA
0x18000a493  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a498  mov     edi, eax
0x18000a49a  test    eax, eax
0x18000a49c  jns     short loc_18000A4EE
0x18000a49e  mov     rcx, [rsp+288h]; this
0x18000a4a6  mov     r9d, eax; char *
0x18000a4a9  mov     edx, 8Bh; void *
0x18000a4ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4b3  mov     eax, edi
0x18000a4b5  jmp     loc_18000A588
0x18000a4ba  call    cs:__imp_GetLastError
0x18000a4c0  mov     rdi, [rbx]
0x18000a4c3  test    rdi, rdi
0x18000a4c6  jz      short loc_18000A4EB
0x18000a4c8  call    cs:__imp_GetLastError
0x18000a4ce  mov     rcx, rdi; hObject
0x18000a4d1  mov     r14d, eax
0x18000a4d4  call    cs:__imp_CloseHandle
0x18000a4da  test    eax, eax
0x18000a4dc  jz      loc_18000A5CC
0x18000a4e2  mov     ecx, r14d; dwErrCode
0x18000a4e5  call    cs:__imp_SetLastError
0x18000a4eb  mov     [rbx], r15
0x18000a4ee  lea     r8, asc_1800596E8; "h"
0x18000a4f5  shr     rsi, 1Fh
0x18000a4f9  mov     rdx, r13; unsigned __int64
0x18000a4fc  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a501  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a506  test    esi, esi
0x18000a508  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a510  lea     r9, [rsp+288h+Name]; lpName
0x18000a515  mov     [rsp+288h+dwFlags], r12d; int
0x18000a51a  cmovnz  ebp, esi
0x18000a51d  mov     edx, esi; lInitialCount
0x18000a51f  mov     r8d, ebp; lMaximumCount
0x18000a522  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a524  call    cs:__imp_CreateSemaphoreExW
0x18000a52a  mov     rbp, rax
0x18000a52d  test    rax, rax
0x18000a530  jnz     short loc_18000A556
0x18000a532  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a537  mov     ebx, eax
0x18000a539  test    eax, eax
0x18000a53b  jns     short loc_18000A586
0x18000a53d  mov     rcx, [rsp+288h]; this
0x18000a545  mov     r9d, eax; char *
0x18000a548  mov     edx, 90h; void *
0x18000a54d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a552  mov     eax, ebx
0x18000a554  jmp     short loc_18000A588
0x18000a556  call    cs:__imp_GetLastError
0x18000a55c  mov     rdi, [rbx+8]
0x18000a560  test    rdi, rdi
0x18000a563  jz      short loc_18000A582
0x18000a565  call    cs:__imp_GetLastError
0x18000a56b  mov     rcx, rdi; hObject
0x18000a56e  mov     esi, eax
0x18000a570  call    cs:__imp_CloseHandle
0x18000a576  test    eax, eax
0x18000a578  jz      short loc_18000A5B3
0x18000a57a  mov     ecx, esi; dwErrCode
0x18000a57c  call    cs:__imp_SetLastError
0x18000a582  mov     [rbx+8], rbp
0x18000a586  xor     eax, eax
0x18000a588  mov     rcx, [rsp+288h+var_48]
0x18000a590  xor     rcx, rsp; StackCookie
0x18000a593  call    __security_check_cookie
0x18000a598  mov     rbx, [rsp+288h+arg_8]
0x18000a5a0  add     rsp, 250h
0x18000a5a7  pop     r15
0x18000a5a9  pop     r14
0x18000a5ab  pop     r13
0x18000a5ad  pop     r12
0x18000a5af  pop     rdi
0x18000a5b0  pop     rsi
0x18000a5b1  pop     rbp
0x18000a5b2  retn
0x18000a5b3  mov     rcx, [rsp+288h]; this
0x18000a5bb  mov     edx, 0A0Bh; void *
0x18000a5c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a5c6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a5cc  mov     rcx, [rsp+288h]; this
0x18000a5d4  mov     edx, 0A0Bh; void *
0x18000a5d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
