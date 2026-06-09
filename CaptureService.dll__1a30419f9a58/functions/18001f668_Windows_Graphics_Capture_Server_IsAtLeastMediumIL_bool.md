# Windows::Graphics::Capture::Server::IsAtLeastMediumIL(bool *)

- ea: `0x18001f668`
- end: `0x18001f7da`
- name: `?IsAtLeastMediumIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z`
- size: `370`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *__hidden this, bool *)`
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
- `0x18001f160`
- `0x18001f668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f6aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f6aa`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001f77b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001f77b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001f795`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001f795`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f6e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f74c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f6e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f74c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f726`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f726`

## string_xrefs

- `0x18001f6b8`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001f709`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001f75f`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::IsAtLeastMediumIL(
        Windows::Graphics::Capture::Server *this,
        bool *a2)
{
  const char *v3; // r9
  int LastError; // eax
  DWORD v5; // eax
  unsigned int v6; // ebx
  PSID *v7; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  unsigned int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  PSID *v17; // [rsp+60h] [rbp+30h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp+38h] BYREF

  *(_BYTE *)this = 0;
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
                  (void *)0xB8,
                  (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                  v3);
LABEL_7:
    v6 = LastError;
    goto LABEL_16;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    v5 = GetLastError();
    if ( v5 != 122 )
    {
      if ( v5 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0xC1,
                      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                      (const char *)v5,
                      ReturnLength);
        goto LABEL_7;
      }
    }
  }
  v7 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v17 = v7;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(*v7);
    if ( SidSubAuthorityCount )
    {
      SidSubAuthority = GetSidSubAuthority(*v7, (unsigned int)*SidSubAuthorityCount - 1);
      if ( SidSubAuthority )
      {
        *(_BYTE *)this = *SidSubAuthority >= 0x2000;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
        v6 = 0;
        goto LABEL_16;
      }
      v9 = 204;
    }
    else
    {
      v9 = 202;
    }
  }
  else
  {
    v9 = 200;
  }
  v6 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)v9,
         (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
         v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return v6;
}

```

## disassembly

```asm
0x18001f668  push    rbp
0x18001f66a  push    rbx
0x18001f66b  push    rdi
0x18001f66c  mov     rbp, rsp
0x18001f66f  sub     rsp, 30h
0x18001f673  mov     rdi, rcx
0x18001f676  mov     byte ptr [rcx], 0
0x18001f679  mov     [rbp+ProcessHandle], 0
0x18001f681  lea     rcx, [rbp+ProcessHandle]
0x18001f685  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001f68a  mov     [rbp+TokenHandle], 0
0x18001f692  xor     edx, edx
0x18001f694  lea     rcx, [rbp+TokenHandle]
0x18001f698  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001f69d  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001f6a1  mov     edx, 18h; DesiredAccess
0x18001f6a6  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x18001f6aa  call    cs:__imp_OpenProcessToken
0x18001f6b0  test    eax, eax
0x18001f6b2  jnz     short loc_18001F6CB
0x18001f6b4  mov     rcx, [rbp+18h]; this
0x18001f6b8  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f6bf  mov     edx, 0B8h; void *
0x18001f6c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f6c9  jmp     short loc_18001F71A
0x18001f6cb  mov     [rbp+TokenInformationLength], 0
0x18001f6d2  lea     rax, [rbp+TokenInformationLength]
0x18001f6d6  mov     qword ptr [rsp+30h+ReturnLength], rax; unsigned int
0x18001f6db  xor     r9d, r9d; TokenInformationLength
0x18001f6de  xor     r8d, r8d; TokenInformation
0x18001f6e1  lea     edx, [r9+19h]; TokenInformationClass
0x18001f6e5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f6e9  call    cs:__imp_GetTokenInformation
0x18001f6ef  test    eax, eax
0x18001f6f1  jnz     short loc_18001F721
0x18001f6f3  call    cs:__imp_GetLastError
0x18001f6f9  cmp     eax, 7Ah ; 'z'
0x18001f6fc  jz      short loc_18001F721
0x18001f6fe  test    eax, eax
0x18001f700  jz      short loc_18001F721
0x18001f702  mov     rcx, [rbp+18h]; this
0x18001f706  mov     r9d, eax; char *
0x18001f709  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f710  mov     edx, 0C1h; void *
0x18001f715  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f71a  mov     ebx, eax
0x18001f71c  jmp     loc_18001F7BD
0x18001f721  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18001f724  xor     ecx, ecx; uFlags
0x18001f726  call    cs:__imp_LocalAlloc
0x18001f72c  mov     rbx, rax
0x18001f72f  mov     [rbp+arg_10], rax
0x18001f733  lea     rax, [rbp+TokenInformationLength]
0x18001f737  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x18001f73c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001f740  mov     r8, rbx; TokenInformation
0x18001f743  mov     edx, 19h; TokenInformationClass
0x18001f748  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f74c  call    cs:__imp_GetTokenInformation
0x18001f752  test    eax, eax
0x18001f754  jnz     short loc_18001F778
0x18001f756  mov     edx, 0C8h; void *
0x18001f75b  mov     rcx, [rbp+18h]; this
0x18001f75f  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f766  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f76b  mov     ebx, eax
0x18001f76d  lea     rcx, [rbp+arg_10]
0x18001f771  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f776  jmp     short loc_18001F7BD
0x18001f778  mov     rcx, [rbx]; pSid
0x18001f77b  call    cs:__imp_GetSidSubAuthorityCount
0x18001f781  test    rax, rax
0x18001f784  jnz     short loc_18001F78D
0x18001f786  mov     edx, 0CAh
0x18001f78b  jmp     short loc_18001F75B
0x18001f78d  movzx   edx, byte ptr [rax]
0x18001f790  dec     edx; nSubAuthority
0x18001f792  mov     rcx, [rbx]; pSid
0x18001f795  call    cs:__imp_GetSidSubAuthority
0x18001f79b  test    rax, rax
0x18001f79e  jnz     short loc_18001F7A7
0x18001f7a0  mov     edx, 0CCh
0x18001f7a5  jmp     short loc_18001F75B
0x18001f7a7  cmp     dword ptr [rax], 2000h
0x18001f7ad  setnb   al
0x18001f7b0  mov     [rdi], al
0x18001f7b2  lea     rcx, [rbp+arg_10]
0x18001f7b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f7bb  xor     ebx, ebx
0x18001f7bd  lea     rcx, [rbp+TokenHandle]
0x18001f7c1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f7c6  nop
0x18001f7c7  lea     rcx, [rbp+ProcessHandle]
0x18001f7cb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f7d0  mov     eax, ebx
0x18001f7d2  add     rsp, 30h
0x18001f7d6  pop     rdi
0x18001f7d7  pop     rbx
0x18001f7d8  pop     rbp
0x18001f7d9  retn
```
