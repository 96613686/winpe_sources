# DdcMobileNetworksHelper::FormatNetworkCode(RILNETWORKCODE *,ulong,Windows::Data::Json::IJsonObject *)

- ea: `0x180023180`
- end: `0x180023c5c`
- name: `?FormatNetworkCode@DdcMobileNetworksHelper@@CAJPEAURILNETWORKCODE@@KPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `2780`
- prototype: `__int64 __fastcall(struct RILNETWORKCODE *, int, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022240`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013a58`
- `0x180023180`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023257`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023257`

## string_xrefs

- `0x180023238`: `Windows.Data.Json.JsonValue`
- `0x1800232a6`: `Windows.Data.Json.JsonValue`
- `0x180023372`: `Windows.Data.Json.JsonValue`
- `0x18002343a`: `Windows.Data.Json.JsonValue`
- `0x180023502`: `Windows.Data.Json.JsonValue`
- `0x180023698`: `Windows.Data.Json.JsonValue`
- `0x18002382f`: `Windows.Data.Json.JsonValue`
- `0x1800239c6`: `Windows.Data.Json.JsonValue`
- `0x180023b5d`: `Windows.Data.Json.JsonValue`
- `0x180023270`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x1800232d7`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800233a3`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002346b`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023533`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800236c9`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023860`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800239f7`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023b8e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023c06`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmobilenetworkshelper.cpp`
- `0x1800231d9`: `CPR(pJsonObject)`
- `0x18002333f`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_OPERATOR_MCC_2).Get(), pJsonValue.Get()))`
- `0x18002366d`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_OPERATOR_MCC_2).Get(), pJsonValue.Get()))`
- `0x180023731`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_OPERATOR_MCC_2).Get(), pJsonValue.Get()))`
- `0x18002340b`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_OPERATOR_MNC_2).Get(), pJsonValue.Get()))`
- `0x180023803`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_OPERATOR_MNC_2).Get(), pJsonValue.Get()))`
- `0x1800238c8`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_OPERATOR_MNC_2).Get(), pJsonValue.Get()))`
- `0x1800234d3`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_OPERATOR_SID_2).Get(), pJsonValue.Get()))`
- `0x18002399a`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_OPERATOR_SID_2).Get(), pJsonValue.Get()))`
- `0x180023a5f`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_OPERATOR_SID_2).Get(), pJsonValue.Get()))`
- `0x18002359f`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_OPERATOR_NID_2).Get(), pJsonValue.Get()))`
- `0x180023b31`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_OPERATOR_NID_2).Get(), pJsonValue.Get()))`
- `0x180023bef`: `CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_OPERATOR_NID_2).Get(), pJsonValue.Get()))`
- `0x180023601`: `CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwMCC, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023797`: `CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwMNC, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002392e`: `CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwSID, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180023ac5`: `CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwNID, pJsonValue.ReleaseAndGetAddressOf()))`

## pseudocode

