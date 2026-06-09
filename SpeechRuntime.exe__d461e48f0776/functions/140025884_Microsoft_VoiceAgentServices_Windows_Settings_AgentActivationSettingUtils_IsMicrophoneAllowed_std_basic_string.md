# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsMicrophoneAllowed(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x140025884`
- end: `0x140025e25`
- name: `?IsMicrophoneAllowed@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `1441`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400295d0`

## callees

- `0x140002d30`
- `0x140004dbc`
- `0x140007c0c`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x14001296c`
- `0x140012d68`
- `0x1400210dc`
- `0x14002431c`
- `0x140024394`
- `0x140025078`
- `0x14002511c`
- `0x140025200`
- `0x140025698`
- `0x140025884`
- `0x140025f88`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025c40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025c40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140025d52`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400258f8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400258f8`

## string_xrefs

- `0x14002590b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x14002596c`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x1400259ad`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025a07`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025aa9`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025c29`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025c95`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025d89`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025da9`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x1400258cd`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsMicrophoneAllowed(
        __int64 a1,
        _BYTE *a2)
{
  int v4; // r14d
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  int UserSid; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  char v17; // si
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64 *); // rbx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int PackageFullNameFromFamilyName; // eax
  int v32; // eax
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v35; // rbx
  __int64 v36; // rax
  int v37; // eax
  int v39; // [rsp+20h] [rbp-B9h]
  __int64 v40; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v41; // [rsp+38h] [rbp-A1h] BYREF
  int v42; // [rsp+40h] [rbp-99h] BYREF
  __int64 v43; // [rsp+48h] [rbp-91h] BYREF
  HSTRING string; // [rsp+50h] [rbp-89h] BYREF
  __int64 v45; // [rsp+58h] [rbp-81h] BYREF
  __int64 v46; // [rsp+60h] [rbp-79h] BYREF
  int v47; // [rsp+68h] [rbp-71h] BYREF
  int v48; // [rsp+6Ch] [rbp-6Dh] BYREF
  __int64 v49; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v50[32]; // [rsp+78h] [rbp-61h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-41h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-29h]
  _BYTE v53[32]; // [rsp+B8h] [rbp-21h] BYREF
  _BYTE v54[32]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v4 = 0;
  *a2 = 0;
  v49 = 0;
  v52 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
    0x46u,
    0x45u);
  v5 = v52;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v49);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v40 = 0;
    v8 = v49;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &c_szCapabilityMicrophone);
    v11 = v9(v8, *(_QWORD *)(v10 + 24), &v40);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)(unsigned int)v11,
        v39);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      goto LABEL_44;
    }
    std::wstring::wstring(v50);
    UserSid = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetUserSid(v50);
    v7 = UserSid;
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)(unsigned int)UserSid,
        v39);
LABEL_8:
      std::wstring::~wstring(v50);
      goto LABEL_5;
    }
    if ( !*(_QWORD *)(a1 + 16) )
    {
      v46 = 0;
      v13 = v40;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      v15 = v14(v13, &v46);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = 81;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
          (const char *)(unsigned int)v15,
          v39);
LABEL_13:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
        goto LABEL_8;
      }
      v17 = 1;
      v48 = 1;
      if ( v46 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 88LL))(v46, &v48);
        v7 = v15;
        if ( v15 < 0 )
        {
          v16 = 86;
          goto LABEL_12;
        }
      }
      v41 = 0;
      v18 = v40;
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v45);
      v21 = v19(v18, *(_QWORD *)(v20 + 24), &v41);
      v7 = v21;
      if ( v21 < 0 )
      {
        v22 = 90;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
          (const char *)(unsigned int)v21,
          v39);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
        goto LABEL_13;
      }
      v23 = 1;
      v47 = 1;
      if ( v41 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 88LL))(v41, &v47);
        v7 = v21;
        if ( v21 < 0 )
        {
          v22 = 95;
          goto LABEL_19;
        }
        v23 = v47;
      }
      if ( v48 != 1 || v23 != 1 )
        v17 = 0;
      *a2 = v17;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
LABEL_43:
      std::wstring::~wstring(v50);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v7 = v4;
      goto LABEL_44;
    }
    v24 = std::wstring::find(a1, 33, 0);
    std::wstring::wstring(&hstringHeader, a1, 0, v24);
    v43 = 0;
    v25 = v40;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v40 + 88LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
    v27 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v54, &v45) + 24);
    v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v53, &v45);
    v29 = v26(v25, *(_QWORD *)(v28 + 24), v27, &v43);
    v4 = v29;
    if ( v29 == -2147024444 )
    {
      string = 0;
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::MicPermissionNotProvisioned<unsigned short const *>(&v41);
      WindowsDeleteString(string);
      string = 0;
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
      v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v53, &v41);
      PackageFullNameFromFamilyName = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::TryGetPackageFullNameFromFamilyName(
                                        *(HSTRING *)(v30 + 24),
                                        &string);
      v7 = PackageFullNameFromFamilyName;
      if ( PackageFullNameFromFamilyName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
          (const char *)(unsigned int)PackageFullNameFromFamilyName,
          v39);
LABEL_31:
        WindowsDeleteString(string);
        string = 0;
LABEL_32:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
        std::wstring::~wstring(&hstringHeader);
        goto LABEL_8;
      }
      wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(&v45);
      v32 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v45 + 264LL))(v45, string);
      v7 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
          (const char *)(unsigned int)v32,
          v39);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
        goto LABEL_31;
      }
      v33 = v40;
      v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v40 + 88LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
      v35 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v53, &v41) + 24);
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
      v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v54, &v41);
      v4 = v34(v33, *(_QWORD *)(v36 + 24), v35, &v43);
      v42 = v4;
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::EnsurePackageIsRegistered<unsigned short const *,long &>(
        &v41,
        &v42);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v45);
      WindowsDeleteString(string);
    }
    else if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)(unsigned int)v29,
        v39);
      goto LABEL_42;
    }
    if ( v43 )
    {
      v42 = 1;
      v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 88LL))(v43, &v42);
      v7 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7E,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
          (const char *)(unsigned int)v37,
          v39);
        goto LABEL_32;
      }
      *a2 = v42 == 1;
    }
LABEL_42:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    std::wstring::~wstring(&hstringHeader);
    goto LABEL_43;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x44,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v39);
LABEL_44:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  return v7;
}

```

