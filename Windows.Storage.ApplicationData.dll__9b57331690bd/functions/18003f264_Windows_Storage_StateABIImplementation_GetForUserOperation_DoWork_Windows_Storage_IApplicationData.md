# Windows::Storage::StateABIImplementation::GetForUserOperation::DoWork(Windows::Storage::IApplicationData * *)

- ea: `0x18003f264`
- end: `0x18003f51d`
- name: `?DoWork@GetForUserOperation@StateABIImplementation@Storage@Windows@@QEAAJPEAPEAUIApplicationData@34@@Z`
- size: `697`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::GetForUserOperation *this, Windows::Storage::IApplicationData **appData)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d810`

## callees

- `0x180003820`
- `0x1800092d0`
- `0x180009778`
- `0x180013428`
- `0x180017250`
- `0x180019580`
- `0x18001a614`
- `0x18001b248`
- `0x180021efc`
- `0x180021fc4`
- `0x18003f264`
- `0x18003f524`
- `0x18003f854`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18003f2b7`
- `ntdll!WinSqmIncrementDWORD` at `0x18003f2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f49a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f49a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f37b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f4d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f37b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f4d9`

## string_xrefs

- `0x18003f397`: `GetSidFromUser`
- `0x18003f3ed`: `UpdateStateLocationsIfRequired`
- `0x18003f463`: `CreateApplicationDataInstance %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::GetForUserOperation::DoWork(
        Windows::Storage::StateABIImplementation::GetForUserOperation *this,
        Windows::Storage::IApplicationData **appData)
{
  HRESULT SidFromUser; // ebx
  bool v5; // r9
  Windows::Storage::IApplicationData *ptr; // rax
  PCWSTR StringRawBuffer; // [rsp+28h] [rbp-18h]
  PCWSTR v9; // [rsp+28h] [rbp-18h]
  Microsoft::WRL::ComPtr<Windows::System::IUser> user; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 userContext; // [rsp+38h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+28h]
  Microsoft::WRL::Wrappers::HString userSid; // [rsp+78h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationData> localAppData; // [rsp+80h] [rbp+40h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > token; // [rsp+88h] [rbp+48h] BYREF

  if ( appData )
  {
    *appData = 0;
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATASERVER_FORUSER_START);
    WinSqmIncrementDWORD(0, 0, 1);
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_START);
    user.ptr_ = 0;
    SidFromUser = CMarshaledInterface::_Unmarshal(
                    &this->marshaledUserInterface,
                    &GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b,
                    (void **)&user.ptr_,
                    v5);
    if ( SidFromUser < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x36u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
        SidFromUser,
        "Unmarshal");
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
      Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP);
      Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATASERVER_FORUSER_STOP);
      return (unsigned int)SidFromUser;
    }
    token.m_ptr = 0;
    userSid.hstr_ = 0;
    userContext = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &token,
      0);
    WindowsDeleteString(userSid.hstr_);
    userSid.hstr_ = 0;
    SidFromUser = Windows::Storage::StateABIImplementation::GetForUserOperation::GetSidFromUser(
                    user.ptr_,
                    &userSid.hstr_,
                    &token.m_ptr,
                    &userContext);
    if ( SidFromUser == -2147023651 || SidFromUser == -2147023652 )
    {
LABEL_7:
      WindowsDeleteString(userSid.hstr_);
      userSid.hstr_ = 0;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
      goto LABEL_23;
    }
    if ( SidFromUser < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x3Eu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
        SidFromUser,
        "GetSidFromUser");
      goto LABEL_7;
    }
    SidFromUser = Windows::Storage::StateABIImplementation::GetForUserOperation::UpdateStateLocationsIfRequired(
                    this,
                    userSid.hstr_,
                    userContext);
    if ( SidFromUser < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x41u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
        SidFromUser,
        "UpdateStateLocationsIfRequired");
      goto LABEL_7;
    }
    localAppData.ptr_ = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&localAppData);
    SidFromUser = Windows::Storage::ApplicationDataFactoryServer::GetApplicationDataInstance(
                    userSid.hstr_,
                    &localAppData.ptr_);
    if ( SidFromUser == -2147483637 )
    {
      if ( localAppData.ptr_ )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&localAppData);
      SidFromUser = Windows::Storage::ApplicationDataFactoryServer::CreateApplicationDataInstance(
                      userSid.hstr_,
                      user.ptr_,
                      &token,
                      &localAppData.ptr_);
      if ( SidFromUser < 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(userSid.hstr_, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x52u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
          SidFromUser,
          "CreateApplicationDataInstance %ws",
          StringRawBuffer);
LABEL_17:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&localAppData);
        goto LABEL_7;
      }
    }
    else if ( SidFromUser < 0 )
    {
      v9 = WindowsGetStringRawBuffer(userSid.hstr_, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x61u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
        SidFromUser,
        "GetApplicationDataInstance %ws",
        v9);
      goto LABEL_17;
    }
    ptr = localAppData.ptr_;
    if ( !localAppData.ptr_ )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      ptr = localAppData.ptr_;
    }
    localAppData.ptr_ = 0;
    *appData = ptr;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&localAppData);
    WindowsDeleteString(userSid.hstr_);
    userSid.hstr_ = 0;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
    SidFromUser = 0;
    goto LABEL_23;
  }
  SidFromUser = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    0x27u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
    -2147024809);
  return (unsigned int)SidFromUser;
}

```

