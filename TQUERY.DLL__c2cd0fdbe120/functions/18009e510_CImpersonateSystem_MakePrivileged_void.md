# CImpersonateSystem::MakePrivileged(void)

- ea: `0x18009e510`
- end: `0x18009e60e`
- name: `?MakePrivileged@CImpersonateSystem@@AEAAXXZ`
- size: `254`
- prototype: `void __fastcall(CImpersonateSystem *__hidden this)`
- caller_count: `22`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062520`
- `0x180062830`
- `0x180062b60`
- `0x180063980`
- `0x180075580`
- `0x18009e470`
- `0x18009f068`
- `0x18009f2e0`
- `0x1800a8f84`
- `0x1800ebebc`
- `0x1800f77b0`
- `0x180157650`
- `0x180159ed0`
- `0x1801a6e2c`
- `0x1801a8a3c`
- `0x1801e4e4c`
- `0x1801edbc8`
- `0x1801f4b40`
- `0x1801f4c20`
- `0x1801f4dd0`
- `0x180204cd0`
- `0x180215da0`

## callees

- `0x18009e510`
- `0x180147154`
- `0x1801480fc`
- `0x18019b924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e585`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009e54f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009e54f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009e521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009e521`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009e536`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009e536`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009e560`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009e560`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009e579`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009e579`

## string_xrefs

- `0x18009e5ab`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x18009e5e2`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x18009e5fc`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x18009e5c5`: `OpenThreadToken() failed with error %#x\n`
- `0x18009e59a`: `"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx"`
- `0x18009e5d1`: `"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx"`

## pseudocode

```c
void __fastcall CImpersonateSystem::MakePrivileged(CImpersonateSystem *this)
{
  void **v2; // rdi
  HANDLE CurrentThread; // rax
  DWORD v4; // eax
  DWORD v5; // ebx
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  BOOL v8; // eax
  DWORD LastError; // eax
  const char *v10; // r9
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void **)((char *)this + 8);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, v2) )
  {
    v8 = RevertToSelf();
    *(_DWORD *)this = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\sysimprs\\\\sysimprs.cxx\"",
        (const wchar_t *)0x49,
        (unsigned int)L"RevertToSelf() failed with error %d\n",
        (const wchar_t *)LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx",
        v10);
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 != 1008 && v4 != 5 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\sysimprs\\\\sysimprs.cxx\"",
        (const wchar_t *)0x3E,
        (unsigned int)L"OpenThreadToken() failed with error %#x\n",
        (const wchar_t *)v4);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx",
        (const char *)v5,
        v11);
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, v2) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx",
        v7);
  }
}

```

## disassembly

```asm
0x18009e510  mov     [rsp+arg_0], rbx
0x18009e515  push    rdi; unsigned int
0x18009e516  sub     rsp, 20h
0x18009e51a  mov     rbx, rcx
0x18009e51d  lea     rdi, [rcx+8]
0x18009e521  call    cs:__imp_GetCurrentThread
0x18009e527  mov     edx, 0Eh; DesiredAccess
0x18009e52c  mov     r9, rdi; TokenHandle
0x18009e52f  mov     rcx, rax; ThreadHandle
0x18009e532  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x18009e536  call    cs:__imp_OpenThreadToken
0x18009e53c  test    eax, eax
0x18009e53e  jnz     short loc_18009E579
0x18009e540  call    cs:__imp_GetLastError
0x18009e546  mov     ebx, eax
0x18009e548  cmp     eax, 3F0h
0x18009e54d  jnz     short loc_18009E5BD
0x18009e54f  call    cs:__imp_GetCurrentProcess
0x18009e555  mov     r8, rdi; TokenHandle
0x18009e558  mov     edx, 0Ah; DesiredAccess
0x18009e55d  mov     rcx, rax; ProcessHandle
0x18009e560  call    cs:__imp_OpenProcessToken
0x18009e566  test    eax, eax
0x18009e568  jz      loc_18009E5F7
0x18009e56e  mov     rbx, [rsp+28h+arg_0]
0x18009e573  add     rsp, 20h
0x18009e577  pop     rdi
0x18009e578  retn
0x18009e579  call    cs:__imp_RevertToSelf
0x18009e57f  mov     [rbx], eax
0x18009e581  test    eax, eax
0x18009e583  jnz     short loc_18009E56E
0x18009e585  call    cs:__imp_GetLastError
0x18009e58b  lea     r8, aReverttoselfFa; "RevertToSelf() failed with error %d\n"
0x18009e592  mov     edx, 49h ; 'I'; wchar_t *
0x18009e597  mov     r9d, eax; wchar_t *
0x18009e59a  lea     rcx, aOnecoreuapBase_4; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18009e5a1  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18009e5a6  mov     rcx, [rsp+28h]; this
0x18009e5ab  lea     r8, aOnecoreuapBase_207; "onecoreuap\\base\\appmodel\\search\\com"...
0x18009e5b2  mov     edx, 4Ah ; 'J'; void *
0x18009e5b7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009e5bd  cmp     ebx, 5
0x18009e5c0  jz      short loc_18009E54F
0x18009e5c2  mov     r9d, ebx; wchar_t *
0x18009e5c5  lea     r8, aOpenthreadtoke; "OpenThreadToken() failed with error %#x"...
0x18009e5cc  mov     edx, 3Eh ; '>'; wchar_t *
0x18009e5d1  lea     rcx, aOnecoreuapBase_4; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18009e5d8  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18009e5dd  mov     rcx, [rsp+28h]; this
0x18009e5e2  lea     r8, aOnecoreuapBase_207; "onecoreuap\\base\\appmodel\\search\\com"...
0x18009e5e9  mov     r9d, ebx; char *
0x18009e5ec  mov     edx, 3Fh ; '?'; void *
0x18009e5f1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009e5f7  mov     rcx, [rsp+28h]; this
0x18009e5fc  lea     r8, aOnecoreuapBase_207; "onecoreuap\\base\\appmodel\\search\\com"...
0x18009e603  mov     edx, 39h ; '9'; void *
0x18009e608  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