```c
__int64 __fastcall DdcMobileNetworksHelper::FormatNetworkCode(
        struct RILNETWORKCODE *a1,
        int a2,
        struct Windows::Data::Json::IJsonObject *a3)
{
  int ActivationFactory; // ebx
  int v7; // edx
  int v8; // ecx
  char v9; // r8
  __int64 (__fastcall *v10)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v11; // rbx
  wchar_t **v12; // rdx
  HSTRING_HEADER *v13; // rax
  char v14; // r8
  __int64 (__fastcall *v15)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v16; // rbx
  wchar_t **v17; // rdx
  HSTRING_HEADER *v18; // rax
  char v19; // r8
  __int64 (__fastcall *v20)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v21; // rbx
  wchar_t **v22; // rdx
  HSTRING_HEADER *v23; // rax
  char v24; // r8
  __int64 (__fastcall *v25)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v26; // rbx
  wchar_t **v27; // rdx
  HSTRING_HEADER *v28; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  char v31; // r8
  __int64 (__fastcall *v32)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v33; // rbx
  wchar_t **v34; // rdx
  HSTRING_HEADER *v35; // rax
  char v36; // r8
  __int64 (__fastcall *v37)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v38; // rbx
  wchar_t **v39; // rdx
  HSTRING_HEADER *v40; // rax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, __int64 *); // rbx
  char v43; // r8
  __int64 (__fastcall *v44)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v45; // rbx
  wchar_t **v46; // rdx
  HSTRING_HEADER *v47; // rax
  char v48; // r8
  __int64 (__fastcall *v49)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v50; // rbx
  wchar_t **v51; // rdx
  HSTRING_HEADER *v52; // rax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, _QWORD, __int64 *); // rbx
  char v55; // r8
  __int64 (__fastcall *v56)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v57; // rbx
  wchar_t **v58; // rdx
  HSTRING_HEADER *v59; // rax
  char v60; // r8
  __int64 (__fastcall *v61)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v62; // rbx
  wchar_t **v63; // rdx
  HSTRING_HEADER *v64; // rax
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, _QWORD, __int64 *); // rbx
  char v67; // r8
  __int64 (__fastcall *v68)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v69; // rbx
  wchar_t **v70; // rdx
  HSTRING_HEADER *v71; // rax
  char v72; // r8
  __int64 (__fastcall *v73)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v74; // rbx
  wchar_t **v75; // rdx
  HSTRING_HEADER *v76; // rax
  __int64 v77; // rcx
  char v79; // [rsp+20h] [rbp-50h]
  const char *v80; // [rsp+28h] [rbp-48h]
  __int64 v81; // [rsp+30h] [rbp-40h] BYREF
  __int64 v82; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v84; // [rsp+58h] [rbp-18h]

  v81 = 0;
  v82 = 0;
  if ( !a3 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        39,
        "CPR(pJsonObject)");
    goto LABEL_112;
  }
  if ( (unsigned int)(a2 - 1) > 1 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        40,
        "CBR(dwNetworkNumber == 1 || dwNetworkNumber == 2)");
    goto LABEL_112;
  }
  v84 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v84, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v82);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_112;
    v80 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))";
    v79 = 42;
    goto LABEL_111;
  }
  if ( a1 )
  {
    if ( (a1->dwParams & 2) != 0 )
    {
      v29 = v82;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      ActivationFactory = v30(v29, a1->dwMCC, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwMCC, pJsonValue.ReleaseAndGetAddressOf()))";
        v79 = 59;
        goto LABEL_111;
      }
      v32 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v33 = v81;
      v34 = off_18002B798;
      if ( a2 != 1 )
        v34 = off_18002B778;
      v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v34, v31);
      ActivationFactory = v32(a3, v35[1].Reserved.Reserved1, v33);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_"
              "OPERATOR_MCC_2).Get(), pJsonValue.Get()))";
        v79 = 60;
        goto LABEL_111;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v79 = 64;
        goto LABEL_111;
      }
      v37 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v38 = v81;
      v39 = off_18002B798;
      if ( a2 != 1 )
        v39 = off_18002B778;
      v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v39, v36);
      ActivationFactory = v37(a3, v40[1].Reserved.Reserved1, v38);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_"
              "OPERATOR_MCC_2).Get(), pJsonValue.Get()))";
        v79 = 65;
        goto LABEL_111;
      }
    }
    if ( (a1->dwParams & 4) != 0 )
    {
      v41 = v82;
      v42 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      ActivationFactory = v42(v41, a1->dwMNC, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwMNC, pJsonValue.ReleaseAndGetAddressOf()))";
        v79 = 70;
        goto LABEL_111;
      }
      v44 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v45 = v81;
      v46 = off_18002B790;
      if ( a2 != 1 )
        v46 = off_18002B770;
      v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v46, v43);
      ActivationFactory = v44(a3, v47[1].Reserved.Reserved1, v45);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_"
              "OPERATOR_MNC_2).Get(), pJsonValue.Get()))";
        v79 = 71;
        goto LABEL_111;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v79 = 75;
        goto LABEL_111;
      }
      v49 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v50 = v81;
      v51 = off_18002B790;
      if ( a2 != 1 )
        v51 = off_18002B770;
      v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v51, v48);
      ActivationFactory = v49(a3, v52[1].Reserved.Reserved1, v50);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_"
              "OPERATOR_MNC_2).Get(), pJsonValue.Get()))";
        v79 = 76;
        goto LABEL_111;
      }
    }
    if ( (a1->dwParams & 8) != 0 )
    {
      v53 = v82;
      v54 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      ActivationFactory = v54(v53, a1->dwSID, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwSID, pJsonValue.ReleaseAndGetAddressOf()))";
        v79 = 81;
        goto LABEL_111;
      }
      v56 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v57 = v81;
      v58 = off_18002B788;
      if ( a2 != 1 )
        v58 = off_18002B768;
      v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v58, v55);
      ActivationFactory = v56(a3, v59[1].Reserved.Reserved1, v57);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_"
              "OPERATOR_SID_2).Get(), pJsonValue.Get()))";
        v79 = 82;
        goto LABEL_111;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v79 = 86;
        goto LABEL_111;
      }
      v61 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v62 = v81;
      v63 = off_18002B788;
      if ( a2 != 1 )
        v63 = off_18002B768;
      v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v63, v60);
      ActivationFactory = v61(a3, v64[1].Reserved.Reserved1, v62);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_"
              "OPERATOR_SID_2).Get(), pJsonValue.Get()))";
        v79 = 87;
        goto LABEL_111;
      }
    }
    if ( (a1->dwParams & 0x10) != 0 )
    {
      v65 = v82;
      v66 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v82 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      ActivationFactory = v66(v65, a1->dwNID, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(pJsonValueStatics->CreateNumberValue(pRilNetworkCode->dwNID, pJsonValue.ReleaseAndGetAddressOf()))";
        v79 = 92;
        goto LABEL_111;
      }
      v68 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v69 = v81;
      v70 = off_18002B780;
      if ( a2 != 1 )
        v70 = off_18002B760;
      v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v70, v67);
      ActivationFactory = v68(a3, v71[1].Reserved.Reserved1, v69);
      if ( ActivationFactory < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_"
              "OPERATOR_NID_2).Get(), pJsonValue.Get()))";
        v79 = 93;
        goto LABEL_111;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v84 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_112;
        v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v79 = 97;
        goto LABEL_111;
      }
      v73 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
      v74 = v81;
      v75 = off_18002B780;
      if ( a2 != 1 )
        v75 = off_18002B760;
      v76 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v75, v72);
      ActivationFactory = v73(a3, v76[1].Reserved.Reserved1, v74);
      if ( ActivationFactory < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_"
              "OPERATOR_NID_2).Get(), pJsonValue.Get()))";
        v79 = 98;
        goto LABEL_111;
      }
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAnd"
            "GetAddressOf()))";
      v79 = 46;
      goto LABEL_111;
    }
    v10 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
    v11 = v81;
    v12 = off_18002B798;
    if ( a2 != 1 )
      v12 = off_18002B778;
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v12, v9);
    ActivationFactory = v10(a3, v13[1].Reserved.Reserved1, v11);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MCC : JSON_HOME_OP"
            "ERATOR_MCC_2).Get(), pJsonValue.Get()))";
      v79 = 47;
      goto LABEL_111;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAnd"
            "GetAddressOf()))";
      v79 = 48;
      goto LABEL_111;
    }
    v15 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
    v16 = v81;
    v17 = off_18002B790;
    if ( a2 != 1 )
      v17 = off_18002B770;
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v17, v14);
    ActivationFactory = v15(a3, v18[1].Reserved.Reserved1, v16);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_MNC : JSON_HOME_OP"
            "ERATOR_MNC_2).Get(), pJsonValue.Get()))";
      v79 = 49;
      goto LABEL_111;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAnd"
            "GetAddressOf()))";
      v79 = 50;
      goto LABEL_111;
    }
    v20 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
    v21 = v81;
    v22 = off_18002B788;
    if ( a2 != 1 )
      v22 = off_18002B768;
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v22, v19);
    ActivationFactory = v20(a3, v23[1].Reserved.Reserved1, v21);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_SID : JSON_HOME_OP"
            "ERATOR_SID_2).Get(), pJsonValue.Get()))";
      v79 = 51;
      goto LABEL_111;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v84 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v84, &v81);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_112;
      v80 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAnd"
            "GetAddressOf()))";
      v79 = 52;
      goto LABEL_111;
    }
    v25 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a3 + 56LL);
    v26 = v81;
    v27 = off_18002B780;
    if ( a2 != 1 )
      v27 = off_18002B760;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)v27, v24);
    ActivationFactory = v25(a3, v28[1].Reserved.Reserved1, v26);
    if ( ActivationFactory < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      v80 = "CHR(pJsonObject->SetNamedValue(HStringReference(dwNetworkNumber == 1 ? JSON_HOME_OPERATOR_NID : JSON_HOME_OP"
            "ERATOR_NID_2).Get(), pJsonValue.Get()))";
      v79 = 53;
LABEL_111:
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        v79,
        v80);
    }
  }
LABEL_112:
  v77 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180023180  mov     [rsp-38h+arg_8], rbx
0x180023185  push    rbp
0x180023186  push    rsi
0x180023187  push    rdi
0x180023188  push    r12
0x18002318a  push    r13
0x18002318c  push    r14
0x18002318e  push    r15
0x180023190  mov     rbp, rsp
0x180023193  sub     rsp, 70h
0x180023197  mov     rax, cs:__security_cookie
0x18002319e  xor     rax, rsp
0x1800231a1  mov     [rbp+var_10], rax
0x1800231a5  mov     r15, r8
0x1800231a8  mov     r13d, edx
0x1800231ab  mov     r14, rcx
0x1800231ae  xor     r12d, r12d
0x1800231b1  mov     [rbp+var_40], r12
0x1800231b5  mov     [rbp+var_38], r12
0x1800231b9  lea     esi, [r12+1]
0x1800231be  test    r8, r8
0x1800231c1  jnz     short loc_1800231F2
0x1800231c3  mov     r8d, 80070057h
0x1800231c9  mov     ebx, r8d
0x1800231cc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800231d3  jz      loc_180023C13
0x1800231d9  lea     rax, aCprPjsonobject; "CPR(pJsonObject)"
0x1800231e0  mov     [rsp+70h+var_48], rax
0x1800231e5  mov     dword ptr [rsp+70h+var_50], 127h
0x1800231ed  jmp     loc_180023C06
0x1800231f2  lea     eax, [rdx-1]
0x1800231f5  cmp     eax, esi
0x1800231f7  jbe     short loc_180023228
0x1800231f9  mov     r8d, 80070057h
0x1800231ff  mov     ebx, r8d
0x180023202  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023209  jz      loc_180023C13
0x18002320f  lea     rax, aCbrDwnetworknu; "CBR(dwNetworkNumber == 1 || dwNetworkNu"...
0x180023216  mov     [rsp+70h+var_48], rax
0x18002321b  mov     dword ptr [rsp+70h+var_50], 128h
0x180023223  jmp     loc_180023C06
0x180023228  mov     [rbp+var_18], r12
0x18002322c  mov     edi, 1Bh
0x180023231  mov     r9d, edi; unsigned int
0x180023234  lea     r8d, [rdi+1]; unsigned int
0x180023238  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18002323f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180023243  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180023248  lea     r8, [rbp+var_38]
0x18002324c  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180023253  mov     rcx, [rbp+var_18]
0x180023257  call    cs:__imp_RoGetActivationFactory
0x18002325d  mov     ebx, eax
0x18002325f  test    eax, eax
0x180023261  jns     short loc_180023289
0x180023263  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18002326a  jz      loc_180023C13
0x180023270  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180023277  mov     [rsp+70h+var_48], rax
0x18002327c  mov     dword ptr [rsp+70h+var_50], 12Ah
0x180023284  jmp     loc_180023C03
0x180023289  lea     rcx, [rbp+var_40]
0x18002328d  test    r14, r14
0x180023290  jnz     loc_1800235B8
0x180023296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002329b  mov     [rbp+var_18], r12
0x18002329f  mov     r9d, edi; unsigned int
0x1800232a2  lea     r8d, [r14+1Ch]; unsigned int
0x1800232a6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800232ad  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800232b1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800232b6  nop
0x1800232b7  lea     rdx, [rbp+var_40]
0x1800232bb  mov     rcx, [rbp+var_18]
0x1800232bf  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x1800232c4  mov     ebx, eax
0x1800232c6  test    eax, eax
0x1800232c8  jns     short loc_1800232F0
0x1800232ca  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800232d1  jz      loc_180023C13
0x1800232d7  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x1800232de  mov     [rsp+70h+var_48], rax
0x1800232e3  mov     dword ptr [rsp+70h+var_50], 12Eh
0x1800232eb  jmp     loc_180023C03
0x1800232f0  mov     rax, [r15]
0x1800232f3  mov     rdi, [rax+38h]
0x1800232f7  mov     rbx, [rbp+var_40]
0x1800232fb  lea     rax, off_18002B778; "HomeOperatorMcc2"
0x180023302  lea     rdx, off_18002B798; "HomeOperatorMcc"
0x180023309  cmp     r13d, esi
0x18002330c  cmovnz  rdx, rax
0x180023310  lea     rcx, [rbp+hstringHeader]
0x180023314  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180023319  nop
0x18002331a  mov     r8, rbx
0x18002331d  mov     rdx, [rax+18h]
0x180023321  mov     rcx, r15
0x180023324  mov     rax, rdi
0x180023327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002332c  mov     ebx, eax
0x18002332e  test    eax, eax
0x180023330  jns     short loc_180023358
0x180023332  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023339  jz      loc_180023C13
0x18002333f  lea     rax, aChrPjsonobject_1; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180023346  mov     [rsp+70h+var_48], rax
0x18002334b  mov     dword ptr [rsp+70h+var_50], 12Fh
0x180023353  jmp     loc_180023C03
0x180023358  lea     rcx, [rbp+var_40]
0x18002335c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023361  mov     [rbp+var_18], r12
0x180023365  mov     r14d, 1Bh
0x18002336b  mov     r9d, r14d; unsigned int
0x18002336e  lea     r8d, [r14+1]; unsigned int
0x180023372  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180023379  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002337d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180023382  nop
0x180023383  lea     rdx, [rbp+var_40]
0x180023387  mov     rcx, [rbp+var_18]
0x18002338b  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180023390  mov     ebx, eax
0x180023392  test    eax, eax
0x180023394  jns     short loc_1800233BC
0x180023396  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18002339d  jz      loc_180023C13
0x1800233a3  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x1800233aa  mov     [rsp+70h+var_48], rax
0x1800233af  mov     dword ptr [rsp+70h+var_50], 130h
0x1800233b7  jmp     loc_180023C03
0x1800233bc  mov     rax, [r15]
0x1800233bf  mov     rdi, [rax+38h]
0x1800233c3  mov     rbx, [rbp+var_40]
0x1800233c7  lea     rax, off_18002B770; "HomeOperatorMnc2"
0x1800233ce  lea     rdx, off_18002B790; "HomeOperatorMnc"
0x1800233d5  cmp     r13d, esi
0x1800233d8  cmovnz  rdx, rax
0x1800233dc  lea     rcx, [rbp+hstringHeader]
0x1800233e0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800233e5  nop
0x1800233e6  mov     r8, rbx
0x1800233e9  mov     rdx, [rax+18h]
0x1800233ed  mov     rcx, r15
0x1800233f0  mov     rax, rdi
0x1800233f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233f8  mov     ebx, eax
0x1800233fa  test    eax, eax
0x1800233fc  jns     short loc_180023424
0x1800233fe  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023405  jz      loc_180023C13
0x18002340b  lea     rax, aChrPjsonobject_26; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180023412  mov     [rsp+70h+var_48], rax
0x180023417  mov     dword ptr [rsp+70h+var_50], 131h
0x18002341f  jmp     loc_180023C03
0x180023424  lea     rcx, [rbp+var_40]
0x180023428  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002342d  mov     [rbp+var_18], r12
0x180023431  mov     r9d, r14d; unsigned int
0x180023434  mov     r8d, 1Ch; unsigned int
0x18002343a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180023441  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180023445  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002344a  nop
0x18002344b  lea     rdx, [rbp+var_40]
0x18002344f  mov     rcx, [rbp+var_18]
0x180023453  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180023458  mov     ebx, eax
0x18002345a  test    eax, eax
0x18002345c  jns     short loc_180023484
0x18002345e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023465  jz      loc_180023C13
0x18002346b  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180023472  mov     [rsp+70h+var_48], rax
0x180023477  mov     dword ptr [rsp+70h+var_50], 132h
0x18002347f  jmp     loc_180023C03
0x180023484  mov     rax, [r15]
0x180023487  mov     rdi, [rax+38h]
0x18002348b  mov     rbx, [rbp+var_40]
0x18002348f  lea     rax, off_18002B768; "HomeOperatorSid2"
0x180023496  lea     rdx, off_18002B788; "HomeOperatorSid"
0x18002349d  cmp     r13d, esi
0x1800234a0  cmovnz  rdx, rax
0x1800234a4  lea     rcx, [rbp+hstringHeader]
0x1800234a8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800234ad  nop
0x1800234ae  mov     r8, rbx
0x1800234b1  mov     rdx, [rax+18h]
0x1800234b5  mov     rcx, r15
0x1800234b8  mov     rax, rdi
0x1800234bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c0  mov     ebx, eax
0x1800234c2  test    eax, eax
0x1800234c4  jns     short loc_1800234EC
0x1800234c6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800234cd  jz      loc_180023C13
0x1800234d3  lea     rax, aChrPjsonobject_11; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800234da  mov     [rsp+70h+var_48], rax
0x1800234df  mov     dword ptr [rsp+70h+var_50], 133h
0x1800234e7  jmp     loc_180023C03
0x1800234ec  lea     rcx, [rbp+var_40]
0x1800234f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800234f5  mov     [rbp+var_18], r12
0x1800234f9  mov     r9d, r14d; unsigned int
0x1800234fc  mov     r8d, 1Ch; unsigned int
0x180023502  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180023509  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002350d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180023512  nop
0x180023513  lea     rdx, [rbp+var_40]
0x180023517  mov     rcx, [rbp+var_18]
0x18002351b  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180023520  mov     ebx, eax
0x180023522  test    eax, eax
0x180023524  jns     short loc_18002354C
0x180023526  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x18002352d  jz      loc_180023C13
0x180023533  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x18002353a  mov     [rsp+70h+var_48], rax
0x18002353f  mov     dword ptr [rsp+70h+var_50], 134h
0x180023547  jmp     loc_180023C03
0x18002354c  mov     rax, [r15]
0x18002354f  mov     rdi, [rax+38h]
0x180023553  mov     rbx, [rbp+var_40]
0x180023557  lea     rax, off_18002B760; "HomeOperatorNid2"
0x18002355e  lea     rdx, off_18002B780; "HomeOperatorNid"
0x180023565  cmp     r13d, esi
0x180023568  cmovnz  rdx, rax
0x18002356c  lea     rcx, [rbp+hstringHeader]
0x180023570  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180023575  nop
0x180023576  mov     r8, rbx
0x180023579  mov     rdx, [rax+18h]
0x18002357d  mov     rcx, r15
0x180023580  mov     rax, rdi
0x180023583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023588  mov     ebx, eax
0x18002358a  test    eax, eax
0x18002358c  jns     loc_180023C13
0x180023592  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023599  jz      loc_180023C13
0x18002359f  lea     rax, aChrPjsonobject_19; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800235a6  mov     [rsp+70h+var_48], rax
0x1800235ab  mov     dword ptr [rsp+70h+var_50], 135h
0x1800235b3  jmp     loc_180023C03
0x1800235b8  test    byte ptr [r14+4], 2
0x1800235bd  jz      loc_180023686
0x1800235c3  mov     rdi, [rbp+var_38]
0x1800235c7  mov     rax, [rdi]
0x1800235ca  mov     rbx, [rax+48h]
0x1800235ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800235d3  mov     edx, [r14+0Ch]
0x1800235d7  xorps   xmm1, xmm1
0x1800235da  cvtsi2sd xmm1, rdx
0x1800235df  lea     r8, [rbp+var_40]
0x1800235e3  mov     rcx, rdi
0x1800235e6  mov     rax, rbx
0x1800235e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ee  mov     ebx, eax
0x1800235f0  test    eax, eax
0x1800235f2  jns     short loc_18002361A
0x1800235f4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x1800235fb  jz      loc_180023C13
0x180023601  lea     rax, aChrPjsonvalues_49; "CHR(pJsonValueStatics->CreateNumberValu"...
0x180023608  mov     [rsp+70h+var_48], rax
0x18002360d  mov     dword ptr [rsp+70h+var_50], 13Bh
0x180023615  jmp     loc_180023C03
0x18002361a  mov     rax, [r15]
0x18002361d  mov     rdi, [rax+38h]
0x180023621  mov     rbx, [rbp+var_40]
0x180023625  lea     rax, off_18002B778; "HomeOperatorMcc2"
0x18002362c  lea     rdx, off_18002B798; "HomeOperatorMcc"
0x180023633  cmp     r13d, esi
0x180023636  cmovnz  rdx, rax
0x18002363a  lea     rcx, [rbp+hstringHeader]
0x18002363e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180023643  nop
0x180023644  mov     r8, rbx
0x180023647  mov     rdx, [rax+18h]
0x18002364b  mov     rcx, r15
0x18002364e  mov     rax, rdi
0x180023651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023656  mov     ebx, eax
0x180023658  test    eax, eax
0x18002365a  jns     loc_18002374A
0x180023660  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, sil
0x180023667  jz      loc_180023C13
0x18002366d  lea     rax, aChrPjsonobject_1; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180023674  mov     [rsp+70h+var_48], rax
0x180023679  mov     dword ptr [rsp+70h+var_50], 13Ch
0x180023681  jmp     loc_180023C03
0x180023686  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002368b  mov     [rbp+var_18], r12
0x18002368f  mov     r9d, edi; unsigned int
0x180023692  mov     r8d, 1Ch; unsigned int
0x180023698  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18002369f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800236a3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800236a8  nop
0x1800236a9  lea     rdx, [rbp+var_40]
0x1800236ad  mov     rcx, [rbp+var_18]
  ... truncated ...
```
