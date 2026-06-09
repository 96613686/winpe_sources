# DdcProtectionStateHelper::GetDefenderValues(Windows::Data::Json::IJsonObject *)

- ea: `0x18001e8a0`
- end: `0x18001f233`
- name: `?GetDefenderValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `2451`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x18001cfe8`
- `0x18001e80c`
- `0x18001e8a0`
- `0x18001f694`
- `0x18001f6d0`
- `0x18002045c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001eb23`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001eb23`

## string_xrefs

- `0x18001eb04`: `Windows.Data.Json.JsonValue`
- `0x18001eb3c`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001f1d8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001ea62`: `EnableControlledFolderAccess`
- `0x18001ea69`: `Windows Defender Exploit Guard\Controlled Folder Access`
- `0x18001eb9d`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRunning).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ebf7`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RUNNING).Get(), pJsonValue.Get()))`
- `0x18001ec58`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderCloudBasedProtectionStatus).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ecb2`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_CLOUD_BASED_PROTECTION_STATUS).Get(), pJsonValue.Get()))`
- `0x18001ed13`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderCloudBasedProtectionOrigin).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ed6d`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_CLOUD_BASED_PROTECTION_ORIGIN).Get(), pJsonValue.Get()))`
- `0x18001edce`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderSampleSubmissionEnabled).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ee28`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_SAMPLE_SUBMISSION_ENABLED).Get(), pJsonValue.Get()))`
- `0x18001ee89`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderSampleSubmissionOrigin).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001eee3`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_SAMPLE_SUBMISSION_ORIGIN).Get(), pJsonValue.Get()))`
- `0x18001ef44`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRtpEnabled).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001ef9e`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RTP_ENABLED).Get(), pJsonValue.Get()))`
- `0x18001efff`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRtpOrigin).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001f059`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RTP_ORIGIN).Get(), pJsonValue.Get()))`
- `0x18001f0ba`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFolderGuardEnabled).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001f114`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_FOLDER_GUARD_ENABLED).Get(), pJsonValue.Get()))`
- `0x18001f171`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFolderGuardOrigin).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001f1c4`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_FOLDER_GUARD_ORIGIN).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetDefenderValues(struct Windows::Data::Json::IJsonObject *a1, int a2)
{
  int ActivationFactory; // ebx
  int v4; // edx
  int v5; // ecx
  IUnknown *v6; // rbx
  int v7; // edx
  int *v8; // rcx
  const WCHAR *v9; // r8
  int *v10; // rcx
  const WCHAR *v11; // r8
  int *v12; // rcx
  const WCHAR *v13; // r8
  unsigned int *v14; // rcx
  enum ConfigOrigin *v15; // rcx
  enum ConfigOrigin *v16; // rcx
  enum ConfigOrigin *v17; // rcx
  const WCHAR *v18; // rdx
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PVOID, __int64 *); // rbx
  char v23; // r8
  HSTRING_HEADER *v24; // rax
  int v25; // edx
  int v26; // ecx
  char v27; // r8
  __int64 (__fastcall *v28)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v29; // rbx
  HSTRING_HEADER *v30; // rax
  int v31; // edx
  int v32; // ecx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, PVOID, __int64 *); // rbx
  char v35; // r8
  HSTRING_HEADER *v36; // rax
  int v37; // edx
  int v38; // ecx
  char v39; // r8
  __int64 (__fastcall *v40)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v41; // rbx
  HSTRING_HEADER *v42; // rax
  int v43; // edx
  int v44; // ecx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, PVOID, __int64 *); // rbx
  char v47; // r8
  HSTRING_HEADER *v48; // rax
  int v49; // edx
  int v50; // ecx
  char v51; // r8
  __int64 (__fastcall *v52)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v53; // rbx
  HSTRING_HEADER *v54; // rax
  int v55; // edx
  int v56; // ecx
  __int64 v57; // rdi
  __int64 (__fastcall *v58)(__int64, PVOID, __int64 *); // rbx
  char v59; // r8
  HSTRING_HEADER *v60; // rax
  int v61; // edx
  int v62; // ecx
  char v63; // r8
  __int64 (__fastcall *v64)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v65; // rbx
  HSTRING_HEADER *v66; // rax
  int v67; // edx
  int v68; // ecx
  __int64 v69; // rdi
  __int64 (__fastcall *v70)(__int64, PVOID, __int64 *); // rbx
  char v71; // r8
  HSTRING_HEADER *v72; // rax
  int v73; // edx
  int v74; // ecx
  char v75; // r8
  __int64 (__fastcall *v76)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v77; // rbx
  HSTRING_HEADER *v78; // rax
  int v79; // edx
  int v80; // ecx
  __int64 v81; // rdi
  __int64 (__fastcall *v82)(__int64, PVOID, __int64 *); // rbx
  char v83; // r8
  HSTRING_HEADER *v84; // rax
  int v85; // edx
  int v86; // ecx
  char v87; // r8
  __int64 (__fastcall *v88)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v89; // rbx
  HSTRING_HEADER *v90; // rax
  int v91; // edx
  int v92; // ecx
  __int64 v93; // rdi
  __int64 (__fastcall *v94)(__int64, PVOID, __int64 *); // rbx
  char v95; // r8
  HSTRING_HEADER *v96; // rax
  int v97; // edx
  int v98; // ecx
  char v99; // r8
  __int64 (__fastcall *v100)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v101; // rbx
  HSTRING_HEADER *v102; // rax
  int v103; // edx
  int v104; // ecx
  __int64 v105; // rdi
  __int64 (__fastcall *v106)(__int64, PVOID, __int64 *); // rbx
  char v107; // r8
  HSTRING_HEADER *v108; // rax
  int v109; // edx
  int v110; // ecx
  char v111; // r8
  __int64 (__fastcall *v112)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v113; // rbx
  HSTRING_HEADER *v114; // rax
  int v115; // edx
  int v116; // ecx
  __int64 v117; // rdi
  __int64 (__fastcall *v118)(__int64, PVOID, __int64 *); // rbx
  char v119; // r8
  HSTRING_HEADER *v120; // rax
  int v121; // edx
  int v122; // ecx
  char v123; // r8
  __int64 (__fastcall *v124)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v125; // rbx
  HSTRING_HEADER *v126; // rax
  int v127; // edx
  int v128; // ecx
  __int64 v129; // rcx
  __int64 v131; // [rsp+30h] [rbp-69h] BYREF
  int v132; // [rsp+38h] [rbp-61h] BYREF
  int v133; // [rsp+3Ch] [rbp-5Dh] BYREF
  __int64 v134; // [rsp+40h] [rbp-59h] BYREF
  int v135; // [rsp+48h] [rbp-51h] BYREF
  int v136; // [rsp+4Ch] [rbp-4Dh] BYREF
  IUnknown *v137; // [rsp+50h] [rbp-49h] BYREF
  const WCHAR *RunningModeMapping; // [rsp+58h] [rbp-41h] BYREF
  const WCHAR *v139; // [rsp+60h] [rbp-39h] BYREF
  const WCHAR *ConfigOriginMapping; // [rsp+68h] [rbp-31h] BYREF
  const WCHAR *v141; // [rsp+70h] [rbp-29h] BYREF
  const WCHAR *v142; // [rsp+78h] [rbp-21h] BYREF
  const WCHAR *v143; // [rsp+80h] [rbp-19h] BYREF
  const WCHAR *v144; // [rsp+88h] [rbp-11h] BYREF
  const WCHAR *v145; // [rsp+90h] [rbp-9h] BYREF
  const WCHAR *v146; // [rsp+98h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v148; // [rsp+B8h] [rbp+1Fh]

  v137 = 0;
  v135 = 0;
  v133 = 0;
  v136 = 0;
  v132 = 0;
  v134 = 0;
  v131 = 0;
  if ( !a1 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        74,
        "CPR(pProtectionState)");
    goto LABEL_78;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  if ( (int)CreateInstanceWithCloak<IDefenderShield>(v5, v4, &v137) < 0
    || (v6 = v137, ((int (__fastcall *)(IUnknown *, int *))v137->lpVtbl[23].Release)(v137, &v135) < 0) )
  {
    RunningModeMapping = GetRunningModeMapping(0);
    goto LABEL_19;
  }
  RunningModeMapping = GetRunningModeMapping((enum tagMPRUNNING_MODE *)&v135);
  if ( !v7 )
  {
LABEL_19:
    v139 = GetOnOffMapping(0);
    ConfigOriginMapping = GetConfigOriginMapping(v15);
    v141 = GetOnOffMapping(0);
    v142 = GetConfigOriginMapping(v16);
    v143 = GetOnOffMapping(0);
    v144 = GetConfigOriginMapping(v17);
    goto LABEL_20;
  }
  if ( ((int (__fastcall *)(IUnknown *, int *, int *))v6->lpVtbl[13].AddRef)(v6, &v133, &v132) < 0 )
  {
    GetConfigOriginMapping(0);
    v8 = 0;
  }
  else
  {
    GetConfigOriginMapping((enum ConfigOrigin *)&v132);
    v8 = &v133;
  }
  v139 = GetOnOffMapping(v8);
  ConfigOriginMapping = v9;
  if ( ((int (__fastcall *)(IUnknown *, int *, int *))v6->lpVtbl[13].Release)(v6, &v133, &v132) < 0 )
  {
    GetConfigOriginMapping(0);
    v10 = 0;
  }
  else
  {
    GetConfigOriginMapping((enum ConfigOrigin *)&v132);
    v10 = &v133;
  }
  v141 = GetOnOffMapping(v10);
  v142 = v11;
  if ( ((int (__fastcall *)(IUnknown *, int *, int *))v6->lpVtbl[14].QueryInterface)(v6, &v133, &v132) < 0 )
  {
    GetConfigOriginMapping(0);
    v12 = 0;
  }
  else
  {
    GetConfigOriginMapping((enum ConfigOrigin *)&v132);
    v12 = &v133;
  }
  v143 = GetOnOffMapping(v12);
  v144 = v13;
  if ( ((int (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, int *, int *))v6->lpVtbl[9].QueryInterface)(
         v6,
         L"Windows Defender Exploit Guard\\Controlled Folder Access",
         L"EnableControlledFolderAccess",
         &v136,
         &v132) >= 0 )
  {
    GetConfigOriginMapping((enum ConfigOrigin *)&v132);
    v14 = (unsigned int *)&v136;
    goto LABEL_21;
  }
LABEL_20:
  GetConfigOriginMapping(0);
  v14 = 0;
LABEL_21:
  v145 = GetOnOffAuditMapping(v14);
  v146 = v18;
  v148 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v148, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v134);
  if ( ActivationFactory >= 0 )
  {
    v21 = v134;
    v22 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &RunningModeMapping, v23);
    ActivationFactory = v22(v21, v24[1].Reserved.Reserved1, &v131);
    if ( ActivationFactory >= 0 )
    {
      v28 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
      v29 = v131;
      v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B6F0,
              v27);
      ActivationFactory = v28(a1, v30[1].Reserved.Reserved1, v29);
      if ( ActivationFactory >= 0 )
      {
        v33 = v134;
        v34 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
        v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v139, v35);
        ActivationFactory = v34(v33, v36[1].Reserved.Reserved1, &v131);
        if ( ActivationFactory >= 0 )
        {
          v40 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
          v41 = v131;
          v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_18002B6E8,
                  v39);
          ActivationFactory = v40(a1, v42[1].Reserved.Reserved1, v41);
          if ( ActivationFactory >= 0 )
          {
            v45 = v134;
            v46 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
            v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    &ConfigOriginMapping,
                    v47);
            ActivationFactory = v46(v45, v48[1].Reserved.Reserved1, &v131);
            if ( ActivationFactory >= 0 )
            {
              v52 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
              v53 = v131;
              v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_18002B6E0,
                      v51);
              ActivationFactory = v52(a1, v54[1].Reserved.Reserved1, v53);
              if ( ActivationFactory >= 0 )
              {
                v57 = v134;
                v58 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                v60 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v141, v59);
                ActivationFactory = v58(v57, v60[1].Reserved.Reserved1, &v131);
                if ( ActivationFactory >= 0 )
                {
                  v64 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                  v65 = v131;
                  v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &hstringHeader,
                          (const WCHAR **)off_18002B6D8,
                          v63);
                  ActivationFactory = v64(a1, v66[1].Reserved.Reserved1, v65);
                  if ( ActivationFactory >= 0 )
                  {
                    v69 = v134;
                    v70 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                    v72 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v142, v71);
                    ActivationFactory = v70(v69, v72[1].Reserved.Reserved1, &v131);
                    if ( ActivationFactory >= 0 )
                    {
                      v76 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                      v77 = v131;
                      v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                              &hstringHeader,
                              (const WCHAR **)off_18002B6D0,
                              v75);
                      ActivationFactory = v76(a1, v78[1].Reserved.Reserved1, v77);
                      if ( ActivationFactory >= 0 )
                      {
                        v81 = v134;
                        v82 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                        v84 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v143, v83);
                        ActivationFactory = v82(v81, v84[1].Reserved.Reserved1, &v131);
                        if ( ActivationFactory >= 0 )
                        {
                          v88 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                          v89 = v131;
                          v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                  &hstringHeader,
                                  (const WCHAR **)off_18002B6C8,
                                  v87);
                          ActivationFactory = v88(a1, v90[1].Reserved.Reserved1, v89);
                          if ( ActivationFactory >= 0 )
                          {
                            v93 = v134;
                            v94 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                            v96 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                    &hstringHeader,
                                    &v144,
                                    v95);
                            ActivationFactory = v94(v93, v96[1].Reserved.Reserved1, &v131);
                            if ( ActivationFactory >= 0 )
                            {
                              v100 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                              v101 = v131;
                              v102 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       (const WCHAR **)off_18002B6C0,
                                       v99);
                              ActivationFactory = v100(a1, v102[1].Reserved.Reserved1, v101);
                              if ( ActivationFactory >= 0 )
                              {
                                v105 = v134;
                                v106 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                                v108 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                         &hstringHeader,
                                         &v145,
                                         v107);
                                ActivationFactory = v106(v105, v108[1].Reserved.Reserved1, &v131);
                                if ( ActivationFactory >= 0 )
                                {
                                  v112 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                  v113 = v131;
                                  v114 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           &hstringHeader,
                                           (const WCHAR **)off_18002B6B8,
                                           v111);
                                  ActivationFactory = v112(a1, v114[1].Reserved.Reserved1, v113);
                                  if ( ActivationFactory >= 0 )
                                  {
                                    v117 = v134;
                                    v118 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v134 + 80LL);
                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                                    v120 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                             &hstringHeader,
                                             &v146,
                                             v119);
                                    ActivationFactory = v118(v117, v120[1].Reserved.Reserved1, &v131);
                                    if ( ActivationFactory >= 0 )
                                    {
                                      v124 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                      v125 = v131;
                                      v126 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                               &hstringHeader,
                                               (const WCHAR **)off_18002B6B0,
                                               v123);
                                      ActivationFactory = v124(a1, v126[1].Reserved.Reserved1, v125);
                                      if ( ActivationFactory < 0
                                        && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                      {
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v128,
                                          v127,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcprotectionstatehelper.cpp",
                                          176,
                                          "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_FOLDER_GUAR"
                                          "D_ORIGIN).Get(), pJsonValue.Get()))");
                                      }
                                    }
                                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    {
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v122,
                                        v121,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\dd"
                                                      "cprotectionstatehelper.cpp",
                                        175,
                                        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFolderGuardOrigin)"
                                        ".Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                    }
                                  }
                                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  {
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v116,
                                      v115,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcp"
                                                    "rotectionstatehelper.cpp",
                                      174,
                                      "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_FOLDER_GUARD_EN"
                                      "ABLED).Get(), pJsonValue.Get()))");
                                  }
                                }
                                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                {
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v110,
                                    v109,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcpro"
                                                  "tectionstatehelper.cpp",
                                    173,
                                    "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszFolderGuardEnabled).Ge"
                                    "t(), pJsonValue.ReleaseAndGetAddressOf()))");
                                }
                              }
                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                              {
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v104,
                                  v103,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprote"
                                                "ctionstatehelper.cpp",
                                  171,
                                  "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RTP_ORIGIN).Get(), "
                                  "pJsonValue.Get()))");
                              }
                            }
                            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                            {
                              McTemplateU0dsqs_EventWriteTransfer(
                                v98,
                                v97,
                                ActivationFactory,
                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotect"
                                              "ionstatehelper.cpp",
                                170,
                                "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRtpOrigin).Get(), "
                                "pJsonValue.ReleaseAndGetAddressOf()))");
                            }
                          }
                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v92,
                              v91,
                              ActivationFactory,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectio"
                                            "nstatehelper.cpp",
                              169,
                              "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RTP_ENABLED).Get(), pJsonValue.Get()))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v86,
                            v85,
                            ActivationFactory,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                            168,
                            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRtpEnabled).Get(), pJs"
                            "onValue.ReleaseAndGetAddressOf()))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v80,
                          v79,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                          166,
                          "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_SAMPLE_SUBMISSION_ORIGIN).G"
                          "et(), pJsonValue.Get()))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v74,
                        v73,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                        165,
                        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderSampleSubmissionOrigin).Ge"
                        "t(), pJsonValue.ReleaseAndGetAddressOf()))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v68,
                      v67,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                      164,
                      "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_SAMPLE_SUBMISSION_ENABLED).Get("
                      "), pJsonValue.Get()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v62,
                    v61,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    163,
                    "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderSampleSubmissionEnabled).Get()"
                    ", pJsonValue.ReleaseAndGetAddressOf()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v56,
                  v55,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                  161,
                  "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_CLOUD_BASED_PROTECTION_ORIGIN).Get("
                  "), pJsonValue.Get()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v50,
                v49,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                160,
                "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderCloudBasedProtectionOrigin).Get(),"
                " pJsonValue.ReleaseAndGetAddressOf()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v44,
              v43,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
              159,
              "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_CLOUD_BASED_PROTECTION_STATUS).Get(), p"
              "JsonValue.Get()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v38,
            v37,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            158,
            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderCloudBasedProtectionStatus).Get(), pJs"
            "onValue.ReleaseAndGetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v32,
          v31,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          156,
          "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_DEFENDER_RUNNING).Get(), pJsonValue.Get()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v26,
        v25,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        155,
        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszDefenderRunning).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v20,
      v19,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      153,
      "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
  }
LABEL_78:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
  v129 = v134;
  if ( v134 )
  {
    v134 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001e8a0  push    rbp
0x18001e8a2  push    rbx
0x18001e8a3  push    rsi
0x18001e8a4  push    rdi
0x18001e8a5  lea     rbp, [rsp-3Fh]
0x18001e8aa  sub     rsp, 0D8h
0x18001e8b1  mov     rax, cs:__security_cookie
0x18001e8b8  xor     rax, rsp
0x18001e8bb  mov     [rbp+57h+var_30], rax
0x18001e8bf  mov     rsi, rcx
0x18001e8c2  mov     [rbp+57h+var_A0], 0
0x18001e8ca  mov     [rbp+57h+var_A8], 0
0x18001e8d1  mov     [rbp+57h+var_B4], 0
0x18001e8d8  mov     [rbp+57h+var_A4], 0
0x18001e8df  mov     [rbp+57h+var_B8], 0
0x18001e8e6  mov     [rbp+57h+var_B0], 0
0x18001e8ee  mov     [rbp+57h+var_C0], 0
0x18001e8f6  test    rcx, rcx
0x18001e8f9  jnz     short loc_18001E926
0x18001e8fb  mov     ebx, 80070057h
0x18001e900  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001e907  jz      loc_18001F1E8
0x18001e90d  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x18001e914  mov     [rsp+0F0h+var_C8], rax
0x18001e919  mov     dword ptr [rsp+0F0h+var_D0], 34Ah
0x18001e921  jmp     loc_18001F1D8
0x18001e926  lea     rcx, [rbp+57h+var_A0]
0x18001e92a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e92f  lea     r8, [rbp+57h+var_A0]
0x18001e933  call    ??$CreateInstanceWithCloak@UIDefenderShield@@@@YAJAEBU_GUID@@0PEAPEAUIDefenderShield@@@Z; CreateInstanceWithCloak<IDefenderShield>(_GUID const &,_GUID const &,IDefenderShield * *)
0x18001e938  test    eax, eax
0x18001e93a  js      loc_18001EA92
0x18001e940  mov     rbx, [rbp+57h+var_A0]
0x18001e944  mov     rax, [rbx]
0x18001e947  lea     rdx, [rbp+57h+var_A8]
0x18001e94b  mov     rcx, rbx
0x18001e94e  mov     rax, [rax+238h]
0x18001e955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e95a  test    eax, eax
0x18001e95c  js      loc_18001EA92
0x18001e962  xor     edx, edx
0x18001e964  cmp     [rbp+57h+var_A8], 3
0x18001e968  setnz   dl
0x18001e96b  lea     rcx, [rbp+57h+var_A8]; enum tagMPRUNNING_MODE *
0x18001e96f  call    ?GetRunningModeMapping@@YAPEBGPEAW4tagMPRUNNING_MODE@@@Z; GetRunningModeMapping(tagMPRUNNING_MODE *)
0x18001e974  mov     [rbp+57h+var_98], rax
0x18001e978  test    edx, edx
0x18001e97a  jz      loc_18001EA9D
0x18001e980  mov     rax, [rbx]
0x18001e983  lea     r8, [rbp+57h+var_B8]
0x18001e987  lea     rdx, [rbp+57h+var_B4]
0x18001e98b  mov     rcx, rbx
0x18001e98e  mov     rax, [rax+140h]
0x18001e995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e99a  test    eax, eax
0x18001e99c  js      short loc_18001E9AD
0x18001e99e  lea     rcx, [rbp+57h+var_B8]; enum ConfigOrigin *
0x18001e9a2  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001e9a7  lea     rcx, [rbp+57h+var_B4]
0x18001e9ab  jmp     short loc_18001E9B6
0x18001e9ad  xor     ecx, ecx; enum ConfigOrigin *
0x18001e9af  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001e9b4  xor     ecx, ecx; int *
0x18001e9b6  mov     r8, rax
0x18001e9b9  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001e9be  mov     [rbp+57h+var_90], rax
0x18001e9c2  mov     [rbp+57h+var_88], r8
0x18001e9c6  mov     rax, [rbx]
0x18001e9c9  lea     r8, [rbp+57h+var_B8]
0x18001e9cd  lea     rdx, [rbp+57h+var_B4]
0x18001e9d1  mov     rcx, rbx
0x18001e9d4  mov     rax, [rax+148h]
0x18001e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e0  test    eax, eax
0x18001e9e2  js      short loc_18001E9F3
0x18001e9e4  lea     rcx, [rbp+57h+var_B8]; enum ConfigOrigin *
0x18001e9e8  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001e9ed  lea     rcx, [rbp+57h+var_B4]
0x18001e9f1  jmp     short loc_18001E9FC
0x18001e9f3  xor     ecx, ecx; enum ConfigOrigin *
0x18001e9f5  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001e9fa  xor     ecx, ecx; int *
0x18001e9fc  mov     r8, rax
0x18001e9ff  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001ea04  mov     [rbp+57h+var_80], rax
0x18001ea08  mov     [rbp+57h+var_78], r8
0x18001ea0c  mov     rax, [rbx]
0x18001ea0f  lea     r8, [rbp+57h+var_B8]
0x18001ea13  lea     rdx, [rbp+57h+var_B4]
0x18001ea17  mov     rcx, rbx
0x18001ea1a  mov     rax, [rax+150h]
0x18001ea21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea26  test    eax, eax
0x18001ea28  js      short loc_18001EA39
0x18001ea2a  lea     rcx, [rbp+57h+var_B8]; enum ConfigOrigin *
0x18001ea2e  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001ea33  lea     rcx, [rbp+57h+var_B4]
0x18001ea37  jmp     short loc_18001EA42
0x18001ea39  xor     ecx, ecx; enum ConfigOrigin *
0x18001ea3b  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001ea40  xor     ecx, ecx; int *
0x18001ea42  mov     r8, rax
0x18001ea45  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001ea4a  mov     [rbp+57h+var_70], rax
0x18001ea4e  mov     [rbp+57h+var_68], r8
0x18001ea52  mov     rax, [rbx]
0x18001ea55  lea     rcx, [rbp+57h+var_B8]
0x18001ea59  mov     [rsp+0F0h+var_D0], rcx
0x18001ea5e  lea     r9, [rbp+57h+var_A4]
0x18001ea62  lea     r8, aEnablecontroll; "EnableControlledFolderAccess"
0x18001ea69  lea     rdx, aWindowsDefende; "Windows Defender Exploit Guard\\Control"...
0x18001ea70  mov     rcx, rbx
0x18001ea73  mov     rax, [rax+0D8h]
0x18001ea7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea7f  test    eax, eax
0x18001ea81  js      short loc_18001EAD9
0x18001ea83  lea     rcx, [rbp+57h+var_B8]; enum ConfigOrigin *
0x18001ea87  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001ea8c  lea     rcx, [rbp+57h+var_A4]
0x18001ea90  jmp     short loc_18001EAE2
0x18001ea92  xor     ecx, ecx; enum tagMPRUNNING_MODE *
0x18001ea94  call    ?GetRunningModeMapping@@YAPEBGPEAW4tagMPRUNNING_MODE@@@Z; GetRunningModeMapping(tagMPRUNNING_MODE *)
0x18001ea99  mov     [rbp+57h+var_98], rax
0x18001ea9d  xor     ecx, ecx; int *
0x18001ea9f  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001eaa4  mov     [rbp+57h+var_90], rax
0x18001eaa8  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001eaad  mov     [rbp+57h+var_88], rax
0x18001eab1  xor     ecx, ecx; int *
0x18001eab3  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001eab8  mov     [rbp+57h+var_80], rax
0x18001eabc  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001eac1  mov     [rbp+57h+var_78], rax
0x18001eac5  xor     ecx, ecx; int *
0x18001eac7  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001eacc  mov     [rbp+57h+var_70], rax
0x18001ead0  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001ead5  mov     [rbp+57h+var_68], rax
0x18001ead9  xor     ecx, ecx; enum ConfigOrigin *
0x18001eadb  call    ?GetConfigOriginMapping@@YAPEBGPEAW4ConfigOrigin@@@Z; GetConfigOriginMapping(ConfigOrigin *)
0x18001eae0  xor     ecx, ecx; unsigned int *
0x18001eae2  mov     rdx, rax
0x18001eae5  call    ?GetOnOffAuditMapping@@YAPEBGPEAK@Z; GetOnOffAuditMapping(ulong *)
0x18001eaea  mov     [rbp+57h+var_60], rax
0x18001eaee  mov     [rbp+57h+var_58], rdx
0x18001eaf2  mov     [rbp+57h+var_38], 0
0x18001eafa  mov     r9d, 1Bh; unsigned int
0x18001eb00  lea     r8d, [r9+1]; unsigned int
0x18001eb04  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001eb0b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001eb0f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001eb14  lea     r8, [rbp+57h+var_B0]
0x18001eb18  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001eb1f  mov     rcx, [rbp+57h+var_38]
0x18001eb23  call    cs:__imp_RoGetActivationFactory
0x18001eb29  mov     ebx, eax
0x18001eb2b  test    eax, eax
0x18001eb2d  jns     short loc_18001EB55
0x18001eb2f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001eb36  jz      loc_18001F1E8
0x18001eb3c  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001eb43  mov     [rsp+0F0h+var_C8], rax
0x18001eb48  mov     dword ptr [rsp+0F0h+var_D0], 399h
0x18001eb50  jmp     loc_18001F1D8
0x18001eb55  mov     rdi, [rbp+57h+var_B0]
0x18001eb59  mov     rax, [rdi]
0x18001eb5c  mov     rbx, [rax+50h]
0x18001eb60  lea     rcx, [rbp+57h+var_C0]
0x18001eb64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb69  lea     rdx, [rbp+57h+var_98]
0x18001eb6d  lea     rcx, [rbp+57h+hstringHeader]
0x18001eb71  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001eb76  nop
0x18001eb77  lea     r8, [rbp+57h+var_C0]
0x18001eb7b  mov     rdx, [rax+18h]
0x18001eb7f  mov     rcx, rdi
0x18001eb82  mov     rax, rbx
0x18001eb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb8a  mov     ebx, eax
0x18001eb8c  test    eax, eax
0x18001eb8e  jns     short loc_18001EBB6
0x18001eb90  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001eb97  jz      loc_18001F1E8
0x18001eb9d  lea     rax, aChrPjsonvalues_8; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001eba4  mov     [rsp+0F0h+var_C8], rax
0x18001eba9  mov     dword ptr [rsp+0F0h+var_D0], 39Bh
0x18001ebb1  jmp     loc_18001F1D8
0x18001ebb6  mov     rax, [rsi]
0x18001ebb9  mov     rdi, [rax+38h]
0x18001ebbd  mov     rbx, [rbp+57h+var_C0]
0x18001ebc1  lea     rdx, off_18002B6F0; "DefenderRunning"
0x18001ebc8  lea     rcx, [rbp+57h+hstringHeader]
0x18001ebcc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ebd1  nop
0x18001ebd2  mov     r8, rbx
0x18001ebd5  mov     rdx, [rax+18h]
0x18001ebd9  mov     rcx, rsi
0x18001ebdc  mov     rax, rdi
0x18001ebdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebe4  mov     ebx, eax
0x18001ebe6  test    eax, eax
0x18001ebe8  jns     short loc_18001EC10
0x18001ebea  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ebf1  jz      loc_18001F1E8
0x18001ebf7  lea     rax, aChrPprotection_15; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001ebfe  mov     [rsp+0F0h+var_C8], rax
0x18001ec03  mov     dword ptr [rsp+0F0h+var_D0], 39Ch
0x18001ec0b  jmp     loc_18001F1D8
0x18001ec10  mov     rdi, [rbp+57h+var_B0]
0x18001ec14  mov     rax, [rdi]
0x18001ec17  mov     rbx, [rax+50h]
0x18001ec1b  lea     rcx, [rbp+57h+var_C0]
0x18001ec1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ec24  lea     rdx, [rbp+57h+var_90]
0x18001ec28  lea     rcx, [rbp+57h+hstringHeader]
0x18001ec2c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ec31  nop
0x18001ec32  lea     r8, [rbp+57h+var_C0]
0x18001ec36  mov     rdx, [rax+18h]
0x18001ec3a  mov     rcx, rdi
0x18001ec3d  mov     rax, rbx
0x18001ec40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec45  mov     ebx, eax
0x18001ec47  test    eax, eax
0x18001ec49  jns     short loc_18001EC71
0x18001ec4b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ec52  jz      loc_18001F1E8
0x18001ec58  lea     rax, aChrPjsonvalues_53; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001ec5f  mov     [rsp+0F0h+var_C8], rax
0x18001ec64  mov     dword ptr [rsp+0F0h+var_D0], 39Eh
0x18001ec6c  jmp     loc_18001F1D8
0x18001ec71  mov     rax, [rsi]
0x18001ec74  mov     rdi, [rax+38h]
0x18001ec78  mov     rbx, [rbp+57h+var_C0]
0x18001ec7c  lea     rdx, off_18002B6E8; "DefenderCloudBasedProtectionStatus"
0x18001ec83  lea     rcx, [rbp+57h+hstringHeader]
0x18001ec87  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ec8c  nop
0x18001ec8d  mov     r8, rbx
0x18001ec90  mov     rdx, [rax+18h]
0x18001ec94  mov     rcx, rsi
0x18001ec97  mov     rax, rdi
0x18001ec9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec9f  mov     ebx, eax
0x18001eca1  test    eax, eax
0x18001eca3  jns     short loc_18001ECCB
0x18001eca5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ecac  jz      loc_18001F1E8
0x18001ecb2  lea     rax, aChrPprotection_16; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001ecb9  mov     [rsp+0F0h+var_C8], rax
0x18001ecbe  mov     dword ptr [rsp+0F0h+var_D0], 39Fh
0x18001ecc6  jmp     loc_18001F1D8
0x18001eccb  mov     rdi, [rbp+57h+var_B0]
0x18001eccf  mov     rax, [rdi]
0x18001ecd2  mov     rbx, [rax+50h]
0x18001ecd6  lea     rcx, [rbp+57h+var_C0]
0x18001ecda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ecdf  lea     rdx, [rbp+57h+var_88]
0x18001ece3  lea     rcx, [rbp+57h+hstringHeader]
0x18001ece7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ecec  nop
0x18001eced  lea     r8, [rbp+57h+var_C0]
0x18001ecf1  mov     rdx, [rax+18h]
0x18001ecf5  mov     rcx, rdi
0x18001ecf8  mov     rax, rbx
0x18001ecfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed00  mov     ebx, eax
0x18001ed02  test    eax, eax
0x18001ed04  jns     short loc_18001ED2C
0x18001ed06  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ed0d  jz      loc_18001F1E8
0x18001ed13  lea     rax, aChrPjsonvalues_15; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001ed1a  mov     [rsp+0F0h+var_C8], rax
0x18001ed1f  mov     dword ptr [rsp+0F0h+var_D0], 3A0h
0x18001ed27  jmp     loc_18001F1D8
0x18001ed2c  mov     rax, [rsi]
0x18001ed2f  mov     rdi, [rax+38h]
0x18001ed33  mov     rbx, [rbp+57h+var_C0]
0x18001ed37  lea     rdx, off_18002B6E0; "DefenderCloudBasedProtectionOrigin"
0x18001ed3e  lea     rcx, [rbp+57h+hstringHeader]
0x18001ed42  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001ed47  nop
0x18001ed48  mov     r8, rbx
0x18001ed4b  mov     rdx, [rax+18h]
0x18001ed4f  mov     rcx, rsi
0x18001ed52  mov     rax, rdi
0x18001ed55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed5a  mov     ebx, eax
0x18001ed5c  test    eax, eax
0x18001ed5e  jns     short loc_18001ED86
0x18001ed60  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001ed67  jz      loc_18001F1E8
0x18001ed6d  lea     rax, aChrPprotection_11; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001ed74  mov     [rsp+0F0h+var_C8], rax
0x18001ed79  mov     dword ptr [rsp+0F0h+var_D0], 3A1h
0x18001ed81  jmp     loc_18001F1D8
0x18001ed86  mov     rdi, [rbp+57h+var_B0]
0x18001ed8a  mov     rax, [rdi]
0x18001ed8d  mov     rbx, [rax+50h]
0x18001ed91  lea     rcx, [rbp+57h+var_C0]
  ... truncated ...
```
