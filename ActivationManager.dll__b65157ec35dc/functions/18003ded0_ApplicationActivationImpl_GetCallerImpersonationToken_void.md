# ApplicationActivationImpl::GetCallerImpersonationToken(void * *)

- ea: `0x18003ded0`
- end: `0x18003e014`
- name: `?GetCallerImpersonationToken@ApplicationActivationImpl@@AEAAJPEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(ApplicationActivationImpl *this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076d90`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x18003ded0`
- `0x18003f63c`
- `0x180044408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df1d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003dfd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003dfd7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003df30`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003df30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003dfc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003dfc2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003dff9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003e001`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003dff9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003e001`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003dee9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003dee9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003df67`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003df67`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall ApplicationActivationImpl::GetCallerImpersonationToken(ApplicationActivationImpl *this, void **a2)
{
  HRESULT v3; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rax
  BOOL v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-38h]
  HANDLE *p_hExistingToken; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-20h] BYREF
  char v15; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE hExistingToken; // [rsp+60h] [rbp+8h] BYREF

  hExistingToken = this;
  *a2 = 0;
  v3 = CoImpersonateClient();
  LastError = v3;
  if ( v3 == -2147417833 )
  {
    hExistingToken = 0;
    p_hExistingToken = &hExistingToken;
    TokenHandle = 0;
    v15 = 1;
    CurrentProcess = GetCurrentProcess();
    v6 = OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hExistingToken);
    if ( !v6 )
    {
      v8 = 973;
LABEL_6:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v8,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                    v7);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
      return LastError;
    }
    if ( !DuplicateTokenEx(hExistingToken, 0, 0, SecurityImpersonation, TokenImpersonation, a2) )
    {
      v8 = 974;
      goto LABEL_6;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  }
  else
  {
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D2,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v3,
        TokenType);
      return LastError;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, a2) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3D4,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                    v11);
      CoRevertToSelf();
      return LastError;
    }
    CoRevertToSelf();
  }
  return 0;
}

```

## disassembly

```asm
0x18003ded0  mov     [rsp+arg_8], rbx
0x18003ded5  mov     [rsp+hExistingToken], rcx
0x18003deda  push    rdi
0x18003dedb  sub     rsp, 50h
0x18003dedf  mov     rdi, rdx
0x18003dee2  mov     qword ptr [rdx], 0
0x18003dee9  call    cs:__imp_CoImpersonateClient
0x18003deef  mov     ebx, eax
0x18003def1  cmp     eax, 80010117h
0x18003def6  jnz     loc_18003DFA3
0x18003defc  lea     rax, [rsp+58h+hExistingToken]
0x18003df01  mov     [rsp+58h+hExistingToken], 0
0x18003df0a  mov     [rsp+58h+var_28], rax
0x18003df0f  mov     [rsp+58h+TokenHandle], 0
0x18003df18  mov     [rsp+58h+var_18], 1
0x18003df1d  call    cs:__imp_GetCurrentProcess
0x18003df23  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18003df28  mov     edx, 0Ah; DesiredAccess
0x18003df2d  mov     rcx, rax; ProcessHandle
0x18003df30  call    cs:__imp_OpenProcessToken
0x18003df36  lea     rcx, [rsp+58h+var_28]
0x18003df3b  mov     ebx, eax
0x18003df3d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18003df42  test    ebx, ebx
0x18003df44  jnz     short loc_18003DF4D
0x18003df46  mov     edx, 3CDh
0x18003df4b  jmp     short loc_18003DF76
0x18003df4d  mov     rcx, [rsp+58h+hExistingToken]; hExistingToken
0x18003df52  mov     r9d, 2; ImpersonationLevel
0x18003df58  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x18003df5d  xor     r8d, r8d; lpTokenAttributes
0x18003df60  xor     edx, edx; dwDesiredAccess
0x18003df62  mov     [rsp+58h+TokenType], r9d; TokenType
0x18003df67  call    cs:__imp_DuplicateTokenEx
0x18003df6d  test    eax, eax
0x18003df6f  jnz     short loc_18003DF97
0x18003df71  mov     edx, 3CEh; void *
0x18003df76  mov     rcx, [rsp+58h]; this
0x18003df7b  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003df82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003df87  lea     rcx, [rsp+58h+hExistingToken]
0x18003df8c  mov     ebx, eax
0x18003df8e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003df93  mov     eax, ebx
0x18003df95  jmp     short loc_18003E009
0x18003df97  lea     rcx, [rsp+58h+hExistingToken]
0x18003df9c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003dfa1  jmp     short loc_18003E007
0x18003dfa3  test    ebx, ebx
0x18003dfa5  jns     short loc_18003DFC2
0x18003dfa7  mov     rcx, [rsp+58h]; this
0x18003dfac  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003dfb3  mov     r9d, ebx; char *
0x18003dfb6  mov     edx, 3D2h; void *
0x18003dfbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dfc0  jmp     short loc_18003DF93
0x18003dfc2  call    cs:__imp_GetCurrentThread
0x18003dfc8  mov     edx, 8; DesiredAccess
0x18003dfcd  mov     r9, rdi; TokenHandle
0x18003dfd0  mov     rcx, rax; ThreadHandle
0x18003dfd3  lea     r8d, [rdx-7]; OpenAsSelf
0x18003dfd7  call    cs:__imp_OpenThreadToken
0x18003dfdd  test    eax, eax
0x18003dfdf  jnz     short loc_18003E001
0x18003dfe1  mov     rcx, [rsp+58h]; this
0x18003dfe6  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003dfed  mov     edx, 3D4h; void *
0x18003dff2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003dff7  mov     ebx, eax
0x18003dff9  call    cs:__imp_CoRevertToSelf
0x18003dfff  jmp     short loc_18003DF93
0x18003e001  call    cs:__imp_CoRevertToSelf
0x18003e007  xor     eax, eax
0x18003e009  mov     rbx, [rsp+58h+arg_8]
0x18003e00e  add     rsp, 50h
0x18003e012  pop     rdi
0x18003e013  retn
```
