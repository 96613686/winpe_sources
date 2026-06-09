# Windows::Storage::ApplicationDataContainerServer::Initialize(void * const,Windows::Storage::ApplicationDataLocality,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> const &,Windows::System::IUser *)

- ea: `0x180012d50`
- end: `0x180013104`
- name: `?Initialize@ApplicationDataContainerServer@Storage@Windows@@UEAAJQEAXW4ApplicationDataLocality@23@AEBV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAUIUser@System@3@@Z`
- size: `948`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerServer *this, void *const appState, const Windows::Storage::ApplicationDataLocality locality, const Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterfaceParameter, Windows::System::IUser *userParam)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180012d50`
- `0x180013110`
- `0x18001333c`
- `0x180021efc`
- `0x180022628`
- `0x180029bfc`
- `0x180029d20`
- `0x18002fcd0`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f33`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001309b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800130d1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001309b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800130d1`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x180012df7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x180012eda`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x180012df7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateContainer` at `0x180012eda`

## string_xrefs

- `0x180012ff1`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x18001302b`: `Impersonate %u`
- `0x180012f6a`: `CreateStateContainer %u persist %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerServer::Initialize(
        Windows::Storage::ApplicationDataContainerServer *this,
        void *const appState,
        Windows::Storage::ApplicationDataLocality locality,
        const Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterfaceParameter,
        Windows::System::IUser *userParam)
{
  unsigned int v9; // esi
  signed int v10; // ebx
  void *m_ptr; // r15
  Windows::Foundation::IPropertyValueStatics *ptr; // rbx
  Windows::Foundation::IPropertyValueStatics *v13; // rcx
  unsigned int v15; // edx
  signed int LastError; // eax
  void *StateContainer; // rax
  HRESULT v18; // eax
  const char *formatString; // rax
  unsigned int v20; // edx
  __int64 v21; // [rsp+28h] [rbp-A9h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseStateContainer,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > newStateContainerHandle; // [rsp+40h] [rbp-91h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseStateContainer,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > other; // [rsp+48h] [rbp-89h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseStateContainer,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > tempStateContainerHandle; // [rsp+50h] [rbp-81h] BYREF
  ConstrainedImpersonateLoggedOnUser impersonator; // [rsp+58h] [rbp-79h] BYREF
  wchar_t szParam[12]; // [rsp+78h] [rbp-59h] BYREF
  _OWORD v27[3]; // [rsp+90h] [rbp-41h] BYREF
  _OWORD v28[2]; // [rsp+C0h] [rbp-11h]
  void *retaddr; // [rsp+128h] [rbp+57h]

  other.m_ptr = appState;
  if ( !appState )
  {
    v10 = -2147024809;
    v15 = 63;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v15,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      -2147024809);
    return (unsigned int)v10;
  }
  v9 = 1;
  if ( (unsigned int)(locality - 2) <= 1 )
  {
    v10 = -2147024809;
    wcscpy(szParam, L"locality");
    RoOriginateErrorW(2147942487LL, 8, szParam);
    formatString = "Locality %u";
    v20 = 71;
    goto LABEL_39;
  }
  if ( !propertyValueStaticInterfaceParameter->ptr_ )
  {
    v10 = -2147024809;
    v27[0] = *(_OWORD *)L"propertyValueStaticInterfaceParameter";
    v27[2] = *(_OWORD *)L"ticInterfaceParameter";
    v27[1] = *(_OWORD *)L"ValueStaticInterfaceParameter";
    v28[0] = *(_OWORD *)L"faceParameter";
    *(_OWORD *)((char *)v28 + 12) = *(_OWORD *)L"rameter";
    RoOriginateErrorW(2147942487LL, 37, v27);
    v15 = 78;
    goto LABEL_16;
  }
  switch ( locality )
  {
    case ApplicationDataLocality_Local:
      break;
    case ApplicationDataLocality_Roaming:
      v9 = 2;
      break;
    case ApplicationDataLocality_Temporary:
      v9 = 3;
      break;
    case ApplicationDataLocality_LocalCache:
      v9 = 4;
      break;
    default:
      v10 = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x3Au,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
        -2147024809,
        "Locality %u",
        locality);
      formatString = "GetStateApiSetPersistAttrib %u";
      v20 = 82;
LABEL_39:
      LODWORD(v21) = locality;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        v20,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
        -2147024809,
        formatString,
        v21);
      return (unsigned int)v10;
  }
  impersonator.m_impersonating = 0;
  impersonator.m_userTokenHandle.m_ptr = 0;
  impersonator.m_userObject.ptr_ = userParam;
  if ( userParam )
    userParam->AddRef(userParam);
  impersonator.m_contextToken = 0;
  v10 = ConstrainedImpersonateLoggedOnUser::Impersonate(&impersonator);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x57u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      v10,
      "Impersonate %u",
      locality);
LABEL_28:
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
    return (unsigned int)v10;
  }
  newStateContainerHandle.m_ptr = (void *)CreateStateContainer(appState, v9, 0, 2);
  m_ptr = newStateContainerHandle.m_ptr;
  if ( !newStateContainerHandle.m_ptr )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( Windows::Storage::StateABIHelpers::RepairStateLocations(L"SettingsInitialize", v10, userParam) >= 0 )
    {
      StateContainer = (void *)CreateStateContainer(other.m_ptr, v9, 0, 2);
      other.m_ptr = 0;
      tempStateContainerHandle.m_ptr = StateContainer;
      newStateContainerHandle.m_ptr = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
        &newStateContainerHandle,
        &tempStateContainerHandle);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
        &tempStateContainerHandle,
        &other);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&other);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&tempStateContainerHandle);
      m_ptr = newStateContainerHandle.m_ptr;
    }
    if ( !m_ptr )
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"SettingsInitialize", v18, 0);
      Windows::Storage::StateABIHelpers::ReportError(v10, 4u);
      if ( v10 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x79u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
          v10,
          "CreateStateContainer %u persist %u",
          locality,
          v9);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&newStateContainerHandle);
      goto LABEL_28;
    }
  }
  this->m_containerHandle = m_ptr;
  this->m_locality = locality;
  ptr = propertyValueStaticInterfaceParameter->ptr_;
  if ( this->m_propertyValueStaticInterface.ptr_ != propertyValueStaticInterfaceParameter->ptr_ )
  {
    if ( ptr )
      ptr->AddRef(propertyValueStaticInterfaceParameter->ptr_);
    v13 = this->m_propertyValueStaticInterface.ptr_;
    this->m_propertyValueStaticInterface.ptr_ = ptr;
    if ( v13 )
      v13->Release(v13);
  }
  ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
  return 0;
}

```

