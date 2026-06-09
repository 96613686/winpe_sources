# Windows::Internal::AssignedAccess::AadUserTokenHelper::GetAADTokenForGraphAPI(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180089cbc`
- end: `0x180089e87`
- name: `?GetAADTokenForGraphAPI@AadUserTokenHelper@AssignedAccess@Internal@Windows@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800865ec`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180013fac`
- `0x180016c24`
- `0x18001f2b0`
- `0x1800896d4`
- `0x18008972c`
- `0x18008995c`
- `0x180089cbc`
- `0x180089e90`
- `0x18008a540`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180089d50`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180089d50`

## string_xrefs

- `0x180089cea`: `AadUserTokenHelper_GetAADTokenForGraphAPI`
- `0x180089d2e`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180089d66`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x180089da4`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x180089de8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::AssignedAccess::AadUserTokenHelper::GetAADTokenForGraphAPI(
        __int64 a1,
        __int64 a2)
{
  int ActivationFactory; // eax
  Windows::Internal::AssignedAccess::AadUserTokenHelper *v4; // rcx
  unsigned int v5; // ebx
  int WebAccountProvider; // eax
  Windows::Internal::AssignedAccess::AadUserTokenHelper *v7; // rcx
  int UserAuthToken; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v12; // [rsp+20h] [rbp-E0h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *v13; // [rsp+28h] [rbp-D8h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *v14; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  _QWORD v17[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "AadUserTokenHelper_GetAADTokenForGraphAPI");
  v17[0] = &AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::`vftable';
  AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::StartActivity((AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI *)v17);
  v14 = 0;
  v16 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v16, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v14);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v12 = 0;
    WebAccountProvider = Windows::Internal::AssignedAccess::AadUserTokenHelper::FindWebAccountProvider(v4, v14, &v12);
    v5 = WebAccountProvider;
    if ( WebAccountProvider >= 0 )
    {
      v13 = 0;
      UserAuthToken = Windows::Internal::AssignedAccess::AadUserTokenHelper::BuildTokenRequestOperation(v7, v12, &v13);
      v5 = UserAuthToken;
      if ( UserAuthToken >= 0 )
      {
        UserAuthToken = Windows::Internal::AssignedAccess::AadUserTokenHelper::GetUserAuthToken(
                          v9,
                          (__int64)v13,
                          (__int64 *)v14,
                          a2);
        v5 = UserAuthToken;
        if ( UserAuthToken >= 0 )
        {
          wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v13);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v12);
          v5 = 0;
          goto LABEL_12;
        }
        v10 = 50;
      }
      else
      {
        v10 = 49;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
        (const char *)(unsigned int)UserAuthToken,
        (int)v12);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
        (const char *)(unsigned int)WebAccountProvider,
        (int)v12);
    }
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v12);
  }
LABEL_12:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v14);
  AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::~AadUserTokenHelper_GetAADTokenForGraphAPI((AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI *)v17);
  return v5;
}

