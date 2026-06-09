# DdcDeviceInfoHelper::GetDeviceHardwareInfo(Windows::Data::Json::IJsonValue * *)

- ea: `0x180015fbc`
- end: `0x180016915`
- name: `?GetDeviceHardwareInfo@DdcDeviceInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `2393`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x1800036e8`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013a58`
- `0x180013b38`
- `0x180015120`
- `0x180015fbc`
- `0x180019400`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800160e7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800160e7`

## string_xrefs

- `0x1800160c6`: `Windows.Data.Json.JsonValue`
- `0x180016211`: `Windows.Data.Json.JsonValue`
- `0x18001633b`: `Windows.Data.Json.JsonValue`
- `0x18001646e`: `Windows.Data.Json.JsonValue`
- `0x1800165a1`: `Windows.Data.Json.JsonValue`
- `0x1800166d4`: `Windows.Data.Json.JsonValue`
- `0x180016058`: `Windows.Data.Json.JsonObject`
- `0x18001609f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180016100`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180016244`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001636e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800164a1`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800165d4`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016707`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001608b`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pDeviceHardwareInfo.GetAddressOf()))`
- `0x1800161e0`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszRandomAccessMemory).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800162a5`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_RANDOM_ACCESS_MEMORY).Get(), pJsonValue.Get()))`
- `0x18001630b`: `CHR(pJsonValueStatics->CreateNumberValue(dwNumProcessors, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800163cf`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_NUM_PROCESSORS).Get(), pJsonValue.Get()))`
- `0x18001643e`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProcessorName).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016502`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_PROCESSOR_NAME).Get(), pJsonValue.Get()))`
- `0x180016571`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProcessorSpeed).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016635`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_PROCESSOR_SPEED).Get(), pJsonValue.Get()))`
- `0x1800166a4`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszSystemType).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016768`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_SYSTEM_TYPE).Get(), pJsonValue.Get()))`
- `0x1800167a8`: `CHR(FormatHardwareDisplayInfo(&pJsonValue))`
- `0x18001680a`: `CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_DISPLAY_CARDS).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetDeviceHardwareInfo(struct Windows::Data::Json::IJsonValue **a1)
{
  const WCHAR *v2; // rdx
  __int64 v3; // r14
  const WCHAR *v4; // rdx
  __int64 v5; // r15
  const WCHAR *v6; // rdx
  __int64 v7; // r12
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64); // rdx
  UINT32 v9; // edi
  int v10; // edx
  int v11; // ecx
  int ActivationFactory; // ebx
  int v13; // edx
  int v14; // ecx
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64); // rbx
  char v18; // r8
  HSTRING_HEADER *v19; // rax
  int v20; // edx
  int v21; // ecx
  char v22; // r8
  int v23; // edx
  int v24; // ecx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v27; // rbx
  HSTRING_HEADER *v28; // rax
  int v29; // edx
  int v30; // ecx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v32)(_QWORD, GUID *, __int64); // rbx
  GUID *v33; // rdx
  int v34; // edx
  int v35; // ecx
  char v36; // r8
  int v37; // edx
  int v38; // ecx
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v40)(_QWORD, GUID *, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v41; // rbx
  HSTRING_HEADER *v42; // rax
  int v43; // edx
  int v44; // ecx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64); // rbx
  char v47; // r8
  HSTRING_HEADER *v48; // rax
  int v49; // edx
  int v50; // ecx
  char v51; // r8
  int v52; // edx
  int v53; // ecx
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v55)(_QWORD, GUID *, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v56; // rbx
  HSTRING_HEADER *v57; // rax
  int v58; // edx
  int v59; // ecx
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v61)(_QWORD, GUID *, __int64); // rbx
  char v62; // r8
  HSTRING_HEADER *v63; // rax
  int v64; // edx
  int v65; // ecx
  char v66; // r8
  int v67; // edx
  int v68; // ecx
  __int64 (__fastcall ***v69)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v70)(_QWORD, GUID *, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v71; // rbx
  HSTRING_HEADER *v72; // rax
  int v73; // edx
  int v74; // ecx
  __int64 (__fastcall ***v75)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v76)(_QWORD, GUID *, __int64); // rbx
  char v77; // r8
  HSTRING_HEADER *v78; // rax
  int v79; // edx
  int v80; // ecx
  char v81; // r8
  int v82; // edx
  int v83; // ecx
  __int64 (__fastcall ***v84)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v85)(_QWORD, GUID *, __int64); // rdi
  struct Windows::Data::Json::IJsonValue *v86; // rbx
  HSTRING_HEADER *v87; // rax
  int v88; // edx
  int v89; // ecx
  int v90; // edx
  int v91; // ecx
  char v92; // r8
  struct Windows::Data::Json::IJsonValue *v93; // rbx
  __int64 (__fastcall ***v94)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v95)(_QWORD, GUID *, __int64); // rdi
  HSTRING_HEADER *v96; // rax
  int v97; // edx
  int v98; // ecx
  int v99; // edx
  int v100; // ecx
  struct Windows::Data::Json::IJsonValue *v101; // rax
  __int64 (__fastcall ***v102)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v103)(_QWORD, GUID *, __int64); // rcx
  struct Windows::Data::Json::IJsonValue *v105; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v106)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v107)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-C0h] BYREF
  int v108; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Data::Json::IJsonValue *v109; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v110; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v111; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v112; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR *v113; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v115)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-70h]
  _BYTE v116[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v117[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v118[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v119[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v120[32]; // [rsp+118h] [rbp+18h] BYREF

  std::wstring::wstring((__int64)v119);
  v108 = 0;
  std::wstring::wstring((__int64)v118);
  v3 = (unsigned int)v2;
  v110 = v2;
  std::wstring::wstring((__int64)v117);
  v5 = (unsigned int)v4;
  v111 = v4;
  std::wstring::wstring((__int64)v116);
  v7 = (unsigned int)v6;
  v112 = v6;
  std::wstring::wstring((__int64)v120);
  v106 = v8;
  v109 = (struct Windows::Data::Json::IJsonValue *)v8;
  v105 = (struct Windows::Data::Json::IJsonValue *)v8;
  v107 = v8;
  v115 = v8;
  v9 = (_DWORD)v8 + 28;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    (_DWORD)v8 + 29,
    (_DWORD)v8 + 28);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)v115, &v106);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        165,
        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pDeviceHardwareInfo.GetAddressOf()))");
    goto LABEL_70;
  }
  v115 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Data.Json.JsonValue", v9, 0x1Bu);
  ActivationFactory = RoGetActivationFactory(v115, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v107);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        166,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    goto LABEL_70;
  }
  if ( (int)DdcDeviceInfoHelper::GetHardwareSpecifications(
              (unsigned int)v119,
              (unsigned int)&v108,
              (unsigned int)v118,
              (unsigned int)v117,
              (__int64)v116,
              (__int64)v120) >= 0
    && (v113 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
        v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
        v110 = (const WCHAR *)v3,
        v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
        v111 = (const WCHAR *)v5,
        v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
        v112 = (const WCHAR *)v7,
        v15) )
  {
    v16 = v107;
    v17 = (*v107)[10];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v113, v18);
    ActivationFactory = v17(v16, (GUID *)v19[1].Reserved.Reserved1, (__int64)&v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v21,
          v20,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          181,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszRandomAccessMemory).Get(), pJsonValue.ReleaseAnd"
          "GetAddressOf()))");
      goto LABEL_70;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      v9,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)v115, &v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v24,
          v23,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          185,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  v25 = v106;
  v26 = (*v106)[7];
  v27 = v105;
  v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B598, v22);
  ActivationFactory = v26(v25, (GUID *)v28[1].Reserved.Reserved1, (__int64)v27);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v30,
        v29,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        188,
        "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_RANDOM_ACCESS_MEMORY).Get(), pJsonValue.Get()))");
    goto LABEL_70;
  }
  if ( v108 )
  {
    v31 = v107;
    v32 = (*v107)[9];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    ActivationFactory = v32(v31, v33, (__int64)&v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v35,
          v34,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          194,
          "CHR(pJsonValueStatics->CreateNumberValue(dwNumProcessors, pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)v115, &v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v38,
          v37,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          198,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  v39 = v106;
  v40 = (*v106)[7];
  v41 = v105;
  v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B590, v36);
  ActivationFactory = v40(v39, (GUID *)v42[1].Reserved.Reserved1, (__int64)v41);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v44,
        v43,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        201,
        "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_NUM_PROCESSORS).Get(), pJsonValue.Get()))");
    goto LABEL_70;
  }
  if ( v3 )
  {
    v45 = v107;
    v46 = (*v107)[10];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v110, v47);
    ActivationFactory = v46(v45, (GUID *)v48[1].Reserved.Reserved1, (__int64)&v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v50,
          v49,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          206,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProcessorName).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)v115, &v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v53,
          v52,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          210,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  v54 = v106;
  v55 = (*v106)[7];
  v56 = v105;
  v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B588, v51);
  ActivationFactory = v55(v54, (GUID *)v57[1].Reserved.Reserved1, (__int64)v56);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v59,
        v58,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        213,
        "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_PROCESSOR_NAME).Get(), pJsonValue.Get()))");
    goto LABEL_70;
  }
  if ( v5 )
  {
    v60 = v107;
    v61 = (*v107)[10];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v111, v62);
    ActivationFactory = v61(v60, (GUID *)v63[1].Reserved.Reserved1, (__int64)&v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v65,
          v64,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          218,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszProcessorSpeed).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)v115, &v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v68,
          v67,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          222,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
  }
  v69 = v106;
  v70 = (*v106)[7];
  v71 = v105;
  v72 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_18002B580, v66);
  ActivationFactory = v70(v69, (GUID *)v72[1].Reserved.Reserved1, (__int64)v71);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v74,
        v73,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        225,
        "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_PROCESSOR_SPEED).Get(), pJsonValue.Get()))");
    goto LABEL_70;
  }
  if ( v7 )
  {
    v75 = v107;
    v76 = (*v107)[10];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
    v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v112, v77);
    ActivationFactory = v76(v75, (GUID *)v78[1].Reserved.Reserved1, (__int64)&v105);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v80,
          v79,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          230,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszSystemType).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      goto LABEL_70;
    }
    goto LABEL_56;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
  v115 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)v115, &v105);
  if ( ActivationFactory >= 0 )
  {
LABEL_56:
    v84 = v106;
    v85 = (*v106)[7];
    v86 = v105;
    v87 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_18002B578,
            v81);
    ActivationFactory = v85(v84, (GUID *)v87[1].Reserved.Reserved1, (__int64)v86);
    if ( ActivationFactory >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
      ActivationFactory = DdcDeviceInfoHelper::FormatHardwareDisplayInfo(&v105);
      if ( ActivationFactory >= 0 )
      {
        v93 = v105;
        if ( v105
          && (v94 = v106,
              v95 = (*v106)[7],
              v96 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_18002B558,
                      v92),
              ActivationFactory = v95(v94, (GUID *)v96[1].Reserved.Reserved1, (__int64)v93),
              ActivationFactory < 0) )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v98,
              v97,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              243,
              "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_DISPLAY_CARDS).Get(), pJsonValue.Get()))");
        }
        else
        {
          ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                &v106,
                                (__int64)&v109);
          if ( ActivationFactory >= 0 )
          {
            v101 = v109;
            v109 = 0;
            *a1 = v101;
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v100,
              v99,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              246,
              "CHR(pDeviceHardwareInfo.As(&pDeviceHardwareInfoAsValue))");
          }
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v91,
          v90,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          240,
          "CHR(FormatHardwareDisplayInfo(&pJsonValue))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v89,
        v88,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        237,
        "CHR(pDeviceHardwareInfo->SetNamedValue(HStringReference(JSON_SYSTEM_TYPE).Get(), pJsonValue.Get()))");
    }
    goto LABEL_70;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v83,
      v82,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      234,
      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
