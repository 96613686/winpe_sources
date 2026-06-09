# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000a7b0`
- end: `0x18000a9e1`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a3b8`
- `0x1800298b4`

## callees

- `0x18000a7b0`
- `0x18000b320`
- `0x18000cfe8`
- `0x18000d11c`
- `0x18000e238`
- `0x18000e248`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a967`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a8e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a97e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a8e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a97e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a972`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a879`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a91f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a879`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000a91f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  unsigned int v16; // edi
  void *v18; // rdi
  DWORD LastError; // r14d
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int64 v22; // rsi
  wil::details *v23; // rcx
  HANDLE v24; // rbp
  int v25; // eax
  unsigned int v26; // ebx
  void *v27; // rdi
  DWORD v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
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
    v18 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v16;
    }
  }
  v22 = a4 >> 31;
  StringCchCatW(Name, 0x104u, L"h");
  if ( (_DWORD)v22 )
    v10 = v22;
  v24 = CreateSemaphoreExW(0, v22, v10, Name, 0, 0x1F0003u);
  if ( v24 )
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
    *((_QWORD *)this + 1) = v24;
  }
  else
  {
    v25 = wil::details::GetLastErrorFailHr(v23);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      return v26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a7b0  mov     [rsp+arg_8], rbx
0x18000a7b5  push    rbp
0x18000a7b6  push    rsi
0x18000a7b7  push    rdi
0x18000a7b8  push    r12
0x18000a7ba  push    r13
0x18000a7bc  push    r14
0x18000a7be  push    r15
0x18000a7c0  sub     rsp, 250h
0x18000a7c7  mov     rax, cs:__security_cookie
0x18000a7ce  xor     rax, rsp
0x18000a7d1  mov     [rsp+288h+var_48], rax
0x18000a7d9  mov     rax, 0C000000000000000h
0x18000a7e3  mov     rsi, r9
0x18000a7e6  mov     r8, rdx
0x18000a7e9  mov     rbx, rcx
0x18000a7ec  test    rax, r9
0x18000a7ef  jnz     loc_18000A9C8
0x18000a7f5  xor     r12d, r12d
0x18000a7f8  lea     rax, [rsp+288h+Name]
0x18000a7fd  mov     r13d, 104h
0x18000a803  mov     ecx, 7FFFFFFEh
0x18000a808  mov     edx, r13d
0x18000a80b  lea     ebp, [r12+1]
0x18000a810  test    rcx, rcx
0x18000a813  jz      short loc_18000A833
0x18000a815  movzx   r9d, word ptr [r8]
0x18000a819  test    r9w, r9w
0x18000a81d  jz      short loc_18000A833
0x18000a81f  mov     [rax], r9w
0x18000a823  add     r8, 2
0x18000a827  add     rax, 2
0x18000a82b  sub     rcx, rbp
0x18000a82e  sub     rdx, rbp
0x18000a831  jnz     short loc_18000A810
0x18000a833  test    rdx, rdx
0x18000a836  lea     rcx, [rax-2]
0x18000a83a  lea     r8, aP0; "_p0"
0x18000a841  mov     rdx, r13; unsigned __int64
0x18000a844  cmovnz  rcx, rax
0x18000a848  mov     [rcx], r12w
0x18000a84c  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a851  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a856  mov     edx, esi
0x18000a858  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a860  and     edx, 7FFFFFFFh; lInitialCount
0x18000a866  mov     [rsp+288h+dwFlags], r12d; int
0x18000a86b  mov     r8d, ebp
0x18000a86e  lea     r9, [rsp+288h+Name]; lpName
0x18000a873  cmova   r8d, edx; lMaximumCount
0x18000a877  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a879  call    cs:__imp_CreateSemaphoreExW
0x18000a87f  mov     r15, rax
0x18000a882  test    rax, rax
0x18000a885  jnz     short loc_18000A8B5
0x18000a887  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a88c  mov     edi, eax
0x18000a88e  test    eax, eax
0x18000a890  jns     short loc_18000A8E9
0x18000a892  mov     rcx, [rsp+288h]; this
0x18000a89a  lea     r8, aWil; "wil"
0x18000a8a1  mov     r9d, eax; char *
0x18000a8a4  mov     edx, 8Bh; void *
0x18000a8a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8ae  mov     eax, edi
0x18000a8b0  jmp     loc_18000A98A
0x18000a8b5  call    cs:__imp_GetLastError
0x18000a8bb  mov     rdi, [rbx]
0x18000a8be  test    rdi, rdi
0x18000a8c1  jz      short loc_18000A8E6
0x18000a8c3  call    cs:__imp_GetLastError
0x18000a8c9  mov     rcx, rdi; hObject
0x18000a8cc  mov     r14d, eax
0x18000a8cf  call    cs:__imp_CloseHandle
0x18000a8d5  test    eax, eax
0x18000a8d7  jz      loc_18000A9CE
0x18000a8dd  mov     ecx, r14d; dwErrCode
0x18000a8e0  call    cs:__imp_SetLastError
0x18000a8e6  mov     [rbx], r15
0x18000a8e9  lea     r8, asc_1800713B8; "h"
0x18000a8f0  shr     rsi, 1Fh
0x18000a8f4  mov     rdx, r13; unsigned __int64
0x18000a8f7  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x18000a8fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a901  test    esi, esi
0x18000a903  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a90b  lea     r9, [rsp+288h+Name]; lpName
0x18000a910  mov     [rsp+288h+dwFlags], r12d; int
0x18000a915  cmovnz  ebp, esi
0x18000a918  mov     edx, esi; lInitialCount
0x18000a91a  mov     r8d, ebp; lMaximumCount
0x18000a91d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a91f  call    cs:__imp_CreateSemaphoreExW
0x18000a925  mov     rbp, rax
0x18000a928  test    rax, rax
0x18000a92b  jnz     short loc_18000A958
0x18000a92d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a932  mov     ebx, eax
0x18000a934  test    eax, eax
0x18000a936  jns     short loc_18000A988
0x18000a938  mov     rcx, [rsp+288h]; this
0x18000a940  lea     r8, aWil; "wil"
0x18000a947  mov     r9d, eax; char *
0x18000a94a  mov     edx, 90h; void *
0x18000a94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a954  mov     eax, ebx
0x18000a956  jmp     short loc_18000A98A
0x18000a958  call    cs:__imp_GetLastError
0x18000a95e  mov     rdi, [rbx+8]
0x18000a962  test    rdi, rdi
0x18000a965  jz      short loc_18000A984
0x18000a967  call    cs:__imp_GetLastError
0x18000a96d  mov     rcx, rdi; hObject
0x18000a970  mov     esi, eax
0x18000a972  call    cs:__imp_CloseHandle
0x18000a978  test    eax, eax
0x18000a97a  jz      short loc_18000A9B5
0x18000a97c  mov     ecx, esi; dwErrCode
0x18000a97e  call    cs:__imp_SetLastError
0x18000a984  mov     [rbx+8], rbp
0x18000a988  xor     eax, eax
0x18000a98a  mov     rcx, [rsp+288h+var_48]
0x18000a992  xor     rcx, rsp; StackCookie
0x18000a995  call    __security_check_cookie
0x18000a99a  mov     rbx, [rsp+288h+arg_8]
0x18000a9a2  add     rsp, 250h
0x18000a9a9  pop     r15
0x18000a9ab  pop     r14
0x18000a9ad  pop     r13
0x18000a9af  pop     r12
0x18000a9b1  pop     rdi
0x18000a9b2  pop     rsi
0x18000a9b3  pop     rbp
0x18000a9b4  retn
0x18000a9b5  mov     rcx, [rsp+288h]; this
0x18000a9bd  mov     edx, 0A0Bh; void *
0x18000a9c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a9ce  mov     rcx, [rsp+288h]; this
0x18000a9d6  mov     edx, 0A0Bh; void *
0x18000a9db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
