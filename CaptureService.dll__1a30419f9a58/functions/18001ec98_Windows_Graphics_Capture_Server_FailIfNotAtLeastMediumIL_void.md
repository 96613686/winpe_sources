# Windows::Graphics::Capture::Server::FailIfNotAtLeastMediumIL(void)

- ea: `0x18001ec98`
- end: `0x18001ee07`
- name: `?FailIfNotAtLeastMediumIL@Server@Capture@Graphics@Windows@@YAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e5e4`

## callees

- `0x18000905c`
- `0x18000dec8`
- `0x180014800`
- `0x18001892c`
- `0x18001e5c4`
- `0x18001ec98`
- `0x18001f160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ecd3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ecd3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001eda0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001eda0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001edba`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001edba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ed10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ed73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ed10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ed73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ed4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ed4d`

## string_xrefs

- `0x18001ece1`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001ed30`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001ed84`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::FailIfNotAtLeastMediumIL(
        Windows::Graphics::Capture::Server *this)
{
  const char *v1; // r9
  int LastError; // eax
  DWORD v3; // eax
  unsigned int v4; // ebx
  PSID *v5; // rbx
  const char *v6; // r9
  __int64 v7; // rdx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  unsigned int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  PSID *v14; // [rsp+58h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+28h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp+30h] BYREF

  ProcessHandle = 0;
  Windows::Graphics::Capture::Server::GetClientProcessHandle(&ProcessHandle);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( !OpenProcessToken(ProcessHandle, 0x18u, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6F,
                  (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                  v1);
LABEL_7:
    v4 = LastError;
    goto LABEL_18;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    v3 = GetLastError();
    if ( v3 != 122 )
    {
      if ( v3 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x78,
                      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                      (const char *)v3,
                      ReturnLength);
        goto LABEL_7;
      }
    }
  }
  v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v14 = v5;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
  {
    v7 = 127;
LABEL_10:
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v7,
           (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
           v6);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    goto LABEL_18;
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
  if ( !SidSubAuthorityCount )
  {
    v7 = 129;
    goto LABEL_10;
  }
  SidSubAuthority = GetSidSubAuthority(*v5, (unsigned int)*SidSubAuthorityCount - 1);
  if ( !SidSubAuthority )
  {
    v7 = 131;
    goto LABEL_10;
  }
  if ( *SidSubAuthority >= 0x2000 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    v4 = 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    v4 = -2147024891;
  }
LABEL_18:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return v4;
}

```

## disassembly

```asm
0x18001ec98  push    rbp
0x18001ec9a  push    rbx
0x18001ec9b  mov     rbp, rsp
0x18001ec9e  sub     rsp, 38h
0x18001eca2  mov     [rbp+ProcessHandle], 0
0x18001ecaa  lea     rcx, [rbp+ProcessHandle]
0x18001ecae  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001ecb3  mov     [rbp+TokenHandle], 0
0x18001ecbb  xor     edx, edx
0x18001ecbd  lea     rcx, [rbp+TokenHandle]
0x18001ecc1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ecc6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001ecca  mov     edx, 18h; DesiredAccess
0x18001eccf  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18001ecd3  call    cs:__imp_OpenProcessToken
0x18001ecd9  test    eax, eax
0x18001ecdb  jnz     short loc_18001ECF2
0x18001ecdd  mov     rcx, [rbp+10h]; this
0x18001ece1  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ece8  lea     edx, [rax+6Fh]; void *
0x18001eceb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ecf0  jmp     short loc_18001ED41
0x18001ecf2  mov     [rbp+TokenInformationLength], 0
0x18001ecf9  lea     rax, [rbp+TokenInformationLength]
0x18001ecfd  mov     qword ptr [rsp+38h+ReturnLength], rax; unsigned int
0x18001ed02  xor     r9d, r9d; TokenInformationLength
0x18001ed05  xor     r8d, r8d; TokenInformation
0x18001ed08  lea     edx, [r9+19h]; TokenInformationClass
0x18001ed0c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ed10  call    cs:__imp_GetTokenInformation
0x18001ed16  test    eax, eax
0x18001ed18  jnz     short loc_18001ED48
0x18001ed1a  call    cs:__imp_GetLastError
0x18001ed20  cmp     eax, 7Ah ; 'z'
0x18001ed23  jz      short loc_18001ED48
0x18001ed25  test    eax, eax
0x18001ed27  jz      short loc_18001ED48
0x18001ed29  mov     rcx, [rbp+10h]; this
0x18001ed2d  mov     r9d, eax; char *
0x18001ed30  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ed37  mov     edx, 78h ; 'x'; void *
0x18001ed3c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ed41  mov     ebx, eax
0x18001ed43  jmp     loc_18001EDEB
0x18001ed48  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18001ed4b  xor     ecx, ecx; uFlags
0x18001ed4d  call    cs:__imp_LocalAlloc
0x18001ed53  mov     rbx, rax
0x18001ed56  mov     [rbp+arg_8], rax
0x18001ed5a  lea     rax, [rbp+TokenInformationLength]
0x18001ed5e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18001ed63  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001ed67  mov     r8, rbx; TokenInformation
0x18001ed6a  mov     edx, 19h; TokenInformationClass
0x18001ed6f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001ed73  call    cs:__imp_GetTokenInformation
0x18001ed79  test    eax, eax
0x18001ed7b  jnz     short loc_18001ED9D
0x18001ed7d  lea     edx, [rax+7Fh]; void *
0x18001ed80  mov     rcx, [rbp+10h]; this
0x18001ed84  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ed8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ed90  mov     ebx, eax
0x18001ed92  lea     rcx, [rbp+arg_8]
0x18001ed96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ed9b  jmp     short loc_18001EDEB
0x18001ed9d  mov     rcx, [rbx]; pSid
0x18001eda0  call    cs:__imp_GetSidSubAuthorityCount
0x18001eda6  test    rax, rax
0x18001eda9  jnz     short loc_18001EDB2
0x18001edab  mov     edx, 81h
0x18001edb0  jmp     short loc_18001ED80
0x18001edb2  movzx   edx, byte ptr [rax]
0x18001edb5  dec     edx; nSubAuthority
0x18001edb7  mov     rcx, [rbx]; pSid
0x18001edba  call    cs:__imp_GetSidSubAuthority
0x18001edc0  test    rax, rax
0x18001edc3  jnz     short loc_18001EDCC
0x18001edc5  mov     edx, 83h
0x18001edca  jmp     short loc_18001ED80
0x18001edcc  lea     rcx, [rbp+arg_8]
0x18001edd0  cmp     dword ptr [rax], 2000h
0x18001edd6  jnb     short loc_18001EDE4
0x18001edd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001eddd  mov     ebx, 80070005h
0x18001ede2  jmp     short loc_18001EDEB
0x18001ede4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ede9  xor     ebx, ebx
0x18001edeb  lea     rcx, [rbp+TokenHandle]
0x18001edef  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001edf4  nop
0x18001edf5  lea     rcx, [rbp+ProcessHandle]
0x18001edf9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001edfe  mov     eax, ebx
0x18001ee00  add     rsp, 38h
0x18001ee04  pop     rbx
0x18001ee05  pop     rbp
0x18001ee06  retn
```