```

## disassembly

```asm
0x180089cbc  mov     [rsp-8+arg_0], rbx
0x180089cc1  mov     [rsp-8+arg_10], rdi
0x180089cc6  push    rbp
0x180089cc7  lea     rbp, [rsp-0C0h]
0x180089ccf  sub     rsp, 1C0h
0x180089cd6  mov     rax, cs:__security_cookie
0x180089cdd  xor     rax, rsp
0x180089ce0  mov     [rbp+0C0h+var_10], rax
0x180089ce7  mov     rdi, rdx
0x180089cea  lea     rdx, aAadusertokenhe_2; "AadUserTokenHelper_GetAADTokenForGraphA"...
0x180089cf1  lea     rcx, [rsp+1C0h+var_160]
0x180089cf6  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180089cfb  lea     rax, ??_7AadUserTokenHelper_GetAADTokenForGraphAPI@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::`vftable'
0x180089d02  mov     [rsp+1C0h+var_160], rax
0x180089d07  lea     rcx, [rsp+1C0h+var_160]; this
0x180089d0c  call    ?StartActivity@AadUserTokenHelper_GetAADTokenForGraphAPI@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::StartActivity(void)
0x180089d11  nop
0x180089d12  mov     [rsp+1C0h+var_190], 0
0x180089d1b  mov     [rsp+1C0h+var_170], 0
0x180089d24  mov     r9d, 45h ; 'E'; unsigned int
0x180089d2a  lea     r8d, [r9+1]; unsigned int
0x180089d2e  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180089d35  lea     rcx, [rsp+1C0h+hstringHeader]; hstringHeader
0x180089d3a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180089d3f  lea     r8, [rsp+1C0h+var_190]
0x180089d44  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180089d4b  mov     rcx, [rsp+1C0h+var_170]
0x180089d50  call    cs:__imp_RoGetActivationFactory
0x180089d56  mov     ebx, eax
0x180089d58  test    eax, eax
0x180089d5a  jns     short loc_180089D7C
0x180089d5c  mov     rcx, [rbp+0C8h]; this
0x180089d63  mov     r9d, eax; char *
0x180089d66  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180089d6d  mov     edx, 2Dh ; '-'; void *
0x180089d72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089d77  jmp     loc_180089E4C
0x180089d7c  mov     [rsp+1C0h+var_1A0], 0; int
0x180089d85  lea     r8, [rsp+1C0h+var_1A0]; struct Windows::Security::Credentials::IWebAccountProvider **
0x180089d8a  mov     rdx, [rsp+1C0h+var_190]; struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *
0x180089d8f  call    ?FindWebAccountProvider@AadUserTokenHelper@AssignedAccess@Internal@Windows@@AEAAJPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@4@PEAPEAUIWebAccountProvider@Credentials@94@@Z; Windows::Internal::AssignedAccess::AadUserTokenHelper::FindWebAccountProvider(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180089d94  mov     ebx, eax
0x180089d96  test    eax, eax
0x180089d98  jns     short loc_180089DC5
0x180089d9a  mov     rcx, [rbp+0C8h]; this
0x180089da1  mov     r9d, eax; char *
0x180089da4  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180089dab  mov     edx, 2Fh ; '/'; void *
0x180089db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089db5  nop
0x180089db6  lea     rcx, [rsp+1C0h+var_1A0]
0x180089dbb  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089dc0  jmp     loc_180089E4C
0x180089dc5  mov     [rsp+1C0h+var_198], 0
0x180089dce  lea     r8, [rsp+1C0h+var_198]; struct Windows::Security::Authentication::Web::Core::IWebTokenRequest **
0x180089dd3  mov     rdx, [rsp+1C0h+var_1A0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180089dd8  call    ?BuildTokenRequestOperation@AadUserTokenHelper@AssignedAccess@Internal@Windows@@AEAAJPEAUIWebAccountProvider@Credentials@Security@4@PEAPEAUIWebTokenRequest@Core@Web@Authentication@74@@Z; Windows::Internal::AssignedAccess::AadUserTokenHelper::BuildTokenRequestOperation(Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x180089ddd  mov     ebx, eax
0x180089ddf  test    eax, eax
0x180089de1  jns     short loc_180089E0B
0x180089de3  mov     edx, 31h ; '1'; void *
0x180089de8  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180089def  mov     r9d, eax; char *
0x180089df2  mov     rcx, [rbp+0C8h]; this
0x180089df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089dfe  nop
0x180089dff  lea     rcx, [rsp+1C0h+var_198]
0x180089e04  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089e09  jmp     short loc_180089DB6
0x180089e0b  mov     r9, rdi
0x180089e0e  mov     r8, [rsp+1C0h+var_190]
0x180089e13  mov     rdx, [rsp+1C0h+var_198]
0x180089e18  call    ?GetUserAuthToken@AadUserTokenHelper@AssignedAccess@Internal@Windows@@AEAAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@4@PEAUIWebAuthenticationCoreManagerStatics@67894@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::AadUserTokenHelper::GetUserAuthToken(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,std::wstring &)
0x180089e1d  mov     ebx, eax
0x180089e1f  test    eax, eax
0x180089e21  jns     short loc_180089E2A
0x180089e23  mov     edx, 32h ; '2'
0x180089e28  jmp     short loc_180089DE8
0x180089e2a  lea     rcx, [rsp+1C0h+var_160]
0x180089e2f  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180089e34  nop
0x180089e35  lea     rcx, [rsp+1C0h+var_198]
0x180089e3a  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089e3f  nop
0x180089e40  lea     rcx, [rsp+1C0h+var_1A0]
0x180089e45  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089e4a  xor     ebx, ebx
0x180089e4c  lea     rcx, [rsp+1C0h+var_190]
0x180089e51  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089e56  nop
0x180089e57  lea     rcx, [rsp+1C0h+var_160]; this
0x180089e5c  call    ??1AadUserTokenHelper_GetAADTokenForGraphAPI@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AadUserTokenHelper_GetAADTokenForGraphAPI::~AadUserTokenHelper_GetAADTokenForGraphAPI(void)
0x180089e61  mov     eax, ebx
0x180089e63  mov     rcx, [rbp+0C0h+var_10]
0x180089e6a  xor     rcx, rsp; StackCookie
0x180089e6d  call    __security_check_cookie
0x180089e72  lea     r11, [rsp+1C0h+var_s0]
0x180089e7a  mov     rbx, [r11+10h]
0x180089e7e  mov     rdi, [r11+20h]
0x180089e82  mov     rsp, r11
0x180089e85  pop     rbp
0x180089e86  retn
```
