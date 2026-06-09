# utilToast::ShowToast(void)

- ea: `0x140012a38`
- end: `0x1400132d7`
- name: `?ShowToast@utilToast@@YAJXZ`
- size: `2207`
- prototype: `__int64 __fastcall(utilToast *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140003454`
- `0x140004780`
- `0x140005a8c`
- `0x140006230`
- `0x140007684`
- `0x14000ff44`
- `0x140011010`
- `0x140012870`
- `0x140012938`
- `0x140012a38`
- `0x1400134a0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012deb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012deb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012dfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012dfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012b2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012b2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140012ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140013112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012e48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400130e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012e48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400130e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013205`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012d18`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140012d18`

## pseudocode

```c
__int64 __fastcall utilToast::ShowToast(utilToast *this)
{
  unsigned int v1; // r8d
  HRESULT v2; // eax
  unsigned int v3; // edi
  int ActivationFactory; // eax
  HRESULT v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rdi
  HRESULT v8; // eax
  int v9; // eax
  unsigned int v10; // r8d
  unsigned __int16 *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  unsigned int v17; // r8d
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rdi
  HRESULT v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rdi
  HRESULT v26; // eax
  unsigned int v27; // r8d
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, PVOID); // rbx
  HSTRING_HEADER *v30; // rax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rdx
  __int64 v34; // rax
  __int64 (__fastcall *v35)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, PCWSTR, const wchar_t *, const wchar_t *, const WCHAR **, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *); // rax
  int v36; // eax
  int v38; // [rsp+30h] [rbp-E0h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  __int64 *v40; // [rsp+98h] [rbp-78h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-48h] BYREF
  __int64 *v47; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-18h] BYREF
  unsigned __int16 *v53; // [rsp+100h] [rbp-10h] BYREF
  unsigned __int16 *v54; // [rsp+108h] [rbp-8h] BYREF
  int v55; // [rsp+110h] [rbp+0h] BYREF
  __int16 v56; // [rsp+114h] [rbp+4h]
  UINT32 length; // [rsp+118h] [rbp+8h] BYREF
  const WCHAR *v58; // [rsp+120h] [rbp+10h] BYREF
  int v59; // [rsp+128h] [rbp+18h]
  _QWORD v60[2]; // [rsp+130h] [rbp+20h]
  HSTRING_HEADER hstringHeader; // [rsp+140h] [rbp+30h] BYREF
  HSTRING v62; // [rsp+158h] [rbp+48h] BYREF

  v1 = *(_DWORD *)Feature_MFACheckInClipRenew__descriptor;
  if ( (*(_DWORD *)Feature_MFACheckInClipRenew__descriptor & 4) == 0 )
    v1 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_MFACheckInClipRenew>::GetCachedFeatureEnabledState(
            this,
            &v58);
  v56 = 3;
  v55 = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_140019CB0,
    0x245BA41u,
    (v1 >> 10) & 1,
    (v1 >> 11) & 1,
    (__int64)&v55,
    1u,
    v38);
  v52 = 0;
  v58 = L"page=SettingsPageActivate&target=SystemSettings_Subscription_NeedsSignIn";
  v40 = 0;
  v42 = 0;
  v45 = 0;
  v41 = 0;
  v44 = 0;
  v51 = 0;
  v46 = 0;
  ppv = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  v43 = 0;
  *(_QWORD *)((char *)v60 + 4) = 0;
  v55 = 0;
  length = 0;
  v54 = 0;
  v53 = 0;
  string = 0;
  v2 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v2);
    WindowsDeleteString(string);
    string = 0;
LABEL_5:
    if ( v47 )
    {
      (*(void (__fastcall **)(__int64 *))(*v47 + 16))(v47);
      v47 = 0;
    }
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    if ( v49 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      v49 = 0;
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v46 = 0;
    }
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
    if ( v41 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v41 = 0;
    }
    if ( v45 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v45 = 0;
    }
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
    }
    if ( v40 )
    {
      (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
      v40 = 0;
    }
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    goto LABEL_69;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(*(_QWORD *)ppv + 24LL))(ppv, &v47);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_30;
  v62 = 0;
  v5 = WindowsCreateStringReference(L"Windows.UI.Notifications.ToastNotificationManager", 0x31u, &hstringHeader, &v62);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v62, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v52);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_30;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v52 + 64LL))(v52, 5, &v40);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_30;
  v6 = (__int64)v40;
  v7 = *v40;
  v62 = 0;
  v8 = WindowsCreateStringReference(L"text", 4u, &hstringHeader, &v62);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(v7 + 128))(v6, v62, &v42);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0
    || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 56LL))(
                              v42,
                              0,
                              &v41),
        v3 = ActivationFactory,
        ActivationFactory < 0) )
  {
LABEL_30:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(ActivationFactory);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_31;
  }
  v9 = STRAPI_LoadFromResource(0x78u, &v54);
  v3 = v9;
  if ( v9 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    WindowsDeleteString(string);
    v11 = v54;
    string = 0;
    if ( v54 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    goto LABEL_31;
  }
  v13 = (__int64)v40;
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*v40 + 88);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v54, v10);
  v16 = v14(v13, v15[1].Reserved.Reserved1, &v45);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v45)(
          v45,
          &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
          &v44);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v41 + 176LL))(v41, v44, &v43);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v42 + 56LL))(v42, 1, &v41);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = STRAPI_LoadFromResource(0x79u, &v53);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v18 = (__int64)v40;
  v19 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*v40 + 88);
  v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&v53, v17);
  v16 = v19(v18, v20[1].Reserved.Reserved1, &v45);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v45)(
          v45,
          &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
          &v44);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v41 + 176LL))(v41, v44, &v43);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v21 = (__int64)v40;
  v22 = *v40;
  v62 = 0;
  v23 = WindowsCreateStringReference(L"toast", 5u, &hstringHeader, &v62);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23);
    JUMPOUT(0x1400132D6LL);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(v22 + 128))(v21, v62, &v42);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 56LL))(v42, 0, &v41);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v24 = (__int64)v40;
  v25 = *v40;
  v62 = 0;
  v26 = WindowsCreateStringReference(L"launch", 6u, &hstringHeader, &v62);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26);
    __debugbreak();
  }
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(v25 + 112))(v24, v62, &v46);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v28 = v46;
  v29 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v46 + 72LL);
  v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v58, v27);
  v16 = v29(v28, v30[1].Reserved.Reserved1);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 128LL))(v41, &v49);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v46)(
          v46,
          &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
          &v51);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 72LL))(v49, v51, &v43);
  v3 = v16;
  if ( v16 < 0 )
    goto LABEL_43;
  v16 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v40)(
          v40,
          &GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c,
          &v48);
  v3 = v16;
  if ( v16 < 0
    || (v31 = v48,
        v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL),
        WindowsDeleteString(string),
        string = 0,
        v16 = v32(v31, &string),
        v3 = v16,
        v16 < 0) )
  {
LABEL_43:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    WindowsDeleteString(string);
    string = 0;
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v53);
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v54);
LABEL_31:
    if ( v43 )
    {
      (*(void (**)(void))(*(_QWORD *)v43 + 16LL))();
      v43 = 0;
    }
    goto LABEL_5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  if ( length )
  {
    v59 = v60[1];
    v34 = *v47;
    LODWORD(v60[0]) = 0;
    v35 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, int, PCWSTR, const wchar_t *, const wchar_t *, const WCHAR **, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(v34 + 64);
    v58 = (const WCHAR *)v60[0];
    v36 = v35(
            (__int64)v47,
            L"windows.immersivecontrolpanel_cw5n1h2txyewy",
            L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
            0,
            1,
            StringRawBuffer,
            L"EditionUpgradeTag",
            L"EditionUpgradeGroup",
            &v58,
            0,
            0,
            0,
            0,
            0,
            0,
            &v55);
    v3 = v36;
    if ( v36 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v36);
    WindowsDeleteString(string);
    string = 0;
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v53);
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v54);
    SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v43);
  }
  else
  {
    v3 = -2147418113;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147418113);
    WindowsDeleteString(string);
    string = 0;
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v53);
    SH_SSTRING::~SH_SSTRING((SH_SSTRING *)&v54);
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      v43 = 0;
    }
  }
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>((__int64 *)&v47);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v48);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v49);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>((__int64 *)&ppv);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v46);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v51);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v44);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v41);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v45);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v42);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>((__int64 *)&v40);
  SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>::~SP_COM<Windows::Data::Xml::Dom::IXmlNodeSerializer>(&v52);
LABEL_69:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x140012a38  push    rbp
0x140012a3a  push    rbx
0x140012a3b  push    rsi
0x140012a3c  push    rdi
0x140012a3d  lea     rbp, [rsp-68h]
0x140012a42  sub     rsp, 178h
0x140012a49  mov     rax, cs:__security_cookie
0x140012a50  xor     rax, rsp
0x140012a53  mov     [rbp+80h+var_30], rax
0x140012a57  mov     rax, cs:Feature_MFACheckInClipRenew__descriptor
0x140012a5e  mov     r8d, [rax]
0x140012a61  test    r8b, 4
0x140012a65  jnz     short loc_140012A7A
0x140012a67  lea     rdx, [rbp+80h+var_70]
0x140012a6b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MFACheckInClipRenew@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MFACheckInClipRenew>::GetCachedFeatureEnabledState(void)
0x140012a70  mov     rcx, [rax]
0x140012a73  mov     [rbp+80h+var_90], rcx
0x140012a77  mov     r8d, ecx
0x140012a7a  mov     r9d, r8d
0x140012a7d  mov     dword ptr [rsp+190h+var_168], 1
0x140012a85  shr     r9d, 0Bh
0x140012a89  lea     rax, [rbp+80h+var_80]
0x140012a8d  shr     r8d, 0Ah
0x140012a91  lea     rcx, qword_140019CB0
0x140012a98  xor     esi, esi
0x140012a9a  mov     [rbp+80h+var_7C], 3
0x140012aa0  and     r9d, 1
0x140012aa4  mov     [rbp+80h+var_80], esi
0x140012aa7  and     r8d, 1
0x140012aab  mov     [rsp+190h+ppv], rax
0x140012ab0  mov     edx, 245BA41h
0x140012ab5  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140012aba  lea     rax, aPageSettingspa; "page=SettingsPageActivate&target=System"...
0x140012ac1  mov     [rbp+80h+var_98], rsi
0x140012ac5  mov     [rbp+80h+var_70], rax
0x140012ac9  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x140012ad0  lea     rax, [rbp+80h+var_A8]
0x140012ad4  mov     [rbp+80h+var_F8], rsi
0x140012ad8  xor     edx, edx; pUnkOuter
0x140012ada  mov     [rsp+190h+ppv], rax; ppv
0x140012adf  lea     r8d, [rsi+4]; dwClsContext
0x140012ae3  mov     [rbp+80h+var_E8], rsi
0x140012ae7  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x140012aee  mov     [rbp+80h+var_D0], rsi
0x140012af2  mov     [rbp+80h+var_F0], rsi
0x140012af6  mov     [rbp+80h+var_D8], rsi
0x140012afa  mov     [rbp+80h+var_A0], rsi
0x140012afe  mov     [rbp+80h+var_C8], rsi
0x140012b02  mov     [rbp+80h+var_A8], rsi
0x140012b06  mov     [rbp+80h+var_B0], rsi
0x140012b0a  mov     [rbp+80h+var_B8], rsi
0x140012b0e  mov     [rbp+80h+var_C0], rsi
0x140012b12  mov     [rbp+80h+var_E0], rsi
0x140012b16  mov     qword ptr [rbp+80h+var_60+4], rsi
0x140012b1a  mov     [rbp+80h+var_80], esi
0x140012b1d  mov     [rbp+80h+length], esi
0x140012b20  mov     [rbp+80h+var_88], rsi
0x140012b24  mov     [rbp+80h+var_90], rsi
0x140012b28  mov     [rbp+80h+string], rsi
0x140012b2c  call    cs:__imp_CoCreateInstance
0x140012b32  mov     edi, eax
0x140012b34  test    eax, eax
0x140012b36  jns     loc_140012C9B
0x140012b3c  mov     ecx, eax
0x140012b3e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012b43  mov     rcx, [rbp+80h+string]; string
0x140012b47  call    cs:__imp_WindowsDeleteString
0x140012b4d  mov     rcx, [rbp+80h+var_E0]
0x140012b51  mov     [rbp+80h+string], rsi
0x140012b55  test    rcx, rcx
0x140012b58  jz      short loc_140012B6A
0x140012b5a  mov     rdx, [rcx]
0x140012b5d  mov     rax, [rdx+10h]
0x140012b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b66  mov     [rbp+80h+var_E0], rsi
0x140012b6a  mov     rcx, [rbp+80h+var_C0]
0x140012b6e  test    rcx, rcx
0x140012b71  jz      short loc_140012B83
0x140012b73  mov     rax, [rcx]
0x140012b76  mov     rax, [rax+10h]
0x140012b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b7f  mov     [rbp+80h+var_C0], rsi
0x140012b83  mov     rcx, [rbp+80h+var_B8]
0x140012b87  test    rcx, rcx
0x140012b8a  jz      short loc_140012B9C
0x140012b8c  mov     rax, [rcx]
0x140012b8f  mov     rax, [rax+10h]
0x140012b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b98  mov     [rbp+80h+var_B8], rsi
0x140012b9c  mov     rcx, [rbp+80h+var_B0]
0x140012ba0  test    rcx, rcx
0x140012ba3  jz      short loc_140012BB5
0x140012ba5  mov     rax, [rcx]
0x140012ba8  mov     rax, [rax+10h]
0x140012bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bb1  mov     [rbp+80h+var_B0], rsi
0x140012bb5  mov     rcx, [rbp+80h+var_A8]
0x140012bb9  test    rcx, rcx
0x140012bbc  jz      short loc_140012BCE
0x140012bbe  mov     rax, [rcx]
0x140012bc1  mov     rax, [rax+10h]
0x140012bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bca  mov     [rbp+80h+var_A8], rsi
0x140012bce  mov     rcx, [rbp+80h+var_C8]
0x140012bd2  test    rcx, rcx
0x140012bd5  jz      short loc_140012BE7
0x140012bd7  mov     rax, [rcx]
0x140012bda  mov     rax, [rax+10h]
0x140012bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012be3  mov     [rbp+80h+var_C8], rsi
0x140012be7  mov     rcx, [rbp+80h+var_A0]
0x140012beb  test    rcx, rcx
0x140012bee  jz      short loc_140012C00
0x140012bf0  mov     rax, [rcx]
0x140012bf3  mov     rax, [rax+10h]
0x140012bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bfc  mov     [rbp+80h+var_A0], rsi
0x140012c00  mov     rcx, [rbp+80h+var_D8]
0x140012c04  test    rcx, rcx
0x140012c07  jz      short loc_140012C19
0x140012c09  mov     rax, [rcx]
0x140012c0c  mov     rax, [rax+10h]
0x140012c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c15  mov     [rbp+80h+var_D8], rsi
0x140012c19  mov     rcx, [rbp+80h+var_F0]
0x140012c1d  test    rcx, rcx
0x140012c20  jz      short loc_140012C32
0x140012c22  mov     rax, [rcx]
0x140012c25  mov     rax, [rax+10h]
0x140012c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c2e  mov     [rbp+80h+var_F0], rsi
0x140012c32  mov     rcx, [rbp+80h+var_D0]
0x140012c36  test    rcx, rcx
0x140012c39  jz      short loc_140012C4B
0x140012c3b  mov     rax, [rcx]
0x140012c3e  mov     rax, [rax+10h]
0x140012c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c47  mov     [rbp+80h+var_D0], rsi
0x140012c4b  mov     rcx, [rbp+80h+var_E8]
0x140012c4f  test    rcx, rcx
0x140012c52  jz      short loc_140012C64
0x140012c54  mov     rax, [rcx]
0x140012c57  mov     rax, [rax+10h]
0x140012c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c60  mov     [rbp+80h+var_E8], rsi
0x140012c64  mov     rcx, [rbp+80h+var_F8]
0x140012c68  test    rcx, rcx
0x140012c6b  jz      short loc_140012C7D
0x140012c6d  mov     rax, [rcx]
0x140012c70  mov     rax, [rax+10h]
0x140012c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c79  mov     [rbp+80h+var_F8], rsi
0x140012c7d  mov     rcx, [rbp+80h+var_98]
0x140012c81  test    rcx, rcx
0x140012c84  jz      loc_140013296
0x140012c8a  mov     rax, [rcx]
0x140012c8d  mov     rax, [rax+10h]
0x140012c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c96  jmp     loc_140013296
0x140012c9b  mov     rcx, [rbp+80h+var_A8]
0x140012c9f  lea     rdx, [rbp+80h+var_C0]
0x140012ca3  mov     rax, [rcx]
0x140012ca6  mov     rax, [rax+18h]
0x140012caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012caf  mov     edi, eax
0x140012cb1  test    eax, eax
0x140012cb3  jns     short loc_140012CE3
0x140012cb5  mov     ecx, eax
0x140012cb7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012cbc  mov     rcx, [rbp+80h+string]; string
0x140012cc0  call    cs:__imp_WindowsDeleteString
0x140012cc6  mov     [rbp+80h+string], rsi
0x140012cca  mov     rcx, [rbp+80h+var_E0]
0x140012cce  test    rcx, rcx
0x140012cd1  jz      loc_140012B6A
0x140012cd7  mov     rax, [rcx]
0x140012cda  mov     rax, [rax+10h]
0x140012cde  jmp     loc_140012B61
0x140012ce3  lea     r9, [rbp+80h+var_38]; string
0x140012ce7  mov     [rbp+80h+var_38], rsi
0x140012ceb  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x140012cef  mov     edx, 31h ; '1'; length
0x140012cf4  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x140012cfb  call    cs:__imp_WindowsCreateStringReference
0x140012d01  test    eax, eax
0x140012d03  js      loc_1400132BF
0x140012d09  mov     rcx, [rbp+80h+var_38]
0x140012d0d  lea     r8, [rbp+80h+var_98]
0x140012d11  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x140012d18  call    cs:__imp_RoGetActivationFactory
0x140012d1e  mov     edi, eax
0x140012d20  test    eax, eax
0x140012d22  js      short loc_140012CB5
0x140012d24  mov     rcx, [rbp+80h+var_98]
0x140012d28  lea     r8, [rbp+80h+var_F8]
0x140012d2c  mov     edx, 5
0x140012d31  mov     rax, [rcx]
0x140012d34  mov     rax, [rax+40h]
0x140012d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d3d  mov     edi, eax
0x140012d3f  test    eax, eax
0x140012d41  js      loc_140012CB5
0x140012d47  mov     rbx, [rbp+80h+var_F8]
0x140012d4b  lea     r9, [rbp+80h+var_38]; string
0x140012d4f  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x140012d53  mov     edx, 4; length
0x140012d58  lea     rcx, sourceString; "text"
0x140012d5f  mov     rdi, [rbx]
0x140012d62  mov     [rbp+80h+var_38], rsi
0x140012d66  call    cs:__imp_WindowsCreateStringReference
0x140012d6c  test    eax, eax
0x140012d6e  js      loc_1400132C7
0x140012d74  mov     rdx, [rbp+80h+var_38]
0x140012d78  lea     r8, [rbp+80h+var_E8]
0x140012d7c  mov     rax, [rdi+80h]
0x140012d83  mov     rcx, rbx
0x140012d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d8b  mov     edi, eax
0x140012d8d  test    eax, eax
0x140012d8f  js      loc_140012CB5
0x140012d95  mov     rcx, [rbp+80h+var_E8]
0x140012d99  lea     r8, [rbp+80h+var_F0]
0x140012d9d  xor     edx, edx
0x140012d9f  mov     rax, [rcx]
0x140012da2  mov     rax, [rax+38h]
0x140012da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dab  mov     edi, eax
0x140012dad  test    eax, eax
0x140012daf  js      loc_140012CB5
0x140012db5  lea     rdx, [rbp+80h+var_88]; unsigned __int16 **
0x140012db9  mov     ecx, 78h ; 'x'; unsigned int
0x140012dbe  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x140012dc3  mov     edi, eax
0x140012dc5  test    eax, eax
0x140012dc7  jns     short loc_140012E0C
0x140012dc9  mov     ecx, eax
0x140012dcb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012dd0  mov     rcx, [rbp+80h+string]; string
0x140012dd4  call    cs:__imp_WindowsDeleteString
0x140012dda  mov     rbx, [rbp+80h+var_88]
0x140012dde  mov     [rbp+80h+string], rsi
0x140012de2  test    rbx, rbx
0x140012de5  jz      loc_140012CCA
0x140012deb  call    cs:__imp_GetProcessHeap
0x140012df1  lea     r8, [rbx-4]; lpMem
0x140012df5  xor     edx, edx; dwFlags
0x140012df7  mov     rcx, rax; hHeap
0x140012dfa  call    cs:__imp_HeapFree
0x140012e00  xor     ecx, ecx
0x140012e02  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140012e07  jmp     loc_140012CCA
0x140012e0c  mov     rdi, [rbp+80h+var_F8]
0x140012e10  lea     rdx, [rbp+80h+var_88]
0x140012e14  lea     rcx, [rbp+80h+hstringHeader]
0x140012e18  mov     rax, [rdi]
0x140012e1b  mov     rbx, [rax+58h]
0x140012e1f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140012e24  lea     r8, [rbp+80h+var_D0]
0x140012e28  mov     rcx, rdi
0x140012e2b  mov     rdx, [rax+18h]
0x140012e2f  mov     rax, rbx
0x140012e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e37  mov     edi, eax
0x140012e39  test    eax, eax
0x140012e3b  jns     short loc_140012E69
0x140012e3d  mov     ecx, eax
0x140012e3f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140012e44  mov     rcx, [rbp+80h+string]; string
0x140012e48  call    cs:__imp_WindowsDeleteString
0x140012e4e  lea     rcx, [rbp+80h+var_90]; this
0x140012e52  mov     [rbp+80h+string], rsi
0x140012e56  call    ??1SH_SSTRING@@QEAA@XZ; SH_SSTRING::~SH_SSTRING(void)
0x140012e5b  lea     rcx, [rbp+80h+var_88]; this
0x140012e5f  call    ??1SH_SSTRING@@QEAA@XZ; SH_SSTRING::~SH_SSTRING(void)
0x140012e64  jmp     loc_140012CCA
0x140012e69  mov     rcx, [rbp+80h+var_D0]
0x140012e6d  lea     r8, [rbp+80h+var_D8]
0x140012e71  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x140012e78  mov     rax, [rcx]
0x140012e7b  mov     rax, [rax]
0x140012e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e83  mov     edi, eax
0x140012e85  test    eax, eax
0x140012e87  js      short loc_140012E3D
0x140012e89  mov     rcx, [rbp+80h+var_F0]
0x140012e8d  lea     r8, [rbp+80h+var_E0]
0x140012e91  mov     rdx, [rbp+80h+var_D8]
0x140012e95  mov     rax, [rcx]
0x140012e98  mov     rax, [rax+0B0h]
0x140012e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ea4  mov     edi, eax
0x140012ea6  test    eax, eax
0x140012ea8  js      short loc_140012E3D
0x140012eaa  mov     rcx, [rbp+80h+var_E8]
0x140012eae  lea     r8, [rbp+80h+var_F0]
0x140012eb2  mov     edx, 1
0x140012eb7  mov     rax, [rcx]
0x140012eba  mov     rax, [rax+38h]
0x140012ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ec3  mov     edi, eax
  ... truncated ...
```