## disassembly

```asm
0x18003f264  push    rbp
0x18003f266  push    rbx
0x18003f267  push    rsi
0x18003f268  push    rdi
0x18003f269  push    r14
0x18003f26b  mov     rbp, rsp
0x18003f26e  sub     rsp, 40h
0x18003f272  xor     r14d, r14d
0x18003f275  mov     rdi, appData
0x18003f278  mov     rsi, this
0x18003f27b  test    appData, appData
0x18003f27e  jnz     short loc_18003F2A0
0x18003f280  mov     this, [rbp+28h]; callerReturnAddress
0x18003f284  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f28b  mov     ebx, 80070057h
0x18003f290  lea     edx, [rdi+27h]; lineNumber
0x18003f293  mov     r9d, ebx; hr
0x18003f296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f29b  jmp     loc_18003F510
0x18003f2a0  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATASERVER_FORUSER_START; eventDescriptor
0x18003f2a7  mov     [appData], r14
0x18003f2aa  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18003f2af  xor     edx, edx
0x18003f2b1  xor     ecx, ecx
0x18003f2b3  lea     r8d, [appData+1]
0x18003f2b7  call    cs:__imp_WinSqmIncrementDWORD
0x18003f2bd  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_START; eventDescriptor
0x18003f2c4  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18003f2c9  lea     this, [rsi+40h]; this
0x18003f2cd  mov     [rbp+user.ptr_], r14
0x18003f2d1  lea     r8, [rbp+user]; ppv
0x18003f2d5  lea     appData, _GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b; riid
0x18003f2dc  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18003f2e1  mov     ebx, eax
0x18003f2e3  test    eax, eax
0x18003f2e5  jns     short loc_18003F310
0x18003f2e7  mov     this, [rbp+28h]; callerReturnAddress
0x18003f2eb  lea     rax, aUnmarshal; "Unmarshal"
0x18003f2f2  mov     r9d, ebx; hr
0x18003f2f5  mov     [rsp+40h+formatString], rax; formatString
0x18003f2fa  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f301  mov     edx, 36h ; '6'; lineNumber
0x18003f306  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f30b  jmp     loc_18003F4EF
0x18003f310  xor     edx, edx; ptr
0x18003f312  mov     [rbp+token.m_ptr], r14
0x18003f316  lea     this, [rbp+token]; this
0x18003f31a  mov     [rbp+userSid.hstr_], r14
0x18003f31e  mov     [rbp+userContext], r14
0x18003f322  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003f327  mov     this, [rbp+userSid.hstr_]; string
0x18003f32b  call    cs:__imp_WindowsDeleteString
0x18003f331  mov     this, [rbp+user.ptr_]; userParam
0x18003f335  lea     r9, [rbp+userContext]; userContextToken
0x18003f339  lea     r8, [rbp+token]; token
0x18003f33d  mov     [rbp+userSid.hstr_], r14
0x18003f341  lea     appData, [rbp+userSid]; userSidHString
0x18003f345  call    ?GetSidFromUser@GetForUserOperation@StateABIImplementation@Storage@Windows@@CAJPEAUIUser@System@4@PEAPEAUHSTRING__@@PEAPEAXPEA_K@Z; Windows::Storage::StateABIImplementation::GetForUserOperation::GetSidFromUser(Windows::System::IUser *,HSTRING__ * *,void * *,unsigned __int64 *)
0x18003f34a  mov     ebx, eax
0x18003f34c  cmp     eax, 800704DDh
0x18003f351  jnz     short loc_18003F36F
0x18003f353  mov     this, [rbp+userSid.hstr_]; string
0x18003f357  call    cs:__imp_WindowsDeleteString
0x18003f35d  lea     this, [rbp+token]; this
0x18003f361  mov     [rbp+userSid.hstr_], r14
0x18003f365  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f36a  jmp     loc_18003F4EF
0x18003f36f  cmp     ebx, 800704DCh
0x18003f375  jnz     short loc_18003F393
0x18003f377  mov     this, [rbp+userSid.hstr_]; string
0x18003f37b  call    cs:__imp_WindowsDeleteString
0x18003f381  lea     this, [rbp+token]; this
0x18003f385  mov     [rbp+userSid.hstr_], r14
0x18003f389  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f38e  jmp     loc_18003F4EF
0x18003f393  test    ebx, ebx
0x18003f395  jns     short loc_18003F3D7
0x18003f397  lea     rax, aGetsidfromuser; "GetSidFromUser"
0x18003f39e  mov     edx, 3Eh ; '>'; lineNumber
0x18003f3a3  mov     this, [rbp+28h]; callerReturnAddress
0x18003f3a7  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f3ae  mov     r9d, ebx; hr
0x18003f3b1  mov     [rsp+40h+formatString], rax; formatString
0x18003f3b6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f3bb  mov     this, [rbp+userSid.hstr_]; string
0x18003f3bf  call    cs:__imp_WindowsDeleteString
0x18003f3c5  lea     this, [rbp+token]; this
0x18003f3c9  mov     [rbp+userSid.hstr_], r14
0x18003f3cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f3d2  jmp     loc_18003F4EF
0x18003f3d7  mov     r8, [rbp+userContext]; userContext
0x18003f3db  mov     this, rsi; this
0x18003f3de  mov     appData, [rbp+userSid.hstr_]; userSidHString
0x18003f3e2  call    ?UpdateStateLocationsIfRequired@GetForUserOperation@StateABIImplementation@Storage@Windows@@QEAAJPEAUHSTRING__@@_K@Z; Windows::Storage::StateABIImplementation::GetForUserOperation::UpdateStateLocationsIfRequired(HSTRING__ *,unsigned __int64)
0x18003f3e7  mov     ebx, eax
0x18003f3e9  test    eax, eax
0x18003f3eb  jns     short loc_18003F3FB
0x18003f3ed  lea     rax, aUpdatestateloc; "UpdateStateLocationsIfRequired"
0x18003f3f4  mov     edx, 41h ; 'A'
0x18003f3f9  jmp     short loc_18003F3A3
0x18003f3fb  lea     this, [rbp+localAppData]; this
0x18003f3ff  mov     [rbp+localAppData.ptr_], r14
0x18003f403  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f408  mov     this, [rbp+userSid.hstr_]; userSid
0x18003f40c  lea     appData, [rbp+localAppData]; value
0x18003f410  call    ?GetApplicationDataInstance@ApplicationDataFactoryServer@Storage@Windows@@CAJPEAUHSTRING__@@PEAPEAUIApplicationData@23@@Z; Windows::Storage::ApplicationDataFactoryServer::GetApplicationDataInstance(HSTRING__ *,Windows::Storage::IApplicationData * *)
0x18003f415  mov     ebx, eax
0x18003f417  cmp     eax, 8000000Bh
0x18003f41c  jnz     short loc_18003F490
0x18003f41e  cmp     [rbp+localAppData.ptr_], r14
0x18003f422  jz      short loc_18003F429
0x18003f424  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localAppData == nullptr")
0x18003f429  lea     this, [rbp+localAppData]; this
0x18003f42d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f432  mov     appData, [rbp+user.ptr_]; userParam
0x18003f436  lea     r9, [rbp+localAppData]; value
0x18003f43a  mov     this, [rbp+userSid.hstr_]; userSid
0x18003f43e  lea     r8, [rbp+token]; token
0x18003f442  call    ?CreateApplicationDataInstance@ApplicationDataFactoryServer@Storage@Windows@@CAJPEAUHSTRING__@@PEAUIUser@System@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAPEAUIApplicationData@23@@Z; Windows::Storage::ApplicationDataFactoryServer::CreateApplicationDataInstance(HSTRING__ *,Windows::System::IUser *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,Windows::Storage::IApplicationData * *)
0x18003f447  mov     ebx, eax
0x18003f449  test    eax, eax
0x18003f44b  jns     short loc_18003F4B3
0x18003f44d  mov     this, [rbp+userSid.hstr_]; string
0x18003f451  xor     edx, edx; length
0x18003f453  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f459  mov     [rsp+40h+var_18], rax
0x18003f45e  mov     edx, 52h ; 'R'; lineNumber
0x18003f463  lea     rax, aCreateapplicat; "CreateApplicationDataInstance %ws"
0x18003f46a  mov     this, [rbp+28h]; callerReturnAddress
0x18003f46e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003f475  mov     r9d, ebx; hr
0x18003f478  mov     [rsp+40h+formatString], rax; formatString
0x18003f47d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f482  lea     this, [rbp+localAppData]; this
0x18003f486  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f48b  jmp     loc_18003F3BB
0x18003f490  test    ebx, ebx
0x18003f492  jns     short loc_18003F4B3
0x18003f494  mov     this, [rbp+userSid.hstr_]; string
0x18003f498  xor     edx, edx; length
0x18003f49a  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f4a0  mov     [rsp+40h+var_18], rax
0x18003f4a5  mov     edx, 61h ; 'a'
0x18003f4aa  lea     rax, aGetapplication; "GetApplicationDataInstance %ws"
0x18003f4b1  jmp     short loc_18003F46A
0x18003f4b3  mov     rax, [rbp+localAppData.ptr_]
0x18003f4b7  test    rax, rax
0x18003f4ba  jnz     short loc_18003F4C5
0x18003f4bc  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localAppData.Get() != nullptr")
0x18003f4c1  mov     rax, [rbp+localAppData.ptr_]
0x18003f4c5  lea     this, [rbp+localAppData]; this
0x18003f4c9  mov     [rbp+localAppData.ptr_], r14
0x18003f4cd  mov     [rdi], rax
0x18003f4d0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f4d5  mov     this, [rbp+userSid.hstr_]; string
0x18003f4d9  call    cs:__imp_WindowsDeleteString
0x18003f4df  lea     this, [rbp+token]; this
0x18003f4e3  mov     [rbp+userSid.hstr_], r14
0x18003f4e7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f4ec  mov     ebx, r14d
0x18003f4ef  lea     this, [rbp+user]; this
0x18003f4f3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f4f8  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP; eventDescriptor
0x18003f4ff  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18003f504  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATASERVER_FORUSER_STOP; eventDescriptor
0x18003f50b  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18003f510  mov     eax, ebx
0x18003f512  add     rsp, 40h
0x18003f516  pop     r14
0x18003f518  pop     rdi
0x18003f519  pop     rsi
0x18003f51a  pop     rbx
0x18003f51b  pop     rbp
0x18003f51c  retn
```
