# Windows::Graphics::Capture::Server::FailIfUapApplication(void)

- ea: `0x18001ee10`
- end: `0x18001eeba`
- name: `?FailIfUapApplication@Server@Capture@Graphics@Windows@@YAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e5e4`

## callees

- `0x18000905c`
- `0x18000dec8`
- `0x18001892c`
- `0x18001ee10`
- `0x18001f160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ee43`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ee43`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ee73`

## string_xrefs

- `0x18001ee80`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::FailIfUapApplication(Windows::Graphics::Capture::Server *this)
{
  unsigned int LastError; // ebx
  const char *v2; // r9
  __int64 v3; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  int TokenInformation; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+28h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp+30h] BYREF

  LastError = 0;
  ProcessHandle = 0;
  Windows::Graphics::Capture::Server::GetClientProcessHandle(&ProcessHandle);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( !OpenProcessToken(ProcessHandle, 0x18u, &TokenHandle) )
  {
    v3 = 93;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v3,
                  (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                  v2);
    goto LABEL_8;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    v3 = 97;
    goto LABEL_5;
  }
  if ( TokenInformation )
    LastError = -2147024891;
LABEL_8:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001ee10  push    rbp
0x18001ee12  push    rbx
0x18001ee13  mov     rbp, rsp
0x18001ee16  sub     rsp, 38h
0x18001ee1a  xor     ebx, ebx
0x18001ee1c  mov     [rbp+ProcessHandle], rbx
0x18001ee20  lea     rcx, [rbp+ProcessHandle]
0x18001ee24  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001ee29  mov     [rbp+TokenHandle], rbx
0x18001ee2d  xor     edx, edx
0x18001ee2f  lea     rcx, [rbp+TokenHandle]
0x18001ee33  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ee38  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001ee3c  lea     edx, [rbx+18h]; DesiredAccess
0x18001ee3f  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18001ee43  call    cs:__imp_OpenProcessToken
0x18001ee49  test    eax, eax
0x18001ee4b  jnz     short loc_18001EE52
0x18001ee4d  lea     edx, [rbx+5Dh]
0x18001ee50  jmp     short loc_18001EE80
0x18001ee52  mov     [rbp+TokenInformation], ebx
0x18001ee55  mov     [rbp+arg_8], ebx
0x18001ee58  lea     rax, [rbp+arg_8]
0x18001ee5c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001ee61  mov     r9d, 4; TokenInformationLength
0x18001ee67  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001ee6b  lea     edx, [r9+19h]; TokenInformationClass
0x18001ee6f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ee73  call    cs:__imp_GetTokenInformation
0x18001ee79  test    eax, eax
0x18001ee7b  jnz     short loc_18001EE94
0x18001ee7d  lea     edx, [rax+61h]; void *
0x18001ee80  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ee87  mov     rcx, [rbp+10h]; this
0x18001ee8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ee90  mov     ebx, eax
0x18001ee92  jmp     short loc_18001EE9E
0x18001ee94  cmp     [rbp+TokenInformation], ebx
0x18001ee97  jz      short loc_18001EE9E
0x18001ee99  mov     ebx, 80070005h
0x18001ee9e  lea     rcx, [rbp+TokenHandle]
0x18001eea2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001eea7  nop
0x18001eea8  lea     rcx, [rbp+ProcessHandle]
0x18001eeac  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001eeb1  mov     eax, ebx
0x18001eeb3  add     rsp, 38h
0x18001eeb7  pop     rbx
0x18001eeb8  pop     rbp
0x18001eeb9  retn
```
