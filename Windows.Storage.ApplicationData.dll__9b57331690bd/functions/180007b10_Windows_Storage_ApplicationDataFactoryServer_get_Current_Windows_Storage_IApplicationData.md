# Windows::Storage::ApplicationDataFactoryServer::get_Current(Windows::Storage::IApplicationData * *)

- ea: `0x180007b10`
- end: `0x180007db6`
- name: `?get_Current@ApplicationDataFactoryServer@Storage@Windows@@UEAAJPEAPEAUIApplicationData@23@@Z`
- size: `678`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataFactoryServer *this, Windows::Storage::IApplicationData **value)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003820`
- `0x180007b10`
- `0x1800092d0`
- `0x180009400`
- `0x180009778`
- `0x1800173ec`
- `0x18001e9b4`
- `0x180021efc`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d26`
- `ntdll!WinSqmIncrementDWORD` at `0x180007b4a`
- `ntdll!WinSqmIncrementDWORD` at `0x180007b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007bde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007bde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d44`

## string_xrefs

- `0x180007c3d`: `GetUserSidStringByToken`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataFactoryServer::get_Current(
        Windows::Storage::ApplicationDataFactoryServer *this,
        Windows::Storage::IApplicationData **value)
{
  HSTRING__ *m_ptr; // rdi
  HRESULT UserSidStringByToken; // ebx
  Windows::ApplicationModel::Core::ICoreApplication *v4; // rcx
  Windows::Storage::IApplicationData *v5; // rcx
  Windows::ApplicationModel::Core::ICoreApplication *v7; // rcx
  Windows::Storage::IApplicationData *v8; // rcx
  Windows::ApplicationModel::Core::ICoreApplication *ptr; // rcx
  DWORD LastError; // ebx
  PCWSTR StringRawBuffer; // rax
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationData> appData; // [rsp+30h] [rbp-40h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > propertyKeyHString; // [rsp+38h] [rbp-38h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *p_userSid; // [rsp+40h] [rbp-30h]
  Windows::Storage::IApplicationData ***v15; // [rsp+48h] [rbp-28h]
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationData> *p_appData; // [rsp+50h] [rbp-20h]
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication> *p_appObject; // [rsp+58h] [rbp-18h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *p_propertyKeyHString; // [rsp+60h] [rbp-10h]
  void *retaddr; // [rsp+88h] [rbp+18h]
  Windows::Storage::IApplicationData **v20; // [rsp+98h] [rbp+28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > userSid; // [rsp+A0h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplication> appObject; // [rsp+A8h] [rbp+38h] BYREF

  v20 = value;
  appData.ptr_ = 0;
  appObject.ptr_ = 0;
  userSid.m_ptr = 0;
  propertyKeyHString.m_ptr = 0;
  if ( !value )
  {
    UserSidStringByToken = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3Au,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      -2147024809);
    if ( userSid.m_ptr )
      WindowsDeleteString(userSid.m_ptr);
    ptr = appObject.ptr_;
    if ( appObject.ptr_ )
    {
      appObject.ptr_ = 0;
      ptr->Release(ptr);
    }
    return (unsigned int)UserSidStringByToken;
  }
  WinSqmIncrementDWORD(0, 11323, 1);
  *v20 = 0;
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_START);
  m_ptr = userSid.m_ptr;
  if ( userSid.m_ptr )
  {
    LastError = GetLastError();
    WindowsDeleteString(m_ptr);
    SetLastError(LastError);
  }
  userSid.m_ptr = 0;
  UserSidStringByToken = GetUserSidStringByToken((void *const)0xFFFFFFFFFFFFFFFCLL, &userSid.m_ptr);
  if ( UserSidStringByToken < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x45u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      UserSidStringByToken,
      "GetUserSidStringByToken");
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP);
    if ( propertyKeyHString.m_ptr )
      WindowsDeleteString(propertyKeyHString.m_ptr);
    if ( userSid.m_ptr )
      WindowsDeleteString(userSid.m_ptr);
    v7 = appObject.ptr_;
    if ( appObject.ptr_ )
    {
      appObject.ptr_ = 0;
      v7->Release(v7);
    }
    v8 = appData.ptr_;
    if ( appData.ptr_ )
    {
      appData.ptr_ = 0;
      ((void (*)(void))v8->Release)();
    }
    return (unsigned int)UserSidStringByToken;
  }
  p_userSid = &userSid;
  v15 = &v20;
  p_appData = &appData;
  p_appObject = &appObject;
  p_propertyKeyHString = &propertyKeyHString;
  UserSidStringByToken = lambda_aa36a290e114e1697862a2638a5ec855_::operator()();
  if ( UserSidStringByToken < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(userSid.m_ptr, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x6Bu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      UserSidStringByToken,
      "User %ws",
      StringRawBuffer);
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&propertyKeyHString);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&userSid);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&appObject);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&appData);
    return (unsigned int)UserSidStringByToken;
  }
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP);
  if ( propertyKeyHString.m_ptr )
    WindowsDeleteString(propertyKeyHString.m_ptr);
  if ( userSid.m_ptr )
    WindowsDeleteString(userSid.m_ptr);
  v4 = appObject.ptr_;
  if ( appObject.ptr_ )
  {
    appObject.ptr_ = 0;
    v4->Release(v4);
  }
  v5 = appData.ptr_;
  if ( appData.ptr_ )
  {
    appData.ptr_ = 0;
    v5->Release(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180007b10  mov     [rsp-18h+arg_0], rbx
0x180007b15  mov     [rsp-18h+arg_8], value
0x180007b1a  push    rbp
0x180007b1b  push    rsi
0x180007b1c  push    rdi
0x180007b1d  mov     rbp, rsp
0x180007b20  sub     rsp, 70h
0x180007b24  xor     esi, esi
0x180007b26  mov     [rbp+appData.ptr_], rsi
0x180007b2a  mov     [rbp+appObject.ptr_], rsi
0x180007b2e  mov     [rbp+userSid.m_ptr], rsi
0x180007b32  mov     [rbp+propertyKeyHString.m_ptr], rsi
0x180007b36  test    value, value
0x180007b39  jz      loc_180007CC2
0x180007b3f  mov     edx, 2C3Bh
0x180007b44  lea     r8d, [rsi+1]
0x180007b48  xor     ecx, ecx
0x180007b4a  call    cs:__imp_WinSqmIncrementDWORD
0x180007b50  mov     rax, [rbp+arg_8]
0x180007b54  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_START; eventDescriptor
0x180007b5b  mov     [rax], rsi
0x180007b5e  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007b63  mov     rdi, [rbp+userSid.m_ptr]
0x180007b67  test    rdi, rdi
0x180007b6a  jnz     loc_180007D26
0x180007b70  lea     value, [rbp+userSid]; userSidHString
0x180007b74  mov     [rbp+userSid.m_ptr], rsi
0x180007b78  mov     this, 0FFFFFFFFFFFFFFFCh; token
0x180007b7f  call    ?GetUserSidStringByToken@@YAJQEAXPEAPEAUHSTRING__@@@Z; GetUserSidStringByToken(void * const,HSTRING__ * *)
0x180007b84  mov     ebx, eax
0x180007b86  test    eax, eax
0x180007b88  js      loc_180007C39
0x180007b8e  lea     rax, [rbp+userSid]
0x180007b92  mov     [rbp+var_30], rax
0x180007b96  lea     this, [rbp+var_30]
0x180007b9a  lea     rax, [rbp+arg_8]
0x180007b9e  mov     [rbp+var_28], rax
0x180007ba2  lea     rax, [rbp+appData]
0x180007ba6  mov     [rbp+var_20], rax
0x180007baa  lea     rax, [rbp+appObject]
0x180007bae  mov     [rbp+var_18], rax
0x180007bb2  lea     rax, [rbp+propertyKeyHString]
0x180007bb6  mov     [rbp+var_10], rax
0x180007bba  call    _lambda_aa36a290e114e1697862a2638a5ec855___operator__
0x180007bbf  mov     ebx, eax
0x180007bc1  test    eax, eax
0x180007bc3  js      loc_180007D4C
0x180007bc9  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP; eventDescriptor
0x180007bd0  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007bd5  mov     this, [rbp+propertyKeyHString.m_ptr]; string
0x180007bd9  test    this, this
0x180007bdc  jz      short loc_180007BE4
0x180007bde  call    cs:__imp_WindowsDeleteString
0x180007be4  mov     this, [rbp+userSid.m_ptr]; string
0x180007be8  test    this, this
0x180007beb  jnz     short loc_180007C31
0x180007bed  mov     this, [rbp+appObject.ptr_]
0x180007bf1  test    this, this
0x180007bf4  jz      short loc_180007C06
0x180007bf6  mov     [rbp+appObject.ptr_], rsi
0x180007bfa  mov     rax, [this]
0x180007bfd  mov     rax, [rax+10h]
0x180007c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c06  mov     this, [rbp+appData.ptr_]
0x180007c0a  test    this, this
0x180007c0d  jz      short loc_180007C1F
0x180007c0f  mov     [rbp+appData.ptr_], rsi
0x180007c13  mov     rax, [this]
0x180007c16  mov     rax, [rax+10h]
0x180007c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c1f  xor     eax, eax
0x180007c21  mov     rbx, [rsp+70h+arg_0]
0x180007c29  add     rsp, 70h
0x180007c2d  pop     rdi
0x180007c2e  pop     rsi
0x180007c2f  pop     rbp
0x180007c30  retn
0x180007c31  call    cs:__imp_WindowsDeleteString
0x180007c37  jmp     short loc_180007BED
0x180007c39  mov     this, [rbp+18h]; callerReturnAddress
0x180007c3d  lea     rax, aGetusersidstri_0; "GetUserSidStringByToken"
0x180007c44  mov     r9d, ebx; hr
0x180007c47  mov     [rsp+70h+formatString], rax; formatString
0x180007c4c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007c53  mov     edx, 45h ; 'E'; lineNumber
0x180007c58  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007c5d  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP; eventDescriptor
0x180007c64  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007c69  mov     this, [rbp+propertyKeyHString.m_ptr]; string
0x180007c6d  test    this, this
0x180007c70  jz      short loc_180007C78
0x180007c72  call    cs:__imp_WindowsDeleteString
0x180007c78  mov     this, [rbp+userSid.m_ptr]; string
0x180007c7c  test    this, this
0x180007c7f  jnz     short loc_180007CBA
0x180007c81  mov     this, [rbp+appObject.ptr_]
0x180007c85  test    this, this
0x180007c88  jz      short loc_180007C9A
0x180007c8a  mov     [rbp+appObject.ptr_], rsi
0x180007c8e  mov     rax, [this]
0x180007c91  mov     rax, [rax+10h]
0x180007c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9a  mov     this, [rbp+appData.ptr_]
0x180007c9e  test    this, this
0x180007ca1  jz      short loc_180007CB3
0x180007ca3  mov     [rbp+appData.ptr_], rsi
0x180007ca7  mov     rax, [this]
0x180007caa  mov     rax, [rax+10h]
0x180007cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb3  mov     eax, ebx
0x180007cb5  jmp     loc_180007C21
0x180007cba  call    cs:__imp_WindowsDeleteString
0x180007cc0  jmp     short loc_180007C81
0x180007cc2  mov     this, [rbp+18h]; callerReturnAddress
0x180007cc6  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007ccd  mov     ebx, 80070057h
0x180007cd2  mov     edx, 3Ah ; ':'; lineNumber
0x180007cd7  mov     r9d, ebx; hr
0x180007cda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cdf  mov     this, [rbp+propertyKeyHString.m_ptr]; string
0x180007ce3  test    this, this
0x180007ce6  jz      short loc_180007CEE
0x180007ce8  call    cs:__imp_WindowsDeleteString
0x180007cee  mov     this, [rbp+userSid.m_ptr]; string
0x180007cf2  test    this, this
0x180007cf5  jnz     short loc_180007D44
0x180007cf7  mov     this, [rbp+appObject.ptr_]
0x180007cfb  test    this, this
0x180007cfe  jz      short loc_180007D10
0x180007d00  mov     [rbp+appObject.ptr_], rsi
0x180007d04  mov     rax, [this]
0x180007d07  mov     rax, [rax+10h]
0x180007d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d10  mov     this, [rbp+appData.ptr_]
0x180007d14  test    this, this
0x180007d17  jz      short loc_180007CB3
0x180007d19  mov     [rbp+appData.ptr_], rsi
0x180007d1d  mov     value, [this]
0x180007d20  mov     rax, [value+10h]
0x180007d24  jmp     short loc_180007CAE
0x180007d26  call    cs:__imp_GetLastError
0x180007d2c  mov     this, rdi; string
0x180007d2f  mov     ebx, eax
0x180007d31  call    cs:__imp_WindowsDeleteString
0x180007d37  mov     ecx, ebx; dwErrCode
0x180007d39  call    cs:__imp_SetLastError
0x180007d3f  jmp     loc_180007B70
0x180007d44  call    cs:__imp_WindowsDeleteString
0x180007d4a  jmp     short loc_180007CF7
0x180007d4c  mov     this, [rbp+userSid.m_ptr]; string
0x180007d50  xor     edx, edx; length
0x180007d52  call    cs:__imp_WindowsGetStringRawBuffer
0x180007d58  mov     this, [rbp+18h]; callerReturnAddress
0x180007d5c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007d63  mov     [rsp+70h+var_48], rax
0x180007d68  mov     r9d, ebx; hr
0x180007d6b  lea     rax, aUserWs; "User %ws"
0x180007d72  mov     edx, 6Bh ; 'k'; lineNumber
0x180007d77  mov     [rsp+70h+formatString], rax; formatString
0x180007d7c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007d81  lea     this, APPMODELSTATE_WINRT_APPDATAFACTORY_ACTIVATE_STOP; eventDescriptor
0x180007d88  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007d8d  lea     this, [rbp+propertyKeyHString]; this
0x180007d91  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180007d96  lea     this, [rbp+userSid]; this
0x180007d9a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180007d9f  lea     this, [rbp+appObject]; this
0x180007da3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180007da8  lea     this, [rbp+appData]; this
0x180007dac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180007db1  jmp     loc_180007CB3
```
