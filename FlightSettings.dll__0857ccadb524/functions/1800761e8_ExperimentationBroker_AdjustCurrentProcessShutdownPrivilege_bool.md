# ExperimentationBroker::AdjustCurrentProcessShutdownPrivilege(bool)

- ea: `0x1800761e8`
- end: `0x1800762ea`
- name: `?AdjustCurrentProcessShutdownPrivilege@ExperimentationBroker@@CAJ_N@Z`
- size: `258`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075bf4`
- `0x1800765c0`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x180010e9c`
- `0x180017870`
- `0x1800761e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180076273`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180076273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076260`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800762a5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800762a5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180076216`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180076216`

## string_xrefs

- `0x180076208`: `SeShutdownPrivilege`
- `0x180076225`: `onecore\base\flighting\flightsettings\broker\libs\experimentationbroker\experimentationbroker.cpp`
- `0x1800762b9`: `onecore\base\flighting\flightsettings\broker\libs\experimentationbroker\experimentationbroker.cpp`

## pseudocode

```c
__int64 __fastcall ExperimentationBroker::AdjustCurrentProcessShutdownPrivilege(unsigned __int8 a1)
{
  int v1; // ebx
  const char *v2; // r9
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = a1;
  NewState = 0;
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &NewState.Privileges[0].Luid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xE3,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\experimentationbroker\\experimentationbroker.cpp",
             v2);
  NewState.PrivilegeCount = 1;
  TokenHandle = 0;
  NewState.Privileges[0].Attributes = 2 * v1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
    {
      LastError = 0;
      goto LABEL_9;
    }
    v6 = 235;
  }
  else
  {
    v6 = 233;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\experimentationbroker\\experimentationbroker.cpp",
                v5);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800761e8  push    rbx
0x1800761ea  sub     rsp, 50h
0x1800761ee  mov     rax, cs:__security_cookie
0x1800761f5  xor     rax, rsp
0x1800761f8  mov     [rsp+58h+var_10], rax
0x1800761fd  movzx   ebx, cl
0x180076200  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x180076205  xorps   xmm0, xmm0
0x180076208  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18007620f  xor     ecx, ecx; lpSystemName
0x180076211  movups  xmmword ptr [rsp+38h], xmm0
0x180076216  call    cs:__imp_LookupPrivilegeValueW
0x18007621c  test    eax, eax
0x18007621e  jnz     short loc_18007623B
0x180076220  mov     rcx, [rsp+58h]; this
0x180076225  lea     r8, aOnecoreBaseFli_59; "onecore\\base\\flighting\\flightsetting"...
0x18007622c  mov     edx, 0E3h; void *
0x180076231  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180076236  jmp     loc_1800762D7
0x18007623b  mov     eax, ebx
0x18007623d  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x180076245  add     eax, eax
0x180076247  mov     [rsp+58h+TokenHandle], 0
0x180076250  xor     edx, edx
0x180076252  mov     [rsp+58h+NewState.Privileges.Attributes], eax
0x180076256  lea     rcx, [rsp+58h+TokenHandle]
0x18007625b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180076260  call    cs:__imp_GetCurrentProcess
0x180076266  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18007626b  mov     edx, 28h ; '('; DesiredAccess
0x180076270  mov     rcx, rax; ProcessHandle
0x180076273  call    cs:__imp_OpenProcessToken
0x180076279  test    eax, eax
0x18007627b  jnz     short loc_180076284
0x18007627d  mov     edx, 0E9h
0x180076282  jmp     short loc_1800762B4
0x180076284  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180076289  lea     r8, [rsp+58h+NewState]; NewState
0x18007628e  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x180076297  xor     r9d, r9d; BufferLength
0x18007629a  xor     edx, edx; DisableAllPrivileges
0x18007629c  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800762a5  call    cs:__imp_AdjustTokenPrivileges
0x1800762ab  test    eax, eax
0x1800762ad  jnz     short loc_1800762C9
0x1800762af  mov     edx, 0EBh; void *
0x1800762b4  mov     rcx, [rsp+58h]; this
0x1800762b9  lea     r8, aOnecoreBaseFli_59; "onecore\\base\\flighting\\flightsetting"...
0x1800762c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800762c5  mov     ebx, eax
0x1800762c7  jmp     short loc_1800762CB
0x1800762c9  xor     ebx, ebx
0x1800762cb  lea     rcx, [rsp+58h+TokenHandle]
0x1800762d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800762d5  mov     eax, ebx
0x1800762d7  mov     rcx, [rsp+58h+var_10]
0x1800762dc  xor     rcx, rsp; StackCookie
0x1800762df  call    __security_check_cookie
0x1800762e4  add     rsp, 50h
0x1800762e8  pop     rbx
0x1800762e9  retn
```
