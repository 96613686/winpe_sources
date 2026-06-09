# MdmHttpWrapper::CreateLocationEntity(MdmLocation *,MdmLocationTechnique,Windows::Data::Json::IJsonValue * *)

- ea: `0x18000ba7c`
- end: `0x18000c386`
- name: `?CreateLocationEntity@MdmHttpWrapper@@CAJPEAUMdmLocation@@W4MdmLocationTechnique@@PEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `2314`
- prototype: `__int64 __fastcall(unsigned int *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef34`

## callees

- `0x180001520`
- `0x180006548`
- `0x18000ac7c`
- `0x18000acf4`
- `0x18000ad84`
- `0x18000ba7c`
- `0x180011414`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bbdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bcae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c09b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bb79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bbdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bcae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c09b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c105`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1ea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bbf8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000bbf8`

## string_xrefs

- `0x18000bbd4`: `Windows.Data.Json.JsonValue`
- `0x18000c094`: `Windows.Data.Json.JsonValue`
- `0x18000bb72`: `Windows.Data.Json.JsonObject`
- `0x18000baee`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000bba7`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000bc11`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18000c280`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x18000bada`: `CPR(ppJsonValue)`
- `0x18000bb1a`: `CBR(*ppJsonValue == nullptr)`
- `0x18000c0c9`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000bc72`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLatitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000bce2`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Latitude").Get(), pJsonValue.Get()))`
- `0x18000bd47`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLongitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000bdb7`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Longitude").Get(), pJsonValue.Get()))`
- `0x18000be22`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwPositionAccuracy, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000be92`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ErrorRadius").Get(), pJsonValue.Get()))`
- `0x18000bef7`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dAltitude, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000bf67`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Altitude").Get(), pJsonValue.Get()))`
- `0x18000bfdc`: `CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwAltitudeAccuracy, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c050`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AltitudeErrorDistance").Get(), pJsonValue.Get()))`
- `0x18000c139`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AltitudeErrorDistance").Get(), pJsonValue.Get()))`
- `0x18000c1ae`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszLocationTechniqueMappings[eLocationTechnique]).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000c21e`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"LocationTechnique").Get(), pJsonValue.Get()))`

## pseudocode

