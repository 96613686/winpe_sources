# Windows::Graphics::Capture::Server::IsAppContainer(bool *)

- ea: `0x18001f4d0`
- end: `0x18001f595`
- name: `?IsAppContainer@Server@Capture@Graphics@Windows@@YAJPEA_N@Z`
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
- `0x18001f4d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f511`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f511`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f54b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f54b`

## string_xrefs

- `0x18001f55a`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::IsAppContainer(
        Windows::Graphics::Capture::Server *this,
        bool *a2)
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
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      *(_BYTE *)this = TokenInformation != 0;
      LastError = 0;
      goto LABEL_7;
    }
    v4 = 170;
  }
  else
  {
    v4 = 166;
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
0x18001f4d0  push    rbp
0x18001f4d2  push    rbx
0x18001f4d3  mov     rbp, rsp
0x18001f4d6  sub     rsp, 38h
0x18001f4da  mov     rbx, rcx
0x18001f4dd  mov     byte ptr [rcx], 0
0x18001f4e0  mov     [rbp+ProcessHandle], 0
0x18001f4e8  lea     rcx, [rbp+ProcessHandle]
0x18001f4ec  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001f4f1  mov     [rbp+TokenHandle], 0
0x18001f4f9  xor     edx, edx
0x18001f4fb  lea     rcx, [rbp+TokenHandle]
0x18001f4ff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001f504  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001f508  mov     edx, 18h; DesiredAccess
0x18001f50d  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18001f511  call    cs:__imp_OpenProcessToken
0x18001f517  test    eax, eax
0x18001f519  jnz     short loc_18001F522
0x18001f51b  mov     edx, 0A6h
0x18001f520  jmp     short loc_18001F55A
0x18001f522  mov     [rbp+TokenInformation], 0
0x18001f529  mov     [rbp+arg_8], 0
0x18001f530  lea     rax, [rbp+arg_8]
0x18001f534  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001f539  mov     r9d, 4; TokenInformationLength
0x18001f53f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001f543  lea     edx, [r9+19h]; TokenInformationClass
0x18001f547  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f54b  call    cs:__imp_GetTokenInformation
0x18001f551  test    eax, eax
0x18001f553  jnz     short loc_18001F56E
0x18001f555  mov     edx, 0AAh; void *
0x18001f55a  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f561  mov     rcx, [rbp+10h]; this
0x18001f565  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f56a  mov     ebx, eax
0x18001f56c  jmp     short loc_18001F579
0x18001f56e  cmp     [rbp+TokenInformation], 0
0x18001f572  setnbe  al
0x18001f575  mov     [rbx], al
0x18001f577  xor     ebx, ebx
0x18001f579  lea     rcx, [rbp+TokenHandle]
0x18001f57d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f582  nop
0x18001f583  lea     rcx, [rbp+ProcessHandle]
0x18001f587  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f58c  mov     eax, ebx
0x18001f58e  add     rsp, 38h
0x18001f592  pop     rbx
0x18001f593  pop     rbp
0x18001f594  retn
```
