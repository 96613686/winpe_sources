# Windows::Graphics::Capture::Server::IsAppSilo(bool *)

- ea: `0x18001f59c`
- end: `0x18001f661`
- name: `?IsAppSilo@Server@Capture@Graphics@Windows@@YAJPEA_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e5e4`

## callees

- `0x18000905c`
- `0x18000dec8`
- `0x18001892c`
- `0x18001f160`
- `0x18001f59c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f5dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f5dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f617`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f617`

## string_xrefs

- `0x18001f626`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Graphics::Capture::Server::IsAppSilo(Windows::Graphics::Capture::Server *this, bool *a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  int TokenInformation; // [rsp+50h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+28h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp+30h] BYREF

  *(_BYTE *)this = 0;
  ProcessHandle = 0;
  Windows::Graphics::Capture::Server::GetClientProcessHandle(&ProcessHandle);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( OpenProcessToken(ProcessHandle, 0x18u, &TokenHandle) )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(
           TokenHandle,
           TokenAppContainerNumber|TokenAuditPolicy,
           &TokenInformation,
           4u,
           &ReturnLength) )
    {
      *(_BYTE *)this = TokenInformation != 0;
      LastError = 0;
      goto LABEL_7;
    }
    v4 = 152;
  }
  else
  {
    v4 = 148;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v4,
                (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                v3);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return LastError;
}

```

## disassembly

```asm
0x18001f59c  push    rbp
0x18001f59e  push    rbx
0x18001f59f  mov     rbp, rsp
0x18001f5a2  sub     rsp, 38h
0x18001f5a6  mov     rbx, rcx
0x18001f5a9  mov     byte ptr [rcx], 0
0x18001f5ac  mov     [rbp+ProcessHandle], 0
0x18001f5b4  lea     rcx, [rbp+ProcessHandle]
0x18001f5b8  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001f5bd  mov     [rbp+TokenHandle], 0
0x18001f5c5  xor     edx, edx
0x18001f5c7  lea     rcx, [rbp+TokenHandle]
0x18001f5cb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001f5d0  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001f5d4  mov     edx, 18h; DesiredAccess
0x18001f5d9  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18001f5dd  call    cs:__imp_OpenProcessToken
0x18001f5e3  test    eax, eax
0x18001f5e5  jnz     short loc_18001F5EE
0x18001f5e7  mov     edx, 94h
0x18001f5ec  jmp     short loc_18001F626
0x18001f5ee  mov     [rbp+TokenInformation], 0
0x18001f5f5  mov     [rbp+arg_8], 0
0x18001f5fc  lea     rax, [rbp+arg_8]
0x18001f600  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001f605  mov     r9d, 4; TokenInformationLength
0x18001f60b  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001f60f  lea     edx, [r9+2Ch]; TokenInformationClass
0x18001f613  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f617  call    cs:__imp_GetTokenInformation
0x18001f61d  test    eax, eax
0x18001f61f  jnz     short loc_18001F63A
0x18001f621  mov     edx, 98h; void *
0x18001f626  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f62d  mov     rcx, [rbp+10h]; this
0x18001f631  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f636  mov     ebx, eax
0x18001f638  jmp     short loc_18001F645
0x18001f63a  cmp     [rbp+TokenInformation], 0
0x18001f63e  setnbe  al
0x18001f641  mov     [rbx], al
0x18001f643  xor     ebx, ebx
0x18001f645  lea     rcx, [rbp+TokenHandle]
0x18001f649  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f64e  nop
0x18001f64f  lea     rcx, [rbp+ProcessHandle]
0x18001f653  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f658  mov     eax, ebx
0x18001f65a  add     rsp, 38h
0x18001f65e  pop     rbx
0x18001f65f  pop     rbp
0x18001f660  retn
```
