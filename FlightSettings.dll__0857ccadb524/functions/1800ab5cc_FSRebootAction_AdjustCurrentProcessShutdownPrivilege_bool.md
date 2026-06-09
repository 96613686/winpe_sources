# FSRebootAction::AdjustCurrentProcessShutdownPrivilege(bool)

- ea: `0x1800ab5cc`
- end: `0x1800ab6b4`
- name: `?AdjustCurrentProcessShutdownPrivilege@FSRebootAction@@CAJ_N@Z`
- size: `232`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab920`

## callees

- `0x180004b80`
- `0x18000cc6c`
- `0x180010e9c`
- `0x180017870`
- `0x1800ab5cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab60c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab60c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab5f9`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800ab684`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800ab684`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800ab631`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800ab631`

## string_xrefs

- `0x1800ab623`: `SeShutdownPrivilege`
- `0x1800ab643`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsrebootaction.cpp`

## pseudocode

```c
__int64 __fastcall FSRebootAction::AdjustCurrentProcessShutdownPrivilege(unsigned __int8 a1)
{
  int v1; // ebx
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = a1;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState = 0;
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", &NewState.Privileges[0].Luid) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2 * v1;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        LastError = 0;
        goto LABEL_9;
      }
      v4 = 94;
    }
    else
    {
      v4 = 89;
    }
  }
  else
  {
    v4 = 86;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsrebootaction.cpp",
                v3);
LABEL_9:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800ab5cc  push    rbx
0x1800ab5ce  sub     rsp, 50h
0x1800ab5d2  mov     rax, cs:__security_cookie
0x1800ab5d9  xor     rax, rsp
0x1800ab5dc  mov     [rsp+58h+var_10], rax
0x1800ab5e1  movzx   ebx, cl
0x1800ab5e4  xor     edx, edx
0x1800ab5e6  lea     rcx, [rsp+58h+TokenHandle]
0x1800ab5eb  mov     [rsp+58h+TokenHandle], 0
0x1800ab5f4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800ab5f9  call    cs:__imp_GetCurrentProcess
0x1800ab5ff  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800ab604  mov     edx, 28h ; '('; DesiredAccess
0x1800ab609  mov     rcx, rax; ProcessHandle
0x1800ab60c  call    cs:__imp_OpenProcessToken
0x1800ab612  test    eax, eax
0x1800ab614  jnz     short loc_1800AB61B
0x1800ab616  lea     edx, [rax+56h]
0x1800ab619  jmp     short loc_1800AB63E
0x1800ab61b  xorps   xmm0, xmm0
0x1800ab61e  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x1800ab623  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x1800ab62a  xor     ecx, ecx; lpSystemName
0x1800ab62c  movups  xmmword ptr [rsp+38h], xmm0
0x1800ab631  call    cs:__imp_LookupPrivilegeValueW
0x1800ab637  test    eax, eax
0x1800ab639  jnz     short loc_1800AB653
0x1800ab63b  lea     edx, [rax+59h]; void *
0x1800ab63e  mov     rcx, [rsp+58h]; this
0x1800ab643  lea     r8, aOnecoreBaseFli_98; "onecore\\base\\flighting\\flightsetting"...
0x1800ab64a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ab64f  mov     ebx, eax
0x1800ab651  jmp     short loc_1800AB695
0x1800ab653  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800ab658  lea     r8, [rsp+58h+NewState]; NewState
0x1800ab65d  mov     eax, ebx
0x1800ab65f  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1800ab668  add     eax, eax
0x1800ab66a  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1800ab672  xor     r9d, r9d; BufferLength
0x1800ab675  mov     [rsp+58h+NewState.Privileges.Attributes], eax
0x1800ab679  xor     edx, edx; DisableAllPrivileges
0x1800ab67b  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800ab684  call    cs:__imp_AdjustTokenPrivileges
0x1800ab68a  test    eax, eax
0x1800ab68c  jnz     short loc_1800AB693
0x1800ab68e  lea     edx, [rax+5Eh]
0x1800ab691  jmp     short loc_1800AB63E
0x1800ab693  xor     ebx, ebx
0x1800ab695  lea     rcx, [rsp+58h+TokenHandle]
0x1800ab69a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ab69f  mov     eax, ebx
0x1800ab6a1  mov     rcx, [rsp+58h+var_10]
0x1800ab6a6  xor     rcx, rsp; StackCookie
0x1800ab6a9  call    __security_check_cookie
0x1800ab6ae  add     rsp, 50h
0x1800ab6b2  pop     rbx
0x1800ab6b3  retn
```