## disassembly

```asm
0x140025884  mov     [rsp-8+arg_10], rbx
0x140025889  push    rbp
0x14002588a  push    rsi
0x14002588b  push    rdi
0x14002588c  push    r12
0x14002588e  push    r13
0x140025890  push    r14
0x140025892  push    r15
0x140025894  lea     rbp, [rsp-27h]
0x140025899  sub     rsp, 100h
0x1400258a0  mov     rax, cs:__security_cookie
0x1400258a7  xor     rax, rsp
0x1400258aa  mov     [rbp+57h+var_38], rax
0x1400258ae  mov     r12, rdx
0x1400258b1  mov     r15, rcx
0x1400258b4  xor     r13d, r13d
0x1400258b7  mov     r14d, r13d
0x1400258ba  mov     [rdx], r13b
0x1400258bd  mov     [rbp+57h+var_C0], r13
0x1400258c1  mov     [rbp+57h+var_80], r13
0x1400258c5  lea     r9d, [r13+45h]; unsigned int
0x1400258c9  lea     r8d, [r13+46h]; unsigned int
0x1400258cd  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x1400258d4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1400258d8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400258dd  mov     rbx, [rbp+57h+var_80]
0x1400258e1  lea     rcx, [rbp+57h+var_C0]
0x1400258e5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400258ea  lea     r8, [rbp+57h+var_C0]
0x1400258ee  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x1400258f5  mov     rcx, rbx
0x1400258f8  call    cs:__imp_RoGetActivationFactory
0x1400258fe  mov     ebx, eax
0x140025900  test    eax, eax
0x140025902  jns     short loc_140025920
0x140025904  mov     rcx, [rbp+5Fh]; this
0x140025908  mov     r9d, eax; char *
0x14002590b  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025912  lea     edx, [r13+44h]; void *
0x140025916  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002591b  jmp     loc_140025DF3
0x140025920  mov     [rsp+130h+var_100], r13
0x140025925  mov     rdi, [rbp+57h+var_C0]
0x140025929  mov     rax, [rdi]
0x14002592c  mov     rbx, [rax+30h]
0x140025930  lea     rcx, [rsp+130h+var_100]
0x140025935  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002593a  lea     rdx, ?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x140025941  lea     rcx, [rbp+57h+hstringHeader]
0x140025945  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14002594a  nop
0x14002594b  lea     r8, [rsp+130h+var_100]
0x140025950  mov     rdx, [rax+18h]
0x140025954  mov     rcx, rdi
0x140025957  mov     rax, rbx
0x14002595a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002595f  mov     ebx, eax
0x140025961  test    eax, eax
0x140025963  jns     short loc_14002598D
0x140025965  mov     rcx, [rbp+5Fh]; this
0x140025969  mov     r9d, eax; char *
0x14002596c  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025973  mov     edx, 49h ; 'I'; void *
0x140025978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002597d  nop
0x14002597e  lea     rcx, [rsp+130h+var_100]
0x140025983  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025988  jmp     loc_140025DF3
0x14002598d  lea     rcx, [rbp+57h+var_B8]
0x140025991  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140025996  nop
0x140025997  lea     rcx, [rbp+57h+var_B8]
0x14002599b  call    ?GetUserSid@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetUserSid(std::wstring &)
0x1400259a0  mov     ebx, eax
0x1400259a2  test    eax, eax
0x1400259a4  jns     short loc_1400259CA
0x1400259a6  mov     rcx, [rbp+5Fh]; this
0x1400259aa  mov     r9d, eax; char *
0x1400259ad  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x1400259b4  mov     edx, 4Ch ; 'L'; void *
0x1400259b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400259be  nop
0x1400259bf  lea     rcx, [rbp+57h+var_B8]
0x1400259c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400259c8  jmp     short loc_14002597E
0x1400259ca  cmp     [r15+10h], r13
0x1400259ce  jnz     loc_140025B24
0x1400259d4  mov     [rbp+57h+var_D0], r13
0x1400259d8  mov     rdi, [rsp+130h+var_100]
0x1400259dd  mov     rax, [rdi]
0x1400259e0  mov     rbx, [rax+30h]
0x1400259e4  lea     rcx, [rbp+57h+var_D0]
0x1400259e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400259ed  lea     rdx, [rbp+57h+var_D0]
0x1400259f1  mov     rcx, rdi
0x1400259f4  mov     rax, rbx
0x1400259f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400259fc  mov     ebx, eax
0x1400259fe  test    eax, eax
0x140025a00  jns     short loc_140025A26
0x140025a02  mov     edx, 51h ; 'Q'; void *
0x140025a07  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025a0e  mov     r9d, eax; char *
0x140025a11  mov     rcx, [rbp+5Fh]; this
0x140025a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025a1a  nop
0x140025a1b  lea     rcx, [rbp+57h+var_D0]
0x140025a1f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025a24  jmp     short loc_1400259BF
0x140025a26  mov     esi, 1
0x140025a2b  mov     [rbp+57h+var_C4], esi
0x140025a2e  mov     rcx, [rbp+57h+var_D0]
0x140025a32  test    rcx, rcx
0x140025a35  jz      short loc_140025A52
0x140025a37  mov     rax, [rcx]
0x140025a3a  lea     rdx, [rbp+57h+var_C4]
0x140025a3e  mov     rax, [rax+58h]
0x140025a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025a47  mov     ebx, eax
0x140025a49  test    eax, eax
0x140025a4b  jns     short loc_140025A52
0x140025a4d  lea     edx, [rsi+55h]
0x140025a50  jmp     short loc_140025A07
0x140025a52  mov     [rsp+130h+var_F8], r13
0x140025a57  mov     rdi, [rsp+130h+var_100]
0x140025a5c  mov     rax, [rdi]
0x140025a5f  mov     rbx, [rax+38h]
0x140025a63  lea     rcx, [rsp+130h+var_F8]
0x140025a68  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025a6d  lea     rcx, [rbp+57h+var_B8]
0x140025a71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025a76  mov     [rsp+130h+var_D8], rax
0x140025a7b  lea     rdx, [rsp+130h+var_D8]
0x140025a80  lea     rcx, [rbp+57h+hstringHeader]
0x140025a84  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025a89  nop
0x140025a8a  lea     r8, [rsp+130h+var_F8]
0x140025a8f  mov     rdx, [rax+18h]
0x140025a93  mov     rcx, rdi
0x140025a96  mov     rax, rbx
0x140025a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025a9e  mov     ebx, eax
0x140025aa0  test    eax, eax
0x140025aa2  jns     short loc_140025ACC
0x140025aa4  mov     edx, 5Ah ; 'Z'; void *
0x140025aa9  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025ab0  mov     r9d, eax; char *
0x140025ab3  mov     rcx, [rbp+5Fh]; this
0x140025ab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025abc  nop
0x140025abd  lea     rcx, [rsp+130h+var_F8]
0x140025ac2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025ac7  jmp     loc_140025A1B
0x140025acc  mov     eax, esi
0x140025ace  mov     [rbp+57h+var_C8], eax
0x140025ad1  mov     rcx, [rsp+130h+var_F8]
0x140025ad6  test    rcx, rcx
0x140025ad9  jz      short loc_140025AFB
0x140025adb  mov     rax, [rcx]
0x140025ade  lea     rdx, [rbp+57h+var_C8]
0x140025ae2  mov     rax, [rax+58h]
0x140025ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025aeb  mov     ebx, eax
0x140025aed  test    eax, eax
0x140025aef  jns     short loc_140025AF8
0x140025af1  mov     edx, 5Fh ; '_'
0x140025af6  jmp     short loc_140025AA9
0x140025af8  mov     eax, [rbp+57h+var_C8]
0x140025afb  cmp     [rbp+57h+var_C4], esi
0x140025afe  jnz     short loc_140025B04
0x140025b00  cmp     eax, esi
0x140025b02  jz      short loc_140025B07
0x140025b04  mov     sil, r13b
0x140025b07  mov     [r12], sil
0x140025b0b  lea     rcx, [rsp+130h+var_F8]
0x140025b10  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025b15  nop
0x140025b16  lea     rcx, [rbp+57h+var_D0]
0x140025b1a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025b1f  jmp     loc_140025DDC
0x140025b24  mov     edx, 21h ; '!'
0x140025b29  xor     r8d, r8d
0x140025b2c  mov     rcx, r15
0x140025b2f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x140025b34  mov     r9, rax
0x140025b37  xor     r8d, r8d
0x140025b3a  mov     rdx, r15
0x140025b3d  lea     rcx, [rbp+57h+hstringHeader]
0x140025b41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x140025b46  nop
0x140025b47  mov     [rsp+130h+var_E8], r13
0x140025b4c  mov     rsi, [rsp+130h+var_100]
0x140025b51  mov     rax, [rsi]
0x140025b54  mov     rdi, [rax+58h]
0x140025b58  lea     rcx, [rsp+130h+var_E8]
0x140025b5d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025b62  lea     rcx, [rbp+57h+hstringHeader]
0x140025b66  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025b6b  mov     [rsp+130h+var_D8], rax
0x140025b70  lea     rdx, [rsp+130h+var_D8]
0x140025b75  lea     rcx, [rbp+57h+var_58]
0x140025b79  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025b7e  nop
0x140025b7f  mov     rbx, [rax+18h]
0x140025b83  lea     rcx, [rbp+57h+var_B8]
0x140025b87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025b8c  mov     [rsp+130h+var_D8], rax
0x140025b91  lea     rdx, [rsp+130h+var_D8]
0x140025b96  lea     rcx, [rbp+57h+var_78]
0x140025b9a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025b9f  nop
0x140025ba0  lea     r9, [rsp+130h+var_E8]
0x140025ba5  mov     r8, rbx
0x140025ba8  mov     rdx, [rax+18h]
0x140025bac  mov     rcx, rsi
0x140025baf  mov     rax, rdi
0x140025bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025bb7  mov     r14d, eax
0x140025bba  cmp     eax, 800701C4h
0x140025bbf  jnz     loc_140025D9D
0x140025bc5  mov     [rsp+130h+string], r13
0x140025bca  mov     rcx, r15
0x140025bcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025bd2  mov     [rsp+130h+var_F8], rax
0x140025bd7  lea     rcx, [rsp+130h+var_F8]
0x140025bdc  call    ??$MicPermissionNotProvisioned@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::MicPermissionNotProvisioned<ushort const *>(ushort const * &&)
0x140025be1  mov     rcx, [rsp+130h+string]; string
0x140025be6  call    cs:__imp_WindowsDeleteString
0x140025bec  mov     [rsp+130h+string], r13
0x140025bf1  lea     rcx, [rbp+57h+hstringHeader]
0x140025bf5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025bfa  mov     [rsp+130h+var_F8], rax
0x140025bff  lea     rdx, [rsp+130h+var_F8]
0x140025c04  lea     rcx, [rbp+57h+var_78]
0x140025c08  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025c0d  nop
0x140025c0e  lea     rdx, [rsp+130h+string]; HSTRING *
0x140025c13  mov     rcx, [rax+18h]; HSTRING
0x140025c17  call    ?TryGetPackageFullNameFromFamilyName@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@CAJPEAUHSTRING__@@PEAPEAU6@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::TryGetPackageFullNameFromFamilyName(HSTRING__ *,HSTRING__ * *)
0x140025c1c  mov     ebx, eax
0x140025c1e  test    eax, eax
0x140025c20  jns     short loc_140025C64
0x140025c22  mov     rcx, [rbp+5Fh]; this
0x140025c26  mov     r9d, eax; char *
0x140025c29  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025c30  mov     edx, 6Fh ; 'o'; void *
0x140025c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025c3a  nop
0x140025c3b  mov     rcx, [rsp+130h+string]; string
0x140025c40  call    cs:__imp_WindowsDeleteString
0x140025c46  mov     [rsp+130h+string], r13
0x140025c4b  lea     rcx, [rsp+130h+var_E8]
0x140025c50  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025c55  nop
0x140025c56  lea     rcx, [rbp+57h+hstringHeader]
0x140025c5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025c5f  jmp     loc_1400259BF
0x140025c64  lea     rcx, [rsp+130h+var_D8]
0x140025c69  call    ??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(ushort const *)
0x140025c6e  nop
0x140025c6f  mov     rcx, [rsp+130h+var_D8]
0x140025c74  mov     rax, [rcx]
0x140025c77  mov     rdx, [rsp+130h+string]
0x140025c7c  mov     rax, [rax+108h]
0x140025c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025c88  mov     ebx, eax
0x140025c8a  test    eax, eax
0x140025c8c  jns     short loc_140025CB3
0x140025c8e  mov     rcx, [rbp+5Fh]; this
0x140025c92  mov     r9d, eax; char *
0x140025c95  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025c9c  mov     edx, 71h ; 'q'; void *
0x140025ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025ca6  nop
0x140025ca7  lea     rcx, [rsp+130h+var_D8]
0x140025cac  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140025cb1  jmp     short loc_140025C3B
0x140025cb3  mov     rsi, [rsp+130h+var_100]
0x140025cb8  mov     rax, [rsi]
0x140025cbb  mov     rdi, [rax+58h]
0x140025cbf  lea     rcx, [rsp+130h+var_E8]
0x140025cc4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025cc9  lea     rcx, [rbp+57h+hstringHeader]
0x140025ccd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025cd2  mov     [rsp+130h+var_F8], rax
0x140025cd7  lea     rdx, [rsp+130h+var_F8]
0x140025cdc  lea     rcx, [rbp+57h+var_78]
0x140025ce0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025ce5  nop
0x140025ce6  mov     rbx, [rax+18h]
0x140025cea  lea     rcx, [rbp+57h+var_B8]
0x140025cee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140025cf3  mov     [rsp+130h+var_F8], rax
0x140025cf8  lea     rdx, [rsp+130h+var_F8]
0x140025cfd  lea     rcx, [rbp+57h+var_58]
0x140025d01  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140025d06  nop
0x140025d07  lea     r9, [rsp+130h+var_E8]
0x140025d0c  mov     r8, rbx
0x140025d0f  mov     rdx, [rax+18h]
  ... truncated ...
```
