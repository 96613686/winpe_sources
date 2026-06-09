# TokenUtility::GetUserToken(TokenQueryType,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint)

- ea: `0x180031a9c`
- end: `0x180031d1b`
- name: `?GetUserToken@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4TokenQueryType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z`
- size: `639`
- prototype: `void *__fastcall(__int64, void *, int, __int64, ULONG SessionId)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012998`
- `0x180012a2c`
- `0x180012ac0`

## callees

- `0x180002d40`
- `0x18000f8a8`
- `0x18001255c`
- `0x18001c60c`
- `0x18001cf40`
- `0x18001d058`
- `0x18001d0a0`
- `0x180023264`
- `0x1800291d0`
- `0x180030a38`
- `0x180031a9c`
- `0x180031d24`
- `0x180031f84`
- `0x1800320a4`
- `0x18003286c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031bca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031bb5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031cd5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031cd5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031c90`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180031c90`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031c25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031c25`

## string_xrefs

- `0x180031b79`: `ImpersonateUser failed!`
- `0x180031ae5`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180031c9a`: `DuplicateTokenEx failed!`
- `0x180031bd4`: `OpenThreadToken failed!`
- `0x180031c34`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed!`
- `0x180031b22`: `ImpersonateActiveUser failed!`
- `0x180031b5e`: `ImpersonateActiveUser failed!`
- `0x180031b0a`: `ImpersonateUser (Session Id) failed!`
- `0x180031b3d`: `ImpersonateUser (SID) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall TokenUtility::GetUserToken(__int64 a1, void *a2, int a3, __int64 a4, ULONG SessionId)
{
  int v8; // ebx
  unsigned int v9; // eax
  unsigned int active; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  HANDLE CurrentThread; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  const WCHAR *v17; // rcx
  BOOL v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rcx
  const char *phNewToken; // [rsp+28h] [rbp-39h]
  const char *phNewTokena; // [rsp+28h] [rbp-39h]
  const char *phNewTokenb; // [rsp+28h] [rbp-39h]
  void *TokenHandle; // [rsp+30h] [rbp-31h] BYREF
  void *v26; // [rsp+38h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-21h] BYREF
  char v28; // [rsp+49h] [rbp-18h]
  ULONG SecurityDescriptorSize[3]; // [rsp+4Ch] [rbp-15h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+58h] [rbp-9h] BYREF
  LPCWSTR StringSecurityDescriptor[4]; // [rsp+70h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  SecurityDescriptor = a2;
  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
    {
      v8 = a3 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          v9 = PrintCore::UserImpersonationHelpers::ImpersonateUser(SessionId);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
            (const char *)v9,
            (int)"ImpersonateUser (Session Id) failed!",
            phNewToken);
        }
      }
      else
      {
        active = PrintCore::UserImpersonationHelpers::ImpersonateActiveUser();
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
          (const char *)active,
          (int)"ImpersonateActiveUser failed!",
          phNewToken);
      }
    }
    else
    {
      v11 = PrintCore::UserImpersonationHelpers::ImpersonateUser(a4);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
        (const char *)v11,
        (int)"ImpersonateUser (SID) failed!",
        phNewToken);
    }
  }
  else if ( a3 )
  {
    if ( a3 == 1 )
    {
      v12 = PrintCore::UserImpersonationHelpers::ImpersonateActiveUser();
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
        (const char *)v12,
        (int)"ImpersonateActiveUser failed!",
        phNewToken);
    }
  }
  else
  {
    v13 = PrintCore::UserImpersonationHelpers::ImpersonateUser(a4);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
      (const char *)v13,
      (int)"ImpersonateUser failed!",
      phNewToken);
  }
  v28 = 1;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  v15 = OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0xEE,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v15,
    (int)"OpenThreadToken failed!",
    phNewToken);
  TokenUtility::_CreateAllAccessDaclForUserAndWorker(v16, StringSecurityDescriptor, TokenHandle);
  SecurityDescriptorSize[0] = 0;
  SecurityDescriptor = 0;
  v17 = (const WCHAR *)StringSecurityDescriptor;
  if ( StringSecurityDescriptor[3] > (LPCWSTR)7 )
    v17 = StringSecurityDescriptor[0];
  v18 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v17, 1u, &SecurityDescriptor, SecurityDescriptorSize);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xF5,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v18,
    (bool)"ConvertStringSecurityDescriptorToSecurityDescriptor failed!",
    phNewTokena);
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_QWORD *)&TokenAttributes.bInheritHandle = 1;
  TokenAttributes.lpSecurityDescriptor = SecurityDescriptor;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v26,
    0);
  v19 = DuplicateTokenEx(TokenHandle, 0xEu, &TokenAttributes, SecurityImpersonation, TokenImpersonation, &v26);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x101,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v19,
    (int)"DuplicateTokenEx failed!",
    phNewTokenb);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  RevertToSelf();
  TokenUtility::_DuplicateHandle(v20, a2, v26, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
  return a2;
}

```

