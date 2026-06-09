# CRevertToSelf::MakePrivileged(void)

- ea: `0x1800e104c`
- end: `0x1800e1128`
- name: `?MakePrivileged@CRevertToSelf@@AEAAXXZ`
- size: `220`
- prototype: `void __fastcall(CRevertToSelf *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e05ac`
- `0x1800e1018`

## callees

- `0x18004e5d8`
- `0x1800e104c`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1068`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1068`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e107e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e107e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e10d0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e10d0`

## string_xrefs

- `0x1800e10bb`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800e1108`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800e10e2`: `[UtilSecurity] RevertToSelf() failed. 0x%08x`
- `0x1800e109e`: `[UtilSecurity] OpenThreadToken() failed with error 0x%08x.`
- `0x1800e10aa`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`
- `0x1800e10f1`: `"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx"`

## pseudocode

```c
void __fastcall CRevertToSelf::MakePrivileged(CRevertToSelf *this)
{
  HANDLE CurrentThread; // rax
  DWORD v3; // eax
  DWORD v4; // ebx
  BOOL v5; // eax
  DWORD LastError; // eax
  DWORD v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 0xEu, 1, (PHANDLE)this + 1)) )
  {
    v5 = RevertToSelf();
    *(_DWORD *)this = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
        (const wchar_t *)0x53,
        (unsigned int)L"[UtilSecurity] RevertToSelf() failed. 0x%08x",
        (const wchar_t *)LastError);
      v7 = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        (const char *)v7,
        v8);
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 != 1008 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\secutil\\\\secutil.cxx\"",
        (const wchar_t *)0x4A,
        (unsigned int)L"[UtilSecurity] OpenThreadToken() failed with error 0x%08x.",
        (const wchar_t *)v3);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        (const char *)v4,
        v8);
    }
  }
}

```

## disassembly

```asm
0x1800e104c  mov     [rsp+arg_0], rbx
0x1800e1051  push    rdi; unsigned int
0x1800e1052  sub     rsp, 20h
0x1800e1056  mov     rax, [rcx+8]
0x1800e105a  mov     rbx, rcx
0x1800e105d  inc     rax
0x1800e1060  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e1066  jnz     short loc_1800E10D0
0x1800e1068  call    cs:__imp_GetCurrentThread
0x1800e106e  mov     edx, 0Eh; DesiredAccess
0x1800e1073  lea     r9, [rbx+8]; TokenHandle
0x1800e1077  mov     rcx, rax; ThreadHandle
0x1800e107a  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800e107e  call    cs:__imp_OpenThreadToken
0x1800e1084  test    eax, eax
0x1800e1086  jnz     short loc_1800E10D0
0x1800e1088  call    cs:__imp_GetLastError
0x1800e108e  mov     ebx, eax
0x1800e1090  cmp     eax, 3F0h
0x1800e1095  jz      loc_1800E111D
0x1800e109b  mov     r9d, eax; wchar_t *
0x1800e109e  lea     r8, aUtilsecurityOp; "[UtilSecurity] OpenThreadToken() failed"...
0x1800e10a5  mov     edx, 4Ah ; 'J'; wchar_t *
0x1800e10aa  lea     rcx, aOnecoreuapBase_73; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800e10b1  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800e10b6  mov     rcx, [rsp+28h]; this
0x1800e10bb  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800e10c2  mov     r9d, ebx; char *
0x1800e10c5  mov     edx, 4Bh ; 'K'; void *
0x1800e10ca  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e10d0  call    cs:__imp_RevertToSelf
0x1800e10d6  mov     [rbx], eax
0x1800e10d8  test    eax, eax
0x1800e10da  jnz     short loc_1800E111D
0x1800e10dc  call    cs:__imp_GetLastError
0x1800e10e2  lea     r8, aUtilsecurityRe; "[UtilSecurity] RevertToSelf() failed. 0"...
0x1800e10e9  mov     edx, 53h ; 'S'; wchar_t *
0x1800e10ee  mov     r9d, eax; wchar_t *
0x1800e10f1  lea     rcx, aOnecoreuapBase_73; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800e10f8  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800e10fd  call    cs:__imp_GetLastError
0x1800e1103  mov     rcx, [rsp+28h]; this
0x1800e1108  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800e110f  mov     r9d, eax; char *
0x1800e1112  mov     edx, 54h ; 'T'; void *
0x1800e1117  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800e111d  mov     rbx, [rsp+28h+arg_0]
0x1800e1122  add     rsp, 20h
0x1800e1126  pop     rdi
0x1800e1127  retn
```