## disassembly

```asm
0x180012d50  mov     [rsp-8+arg_18], rbx
0x180012d55  push    rbp
0x180012d56  push    rsi
0x180012d57  push    rdi
0x180012d58  push    r12
0x180012d5a  push    r13
0x180012d5c  push    r14
0x180012d5e  push    r15
0x180012d60  lea     rbp, [rsp-1Fh]
0x180012d65  sub     rsp, 0F0h
0x180012d6c  mov     rax, cs:__security_cookie
0x180012d73  xor     rax, rsp
0x180012d76  mov     [rbp+4Fh+var_40], rax
0x180012d7a  mov     r12, [rbp+4Fh+arg_20]
0x180012d7e  xor     ebx, ebx
0x180012d80  mov     [rsp+120h+other.m_ptr], appState
0x180012d85  mov     r13, propertyValueStaticInterfaceParameter
0x180012d88  mov     edi, locality
0x180012d8b  mov     r15, appState
0x180012d8e  mov     r14, this
0x180012d91  test    appState, appState
0x180012d94  jz      loc_180012E7F
0x180012d9a  lea     eax, [r8-2]
0x180012d9e  lea     esi, [rbx+1]
0x180012da1  cmp     eax, esi
0x180012da3  jbe     loc_1800130AB
0x180012da9  cmp     [propertyValueStaticInterfaceParameter], rbx
0x180012dac  jz      loc_180013054
0x180012db2  mov     ecx, locality
0x180012db5  test    locality, locality
0x180012db8  jnz     loc_180012FBF
0x180012dbe  mov     [rbp+4Fh+impersonator.m_impersonating], bl
0x180012dc1  mov     [rbp+4Fh+impersonator.m_userTokenHandle.m_ptr], rbx
0x180012dc5  mov     [rbp+4Fh+impersonator.m_userObject.ptr_], r12
0x180012dc9  test    r12, r12
0x180012dcc  jnz     loc_180012FAA
0x180012dd2  lea     this, [rbp+4Fh+impersonator]; this
0x180012dd6  mov     [rbp+4Fh+impersonator.m_contextToken], rbx
0x180012dda  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x180012ddf  mov     ebx, eax
0x180012de1  test    eax, eax
0x180012de3  js      loc_180013027
0x180012de9  mov     r9d, 2
0x180012def  xor     locality, locality
0x180012df2  mov     edx, esi
0x180012df4  mov     this, r15
0x180012df7  call    cs:__imp_CreateStateContainer
0x180012dfd  mov     [rsp+120h+newStateContainerHandle.m_ptr], rax
0x180012e02  mov     r15, rax
0x180012e05  test    rax, rax
0x180012e08  jz      loc_180012EA0
0x180012e0e  mov     [r14+58h], r15
0x180012e12  mov     [r14+50h], edi
0x180012e16  mov     rbx, [r13+0]
0x180012e1a  cmp     [r14+60h], rbx
0x180012e1e  jz      short loc_180012E4D
0x180012e20  test    rbx, rbx
0x180012e23  jz      short loc_180012E34
0x180012e25  mov     rax, [rbx]
0x180012e28  mov     this, rbx
0x180012e2b  mov     rax, [rax+8]
0x180012e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e34  mov     this, [r14+60h]
0x180012e38  mov     [r14+60h], rbx
0x180012e3c  test    this, this
0x180012e3f  jz      short loc_180012E4D
0x180012e41  mov     rax, [this]
0x180012e44  mov     rax, [rax+10h]
0x180012e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e4d  lea     this, [rbp+4Fh+impersonator]; this
0x180012e51  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180012e56  xor     eax, eax
0x180012e58  mov     this, [rbp+4Fh+var_40]
0x180012e5c  xor     this, rsp; StackCookie
0x180012e5f  call    __security_check_cookie
0x180012e64  mov     rbx, [rsp+120h+arg_18]
0x180012e6c  add     rsp, 0F0h
0x180012e73  pop     r15
0x180012e75  pop     r14
0x180012e77  pop     r13
0x180012e79  pop     r12
0x180012e7b  pop     rdi
0x180012e7c  pop     rsi
0x180012e7d  pop     rbp
0x180012e7e  retn
0x180012e7f  mov     ebx, 80070057h
0x180012e84  mov     edx, 3Fh ; '?'; lineNumber
0x180012e89  mov     this, [rbp+57h]; callerReturnAddress
0x180012e8d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x180012e94  mov     r9d, ebx; hr
0x180012e97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e9c  mov     eax, ebx
0x180012e9e  jmp     short loc_180012E58
0x180012ea0  call    cs:__imp_GetLastError
0x180012ea6  mov     ebx, eax
0x180012ea8  test    eax, eax
0x180012eaa  jle     short loc_180012EB5
0x180012eac  movzx   ebx, ax
0x180012eaf  or      ebx, 80070000h
0x180012eb5  mov     r8, r12; userParam
0x180012eb8  lea     this, aSettingsinitia; "SettingsInitialize"
0x180012ebf  mov     edx, ebx; inputHr
0x180012ec1  call    ?RepairStateLocations@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::RepairStateLocations(ushort const *,long,Windows::System::IUser *)
0x180012ec6  test    eax, eax
0x180012ec8  js      short loc_180012F2A
0x180012eca  mov     this, [rsp+120h+other.m_ptr]
0x180012ecf  mov     r9d, 2
0x180012ed5  xor     locality, locality
0x180012ed8  mov     edx, esi
0x180012eda  call    cs:__imp_CreateStateContainer
0x180012ee0  lea     appState, [rsp+120h+tempStateContainerHandle]; other
0x180012ee5  mov     [rsp+120h+other.m_ptr], r15
0x180012eea  lea     this, [rsp+120h+newStateContainerHandle]; this
0x180012eef  mov     [rsp+120h+tempStateContainerHandle.m_ptr], rax
0x180012ef4  mov     [rsp+120h+newStateContainerHandle.m_ptr], 0
0x180012efd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180012f02  lea     appState, [rsp+120h+other]; other
0x180012f07  lea     this, [rsp+120h+tempStateContainerHandle]; this
0x180012f0c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180012f11  lea     this, [rsp+120h+other]; this
0x180012f16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012f1b  lea     this, [rsp+120h+tempStateContainerHandle]; this
0x180012f20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012f25  mov     r15, [rsp+120h+newStateContainerHandle.m_ptr]
0x180012f2a  test    r15, r15
0x180012f2d  jnz     loc_180012E0E
0x180012f33  call    cs:__imp_GetLastError
0x180012f39  test    eax, eax
0x180012f3b  jle     short loc_180012F45
0x180012f3d  movzx   eax, ax
0x180012f40  or      eax, 80070000h
0x180012f45  xor     locality, locality; userParam
0x180012f48  lea     this, aSettingsinitia; "SettingsInitialize"
0x180012f4f  mov     edx, eax; inputHr
0x180012f51  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180012f56  mov     edx, 4; idsValue
0x180012f5b  mov     ecx, ebx; hr
0x180012f5d  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180012f62  test    ebx, ebx
0x180012f64  jns     short loc_180012F92
0x180012f66  mov     this, [rbp+57h]; callerReturnAddress
0x180012f6a  lea     rax, aCreatestatecon_1; "CreateStateContainer %u persist %u"
0x180012f71  mov     [rsp+120h+var_F0], esi
0x180012f75  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x180012f7c  mov     dword ptr [rsp+120h+var_F8], edi
0x180012f80  mov     r9d, ebx; hr
0x180012f83  mov     edx, 79h ; 'y'; lineNumber
0x180012f88  mov     [rsp+120h+formatString], rax; formatString
0x180012f8d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180012f92  lea     this, [rsp+120h+newStateContainerHandle]; this
0x180012f97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseStateContainer@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseStateContainer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012f9c  lea     this, [rbp+4Fh+impersonator]; this
0x180012fa0  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180012fa5  jmp     loc_180012E9C
0x180012faa  mov     rax, [r12]
0x180012fae  mov     this, r12
0x180012fb1  mov     rax, [rax+8]
0x180012fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fba  jmp     loc_180012DD2
0x180012fbf  sub     ecx, esi
0x180012fc1  jz      short loc_18001301D
0x180012fc3  sub     ecx, esi
0x180012fc5  jz      short loc_180013013
0x180012fc7  cmp     ecx, esi
0x180012fc9  jnz     short loc_180012FD5
0x180012fcb  mov     esi, 4
0x180012fd0  jmp     loc_180012DBE
0x180012fd5  mov     this, [rbp+57h]; callerReturnAddress
0x180012fd9  lea     rax, aLocalityU; "Locality %u"
0x180012fe0  mov     ebx, 80070057h
0x180012fe5  mov     dword ptr [rsp+120h+var_F8], edi
0x180012fe9  mov     r9d, ebx; hr
0x180012fec  mov     [rsp+120h+formatString], rax; formatString
0x180012ff1  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x180012ff8  mov     edx, 3Ah ; ':'; lineNumber
0x180012ffd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180013002  lea     rax, aGetstateapiset; "GetStateApiSetPersistAttrib %u"
0x180013009  mov     edx, 52h ; 'R'
0x18001300e  jmp     loc_1800130E3
0x180013013  mov     esi, 3
0x180013018  jmp     loc_180012DBE
0x18001301d  mov     esi, 2
0x180013022  jmp     loc_180012DBE
0x180013027  mov     this, [rbp+57h]; callerReturnAddress
0x18001302b  lea     rax, aImpersonateU; "Impersonate %u"
0x180013032  mov     dword ptr [rsp+120h+var_F8], edi
0x180013036  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001303d  mov     r9d, ebx; hr
0x180013040  mov     [rsp+120h+formatString], rax; formatString
0x180013045  mov     edx, 57h ; 'W'; lineNumber
0x18001304a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001304f  jmp     loc_180012F9C
0x180013054  movaps  xmm0, xmmword ptr cs:aPropertyvalues; "propertyValueStaticInterfaceParameter"
0x18001305b  lea     r8, [rbp+4Fh+var_90]
0x18001305f  movaps  xmm1, xmmword ptr cs:aPropertyvalues+10h; "ValueStaticInterfaceParameter"
0x180013066  mov     ebx, 80070057h
0x18001306b  movaps  [rbp+4Fh+var_90], xmm0
0x18001306f  mov     edx, 25h ; '%'
0x180013074  movaps  xmm0, xmmword ptr cs:aPropertyvalues+20h; "ticInterfaceParameter"
0x18001307b  mov     ecx, ebx
0x18001307d  movaps  [rbp+4Fh+var_70], xmm0
0x180013081  movups  xmm0, xmmword ptr cs:aPropertyvalues+3Ch; "rameter"
0x180013088  movaps  [rbp+4Fh+var_80], xmm1
0x18001308c  movaps  xmm1, xmmword ptr cs:aPropertyvalues+30h; "faceParameter"
0x180013093  movaps  xmmword ptr [rbp+4Fh+var_60], xmm1
0x180013097  movups  xmmword ptr [rbp+4Fh+var_60+0Ch], xmm0
0x18001309b  call    cs:__imp_RoOriginateErrorW
0x1800130a1  mov     edx, 4Eh ; 'N'
0x1800130a6  jmp     loc_180012E89
0x1800130ab  movups  xmm0, xmmword ptr cs:aLocality; "locality"
0x1800130b2  movzx   eax, word ptr cs:aLocality+10h; ""
0x1800130b9  lea     r8, [rbp+4Fh+szParam]
0x1800130bd  mov     ebx, 80070057h
0x1800130c2  mov     [rbp+4Fh+szParam+10h], ax
0x1800130c6  mov     edx, 8
0x1800130cb  mov     ecx, ebx
0x1800130cd  movups  xmmword ptr [rbp+4Fh+szParam], xmm0
0x1800130d1  call    cs:__imp_RoOriginateErrorW
0x1800130d7  lea     rax, aLocalityU; "Locality %u"
0x1800130de  mov     edx, 47h ; 'G'; lineNumber
0x1800130e3  mov     this, [rbp+57h]; callerReturnAddress
0x1800130e7  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800130ee  mov     dword ptr [rsp+120h+var_F8], edi
0x1800130f2  mov     r9d, ebx; hr
0x1800130f5  mov     [rsp+120h+formatString], rax; formatString
0x1800130fa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800130ff  jmp     loc_180012E9C
```
