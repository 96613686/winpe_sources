# UiaManagerCrossMachineStub::GetPlatformSpecificSecurityAttributes(uint,_SECURITY_ATTRIBUTES *)

- ea: `0x1800294d0`
- end: `0x180029718`
- name: `?GetPlatformSpecificSecurityAttributes@UiaManagerCrossMachineStub@@AEAAJIPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineStub *this, DWORD, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017600`

## callees

- `0x180010f78`
- `0x180012120`
- `0x180016c74`
- `0x1800294d0`
- `0x180029720`
- `0x18002991c`
- `0x18002a514`
- `0x18002dfd8`
- `0x180031540`
- `0x180043680`
- `0x18005fde0`
- `0x1800684e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002952c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002952c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800294fc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800294fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029585`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029585`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029653`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029653`

## string_xrefs

- `0x18002953e`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x18002958f`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x18002966c`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180029705`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180029665`: `ConvertStringSecurityDescriptorToSecurityDescriptor, connecting to server`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaManagerCrossMachineStub::GetPlatformSpecificSecurityAttributes(
        UiaManagerCrossMachineStub *this,
        DWORD a2,
        struct _SECURITY_ATTRIBUTES *a3)
{
  HANDLE v4; // rbx
  BOOL v5; // eax
  const char *v6; // r9
  const char *v7; // r9
  __int64 v8; // rdx
  void *v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  const char *v12; // r9
  __int64 result; // rax
  int v14; // eax
  const char *ReturnLength; // [rsp+20h] [rbp-A8h]
  DWORD v16; // [rsp+30h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-90h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-80h] BYREF
  HANDLE v20; // [rsp+50h] [rbp-78h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+58h] [rbp-70h] BYREF
  __int128 v22; // [rsp+68h] [rbp-60h]
  _BYTE v23[32]; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v24[32]; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = OpenProcess(0x400u, 0, a2);
  v20 = v4;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  v5 = OpenProcessToken(v4, 8u, &TokenHandle);
  try
  {
    if ( !v5 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        v6);
    TokenInformation = 0;
    v16 = 0;
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v16) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
        v7);
    SecurityDescriptor = 0;
    if ( TokenInformation )
    {
      BasicUiaUtils::TryGetAppContainerSid(v23, TokenHandle);
      v9 = (void *)std::operator+<unsigned short>(v24, v8, v23);
      v10 = std::wstring::_Append<unsigned short>(v9);
      *(_OWORD *)StringSecurityDescriptor = 0;
      v22 = 0;
      *(_OWORD *)StringSecurityDescriptor = *(_OWORD *)v10;
      v22 = *(_OWORD *)(v10 + 16);
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
      *(_WORD *)v10 = 0;
      std::wstring::_Tidy_deallocate(v24);
      v11 = (const WCHAR *)StringSecurityDescriptor;
      if ( *((_QWORD *)&v22 + 1) > 7u )
        v11 = StringSecurityDescriptor[0];
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v11, 1u, &SecurityDescriptor, 0) )
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x262,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
          "ConvertStringSecurityDescriptorToSecurityDescriptor, connecting to server",
          ReturnLength);
      std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
      std::wstring::_Tidy_deallocate(v23);
    }
    else
    {
      v14 = BasicUiaUtils::CreateSecurityDescriptorForProcess(TokenHandle, &SecurityDescriptor);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x267,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
          (const char *)(unsigned int)v14,
          (int)ReturnLength);
    }
    a3->nLength = 24;
    a3->lpSecurityDescriptor = SecurityDescriptor;
    a3->bInheritHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x271,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800294d0  mov     [rsp+arg_0], rbx
0x1800294d5  push    rdi
0x1800294d6  sub     rsp, 0C0h
0x1800294dd  mov     rax, cs:__security_cookie
0x1800294e4  xor     rax, rsp
0x1800294e7  mov     [rsp+0C8h+var_10], rax
0x1800294ef  mov     rdi, r8
0x1800294f2  mov     r8d, edx; dwProcessId
0x1800294f5  xor     edx, edx; bInheritHandle
0x1800294f7  mov     ecx, 400h; dwDesiredAccess
0x1800294fc  call    cs:__imp_OpenProcess
0x180029502  mov     rbx, rax
0x180029505  mov     [rsp+0C8h+var_78], rax
0x18002950a  mov     [rsp+0C8h+TokenHandle], 0
0x180029513  xor     edx, edx
0x180029515  lea     rcx, [rsp+0C8h+TokenHandle]
0x18002951a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002951f  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180029524  mov     edx, 8; DesiredAccess
0x180029529  mov     rcx, rbx; ProcessHandle
0x18002952c  call    cs:__imp_OpenProcessToken
0x180029532  mov     rcx, [rsp+0C8h]; this
0x18002953a  test    eax, eax
0x18002953c  jnz     short loc_18002954F
0x18002953e  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180029545  mov     edx, 250h; void *
0x18002954a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002954f  mov     [rsp+0C8h+TokenInformation], 0
0x180029557  mov     [rsp+0C8h+var_98], 0
0x18002955f  mov     rbx, [rsp+0C8h]
0x180029567  lea     rax, [rsp+0C8h+var_98]
0x18002956c  mov     [rsp+0C8h+ReturnLength], rax; int
0x180029571  mov     r9d, 4; TokenInformationLength
0x180029577  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18002957c  lea     edx, [r9+19h]; TokenInformationClass
0x180029580  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180029585  call    cs:__imp_GetTokenInformation
0x18002958b  test    eax, eax
0x18002958d  jnz     short loc_1800295A3
0x18002958f  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180029596  mov     edx, 255h; void *
0x18002959b  mov     rcx, rbx; this
0x18002959e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800295a3  mov     [rsp+0C8h+SecurityDescriptor], 0
0x1800295ac  cmp     [rsp+0C8h+TokenInformation], 0
0x1800295b1  jz      loc_1800296E7
0x1800295b7  mov     rdx, [rsp+0C8h+TokenHandle]
0x1800295bc  lea     rcx, [rsp+0C8h+var_50]
0x1800295c1  call    ?TryGetAppContainerSid@BasicUiaUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; BasicUiaUtils::TryGetAppContainerSid(void *)
0x1800295c6  nop
0x1800295c7  lea     r8, [rsp+0C8h+var_50]
0x1800295cc  lea     rcx, [rsp+0C8h+var_30]
0x1800295d4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800295d9  nop
0x1800295da  mov     ebx, 1
0x1800295df  mov     r8d, ebx
0x1800295e2  lea     rdx, asc_1800A63B8; ")"
0x1800295e9  mov     rcx, rax; Src
0x1800295ec  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800295f1  mov     rcx, rax
0x1800295f4  xorps   xmm0, xmm0
0x1800295f7  movups  xmmword ptr [rsp+0C8h+StringSecurityDescriptor], xmm0
0x1800295fc  xorps   xmm1, xmm1
0x1800295ff  movdqu  [rsp+0C8h+var_60], xmm1
0x180029605  movups  xmm0, xmmword ptr [rax]
0x180029608  movups  xmmword ptr [rsp+0C8h+StringSecurityDescriptor], xmm0
0x18002960d  movups  xmm1, xmmword ptr [rax+10h]
0x180029611  movups  [rsp+0C8h+var_60], xmm1
0x180029616  mov     qword ptr [rax+10h], 0
0x18002961e  mov     qword ptr [rax+18h], 7
0x180029626  xor     eax, eax
0x180029628  mov     [rcx], ax
0x18002962b  lea     rcx, [rsp+0C8h+var_30]
0x180029633  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029638  lea     rcx, [rsp+0C8h+StringSecurityDescriptor]
0x18002963d  cmp     qword ptr [rsp+0C8h+var_60+8], 7
0x180029643  cmova   rcx, [rsp+0C8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180029649  xor     r9d, r9d; SecurityDescriptorSize
0x18002964c  lea     r8, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x180029651  mov     edx, ebx; StringSDRevision
0x180029653  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180029659  test    eax, eax
0x18002965b  jnz     short loc_18002967E
0x18002965d  mov     rcx, [rsp+0C8h]; this
0x180029665  lea     r9, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x18002966c  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180029673  mov     edx, 262h; void *
0x180029678  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002967e  lea     rcx, [rsp+0C8h+StringSecurityDescriptor]
0x180029683  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029688  nop
0x180029689  lea     rcx, [rsp+0C8h+var_50]
0x18002968e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029693  mov     dword ptr [rdi], 18h
0x180029699  mov     rax, [rsp+0C8h+SecurityDescriptor]
0x18002969e  mov     [rdi+8], rax
0x1800296a2  mov     dword ptr [rdi+10h], 0
0x1800296a9  lea     rcx, [rsp+0C8h+TokenHandle]
0x1800296ae  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800296b3  nop
0x1800296b4  lea     rcx, [rsp+0C8h+var_78]
0x1800296b9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800296be  xor     eax, eax
0x1800296c0  jmp     short loc_1800296C6
0x1800296c2  mov     eax, [rsp+0C8h+var_98]
0x1800296c6  mov     rcx, [rsp+0C8h+var_10]
0x1800296ce  xor     rcx, rsp; StackCookie
0x1800296d1  call    __security_check_cookie
0x1800296d6  mov     rbx, [rsp+0C8h+arg_0]
0x1800296de  add     rsp, 0C0h
0x1800296e5  pop     rdi
0x1800296e6  retn
0x1800296e7  lea     rdx, [rsp+0C8h+SecurityDescriptor]; void **
0x1800296ec  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x1800296f1  call    ?CreateSecurityDescriptorForProcess@BasicUiaUtils@@SAJPEAXPEAPEAX@Z; BasicUiaUtils::CreateSecurityDescriptorForProcess(void *,void * *)
0x1800296f6  mov     rcx, [rsp+0C8h]; this
0x1800296fe  test    eax, eax
0x180029700  jns     short loc_180029693
0x180029702  mov     r9d, eax; char *
0x180029705  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18002970c  mov     edx, 267h; void *
0x180029711  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
