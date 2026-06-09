# IsComCallerAdmin(void)

- ea: `0x1800c3264`
- end: `0x1800c3378`
- name: `?IsComCallerAdmin@@YAHXZ`
- size: `276`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c9638`

## callees

- `0x180022730`
- `0x18002a700`
- `0x18002afbc`
- `0x18005cb90`
- `0x1800c3264`
- `0x1800c3380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c32b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c32b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c32a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c32a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c32e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3314`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c32e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c3314`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 IsComCallerAdmin(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  void *v2; // rdx
  HANDLE v4; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v5[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+28h] BYREF
  void *v10; // [rsp+88h] [rbp+30h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v10 = 0;
  v4 = 0;
  v5[0] = 0;
  v6 = 0;
  if ( (int)CImpersonateCaller::Impersonate((CImpersonateCaller *)v5) >= 0 )
  {
    ReturnLength = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength)
        && TokenInformation != 2
        && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v10,
              0),
            GetTokenInformation(TokenHandle, TokenLinkedToken, &v10, 8u, &ReturnLength)) )
      {
        v2 = v10;
        v10 = 0;
      }
      else
      {
        v2 = TokenHandle;
        TokenHandle = 0;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v4,
        v2);
      v0 = IsInAdministratorGroup(v4);
    }
  }
  CImpersonateCaller::~CImpersonateCaller((CImpersonateCaller *)v5);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v4);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x1800c3264  push    rbp
0x1800c3266  push    rbx
0x1800c3267  mov     rbp, rsp
0x1800c326a  sub     rsp, 58h
0x1800c326e  xor     ebx, ebx
0x1800c3270  mov     [rbp+TokenHandle], rbx
0x1800c3274  mov     [rbp+arg_18], rbx
0x1800c3278  mov     [rbp+var_28], rbx
0x1800c327c  mov     [rbp+var_20], bl
0x1800c327f  mov     [rbp+var_18], rbx
0x1800c3283  lea     rcx, [rbp+var_20]; this
0x1800c3287  call    ?Impersonate@CImpersonateCaller@@QEAAJXZ; CImpersonateCaller::Impersonate(void)
0x1800c328c  test    eax, eax
0x1800c328e  js      loc_1800C3348
0x1800c3294  mov     [rbp+arg_8], ebx
0x1800c3297  xor     edx, edx
0x1800c3299  lea     rcx, [rbp+TokenHandle]
0x1800c329d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c32a2  call    cs:__imp_GetCurrentThread
0x1800c32a8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c32ac  mov     edx, 0F01FFh; DesiredAccess
0x1800c32b1  lea     r8d, [rbx+1]; OpenAsSelf
0x1800c32b5  mov     rcx, rax; ThreadHandle
0x1800c32b8  call    cs:__imp_OpenThreadToken
0x1800c32be  test    eax, eax
0x1800c32c0  jz      loc_1800C3348
0x1800c32c6  mov     [rbp+TokenInformation], ebx
0x1800c32c9  lea     rax, [rbp+arg_8]
0x1800c32cd  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800c32d2  lea     r9d, [rbx+4]; TokenInformationLength
0x1800c32d6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800c32da  lea     edx, [rbx+12h]; TokenInformationClass
0x1800c32dd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c32e1  call    cs:__imp_GetTokenInformation
0x1800c32e7  test    eax, eax
0x1800c32e9  jz      short loc_1800C3328
0x1800c32eb  cmp     [rbp+TokenInformation], 2
0x1800c32ef  jz      short loc_1800C3328
0x1800c32f1  xor     edx, edx
0x1800c32f3  lea     rcx, [rbp+arg_18]
0x1800c32f7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c32fc  lea     rax, [rbp+arg_8]
0x1800c3300  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800c3305  lea     r9d, [rbx+8]; TokenInformationLength
0x1800c3309  lea     r8, [rbp+arg_18]; TokenInformation
0x1800c330d  lea     edx, [rbx+13h]; TokenInformationClass
0x1800c3310  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c3314  call    cs:__imp_GetTokenInformation
0x1800c331a  test    eax, eax
0x1800c331c  jz      short loc_1800C3328
0x1800c331e  mov     rdx, [rbp+arg_18]
0x1800c3322  mov     [rbp+arg_18], rbx
0x1800c3326  jmp     short loc_1800C3334
0x1800c3328  mov     rdx, [rbp+TokenHandle]
0x1800c332c  mov     [rbp+TokenHandle], 0
0x1800c3334  lea     rcx, [rbp+var_28]
0x1800c3338  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c333d  mov     rcx, [rbp+var_28]; TokenHandle
0x1800c3341  call    ?IsInAdministratorGroup@@YAHPEAX@Z; IsInAdministratorGroup(void *)
0x1800c3346  mov     ebx, eax
0x1800c3348  lea     rcx, [rbp+var_20]; this
0x1800c334c  call    ??1CImpersonateCaller@@QEAA@XZ; CImpersonateCaller::~CImpersonateCaller(void)
0x1800c3351  nop
0x1800c3352  lea     rcx, [rbp+var_28]
0x1800c3356  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c335b  nop
0x1800c335c  lea     rcx, [rbp+arg_18]
0x1800c3360  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c3365  nop
0x1800c3366  lea     rcx, [rbp+TokenHandle]
0x1800c336a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c336f  mov     eax, ebx
0x1800c3371  add     rsp, 58h
0x1800c3375  pop     rbx
0x1800c3376  pop     rbp
0x1800c3377  retn
```
