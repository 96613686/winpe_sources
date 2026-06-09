# DdcMobileNetworksHelper::CreateMobileNetworkPropertiesForCanJsonValue(WNF_CELL_CAN_CONFIGURATION_TYPE *,WNF_CELL_DEVICE_INFO_TYPE *,WNF_CELL_PHONE_NUMBER_TYPE *,WNF_CELL_HOME_OPERATOR_INFO_TYPE *,RILSYSTEMTYPE *,ushort const *,Windows::Data::Json::IJsonValue * *)

- ea: `0x180022240`
- end: `0x180023178`
- name: `?CreateMobileNetworkPropertiesForCanJsonValue@DdcMobileNetworksHelper@@CAJPEAUWNF_CELL_CAN_CONFIGURATION_TYPE@@PEAUWNF_CELL_DEVICE_INFO_TYPE@@PEAUWNF_CELL_PHONE_NUMBER_TYPE@@PEAUWNF_CELL_HOME_OPERATOR_INFO_TYPE@@PEAW4RILSYSTEMTYPE@@PEBGPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `3896`
- prototype: `__int64 __fastcall(struct WNF_CELL_CAN_CONFIGURATION_TYPE *, const WCHAR *, const WCHAR *, struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *, enum RILSYSTEMTYPE *, const unsigned __int16 *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023c64`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013a58`
- `0x180013b38`
- `0x18002099c`
- `0x180022240`
- `0x180023180`
- `0x180024328`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800223f6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800223f6`

## string_xrefs

- `0x1800223d6`: `Windows.Data.Json.JsonValue`
- `0x18002276c`: `Windows.Data.Json.JsonValue`
- `0x18002282f`: `Windows.Data.Json.JsonValue`
- `0x1800229c7`: `Windows.Data.Json.JsonValue`
- `0x180022db9`: `Windows.Data.Json.JsonValue`
- `0x180022e7c`: `Windows.Data.Json.JsonValue`
- `0x18002300d`: `Windows.Data.Json.JsonValue`
- `0x180022377`: `Windows.Data.Json.JsonObject`
- `0x18002240f`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18002279e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022861`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800229f9`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022deb`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022eae`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002303f`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800223a9`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x1800230d2`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x180022320`: `CPR(ppJsonValue)`
- `0x1800222f4`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmobilenetworkshelper.cpp`
- `0x180022351`: `CBR(*ppJsonValue == 0)`
- `0x1800222e0`: `CPR(pCanConfiguration)`
- `0x18002246a`: `CHR(pJsonValueStatics->CreateNumberValue(pCanConfiguration->dwSlotAffinity, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800224ca`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_SIM_SLOT_NUMBER).Get(), pJsonValue.Get()))`
- `0x18002253b`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszIccid).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002259b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_ICCID).Get(), pJsonValue.Get()))`
- `0x18002260b`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pDeviceInfo->wszSerialNumber3gpp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002266b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_IMEI).Get(), pJsonValue.Get()))`
- `0x1800227fe`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_IMEI).Get(), pJsonValue.Get()))`
- `0x1800226d2`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pDeviceInfo->wszSerialNumber3gpp2).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022736`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_MEID).Get(), pJsonValue.Get()))`
- `0x1800228c1`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_MEID).Get(), pJsonValue.Get()))`
- `0x180022937`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pPhoneNumber->wszNumber).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002299b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_PHONE_NUMBER).Get(), pJsonValue.Get()))`
- `0x180022a59`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_PHONE_NUMBER).Get(), pJsonValue.Get()))`
- `0x180022ae2`: `CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[0], 1, pJsonObject.Get()))`
- `0x180022b53`: `CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[0], 1, pJsonObject.Get()))`
- `0x180022b22`: `CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[1], 2, pJsonObject.Get()))`
- `0x180022b91`: `CHR(FormatNetworkCode(0, 2, pJsonObject.Get()))`
- `0x180022c0b`: `CHR(FormatNetworkCode(0, 2, pJsonObject.Get()))`
- `0x180022bce`: `CHR(FormatNetworkCode(0, 1, pJsonObject.Get()))`
- `0x180022c71`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)(*pRilSystemType & RIL_SYSTEMTYPE_CDMA), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022cd1`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_CDMA_EXISTS).Get(), pJsonValue.Get()))`
- `0x180022e4b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_CDMA_EXISTS).Get(), pJsonValue.Get()))`
- `0x180022d29`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)(*pRilSystemType & RIL_SYSTEMTYPE_3GPP), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022d8d`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_GSM_EXISTS).Get(), pJsonValue.Get()))`
- `0x180022f0e`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_GSM_EXISTS).Get(), pJsonValue.Get()))`
- `0x180022f7d`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBillingOperatorId).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180022fe1`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_BILLING_OPERATOR_ID).Get(), pJsonValue.Get()))`
- `0x18002309b`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_BILLING_OPERATOR_ID).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcMobileNetworksHelper::CreateMobileNetworkPropertiesForCanJsonValue(
        struct WNF_CELL_CAN_CONFIGURATION_TYPE *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        struct WNF_CELL_HOME_OPERATOR_INFO_TYPE *a4,
        enum RILSYSTEMTYPE *a5,
        const unsigned __int16 *a6,
        struct Windows::Data::Json::IJsonValue **a7)
{
  int v11; // ecx
  int v12; // r8d
  int ActivationFactory; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  char v16; // r8
  struct Windows::Data::Json::IJsonObject *v17; // rsi
  __int64 (__fastcall *v18)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v19; // rbx
  HSTRING_HEADER *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  __int64 v23; // rax
  char v24; // r8
  struct Windows::Data::Json::IJsonObject *v25; // rsi
  __int64 (__fastcall *v26)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v27; // rbx
  HSTRING_HEADER *v28; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  __int64 v31; // rax
  char v32; // r8
  struct Windows::Data::Json::IJsonObject *v33; // rsi
  __int64 (__fastcall *v34)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v35; // rbx
  HSTRING_HEADER *v36; // rax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, __int64 *); // rbx
  __int64 v39; // rax
  char v40; // r8
  struct Windows::Data::Json::IJsonObject *v41; // rsi
  __int64 (__fastcall *v42)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v43; // rbx
  HSTRING_HEADER *v44; // rax
  char v45; // r8
  struct Windows::Data::Json::IJsonObject *v46; // rsi
  __int64 (__fastcall *v47)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v48; // rbx
  HSTRING_HEADER *v49; // rax
  char v50; // r8
  struct Windows::Data::Json::IJsonObject *v51; // rsi
  __int64 (__fastcall *v52)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v53; // rbx
  HSTRING_HEADER *v54; // rax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, _QWORD, __int64 *); // rbx
  __int64 v57; // rax
  char v58; // r8
  struct Windows::Data::Json::IJsonObject *v59; // rsi
  __int64 (__fastcall *v60)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v61; // rbx
  HSTRING_HEADER *v62; // rax
  char v63; // r8
  struct Windows::Data::Json::IJsonObject *v64; // rsi
  __int64 (__fastcall *v65)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v66; // rbx
  HSTRING_HEADER *v67; // rax
  struct RILNETWORKCODE *v68; // rcx
  enum RILSYSTEMTYPE *v69; // r14
  __int64 v70; // rdi
  __int64 (__fastcall *v71)(__int64, __int64, __int64 *); // rbx
  __int64 v72; // rdx
  char v73; // r8
  struct Windows::Data::Json::IJsonObject *v74; // rsi
  __int64 (__fastcall *v75)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v76; // rbx
  HSTRING_HEADER *v77; // rax
  __int64 v78; // rdi
  __int64 (__fastcall *v79)(__int64, __int64, __int64 *); // rbx
  __int64 v80; // rdx
  char v81; // r8
  struct Windows::Data::Json::IJsonObject *v82; // rsi
  __int64 (__fastcall *v83)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v84; // rbx
  HSTRING_HEADER *v85; // rax
  char v86; // r8
  struct Windows::Data::Json::IJsonObject *v87; // rsi
  __int64 (__fastcall *v88)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v89; // rbx
  HSTRING_HEADER *v90; // rax
  char v91; // r8
  struct Windows::Data::Json::IJsonObject *v92; // rsi
  __int64 (__fastcall *v93)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v94; // rbx
  HSTRING_HEADER *v95; // rax
  __int64 v96; // rdi
  __int64 (__fastcall *v97)(__int64, PVOID, __int64 *); // rbx
  char v98; // r8
  HSTRING_HEADER *v99; // rax
  char v100; // r8
  struct Windows::Data::Json::IJsonObject *v101; // rsi
  __int64 (__fastcall *v102)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v103; // rbx
  HSTRING_HEADER *v104; // rax
  char v105; // r8
  struct Windows::Data::Json::IJsonObject *v106; // rsi
  __int64 (__fastcall *v107)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v108; // rbx
  HSTRING_HEADER *v109; // rax
  struct Windows::Data::Json::IJsonValue *v110; // rax
  __int64 v111; // rcx
  struct Windows::Data::Json::IJsonObject *v112; // rcx
  char v114; // [rsp+20h] [rbp-B1h]
  const char *v115; // [rsp+28h] [rbp-A9h]
  __int64 v116; // [rsp+30h] [rbp-A1h] BYREF
  struct Windows::Data::Json::IJsonObject *v117; // [rsp+38h] [rbp-99h] BYREF
  __int64 v118; // [rsp+40h] [rbp-91h] BYREF
  struct Windows::Data::Json::IJsonValue *v119; // [rsp+48h] [rbp-89h] BYREF
  enum RILSYSTEMTYPE *v120; // [rsp+50h] [rbp-81h]
  const unsigned __int16 *v121; // [rsp+58h] [rbp-79h]
  const WCHAR *v122; // [rsp+60h] [rbp-71h] BYREF
  struct Windows::Data::Json::IJsonValue **v123; // [rsp+68h] [rbp-69h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-61h] BYREF
  __int64 v125; // [rsp+88h] [rbp-49h]
  WCHAR sourceString[24]; // [rsp+90h] [rbp-41h] BYREF

