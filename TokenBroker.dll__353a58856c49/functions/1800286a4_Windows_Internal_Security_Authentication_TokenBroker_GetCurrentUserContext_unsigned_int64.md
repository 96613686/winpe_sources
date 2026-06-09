# Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(unsigned __int64 *)

- ea: `0x1800286a4`
- end: `0x1800287a6`
- name: `?GetCurrentUserContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEA_K@Z`
- size: `258`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, unsigned __int64 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028adc`
- `0x180028f20`
- `0x1800435d4`
- `0x18005f6c0`
- `0x180073f54`
- `0x1800f0260`
- `0x180101d00`

## callees

- `0x180024000`
- `0x1800286a4`
- `0x1800349d0`
- `0x18007c220`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800286db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800286db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800286f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800286f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002873f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002873f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002872d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002872d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028720`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002876a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002877f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002876a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002877f`

## string_xrefs

- `0x1800286ff`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002874d`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCurrentUserContext(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        unsigned __int64 *a2)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  unsigned int v8; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  void *TokenHandle; // [rsp+38h] [rbp+18h] BYREF
  __int64 v12; // [rsp+40h] [rbp+20h] BYREF

  TokenHandle = 0;
  v12 = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x986,
                    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
                    v7);
LABEL_10:
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
      return LastError;
    }
LABEL_7:
    v8 = UMgrQueryUserContext(TokenHandle, &v12);
    if ( v8 == -2147024891 )
      v8 = UMgrQueryUserContext(0, &v12);
    *(_QWORD *)this = v12;
    LastError = v8;
    goto LABEL_10;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_7;
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x982,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
                v4);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800286a4  mov     [rsp-8+arg_0], rbx
0x1800286a9  push    rbp
0x1800286aa  mov     rbp, rsp
0x1800286ad  sub     rsp, 20h
0x1800286b1  mov     [rbp+TokenHandle], 0
0x1800286b9  xor     edx, edx
0x1800286bb  mov     [rbp+arg_10], 0
0x1800286c3  mov     rbx, rcx
0x1800286c6  mov     eax, gs:179Ch
0x1800286ce  lea     rcx, [rbp+TokenHandle]
0x1800286d2  test    eax, eax
0x1800286d4  jz      short loc_180028728
0x1800286d6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800286db  call    cs:__imp_GetCurrentThread
0x1800286e1  mov     edx, 8; DesiredAccess
0x1800286e6  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800286ea  mov     rcx, rax; ThreadHandle
0x1800286ed  lea     r8d, [rdx-7]; OpenAsSelf
0x1800286f1  call    cs:__imp_OpenThreadToken
0x1800286f7  test    eax, eax
0x1800286f9  jnz     short loc_180028762
0x1800286fb  mov     rcx, [rbp+8]; this
0x1800286ff  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x180028706  mov     edx, 982h; void *
0x18002870b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028710  mov     rcx, [rbp+TokenHandle]; hObject
0x180028714  mov     ebx, eax
0x180028716  lea     rdx, [rcx-1]
0x18002871a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002871e  ja      short loc_180028799
0x180028720  call    cs:__imp_CloseHandle
0x180028726  jmp     short loc_180028799
0x180028728  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002872d  call    cs:__imp_GetCurrentProcess
0x180028733  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180028737  mov     edx, 8; DesiredAccess
0x18002873c  mov     rcx, rax; ProcessHandle
0x18002873f  call    cs:__imp_OpenProcessToken
0x180028745  test    eax, eax
0x180028747  jnz     short loc_180028762
0x180028749  mov     rcx, [rbp+8]; this
0x18002874d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x180028754  mov     edx, 986h; void *
0x180028759  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002875e  mov     ebx, eax
0x180028760  jmp     short loc_180028790
0x180028762  mov     rcx, [rbp+TokenHandle]
0x180028766  lea     rdx, [rbp+arg_10]
0x18002876a  call    cs:__imp_UMgrQueryUserContext
0x180028770  mov     ecx, eax
0x180028772  cmp     eax, 80070005h
0x180028777  jnz     short loc_180028787
0x180028779  lea     rdx, [rbp+arg_10]
0x18002877d  xor     ecx, ecx
0x18002877f  call    cs:__imp_UMgrQueryUserContext
0x180028785  mov     ecx, eax
0x180028787  mov     rax, [rbp+arg_10]
0x18002878b  mov     [rbx], rax
0x18002878e  mov     ebx, ecx
0x180028790  lea     rcx, [rbp+TokenHandle]; this
0x180028794  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180028799  mov     eax, ebx
0x18002879b  mov     rbx, [rsp+20h+arg_0]
0x1800287a0  add     rsp, 20h
0x1800287a4  pop     rbp
0x1800287a5  retn
```
