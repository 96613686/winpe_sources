# _lambda_2f650bdc441fb3338cfbabd2d791d9eb_::operator()

- ea: `0x180035c28`
- end: `0x180035f56`
- name: `_lambda_2f650bdc441fb3338cfbabd2d791d9eb_::operator()`
- size: `814`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e100`

## callees

- `0x18000275c`
- `0x180005ee0`
- `0x1800093d0`
- `0x180009778`
- `0x180013110`
- `0x18001333c`
- `0x1800134f0`
- `0x180013b54`
- `0x1800163ac`
- `0x180018fb8`
- `0x180019bf4`
- `0x18001ca9c`
- `0x180029d20`
- `0x180029df0`
- `0x180035c28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ee9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035ee9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035efb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x180035cec`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x180035cec`

## string_xrefs

- `0x180035dfc`: `Impersonate`
- `0x180035c97`: `OpenStateExplicitForUserSidString 0x%0x`
- `0x180035d3a`: `OpenStateExplicitForUserSidString`
- `0x180035f27`: `Package %ws userSID %ws operation %ws`

## pseudocode

```c
__int64 __fastcall lambda_2f650bdc441fb3338cfbabd2d791d9eb_::operator()(Windows::Internal::String **a1)
{
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *v1; // rbx
  signed int LastError; // eax
  Windows::System::IUser *v4; // r8
  signed int PropertyValueStaticInterface; // ebx
  int v6; // edi
  wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > *v8; // rdi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v10; // rax
  void *v11; // rax
  signed int v12; // eax
  Windows::Internal::String *v13; // r14
  const wchar_t *v14; // rcx
  HRESULT v15; // eax
  Windows::System::IUser *v16; // r8
  HRESULT v17; // eax
  HRESULT v18; // ebp
  HSTRING__ *hstring; // rdi
  PCWSTR v20; // rbx
  PCWSTR v21; // rax
  ConstrainedImpersonateLoggedOnUser impersonator; // [rsp+40h] [rbp-48h] BYREF
  void *retaddr; // [rsp+88h] [rbp+0h]

  v1 = (Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)*a1;
  if ( !(*a1)[11]._hstring )
  {
    LastError = GetLastError();
    PropertyValueStaticInterface = LastError;
    if ( LastError > 0 )
      PropertyValueStaticInterface = (unsigned __int16)LastError | 0x80070000;
    v6 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(
           (const wchar_t *)a1[1]->_hstring,
           PropertyValueStaticInterface,
           v4);
    if ( v6 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        (const wchar_t *)a1[1]->_hstring,
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 2u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x188u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenStateExplicitForUserSidString 0x%0x",
          v6);
      return (unsigned int)PropertyValueStaticInterface;
    }
    v8 = (wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > *)*a1;
    StringRawBuffer = WindowsGetStringRawBuffer(a1[3]->_hstring, 0);
    v10 = WindowsGetStringRawBuffer(a1[2]->_hstring, 0);
    v11 = (void *)OpenStateExplicitForUserSidString(v10, StringRawBuffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v8 + 11,
      v11);
    v1 = (Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)*a1;
    if ( !(*a1)[11]._hstring )
    {
      v12 = GetLastError();
      PropertyValueStaticInterface = v12;
      if ( v12 > 0 )
        PropertyValueStaticInterface = (unsigned __int16)v12 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        (const wchar_t *)a1[1]->_hstring,
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 2u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x199u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenStateExplicitForUserSidString");
      return (unsigned int)PropertyValueStaticInterface;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(v1 + 25);
  PropertyValueStaticInterface = Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface((Windows::Foundation::IPropertyValueStatics **)&v1[25]);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x19Eu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "GetPropertyValueStaticInterface");
    return (unsigned int)PropertyValueStaticInterface;
  }
  PropertyValueStaticInterface = Windows::Internal::String::Initialize(*a1 + 12, &a1[3]->_hstring);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x1A0u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "Initialize");
    return (unsigned int)PropertyValueStaticInterface;
  }
  v13 = *a1;
  v14 = L"InitializeDataChangedSignalerForUser";
  if ( !a1[4]->_hstring )
    v14 = L"InitializeDataChangedSignaler";
  a1[1]->_hstring = (HSTRING__ *)v14;
  ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser(
    &impersonator,
    (Windows::System::IUser *)a1[4]->_hstring);
  PropertyValueStaticInterface = ConstrainedImpersonateLoggedOnUser::Impersonate(&impersonator);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x1ABu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "Impersonate");
LABEL_22:
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
    Windows::Internal::String::Release(v13 + 12);
    return (unsigned int)PropertyValueStaticInterface;
  }
  v15 = Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler((Windows::Storage::ApplicationDataServer *)*a1);
  PropertyValueStaticInterface = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      0x1ADu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      v15);
    if ( Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(
           (const wchar_t *)a1[1]->_hstring,
           PropertyValueStaticInterface,
           v16) < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        (const wchar_t *)a1[1]->_hstring,
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 2u);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1B9u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
        PropertyValueStaticInterface,
        "InitializeDataChangedSignaler");
      goto LABEL_22;
    }
    v17 = Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler((Windows::Storage::ApplicationDataServer *)*a1);
    v18 = v17;
    if ( v17 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded((const wchar_t *)a1[1]->_hstring, v17, 0);
      Windows::Storage::StateABIHelpers::ReportError(v18, 2u);
      hstring = a1[1]->_hstring;
      v20 = WindowsGetStringRawBuffer(a1[2]->_hstring, 0);
      v21 = WindowsGetStringRawBuffer(a1[3]->_hstring, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1C9u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
        v18,
        "Package %ws userSID %ws operation %ws",
        v21,
        v20,
        hstring);
      PropertyValueStaticInterface = v18;
      goto LABEL_22;
    }
  }
  ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
  return 0;
}

```

