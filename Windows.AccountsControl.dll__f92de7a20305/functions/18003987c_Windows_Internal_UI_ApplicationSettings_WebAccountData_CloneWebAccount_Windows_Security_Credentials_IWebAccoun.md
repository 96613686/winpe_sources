# Windows::Internal::UI::ApplicationSettings::WebAccountData::CloneWebAccount(Windows::Security::Credentials::IWebAccount *,Windows::Security::Credentials::IWebAccount * *)

- ea: `0x18003987c`
- end: `0x180039f2c`
- name: `?CloneWebAccount@WebAccountData@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccount@Credentials@Security@5@PEAPEAU6785@@Z`
- size: `1712`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::WebAccountData *__hidden this, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccount **)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037dd8`
- `0x180037eec`
- `0x180038128`
- `0x18003bf1c`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x1800083a8`
- `0x180008e2c`
- `0x18000e87c`
- `0x180011f64`
- `0x180011ffc`
- `0x180018f90`
- `0x180038f9c`
- `0x18003987c`
- `0x180067f50`
- `0x1800680a0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800399aa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800399aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039ec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180039bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180039bb0`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039c70`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039cfc`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039e52`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039c70`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039cfc`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180039e52`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800399cd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800399cd`

## string_xrefs

- `0x180039ca3`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18003998a`: `Windows.Internal.Security.Credentials.WebAccountInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::WebAccountData::CloneWebAccount(
        HSTRING *this,
        void (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *),
        struct Windows::Security::Credentials::IWebAccount **a3)
{
  void (__fastcall *v6)(struct Windows::Security::Credentials::IWebAccount *, GUID *, __int64 *); // rbx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rbx
  HSTRING v10; // rbx
  int ActivationFactory; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, __int64 *); // rbx
  int IsCallingProcessAppContainer; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  __int64 (__fastcall *v20)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  unsigned __int16 **v23; // rdx
  int CallingProcessPackageFamilyName; // eax
  __int64 (__fastcall *v25)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  HRESULT v26; // eax
  __int64 v27; // rdx
  IUnknown *v28; // rbx
  int v29; // eax
  int v30; // edi
  HRESULT v31; // eax
  __int64 v32; // r14
  __int64 (__fastcall *v33)(__int64, __int64, _QWORD, HSTRING); // rsi
  HSTRING v34; // rdi
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r14
  __int64 (__fastcall *v38)(__int64, HSTRING *); // rsi
  HRESULT v39; // eax
  int *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HSTRING v43; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v44[8]; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  int v49[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h]
  unsigned int v54; // [rsp+88h] [rbp-78h] BYREF
  __int64 v55; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v56[2]; // [rsp+98h] [rbp-68h] BYREF
  char v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-50h] BYREF
  IUnknown *ppOldObject; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER v62; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *a3 = 0;
  v55 = 0;
  *(_QWORD *)v49 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v49);
  v6 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v6((struct Windows::Security::Credentials::IWebAccount *)a2, &GUID_ad7b0e08_6151_4da3_b6ba_890936053b0e, &v55);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
  v58 = 0;
  v54 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v55 + 32LL))(v55, &v58, &v54);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v7,
      (int)v41);
    goto LABEL_53;
  }
  v9 = v55;
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 8LL))(v55);
  v53 = v58;
  v56[0] = v9;
  v52 = 0;
  v56[1] = v58;
  v57 = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v46 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.Credentials.WebAccountInternal",
         0x38u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v10 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_067cd3b2_1f07_4710_8ae5_5cd2e71efc11, &v46);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v41);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    wil::details::ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___::_ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___(v56);
    goto LABEL_53;
  }
  v47 = 0;
  v12 = v46;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v46 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  IsCallingProcessAppContainer = v13(v12, v54, v58, &v47);
  v8 = IsCallingProcessAppContainer;
  if ( IsCallingProcessAppContainer < 0 )
  {
    v16 = 358;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)IsCallingProcessAppContainer,
      (int)v41);
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_9;
  }
  v44[0] = 0;
  IsCallingProcessAppContainer = CallerIdentity::IsCallingProcessAppContainer(v15, v44);
  v8 = IsCallingProcessAppContainer;
  if ( IsCallingProcessAppContainer < 0 )
  {
    v16 = 363;
    goto LABEL_12;
  }
  v48 = 0;
  *(_QWORD *)v49 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v49);
  v8 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
         v49,
         &v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    goto LABEL_13;
  }
  v43 = 0;
  v17 = v48;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL);
  WindowsDeleteString(0);
  v43 = 0;
  v19 = v18(v17, &v43);
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v19,
      (int)v41);
LABEL_21:
    WindowsDeleteString(v43);
    v43 = 0;
    goto LABEL_18;
  }
  v45 = 0;
  v20 = (__int64 (__fastcall *)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(*a2)[7];
  WindowsDeleteString(0);
  v45 = 0;
  v21 = v20((struct Windows::Security::Credentials::IWebAccount *)a2, &v45);
  v8 = v21;
  if ( v21 < 0 )
  {
    v22 = 374;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v21,
      (int)v41);
LABEL_25:
    WindowsDeleteString(v45);
    v45 = 0;
    goto LABEL_21;
  }
  if ( !v44[0] || !v43 || !WindowsIsStringEmpty(v45) )
    goto LABEL_50;
  string = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
  hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
  CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName((CallerIdentity *)&string, v23);
  v8 = CallingProcessPackageFamilyName;
  if ( CallingProcessPackageFamilyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)CallingProcessPackageFamilyName,
      (int)v41);
LABEL_31:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
    goto LABEL_25;
  }
  v50 = 0;
  v25 = (__int64 (__fastcall *)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*a2)[6];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v26 = v25((struct Windows::Security::Credentials::IWebAccount *)a2, &v50);
  v8 = v26;
  if ( v26 < 0 )
  {
    v27 = 384;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v26,
      (int)v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    goto LABEL_31;
  }
  ppOldObject = 0;
  v26 = CoSwitchCallContext(0, &ppOldObject);
  v8 = v26;
  if ( v26 < 0 )
  {
    v27 = 392;
    goto LABEL_34;
  }
  v28 = ppOldObject;
  v52 = ppOldObject;
  LOBYTE(v53) = 1;
  v51 = 0;
  v63 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v62,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v29 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
          v63,
          &v51);
  v30 = v29;
  if ( v29 >= 0 )
  {
    *(_QWORD *)v49 = 0;
    v32 = v51;
    v33 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING))(*(_QWORD *)v51 + 88LL);
    v34 = v43;
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62);
    v41 = v49;
    v30 = v33(v32, v50, *(_QWORD *)(v35 + 24), v34);
    if ( v30 < 0 )
    {
      v36 = 405;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
        (const char *)(unsigned int)v30,
        (int)v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
      goto LABEL_39;
    }
    v37 = *(_QWORD *)v49;
    v38 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v49 + 56LL);
    WindowsDeleteString(this[11]);
    this[11] = 0;
    v30 = v38(v37, this + 11);
    if ( v30 < 0 )
    {
      v36 = 406;
      goto LABEL_44;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v52 = 0;
    v39 = CoSwitchCallContext(v28, &v52);
    if ( v39 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
        (const char *)(unsigned int)v39,
        (int)v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
LABEL_50:
    v21 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v47 + 48LL))(
            v47,
            a3);
    v8 = v21;
    if ( v21 >= 0 )
    {
      WindowsDeleteString(v45);
      v45 = 0;
      WindowsDeleteString(v43);
      v43 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      wil::details::ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___::_ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___(v56);
      v8 = 0;
      goto LABEL_53;
    }
    v22 = 409;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
    (const char *)(unsigned int)v29,
    (int)v41);
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v52 = 0;
  v31 = CoSwitchCallContext(v28, &v52);
  if ( v31 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\dataobjects.cpp",
      (const char *)(unsigned int)v31,
      v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(v43);
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  wil::details::ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___::_ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___(v56);
  v8 = v30;
LABEL_53:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003987c  mov     [rsp-8+arg_18], rbx
0x180039881  push    rbp
0x180039882  push    rsi
0x180039883  push    rdi
0x180039884  push    r12
0x180039886  push    r13
0x180039888  push    r14
0x18003988a  push    r15
0x18003988c  lea     rbp, [rsp-10h]
0x180039891  sub     rsp, 110h
0x180039898  mov     rax, cs:__security_cookie
0x18003989f  xor     rax, rsp
0x1800398a2  mov     [rbp+40h+var_40], rax
0x1800398a6  mov     r15, r8
0x1800398a9  mov     rsi, rdx
0x1800398ac  mov     r13, rcx
0x1800398af  xor     r12d, r12d
0x1800398b2  mov     [r8], r12
0x1800398b5  mov     [rbp+40h+var_B0], r12
0x1800398b9  mov     qword ptr [rsp+140h+var_E0], rdx
0x1800398be  lea     rcx, [rsp+140h+var_E0]
0x1800398c3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800398c8  nop
0x1800398c9  mov     rax, [rsi]
0x1800398cc  mov     rbx, [rax]
0x1800398cf  lea     rcx, [rbp+40h+var_B0]
0x1800398d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800398d8  lea     r8, [rbp+40h+var_B0]
0x1800398dc  lea     rdx, _GUID_ad7b0e08_6151_4da3_b6ba_890936053b0e
0x1800398e3  mov     rcx, rsi
0x1800398e6  mov     rax, rbx
0x1800398e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398ee  nop
0x1800398ef  lea     rcx, [rsp+140h+var_E0]
0x1800398f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800398f9  mov     [rbp+40h+var_90], r12
0x1800398fd  mov     [rbp+40h+var_B8], r12d
0x180039901  mov     rcx, [rbp+40h+var_B0]
0x180039905  mov     rax, [rcx]
0x180039908  lea     r8, [rbp+40h+var_B8]
0x18003990c  lea     rdx, [rbp+40h+var_90]
0x180039910  mov     rax, [rax+20h]
0x180039914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039919  mov     ebx, eax
0x18003991b  test    eax, eax
0x18003991d  jns     short loc_18003993C
0x18003991f  mov     rcx, [rbp+48h]; this
0x180039923  mov     r9d, eax; char *
0x180039926  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003992d  mov     edx, 153h; void *
0x180039932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039937  jmp     loc_180039EFA
0x18003993c  mov     rbx, [rbp+40h+var_B0]
0x180039940  test    rbx, rbx
0x180039943  jz      short loc_180039955
0x180039945  mov     rax, [rbx]
0x180039948  mov     rcx, rbx
0x18003994b  mov     rax, [rax+8]
0x18003994f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039954  nop
0x180039955  mov     rax, [rbp+40h+var_90]
0x180039959  mov     [rbp+40h+var_C0], rax
0x18003995d  mov     [rbp+40h+var_A8], rbx
0x180039961  mov     [rsp+140h+var_C8], r12
0x180039966  mov     [rbp+40h+var_A0], rax
0x18003996a  mov     [rbp+40h+var_98], 1
0x18003996e  lea     rcx, [rsp+140h+var_C8]
0x180039973  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039978  mov     [rsp+140h+var_F8], r12
0x18003997d  lea     r9, [rbp+40h+string]; string
0x180039981  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180039985  mov     edx, 38h ; '8'; length
0x18003998a  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Credentials_WebAccountInternal@@3QBGB; "Windows.Internal.Security.Credentials.W"...
0x180039991  call    cs:__imp_WindowsCreateStringReference
0x180039997  test    eax, eax
0x180039999  jns     short loc_1800399B0
0x18003999b  xor     r9d, r9d; lpArguments
0x18003999e  xor     r8d, r8d; nNumberOfArguments
0x1800399a1  lea     edx, [r9+1]; dwExceptionFlags
0x1800399a5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800399aa  call    cs:__imp_RaiseException
0x1800399b0  mov     rbx, [rbp+40h+string]
0x1800399b4  lea     rcx, [rsp+140h+var_F8]
0x1800399b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800399be  lea     r8, [rsp+140h+var_F8]
0x1800399c3  lea     rdx, _GUID_067cd3b2_1f07_4710_8ae5_5cd2e71efc11
0x1800399ca  mov     rcx, rbx
0x1800399cd  call    cs:__imp_RoGetActivationFactory
0x1800399d3  mov     ebx, eax
0x1800399d5  test    eax, eax
0x1800399d7  jns     short loc_180039A0B
0x1800399d9  mov     rcx, [rbp+48h]; this
0x1800399dd  mov     r9d, eax; char *
0x1800399e0  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800399e7  mov     edx, 160h; void *
0x1800399ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800399f1  nop
0x1800399f2  lea     rcx, [rsp+140h+var_F8]
0x1800399f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800399fc  nop
0x1800399fd  lea     rcx, [rbp+40h+var_A8]
0x180039a01  call    wil__details__ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff______ScopeExitFn__lambda_85c679a2d346a142e884477064cb89ff___
0x180039a06  jmp     loc_180039EFA
0x180039a0b  mov     [rsp+140h+var_F0], r12
0x180039a10  mov     rdi, [rsp+140h+var_F8]
0x180039a15  mov     rax, [rdi]
0x180039a18  mov     rbx, [rax+38h]
0x180039a1c  lea     rcx, [rsp+140h+var_F0]
0x180039a21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039a26  lea     r9, [rsp+140h+var_F0]
0x180039a2b  mov     r8, [rbp+40h+var_90]
0x180039a2f  mov     edx, [rbp+40h+var_B8]
0x180039a32  mov     rcx, rdi
0x180039a35  mov     rax, rbx
0x180039a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a3d  mov     ebx, eax
0x180039a3f  test    eax, eax
0x180039a41  jns     short loc_180039A68
0x180039a43  mov     edx, 166h; void *
0x180039a48  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039a4f  mov     r9d, eax; char *
0x180039a52  mov     rcx, [rbp+48h]; this
0x180039a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a5b  nop
0x180039a5c  lea     rcx, [rsp+140h+var_F0]
0x180039a61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039a66  jmp     short loc_1800399F2
0x180039a68  mov     [rsp+140h+var_108], r12b
0x180039a6d  lea     rdx, [rsp+140h+var_108]
0x180039a72  call    ?IsCallingProcessAppContainer@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEA_N@Z; CallerIdentity::IsCallingProcessAppContainer(RUNTIMEBROKER_CALLERIDENTITY_CHECK,bool *)
0x180039a77  mov     ebx, eax
0x180039a79  test    eax, eax
0x180039a7b  jns     short loc_180039A84
0x180039a7d  mov     edx, 16Bh
0x180039a82  jmp     short loc_180039A48
0x180039a84  mov     [rsp+140h+var_E8], r12
0x180039a89  mov     qword ptr [rsp+140h+var_E0], rsi
0x180039a8e  lea     rcx, [rsp+140h+var_E0]
0x180039a93  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180039a98  lea     rdx, [rsp+140h+var_E8]
0x180039a9d  lea     rcx, [rsp+140h+var_E0]
0x180039aa2  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x180039aa7  mov     ebx, eax
0x180039aa9  lea     rcx, [rsp+140h+var_E0]
0x180039aae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039ab3  test    ebx, ebx
0x180039ab5  jns     short loc_180039ADC
0x180039ab7  mov     rcx, [rbp+48h]; this
0x180039abb  mov     r9d, ebx; char *
0x180039abe  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039ac5  mov     edx, 16Fh; void *
0x180039aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039acf  nop
0x180039ad0  lea     rcx, [rsp+140h+var_E8]
0x180039ad5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039ada  jmp     short loc_180039A5C
0x180039adc  mov     [rsp+140h+var_110], r12
0x180039ae1  mov     rdi, [rsp+140h+var_E8]
0x180039ae6  mov     rax, [rdi]
0x180039ae9  mov     rbx, [rax+30h]
0x180039aed  xor     ecx, ecx; string
0x180039aef  call    cs:__imp_WindowsDeleteString
0x180039af5  mov     [rsp+140h+var_110], r12
0x180039afa  lea     rdx, [rsp+140h+var_110]
0x180039aff  mov     rcx, rdi
0x180039b02  mov     rax, rbx
0x180039b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b0a  mov     ebx, eax
0x180039b0c  test    eax, eax
0x180039b0e  jns     short loc_180039B3B
0x180039b10  mov     rcx, [rbp+48h]; this
0x180039b14  mov     r9d, eax; char *
0x180039b17  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039b1e  mov     edx, 171h; void *
0x180039b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b28  nop
0x180039b29  mov     rcx, [rsp+140h+var_110]; string
0x180039b2e  call    cs:__imp_WindowsDeleteString
0x180039b34  mov     [rsp+140h+var_110], r12
0x180039b39  jmp     short loc_180039AD0
0x180039b3b  mov     [rsp+140h+var_100], r12
0x180039b40  mov     rax, [rsi]
0x180039b43  mov     rbx, [rax+38h]
0x180039b47  xor     ecx, ecx; string
0x180039b49  call    cs:__imp_WindowsDeleteString
0x180039b4f  mov     [rsp+140h+var_100], r12
0x180039b54  lea     rdx, [rsp+140h+var_100]
0x180039b59  mov     rcx, rsi
0x180039b5c  mov     rax, rbx
0x180039b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b64  mov     ebx, eax
0x180039b66  test    eax, eax
0x180039b68  jns     short loc_180039B95
0x180039b6a  mov     edx, 176h; void *
0x180039b6f  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039b76  mov     r9d, eax; char *
0x180039b79  mov     rcx, [rbp+48h]; this
0x180039b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b82  nop
0x180039b83  mov     rcx, [rsp+140h+var_100]; string
0x180039b88  call    cs:__imp_WindowsDeleteString
0x180039b8e  mov     [rsp+140h+var_100], r12
0x180039b93  jmp     short loc_180039B29
0x180039b95  cmp     [rsp+140h+var_108], r12b
0x180039b9a  jz      loc_180039E89
0x180039ba0  cmp     [rsp+140h+var_110], r12
0x180039ba5  jz      loc_180039E89
0x180039bab  mov     rcx, [rsp+140h+var_100]; string
0x180039bb0  call    cs:__imp_WindowsIsStringEmpty
0x180039bb6  test    eax, eax
0x180039bb8  jz      loc_180039E89
0x180039bbe  mov     [rbp+40h+string], r12
0x180039bc2  mov     qword ptr [rbp+40h+hstringHeader.Reserved], r12
0x180039bc6  mov     qword ptr [rbp+40h+hstringHeader.Reserved+8], r12
0x180039bca  lea     rcx, [rbp+40h+string]
0x180039bce  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180039bd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039bd7  mov     qword ptr [rbp+40h+hstringHeader.Reserved], rax
0x180039bdb  mov     qword ptr [rbp+40h+hstringHeader.Reserved+8], rax
0x180039bdf  lea     rcx, [rbp+40h+string]; this
0x180039be3  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x180039be8  mov     ebx, eax
0x180039bea  test    eax, eax
0x180039bec  jns     short loc_180039C15
0x180039bee  mov     rcx, [rbp+48h]; this
0x180039bf2  mov     r9d, eax; char *
0x180039bf5  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039bfc  mov     edx, 17Ch; void *
0x180039c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c06  nop
0x180039c07  lea     rcx, [rbp+40h+string]
0x180039c0b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180039c10  jmp     loc_180039B83
0x180039c15  mov     [rsp+140h+var_D8], r12
0x180039c1a  mov     rax, [rsi]
0x180039c1d  mov     rbx, [rax+30h]
0x180039c21  lea     rcx, [rsp+140h+var_D8]
0x180039c26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039c2b  lea     rdx, [rsp+140h+var_D8]
0x180039c30  mov     rcx, rsi
0x180039c33  mov     rax, rbx
0x180039c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c3b  mov     ebx, eax
0x180039c3d  test    eax, eax
0x180039c3f  jns     short loc_180039C66
0x180039c41  mov     edx, 180h; void *
0x180039c46  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039c4d  mov     r9d, eax; char *
0x180039c50  mov     rcx, [rbp+48h]; this
0x180039c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c59  nop
0x180039c5a  lea     rcx, [rsp+140h+var_D8]
0x180039c5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039c64  jmp     short loc_180039C07
0x180039c66  mov     [rbp+40h+ppOldObject], r12
0x180039c6a  lea     rdx, [rbp+40h+ppOldObject]; ppOldObject
0x180039c6e  xor     ecx, ecx; pNewObject
0x180039c70  call    cs:__imp_CoSwitchCallContext
0x180039c76  mov     ebx, eax
0x180039c78  test    eax, eax
0x180039c7a  jns     short loc_180039C83
0x180039c7c  mov     edx, 188h
0x180039c81  jmp     short loc_180039C46
0x180039c83  mov     rbx, [rbp+40h+ppOldObject]
0x180039c87  mov     [rsp+140h+var_C8], rbx
0x180039c8c  mov     byte ptr [rbp+40h+var_C0], 1
0x180039c90  mov     [rsp+140h+var_D0], r12
0x180039c95  mov     [rbp+40h+var_48], r12
0x180039c99  mov     r9d, 40h ; '@'; unsigned int
0x180039c9f  lea     r8d, [r9+1]; unsigned int
0x180039ca3  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180039caa  lea     rcx, [rbp+40h+var_60]; hstringHeader
0x180039cae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180039cb3  lea     rdx, [rsp+140h+var_D0]
0x180039cb8  mov     rcx, [rbp+40h+var_48]
0x180039cbc  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x180039cc1  mov     edi, eax
0x180039cc3  test    eax, eax
0x180039cc5  jns     loc_180039D85
0x180039ccb  mov     rcx, [rbp+48h]; this
0x180039ccf  mov     r9d, eax; char *
0x180039cd2  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039cd9  mov     edx, 193h; void *
0x180039cde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ce3  nop
0x180039ce4  lea     rcx, [rsp+140h+var_D0]
0x180039ce9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039cee  nop
0x180039cef  mov     [rsp+140h+var_C8], r12
0x180039cf4  lea     rdx, [rsp+140h+var_C8]; ppOldObject
0x180039cf9  mov     rcx, rbx; pNewObject
0x180039cfc  call    cs:__imp_CoSwitchCallContext
0x180039d02  test    eax, eax
0x180039d04  jns     short loc_180039D1F
0x180039d06  mov     rcx, [rbp+48h]; this
0x180039d0a  mov     r9d, eax; char *
0x180039d0d  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\accountscontrol\\api"...
0x180039d14  mov     edx, 18Eh; void *
0x180039d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d1e  nop
  ... truncated ...
```
