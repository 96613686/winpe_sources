# OpenCallerImpersonationToken

- ea: `0x18000926c`
- end: `0x180009484`
- name: `OpenCallerImpersonationToken`
- size: `536`
- prototype: ``
- caller_count: `18`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008b00`
- `0x180034114`
- `0x180047cf4`
- `0x1800493c0`
- `0x18004fe40`
- `0x180054074`
- `0x1800547f0`
- `0x180058114`
- `0x18005b5e0`
- `0x1800986e0`
- `0x180098f9c`
- `0x180099b3c`
- `0x18009aa78`
- `0x1800a2ba0`
- `0x1800a3cb0`
- `0x1800a3edc`
- `0x1800a44a8`
- `0x1800a4c30`

## callees

- `0x180007964`
- `0x18000926c`
- `0x1800323d0`
- `0x180048304`
- `0x180049a54`
- `0x1800527ac`
- `0x1800535f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009352`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800093ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800093ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000939a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000939a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009329`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009329`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009417`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009417`
- `RPCRT4!RpcImpersonateClient` at `0x1800092aa`
- `RPCRT4!RpcImpersonateClient` at `0x1800092aa`

## string_xrefs

- `0x1800092bf`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x18000936b`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800093c5`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180009430`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall OpenCallerImpersonationToken(int a1, HANDLE *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  DWORD LastError; // eax
  unsigned int v8; // eax
  HANDLE CurrentProcess; // rax
  BOOL v10; // ebx
  const char *v11; // r9
  BOOL v12; // ebx
  const char *v13; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-40h]
  int *v16; // [rsp+30h] [rbp-30h] BYREF
  __int16 v17; // [rsp+38h] [rbp-28h]
  HANDLE *p_hObject; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  char v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v22; // [rsp+80h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+28h] BYREF
  void *v24; // [rsp+90h] [rbp+30h] BYREF

  v22 = a1;
  hObject = 0;
  LOBYTE(v22) = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a2 = 0;
  v16 = &v22;
  v17 = 256;
  v3 = RpcImpersonateClient(0);
  if ( !v3 )
  {
    LOBYTE(v22) = 1;
LABEL_8:
    TokenHandle = 0;
    p_hObject = &hObject;
    v20 = 1;
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hObject);
    if ( v6 )
    {
      *a2 = hObject;
      hObject = 0;
LABEL_19:
      v4 = 0;
      goto LABEL_20;
    }
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      TokenHandle = 0;
      p_hObject = &hObject;
      v20 = 1;
      CurrentProcess = GetCurrentProcess();
      v10 = OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hObject);
      if ( v10 )
      {
        p_hObject = &v24;
        v24 = 0;
        TokenHandle = 0;
        v20 = 1;
        v12 = DuplicateTokenEx(hObject, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, &TokenHandle);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hObject);
        if ( v12 )
        {
          *a2 = v24;
          v24 = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
          goto LABEL_19;
        }
        v4 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xCF,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
               v13);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
LABEL_20:
        wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&v16);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        return v4;
      }
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xC4,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             v11);
    }
    else
    {
      if ( !LastError )
        goto LABEL_19;
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xBD,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             (const char *)LastError,
             TokenType);
    }
    v4 = v8;
    goto LABEL_20;
  }
  if ( v3 == 1725 )
    goto LABEL_8;
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xAC,
         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
         (const char *)v3,
         TokenType);
  wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&v16);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x18000926c  mov     [rsp-18h+arg_0], ecx