## disassembly

```asm
0x180035c28  push    rbx
0x180035c2a  push    rbp
0x180035c2b  push    rsi
0x180035c2c  push    rdi
0x180035c2d  push    r14
0x180035c2f  sub     rsp, 60h
0x180035c33  mov     rbx, [this]
0x180035c36  mov     rsi, this
0x180035c39  cmp     qword ptr [rbx+58h], 0
0x180035c3e  jnz     loc_180035D67
0x180035c44  call    cs:__imp_GetLastError
0x180035c4a  mov     ebx, eax
0x180035c4c  mov     ebp, 80070000h
0x180035c51  test    eax, eax
0x180035c53  jle     short loc_180035C5A
0x180035c55  movzx   ebx, ax
0x180035c58  or      ebx, ebp
0x180035c5a  mov     this, [rsi+8]
0x180035c5e  mov     edx, ebx; inputHr
0x180035c60  mov     this, [this]; operation
0x180035c63  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035c68  mov     edi, eax
0x180035c6a  test    eax, eax
0x180035c6c  jns     short loc_180035CC2
0x180035c6e  mov     this, [rsi+8]
0x180035c72  xor     r8d, r8d; userParam
0x180035c75  mov     edx, ebx; inputHr
0x180035c77  mov     this, [this]; operation
0x180035c7a  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035c7f  mov     edx, 2; idsValue
0x180035c84  mov     ecx, ebx; hr
0x180035c86  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180035c8b  test    ebx, ebx
0x180035c8d  jns     short loc_180035CBB
0x180035c8f  mov     this, [rsp+88h]; callerReturnAddress
0x180035c97  lea     rax, aOpenstateexpli_7; "OpenStateExplicitForUserSidString 0x%0x"
0x180035c9e  mov     dword ptr [rsp+88h+var_60], edi
0x180035ca2  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180035ca9  mov     r9d, ebx; hr
0x180035cac  mov     [rsp+88h+formatString], rax; formatString
0x180035cb1  mov     edx, 188h; lineNumber
0x180035cb6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035cbb  mov     eax, ebx
0x180035cbd  jmp     loc_180035F4B
0x180035cc2  mov     this, [rsi+18h]
0x180035cc6  xor     edx, edx; length
0x180035cc8  mov     rdi, [rsi]
0x180035ccb  mov     this, [this]; string
0x180035cce  call    cs:__imp_WindowsGetStringRawBuffer
0x180035cd4  mov     this, [rsi+10h]
0x180035cd8  xor     edx, edx; length
0x180035cda  mov     rbx, rax
0x180035cdd  mov     this, [this]; string
0x180035ce0  call    cs:__imp_WindowsGetStringRawBuffer
0x180035ce6  mov     this, rax
0x180035ce9  mov     rdx, rbx
0x180035cec  call    cs:__imp_OpenStateExplicitForUserSidString
0x180035cf2  mov     rdx, rax; ptr
0x180035cf5  lea     this, [rdi+58h]; this
0x180035cf9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180035cfe  mov     rbx, [rsi]
0x180035d01  cmp     qword ptr [rbx+58h], 0
0x180035d06  jnz     short loc_180035D67
0x180035d08  call    cs:__imp_GetLastError
0x180035d0e  mov     ebx, eax
0x180035d10  test    eax, eax
0x180035d12  jle     short loc_180035D19
0x180035d14  movzx   ebx, ax
0x180035d17  or      ebx, ebp
0x180035d19  mov     this, [rsi+8]
0x180035d1d  xor     r8d, r8d; userParam
0x180035d20  mov     edx, ebx; inputHr
0x180035d22  mov     this, [this]; operation
0x180035d25  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035d2a  mov     edx, 2; idsValue
0x180035d2f  mov     ecx, ebx; hr
0x180035d31  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180035d36  test    ebx, ebx
0x180035d38  jns     short loc_180035CBB
0x180035d3a  lea     rax, aOpenstateexpli_4; "OpenStateExplicitForUserSidString"
0x180035d41  mov     edx, 199h; lineNumber
0x180035d46  mov     this, [rsp+88h]; callerReturnAddress
0x180035d4e  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180035d55  mov     r9d, ebx; hr
0x180035d58  mov     [rsp+88h+formatString], rax; formatString
0x180035d5d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035d62  jmp     loc_180035CBB
0x180035d67  lea     this, [rbx+0C8h]; this
0x180035d6e  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180035d73  lea     this, [rbx+0C8h]; propertyValueStaticInterface
0x180035d7a  call    ?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z; Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)
0x180035d7f  mov     ebx, eax
0x180035d81  test    eax, eax
0x180035d83  jns     short loc_180035D93
0x180035d85  lea     rax, aGetpropertyval_0; "GetPropertyValueStaticInterface"
0x180035d8c  mov     edx, 19Eh
0x180035d91  jmp     short loc_180035D46
0x180035d93  mov     this, [rsi]
0x180035d96  mov     rdx, [rsi+18h]; other
0x180035d9a  add     this, 60h ; '`'; this
0x180035d9e  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180035da3  mov     ebx, eax
0x180035da5  test    eax, eax
0x180035da7  jns     short loc_180035DB7
0x180035da9  lea     rax, aInitialize; "Initialize"
0x180035db0  mov     edx, 1A0h
0x180035db5  jmp     short loc_180035D46
0x180035db7  mov     rax, [rsi+20h]
0x180035dbb  lea     rdx, aInitializedata; "InitializeDataChangedSignaler"
0x180035dc2  mov     r14, [rsi]
0x180035dc5  lea     this, aInitializedata_1; "InitializeDataChangedSignalerForUser"
0x180035dcc  cmp     qword ptr [rax], 0
0x180035dd0  mov     rax, [rsi+8]
0x180035dd4  cmovz   this, rdx
0x180035dd8  mov     [rax], this
0x180035ddb  lea     this, [rsp+88h+impersonator]; this
0x180035de0  mov     rdx, [rsi+20h]
0x180035de4  mov     rdx, [rdx]; user
0x180035de7  call    ??0ConstrainedImpersonateLoggedOnUser@@QEAA@PEAUIUser@System@Windows@@@Z; ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser(Windows::System::IUser *)
0x180035dec  lea     this, [rsp+88h+impersonator]; this
0x180035df1  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x180035df6  mov     ebx, eax
0x180035df8  test    eax, eax
0x180035dfa  jns     short loc_180035E3C
0x180035dfc  lea     rax, aImpersonate; "Impersonate"
0x180035e03  mov     edx, 1ABh; lineNumber
0x180035e08  mov     this, [rsp+88h]; callerReturnAddress
0x180035e10  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180035e17  mov     r9d, ebx; hr
0x180035e1a  mov     [rsp+88h+formatString], rax; formatString
0x180035e1f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035e24  lea     this, [rsp+88h+impersonator]; this
0x180035e29  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180035e2e  lea     this, [r14+60h]; this
0x180035e32  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x180035e37  jmp     loc_180035CBB
0x180035e3c  mov     this, [rsi]; this
0x180035e3f  call    ?InitializeDataChangedSignaler@ApplicationDataServer@Storage@Windows@@AEAAJXZ; Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(void)
0x180035e44  mov     ebx, eax
0x180035e46  test    eax, eax
0x180035e48  jns     loc_180035F3F
0x180035e4e  mov     this, [rsp+88h]; callerReturnAddress
0x180035e56  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180035e5d  mov     r9d, eax; hr
0x180035e60  mov     edx, 1ADh; lineNumber
0x180035e65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035e6a  mov     this, [rsi+8]
0x180035e6e  mov     edx, ebx; inputHr
0x180035e70  mov     this, [this]; operation
0x180035e73  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035e78  test    eax, eax
0x180035e7a  jns     short loc_180035EAA
0x180035e7c  mov     this, [rsi+8]
0x180035e80  xor     r8d, r8d; userParam
0x180035e83  mov     edx, ebx; inputHr
0x180035e85  mov     this, [this]; operation
0x180035e88  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035e8d  mov     edx, 2; idsValue
0x180035e92  mov     ecx, ebx; hr
0x180035e94  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180035e99  lea     rax, aInitializedata_0; "InitializeDataChangedSignaler"
0x180035ea0  mov     edx, 1B9h
0x180035ea5  jmp     loc_180035E08
0x180035eaa  mov     this, [rsi]; this
0x180035ead  call    ?InitializeDataChangedSignaler@ApplicationDataServer@Storage@Windows@@AEAAJXZ; Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(void)
0x180035eb2  mov     ebp, eax
0x180035eb4  test    eax, eax
0x180035eb6  jns     loc_180035F3F
0x180035ebc  mov     this, [rsi+8]
0x180035ec0  xor     r8d, r8d; userParam
0x180035ec3  mov     edx, eax; inputHr
0x180035ec5  mov     this, [this]; operation
0x180035ec8  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180035ecd  mov     edx, 2; idsValue
0x180035ed2  mov     ecx, ebp; hr
0x180035ed4  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180035ed9  mov     this, [rsi+8]
0x180035edd  xor     edx, edx; length
0x180035edf  mov     rdi, [this]
0x180035ee2  mov     this, [rsi+10h]
0x180035ee6  mov     this, [this]; string
0x180035ee9  call    cs:__imp_WindowsGetStringRawBuffer
0x180035eef  mov     this, [rsi+18h]
0x180035ef3  xor     edx, edx; length
0x180035ef5  mov     rbx, rax
0x180035ef8  mov     this, [this]; string
0x180035efb  call    cs:__imp_WindowsGetStringRawBuffer
0x180035f01  mov     this, [rsp+88h]; callerReturnAddress
0x180035f09  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180035f10  mov     [rsp+88h+var_50], rdi
0x180035f15  mov     r9d, ebp; hr
0x180035f18  mov     [rsp+88h+var_58], rbx
0x180035f1d  mov     edx, 1C9h; lineNumber
0x180035f22  mov     [rsp+88h+var_60], rax
0x180035f27  lea     rax, aPackageWsUsers; "Package %ws userSID %ws operation %ws"
0x180035f2e  mov     [rsp+88h+formatString], rax; formatString
0x180035f33  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035f38  mov     ebx, ebp
0x180035f3a  jmp     loc_180035E24
0x180035f3f  lea     this, [rsp+88h+impersonator]; this
0x180035f44  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180035f49  xor     eax, eax
0x180035f4b  add     rsp, 60h
0x180035f4f  pop     r14
0x180035f51  pop     rdi
0x180035f52  pop     rsi
0x180035f53  pop     rbp
0x180035f54  pop     rbx
0x180035f55  retn
```
