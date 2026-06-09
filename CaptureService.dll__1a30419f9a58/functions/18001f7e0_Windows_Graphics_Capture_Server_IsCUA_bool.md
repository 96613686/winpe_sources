# Windows::Graphics::Capture::Server::IsCUA(bool *)

- ea: `0x18001f7e0`
- end: `0x18001fa41`
- name: `?IsCUA@Server@Capture@Graphics@Windows@@YAJPEA_N@Z`
- size: `609`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e5e4`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x18000905c`
- `0x18000dec8`
- `0x180014800`
- `0x18001892c`
- `0x18001e1bc`
- `0x18001f160`
- `0x18001f7e0`
- `0x18001fc58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f83a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f83a`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18001f85c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18001f85c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001f9b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001f9b8`
- `ntdll!RtlInitUnicodeString` at `0x18001f93a`
- `ntdll!RtlInitUnicodeString` at `0x18001f93a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18001f96d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18001f96d`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18001f8f0`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18001f8f0`

## string_xrefs

- `0x18001f87e`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001f981`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001f9fc`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001f92f`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::IsCUA(Windows::Graphics::Capture::Server *this, bool *a2)
{
  const char *v3; // r9
  unsigned int PackageFullNameFromToken; // eax
  unsigned int ApplicationCapabilities; // ebx
  int LastError; // eax
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v10; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v13; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v14; // [rsp+78h] [rbp-88h]
  _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  UINT32 packageFullNameLength[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pSid2[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v18[80]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR packageFullName[128]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
                  (void *)0x128,
                  (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                  v3);
    goto LABEL_21;
  }
  packageFullNameLength[0] = 128;
  PackageFullNameFromToken = GetPackageFullNameFromToken(TokenHandle, packageFullNameLength, packageFullName);
  if ( PackageFullNameFromToken != 15700 )
  {
    if ( PackageFullNameFromToken )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x133,
                    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                    (const char *)PackageFullNameFromToken,
                    v10);
LABEL_21:
      ApplicationCapabilities = LastError;
      goto LABEL_22;
    }
    v13 = 0;
    v14 = 0;
    *(_QWORD *)&DestinationString.Length = &v13;
    LODWORD(DestinationString.Buffer) = 0;
    BYTE4(DestinationString.Buffer) = 1;
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v13);
    ApplicationCapabilities = QueryApplicationCapabilitiesEx(packageFullName, 0, 0, 0);
    if ( BYTE4(DestinationString.Buffer) )
      *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 8LL) = LODWORD(DestinationString.Buffer);
    if ( (int)(ApplicationCapabilities + 0x80000000) < 0 || ApplicationCapabilities == -2147024444 )
    {
      if ( v14 )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"Microsoft.appCategory.chatAgent_8wekyb3d8bbwe");
        memset_0(pSid2, 0, 0x44u);
        memset_0(v18, 0, 0x44u);
        v7 = RtlDeriveCapabilitySidsFromName(&DestinationString, v18, pSid2);
        if ( v7 < 0 )
        {
          ApplicationCapabilities = wil::details::in1diag3::Return_NtStatus(
                                      retaddr,
                                      (void *)0x158,
                                      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
                                      (const char *)(unsigned int)v7,
                                      0);
          goto LABEL_13;
        }
        v8 = 0;
        if ( v14 )
        {
          while ( !EqualSid(*(PSID *)(v13 + 8LL * v8), pSid2) )
          {
            if ( ++v8 >= v14 )
              goto LABEL_19;
          }
          *(_BYTE *)this = 1;
        }
      }
LABEL_19:
      wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v13);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
      return 0;
    }
LABEL_13:
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v13);
    goto LABEL_22;
  }
  ApplicationCapabilities = 0;
LABEL_22:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
  return ApplicationCapabilities;
}