  v120 = a5;
  v121 = a6;
  v122 = a6;
  v123 = a7;
  v117 = 0;
  v119 = 0;
  v116 = 0;
  v118 = 0;
  v11 = 0;
  memset(sourceString, 0, 42);
  if ( !a1 )
  {
    v12 = -2147024809;
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_134;
    v115 = "CPR(pCanConfiguration)";
    v114 = -71;
    goto LABEL_4;
  }
  if ( !a7 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        186,
        (__int64)"CPR(ppJsonValue)");
    goto LABEL_134;
  }
  if ( !*a7 )
  {
    v125 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v125, &v117);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v114 = -67;
      goto LABEL_14;
    }
    v125 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v125, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v118);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatic"
             "s.GetAddressOf()))";
      v114 = -66;
      goto LABEL_14;
    }
    v14 = v118;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
    ActivationFactory = v15(v14, *((unsigned int *)a1 + 1), &v116);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(pJsonValueStatics->CreateNumberValue(pCanConfiguration->dwSlotAffinity, pJsonValue.ReleaseAndGetAddressOf()))";
      v114 = -63;
      goto LABEL_14;
    }
    v17 = v117;
    v18 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
    v19 = v116;
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_18002B7C0,
            v16);
    ActivationFactory = v18(v17, v20[1].Reserved.Reserved1, v19);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_SIM_SLOT_NUMBER).Get(), pJsonValue.Get()))";
      v114 = -62;
      goto LABEL_14;
    }
    IccidBCDToString((const unsigned __int8 (*)[10])((char *)a1 + 12), (unsigned __int16 (*)[21])sourceString);
    v21 = v118;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
    ActivationFactory = v22(v21, *(_QWORD *)(v23 + 24), &v116);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszIccid).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
      v114 = -58;
      goto LABEL_14;
    }
    v25 = v117;
    v26 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
    v27 = v116;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_18002B748,
            v24);
    ActivationFactory = v26(v25, v28[1].Reserved.Reserved1, v27);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_134;
      v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_ICCID).Get(), pJsonValue.Get()))";
      v114 = -57;
      goto LABEL_14;
    }
    if ( a2 )
    {
      v29 = v118;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, a2 + 80);
      ActivationFactory = v30(v29, *(_QWORD *)(v31 + 24), &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pDeviceInfo->wszSerialNumber3gpp).Get(), pJsonV"
               "alue.ReleaseAndGetAddressOf()))";
        v114 = -52;
        goto LABEL_14;
      }
      v33 = v117;
      v34 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v35 = v116;
      v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7B8,
              v32);
      ActivationFactory = v34(v33, v36[1].Reserved.Reserved1, v35);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_IMEI).Get(), pJsonValue.Get()))";
        v114 = -51;
        goto LABEL_14;
      }
      v37 = v118;
      v38 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, a2 + 100);
      ActivationFactory = v38(v37, *(_QWORD *)(v39 + 24), &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pDeviceInfo->wszSerialNumber3gpp2).Get(), pJson"
               "Value.ReleaseAndGetAddressOf()))";
        v114 = -50;
        goto LABEL_14;
      }
      v41 = v117;
      v42 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v43 = v116;
      v44 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7B0,
              v40);
      ActivationFactory = v42(v41, v44[1].Reserved.Reserved1, v43);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_MEID).Get(), pJsonValue.Get()))";
        v114 = -49;
        goto LABEL_14;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = -45;
        goto LABEL_14;
      }
      v46 = v117;
      v47 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v48 = v116;
      v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7B8,
              v45);
      ActivationFactory = v47(v46, v49[1].Reserved.Reserved1, v48);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_IMEI).Get(), pJsonValue.Get()))";
        v114 = -44;
        goto LABEL_14;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = -43;
        goto LABEL_14;
      }
      v51 = v117;
      v52 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v53 = v116;
      v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7B0,
              v50);
      ActivationFactory = v52(v51, v54[1].Reserved.Reserved1, v53);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_MEID).Get(), pJsonValue.Get()))";
        v114 = -42;
        goto LABEL_14;
      }
    }
    if ( a3 )
    {
      v55 = v118;
      v56 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, a3);
      ActivationFactory = v56(v55, *(_QWORD *)(v57 + 24), &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pPhoneNumber->wszNumber).Get(), pJsonValue.Rele"
               "aseAndGetAddressOf()))";
        v114 = -36;
        goto LABEL_14;
      }
      v59 = v117;
      v60 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v61 = v116;
      v62 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7A8,
              v58);
      ActivationFactory = v60(v59, v62[1].Reserved.Reserved1, v61);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_PHONE_NUMBER).Get(), pJsonValue.Get()))";
        v114 = -35;
        goto LABEL_14;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = -31;
        goto LABEL_14;
      }
      v64 = v117;
      v65 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v66 = v116;
      v67 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B7A8,
              v63);
      ActivationFactory = v65(v64, v67[1].Reserved.Reserved1, v66);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_PHONE_NUMBER).Get(), pJsonValue.Get()))";
        v114 = -30;
        goto LABEL_14;
      }
    }
    if ( a4 && *(_DWORD *)a4 )
    {
      if ( *(_DWORD *)a4 > 2u )
      {
        ActivationFactory = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CBR(pHomeOperatorInfo->cHomeOperator <= 2)";
        v114 = -24;
        goto LABEL_14;
      }
      v68 = (struct RILNETWORKCODE *)((char *)a4 + 4);
      if ( *(_DWORD *)a4 == 2 )
      {
        ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(v68, 1u, v117);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_134;
          v115 = "CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[0], 1, pJsonObject.Get()))";
          v114 = -21;
          goto LABEL_14;
        }
        ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(
                              (struct RILNETWORKCODE *)((char *)a4 + 36),
                              2u,
                              v117);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_134;
          v115 = "CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[1], 2, pJsonObject.Get()))";
          v114 = -20;
          goto LABEL_14;
        }
      }
      else
      {
        ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(v68, 1u, v117);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_134;
          v115 = "CHR(FormatNetworkCode(&pHomeOperatorInfo->stHomeOperator[0], 1, pJsonObject.Get()))";
          v114 = -16;
          goto LABEL_14;
        }
        ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(0, 2u, v117);
        if ( ActivationFactory < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_134;
          v115 = "CHR(FormatNetworkCode(0, 2, pJsonObject.Get()))";
          v114 = -15;
          goto LABEL_14;
        }
      }
    }
    else
    {
      ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(0, 1u, v117);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(FormatNetworkCode(0, 1, pJsonObject.Get()))";
        v114 = -10;
        goto LABEL_14;
      }
      ActivationFactory = DdcMobileNetworksHelper::FormatNetworkCode(0, 2u, v117);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(FormatNetworkCode(0, 2, pJsonObject.Get()))";
        v114 = -9;
        goto LABEL_14;
      }
    }
    v69 = v120;
    if ( v120 )
    {
      v70 = v118;
      v71 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v118 + 64LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      LOBYTE(v72) = *(_BYTE *)v69 & 3;
      ActivationFactory = v71(v70, v72, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateBooleanValue((boolean)(*pRilSystemType & RIL_SYSTEMTYPE_CDMA), pJsonValue.Re"
               "leaseAndGetAddressOf()))";
        v114 = -3;
        goto LABEL_14;
      }
      v74 = v117;
      v75 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v76 = v116;
      v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B758,
              v73);
      ActivationFactory = v75(v74, v77[1].Reserved.Reserved1, v76);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_CDMA_EXISTS).Get(), pJsonValue.Get()))";
        v114 = -2;
        goto LABEL_14;
      }
      v78 = v118;
      v79 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v118 + 64LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      LOBYTE(v80) = *(_BYTE *)v69 & 0x3C;
      ActivationFactory = v79(v78, v80, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateBooleanValue((boolean)(*pRilSystemType & RIL_SYSTEMTYPE_3GPP), pJsonValue.Re"
               "leaseAndGetAddressOf()))";
        v114 = -1;
        goto LABEL_14;
      }
      v82 = v117;
      v83 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v84 = v116;
      v85 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B750,
              v81);
      ActivationFactory = v83(v82, v85[1].Reserved.Reserved1, v84);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_GSM_EXISTS).Get(), pJsonValue.Get()))";
        v114 = 0;
        goto LABEL_14;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = 4;
        goto LABEL_14;
      }
      v87 = v117;
      v88 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v89 = v116;
      v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B758,
              v86);
      ActivationFactory = v88(v87, v90[1].Reserved.Reserved1, v89);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_CDMA_EXISTS).Get(), pJsonValue.Get()))";
        v114 = 5;
        goto LABEL_14;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = 6;
        goto LABEL_14;
      }
      v92 = v117;
      v93 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v94 = v116;
      v95 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B750,
              v91);
      ActivationFactory = v93(v92, v95[1].Reserved.Reserved1, v94);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_GSM_EXISTS).Get(), pJsonValue.Get()))";
        v114 = 7;
        goto LABEL_14;
      }
    }
    if ( v121 )
    {
      v96 = v118;
      v97 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v118 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v99 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v122, v98);
      ActivationFactory = v97(v96, v99[1].Reserved.Reserved1, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBillingOperatorId).Get(), pJsonValue.Releas"
               "eAndGetAddressOf()))";
        v114 = 13;
        goto LABEL_14;
      }
      v101 = v117;
      v102 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v103 = v116;
      v104 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
               &hstringHeader,
               (const WCHAR **)off_18002B7A0,
               v100);
      ActivationFactory = v102(v101, v104[1].Reserved.Reserved1, v103);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_BILLING_OPERATOR_ID).Get(), pJsonValue.Get()))";
        v114 = 14;
        goto LABEL_14;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      v125 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(v125, &v116);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Release"
               "AndGetAddressOf()))";
        v114 = 18;
        goto LABEL_14;
      }
      v106 = v117;
      v107 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)v117 + 56LL);
      v108 = v116;
      v109 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
               &hstringHeader,
               (const WCHAR **)off_18002B7A0,
               v105);
      ActivationFactory = v107(v106, v109[1].Reserved.Reserved1, v108);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_134;
        v115 = "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_BILLING_OPERATOR_ID).Get(), pJsonValue.Get()))";
        v114 = 19;
        goto LABEL_14;
      }
    }
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v117,
                          (__int64)&v119);
    if ( ActivationFactory >= 0 )
    {
      v110 = v119;
      v119 = 0;
      *v123 = v110;
      goto LABEL_134;
    }
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_134;
    v115 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
    v114 = 22;