0x180009270  push    rbp
0x180009271  push    rbx
0x180009272  push    rdi
0x180009273  mov     rbp, rsp
0x180009276  sub     rsp, 60h
0x18000927a  mov     [rbp+hObject], 0
0x180009282  mov     rdi, rdx
0x180009285  mov     byte ptr [rbp+arg_0], 0
0x180009289  test    rdx, rdx
0x18000928c  jnz     short loc_180009293
0x18000928e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009293  lea     rax, [rbp+arg_0]
0x180009297  mov     qword ptr [rdi], 0
0x18000929e  xor     ecx, ecx; BindingHandle
0x1800092a0  mov     [rbp+var_30], rax
0x1800092a4  mov     [rbp+var_28], 100h
0x1800092aa  call    cs:__imp_RpcImpersonateClient
0x1800092b0  test    eax, eax
0x1800092b2  jz      short loc_1800092FB
0x1800092b4  cmp     eax, 6BDh
0x1800092b9  jz      short loc_1800092FF
0x1800092bb  mov     rcx, [rbp+18h]; this
0x1800092bf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800092c6  mov     r9d, eax; char *
0x1800092c9  mov     edx, 0ACh; void *
0x1800092ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800092d3  lea     rcx, [rbp+var_30]
0x1800092d7  mov     ebx, eax
0x1800092d9  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x1800092de  mov     rcx, [rbp+hObject]; hObject
0x1800092e2  lea     rdx, [rcx-1]
0x1800092e6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800092ea  ja      loc_18000947A
0x1800092f0  call    cs:__imp_CloseHandle
0x1800092f6  jmp     loc_18000947A
0x1800092fb  mov     byte ptr [rbp+arg_0], 1
0x1800092ff  lea     rax, [rbp+hObject]
0x180009303  mov     [rbp+TokenHandle], 0
0x18000930b  mov     [rbp+var_20], rax
0x18000930f  mov     [rbp+var_10], 1
0x180009313  call    cs:__imp_GetCurrentThread
0x180009319  mov     edx, 8; DesiredAccess
0x18000931e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180009322  mov     rcx, rax; ThreadHandle
0x180009325  lea     r8d, [rdx-7]; OpenAsSelf
0x180009329  call    cs:__imp_OpenThreadToken
0x18000932f  lea     rcx, [rbp+var_20]
0x180009333  mov     ebx, eax
0x180009335  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18000933a  test    ebx, ebx
0x18000933c  jz      short loc_180009352
0x18000933e  mov     rax, [rbp+hObject]
0x180009342  mov     [rdi], rax
0x180009345  mov     [rbp+hObject], 0
0x18000934d  jmp     loc_180009466
0x180009352  call    cs:__imp_GetLastError
0x180009358  cmp     eax, 3F0h
0x18000935d  jz      short loc_180009386
0x18000935f  test    eax, eax
0x180009361  jz      loc_180009466
0x180009367  mov     rcx, [rbp+18h]; this
0x18000936b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180009372  mov     r9d, eax; char *
0x180009375  mov     edx, 0BDh; void *
0x18000937a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000937f  mov     ebx, eax
0x180009381  jmp     loc_180009468
0x180009386  lea     rax, [rbp+hObject]
0x18000938a  mov     [rbp+TokenHandle], 0
0x180009392  mov     [rbp+var_20], rax
0x180009396  mov     [rbp+var_10], 1
0x18000939a  call    cs:__imp_GetCurrentProcess
0x1800093a0  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800093a4  mov     edx, 0Ah; DesiredAccess
0x1800093a9  mov     rcx, rax; ProcessHandle
0x1800093ac  call    cs:__imp_OpenProcessToken
0x1800093b2  lea     rcx, [rbp+var_20]
0x1800093b6  mov     ebx, eax
0x1800093b8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800093bd  test    ebx, ebx
0x1800093bf  jnz     short loc_1800093D8
0x1800093c1  mov     rcx, [rbp+18h]; this
0x1800093c5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800093cc  mov     edx, 0C4h; void *
0x1800093d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800093d6  jmp     short loc_18000937F
0x1800093d8  mov     rcx, [rbp+hObject]; hExistingToken
0x1800093dc  lea     rax, [rbp+arg_10]
0x1800093e0  mov     [rbp+var_20], rax
0x1800093e4  mov     r9d, 1; ImpersonationLevel
0x1800093ea  lea     rax, [rbp+TokenHandle]
0x1800093ee  mov     [rbp+arg_10], 0
0x1800093f6  mov     [rsp+60h+phNewToken], rax; phNewToken
0x1800093fb  xor     r8d, r8d; lpTokenAttributes
0x1800093fe  mov     edx, 2000000h; dwDesiredAccess
0x180009403  mov     [rsp+60h+TokenType], 2; TokenType
0x18000940b  mov     [rbp+TokenHandle], 0
0x180009413  mov     [rbp+var_10], 1
0x180009417  call    cs:__imp_DuplicateTokenEx
0x18000941d  lea     rcx, [rbp+var_20]
0x180009421  mov     ebx, eax
0x180009423  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180009428  test    ebx, ebx
0x18000942a  jnz     short loc_18000944E
0x18000942c  mov     rcx, [rbp+18h]; this
0x180009430  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180009437  mov     edx, 0CFh; void *
0x18000943c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009441  lea     rcx, [rbp+arg_10]
0x180009445  mov     ebx, eax
0x180009447  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000944c  jmp     short loc_180009468
0x18000944e  mov     rax, [rbp+arg_10]
0x180009452  lea     rcx, [rbp+arg_10]
0x180009456  mov     [rdi], rax
0x180009459  mov     [rbp+arg_10], 0
0x180009461  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009466  xor     ebx, ebx
0x180009468  lea     rcx, [rbp+var_30]
0x18000946c  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x180009471  lea     rcx, [rbp+hObject]
0x180009475  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000947a  mov     eax, ebx
0x18000947c  add     rsp, 60h
0x180009480  pop     rdi
0x180009481  pop     rbx
0x180009482  pop     rbp
0x180009483  retn
```
