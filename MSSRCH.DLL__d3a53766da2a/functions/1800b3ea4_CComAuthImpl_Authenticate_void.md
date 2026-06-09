# CComAuthImpl::Authenticate(void)

- ea: `0x1800b3ea4`
- end: `0x1800b3faf`
- name: `?Authenticate@CComAuthImpl@@AEAAJXZ`
- size: `267`
- prototype: `__int64 __fastcall(CComAuthImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079bf0`

## callees

- `0x18004b638`
- `0x18004e5d8`
- `0x1800b3ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b3f31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b3f31`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b3f42`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b3f42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3ef9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3ef9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3f0e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b3f0e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3f87`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3f98`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3f87`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3f98`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b3eb0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b3eb0`

## string_xrefs

- `0x1800b3eda`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\atlext.cxx"`
- `0x1800b3f77`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\atlext.cxx"`
- `0x1800b3ece`: `[UtilCommon] failed to impersonate client 0x%08x`
- `0x1800b3f54`: `[UtilCommon] failed to OpenProcessToken %d`
- `0x1800b3f68`: `[UtilCommon] failed to OpenThreadToken %d`

## pseudocode

```c
__int64 __fastcall CComAuthImpl::Authenticate(CComAuthImpl *this)
{
  HRESULT v2; // ebx
  void **v4; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void **v7; // rdi
  HANDLE CurrentProcess; // rax
  const wchar_t *v9; // r8
  __int64 v10; // rdx

  v2 = CoImpersonateClient();
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147417833 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutill\\\\atlext.cxx\"",
      (const wchar_t *)0xE7,
      (unsigned int)L"[UtilCommon] failed to impersonate client 0x%08x",
      (const wchar_t *)(unsigned int)v2);
    return (unsigned int)v2;
  }
  v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 8);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, v4) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      *(_DWORD *)this = 0;
      v9 = (const wchar_t *)L"[UtilCommon] failed to OpenThreadToken %d";
      v10 = 254;
      goto LABEL_9;
    }
    v7 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put((char *)this + 8);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xEu, v7) )
    {
      *(_DWORD *)this = 0;
      LastError = GetLastError();
      v9 = L"[UtilCommon] failed to OpenProcessToken %d";
      v10 = 247;
LABEL_9:
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutill\\\\atlext.cxx\"",
        (const wchar_t *)v10,
        (unsigned int)v9,
        (const wchar_t *)LastError);
      if ( v2 >= 0 )
        CoRevertToSelf();
      return 2147942405LL;
    }
  }
  if ( v2 >= 0 )
    CoRevertToSelf();
  *(_DWORD *)this = 1;
  return 0;
}

```

## disassembly

```asm
0x1800b3ea4  push    rbx
0x1800b3ea6  push    rbp
0x1800b3ea7  push    rsi
0x1800b3ea8  push    rdi
0x1800b3ea9  sub     rsp, 28h
0x1800b3ead  mov     rsi, rcx
0x1800b3eb0  call    cs:__imp_CoImpersonateClient
0x1800b3eb6  mov     ecx, 80000000h
0x1800b3ebb  mov     ebx, eax
0x1800b3ebd  add     eax, ecx
0x1800b3ebf  test    ecx, eax
0x1800b3ec1  jnz     short loc_1800B3EED
0x1800b3ec3  cmp     ebx, 80010117h
0x1800b3ec9  jz      short loc_1800B3EED
0x1800b3ecb  mov     r9d, ebx; wchar_t *
0x1800b3ece  lea     r8, aUtilcommonFail_5; "[UtilCommon] failed to impersonate clie"...
0x1800b3ed5  mov     edx, 0E7h; wchar_t *
0x1800b3eda  lea     rcx, aOnecoreuapBase_193; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b3ee1  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b3ee6  mov     eax, ebx
0x1800b3ee8  jmp     loc_1800B3FA6
0x1800b3eed  lea     rcx, [rsi+8]
0x1800b3ef1  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800b3ef6  mov     rdi, rax
0x1800b3ef9  call    cs:__imp_GetCurrentThread
0x1800b3eff  mov     edx, 8; DesiredAccess
0x1800b3f04  mov     r9, rdi; TokenHandle
0x1800b3f07  mov     rcx, rax; ThreadHandle
0x1800b3f0a  lea     r8d, [rdx-7]; OpenAsSelf
0x1800b3f0e  call    cs:__imp_OpenThreadToken
0x1800b3f14  test    eax, eax
0x1800b3f16  jnz     short loc_1800B3F94
0x1800b3f18  call    cs:__imp_GetLastError
0x1800b3f1e  cmp     eax, 3F0h
0x1800b3f23  jnz     short loc_1800B3F62
0x1800b3f25  lea     rcx, [rsi+8]
0x1800b3f29  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800b3f2e  mov     rdi, rax
0x1800b3f31  call    cs:__imp_GetCurrentProcess
0x1800b3f37  mov     r8, rdi; TokenHandle
0x1800b3f3a  mov     edx, 0Eh; DesiredAccess
0x1800b3f3f  mov     rcx, rax; ProcessHandle
0x1800b3f42  call    cs:__imp_OpenProcessToken
0x1800b3f48  test    eax, eax
0x1800b3f4a  jnz     short loc_1800B3F94
0x1800b3f4c  mov     [rsi], eax
0x1800b3f4e  call    cs:__imp_GetLastError
0x1800b3f54  lea     r8, aUtilcommonFail_0; "[UtilCommon] failed to OpenProcessToken"...
0x1800b3f5b  mov     edx, 0F7h
0x1800b3f60  jmp     short loc_1800B3F74
0x1800b3f62  mov     dword ptr [rsi], 0
0x1800b3f68  lea     r8, aUtilcommonFail_3; "[UtilCommon] failed to OpenThreadToken "...
0x1800b3f6f  mov     edx, 0FEh; wchar_t *
0x1800b3f74  mov     r9d, eax; wchar_t *
0x1800b3f77  lea     rcx, aOnecoreuapBase_193; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800b3f7e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800b3f83  test    ebx, ebx
0x1800b3f85  js      short loc_1800B3F8D
0x1800b3f87  call    cs:__imp_CoRevertToSelf
0x1800b3f8d  mov     eax, 80070005h
0x1800b3f92  jmp     short loc_1800B3FA6
0x1800b3f94  test    ebx, ebx
0x1800b3f96  js      short loc_1800B3F9E
0x1800b3f98  call    cs:__imp_CoRevertToSelf
0x1800b3f9e  mov     dword ptr [rsi], 1
0x1800b3fa4  xor     eax, eax
0x1800b3fa6  add     rsp, 28h
0x1800b3faa  pop     rdi
0x1800b3fab  pop     rsi
0x1800b3fac  pop     rbp
0x1800b3fad  pop     rbx
0x1800b3fae  retn
```
