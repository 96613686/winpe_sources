# Windows::Storage::StateABIImplementation::GetForUserOperation::IsUpdateRequired(ushort const *,ushort const *,bool *)

- ea: `0x18002491c`
- end: `0x180024d78`
- name: `?IsUpdateRequired@GetForUserOperation@StateABIImplementation@Storage@Windows@@AEAAJPEBG0PEA_N@Z`
- size: `1116`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::GetForUserOperation *this, const wchar_t *packageFullName, const wchar_t *userSidString, bool *updateRequired)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f000`

## callees

- `0x1800022b0`
- `0x180003820`
- `0x180009778`
- `0x18000aa74`
- `0x180010224`
- `0x180013110`
- `0x18001333c`
- `0x1800163ac`
- `0x1800186bc`
- `0x180018bcc`
- `0x180018c70`
- `0x180018dd0`
- `0x180018f98`
- `0x18001b248`
- `0x18001bdd4`
- `0x180021efc`
- `0x18002491c`
- `0x180025004`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024c55`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x180024a04`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x180024a04`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800249be`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800249be`

## string_xrefs

- `0x180024a1b`: `OpenStateExplicitForUserSidString %ws userSid %ws`
- `0x180024adb`: `Impersonate`
- `0x1800249cc`: `PackageFamilyNameFromFullName %ws userSid %ws`
- `0x180024b61`: `GetSchemaContext %ws userSid %ws`
- `0x180024ba9`: `GetPackageFullName %ws userSid %ws`
- `0x180024c83`: `GetStateSchema %ws userSid %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::GetForUserOperation::IsUpdateRequired(
        Windows::Storage::StateABIImplementation::GetForUserOperation *this,
        const wchar_t *packageFullName,
        const wchar_t *userSidString,
        bool *updateRequired)
{
  unsigned int v8; // edx
  void *m_ptr; // rbx
  LONG v11; // eax
  bool v12; // r9
  HRESULT v13; // r14d
  HKEY__ *h; // rcx
  HRESULT v15; // eax
  bool v16; // dl
  HRESULT v17; // eax
  void *v18; // rcx
  wchar_t *p; // rcx
  const _EVENT_DESCRIPTOR *v20; // rcx
  HRESULT v21; // r14d
  Microsoft::WRL::ComPtr<Windows::System::IUser> user; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > state; // [rsp+48h] [rbp-B8h] BYREF
  StateSchema::SCHEMA_CONTEXT schemasContext; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int stateSchema; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int packageFamilyNameLength; // [rsp+5Ch] [rbp-A4h] BYREF
  Common::AutoPtr<unsigned short,&Common::AutoPtrDeallocate<unsigned short> > packageFullNameFromRegistry; // [rsp+60h] [rbp-A0h] BYREF
  ConstrainedImpersonateLoggedOnUser impersonator; // [rsp+68h] [rbp-98h] BYREF
  wchar_t packageFamilyName[72]; // [rsp+90h] [rbp-70h] BYREF
  void *retaddr; // [rsp+168h] [rbp+68h]

  if ( !packageFullName )
  {
    v8 = 227;
LABEL_3:
    LODWORD(m_ptr) = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v8,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
      -2147024809);
    return (unsigned int)m_ptr;
  }
  if ( !userSidString )
  {
    v8 = 228;
    goto LABEL_3;
  }
  if ( !updateRequired )
  {
    v8 = 229;
    goto LABEL_3;
  }
  *updateRequired = 1;
  schemasContext.key.h = 0;
  packageFullNameFromRegistry.p = 0;
  stateSchema = 0;
  packageFamilyNameLength = 65;
  v11 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
  if ( v11 )
  {
    LODWORD(m_ptr) = wil::details::in1diag3::Return_Win32Msg(
                       retaddr,
                       0xF2u,
                       "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                       v11,
                       "PackageFamilyNameFromFullName %ws userSid %ws",
                       packageFullName,
                       userSidString);
LABEL_15:
    operator delete(0);
    h = 0;
LABEL_16:
    Common::AutoHandleCloseHKEY<HKEY__ *>(h);
    return (unsigned int)m_ptr;
  }
  state.m_ptr = (void *)OpenStateExplicitForUserSidString(userSidString, packageFamilyName);
  m_ptr = state.m_ptr;
  if ( !state.m_ptr )
  {
    LODWORD(m_ptr) = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       0xF6u,
                       "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
                       "OpenStateExplicitForUserSidString %ws userSid %ws",
                       packageFullName,
                       userSidString);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
    goto LABEL_15;
  }
  user.ptr_ = 0;
  v13 = CMarshaledInterface::_Unmarshal(
          &this->marshaledUserInterface,
          &GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b,
          (void **)&user.ptr_,
          v12);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xFAu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
      v13,
      "Unmarshal");
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
    LODWORD(m_ptr) = v13;
    goto LABEL_15;
  }
  ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser(&impersonator, user.ptr_);
  v15 = ConstrainedImpersonateLoggedOnUser::Impersonate(&impersonator);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    0xFEu,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
    v15,
    "Impersonate");
  v17 = StateSchema::GetOrCreateSchemaContext(m_ptr, v16, &schemasContext);
  LODWORD(m_ptr) = v17;
  if ( ((v17 + 2147024894) & 0xFFFFFFFC) != 0 || v17 == -2147024892 )
  {
    if ( v17 >= 0 )
    {
      LODWORD(m_ptr) = StateSchema::GetPackageFullName(&schemasContext, &packageFullNameFromRegistry.p);
      if ( (int)m_ptr < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x111u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
          (HRESULT)m_ptr,
          "GetPackageFullName %ws userSid %ws",
          packageFullName,
          userSidString);
        ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
        p = packageFullNameFromRegistry.p;
LABEL_24:
        operator delete(p);
LABEL_35:
        h = schemasContext.key.h;
        goto LABEL_16;
      }
      m_ptr = packageFullNameFromRegistry.p;
      if ( packageFullNameFromRegistry.p )
      {
        if ( CompareStringOrdinal(packageFullName, -1, packageFullNameFromRegistry.p, -1, 1) == 2 )
        {
          v21 = StateSchema::GetStateSchema(&schemasContext, &stateSchema);
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x123u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
              v21,
              "GetStateSchema %ws userSid %ws",
              packageFullName,
              userSidString);
            ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
            wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
            operator delete(m_ptr);
            LODWORD(m_ptr) = v21;
            goto LABEL_35;
          }
          if ( stateSchema == 1 )
          {
            *updateRequired = 0;
            ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
            wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
            v18 = m_ptr;
            goto LABEL_37;
          }
          v20 = &APPLICATIONSTATE_UPDATEREQUIRED_SCHEMACHANGED_EVENT;
        }
        else
        {
          v20 = &APPLICATIONSTATE_UPDATEREQUIRED_PACKAGENAMECHANGED_EVENT;
        }
        Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(v20, packageFullName, userSidString, 0);
        ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
        operator delete(m_ptr);
        LODWORD(m_ptr) = 0;
        goto LABEL_35;
      }
      Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(
        &APPLICATIONSTATE_UPDATEREQUIRED_PACKAGENOTFOUND_EVENT,
        packageFullName,
        userSidString,
        0);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x10Cu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.foruseroperation.cpp",
        v17,
        "GetSchemaContext %ws userSid %ws",
        packageFullName,
        userSidString);
    }
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
    p = 0;
    goto LABEL_24;
  }
  Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(
    &APPLICATIONSTATE_UPDATEREQUIRED_SCHEMANOTFOUND_EVENT,
    packageFullName,
    userSidString,
    v17);
  ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(&impersonator);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&user);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&state);
  v18 = 0;
LABEL_37:
  operator delete(v18);
  Common::AutoHandleCloseHKEY<HKEY__ *>(schemasContext.key.h);
  return 0;
}

```

