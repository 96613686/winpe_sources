# DdcDeviceInfoHelper::GetDeviceInfoLight(Windows::Data::Json::IJsonObject *)

- ea: `0x1800183c4`
- end: `0x180018c84`
- name: `?GetDeviceInfoLight@DdcDeviceInfoHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `2240`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001691c`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002fc0`
- `0x180004060`
- `0x1800050b8`
- `0x18000d79c`
- `0x18000fc64`
- `0x18000fd48`
- `0x18001386c`
- `0x180013a58`
- `0x1800183c4`
- `0x1800190fc`
- `0x18001a7fc`
- `0x18001a8e4`
- `0x180028110`
- `0x18002844c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018472`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018472`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180018545`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x180018545`

## string_xrefs

- `0x180018451`: `Windows.Data.Json.JsonValue`
- `0x1800185c8`: `Windows.Data.Json.JsonValue`
- `0x1800186e6`: `Windows.Data.Json.JsonValue`
- `0x180018808`: `Windows.Data.Json.JsonValue`
- `0x180018934`: `Windows.Data.Json.JsonValue`
- `0x180018a5c`: `Windows.Data.Json.JsonValue`
- `0x180018b7f`: `Windows.Data.Json.JsonValue`
- `0x18001849f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180018c17`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001848b`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180018597`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfLocationCollectionOptIn, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800185fb`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018719`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001883b`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018967`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018a8f`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018bae`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018657`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LOCATION_COLLECTION_OPT_IN).Get(), pJsonValue.Get()))`
- `0x1800186b6`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfMasterLocationSwitchOn, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001877b`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_MASTER_LOCATION_SWITCH_IN).Get(), pJsonValue.Get()))`
- `0x1800187da`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfUpdatesAvailable, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001889d`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_UPDATES_AVAILABLE).Get(), pJsonValue.Get()))`
- `0x18001890c`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800189c3`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LAST_UPDATE_TIME).Get(), pJsonValue.Get()))`
- `0x180018a34`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFriendlyName).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018aeb`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_FRIENDLY_NAME).Get(), pJsonValue.Get()))`
- `0x180018b57`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(deviceCountryCode).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018c03`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_DEVICE_COUNTRY_CODE).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetDeviceInfoLight(struct Windows::Data::Json::IJsonObject *a1)
{
  unsigned __int16 *v2; // r14
  int v3; // edx
  int v4; // ecx
  int ActivationFactory; // ebx
  int *v6; // r15
  int v7; // edx
  int *v8; // r12
  int v9; // edx
  int *v10; // r13
  int v11; // eax
  unsigned __int16 *v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64 *); // rbx
  __int64 v15; // rdx
  int v16; // edx
  int v17; // ecx
  char v18; // r8
  int v19; // edx
  int v20; // ecx
  __int64 (__fastcall *v21)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v22; // rbx
  HSTRING_HEADER *v23; // rax
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, __int64 *); // rbx
  __int64 v28; // rdx
  int v29; // edx
  int v30; // ecx
  char v31; // r8
  int v32; // edx
  int v33; // ecx
  __int64 (__fastcall *v34)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v35; // rbx
  HSTRING_HEADER *v36; // rax
  int v37; // edx
  int v38; // ecx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64, __int64 *); // rbx
  __int64 v41; // rdx
  int v42; // edx
  int v43; // ecx
  char v44; // r8
  int v45; // edx
  int v46; // ecx
  __int64 (__fastcall *v47)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v48; // rbx
  HSTRING_HEADER *v49; // rax
  int v50; // edx
  int v51; // ecx
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, PVOID, __int64 *); // rbx
  char v54; // r8
  HSTRING_HEADER *v55; // rax
  int v56; // edx
  int v57; // ecx
  char v58; // r8
  int v59; // edx
  int v60; // ecx
  __int64 (__fastcall *v61)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v62; // rbx
  HSTRING_HEADER *v63; // rax
  int v64; // edx
  int v65; // ecx
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, PVOID, __int64 *); // rbx
  char v68; // r8
  HSTRING_HEADER *v69; // rax
  int v70; // edx
  int v71; // ecx
  char v72; // r8
  int v73; // edx
  int v74; // ecx
  __int64 (__fastcall *v75)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v76; // rbx
  HSTRING_HEADER *v77; // rax
  int v78; // edx
  int v79; // ecx
  __int64 v80; // rdi
  __int64 (__fastcall *v81)(__int64, _QWORD, __int64 *); // rbx
  __int64 v82; // rax
  int v83; // edx
  int v84; // ecx
  char v85; // r8
  int v86; // edx
  int v87; // ecx
  __int64 (__fastcall *v88)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v89; // rbx
  HSTRING_HEADER *v90; // rax
  int v91; // edx
  int v92; // ecx
  __int64 v93; // rcx
  __int64 v95; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v96; // [rsp+38h] [rbp-C8h] BYREF
  int v97; // [rsp+40h] [rbp-C0h] BYREF
  int v98; // [rsp+44h] [rbp-BCh] BYREF
  int v99; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME v100; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v102; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v104; // [rsp+80h] [rbp-80h]
  unsigned __int16 v105[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v106[26]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR geoName[136]; // [rsp+C0h] [rbp-40h] BYREF

  v97 = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  *(_OWORD *)v105 = 0;
  memset(v106, 0, sizeof(v106));
  v2 = 0;
  v102 = 0;
  Block = 0;
  memset_0(geoName, 0, 0x102u);
  v95 = 0;
  v96 = 0;
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v104, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v96);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        122,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    goto LABEL_76;
  }
  v6 = &v97;
  if ( (int)DdcDeviceInfoHelper::LocationSyncEnabled(&v97) < 0 )
    v6 = 0;
  v8 = &v98;
  if ( (int)DdcDeviceInfoHelper::MasterLocationSwitchOn(&v98) < 0 )
    v8 = 0;
  v10 = &v99;
  if ( (int)DdcUpdateHelper::CriticalUpdatesAvailable(&v99, v7) < 0 )
    v10 = 0;
  if ( (int)DdcUpdateHelper::CriticalUpdatesCheckedTime(&v100, v9) >= 0 )
  {
    v11 = StringCchPrintfW(v105, 0x15u, L"%llu", v100);
    v12 = v105;
    if ( v11 < 0 )
      v12 = 0;
    v2 = v12;
    v102 = v12;
  }
  DdcDeviceInfoHelper::GetFriendlyName((unsigned __int16 **)&Block);
  v100.dwLowDateTime = GetUserDefaultGeoName(geoName, 129);
  if ( v6 )
  {
    v13 = v96;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    LOBYTE(v15) = *(_BYTE *)v6;
    ActivationFactory = v14(v13, v15, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v17,
          v16,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          166,
          "CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfLocationCollectionOptIn, pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v104 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v20,
          v19,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          170,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  v21 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
  v22 = v95;
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B5E0, v18);
  ActivationFactory = v21(a1, v23[1].Reserved.Reserved1, v22);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v25,
        v24,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        173,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LOCATION_COLLECTION_OPT_IN).Get(), pJsonValue.Get()))");
    goto LABEL_74;
  }
  if ( v8 )
  {
    v26 = v96;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    LOBYTE(v28) = *(_BYTE *)v8;
    ActivationFactory = v27(v26, v28, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v30,
          v29,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          178,
          "CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfMasterLocationSwitchOn, pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v104 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v33,
          v32,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          182,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  v34 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
  v35 = v95;
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B5D8, v31);
  ActivationFactory = v34(a1, v36[1].Reserved.Reserved1, v35);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v38,
        v37,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        185,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_MASTER_LOCATION_SWITCH_IN).Get(), pJsonValue.Get()))");
    goto LABEL_74;
  }
  if ( v10 )
  {
    v39 = v96;
    v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    LOBYTE(v41) = *(_BYTE *)v10;
    ActivationFactory = v40(v39, v41, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v43,
          v42,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          190,
          "CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfUpdatesAvailable, pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v104 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v46,
          v45,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          194,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  v47 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
  v48 = v95;
  v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B530, v44);
  ActivationFactory = v47(a1, v49[1].Reserved.Reserved1, v48);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v51,
        v50,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        197,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_UPDATES_AVAILABLE).Get(), pJsonValue.Get()))");
    goto LABEL_74;
  }
  if ( v2 )
  {
    v52 = v96;
    v53 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v96 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v55 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v102, v54);
    ActivationFactory = v53(v52, v55[1].Reserved.Reserved1, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v57,
          v56,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          202,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v104 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v60,
          v59,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          206,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
  }
  v61 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
  v62 = v95;
  v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B528, v58);
  ActivationFactory = v61(a1, v63[1].Reserved.Reserved1, v62);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v65,
        v64,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        209,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LAST_UPDATE_TIME).Get(), pJsonValue.Get()))");
    goto LABEL_74;
  }
  if ( Block )
  {
    v66 = v96;
    v67 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v96 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&Block, v68);
    ActivationFactory = v67(v66, v69[1].Reserved.Reserved1, &v95);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v71,
          v70,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          214,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFriendlyName).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_74;
    }
    goto LABEL_61;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
  if ( ActivationFactory >= 0 )
  {
LABEL_61:
    v75 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
    v76 = v95;
    v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_18002B600,
            v72);
    ActivationFactory = v75(a1, v77[1].Reserved.Reserved1, v76);
    if ( ActivationFactory >= 0 )
    {
      if ( v100.dwLowDateTime )
      {
        v80 = v96;
        v81 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v96 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
        v82 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, geoName);
        ActivationFactory = v81(v80, *(_QWORD *)(v82 + 24), &v95);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v84,
              v83,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              226,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(deviceCountryCode).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
          goto LABEL_74;
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
        v104 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v104, &v95);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v87,
              v86,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              230,
              "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))");
          goto LABEL_74;
        }
      }
      v88 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
      v89 = v95;
      v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B5F8,
              v85);
      ActivationFactory = v88(a1, v90[1].Reserved.Reserved1, v89);
      if ( ActivationFactory < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v92,
          v91,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          233,
          "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_DEVICE_COUNTRY_CODE).Get(), pJsonValue.Get()))");
      goto LABEL_74;
    }
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v79,
        v78,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        221,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_FRIENDLY_NAME).Get(), pJsonValue.Get()))");
LABEL_74:
    if ( Block )
      operator delete(Block);
    goto LABEL_76;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v74,
      v73,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      218,
      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
LABEL_76:
  v93 = v96;
  if ( v96 )
  {
    v96 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800183c4  push    rbp
0x1800183c6  push    rbx
0x1800183c7  push    rsi
0x1800183c8  push    rdi
0x1800183c9  push    r12
0x1800183cb  push    r13
0x1800183cd  push    r14
0x1800183cf  push    r15
0x1800183d1  lea     rbp, [rsp-0E8h]
0x1800183d9  sub     rsp, 1E8h
0x1800183e0  mov     rax, cs:__security_cookie
0x1800183e7  xor     rax, rsp
0x1800183ea  mov     [rbp+120h+var_50], rax
0x1800183f1  mov     rsi, rcx
0x1800183f4  xor     r15d, r15d
0x1800183f7  mov     [rsp+220h+var_1E0], r15d
0x1800183fc  mov     [rsp+220h+var_1DC], r15d
0x180018401  mov     [rsp+220h+var_1D8], r15d
0x180018406  mov     qword ptr [rsp+220h+var_1D0.dwLowDateTime], r15
0x18001840b  xorps   xmm0, xmm0
0x18001840e  movups  xmmword ptr [rbp+120h+var_198], xmm0
0x180018412  movups  xmmword ptr [rbp+120h+var_188], xmm0
0x180018416  movups  xmmword ptr [rbp+120h+var_188+0Ah], xmm0
0x18001841a  mov     r14d, r15d
0x18001841d  mov     [rsp+220h+var_1C0], r15
0x180018422  mov     [rsp+220h+Block], r15
0x180018427  xor     edx, edx; Val
0x180018429  mov     r8d, 102h; Size
0x18001842f  lea     rcx, [rbp+120h+geoName]; void *
0x180018433  call    memset_0
0x180018438  mov     [rsp+220h+var_1F0], r15
0x18001843d  mov     [rsp+220h+var_1E8], r15
0x180018442  mov     [rbp+120h+var_1A0], r15
0x180018446  lea     edi, [r15+1Bh]
0x18001844a  mov     r9d, edi; unsigned int
0x18001844d  lea     r8d, [r15+1Ch]; unsigned int
0x180018451  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180018458  lea     rcx, [rsp+220h+hstringHeader]; hstringHeader
0x18001845d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018462  lea     r8, [rsp+220h+var_1E8]
0x180018467  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001846e  mov     rcx, [rbp+120h+var_1A0]
0x180018472  call    cs:__imp_RoGetActivationFactory
0x180018478  mov     ebx, eax
0x18001847a  test    eax, eax
0x18001847c  jns     short loc_1800184B3
0x18001847e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018485  jz      loc_180018C39
0x18001848b  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180018492  mov     [rsp+220h+var_1F8], rax
0x180018497  mov     [rsp+220h+var_200], 7Ah ; 'z'
0x18001849f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800184a6  mov     r8d, ebx
0x1800184a9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800184ae  jmp     loc_180018C39
0x1800184b3  lea     rcx, [rsp+220h+var_1E0]; int *
0x1800184b8  call    ?LocationSyncEnabled@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::LocationSyncEnabled(int *)
0x1800184bd  lea     r15, [rsp+220h+var_1E0]
0x1800184c2  xor     ecx, ecx
0x1800184c4  test    eax, eax
0x1800184c6  cmovs   r15, rcx
0x1800184ca  lea     rcx, [rsp+220h+var_1DC]; int *
0x1800184cf  call    ?MasterLocationSwitchOn@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::MasterLocationSwitchOn(int *)
0x1800184d4  lea     r12, [rsp+220h+var_1DC]
0x1800184d9  xor     ecx, ecx
0x1800184db  test    eax, eax
0x1800184dd  cmovs   r12, rcx
0x1800184e1  lea     rcx, [rsp+220h+var_1D8]; int *
0x1800184e6  call    ?CriticalUpdatesAvailable@DdcUpdateHelper@@SAJPEAH@Z; DdcUpdateHelper::CriticalUpdatesAvailable(int *)
0x1800184eb  lea     r13, [rsp+220h+var_1D8]
0x1800184f0  xor     ecx, ecx
0x1800184f2  test    eax, eax
0x1800184f4  cmovs   r13, rcx
0x1800184f8  lea     rcx, [rsp+220h+var_1D0]; struct _FILETIME *
0x1800184fd  call    ?CriticalUpdatesCheckedTime@DdcUpdateHelper@@SAJPEAU_FILETIME@@@Z; DdcUpdateHelper::CriticalUpdatesCheckedTime(_FILETIME *)
0x180018502  test    eax, eax
0x180018504  js      short loc_180018532
0x180018506  mov     r9, qword ptr [rsp+220h+var_1D0.dwLowDateTime]
0x18001850b  lea     r8, aLlu; "%llu"
0x180018512  mov     edx, 15h; unsigned __int64
0x180018517  lea     rcx, [rbp+120h+var_198]; unsigned __int16 *
0x18001851b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018520  lea     rcx, [rbp+120h+var_198]
0x180018524  test    eax, eax
0x180018526  cmovs   rcx, r14
0x18001852a  mov     r14, rcx
0x18001852d  mov     [rsp+220h+var_1C0], rcx
0x180018532  lea     rcx, [rsp+220h+Block]; unsigned __int16 **
0x180018537  call    ?GetFriendlyName@DdcDeviceInfoHelper@@CAJPEAPEAG@Z; DdcDeviceInfoHelper::GetFriendlyName(ushort * *)
0x18001853c  mov     edx, 81h; geoNameCount
0x180018541  lea     rcx, [rbp+120h+geoName]; geoName
0x180018545  call    cs:__imp_GetUserDefaultGeoName
0x18001854b  mov     [rsp+220h+var_1D0.dwLowDateTime], eax
0x18001854f  test    r15, r15
0x180018552  jz      short loc_1800185B0
0x180018554  mov     rdi, [rsp+220h+var_1E8]
0x180018559  mov     rcx, [rdi]
0x18001855c  mov     rbx, [rcx+40h]
0x180018560  lea     rcx, [rsp+220h+var_1F0]
0x180018565  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001856a  lea     r8, [rsp+220h+var_1F0]
0x18001856f  mov     dl, [r15]
0x180018572  mov     rcx, rdi
0x180018575  mov     rax, rbx
0x180018578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857d  mov     ebx, eax
0x18001857f  xor     r15d, r15d
0x180018582  test    eax, eax
0x180018584  jns     loc_180018614
0x18001858a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018591  jz      loc_180018C26
0x180018597  lea     rax, aChrPjsonvalues_16; "CHR(pJsonValueStatics->CreateBooleanVal"...
0x18001859e  mov     [rsp+220h+var_1F8], rax
0x1800185a3  mov     [rsp+220h+var_200], 0A6h
0x1800185ab  jmp     loc_180018C17
0x1800185b0  lea     rcx, [rsp+220h+var_1F0]
0x1800185b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800185ba  xor     r15d, r15d
0x1800185bd  mov     [rbp+120h+var_1A0], r15
0x1800185c1  mov     r9d, edi; unsigned int
0x1800185c4  lea     r8d, [r15+1Ch]; unsigned int
0x1800185c8  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800185cf  lea     rcx, [rsp+220h+hstringHeader]; hstringHeader
0x1800185d4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800185d9  nop
0x1800185da  lea     rdx, [rsp+220h+var_1F0]
0x1800185df  mov     rcx, [rbp+120h+var_1A0]
0x1800185e3  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x1800185e8  mov     ebx, eax
0x1800185ea  test    eax, eax
0x1800185ec  jns     short loc_180018614
0x1800185ee  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800185f5  jz      loc_180018C26
0x1800185fb  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180018602  mov     [rsp+220h+var_1F8], rax
0x180018607  mov     [rsp+220h+var_200], 0AAh
0x18001860f  jmp     loc_180018C17
0x180018614  mov     rax, [rsi]
0x180018617  mov     rdi, [rax+38h]
0x18001861b  mov     rbx, [rsp+220h+var_1F0]
0x180018620  lea     rdx, off_18002B5E0; "LocationCollectionOptIn"
0x180018627  lea     rcx, [rsp+220h+hstringHeader]
0x18001862c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018631  nop
0x180018632  mov     r8, rbx
0x180018635  mov     rdx, [rax+18h]
0x180018639  mov     rcx, rsi
0x18001863c  mov     rax, rdi
0x18001863f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018644  mov     ebx, eax
0x180018646  test    eax, eax
0x180018648  jns     short loc_180018670
0x18001864a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018651  jz      loc_180018C26
0x180018657  lea     rax, aChrPdeviceinfo_6; "CHR(pDeviceInfo->SetNamedValue(HStringR"...
0x18001865e  mov     [rsp+220h+var_1F8], rax
0x180018663  mov     [rsp+220h+var_200], 0ADh
0x18001866b  jmp     loc_180018C17
0x180018670  lea     rcx, [rsp+220h+var_1F0]
0x180018675  test    r12, r12
0x180018678  jz      short loc_1800186CF
0x18001867a  mov     rdi, [rsp+220h+var_1E8]
0x18001867f  mov     rax, [rdi]
0x180018682  mov     rbx, [rax+40h]
0x180018686  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001868b  lea     r8, [rsp+220h+var_1F0]
0x180018690  mov     dl, [r12]
0x180018694  mov     rcx, rdi
0x180018697  mov     rax, rbx
0x18001869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001869f  mov     ebx, eax
0x1800186a1  test    eax, eax
0x1800186a3  jns     loc_180018732
0x1800186a9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800186b0  jz      loc_180018C26
0x1800186b6  lea     rax, aChrPjsonvalues_78; "CHR(pJsonValueStatics->CreateBooleanVal"...
0x1800186bd  mov     [rsp+220h+var_1F8], rax
0x1800186c2  mov     [rsp+220h+var_200], 0B2h
0x1800186ca  jmp     loc_180018C17
0x1800186cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186d4  mov     [rbp+120h+var_1A0], r15
0x1800186d8  mov     r12d, 1Bh
0x1800186de  mov     r9d, r12d; unsigned int
0x1800186e1  lea     r8d, [r12+1]; unsigned int
0x1800186e6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800186ed  lea     rcx, [rsp+220h+hstringHeader]; hstringHeader
0x1800186f2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800186f7  nop
0x1800186f8  lea     rdx, [rsp+220h+var_1F0]
0x1800186fd  mov     rcx, [rbp+120h+var_1A0]
0x180018701  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180018706  mov     ebx, eax
0x180018708  test    eax, eax
0x18001870a  jns     short loc_180018738
0x18001870c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018713  jz      loc_180018C26
0x180018719  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180018720  mov     [rsp+220h+var_1F8], rax
0x180018725  mov     [rsp+220h+var_200], 0B6h
0x18001872d  jmp     loc_180018C17
0x180018732  mov     r12d, 1Bh
0x180018738  mov     rax, [rsi]
0x18001873b  mov     rdi, [rax+38h]
0x18001873f  mov     rbx, [rsp+220h+var_1F0]
0x180018744  lea     rdx, off_18002B5D8; "DeviceLocationEnabled"
0x18001874b  lea     rcx, [rsp+220h+hstringHeader]
0x180018750  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018755  nop
0x180018756  mov     r8, rbx
0x180018759  mov     rdx, [rax+18h]
0x18001875d  mov     rcx, rsi
0x180018760  mov     rax, rdi
0x180018763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018768  mov     ebx, eax
0x18001876a  test    eax, eax
0x18001876c  jns     short loc_180018794
0x18001876e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018775  jz      loc_180018C26
0x18001877b  lea     rax, aChrPdeviceinfo_13; "CHR(pDeviceInfo->SetNamedValue(HStringR"...
0x180018782  mov     [rsp+220h+var_1F8], rax
0x180018787  mov     [rsp+220h+var_200], 0B9h
0x18001878f  jmp     loc_180018C17
0x180018794  lea     rcx, [rsp+220h+var_1F0]
0x180018799  test    r13, r13
0x18001879c  jz      short loc_1800187F3
0x18001879e  mov     rdi, [rsp+220h+var_1E8]
0x1800187a3  mov     rax, [rdi]
0x1800187a6  mov     rbx, [rax+40h]
0x1800187aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800187af  lea     r8, [rsp+220h+var_1F0]
0x1800187b4  mov     dl, [r13+0]
0x1800187b8  mov     rcx, rdi
0x1800187bb  mov     rax, rbx
0x1800187be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c3  mov     ebx, eax
0x1800187c5  test    eax, eax
0x1800187c7  jns     loc_180018854
0x1800187cd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800187d4  jz      loc_180018C26
0x1800187da  lea     rax, aChrPjsonvalues_30; "CHR(pJsonValueStatics->CreateBooleanVal"...
0x1800187e1  mov     [rsp+220h+var_1F8], rax
0x1800187e6  mov     [rsp+220h+var_200], 0BEh
0x1800187ee  jmp     loc_180018C17
0x1800187f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800187f8  mov     [rbp+120h+var_1A0], r15
0x1800187fc  mov     r9d, r12d; unsigned int
0x1800187ff  mov     r13d, 1Ch
0x180018805  mov     r8d, r13d; unsigned int
0x180018808  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001880f  lea     rcx, [rsp+220h+hstringHeader]; hstringHeader
0x180018814  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018819  nop
0x18001881a  lea     rdx, [rsp+220h+var_1F0]
0x18001881f  mov     rcx, [rbp+120h+var_1A0]
0x180018823  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180018828  mov     ebx, eax
0x18001882a  test    eax, eax
0x18001882c  jns     short loc_18001885A
0x18001882e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018835  jz      loc_180018C26
0x18001883b  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180018842  mov     [rsp+220h+var_1F8], rax
0x180018847  mov     [rsp+220h+var_200], 0C2h
0x18001884f  jmp     loc_180018C17
0x180018854  mov     r13d, 1Ch
0x18001885a  mov     rax, [rsi]
0x18001885d  mov     rdi, [rax+38h]
0x180018861  mov     rbx, [rsp+220h+var_1F0]
0x180018866  lea     rdx, off_18002B530; "CriticalUpdatesAvailable"
0x18001886d  lea     rcx, [rsp+220h+hstringHeader]
0x180018872  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018877  nop
0x180018878  mov     r8, rbx
0x18001887b  mov     rdx, [rax+18h]
0x18001887f  mov     rcx, rsi
0x180018882  mov     rax, rdi
0x180018885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001888a  mov     ebx, eax
0x18001888c  test    eax, eax
0x18001888e  jns     short loc_1800188B6
0x180018890  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018897  jz      loc_180018C26
0x18001889d  lea     rax, aChrPdeviceinfo_23; "CHR(pDeviceInfo->SetNamedValue(HStringR"...
0x1800188a4  mov     [rsp+220h+var_1F8], rax
0x1800188a9  mov     [rsp+220h+var_200], 0C5h
0x1800188b1  jmp     loc_180018C17
0x1800188b6  lea     rcx, [rsp+220h+var_1F0]
0x1800188bb  test    r14, r14
0x1800188be  jz      short loc_180018925
0x1800188c0  mov     rdi, [rsp+220h+var_1E8]
0x1800188c5  mov     rax, [rdi]
0x1800188c8  mov     rbx, [rax+50h]
0x1800188cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800188d1  lea     rdx, [rsp+220h+var_1C0]
0x1800188d6  lea     rcx, [rsp+220h+hstringHeader]
0x1800188db  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800188e0  nop
0x1800188e1  lea     r8, [rsp+220h+var_1F0]
0x1800188e6  mov     rdx, [rax+18h]
0x1800188ea  mov     rcx, rdi
  ... truncated ...
```