LABEL_70:
  v102 = v107;
  if ( v107 )
  {
    v107 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v102)[2])(v102);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v105);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v109);
  v103 = v106;
  if ( v106 )
  {
    v106 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v103)[2])(v103);
  }
  std::wstring::_Tidy_deallocate((__int64)v120);
  std::wstring::_Tidy_deallocate((__int64)v116);
  std::wstring::_Tidy_deallocate((__int64)v117);
  std::wstring::_Tidy_deallocate((__int64)v118);
  std::wstring::_Tidy_deallocate((__int64)v119);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180015fbc  push    rbp
0x180015fbe  push    rbx
0x180015fbf  push    rsi
0x180015fc0  push    rdi
0x180015fc1  push    r12
0x180015fc3  push    r13
0x180015fc5  push    r14
0x180015fc7  push    r15
0x180015fc9  lea     rbp, [rsp-48h]
0x180015fce  sub     rsp, 148h
0x180015fd5  mov     rax, cs:__security_cookie
0x180015fdc  xor     rax, rsp
0x180015fdf  mov     [rbp+80h+var_48], rax
0x180015fe3  mov     r13, rcx
0x180015fe6  lea     rcx, [rbp+80h+var_88]
0x180015fea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015fef  nop
0x180015ff0  xor     edx, edx
0x180015ff2  mov     [rsp+180h+var_138], edx
0x180015ff6  lea     rcx, [rbp+80h+var_A8]
0x180015ffa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015fff  nop
0x180016000  mov     r14d, edx
0x180016003  mov     [rsp+180h+var_128], rdx
0x180016008  lea     rcx, [rbp+80h+var_C8]
0x18001600c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016011  nop
0x180016012  mov     r15d, edx
0x180016015  mov     [rsp+180h+var_120], rdx
0x18001601a  lea     rcx, [rbp+80h+var_E8]
0x18001601e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016023  nop
0x180016024  mov     r12d, edx
0x180016027  mov     [rsp+180h+var_118], rdx
0x18001602c  lea     rcx, [rbp+80h+var_68]
0x180016030  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016035  nop
0x180016036  mov     [rsp+180h+var_148], rdx
0x18001603b  mov     [rsp+180h+var_130], rdx
0x180016040  mov     [rsp+180h+var_150], rdx
0x180016045  mov     [rsp+180h+var_140], rdx
0x18001604a  mov     [rbp+80h+var_F0], rdx
0x18001604e  lea     edi, [rdx+1Ch]
0x180016051  mov     r9d, edi; unsigned int
0x180016054  lea     r8d, [rdx+1Dh]; unsigned int
0x180016058  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001605f  lea     rcx, [rsp+180h+hstringHeader]; hstringHeader
0x180016064  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016069  nop
0x18001606a  lea     rdx, [rsp+180h+var_148]
0x18001606f  mov     rcx, [rbp+80h+var_F0]
0x180016073  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180016078  mov     ebx, eax
0x18001607a  test    eax, eax
0x18001607c  jns     short loc_1800160B3
0x18001607e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016085  jz      loc_18001686C
0x18001608b  lea     rax, aChrActivateins_7; "CHR(ActivateInstance(HStringReference(R"...
0x180016092  mov     [rsp+180h+var_158], rax
0x180016097  mov     dword ptr [rsp+180h+var_160], 2A5h
0x18001609f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800160a6  mov     r8d, ebx
0x1800160a9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800160ae  jmp     loc_18001686C
0x1800160b3  mov     [rbp+80h+var_F0], 0
0x1800160bb  mov     esi, 1Bh
0x1800160c0  mov     r9d, esi; unsigned int
0x1800160c3  mov     r8d, edi; unsigned int
0x1800160c6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800160cd  lea     rcx, [rsp+180h+hstringHeader]; hstringHeader
0x1800160d2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800160d7  lea     r8, [rsp+180h+var_140]
0x1800160dc  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800160e3  mov     rcx, [rbp+80h+var_F0]
0x1800160e7  call    cs:__imp_RoGetActivationFactory
0x1800160ed  mov     ebx, eax
0x1800160ef  test    eax, eax
0x1800160f1  jns     short loc_180016116
0x1800160f3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800160fa  jz      loc_18001686C
0x180016100  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180016107  mov     [rsp+180h+var_158], rax
0x18001610c  mov     dword ptr [rsp+180h+var_160], 2A6h
0x180016114  jmp     short loc_18001609F
0x180016116  lea     rax, [rbp+80h+var_68]
0x18001611a  mov     [rsp+180h+var_158], rax
0x18001611f  lea     rax, [rbp+80h+var_E8]
0x180016123  mov     [rsp+180h+var_160], rax
0x180016128  lea     r9, [rbp+80h+var_C8]
0x18001612c  lea     r8, [rbp+80h+var_A8]
0x180016130  lea     rdx, [rsp+180h+var_138]
0x180016135  lea     rcx, [rbp+80h+var_88]
0x180016139  call    ?GetHardwareSpecifications@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK0000@Z; DdcDeviceInfoHelper::GetHardwareSpecifications(std::wstring *,ulong *,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x18001613e  test    eax, eax
0x180016140  js      loc_1800161F9
0x180016146  lea     rcx, [rbp+80h+var_88]
0x18001614a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001614f  mov     rdx, rax
0x180016152  mov     [rsp+180h+var_110], rax
0x180016157  lea     rcx, [rbp+80h+var_A8]
0x18001615b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016160  mov     r14, rax
0x180016163  mov     [rsp+180h+var_128], rax
0x180016168  lea     rcx, [rbp+80h+var_C8]
0x18001616c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016171  mov     r15, rax
0x180016174  mov     [rsp+180h+var_120], rax
0x180016179  lea     rcx, [rbp+80h+var_E8]
0x18001617d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016182  mov     r12, rax
0x180016185  mov     [rsp+180h+var_118], rax
0x18001618a  test    rdx, rdx
0x18001618d  jz      short loc_1800161F9
0x18001618f  mov     rdi, [rsp+180h+var_140]
0x180016194  mov     rdx, [rdi]
0x180016197  mov     rbx, [rdx+50h]
0x18001619b  lea     rcx, [rsp+180h+var_150]
0x1800161a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800161a5  lea     rdx, [rsp+180h+var_110]
0x1800161aa  lea     rcx, [rsp+180h+hstringHeader]
0x1800161af  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800161b4  nop
0x1800161b5  lea     r8, [rsp+180h+var_150]
0x1800161ba  mov     rdx, [rax+18h]
0x1800161be  mov     rcx, rdi
0x1800161c1  mov     rax, rbx
0x1800161c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161c9  mov     ebx, eax
0x1800161cb  test    eax, eax
0x1800161cd  jns     loc_18001625D
0x1800161d3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800161da  jz      loc_18001686C
0x1800161e0  lea     rax, aChrPjsonvalues_38; "CHR(pJsonValueStatics->CreateStringValu"...
0x1800161e7  mov     [rsp+180h+var_158], rax
0x1800161ec  mov     dword ptr [rsp+180h+var_160], 2B5h
0x1800161f4  jmp     loc_18001609F
0x1800161f9  lea     rcx, [rsp+180h+var_150]
0x1800161fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016203  mov     [rbp+80h+var_F0], 0
0x18001620b  mov     r9d, esi; unsigned int
0x18001620e  mov     r8d, edi; unsigned int
0x180016211  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180016218  lea     rcx, [rsp+180h+hstringHeader]; hstringHeader
0x18001621d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016222  nop
0x180016223  lea     rdx, [rsp+180h+var_150]
0x180016228  mov     rcx, [rbp+80h+var_F0]
0x18001622c  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x180016231  mov     ebx, eax
0x180016233  test    eax, eax
0x180016235  jns     short loc_18001625D
0x180016237  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001623e  jz      loc_18001686C
0x180016244  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x18001624b  mov     [rsp+180h+var_158], rax
0x180016250  mov     dword ptr [rsp+180h+var_160], 2B9h
0x180016258  jmp     loc_18001609F
0x18001625d  mov     rsi, [rsp+180h+var_148]
0x180016262  mov     rax, [rsi]
0x180016265  mov     rdi, [rax+38h]
0x180016269  mov     rbx, [rsp+180h+var_150]
0x18001626e  lea     rdx, off_18002B598; "InstalledRam"
0x180016275  lea     rcx, [rsp+180h+hstringHeader]
0x18001627a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001627f  nop
0x180016280  mov     r8, rbx
0x180016283  mov     rdx, [rax+18h]
0x180016287  mov     rcx, rsi
0x18001628a  mov     rax, rdi
0x18001628d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016292  mov     ebx, eax
0x180016294  test    eax, eax
0x180016296  jns     short loc_1800162BE
0x180016298  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001629f  jz      loc_18001686C
0x1800162a5  lea     rax, aChrPdevicehard_2; "CHR(pDeviceHardwareInfo->SetNamedValue("...
0x1800162ac  mov     [rsp+180h+var_158], rax
0x1800162b1  mov     dword ptr [rsp+180h+var_160], 2BCh
0x1800162b9  jmp     loc_18001609F
0x1800162be  mov     esi, [rsp+180h+var_138]
0x1800162c2  lea     rcx, [rsp+180h+var_150]
0x1800162c7  test    esi, esi
0x1800162c9  jz      short loc_180016324
0x1800162cb  mov     rdi, [rsp+180h+var_140]
0x1800162d0  mov     rax, [rdi]
0x1800162d3  mov     rbx, [rax+48h]
0x1800162d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800162dc  xorps   xmm1, xmm1
0x1800162df  cvtsi2sd xmm1, rsi
0x1800162e4  lea     r8, [rsp+180h+var_150]
0x1800162e9  mov     rcx, rdi
0x1800162ec  mov     rax, rbx
0x1800162ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f4  mov     ebx, eax
0x1800162f6  test    eax, eax
0x1800162f8  jns     loc_180016387
0x1800162fe  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016305  jz      loc_18001686C
0x18001630b  lea     rax, aChrPjsonvalues_27; "CHR(pJsonValueStatics->CreateNumberValu"...
0x180016312  mov     [rsp+180h+var_158], rax
0x180016317  mov     dword ptr [rsp+180h+var_160], 2C2h
0x18001631f  jmp     loc_18001609F
0x180016324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016329  mov     [rbp+80h+var_F0], 0
0x180016331  mov     r9d, 1Bh; unsigned int
0x180016337  lea     r8d, [r9+1]; unsigned int
0x18001633b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180016342  lea     rcx, [rsp+180h+hstringHeader]; hstringHeader
0x180016347  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001634c  nop
0x18001634d  lea     rdx, [rsp+180h+var_150]
0x180016352  mov     rcx, [rbp+80h+var_F0]
0x180016356  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x18001635b  mov     ebx, eax
0x18001635d  test    eax, eax
0x18001635f  jns     short loc_180016387
0x180016361  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016368  jz      loc_18001686C
0x18001636e  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x180016375  mov     [rsp+180h+var_158], rax
0x18001637a  mov     dword ptr [rsp+180h+var_160], 2C6h
0x180016382  jmp     loc_18001609F
0x180016387  mov     rsi, [rsp+180h+var_148]
0x18001638c  mov     rax, [rsi]
0x18001638f  mov     rdi, [rax+38h]
0x180016393  mov     rbx, [rsp+180h+var_150]
0x180016398  lea     rdx, off_18002B590; "NumProcessors"
0x18001639f  lea     rcx, [rsp+180h+hstringHeader]
0x1800163a4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800163a9  nop
0x1800163aa  mov     r8, rbx
0x1800163ad  mov     rdx, [rax+18h]
0x1800163b1  mov     rcx, rsi
0x1800163b4  mov     rax, rdi
0x1800163b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163bc  mov     ebx, eax
0x1800163be  test    eax, eax
0x1800163c0  jns     short loc_1800163E8
0x1800163c2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800163c9  jz      loc_18001686C
0x1800163cf  lea     rax, aChrPdevicehard_3; "CHR(pDeviceHardwareInfo->SetNamedValue("...
0x1800163d6  mov     [rsp+180h+var_158], rax
0x1800163db  mov     dword ptr [rsp+180h+var_160], 2C9h
0x1800163e3  jmp     loc_18001609F
0x1800163e8  lea     rcx, [rsp+180h+var_150]
0x1800163ed  test    r14, r14
0x1800163f0  jz      short loc_180016457
0x1800163f2  mov     rdi, [rsp+180h+var_140]
0x1800163f7  mov     rax, [rdi]
0x1800163fa  mov     rbx, [rax+50h]
0x1800163fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016403  lea     rdx, [rsp+180h+var_128]
0x180016408  lea     rcx, [rsp+180h+hstringHeader]
0x18001640d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016412  nop
0x180016413  lea     r8, [rsp+180h+var_150]
0x180016418  mov     rdx, [rax+18h]
0x18001641c  mov     rcx, rdi
0x18001641f  mov     rax, rbx
0x180016422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016427  mov     ebx, eax
0x180016429  test    eax, eax
0x18001642b  jns     loc_1800164BA
0x180016431  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016438  jz      loc_18001686C
0x18001643e  lea     rax, aChrPjsonvalues_81; "CHR(pJsonValueStatics->CreateStringValu"...
0x180016445  mov     [rsp+180h+var_158], rax
0x18001644a  mov     dword ptr [rsp+180h+var_160], 2CEh
0x180016452  jmp     loc_18001609F
0x180016457  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001645c  mov     [rbp+80h+var_F0], 0
0x180016464  mov     r9d, 1Bh; unsigned int
0x18001646a  lea     r8d, [r9+1]; unsigned int
0x18001646e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180016475  lea     rcx, [rsp+180h+hstringHeader]; hstringHeader
0x18001647a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001647f  nop
0x180016480  lea     rdx, [rsp+180h+var_150]
0x180016485  mov     rcx, [rbp+80h+var_F0]
0x180016489  call    ??$ActivateInstance@UIJsonValue@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonValue@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(HSTRING__ *,Windows::Data::Json::IJsonValue * *)
0x18001648e  mov     ebx, eax
0x180016490  test    eax, eax
0x180016492  jns     short loc_1800164BA
0x180016494  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001649b  jz      loc_18001686C
0x1800164a1  lea     rax, aChrActivateins_0; "CHR(ActivateInstance(HStringReference(R"...
0x1800164a8  mov     [rsp+180h+var_158], rax
0x1800164ad  mov     dword ptr [rsp+180h+var_160], 2D2h
0x1800164b5  jmp     loc_18001609F
0x1800164ba  mov     rsi, [rsp+180h+var_148]
0x1800164bf  mov     rax, [rsi]
0x1800164c2  mov     rdi, [rax+38h]
0x1800164c6  mov     rbx, [rsp+180h+var_150]
0x1800164cb  lea     rdx, off_18002B588; "ProcessorType"
0x1800164d2  lea     rcx, [rsp+180h+hstringHeader]
0x1800164d7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800164dc  nop
0x1800164dd  mov     r8, rbx
0x1800164e0  mov     rdx, [rax+18h]
0x1800164e4  mov     rcx, rsi
  ... truncated ...
```