```

## disassembly

```asm
0x18001f7e0  push    rbp
0x18001f7e2  push    rbx
0x18001f7e3  push    rsi
0x18001f7e4  push    rdi
0x18001f7e5  lea     rbp, [rsp-158h]
0x18001f7ed  sub     rsp, 258h
0x18001f7f4  mov     rax, cs:__security_cookie
0x18001f7fb  xor     rax, rsp
0x18001f7fe  mov     [rbp+170h+var_30], rax
0x18001f805  mov     rdi, rcx
0x18001f808  xor     esi, esi
0x18001f80a  mov     [rcx], sil
0x18001f80d  mov     [rsp+270h+ProcessHandle], rsi
0x18001f812  lea     rcx, [rsp+270h+ProcessHandle]
0x18001f817  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001f81c  mov     [rsp+270h+TokenHandle], rsi
0x18001f821  xor     edx, edx
0x18001f823  lea     rcx, [rsp+270h+TokenHandle]
0x18001f828  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001f82d  lea     r8, [rsp+270h+TokenHandle]; TokenHandle
0x18001f832  lea     edx, [rsi+18h]; DesiredAccess
0x18001f835  mov     rcx, [rsp+270h+ProcessHandle]; ProcessHandle
0x18001f83a  call    cs:__imp_OpenProcessToken
0x18001f840  test    eax, eax
0x18001f842  jz      loc_18001F9F5
0x18001f848  mov     [rbp+170h+packageFullNameLength], 80h
0x18001f84f  lea     r8, [rbp+170h+packageFullName]; packageFullName
0x18001f853  lea     rdx, [rbp+170h+packageFullNameLength]; packageFullNameLength
0x18001f857  mov     rcx, [rsp+270h+TokenHandle]; token
0x18001f85c  call    cs:__imp_GetPackageFullNameFromToken
0x18001f862  cmp     eax, 3D54h
0x18001f867  jnz     short loc_18001F870
0x18001f869  mov     ebx, esi
0x18001f86b  jmp     loc_18001FA0F
0x18001f870  test    eax, eax
0x18001f872  jz      short loc_18001F894
0x18001f874  mov     rcx, [rbp+178h]; this
0x18001f87b  mov     r9d, eax; char *
0x18001f87e  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f885  mov     edx, 133h; void *
0x18001f88a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f88f  jmp     loc_18001FA0D
0x18001f894  mov     [rsp+270h+var_200], rsi
0x18001f899  mov     [rsp+270h+var_1F8], rsi
0x18001f89e  lea     rax, [rsp+270h+var_200]
0x18001f8a3  mov     qword ptr [rbp+170h+DestinationString.Length], rax
0x18001f8a7  mov     dword ptr [rbp+170h+DestinationString.Buffer], esi
0x18001f8aa  mov     byte ptr [rbp+170h+DestinationString.Buffer+4], 1
0x18001f8ae  lea     rcx, [rsp+270h+var_200]
0x18001f8b3  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18001f8b8  mov     [rsp+270h+var_220], rsi
0x18001f8bd  mov     [rsp+270h+var_228], rsi
0x18001f8c2  mov     [rsp+270h+var_230], rsi
0x18001f8c7  mov     [rsp+270h+var_238], rsi
0x18001f8cc  lea     rax, [rbp+170h+DestinationString.Buffer]
0x18001f8d0  mov     [rsp+270h+var_240], rax
0x18001f8d5  lea     rax, [rsp+270h+var_200]
0x18001f8da  mov     [rsp+270h+var_248], rax
0x18001f8df  mov     qword ptr [rsp+270h+var_250], rsi; int
0x18001f8e4  xor     r9d, r9d
0x18001f8e7  xor     r8d, r8d
0x18001f8ea  xor     edx, edx
0x18001f8ec  lea     rcx, [rbp+170h+packageFullName]
0x18001f8f0  call    cs:__imp_QueryApplicationCapabilitiesEx
0x18001f8f6  mov     ebx, eax
0x18001f8f8  cmp     byte ptr [rbp+170h+DestinationString.Buffer+4], sil
0x18001f8fc  jz      short loc_18001F909
0x18001f8fe  mov     ecx, dword ptr [rbp+170h+DestinationString.Buffer]
0x18001f901  mov     rax, qword ptr [rbp+170h+DestinationString.Length]
0x18001f905  mov     [rax+8], rcx
0x18001f909  mov     ecx, 80000000h
0x18001f90e  lea     eax, [rbx+rcx]
0x18001f911  test    ecx, eax
0x18001f913  jnz     short loc_18001F91D
0x18001f915  cmp     ebx, 800701C4h
0x18001f91b  jnz     short loc_18001F994
0x18001f91d  cmp     [rsp+270h+var_1F8], rsi
0x18001f922  jbe     loc_18001F9D2
0x18001f928  xorps   xmm0, xmm0
0x18001f92b  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x18001f92f  lea     rdx, SourceString; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x18001f936  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x18001f93a  call    cs:__imp_RtlInitUnicodeString
0x18001f940  mov     ebx, 44h ; 'D'
0x18001f945  mov     r8d, ebx; Size
0x18001f948  xor     edx, edx; Val
0x18001f94a  lea     rcx, [rbp+170h+pSid2]; void *
0x18001f94e  call    memset_0
0x18001f953  mov     r8d, ebx; Size
0x18001f956  xor     edx, edx; Val
0x18001f958  lea     rcx, [rbp+170h+var_180]; void *
0x18001f95c  call    memset_0
0x18001f961  lea     r8, [rbp+170h+pSid2]
0x18001f965  lea     rdx, [rbp+170h+var_180]
0x18001f969  lea     rcx, [rbp+170h+DestinationString]
0x18001f96d  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18001f973  test    eax, eax
0x18001f975  jns     short loc_18001F9A0
0x18001f977  mov     rcx, [rbp+178h]; this
0x18001f97e  mov     r9d, eax; char *
0x18001f981  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f988  mov     edx, 158h; void *
0x18001f98d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f992  mov     ebx, eax
0x18001f994  lea     rcx, [rsp+270h+var_200]
0x18001f999  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18001f99e  jmp     short loc_18001FA0F
0x18001f9a0  mov     ebx, esi
0x18001f9a2  cmp     [rsp+270h+var_1F8], rsi
0x18001f9a7  jbe     short loc_18001F9D2
0x18001f9a9  mov     eax, ebx
0x18001f9ab  lea     rdx, [rbp+170h+pSid2]; pSid2
0x18001f9af  mov     rcx, [rsp+270h+var_200]
0x18001f9b4  mov     rcx, [rcx+rax*8]; pSid1
0x18001f9b8  call    cs:__imp_EqualSid
0x18001f9be  test    eax, eax
0x18001f9c0  jnz     short loc_18001F9CF
0x18001f9c2  inc     ebx
0x18001f9c4  mov     eax, ebx
0x18001f9c6  cmp     rax, [rsp+270h+var_1F8]
0x18001f9cb  jb      short loc_18001F9A9
0x18001f9cd  jmp     short loc_18001F9D2
0x18001f9cf  mov     byte ptr [rdi], 1
0x18001f9d2  lea     rcx, [rsp+270h+var_200]
0x18001f9d7  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18001f9dc  lea     rcx, [rsp+270h+TokenHandle]
0x18001f9e1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f9e6  nop
0x18001f9e7  lea     rcx, [rsp+270h+ProcessHandle]
0x18001f9ec  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f9f1  xor     eax, eax
0x18001f9f3  jmp     short loc_18001FA26
0x18001f9f5  mov     rcx, [rbp+178h]; this
0x18001f9fc  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001fa03  mov     edx, 128h; void *
0x18001fa08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fa0d  mov     ebx, eax
0x18001fa0f  lea     rcx, [rsp+270h+TokenHandle]
0x18001fa14  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fa19  nop
0x18001fa1a  lea     rcx, [rsp+270h+ProcessHandle]
0x18001fa1f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fa24  mov     eax, ebx
0x18001fa26  mov     rcx, [rbp+170h+var_30]
0x18001fa2d  xor     rcx, rsp; StackCookie
0x18001fa30  call    __security_check_cookie
0x18001fa35  add     rsp, 258h
0x18001fa3c  pop     rdi
0x18001fa3d  pop     rsi
0x18001fa3e  pop     rbx
0x18001fa3f  pop     rbp
0x18001fa40  retn
```
