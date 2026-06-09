# CImpersonateSystem::MakePrivileged(void)

- ea: `0x1800b827c`
- end: `0x1800b8374`
- name: `?MakePrivileged@CImpersonateSystem@@AEAAXXZ`
- size: `248`
- prototype: `void __fastcall(CImpersonateSystem *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b7e9c`
- `0x1800cb000`
- `0x1800e5d84`
- `0x1800e6594`
- `0x18010822c`
- `0x1801c7c0c`
- `0x18020d864`
- `0x18020d95c`

## callees

- `0x18004e5d8`
- `0x1800b827c`
- `0x1800e95f0`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b82ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b82ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b82f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b82f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b8306`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b8306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b828d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b828d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b82a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b82a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b8325`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b8325`

## string_xrefs

- `0x1800b82e0`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x1800b8315`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x1800b8357`: `onecoreuap\base\appmodel\search\common\sysimprs\sysimprs.cxx`
- `0x1800b82c3`: `OpenThreadToken() failed with error %#x\n`
- `0x1800b82cf`: `"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx"`
- `0x1800b8346`: `"onecoreuap\\base\\appmodel\\search\\common\\sysimprs\\sysimprs.cxx"`

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
0x1800b827c  mov     [rsp+arg_0], rbx
0x1800b8281  push    rdi; unsigned int
0x1800b8282  sub     rsp, 20h
0x1800b8286  mov     rbx, rcx
0x1800b8289  lea     rdi, [rcx+8]
0x1800b828d  call    cs:__imp_GetCurrentThread
0x1800b8293  mov     edx, 0Eh; DesiredAccess
0x1800b8298  mov     r9, rdi; TokenHandle
0x1800b829b  mov     rcx, rax; ThreadHandle
0x1800b829e  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800b82a2  call    cs:__imp_OpenThreadToken
0x1800b82a8  test    eax, eax
0x1800b82aa  jnz     short loc_1800B8325
0x1800b82ac  call    cs:__imp_GetLastError
0x1800b82b2  mov     ebx, eax
0x1800b82b4  cmp     eax, 3F0h
0x1800b82b9  jz      short loc_1800B82F5
0x1800b82bb  cmp     eax, 5
0x1800b82be  jz      short loc_1800B82F5
0x1800b82c0  mov     r9d, eax; wchar_t *
0x1800b82c3  lea     r8, aOpenthreadtoke; "OpenThreadToken() failed with error %#x"...
0x1800b82ca  mov     edx, 3Eh ; '>'; wchar_t *
0x1800b82cf  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b82d6  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b82db  mov     rcx, [rsp+28h]; this
0x1800b82e0  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800b82e7  mov     r9d, ebx; char *
0x1800b82ea  mov     edx, 3Fh ; '?'; void *
0x1800b82ef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b82f5  call    cs:__imp_GetCurrentProcess
0x1800b82fb  mov     r8, rdi; TokenHandle
0x1800b82fe  mov     edx, 0Ah; DesiredAccess
0x1800b8303  mov     rcx, rax; ProcessHandle
0x1800b8306  call    cs:__imp_OpenProcessToken
0x1800b830c  test    eax, eax
0x1800b830e  jnz     short loc_1800B8369
0x1800b8310  mov     rcx, [rsp+28h]; this
0x1800b8315  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800b831c  lea     edx, [rax+39h]; void *
0x1800b831f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b8325  call    cs:__imp_RevertToSelf
0x1800b832b  mov     [rbx], eax
0x1800b832d  test    eax, eax
0x1800b832f  jnz     short loc_1800B8369
0x1800b8331  call    cs:__imp_GetLastError
0x1800b8337  lea     r8, aReverttoselfFa; "RevertToSelf() failed with error %d\n"
0x1800b833e  mov     edx, 49h ; 'I'; wchar_t *
0x1800b8343  mov     r9d, eax; wchar_t *
0x1800b8346  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b834d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b8352  mov     rcx, [rsp+28h]; this
0x1800b8357  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800b835e  mov     edx, 4Ah ; 'J'; void *
0x1800b8363  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b8369  mov     rbx, [rsp+28h+arg_0]
0x1800b836e  add     rsp, 20h
0x1800b8372  pop     rdi
0x1800b8373  retn
```