LABEL_14:
    v12 = ActivationFactory;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v11,
      (_DWORD)a2,
      v12,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
      v114,
      (__int64)v115);
    goto LABEL_134;
  }
  ActivationFactory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      0,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
      187,
      (__int64)"CBR(*ppJsonValue == 0)");
LABEL_134:
  v111 = v118;
  if ( v118 )
  {
    v118 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v119);
  v112 = v117;
  if ( v117 )
  {
    v117 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v112 + 16LL))(v112);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180022240  push    rbp
0x180022242  push    rbx
0x180022243  push    rsi
0x180022244  push    rdi
0x180022245  push    r12
0x180022247  push    r13
0x180022249  push    r14
0x18002224b  push    r15
0x18002224d  lea     rbp, [rsp-7]
0x180022252  sub     rsp, 0D8h
0x180022259  mov     rax, cs:__security_cookie
0x180022260  xor     rax, rsp
0x180022263  mov     [rbp+3Fh+var_50], rax
0x180022267  mov     r14, r9
0x18002226a  mov     r12, r8
0x18002226d  mov     r13, rdx
0x180022270  mov     r15, rcx
0x180022273  mov     rax, [rbp+3Fh+arg_20]
0x180022277  mov     [rsp+110h+var_C0], rax
0x18002227c  mov     rax, [rbp+3Fh+arg_28]
0x180022280  mov     [rbp+3Fh+var_B8], rax
0x180022284  mov     [rbp+3Fh+var_B0], rax
0x180022288  mov     rax, [rbp+3Fh+arg_30]
0x18002228c  mov     [rbp+3Fh+var_A8], rax
0x180022290  mov     [rsp+110h+var_D8], 0
0x180022299  mov     [rsp+110h+var_C8], 0
0x1800222a2  mov     [rsp+110h+var_E0], 0
0x1800222ab  mov     [rsp+110h+var_D0], 0
0x1800222b4  xorps   xmm0, xmm0
0x1800222b7  xor     ecx, ecx
0x1800222b9  movups  xmmword ptr [rbp+3Fh+sourceString], xmm0
0x1800222bd  movups  [rbp+3Fh+var_70], xmm0
0x1800222c1  movups  [rbp+3Fh+var_70+0Ah], xmm0
0x1800222c5  test    r15, r15
0x1800222c8  jnz     short loc_180022305
0x1800222ca  mov     r8d, 80070057h
0x1800222d0  mov     ebx, r8d
0x1800222d3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800222da  jz      loc_180023100
0x1800222e0  lea     rax, aCprPcanconfigu; "CPR(pCanConfiguration)"
0x1800222e7  mov     [rsp+110h+var_E8], rax
0x1800222ec  mov     dword ptr [rsp+110h+var_F0], 0B9h
0x1800222f4  lea     r9, aOnecoreuapShel_14; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800222fb  call    McTemplateU0dsqs_EventWriteTransfer
0x180022300  jmp     loc_180023100
0x180022305  test    rax, rax
0x180022308  jnz     short loc_180022336
0x18002230a  mov     r8d, 80070057h
0x180022310  mov     ebx, r8d
0x180022313  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002231a  jz      loc_180023100
0x180022320  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x180022327  mov     [rsp+110h+var_E8], rax
0x18002232c  mov     dword ptr [rsp+110h+var_F0], 0BAh
0x180022334  jmp     short loc_1800222F4
0x180022336  cmp     [rax], rcx
0x180022339  jz      short loc_180022367
0x18002233b  mov     r8d, 80070057h
0x180022341  mov     ebx, r8d
0x180022344  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002234b  jz      loc_180023100
0x180022351  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == 0)"
0x180022358  mov     [rsp+110h+var_E8], rax
0x18002235d  mov     dword ptr [rsp+110h+var_F0], 0BBh
0x180022365  jmp     short loc_1800222F4
0x180022367  mov     [rbp+3Fh+var_88], rcx
0x18002236b  mov     edi, 1Ch
0x180022370  mov     r9d, edi; unsigned int
0x180022373  lea     r8d, [rdi+1]; unsigned int
0x180022377  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18002237e  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x180022382  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180022387  nop
0x180022388  lea     rdx, [rsp+110h+var_D8]
0x18002238d  mov     rcx, [rbp+3Fh+var_88]
0x180022391  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180022396  mov     ebx, eax
0x180022398  test    eax, eax
0x18002239a  jns     short loc_1800223C5
0x18002239c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800223a3  jz      loc_180023100
0x1800223a9  lea     rax, aChrActivateins_5; "CHR(ActivateInstance(HStringReference(R"...
0x1800223b0  mov     [rsp+110h+var_E8], rax
0x1800223b5  mov     dword ptr [rsp+110h+var_F0], 0BDh
0x1800223bd  mov     r8d, ebx
0x1800223c0  jmp     loc_1800222F4
0x1800223c5  mov     [rbp+3Fh+var_88], 0
0x1800223cd  mov     r9d, 1Bh; unsigned int
0x1800223d3  mov     r8d, edi; unsigned int
0x1800223d6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800223dd  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800223e1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800223e6  lea     r8, [rsp+110h+var_D0]
0x1800223eb  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800223f2  mov     rcx, [rbp+3Fh+var_88]
0x1800223f6  call    cs:__imp_RoGetActivationFactory
0x1800223fc  mov     ebx, eax
0x1800223fe  test    eax, eax
0x180022400  jns     short loc_180022425
0x180022402  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022409  jz      loc_180023100
0x18002240f  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180022416  mov     [rsp+110h+var_E8], rax
0x18002241b  mov     dword ptr [rsp+110h+var_F0], 0BEh
0x180022423  jmp     short loc_1800223BD
0x180022425  mov     rdi, [rsp+110h+var_D0]
0x18002242a  mov     rax, [rdi]
0x18002242d  mov     rbx, [rax+48h]
0x180022431  lea     rcx, [rsp+110h+var_E0]
0x180022436  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002243b  mov     edx, [r15+4]
0x18002243f  xorps   xmm1, xmm1
0x180022442  cvtsi2sd xmm1, rdx
0x180022447  lea     r8, [rsp+110h+var_E0]
0x18002244c  mov     rcx, rdi
0x18002244f  mov     rax, rbx
0x180022452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022457  mov     ebx, eax
0x180022459  test    eax, eax
0x18002245b  jns     short loc_180022483
0x18002245d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022464  jz      loc_180023100
0x18002246a  lea     rax, aChrPjsonvalues_64; "CHR(pJsonValueStatics->CreateNumberValu"...
0x180022471  mov     [rsp+110h+var_E8], rax
0x180022476  mov     dword ptr [rsp+110h+var_F0], 0C1h
0x18002247e  jmp     loc_1800223BD
0x180022483  mov     rsi, [rsp+110h+var_D8]
0x180022488  mov     rax, [rsi]
0x18002248b  mov     rdi, [rax+38h]
0x18002248f  mov     rbx, [rsp+110h+var_E0]
0x180022494  lea     rdx, off_18002B7C0; "SimSlotNumber"
0x18002249b  lea     rcx, [rbp+3Fh+hstringHeader]
0x18002249f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800224a4  nop
0x1800224a5  mov     r8, rbx
0x1800224a8  mov     rdx, [rax+18h]
0x1800224ac  mov     rcx, rsi
0x1800224af  mov     rax, rdi
0x1800224b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224b7  mov     ebx, eax
0x1800224b9  test    eax, eax
0x1800224bb  jns     short loc_1800224E3
0x1800224bd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800224c4  jz      loc_180023100
0x1800224ca  lea     rax, aChrPjsonobject_24; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800224d1  mov     [rsp+110h+var_E8], rax
0x1800224d6  mov     dword ptr [rsp+110h+var_F0], 0C2h
0x1800224de  jmp     loc_1800223BD
0x1800224e3  lea     rcx, [r15+0Ch]; unsigned __int8 (*)[10]
0x1800224e7  lea     rdx, [rbp+3Fh+sourceString]; unsigned __int16 (*)[21]
0x1800224eb  call    ?IccidBCDToString@@YAXAEAY09$$CBEAEAY0BF@G@Z; IccidBCDToString(uchar const (&)[10],ushort (&)[21])
0x1800224f0  mov     rdi, [rsp+110h+var_D0]
0x1800224f5  mov     rax, [rdi]
0x1800224f8  mov     rbx, [rax+50h]
0x1800224fc  lea     rcx, [rsp+110h+var_E0]
0x180022501  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022506  lea     rdx, [rbp+3Fh+sourceString]; sourceString
0x18002250a  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x18002250e  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x180022513  nop
0x180022514  lea     r8, [rsp+110h+var_E0]
0x180022519  mov     rdx, [rax+18h]
0x18002251d  mov     rcx, rdi
0x180022520  mov     rax, rbx
0x180022523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022528  mov     ebx, eax
0x18002252a  test    eax, eax
0x18002252c  jns     short loc_180022554
0x18002252e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022535  jz      loc_180023100
0x18002253b  lea     rax, aChrPjsonvalues_0; "CHR(pJsonValueStatics->CreateStringValu"...
0x180022542  mov     [rsp+110h+var_E8], rax
0x180022547  mov     dword ptr [rsp+110h+var_F0], 0C6h
0x18002254f  jmp     loc_1800223BD
0x180022554  mov     rsi, [rsp+110h+var_D8]
0x180022559  mov     rax, [rsi]
0x18002255c  mov     rdi, [rax+38h]
0x180022560  mov     rbx, [rsp+110h+var_E0]
0x180022565  lea     rdx, off_18002B748; "Iccid"
0x18002256c  lea     rcx, [rbp+3Fh+hstringHeader]
0x180022570  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180022575  nop
0x180022576  mov     r8, rbx
0x180022579  mov     rdx, [rax+18h]
0x18002257d  mov     rcx, rsi
0x180022580  mov     rax, rdi
0x180022583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022588  mov     ebx, eax
0x18002258a  test    eax, eax
0x18002258c  jns     short loc_1800225B4
0x18002258e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022595  jz      loc_180023100
0x18002259b  lea     rax, aChrPjsonobject_0; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800225a2  mov     [rsp+110h+var_E8], rax
0x1800225a7  mov     dword ptr [rsp+110h+var_F0], 0C7h
0x1800225af  jmp     loc_1800223BD
0x1800225b4  lea     rcx, [rsp+110h+var_E0]
0x1800225b9  test    r13, r13
0x1800225bc  jz      loc_18002274F
0x1800225c2  mov     rdi, [rsp+110h+var_D0]
0x1800225c7  mov     rax, [rdi]
0x1800225ca  mov     rbx, [rax+50h]
0x1800225ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800225d3  lea     rdx, [r13+0A0h]; sourceString
0x1800225da  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800225de  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x1800225e3  nop
0x1800225e4  lea     r8, [rsp+110h+var_E0]
0x1800225e9  mov     rdx, [rax+18h]
0x1800225ed  mov     rcx, rdi
0x1800225f0  mov     rax, rbx
0x1800225f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f8  mov     ebx, eax
0x1800225fa  test    eax, eax
0x1800225fc  jns     short loc_180022624
0x1800225fe  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022605  jz      loc_180023100
0x18002260b  lea     rax, aChrPjsonvalues_70; "CHR(pJsonValueStatics->CreateStringValu"...
0x180022612  mov     [rsp+110h+var_E8], rax
0x180022617  mov     dword ptr [rsp+110h+var_F0], 0CCh
0x18002261f  jmp     loc_1800223BD
0x180022624  mov     rsi, [rsp+110h+var_D8]
0x180022629  mov     rax, [rsi]
0x18002262c  mov     rdi, [rax+38h]
0x180022630  mov     rbx, [rsp+110h+var_E0]
0x180022635  lea     rdx, off_18002B7B8; "Imei"
0x18002263c  lea     rcx, [rbp+3Fh+hstringHeader]
0x180022640  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180022645  nop
0x180022646  mov     r8, rbx
0x180022649  mov     rdx, [rax+18h]
0x18002264d  mov     rcx, rsi
0x180022650  mov     rax, rdi
0x180022653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022658  mov     ebx, eax
0x18002265a  test    eax, eax
0x18002265c  jns     short loc_180022684
0x18002265e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022665  jz      loc_180023100
0x18002266b  lea     rax, aChrPjsonobject_17; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180022672  mov     [rsp+110h+var_E8], rax
0x180022677  mov     dword ptr [rsp+110h+var_F0], 0CDh
0x18002267f  jmp     loc_1800223BD
0x180022684  mov     rdi, [rsp+110h+var_D0]
0x180022689  mov     rax, [rdi]
0x18002268c  mov     rbx, [rax+50h]
0x180022690  lea     rcx, [rsp+110h+var_E0]
0x180022695  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002269a  lea     rdx, [r13+0C8h]; sourceString
0x1800226a1  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800226a5  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x1800226aa  nop
0x1800226ab  lea     r8, [rsp+110h+var_E0]
0x1800226b0  mov     rdx, [rax+18h]
0x1800226b4  mov     rcx, rdi
0x1800226b7  mov     rax, rbx
0x1800226ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226bf  mov     ebx, eax
0x1800226c1  test    eax, eax
0x1800226c3  jns     short loc_1800226EB
0x1800226c5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800226cc  jz      loc_180023100
0x1800226d2  lea     rax, aChrPjsonvalues_1; "CHR(pJsonValueStatics->CreateStringValu"...
0x1800226d9  mov     [rsp+110h+var_E8], rax
0x1800226de  mov     dword ptr [rsp+110h+var_F0], 0CEh
0x1800226e6  jmp     loc_1800223BD
0x1800226eb  mov     rsi, [rsp+110h+var_D8]
0x1800226f0  mov     rax, [rsi]
0x1800226f3  mov     rdi, [rax+38h]
0x1800226f7  mov     rbx, [rsp+110h+var_E0]
0x1800226fc  lea     rdx, off_18002B7B0; "Meid"
0x180022703  lea     rcx, [rbp+3Fh+hstringHeader]
0x180022707  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002270c  nop
0x18002270d  mov     r8, rbx
0x180022710  mov     rdx, [rax+18h]
0x180022714  mov     rcx, rsi
0x180022717  mov     rax, rdi
0x18002271a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002271f  mov     ebx, eax
0x180022721  test    eax, eax
0x180022723  jns     loc_1800228DA
0x180022729  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180022730  jz      loc_180023100
0x180022736  lea     rax, aChrPjsonobject_9; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18002273d  mov     [rsp+110h+var_E8], rax
0x180022742  mov     dword ptr [rsp+110h+var_F0], 0CFh
0x18002274a  jmp     loc_1800223BD
0x18002274f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022754  mov     [rbp+3Fh+var_88], 0
0x18002275c  mov     r13d, 1Bh
0x180022762  mov     r9d, r13d; unsigned int
0x180022765  lea     r15d, [r13+1]
0x180022769  mov     r8d, r15d; unsigned int
0x18002276c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180022773  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x180022777  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002277c  nop
0x18002277d  lea     rdx, [rsp+110h+var_E0]
0x180022782  mov     rcx, [rbp+3Fh+var_88]
  ... truncated ...
```