## disassembly

```asm
0x180031a9c  mov     [rsp-8+arg_0], rbx
0x180031aa1  mov     [rsp-8+arg_10], rsi
0x180031aa6  push    rbp
0x180031aa7  push    rdi
0x180031aa8  push    r15
0x180031aaa  lea     rbp, [rsp-3Fh]
0x180031aaf  sub     rsp, 0A0h
0x180031ab6  mov     rax, cs:__security_cookie
0x180031abd  xor     rax, rsp
0x180031ac0  mov     [rbp+4Fh+var_20], rax
0x180031ac4  mov     rdi, r9
0x180031ac7  mov     ebx, r8d
0x180031aca  mov     rsi, rdx
0x180031acd  mov     [rbp+4Fh+SecurityDescriptor], rdx
0x180031ad1  mov     [rbp+4Fh+var_78], 0
0x180031ad9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180031ae0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180031ae5  lea     r15, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180031aec  test    al, al
0x180031aee  jz      short loc_180031B50
0x180031af0  test    ebx, ebx
0x180031af2  jz      short loc_180031B35
0x180031af4  sub     ebx, 1
0x180031af7  jz      short loc_180031B1D
0x180031af9  cmp     ebx, 1
0x180031afc  jnz     loc_180031B99
0x180031b02  mov     ecx, [rbp+4Fh+SessionId]; SessionId
0x180031b05  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJK@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(ulong)
0x180031b0a  lea     rdx, aImpersonateuse_0; "ImpersonateUser (Session Id) failed!"
0x180031b11  mov     qword ptr [rsp+0B0h+TokenType], rdx
0x180031b16  mov     edx, 0D7h
0x180031b1b  jmp     short loc_180031B8A
0x180031b1d  call    ?ImpersonateActiveUser@UserImpersonationHelpers@PrintCore@@SAJXZ; PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)
0x180031b22  lea     rdx, aImpersonateact; "ImpersonateActiveUser failed!"
0x180031b29  mov     qword ptr [rsp+0B0h+TokenType], rdx
0x180031b2e  mov     edx, 0D4h
0x180031b33  jmp     short loc_180031B8A
0x180031b35  mov     rcx, rdi
0x180031b38  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180031b3d  lea     rdx, aImpersonateuse; "ImpersonateUser (SID) failed!"
0x180031b44  mov     qword ptr [rsp+0B0h+TokenType], rdx
0x180031b49  mov     edx, 0D1h
0x180031b4e  jmp     short loc_180031B8A
0x180031b50  test    ebx, ebx
0x180031b52  jz      short loc_180031B71
0x180031b54  cmp     ebx, 1
0x180031b57  jnz     short loc_180031B99
0x180031b59  call    ?ImpersonateActiveUser@UserImpersonationHelpers@PrintCore@@SAJXZ; PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)
0x180031b5e  lea     rdx, aImpersonateact; "ImpersonateActiveUser failed!"
0x180031b65  mov     qword ptr [rsp+0B0h+TokenType], rdx
0x180031b6a  mov     edx, 0E3h
0x180031b6f  jmp     short loc_180031B8A
0x180031b71  mov     rcx, rdi
0x180031b74  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180031b79  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180031b80  mov     qword ptr [rsp+0B0h+TokenType], rdx; int
0x180031b85  mov     edx, 0E0h; void *
0x180031b8a  mov     r9d, eax; char *
0x180031b8d  mov     r8, r15; unsigned int
0x180031b90  mov     rcx, [rbp+57h]; this
0x180031b94  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031b99  mov     edi, 1
0x180031b9e  mov     [rbp+4Fh+var_67], dil
0x180031ba2  mov     [rbp+4Fh+TokenHandle], 0
0x180031baa  xor     edx, edx
0x180031bac  lea     rcx, [rbp+4Fh+TokenHandle]
0x180031bb0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180031bb5  call    cs:__imp_GetCurrentThread
0x180031bbb  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180031bbf  mov     r8d, edi; OpenAsSelf
0x180031bc2  lea     ebx, [rdi+0Dh]
0x180031bc5  mov     edx, ebx; DesiredAccess
0x180031bc7  mov     rcx, rax; ThreadHandle
0x180031bca  call    cs:__imp_OpenThreadToken
0x180031bd0  mov     rcx, [rbp+57h]; this
0x180031bd4  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed!"
0x180031bdb  mov     qword ptr [rsp+0B0h+TokenType], rdx; int
0x180031be0  mov     r9d, eax; char *
0x180031be3  mov     r8, r15; unsigned int
0x180031be6  mov     edx, 0EEh; void *
0x180031beb  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180031bf0  mov     r8, [rbp+4Fh+TokenHandle]
0x180031bf4  lea     rdx, [rbp+4Fh+StringSecurityDescriptor]
0x180031bf8  call    ?_CreateAllAccessDaclForUserAndWorker@TokenUtility@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; TokenUtility::_CreateAllAccessDaclForUserAndWorker(void *)
0x180031bfd  nop
0x180031bfe  mov     [rbp+4Fh+SecurityDescriptorSize], 0
0x180031c05  mov     [rbp+4Fh+SecurityDescriptor], 0
0x180031c0d  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]
0x180031c11  cmp     [rbp+4Fh+var_28], 7
0x180031c16  cmova   rcx, [rbp+4Fh+StringSecurityDescriptor]; StringSecurityDescriptor
0x180031c1b  lea     r9, [rbp+4Fh+SecurityDescriptorSize]; SecurityDescriptorSize
0x180031c1f  lea     r8, [rbp+4Fh+SecurityDescriptor]; SecurityDescriptor
0x180031c23  mov     edx, edi; StringSDRevision
0x180031c25  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180031c2b  test    eax, eax
0x180031c2d  setnz   al
0x180031c30  mov     rcx, [rbp+57h]; this
0x180031c34  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180031c3b  mov     qword ptr [rsp+0B0h+TokenType], rdx; bool
0x180031c40  movzx   r9d, al; char *
0x180031c44  mov     r8, r15; unsigned int
0x180031c47  mov     edx, 0F5h; void *
0x180031c4c  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180031c51  mov     qword ptr [rbp+4Fh+TokenAttributes.nLength], 18h
0x180031c59  mov     qword ptr [rbp+4Fh+TokenAttributes.bInheritHandle], 1
0x180031c61  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x180031c65  mov     [rbp+4Fh+TokenAttributes.lpSecurityDescriptor], rax
0x180031c69  xor     edx, edx
0x180031c6b  lea     rcx, [rbp+4Fh+var_78]
0x180031c6f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180031c74  lea     rax, [rbp+4Fh+var_78]
0x180031c78  mov     [rsp+0B0h+phNewToken], rax; char *
0x180031c7d  lea     r9d, [rdi+1]; ImpersonationLevel
0x180031c81  mov     [rsp+0B0h+TokenType], r9d; TokenType
0x180031c86  lea     r8, [rbp+4Fh+TokenAttributes]; lpTokenAttributes
0x180031c8a  mov     edx, ebx; dwDesiredAccess
0x180031c8c  mov     rcx, [rbp+4Fh+TokenHandle]; hExistingToken
0x180031c90  call    cs:__imp_DuplicateTokenEx
0x180031c96  mov     rcx, [rbp+57h]; this
0x180031c9a  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed!"
0x180031ca1  mov     qword ptr [rsp+0B0h+TokenType], rdx; int
0x180031ca6  mov     r9d, eax; char *
0x180031ca9  mov     r8, r15; unsigned int
0x180031cac  mov     edx, 101h; void *
0x180031cb1  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180031cb6  nop
0x180031cb7  lea     rcx, [rbp+4Fh+SecurityDescriptor]
0x180031cbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180031cc0  nop
0x180031cc1  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]
0x180031cc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031cca  nop
0x180031ccb  lea     rcx, [rbp+4Fh+TokenHandle]
0x180031ccf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031cd4  nop
0x180031cd5  call    cs:__imp_RevertToSelf
0x180031cdb  xor     r9d, r9d
0x180031cde  mov     r8, [rbp+4Fh+var_78]
0x180031ce2  mov     rdx, rsi
0x180031ce5  call    ?_DuplicateHandle@TokenUtility@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N@Z; TokenUtility::_DuplicateHandle(void *,bool)
0x180031cea  nop
0x180031ceb  lea     rcx, [rbp+4Fh+var_78]
0x180031cef  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031cf4  mov     rax, rsi
0x180031cf7  mov     rcx, [rbp+4Fh+var_20]
0x180031cfb  xor     rcx, rsp; StackCookie
0x180031cfe  call    __security_check_cookie
0x180031d03  lea     r11, [rsp+0B0h+var_10]
0x180031d0b  mov     rbx, [r11+20h]
0x180031d0f  mov     rsi, [r11+30h]
0x180031d13  mov     rsp, r11
0x180031d16  pop     r15
0x180031d18  pop     rdi
0x180031d19  pop     rbp
0x180031d1a  retn
```