## disassembly

```asm
0x18002491c  push    rbp
0x18002491e  push    rbx
0x18002491f  push    rsi
0x180024920  push    rdi
0x180024921  push    r14
0x180024923  push    r15
0x180024925  lea     rbp, [rsp-38h]
0x18002492a  sub     rsp, 138h
0x180024931  mov     rax, cs:__security_cookie
0x180024938  xor     rax, rsp
0x18002493b  mov     [rbp+60h+var_40], rax
0x18002493f  mov     r15, updateRequired
0x180024942  mov     rsi, userSidString
0x180024945  mov     rdi, packageFullName
0x180024948  mov     r14, this
0x18002494b  test    packageFullName, packageFullName
0x18002494e  jnz     short loc_180024974
0x180024950  mov     edx, 0E3h; lineNumber
0x180024955  mov     this, [rbp+68h]; callerReturnAddress
0x180024959  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024960  mov     ebx, 80070057h
0x180024965  mov     r9d, ebx; hr
0x180024968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002496d  mov     eax, ebx
0x18002496f  jmp     loc_180024D5C
0x180024974  test    rsi, rsi
0x180024977  jnz     short loc_180024980
0x180024979  mov     edx, 0E4h
0x18002497e  jmp     short loc_180024955
0x180024980  test    r15, r15
0x180024983  jnz     short loc_18002498C
0x180024985  mov     edx, 0E5h
0x18002498a  jmp     short loc_180024955
0x18002498c  lea     userSidString, [rbp+60h+packageFamilyName]; packageFamilyName
0x180024990  mov     byte ptr [updateRequired], 1
0x180024994  lea     packageFullName, [rsp+160h+packageFamilyNameLength]; packageFamilyNameLength
0x180024999  mov     [rsp+160h+schemasContext.key.h], 0
0x1800249a2  mov     this, rdi; packageFullName
0x1800249a5  mov     [rsp+160h+packageFullNameFromRegistry.p], 0
0x1800249ae  mov     [rsp+160h+stateSchema], 0
0x1800249b6  mov     [rsp+160h+packageFamilyNameLength], 41h ; 'A'
0x1800249be  call    cs:__imp_PackageFamilyNameFromFullName
0x1800249c4  test    eax, eax
0x1800249c6  jz      short loc_1800249FD
0x1800249c8  mov     this, [rbp+68h]; callerReturnAddress
0x1800249cc  lea     packageFullName, aPackagefamilyn_0; "PackageFamilyNameFromFullName %ws userS"...
0x1800249d3  mov     [rsp+160h+var_130], rsi
0x1800249d8  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800249df  mov     [rsp+160h+var_138], rdi
0x1800249e4  mov     r9d, eax; err
0x1800249e7  mov     [rsp+160h+formatString], packageFullName; formatString
0x1800249ec  mov     edx, 0F2h; lineNumber
0x1800249f1  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800249f6  mov     ebx, eax
0x1800249f8  jmp     loc_180024AAB
0x1800249fd  lea     packageFullName, [rbp+60h+packageFamilyName]
0x180024a01  mov     this, rsi
0x180024a04  call    cs:__imp_OpenStateExplicitForUserSidString
0x180024a0a  mov     [rsp+160h+state.m_ptr], rax
0x180024a0f  mov     rbx, rax
0x180024a12  test    rax, rax
0x180024a15  jnz     short loc_180024A4B
0x180024a17  mov     this, [rbp+68h]; callerReturnAddress
0x180024a1b  lea     updateRequired, aOpenstateexpli_1; "OpenStateExplicitForUserSidString %ws u"...
0x180024a22  mov     [rsp+160h+var_138], rsi
0x180024a27  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024a2e  mov     edx, 0F6h; lineNumber
0x180024a33  mov     [rsp+160h+formatString], rdi
0x180024a38  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180024a3d  lea     this, [rsp+160h+state]; this
0x180024a42  mov     ebx, eax
0x180024a44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024a49  jmp     short loc_180024AAB
0x180024a4b  lea     this, [r14+40h]; this
0x180024a4f  mov     [rsp+160h+user.ptr_], 0
0x180024a58  lea     userSidString, [rsp+160h+user]; ppv
0x180024a5d  lea     packageFullName, _GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b; riid
0x180024a64  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x180024a69  mov     r14d, eax
0x180024a6c  test    eax, eax
0x180024a6e  jns     short loc_180024ABE
0x180024a70  mov     this, [rbp+68h]; callerReturnAddress
0x180024a74  lea     rax, aUnmarshal; "Unmarshal"
0x180024a7b  mov     r9d, r14d; hr
0x180024a7e  mov     [rsp+160h+formatString], rax; formatString
0x180024a83  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024a8a  mov     edx, 0FAh; lineNumber
0x180024a8f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024a94  lea     this, [rsp+160h+user]; this
0x180024a99  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024a9e  lea     this, [rsp+160h+state]; this
0x180024aa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024aa8  mov     ebx, r14d
0x180024aab  xor     ecx, ecx; p
0x180024aad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024ab2  xor     ecx, ecx; h
0x180024ab4  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180024ab9  jmp     loc_18002496D
0x180024abe  mov     packageFullName, [rsp+160h+user.ptr_]; user
0x180024ac3  lea     this, [rsp+160h+impersonator]; this
0x180024ac8  call    ??0ConstrainedImpersonateLoggedOnUser@@QEAA@PEAUIUser@System@Windows@@@Z; ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser(Windows::System::IUser *)
0x180024acd  lea     this, [rsp+160h+impersonator]; this
0x180024ad2  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x180024ad7  mov     this, [rbp+68h]; callerReturnAddress
0x180024adb  lea     packageFullName, aImpersonate; "Impersonate"
0x180024ae2  mov     [rsp+160h+formatString], packageFullName; formatString
0x180024ae7  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024aee  mov     edx, 0FEh; lineNumber
0x180024af3  mov     r9d, eax; hr
0x180024af6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024afb  lea     userSidString, [rsp+160h+schemasContext]; state
0x180024b00  mov     this, rbx; state
0x180024b03  call    ?GetOrCreateSchemaContext@StateSchema@@YAJPEAX_NPEAUSCHEMA_CONTEXT@1@@Z; StateSchema::GetOrCreateSchemaContext(void *,bool,StateSchema::SCHEMA_CONTEXT *)
0x180024b08  mov     ebx, eax
0x180024b0a  lea     ecx, [rax+7FF8FFFEh]
0x180024b10  test    ecx, 0FFFFFFFCh
0x180024b16  jnz     short loc_180024B59
0x180024b18  cmp     eax, 80070004h
0x180024b1d  jz      short loc_180024B59
0x180024b1f  mov     r9d, eax; hResult
0x180024b22  lea     this, APPLICATIONSTATE_UPDATEREQUIRED_SCHEMANOTFOUND_EVENT; eventDescriptor
0x180024b29  mov     userSidString, rsi; userSID
0x180024b2c  mov     packageFullName, rdi; packageFullName
0x180024b2f  call    ?LogStateUpdateRequired@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@PEBG1J@Z; Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long)
0x180024b34  lea     this, [rsp+160h+impersonator]; this
0x180024b39  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024b3e  lea     this, [rsp+160h+user]; this
0x180024b43  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024b48  lea     this, [rsp+160h+state]; this
0x180024b4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024b52  xor     ecx, ecx
0x180024b54  jmp     loc_180024D4B
0x180024b59  test    ebx, ebx
0x180024b5b  jns     short loc_180024B90
0x180024b5d  mov     this, [rbp+68h]; callerReturnAddress
0x180024b61  lea     rax, aGetschemaconte; "GetSchemaContext %ws userSid %ws"
0x180024b68  mov     [rsp+160h+var_130], rsi
0x180024b6d  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024b74  mov     [rsp+160h+var_138], rdi
0x180024b79  mov     r9d, ebx; hr
0x180024b7c  mov     edx, 10Ch; lineNumber
0x180024b81  mov     [rsp+160h+formatString], rax; formatString
0x180024b86  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024b8b  jmp     loc_180024C1F
0x180024b90  lea     packageFullName, [rsp+160h+packageFullNameFromRegistry]; packageFullName
0x180024b95  lea     this, [rsp+160h+schemasContext]; schemaContext
0x180024b9a  call    ?GetPackageFullName@StateSchema@@YAJPEAUSCHEMA_CONTEXT@1@PEAPEAG@Z; StateSchema::GetPackageFullName(StateSchema::SCHEMA_CONTEXT *,ushort * *)
0x180024b9f  mov     ebx, eax
0x180024ba1  test    eax, eax
0x180024ba3  jns     short loc_180024C00
0x180024ba5  mov     this, [rbp+68h]; callerReturnAddress
0x180024ba9  lea     rax, aGetpackagefull; "GetPackageFullName %ws userSid %ws"
0x180024bb0  mov     [rsp+160h+var_130], rsi
0x180024bb5  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024bbc  mov     [rsp+160h+var_138], rdi
0x180024bc1  mov     r9d, ebx; hr
0x180024bc4  mov     edx, 111h; lineNumber
0x180024bc9  mov     [rsp+160h+formatString], rax; formatString
0x180024bce  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024bd3  lea     this, [rsp+160h+impersonator]; this
0x180024bd8  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024bdd  lea     this, [rsp+160h+user]; this
0x180024be2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024be7  lea     this, [rsp+160h+state]; this
0x180024bec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024bf1  mov     this, [rsp+160h+packageFullNameFromRegistry.p]; p
0x180024bf6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024bfb  jmp     loc_180024D1C
0x180024c00  mov     rbx, [rsp+160h+packageFullNameFromRegistry.p]
0x180024c05  test    rbx, rbx
0x180024c08  jnz     short loc_180024C41
0x180024c0a  xor     r9d, r9d; hResult
0x180024c0d  lea     this, APPLICATIONSTATE_UPDATEREQUIRED_PACKAGENOTFOUND_EVENT; eventDescriptor
0x180024c14  mov     userSidString, rsi; userSID
0x180024c17  mov     packageFullName, rdi; packageFullName
0x180024c1a  call    ?LogStateUpdateRequired@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@PEBG1J@Z; Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long)
0x180024c1f  lea     this, [rsp+160h+impersonator]; this
0x180024c24  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024c29  lea     this, [rsp+160h+user]; this
0x180024c2e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024c33  lea     this, [rsp+160h+state]; this
0x180024c38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024c3d  xor     ecx, ecx
0x180024c3f  jmp     short loc_180024BF6
0x180024c41  or      edx, 0FFFFFFFFh; cchCount1
0x180024c44  mov     dword ptr [rsp+160h+formatString], 1; bIgnoreCase
0x180024c4c  mov     r9d, edx; cchCount2
0x180024c4f  mov     userSidString, rbx; lpString2
0x180024c52  mov     this, rdi; lpString1
0x180024c55  call    cs:__imp_CompareStringOrdinal
0x180024c5b  cmp     eax, 2
0x180024c5e  jz      short loc_180024C69
0x180024c60  lea     this, APPLICATIONSTATE_UPDATEREQUIRED_PACKAGENAMECHANGED_EVENT
0x180024c67  jmp     short loc_180024CE6
0x180024c69  lea     packageFullName, [rsp+160h+stateSchema]; stateSchema
0x180024c6e  lea     this, [rsp+160h+schemasContext]; schemaContext
0x180024c73  call    ?GetStateSchema@StateSchema@@YAJPEAUSCHEMA_CONTEXT@1@PEAI@Z; StateSchema::GetStateSchema(StateSchema::SCHEMA_CONTEXT *,uint *)
0x180024c78  mov     r14d, eax
0x180024c7b  test    eax, eax
0x180024c7d  jns     short loc_180024CD8
0x180024c7f  mov     this, [rbp+68h]; callerReturnAddress
0x180024c83  lea     rax, aGetstateschema; "GetStateSchema %ws userSid %ws"
0x180024c8a  mov     [rsp+160h+var_130], rsi
0x180024c8f  lea     userSidString, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\statemanage"...
0x180024c96  mov     [rsp+160h+var_138], rdi
0x180024c9b  mov     r9d, r14d; hr
0x180024c9e  mov     edx, 123h; lineNumber
0x180024ca3  mov     [rsp+160h+formatString], rax; formatString
0x180024ca8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024cad  lea     this, [rsp+160h+impersonator]; this
0x180024cb2  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024cb7  lea     this, [rsp+160h+user]; this
0x180024cbc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024cc1  lea     this, [rsp+160h+state]; this
0x180024cc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024ccb  mov     this, rbx; p
0x180024cce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024cd3  mov     ebx, r14d
0x180024cd6  jmp     short loc_180024D1C
0x180024cd8  cmp     [rsp+160h+stateSchema], 1
0x180024cdd  jz      short loc_180024D26
0x180024cdf  lea     this, APPLICATIONSTATE_UPDATEREQUIRED_SCHEMACHANGED_EVENT; eventDescriptor
0x180024ce6  xor     r9d, r9d; hResult
0x180024ce9  mov     userSidString, rsi; userSID
0x180024cec  mov     packageFullName, rdi; packageFullName
0x180024cef  call    ?LogStateUpdateRequired@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@PEBG1J@Z; Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long)
0x180024cf4  lea     this, [rsp+160h+impersonator]; this
0x180024cf9  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024cfe  lea     this, [rsp+160h+user]; this
0x180024d03  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024d08  lea     this, [rsp+160h+state]; this
0x180024d0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024d12  mov     this, rbx; p
0x180024d15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024d1a  xor     ebx, ebx
0x180024d1c  mov     this, [rsp+160h+schemasContext.key.h]
0x180024d21  jmp     loc_180024AB4
0x180024d26  lea     this, [rsp+160h+impersonator]; this
0x180024d2b  mov     byte ptr [r15], 0
0x180024d2f  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180024d34  lea     this, [rsp+160h+user]; this
0x180024d39  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024d3e  lea     this, [rsp+160h+state]; this
0x180024d43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024d48  mov     this, rbx; p
0x180024d4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024d50  mov     this, [rsp+160h+schemasContext.key.h]; h
0x180024d55  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180024d5a  xor     eax, eax
0x180024d5c  mov     this, [rbp+60h+var_40]
0x180024d60  xor     this, rsp; StackCookie
0x180024d63  call    __security_check_cookie
0x180024d68  add     rsp, 138h
0x180024d6f  pop     r15
0x180024d71  pop     r14
0x180024d73  pop     rdi
0x180024d74  pop     rsi
0x180024d75  pop     rbx
0x180024d76  pop     rbp
0x180024d77  retn
```
