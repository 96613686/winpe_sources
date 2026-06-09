# MdmHttpWrapper::CreateLocationEntity(MdmLocation *,MdmLocationTechnique,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000bd94`
- end: `0x18000c6e1`
- name: `?CreateLocationEntity@MdmHttpWrapper@@CAJPEAUMdmLocation@@W4MdmLocationTechnique@@PEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `2381`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f3b8`

## callees

- `0x180001520`
- `0x1800065c0`
- `0x18000af24`
- `0x18000afa4`
- `0x18000b03c`
- `0x18000bd94`
- `0x1800117e4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bfd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c26f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c3e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c53e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bfd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c26f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c35a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c3e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c53e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bf1c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bf1c`

## string_xrefs

- `0x18000bef2`: `Windows.Data.Json.JsonValue`
- `0x18000c3dc`: `Windows.Data.Json.JsonValue`
- `0x18000be8a`: `Windows.Data.Json.JsonObject`
- `0x18000be06`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000bec5`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000bf3b`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000c5da`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000bdf2`: `CPR(ppJsonValue)`
- `0x18000be32`: `CBR(*ppJsonValue == nullptr)`
- `0x18000c417`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000bf9c`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLatitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c012`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Latitude").Get(), pJsonValue.Get()))`
- `0x18000c077`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLongitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c0ed`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Longitude").Get(), pJsonValue.Get()))`
- `0x18000c158`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwPositionAccuracy, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c1ce`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ErrorRadius").Get(), pJsonValue.Get()))`
- `0x18000c233`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dAltitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c2a9`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Altitude").Get(), pJsonValue.Get()))`
- `0x18000c31e`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwAltitudeAccuracy, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c398`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AltitudeErrorDistance").Get(), pJsonValue.Get()))`
- `0x18000c48d`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AltitudeErrorDistance").Get(), pJsonValue.Get()))`
- `0x18000c502`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszLocationTechniqueMappings[eLocationTechnique]).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c578`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"LocationTechnique").Get(), pJsonValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MdmHttpWrapper::CreateLocationEntity(unsigned int *a1, __int64 a2, _QWORD *a3)
{
  int v5; // r8d
  int ActivationFactory; // ebx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v14)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v15; // r14
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64, __int64 *); // rsi
  __int64 v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v23)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v24; // r14
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rsi
  __int64 v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v32)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v33; // r14
  HRESULT v34; // eax
  int v35; // edx
  unsigned int v36; // r8d
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, __int64, __int64 *); // rsi
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v41)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 v42; // r14
  HRESULT v43; // eax
  int v44; // edx
  unsigned int v45; // r8d
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, _QWORD, __int64 *); // rsi
  __int64 v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v50)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v51; // rsi
  HRESULT v52; // eax
  int v53; // edx
  unsigned int v54; // r8d
  __int64 v55; // rcx
  HRESULT v56; // eax
  int v57; // edx
  unsigned int v58; // r8d
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v60)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v61; // rsi
  HRESULT v62; // eax
  int v63; // edx
  unsigned int v64; // r8d
  __int64 v65; // rbx
  __int64 (__fastcall *v66)(__int64, _QWORD, __int64 *); // rdi
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 (__fastcall ***v69)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v70)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v71; // rsi
  HRESULT v72; // eax
  int v73; // edx
  unsigned int v74; // r8d
  __int64 (__fastcall ***v75)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v76)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 (__fastcall ***v82)(_QWORD, _QWORD, _QWORD); // rcx
  char v84; // [rsp+20h] [rbp-60h]
  const char *v85; // [rsp+28h] [rbp-58h]
  __int64 v86; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v87)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 v88; // [rsp+40h] [rbp-40h] BYREF
  __int64 v89; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v87 = 0;
  v89 = 0;
  v86 = 0;
  v88 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_89;
    v85 = "CPR(ppJsonValue)";
    v84 = -98;
    goto LABEL_4;
  }
  if ( *a3 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        159,
        "CBR(*ppJsonValue == nullptr)");
    goto LABEL_89;
  }
  if ( a1 )
  {
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
      __debugbreak();
    }
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v87);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v84 = -93;
      goto LABEL_15;
    }
    string = 0;
    v10 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v10 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v88);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))";
      v84 = -92;
      goto LABEL_15;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v88 + 72LL))(v88, a2, &v86);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLatitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v84 = -90;
      goto LABEL_15;
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
    v14 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
    v15 = v86;
    string = 0;
    v16 = WindowsCreateStringReference(L"Latitude", 8u, &hstringHeader, &string);
    if ( v16 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v14)[7](v13, string, v15);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Latitude\").Get(), pJsonValue.Get()))";
      v84 = -89;
      goto LABEL_15;
    }
    v19 = v88;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v88 + 72LL);
    v21 = v86;
    if ( v86 )
    {
      v86 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    ActivationFactory = v20(v19, a2, &v86);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLongitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v84 = -88;
      goto LABEL_15;
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
    v23 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
    v24 = v86;
    string = 0;
    v25 = WindowsCreateStringReference(L"Longitude", 9u, &hstringHeader, &string);
    if ( v25 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v23)[7](v22, string, v24);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Longitude\").Get(), pJsonValue.Get()))";
      v84 = -87;
      goto LABEL_15;
    }
    v28 = v88;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v88 + 72LL);
    v30 = v86;
    if ( v86 )
    {
      v86 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    ActivationFactory = v29(v28, a1[6], &v86);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwPositionAccuracy, pJsonValue.ReleaseAndGetAddressOf()))";
      v84 = -86;
      goto LABEL_15;
    }
    v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
    v32 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
    v33 = v86;
    string = 0;
    v34 = WindowsCreateStringReference(L"ErrorRadius", 0xBu, &hstringHeader, &string);
    if ( v34 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v34, v35, v36);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v32)[7](v31, string, v33);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ErrorRadius\").Get(), pJsonValue.Get()))";
      v84 = -85;
      goto LABEL_15;
    }
    v37 = v88;
    v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v88 + 72LL);
    v39 = v86;
    if ( v86 )
    {
      v86 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    ActivationFactory = v38(v37, a2, &v86);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dAltitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v84 = -84;
      goto LABEL_15;
    }
    v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
    v41 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
    v42 = v86;
    string = 0;
    v43 = WindowsCreateStringReference(L"Altitude", 8u, &hstringHeader, &string);
    if ( v43 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v43, v44, v45);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v41)[7](v40, string, v42);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Altitude\").Get(), pJsonValue.Get()))";
      v84 = -83;
      goto LABEL_15;
    }
    if ( a1[7] )
    {
      v46 = v88;
      v47 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v88 + 72LL);
      v48 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      ActivationFactory = v47(v46, a1[8], &v86);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwAltitudeAccuracy, pJsonValue.ReleaseAndGetAddressOf()))";
        v84 = -79;
        goto LABEL_15;
      }
      v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
      v50 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
      v51 = v86;
      string = 0;
      v52 = WindowsCreateStringReference(L"AltitudeErrorDistance", 0x15u, &hstringHeader, &string);
      if ( v52 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v52, v53, v54);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v50)[7](v49, string, v51);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AltitudeErrorDistance\").Get(), pJsonValue.Get()))";
        v84 = -78;
        goto LABEL_15;
      }
    }
    else
    {
      v55 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      string = 0;
      v56 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v56 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v56, v57, v58);
        __debugbreak();
      }
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(string, &v86);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v84 = -74;
        goto LABEL_15;
      }
      v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
      v60 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
      v61 = v86;
      string = 0;
      v62 = WindowsCreateStringReference(L"AltitudeErrorDistance", 0x15u, &hstringHeader, &string);
      if ( v62 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v62, v63, v64);
        JUMPOUT(0x18000C6E0LL);
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v60)[7](v59, string, v61);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AltitudeErrorDistance\").Get(), pJsonValue.Get()))";
        v84 = -73;
        goto LABEL_15;
      }
    }
    v65 = v88;
    v66 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v88 + 80LL);
    v67 = v86;
    if ( v86 )
    {
      v86 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &wszLocationTechniqueMappings);
    ActivationFactory = v66(v65, *(_QWORD *)(v68 + 24), &v86);
    if ( ActivationFactory >= 0 )
    {
      v69 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
      v70 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v87;
      v71 = v86;
      string = 0;
      v72 = WindowsCreateStringReference(L"LocationTechnique", 0x11u, &hstringHeader, &string);
      if ( v72 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v72, v73, v74);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v70)[7](v69, string, v71);
      if ( ActivationFactory >= 0 )
      {
        v75 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
        v76 = **v87;
        v77 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        ActivationFactory = v76(v75, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v89);
        if ( ActivationFactory >= 0 )
        {
          v78 = v89;
          v89 = 0;
          *a3 = v78;
          goto LABEL_89;
        }
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
        v84 = -67;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v85 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"LocationTechnique\").Get(), pJsonValue.Get()))";
        v84 = -69;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v85 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszLocationTechniqueMappings[eLocationTechnique])."
            "Get(), pJsonValue.ReleaseAndGetAddressOf()))";
      v84 = -70;
    }
LABEL_15:
    v5 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v84,
      v85);
    goto LABEL_89;
  }
  ActivationFactory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      0,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      160,
      "CPR(pLocation)");
LABEL_89:
  v79 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  }
  v80 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  v81 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  }
  v82 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
  if ( v87 )
  {
    v87 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v82)[2])(v82);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000bd94  mov     [rsp-28h+arg_8], rbx
0x18000bd99  mov     [rsp-28h+arg_18], rsi
0x18000bd9e  push    rbp
0x18000bd9f  push    rdi
0x18000bda0  push    r12
0x18000bda2  push    r14
0x18000bda4  push    r15
0x18000bda6  mov     rbp, rsp
0x18000bda9  sub     rsp, 80h
0x18000bdb0  mov     rax, cs:__security_cookie
0x18000bdb7  xor     rax, rsp
0x18000bdba  mov     [rbp+var_10], rax
0x18000bdbe  mov     r15, r8
0x18000bdc1  mov     rdi, rcx
0x18000bdc4  xor     r12d, r12d
0x18000bdc7  mov     [rbp+var_48], r12
0x18000bdcb  mov     [rbp+var_38], r12
0x18000bdcf  mov     [rbp+var_50], r12
0x18000bdd3  mov     [rbp+var_40], r12
0x18000bdd7  test    r8, r8
0x18000bdda  jnz     short loc_18000BE17
0x18000bddc  mov     r8d, 80070057h
0x18000bde2  mov     ebx, r8d
0x18000bde5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bdec  jz      loc_18000C5FE
0x18000bdf2  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000bdf9  mov     [rsp+80h+var_58], rax
0x18000bdfe  mov     dword ptr [rsp+80h+var_60], 49Eh
0x18000be06  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000be0d  call    McTemplateU0dsqs_EventWriteTransfer
0x18000be12  jmp     loc_18000C5FE
0x18000be17  cmp     [r8], r12
0x18000be1a  jz      short loc_18000BE48
0x18000be1c  mov     r8d, 80070057h
0x18000be22  mov     ebx, r8d
0x18000be25  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000be2c  jz      loc_18000C5FE
0x18000be32  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000be39  mov     [rsp+80h+var_58], rax
0x18000be3e  mov     dword ptr [rsp+80h+var_60], 49Fh
0x18000be46  jmp     short loc_18000BE06
0x18000be48  test    rdi, rdi
0x18000be4b  jnz     short loc_18000BE79
0x18000be4d  mov     r8d, 80070057h
0x18000be53  mov     ebx, r8d
0x18000be56  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000be5d  jz      loc_18000C5FE
0x18000be63  lea     rax, aCprPlocation; "CPR(pLocation)"
0x18000be6a  mov     [rsp+80h+var_58], rax
0x18000be6f  mov     dword ptr [rsp+80h+var_60], 4A0h
0x18000be77  jmp     short loc_18000BE06
0x18000be79  mov     [rbp+string], r12
0x18000be7d  lea     r9, [rbp+string]; string
0x18000be81  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000be85  mov     edx, 1Ch; length
0x18000be8a  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000be91  call    cs:__imp_WindowsCreateStringReference
0x18000be98  nop     dword ptr [rax+rax+00h]
0x18000be9d  test    eax, eax
0x18000be9f  js      loc_18000C699
0x18000bea5  lea     rdx, [rbp+var_48]
0x18000bea9  mov     rcx, [rbp+string]
0x18000bead  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000beb2  mov     ebx, eax
0x18000beb4  test    eax, eax
0x18000beb6  jns     short loc_18000BEE1
0x18000beb8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bebf  jz      loc_18000C5FE
0x18000bec5  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000becc  mov     [rsp+80h+var_58], rax
0x18000bed1  mov     dword ptr [rsp+80h+var_60], 4A3h
0x18000bed9  mov     r8d, ebx
0x18000bedc  jmp     loc_18000BE06
0x18000bee1  mov     [rbp+string], r12
0x18000bee5  lea     r9, [rbp+string]; string
0x18000bee9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000beed  mov     edx, 1Bh; length
0x18000bef2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000bef9  call    cs:__imp_WindowsCreateStringReference
0x18000bf00  nop     dword ptr [rax+rax+00h]
0x18000bf05  test    eax, eax
0x18000bf07  js      loc_18000C6A1
0x18000bf0d  lea     r8, [rbp+var_40]
0x18000bf11  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000bf18  mov     rcx, [rbp+string]
0x18000bf1c  call    cs:__imp_RoGetActivationFactory
0x18000bf23  nop     dword ptr [rax+rax+00h]
0x18000bf28  mov     ebx, eax
0x18000bf2a  test    eax, eax
0x18000bf2c  jns     short loc_18000BF51
0x18000bf2e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bf35  jz      loc_18000C5FE
0x18000bf3b  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000bf42  mov     [rsp+80h+var_58], rax
0x18000bf47  mov     dword ptr [rsp+80h+var_60], 4A4h
0x18000bf4f  jmp     short loc_18000BED9
0x18000bf51  mov     rbx, [rbp+var_40]
0x18000bf55  mov     rax, [rbx]
0x18000bf58  mov     rsi, [rax+48h]
0x18000bf5c  mov     rcx, [rbp+var_50]
0x18000bf60  test    rcx, rcx
0x18000bf63  jz      short loc_18000BF76
0x18000bf65  mov     [rbp+var_50], r12
0x18000bf69  mov     rdx, [rcx]
0x18000bf6c  mov     rax, [rdx+10h]
0x18000bf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf75  nop
0x18000bf76  lea     r8, [rbp+var_50]
0x18000bf7a  movsd   xmm1, qword ptr [rdi]
0x18000bf7e  mov     rcx, rbx
0x18000bf81  mov     rax, rsi
0x18000bf84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf89  mov     ebx, eax
0x18000bf8b  test    eax, eax
0x18000bf8d  jns     short loc_18000BFB5
0x18000bf8f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bf96  jz      loc_18000C5FE
0x18000bf9c  lea     rax, aChrPjsonvalues_10; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000bfa3  mov     [rsp+80h+var_58], rax
0x18000bfa8  mov     dword ptr [rsp+80h+var_60], 4A6h
0x18000bfb0  jmp     loc_18000BED9
0x18000bfb5  mov     rbx, [rbp+var_48]
0x18000bfb9  mov     rsi, [rbx]
0x18000bfbc  mov     r14, [rbp+var_50]
0x18000bfc0  mov     [rbp+string], r12
0x18000bfc4  lea     r9, [rbp+string]; string
0x18000bfc8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bfcc  mov     edx, 8; length
0x18000bfd1  lea     rcx, aLatitude; "Latitude"
0x18000bfd8  call    cs:__imp_WindowsCreateStringReference
0x18000bfdf  nop     dword ptr [rax+rax+00h]
0x18000bfe4  test    eax, eax
0x18000bfe6  js      loc_18000C6A9
0x18000bfec  mov     r8, r14
0x18000bfef  mov     rdx, [rbp+string]
0x18000bff3  mov     rcx, rbx
0x18000bff6  mov     rax, [rsi+38h]
0x18000bffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfff  mov     ebx, eax
0x18000c001  test    eax, eax
0x18000c003  jns     short loc_18000C02B
0x18000c005  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c00c  jz      loc_18000C5FE
0x18000c012  lea     rax, aChrPjsonobject_13; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000c019  mov     [rsp+80h+var_58], rax
0x18000c01e  mov     dword ptr [rsp+80h+var_60], 4A7h
0x18000c026  jmp     loc_18000BED9
0x18000c02b  mov     rbx, [rbp+var_40]
0x18000c02f  mov     rax, [rbx]
0x18000c032  mov     rsi, [rax+48h]
0x18000c036  mov     rcx, [rbp+var_50]
0x18000c03a  test    rcx, rcx
0x18000c03d  jz      short loc_18000C050
0x18000c03f  mov     [rbp+var_50], r12
0x18000c043  mov     rdx, [rcx]
0x18000c046  mov     rax, [rdx+10h]
0x18000c04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04f  nop
0x18000c050  lea     r8, [rbp+var_50]
0x18000c054  movsd   xmm1, qword ptr [rdi+8]
0x18000c059  mov     rcx, rbx
0x18000c05c  mov     rax, rsi
0x18000c05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c064  mov     ebx, eax
0x18000c066  test    eax, eax
0x18000c068  jns     short loc_18000C090
0x18000c06a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c071  jz      loc_18000C5FE
0x18000c077  lea     rax, aChrPjsonvalues_1; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000c07e  mov     [rsp+80h+var_58], rax
0x18000c083  mov     dword ptr [rsp+80h+var_60], 4A8h
0x18000c08b  jmp     loc_18000BED9
0x18000c090  mov     rbx, [rbp+var_48]
0x18000c094  mov     rsi, [rbx]
0x18000c097  mov     r14, [rbp+var_50]
0x18000c09b  mov     [rbp+string], r12
0x18000c09f  lea     r9, [rbp+string]; string
0x18000c0a3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000c0a7  mov     edx, 9; length
0x18000c0ac  lea     rcx, aLongitude; "Longitude"
0x18000c0b3  call    cs:__imp_WindowsCreateStringReference
0x18000c0ba  nop     dword ptr [rax+rax+00h]
0x18000c0bf  test    eax, eax
0x18000c0c1  js      loc_18000C6B1
0x18000c0c7  mov     r8, r14
0x18000c0ca  mov     rdx, [rbp+string]
0x18000c0ce  mov     rcx, rbx
0x18000c0d1  mov     rax, [rsi+38h]
0x18000c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0da  mov     ebx, eax
0x18000c0dc  test    eax, eax
0x18000c0de  jns     short loc_18000C106
0x18000c0e0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c0e7  jz      loc_18000C5FE
0x18000c0ed  lea     rax, aChrPjsonobject_22; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000c0f4  mov     [rsp+80h+var_58], rax
0x18000c0f9  mov     dword ptr [rsp+80h+var_60], 4A9h
0x18000c101  jmp     loc_18000BED9
0x18000c106  mov     rbx, [rbp+var_40]
0x18000c10a  mov     rax, [rbx]
0x18000c10d  mov     rsi, [rax+48h]
0x18000c111  mov     rcx, [rbp+var_50]
0x18000c115  test    rcx, rcx
0x18000c118  jz      short loc_18000C12B
0x18000c11a  mov     [rbp+var_50], r12
0x18000c11e  mov     rdx, [rcx]
0x18000c121  mov     rax, [rdx+10h]
0x18000c125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12a  nop
0x18000c12b  mov     edx, [rdi+18h]
0x18000c12e  xorps   xmm1, xmm1
0x18000c131  cvtsi2sd xmm1, rdx
0x18000c136  lea     r8, [rbp+var_50]
0x18000c13a  mov     rcx, rbx
0x18000c13d  mov     rax, rsi
0x18000c140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c145  mov     ebx, eax
0x18000c147  test    eax, eax
0x18000c149  jns     short loc_18000C171
0x18000c14b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c152  jz      loc_18000C5FE
0x18000c158  lea     rax, aChrPjsonvalues_6; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000c15f  mov     [rsp+80h+var_58], rax
0x18000c164  mov     dword ptr [rsp+80h+var_60], 4AAh
0x18000c16c  jmp     loc_18000BED9
0x18000c171  mov     rbx, [rbp+var_48]
0x18000c175  mov     rsi, [rbx]
0x18000c178  mov     r14, [rbp+var_50]
0x18000c17c  mov     [rbp+string], r12
0x18000c180  lea     r9, [rbp+string]; string
0x18000c184  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000c188  mov     edx, 0Bh; length
0x18000c18d  lea     rcx, aErrorradius; "ErrorRadius"
0x18000c194  call    cs:__imp_WindowsCreateStringReference
0x18000c19b  nop     dword ptr [rax+rax+00h]
0x18000c1a0  test    eax, eax
0x18000c1a2  js      loc_18000C6B9
0x18000c1a8  mov     r8, r14
0x18000c1ab  mov     rdx, [rbp+string]
0x18000c1af  mov     rcx, rbx
0x18000c1b2  mov     rax, [rsi+38h]
0x18000c1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1bb  mov     ebx, eax
0x18000c1bd  test    eax, eax
0x18000c1bf  jns     short loc_18000C1E7
0x18000c1c1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c1c8  jz      loc_18000C5FE
0x18000c1ce  lea     rax, aChrPjsonobject_4; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000c1d5  mov     [rsp+80h+var_58], rax
0x18000c1da  mov     dword ptr [rsp+80h+var_60], 4ABh
0x18000c1e2  jmp     loc_18000BED9
0x18000c1e7  mov     rbx, [rbp+var_40]
0x18000c1eb  mov     rax, [rbx]
0x18000c1ee  mov     rsi, [rax+48h]
0x18000c1f2  mov     rcx, [rbp+var_50]
0x18000c1f6  test    rcx, rcx
0x18000c1f9  jz      short loc_18000C20C
0x18000c1fb  mov     [rbp+var_50], r12
0x18000c1ff  mov     rdx, [rcx]
0x18000c202  mov     rax, [rdx+10h]
0x18000c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20b  nop
0x18000c20c  lea     r8, [rbp+var_50]
0x18000c210  movsd   xmm1, qword ptr [rdi+10h]
0x18000c215  mov     rcx, rbx
0x18000c218  mov     rax, rsi
0x18000c21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c220  mov     ebx, eax
0x18000c222  test    eax, eax
0x18000c224  jns     short loc_18000C24C
0x18000c226  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c22d  jz      loc_18000C5FE
0x18000c233  lea     rax, aChrPjsonvalues_13; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000c23a  mov     [rsp+80h+var_58], rax
0x18000c23f  mov     dword ptr [rsp+80h+var_60], 4ACh
0x18000c247  jmp     loc_18000BED9
0x18000c24c  mov     rbx, [rbp+var_48]
0x18000c250  mov     rsi, [rbx]
0x18000c253  mov     r14, [rbp+var_50]
0x18000c257  mov     [rbp+string], r12
0x18000c25b  lea     r9, [rbp+string]; string
0x18000c25f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000c263  mov     edx, 8; length
0x18000c268  lea     rcx, aAltitude; "Altitude"
0x18000c26f  call    cs:__imp_WindowsCreateStringReference
0x18000c276  nop     dword ptr [rax+rax+00h]
0x18000c27b  test    eax, eax
0x18000c27d  js      loc_18000C6C1
0x18000c283  mov     r8, r14
0x18000c286  mov     rdx, [rbp+string]
0x18000c28a  mov     rcx, rbx
0x18000c28d  mov     rax, [rsi+38h]
0x18000c291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c296  mov     ebx, eax
0x18000c298  test    eax, eax
0x18000c29a  jns     short loc_18000C2C2
0x18000c29c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000c2a3  jz      loc_18000C5FE
0x18000c2a9  lea     rax, aChrPjsonobject_21; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000c2b0  mov     [rsp+80h+var_58], rax
  ... truncated ...
```
