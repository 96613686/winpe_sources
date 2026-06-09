# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18001c280`
- end: `0x18001c4a3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `547`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001be2c`

## callees

- `0x180001870`
- `0x18001c280`
- `0x18001cfa8`
- `0x18001e744`
- `0x18001f020`
- `0x18001f8ec`
- `0x18001f8fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c349`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c3f0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c349`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c3f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c448`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c43c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c43c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // rax
  LONG v10; // ebp
  WCHAR v11; // r9
  WCHAR *v12; // rcx
  LONG v13; // r8d
  wil::details *v14; // rcx
  HANDLE Semaphore; // r15
  int LastErrorFailHr; // eax
  unsigned int v17; // r8d
  unsigned int v18; // edi
  void *v20; // rdi
  DWORD LastError; // r14d
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rsi
  wil::details *v25; // rcx
  HANDLE v26; // rbp
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // ebx
  void *v30; // rdi
  DWORD v31; // esi
  __int64 v32; // r8
  const char *v33; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = 2147483646;
  v8 = 260;
  v9 = Name;
  v10 = 1;
  do
  {
    if ( !v7 )
      break;
    v11 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v9++ = v11;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v13 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v13 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v13, Name, 0, 0x1F0003u);
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
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
    v18 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        v17,
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v18;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v30 = (void *)*((_QWORD *)this + 1);
    if ( v30 )
    {
      v31 = GetLastError();
      if ( !CloseHandle(v30) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
      SetLastError(v31);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    v27 = wil::details::GetLastErrorFailHr(v25);
    v29 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x90, v28, (const char *)(unsigned int)v27, dwFlagsa);
      return v29;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c280  mov     [rsp+arg_8], rbx
0x18001c285  push    rbp
0x18001c286  push    rsi
0x18001c287  push    rdi
0x18001c288  push    r12
0x18001c28a  push    r13
0x18001c28c  push    r14
0x18001c28e  push    r15
0x18001c290  sub     rsp, 250h
0x18001c297  mov     rax, cs:__security_cookie
0x18001c29e  xor     rax, rsp
0x18001c2a1  mov     [rsp+288h+var_48], rax
0x18001c2a9  mov     rsi, r9
0x18001c2ac  mov     r8, rdx
0x18001c2af  mov     rbx, rcx
0x18001c2b2  mov     rax, 0C000000000000000h
0x18001c2bc  test    rax, r9
0x18001c2bf  jnz     loc_18001C492
0x18001c2c5  mov     ecx, 7FFFFFFEh
0x18001c2ca  mov     r13d, 104h
0x18001c2d0  mov     edx, r13d
0x18001c2d3  lea     rax, [rsp+288h+Name]
0x18001c2d8  xor     r12d, r12d
0x18001c2db  lea     ebp, [r12+1]
0x18001c2e0  test    rcx, rcx
0x18001c2e3  jz      short loc_18001C303
0x18001c2e5  movzx   r9d, word ptr [r8]
0x18001c2e9  test    r9w, r9w
0x18001c2ed  jz      short loc_18001C303
0x18001c2ef  add     r8, 2
0x18001c2f3  mov     [rax], r9w
0x18001c2f7  add     rax, 2
0x18001c2fb  sub     rcx, rbp
0x18001c2fe  sub     rdx, rbp
0x18001c301  jnz     short loc_18001C2E0
0x18001c303  lea     rcx, [rax-2]
0x18001c307  test    rdx, rdx
0x18001c30a  cmovnz  rcx, rax
0x18001c30e  mov     [rcx], r12w
0x18001c312  lea     r8, aP0; "_p0"
0x18001c319  mov     rdx, r13; unsigned __int64
0x18001c31c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001c321  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c326  mov     edx, esi
0x18001c328  and     edx, 7FFFFFFFh; lInitialCount
0x18001c32e  mov     r8d, ebp
0x18001c331  cmova   r8d, edx; lMaximumCount
0x18001c335  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001c33d  mov     [rsp+288h+dwFlags], r12d; int
0x18001c342  lea     r9, [rsp+288h+Name]; lpName
0x18001c347  xor     ecx, ecx; lpSemaphoreAttributes
0x18001c349  call    cs:__imp_CreateSemaphoreExW
0x18001c34f  mov     r15, rax
0x18001c352  test    rax, rax
0x18001c355  jnz     short loc_18001C37E
0x18001c357  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c35c  mov     edi, eax
0x18001c35e  test    eax, eax
0x18001c360  jns     short loc_18001C3BA
0x18001c362  mov     rcx, [rsp+288h]; this
0x18001c36a  mov     r9d, eax; char *
0x18001c36d  mov     edx, 8Bh; void *
0x18001c372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c377  mov     eax, edi
0x18001c379  jmp     loc_18001C454
0x18001c37e  call    cs:__imp_GetLastError
0x18001c384  mov     rdi, [rbx]
0x18001c387  test    rdi, rdi
0x18001c38a  jz      short loc_18001C3B7
0x18001c38c  call    cs:__imp_GetLastError
0x18001c392  mov     r14d, eax
0x18001c395  mov     rcx, rdi; hObject
0x18001c398  call    cs:__imp_CloseHandle
0x18001c39e  mov     rcx, [rsp+288h]; this
0x18001c3a6  test    eax, eax
0x18001c3a8  jz      loc_18001C498
0x18001c3ae  mov     ecx, r14d; dwErrCode
0x18001c3b1  call    cs:__imp_SetLastError
0x18001c3b7  mov     [rbx], r15
0x18001c3ba  shr     rsi, 1Fh
0x18001c3be  lea     r8, asc_18002E858; "h"
0x18001c3c5  mov     rdx, r13; unsigned __int64
0x18001c3c8  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18001c3cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c3d2  test    esi, esi
0x18001c3d4  cmovnz  ebp, esi
0x18001c3d7  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001c3df  mov     [rsp+288h+dwFlags], r12d; int
0x18001c3e4  lea     r9, [rsp+288h+Name]; lpName
0x18001c3e9  mov     r8d, ebp; lMaximumCount
0x18001c3ec  mov     edx, esi; lInitialCount
0x18001c3ee  xor     ecx, ecx; lpSemaphoreAttributes
0x18001c3f0  call    cs:__imp_CreateSemaphoreExW
0x18001c3f6  mov     rbp, rax
0x18001c3f9  test    rax, rax
0x18001c3fc  jnz     short loc_18001C422
0x18001c3fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c403  mov     ebx, eax
0x18001c405  test    eax, eax
0x18001c407  jns     short loc_18001C452
0x18001c409  mov     rcx, [rsp+288h]; this
0x18001c411  mov     r9d, eax; char *
0x18001c414  mov     edx, 90h; void *
0x18001c419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c41e  mov     eax, ebx
0x18001c420  jmp     short loc_18001C454
0x18001c422  call    cs:__imp_GetLastError
0x18001c428  mov     rdi, [rbx+8]
0x18001c42c  test    rdi, rdi
0x18001c42f  jz      short loc_18001C44E
0x18001c431  call    cs:__imp_GetLastError
0x18001c437  mov     esi, eax
0x18001c439  mov     rcx, rdi; hObject
0x18001c43c  call    cs:__imp_CloseHandle
0x18001c442  test    eax, eax
0x18001c444  jz      short loc_18001C47F
0x18001c446  mov     ecx, esi; dwErrCode
0x18001c448  call    cs:__imp_SetLastError
0x18001c44e  mov     [rbx+8], rbp
0x18001c452  xor     eax, eax
0x18001c454  mov     rcx, [rsp+288h+var_48]
0x18001c45c  xor     rcx, rsp; StackCookie
0x18001c45f  call    __security_check_cookie
0x18001c464  mov     rbx, [rsp+288h+arg_8]
0x18001c46c  add     rsp, 250h
0x18001c473  pop     r15
0x18001c475  pop     r14
0x18001c477  pop     r13
0x18001c479  pop     r12
0x18001c47b  pop     rdi
0x18001c47c  pop     rsi
0x18001c47d  pop     rbp
0x18001c47e  retn
0x18001c47f  mov     rcx, [rsp+288h]; this
0x18001c487  mov     edx, 0A0Bh; void *
0x18001c48c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c492  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001c498  mov     edx, 0A0Bh; void *
0x18001c49d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