```c
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
  unsigned int v55; // r8d
  __int64 v56; // rcx
  HRESULT v57; // eax
  int v58; // edx
  unsigned int v59; // r8d
  __int64 (__fastcall ***v60)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v61)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v62; // rsi
  HRESULT v63; // eax
  int v64; // edx
  unsigned int v65; // r8d
  __int64 v66; // rbx
  __int64 (__fastcall *v67)(__int64, PVOID, __int64 *); // rdi
  __int64 v68; // rcx
  HSTRING_HEADER *v69; // rax
  __int64 (__fastcall ***v70)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v71)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v72; // rsi
  HRESULT v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  __int64 (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v77)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 (__fastcall ***v83)(_QWORD, _QWORD, _QWORD); // rcx
  char v85; // [rsp+20h] [rbp-60h]
  const char *v86; // [rsp+28h] [rbp-58h]
  __int64 v87; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v88)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 v89; // [rsp+40h] [rbp-40h] BYREF
  __int64 v90; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v88 = 0;
  v90 = 0;
  v87 = 0;
  v89 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_89;
    v86 = "CPR(ppJsonValue)";
    v85 = -98;
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
        (__int64)"CBR(*ppJsonValue == nullptr)");
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
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v88);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v85 = -93;
      goto LABEL_15;
    }
    string = 0;
    v10 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
    if ( v10 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v89);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))";
      v85 = -92;
      goto LABEL_15;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v89 + 72LL))(v89, a2, &v87);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLatitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v85 = -90;
      goto LABEL_15;
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
    v14 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
    v15 = v87;
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
      v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Latitude\").Get(), pJsonValue.Get()))";
      v85 = -89;
      goto LABEL_15;
    }
    v19 = v89;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v89 + 72LL);
    v21 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    ActivationFactory = v20(v19, a2, &v87);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dLongitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v85 = -88;
      goto LABEL_15;
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
    v23 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
    v24 = v87;
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
      v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Longitude\").Get(), pJsonValue.Get()))";
      v85 = -87;
      goto LABEL_15;
    }
    v28 = v89;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v89 + 72LL);
    v30 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    ActivationFactory = v29(v28, a1[6], &v87);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwPositionAccuracy, pJsonValue.ReleaseAndGetAddressOf()))";
      v85 = -86;
      goto LABEL_15;
    }
    v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
    v32 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
    v33 = v87;
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
      v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ErrorRadius\").Get(), pJsonValue.Get()))";
      v85 = -85;
      goto LABEL_15;
    }
    v37 = v89;
    v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v89 + 72LL);
    v39 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    ActivationFactory = v38(v37, a2, &v87);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dAltitude, pJsonValue.ReleaseAndGetAddressOf()))";
      v85 = -84;
      goto LABEL_15;
    }
    v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
    v41 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
    v42 = v87;
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
      v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Altitude\").Get(), pJsonValue.Get()))";
      v85 = -83;
      goto LABEL_15;
    }
    if ( a1[7] )
    {
      v46 = v89;
      v47 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v89 + 72LL);
      v48 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      ActivationFactory = v47(v46, a1[8], &v87);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v86 = "CHR(pJsonValueStatics->CreateNumberValue(pLocation->m_dwAltitudeAccuracy, pJsonValue.ReleaseAndGetAddressOf()))";
        v85 = -79;
        goto LABEL_15;
      }
      v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
      v50 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
      v51 = v87;
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
        v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AltitudeErrorDistance\").Get(), pJsonValue.Get()))";
        v85 = -78;
        goto LABEL_15;
      }
    }
    else
    {
      v56 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      string = 0;
      v57 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v57 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v57, v58, v59);
        __debugbreak();
      }
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)string, &v87);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v86 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseA"
              "ndGetAddressOf()))";
        v85 = -74;
        goto LABEL_15;
      }
      v60 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
      v61 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
      v62 = v87;
      string = 0;
      v63 = WindowsCreateStringReference(L"AltitudeErrorDistance", 0x15u, &hstringHeader, &string);
      if ( v63 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v63, v64, v65);
        JUMPOUT(0x18000C385LL);
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v61)[7](v60, string, v62);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AltitudeErrorDistance\").Get(), pJsonValue.Get()))";
        v85 = -73;
        goto LABEL_15;
      }
    }
    v66 = v89;
    v67 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v89 + 80LL);
    v68 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&wszLocationTechniqueMappings,
            v55);
    ActivationFactory = v67(v66, v69[1].Reserved.Reserved1, &v87);
    if ( ActivationFactory >= 0 )
    {
      v70 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
      v71 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v88;
      v72 = v87;
      string = 0;
      v73 = WindowsCreateStringReference(L"LocationTechnique", 0x11u, &hstringHeader, &string);
      if ( v73 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v71)[7](v70, string, v72);
      if ( ActivationFactory >= 0 )
      {
        v76 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
        v77 = **v88;
        v78 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        }
        ActivationFactory = v77(v76, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v90);
        if ( ActivationFactory >= 0 )
        {
          v79 = v90;
          v90 = 0;
          *a3 = v79;
          goto LABEL_89;
        }
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v86 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
        v85 = -67;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_89;
        v86 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"LocationTechnique\").Get(), pJsonValue.Get()))";
        v85 = -69;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_89;
      v86 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszLocationTechniqueMappings[eLocationTechnique])."
            "Get(), pJsonValue.ReleaseAndGetAddressOf()))";
      v85 = -70;
    }
LABEL_15:
    v5 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      v85,
      (__int64)v86);
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
      (__int64)"CPR(pLocation)");
LABEL_89:
  v80 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  v81 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  }
  v82 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  }
  v83 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v88;
  if ( v88 )
  {
    v88 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v83)[2])(v83);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000ba7c  mov     [rsp-28h+arg_8], rbx
0x18000ba81  mov     [rsp-28h+arg_18], rsi
0x18000ba86  push    rbp
0x18000ba87  push    rdi
0x18000ba88  push    r12
0x18000ba8a  push    r14
0x18000ba8c  push    r15
0x18000ba8e  mov     rbp, rsp
0x18000ba91  sub     rsp, 80h
0x18000ba98  mov     rax, cs:__security_cookie
0x18000ba9f  xor     rax, rsp
0x18000baa2  mov     [rbp+var_10], rax
0x18000baa6  mov     r15, r8
0x18000baa9  mov     rdi, rcx
0x18000baac  xor     r12d, r12d
0x18000baaf  mov     [rbp+var_48], r12
0x18000bab3  mov     [rbp+var_38], r12
0x18000bab7  mov     [rbp+var_50], r12
0x18000babb  mov     [rbp+var_40], r12
0x18000babf  test    r8, r8
0x18000bac2  jnz     short loc_18000BAFF
0x18000bac4  mov     r8d, 80070057h
0x18000baca  mov     ebx, r8d
0x18000bacd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bad4  jz      loc_18000C2A4
0x18000bada  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x18000bae1  mov     [rsp+80h+var_58], rax
0x18000bae6  mov     dword ptr [rsp+80h+var_60], 49Eh
0x18000baee  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000baf5  call    McTemplateU0dsqs_EventWriteTransfer
0x18000bafa  jmp     loc_18000C2A4
0x18000baff  cmp     [r8], r12
0x18000bb02  jz      short loc_18000BB30
0x18000bb04  mov     r8d, 80070057h
0x18000bb0a  mov     ebx, r8d
0x18000bb0d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bb14  jz      loc_18000C2A4
0x18000bb1a  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == nullptr)"
0x18000bb21  mov     [rsp+80h+var_58], rax
0x18000bb26  mov     dword ptr [rsp+80h+var_60], 49Fh
0x18000bb2e  jmp     short loc_18000BAEE
0x18000bb30  test    rdi, rdi
0x18000bb33  jnz     short loc_18000BB61
0x18000bb35  mov     r8d, 80070057h
0x18000bb3b  mov     ebx, r8d
0x18000bb3e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bb45  jz      loc_18000C2A4
0x18000bb4b  lea     rax, aCprPlocation; "CPR(pLocation)"
0x18000bb52  mov     [rsp+80h+var_58], rax
0x18000bb57  mov     dword ptr [rsp+80h+var_60], 4A0h
0x18000bb5f  jmp     short loc_18000BAEE
0x18000bb61  mov     [rbp+string], r12
0x18000bb65  lea     r9, [rbp+string]; string
0x18000bb69  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bb6d  mov     edx, 1Ch; length
0x18000bb72  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000bb79  call    cs:__imp_WindowsCreateStringReference
0x18000bb7f  test    eax, eax
0x18000bb81  js      loc_18000C33E
0x18000bb87  lea     rdx, [rbp+var_48]
0x18000bb8b  mov     rcx, [rbp+string]
0x18000bb8f  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000bb94  mov     ebx, eax
0x18000bb96  test    eax, eax
0x18000bb98  jns     short loc_18000BBC3
0x18000bb9a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bba1  jz      loc_18000C2A4
0x18000bba7  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000bbae  mov     [rsp+80h+var_58], rax
0x18000bbb3  mov     dword ptr [rsp+80h+var_60], 4A3h
0x18000bbbb  mov     r8d, ebx
0x18000bbbe  jmp     loc_18000BAEE
0x18000bbc3  mov     [rbp+string], r12
0x18000bbc7  lea     r9, [rbp+string]; string
0x18000bbcb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bbcf  mov     edx, 1Bh; length
0x18000bbd4  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000bbdb  call    cs:__imp_WindowsCreateStringReference
0x18000bbe1  test    eax, eax
0x18000bbe3  js      loc_18000C346
0x18000bbe9  lea     r8, [rbp+var_40]
0x18000bbed  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000bbf4  mov     rcx, [rbp+string]
0x18000bbf8  call    cs:__imp_RoGetActivationFactory
0x18000bbfe  mov     ebx, eax
0x18000bc00  test    eax, eax
0x18000bc02  jns     short loc_18000BC27
0x18000bc04  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bc0b  jz      loc_18000C2A4
0x18000bc11  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000bc18  mov     [rsp+80h+var_58], rax
0x18000bc1d  mov     dword ptr [rsp+80h+var_60], 4A4h
0x18000bc25  jmp     short loc_18000BBBB
0x18000bc27  mov     rbx, [rbp+var_40]
0x18000bc2b  mov     rax, [rbx]
0x18000bc2e  mov     rsi, [rax+48h]
0x18000bc32  mov     rcx, [rbp+var_50]
0x18000bc36  test    rcx, rcx
0x18000bc39  jz      short loc_18000BC4C
0x18000bc3b  mov     [rbp+var_50], r12
0x18000bc3f  mov     rdx, [rcx]
0x18000bc42  mov     rax, [rdx+10h]
0x18000bc46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4b  nop
0x18000bc4c  lea     r8, [rbp+var_50]
0x18000bc50  movsd   xmm1, qword ptr [rdi]
0x18000bc54  mov     rcx, rbx
0x18000bc57  mov     rax, rsi
0x18000bc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc5f  mov     ebx, eax
0x18000bc61  test    eax, eax
0x18000bc63  jns     short loc_18000BC8B
0x18000bc65  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bc6c  jz      loc_18000C2A4
0x18000bc72  lea     rax, aChrPjsonvalues_10; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000bc79  mov     [rsp+80h+var_58], rax
0x18000bc7e  mov     dword ptr [rsp+80h+var_60], 4A6h
0x18000bc86  jmp     loc_18000BBBB
0x18000bc8b  mov     rbx, [rbp+var_48]
0x18000bc8f  mov     rsi, [rbx]
0x18000bc92  mov     r14, [rbp+var_50]
0x18000bc96  mov     [rbp+string], r12
0x18000bc9a  lea     r9, [rbp+string]; string
0x18000bc9e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bca2  mov     edx, 8; length
0x18000bca7  lea     rcx, aLatitude; "Latitude"
0x18000bcae  call    cs:__imp_WindowsCreateStringReference
0x18000bcb4  test    eax, eax
0x18000bcb6  js      loc_18000C34E
0x18000bcbc  mov     r8, r14
0x18000bcbf  mov     rdx, [rbp+string]
0x18000bcc3  mov     rcx, rbx
0x18000bcc6  mov     rax, [rsi+38h]
0x18000bcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bccf  mov     ebx, eax
0x18000bcd1  test    eax, eax
0x18000bcd3  jns     short loc_18000BCFB
0x18000bcd5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bcdc  jz      loc_18000C2A4
0x18000bce2  lea     rax, aChrPjsonobject_13; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000bce9  mov     [rsp+80h+var_58], rax
0x18000bcee  mov     dword ptr [rsp+80h+var_60], 4A7h
0x18000bcf6  jmp     loc_18000BBBB
0x18000bcfb  mov     rbx, [rbp+var_40]
0x18000bcff  mov     rax, [rbx]
0x18000bd02  mov     rsi, [rax+48h]
0x18000bd06  mov     rcx, [rbp+var_50]
0x18000bd0a  test    rcx, rcx
0x18000bd0d  jz      short loc_18000BD20
0x18000bd0f  mov     [rbp+var_50], r12
0x18000bd13  mov     rdx, [rcx]
0x18000bd16  mov     rax, [rdx+10h]
0x18000bd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd1f  nop
0x18000bd20  lea     r8, [rbp+var_50]
0x18000bd24  movsd   xmm1, qword ptr [rdi+8]
0x18000bd29  mov     rcx, rbx
0x18000bd2c  mov     rax, rsi
0x18000bd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd34  mov     ebx, eax
0x18000bd36  test    eax, eax
0x18000bd38  jns     short loc_18000BD60
0x18000bd3a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bd41  jz      loc_18000C2A4
0x18000bd47  lea     rax, aChrPjsonvalues_1; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000bd4e  mov     [rsp+80h+var_58], rax
0x18000bd53  mov     dword ptr [rsp+80h+var_60], 4A8h
0x18000bd5b  jmp     loc_18000BBBB
0x18000bd60  mov     rbx, [rbp+var_48]
0x18000bd64  mov     rsi, [rbx]
0x18000bd67  mov     r14, [rbp+var_50]
0x18000bd6b  mov     [rbp+string], r12
0x18000bd6f  lea     r9, [rbp+string]; string
0x18000bd73  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bd77  mov     edx, 9; length
0x18000bd7c  lea     rcx, aLongitude; "Longitude"
0x18000bd83  call    cs:__imp_WindowsCreateStringReference
0x18000bd89  test    eax, eax
0x18000bd8b  js      loc_18000C356
0x18000bd91  mov     r8, r14
0x18000bd94  mov     rdx, [rbp+string]
0x18000bd98  mov     rcx, rbx
0x18000bd9b  mov     rax, [rsi+38h]
0x18000bd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda4  mov     ebx, eax
0x18000bda6  test    eax, eax
0x18000bda8  jns     short loc_18000BDD0
0x18000bdaa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bdb1  jz      loc_18000C2A4
0x18000bdb7  lea     rax, aChrPjsonobject_22; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000bdbe  mov     [rsp+80h+var_58], rax
0x18000bdc3  mov     dword ptr [rsp+80h+var_60], 4A9h
0x18000bdcb  jmp     loc_18000BBBB
0x18000bdd0  mov     rbx, [rbp+var_40]
0x18000bdd4  mov     rax, [rbx]
0x18000bdd7  mov     rsi, [rax+48h]
0x18000bddb  mov     rcx, [rbp+var_50]
0x18000bddf  test    rcx, rcx
0x18000bde2  jz      short loc_18000BDF5
0x18000bde4  mov     [rbp+var_50], r12
0x18000bde8  mov     rdx, [rcx]
0x18000bdeb  mov     rax, [rdx+10h]
0x18000bdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf4  nop
0x18000bdf5  mov     edx, [rdi+18h]
0x18000bdf8  xorps   xmm1, xmm1
0x18000bdfb  cvtsi2sd xmm1, rdx
0x18000be00  lea     r8, [rbp+var_50]
0x18000be04  mov     rcx, rbx
0x18000be07  mov     rax, rsi
0x18000be0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be0f  mov     ebx, eax
0x18000be11  test    eax, eax
0x18000be13  jns     short loc_18000BE3B
0x18000be15  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000be1c  jz      loc_18000C2A4
0x18000be22  lea     rax, aChrPjsonvalues_6; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000be29  mov     [rsp+80h+var_58], rax
0x18000be2e  mov     dword ptr [rsp+80h+var_60], 4AAh
0x18000be36  jmp     loc_18000BBBB
0x18000be3b  mov     rbx, [rbp+var_48]
0x18000be3f  mov     rsi, [rbx]
0x18000be42  mov     r14, [rbp+var_50]
0x18000be46  mov     [rbp+string], r12
0x18000be4a  lea     r9, [rbp+string]; string
0x18000be4e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000be52  mov     edx, 0Bh; length
0x18000be57  lea     rcx, aErrorradius; "ErrorRadius"
0x18000be5e  call    cs:__imp_WindowsCreateStringReference
0x18000be64  test    eax, eax
0x18000be66  js      loc_18000C35E
0x18000be6c  mov     r8, r14
0x18000be6f  mov     rdx, [rbp+string]
0x18000be73  mov     rcx, rbx
0x18000be76  mov     rax, [rsi+38h]
0x18000be7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7f  mov     ebx, eax
0x18000be81  test    eax, eax
0x18000be83  jns     short loc_18000BEAB
0x18000be85  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000be8c  jz      loc_18000C2A4
0x18000be92  lea     rax, aChrPjsonobject_4; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000be99  mov     [rsp+80h+var_58], rax
0x18000be9e  mov     dword ptr [rsp+80h+var_60], 4ABh
0x18000bea6  jmp     loc_18000BBBB
0x18000beab  mov     rbx, [rbp+var_40]
0x18000beaf  mov     rax, [rbx]
0x18000beb2  mov     rsi, [rax+48h]
0x18000beb6  mov     rcx, [rbp+var_50]
0x18000beba  test    rcx, rcx
0x18000bebd  jz      short loc_18000BED0
0x18000bebf  mov     [rbp+var_50], r12
0x18000bec3  mov     rdx, [rcx]
0x18000bec6  mov     rax, [rdx+10h]
0x18000beca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000becf  nop
0x18000bed0  lea     r8, [rbp+var_50]
0x18000bed4  movsd   xmm1, qword ptr [rdi+10h]
0x18000bed9  mov     rcx, rbx
0x18000bedc  mov     rax, rsi
0x18000bedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee4  mov     ebx, eax
0x18000bee6  test    eax, eax
0x18000bee8  jns     short loc_18000BF10
0x18000beea  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bef1  jz      loc_18000C2A4
0x18000bef7  lea     rax, aChrPjsonvalues_13; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000befe  mov     [rsp+80h+var_58], rax
0x18000bf03  mov     dword ptr [rsp+80h+var_60], 4ACh
0x18000bf0b  jmp     loc_18000BBBB
0x18000bf10  mov     rbx, [rbp+var_48]
0x18000bf14  mov     rsi, [rbx]
0x18000bf17  mov     r14, [rbp+var_50]
0x18000bf1b  mov     [rbp+string], r12
0x18000bf1f  lea     r9, [rbp+string]; string
0x18000bf23  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000bf27  mov     edx, 8; length
0x18000bf2c  lea     rcx, aAltitude; "Altitude"
0x18000bf33  call    cs:__imp_WindowsCreateStringReference
0x18000bf39  test    eax, eax
0x18000bf3b  js      loc_18000C366
0x18000bf41  mov     r8, r14
0x18000bf44  mov     rdx, [rbp+string]
0x18000bf48  mov     rcx, rbx
0x18000bf4b  mov     rax, [rsi+38h]
0x18000bf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf54  mov     ebx, eax
0x18000bf56  test    eax, eax
0x18000bf58  jns     short loc_18000BF80
0x18000bf5a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000bf61  jz      loc_18000C2A4
0x18000bf67  lea     rax, aChrPjsonobject_21; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000bf6e  mov     [rsp+80h+var_58], rax
0x18000bf73  mov     dword ptr [rsp+80h+var_60], 4ADh
0x18000bf7b  jmp     loc_18000BBBB
0x18000bf80  cmp     [rdi+1Ch], r12d
0x18000bf84  jz      loc_18000C069
0x18000bf8a  mov     rbx, [rbp+var_40]
0x18000bf8e  mov     rax, [rbx]
0x18000bf91  mov     rsi, [rax+48h]
  ... truncated ...
```
