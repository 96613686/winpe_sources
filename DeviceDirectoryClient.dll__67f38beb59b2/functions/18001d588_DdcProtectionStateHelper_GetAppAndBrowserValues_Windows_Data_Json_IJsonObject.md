# DdcProtectionStateHelper::GetAppAndBrowserValues(Windows::Data::Json::IJsonObject *)

- ea: `0x18001d588`
- end: `0x18001dc32`
- name: `?GetAppAndBrowserValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x18001cd18`
- `0x18001d588`
- `0x18001e864`
- `0x18001f6d0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d753`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d753`

## string_xrefs

- `0x18001d734`: `Windows.Data.Json.JsonValue`
- `0x18001d76c`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001dbd7`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001d7cd`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppInstallRule).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001d827`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APP_INSTALL_RULE).Get(), pJsonValue.Get()))`
- `0x18001d888`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppInstallRuleControlledByPolicy).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001d8e2`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APP_INSTALL_RULE_CONTROLLED_BY_POLICY).Get(), pJsonValue.Get()))`
- `0x18001d943`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBrowserSmartScreen).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001d99d`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_BROWSER_SMART_SCREEN_).Get(), pJsonValue.Get()))`
- `0x18001d9fe`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBrowserSmartScreenControlledByPolicy).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001da58`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_BROWSER_SMART_SCREEN_CONTROLLED_BY_POLICY).Get(), pJsonValue.Get()))`
- `0x18001dab9`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppsSmartScreen).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001db13`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APPS_SMART_SCREEN_).Get(), pJsonValue.Get()))`
- `0x18001db70`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppsSmartScreenControlledByPolicy).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001dbc3`: `CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APPS_SMART_SCREEN_CONTROLLED_BY_POLICY).Get(), pJsonValue.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcProtectionStateHelper::GetAppAndBrowserValues(
        struct Windows::Data::Json::IJsonObject *a1,
        int a2)
{
  int ActivationFactory; // ebx
  int v4; // edx
  int v5; // ecx
  IUnknown *v6; // rbx
  enum AppAndBrowserControlLevel *v7; // rcx
  const WCHAR *v8; // r8
  const WCHAR *v9; // rax
  const WCHAR *v10; // r8
  int *v11; // rcx
  enum AppAndBrowserControlLevel *v12; // rcx
  int *v13; // rcx
  const WCHAR *v14; // rax
  const WCHAR *v15; // r8
  enum AppAndBrowserControlLevel *v16; // rcx
  int *v17; // rcx
  int v18; // edx
  int v19; // ecx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, PVOID, __int64 *); // rbx
  char v22; // r8
  HSTRING_HEADER *v23; // rax
  int v24; // edx
  int v25; // ecx
  char v26; // r8
  __int64 (__fastcall *v27)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v28; // rbx
  HSTRING_HEADER *v29; // rax
  int v30; // edx
  int v31; // ecx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, PVOID, __int64 *); // rbx
  char v34; // r8
  HSTRING_HEADER *v35; // rax
  int v36; // edx
  int v37; // ecx
  char v38; // r8
  __int64 (__fastcall *v39)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v40; // rbx
  HSTRING_HEADER *v41; // rax
  int v42; // edx
  int v43; // ecx
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, PVOID, __int64 *); // rbx
  char v46; // r8
  HSTRING_HEADER *v47; // rax
  int v48; // edx
  int v49; // ecx
  char v50; // r8
  __int64 (__fastcall *v51)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v52; // rbx
  HSTRING_HEADER *v53; // rax
  int v54; // edx
  int v55; // ecx
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, PVOID, __int64 *); // rbx
  char v58; // r8
  HSTRING_HEADER *v59; // rax
  int v60; // edx
  int v61; // ecx
  char v62; // r8
  __int64 (__fastcall *v63)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v64; // rbx
  HSTRING_HEADER *v65; // rax
  int v66; // edx
  int v67; // ecx
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, PVOID, __int64 *); // rbx
  char v70; // r8
  HSTRING_HEADER *v71; // rax
  int v72; // edx
  int v73; // ecx
  char v74; // r8
  __int64 (__fastcall *v75)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v76; // rbx
  HSTRING_HEADER *v77; // rax
  int v78; // edx
  int v79; // ecx
  __int64 v80; // rdi
  __int64 (__fastcall *v81)(__int64, PVOID, __int64 *); // rbx
  char v82; // r8
  HSTRING_HEADER *v83; // rax
  int v84; // edx
  int v85; // ecx
  char v86; // r8
  __int64 (__fastcall *v87)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v88; // rbx
  HSTRING_HEADER *v89; // rax
  int v90; // edx
  int v91; // ecx
  __int64 v92; // rcx
  __int64 v94; // [rsp+30h] [rbp-49h] BYREF
  int v95; // [rsp+38h] [rbp-41h] BYREF
  int v96; // [rsp+3Ch] [rbp-3Dh] BYREF
  __int64 v97; // [rsp+40h] [rbp-39h] BYREF
  IUnknown *v98; // [rsp+48h] [rbp-31h] BYREF
  const WCHAR *ControlLevelMapping; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v100; // [rsp+58h] [rbp-21h] BYREF
  const WCHAR *v101; // [rsp+60h] [rbp-19h] BYREF
  const WCHAR *v102; // [rsp+68h] [rbp-11h] BYREF
  const WCHAR *v103; // [rsp+70h] [rbp-9h] BYREF
  const WCHAR *v104; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v106; // [rsp+98h] [rbp+1Fh]

  v98 = 0;
  v96 = 0;
  v95 = 0;
  v97 = 0;
  v94 = 0;
  if ( !a1 )
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        31,
        "CPR(pProtectionState)");
    goto LABEL_55;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
  if ( (int)CreateInstanceWithCloak<IAppAndBrowserShield>(v5, v4, &v98) < 0 )
  {
    ControlLevelMapping = GetControlLevelMapping(0);
    v100 = GetOnOffMapping(0);
    v101 = GetControlLevelMapping(v16);
    v102 = GetOnOffMapping(0);
    GetOnOffMapping(v17);
  }
  else
  {
    v6 = v98;
    if ( ((int (__fastcall *)(IUnknown *, int *, int *))v98->lpVtbl[1].QueryInterface)(v98, &v96, &v95) < 0 )
    {
      GetOnOffMapping(0);
    }
    else
    {
      GetOnOffMapping(&v95);
      v7 = (enum AppAndBrowserControlLevel *)&v96;
    }
    ControlLevelMapping = GetControlLevelMapping(v7);
    v100 = v8;
    if ( ((int (__fastcall *)(IUnknown *, int *, int *))v6->lpVtbl[1].Release)(v6, &v96, &v95) < 0 )
    {
      GetOnOffMapping(0);
      v9 = GetOnOffMapping(v11);
    }
    else
    {
      GetOnOffMapping(&v95);
      v9 = GetControlLevelMapping((enum AppAndBrowserControlLevel *)&v96);
    }
    v101 = v9;
    v102 = v10;
    if ( ((int (__fastcall *)(IUnknown *, int *, int *))v6->lpVtbl[2].AddRef)(v6, &v96, &v95) < 0 )
    {
      GetOnOffMapping(0);
      v14 = GetOnOffMapping(v13);
      goto LABEL_16;
    }
    GetOnOffMapping(&v95);
    v12 = (enum AppAndBrowserControlLevel *)&v96;
  }
  v14 = GetControlLevelMapping(v12);
LABEL_16:
  v103 = v14;
  v104 = v15;
  v106 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v106, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v97);
  if ( ActivationFactory >= 0 )
  {
    v20 = v97;
    v21 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &ControlLevelMapping, v22);
    ActivationFactory = v21(v20, v23[1].Reserved.Reserved1, &v94);
    if ( ActivationFactory >= 0 )
    {
      v27 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
      v28 = v94;
      v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              &hstringHeader,
              (const WCHAR **)off_18002B670,
              v26);
      ActivationFactory = v27(a1, v29[1].Reserved.Reserved1, v28);
      if ( ActivationFactory >= 0 )
      {
        v32 = v97;
        v33 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
        v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v100, v34);
        ActivationFactory = v33(v32, v35[1].Reserved.Reserved1, &v94);
        if ( ActivationFactory >= 0 )
        {
          v39 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
          v40 = v94;
          v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)off_18002B668,
                  v38);
          ActivationFactory = v39(a1, v41[1].Reserved.Reserved1, v40);
          if ( ActivationFactory >= 0 )
          {
            v44 = v97;
            v45 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
            v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v101, v46);
            ActivationFactory = v45(v44, v47[1].Reserved.Reserved1, &v94);
            if ( ActivationFactory >= 0 )
            {
              v51 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
              v52 = v94;
              v53 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      (const WCHAR **)off_18002B660,
                      v50);
              ActivationFactory = v51(a1, v53[1].Reserved.Reserved1, v52);
              if ( ActivationFactory >= 0 )
              {
                v56 = v97;
                v57 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
                v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v102, v58);
                ActivationFactory = v57(v56, v59[1].Reserved.Reserved1, &v94);
                if ( ActivationFactory >= 0 )
                {
                  v63 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                  v64 = v94;
                  v65 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                          &hstringHeader,
                          (const WCHAR **)off_18002B658,
                          v62);
                  ActivationFactory = v63(a1, v65[1].Reserved.Reserved1, v64);
                  if ( ActivationFactory >= 0 )
                  {
                    v68 = v97;
                    v69 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
                    v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v103, v70);
                    ActivationFactory = v69(v68, v71[1].Reserved.Reserved1, &v94);
                    if ( ActivationFactory >= 0 )
                    {
                      v75 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                      v76 = v94;
                      v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                              &hstringHeader,
                              (const WCHAR **)off_18002B650,
                              v74);
                      ActivationFactory = v75(a1, v77[1].Reserved.Reserved1, v76);
                      if ( ActivationFactory >= 0 )
                      {
                        v80 = v97;
                        v81 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v97 + 80LL);
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
                        v83 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v104, v82);
                        ActivationFactory = v81(v80, v83[1].Reserved.Reserved1, &v94);
                        if ( ActivationFactory >= 0 )
                        {
                          v87 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                          v88 = v94;
                          v89 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                  &hstringHeader,
                                  (const WCHAR **)off_18002B648,
                                  v86);
                          ActivationFactory = v87(a1, v89[1].Reserved.Reserved1, v88);
                          if ( ActivationFactory < 0
                            && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v91,
                              v90,
                              ActivationFactory,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectio"
                                            "nstatehelper.cpp",
                              93,
                              "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APPS_SMART_SCREEN_CONTROLLED_BY_"
                              "POLICY).Get(), pJsonValue.Get()))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v85,
                            v84,
                            ActivationFactory,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                            92,
                            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppsSmartScreenControlledByPol"
                            "icy).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v79,
                          v78,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                          91,
                          "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APPS_SMART_SCREEN_).Get(), pJsonValue.Get()))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v73,
                        v72,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                        90,
                        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppsSmartScreen).Get(), pJsonValue"
                        ".ReleaseAndGetAddressOf()))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v67,
                      v66,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                      89,
                      "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_BROWSER_SMART_SCREEN_CONTROLLED_BY_POLIC"
                      "Y).Get(), pJsonValue.Get()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v61,
                    v60,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                    88,
                    "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBrowserSmartScreenControlledByPolicy)."
                    "Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v55,
                  v54,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                  87,
                  "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_BROWSER_SMART_SCREEN_).Get(), pJsonValue.Get()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v49,
                v48,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                86,
                "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszBrowserSmartScreen).Get(), pJsonValue.Rele"
                "aseAndGetAddressOf()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v43,
              v42,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
              85,
              "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APP_INSTALL_RULE_CONTROLLED_BY_POLICY).Get(), pJ"
              "sonValue.Get()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v37,
            v36,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            84,
            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppInstallRuleControlledByPolicy).Get(), pJson"
            "Value.ReleaseAndGetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v31,
          v30,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          83,
          "CHR(pProtectionState->SetNamedValue(HStringReference(JSON_APP_INSTALL_RULE).Get(), pJsonValue.Get()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v25,
        v24,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        82,
        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszAppInstallRule).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v19,
      v18,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      81,
      "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
  }
LABEL_55:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v94);
  v92 = v97;
  if ( v97 )
  {
    v97 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v98);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001d588  push    rbp
0x18001d58a  push    rbx
0x18001d58b  push    rsi
0x18001d58c  push    rdi
0x18001d58d  lea     rbp, [rsp-3Fh]
0x18001d592  sub     rsp, 0B8h
0x18001d599  mov     rax, cs:__security_cookie
0x18001d5a0  xor     rax, rsp
0x18001d5a3  mov     [rbp+57h+var_30], rax
0x18001d5a7  mov     rsi, rcx
0x18001d5aa  mov     [rbp+57h+var_88], 0
0x18001d5b2  mov     [rbp+57h+var_94], 0
0x18001d5b9  mov     [rbp+57h+var_98], 0
0x18001d5c0  mov     [rbp+57h+var_90], 0
0x18001d5c8  mov     [rbp+57h+var_A0], 0
0x18001d5d0  test    rcx, rcx
0x18001d5d3  jnz     short loc_18001D600
0x18001d5d5  mov     ebx, 80070057h
0x18001d5da  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d5e1  jz      loc_18001DBE7
0x18001d5e7  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x18001d5ee  mov     [rsp+0D0h+var_A8], rax
0x18001d5f3  mov     [rsp+0D0h+var_B0], 41Fh
0x18001d5fb  jmp     loc_18001DBD7
0x18001d600  lea     rcx, [rbp+57h+var_88]
0x18001d604  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d609  lea     r8, [rbp+57h+var_88]
0x18001d60d  call    ??$CreateInstanceWithCloak@UIAppAndBrowserShield@@@@YAJAEBU_GUID@@0PEAPEAUIAppAndBrowserShield@@@Z; CreateInstanceWithCloak<IAppAndBrowserShield>(_GUID const &,_GUID const &,IAppAndBrowserShield * *)
0x18001d612  test    eax, eax
0x18001d614  js      loc_18001D6E3
0x18001d61a  mov     rbx, [rbp+57h+var_88]
0x18001d61e  mov     rax, [rbx]
0x18001d621  lea     r8, [rbp+57h+var_98]
0x18001d625  lea     rdx, [rbp+57h+var_94]
0x18001d629  mov     rcx, rbx
0x18001d62c  mov     rax, [rax+18h]
0x18001d630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d635  test    eax, eax
0x18001d637  js      short loc_18001D648
0x18001d639  lea     rcx, [rbp+57h+var_98]; int *
0x18001d63d  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d642  lea     rcx, [rbp+57h+var_94]
0x18001d646  jmp     short loc_18001D64F
0x18001d648  xor     ecx, ecx; int *
0x18001d64a  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d64f  mov     r8, rax
0x18001d652  call    ?GetControlLevelMapping@@YAPEBGPEAW4AppAndBrowserControlLevel@@@Z; GetControlLevelMapping(AppAndBrowserControlLevel *)
0x18001d657  mov     [rbp+57h+var_80], rax
0x18001d65b  mov     [rbp+57h+var_78], r8
0x18001d65f  mov     rax, [rbx]
0x18001d662  lea     r8, [rbp+57h+var_98]
0x18001d666  lea     rdx, [rbp+57h+var_94]
0x18001d66a  mov     rcx, rbx
0x18001d66d  mov     rax, [rax+28h]
0x18001d671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d676  test    eax, eax
0x18001d678  js      short loc_18001D691
0x18001d67a  lea     rcx, [rbp+57h+var_98]; int *
0x18001d67e  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d683  mov     r8, rax
0x18001d686  lea     rcx, [rbp+57h+var_94]; enum AppAndBrowserControlLevel *
0x18001d68a  call    ?GetControlLevelMapping@@YAPEBGPEAW4AppAndBrowserControlLevel@@@Z; GetControlLevelMapping(AppAndBrowserControlLevel *)
0x18001d68f  jmp     short loc_18001D6A0
0x18001d691  xor     ecx, ecx; int *
0x18001d693  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d698  mov     r8, rax
0x18001d69b  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d6a0  mov     [rbp+57h+var_70], rax
0x18001d6a4  mov     [rbp+57h+var_68], r8
0x18001d6a8  mov     rax, [rbx]
0x18001d6ab  lea     r8, [rbp+57h+var_98]
0x18001d6af  lea     rdx, [rbp+57h+var_94]
0x18001d6b3  mov     rcx, rbx
0x18001d6b6  mov     rax, [rax+38h]
0x18001d6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6bf  test    eax, eax
0x18001d6c1  js      short loc_18001D6D2
0x18001d6c3  lea     rcx, [rbp+57h+var_98]; int *
0x18001d6c7  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d6cc  lea     rcx, [rbp+57h+var_94]
0x18001d6d0  jmp     short loc_18001D712
0x18001d6d2  xor     ecx, ecx; int *
0x18001d6d4  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d6d9  mov     r8, rax
0x18001d6dc  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d6e1  jmp     short loc_18001D71A
0x18001d6e3  xor     ecx, ecx; enum AppAndBrowserControlLevel *
0x18001d6e5  call    ?GetControlLevelMapping@@YAPEBGPEAW4AppAndBrowserControlLevel@@@Z; GetControlLevelMapping(AppAndBrowserControlLevel *)
0x18001d6ea  mov     [rbp+57h+var_80], rax
0x18001d6ee  xor     ecx, ecx; int *
0x18001d6f0  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d6f5  mov     [rbp+57h+var_78], rax
0x18001d6f9  call    ?GetControlLevelMapping@@YAPEBGPEAW4AppAndBrowserControlLevel@@@Z; GetControlLevelMapping(AppAndBrowserControlLevel *)
0x18001d6fe  mov     [rbp+57h+var_70], rax
0x18001d702  xor     ecx, ecx; int *
0x18001d704  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d709  mov     [rbp+57h+var_68], rax
0x18001d70d  call    ?GetOnOffMapping@@YAPEBGPEAH@Z; GetOnOffMapping(int *)
0x18001d712  mov     r8, rax
0x18001d715  call    ?GetControlLevelMapping@@YAPEBGPEAW4AppAndBrowserControlLevel@@@Z; GetControlLevelMapping(AppAndBrowserControlLevel *)
0x18001d71a  mov     [rbp+57h+var_60], rax
0x18001d71e  mov     [rbp+57h+var_58], r8
0x18001d722  mov     [rbp+57h+var_38], 0
0x18001d72a  mov     r9d, 1Bh; unsigned int
0x18001d730  lea     r8d, [r9+1]; unsigned int
0x18001d734  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001d73b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001d73f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d744  lea     r8, [rbp+57h+var_90]
0x18001d748  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001d74f  mov     rcx, [rbp+57h+var_38]
0x18001d753  call    cs:__imp_RoGetActivationFactory
0x18001d759  mov     ebx, eax
0x18001d75b  test    eax, eax
0x18001d75d  jns     short loc_18001D785
0x18001d75f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d766  jz      loc_18001DBE7
0x18001d76c  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001d773  mov     [rsp+0D0h+var_A8], rax
0x18001d778  mov     [rsp+0D0h+var_B0], 451h
0x18001d780  jmp     loc_18001DBD7
0x18001d785  mov     rdi, [rbp+57h+var_90]
0x18001d789  mov     rax, [rdi]
0x18001d78c  mov     rbx, [rax+50h]
0x18001d790  lea     rcx, [rbp+57h+var_A0]
0x18001d794  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d799  lea     rdx, [rbp+57h+var_80]
0x18001d79d  lea     rcx, [rbp+57h+hstringHeader]
0x18001d7a1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d7a6  nop
0x18001d7a7  lea     r8, [rbp+57h+var_A0]
0x18001d7ab  mov     rdx, [rax+18h]
0x18001d7af  mov     rcx, rdi
0x18001d7b2  mov     rax, rbx
0x18001d7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ba  mov     ebx, eax
0x18001d7bc  test    eax, eax
0x18001d7be  jns     short loc_18001D7E6
0x18001d7c0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d7c7  jz      loc_18001DBE7
0x18001d7cd  lea     rax, aChrPjsonvalues_46; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001d7d4  mov     [rsp+0D0h+var_A8], rax
0x18001d7d9  mov     [rsp+0D0h+var_B0], 452h
0x18001d7e1  jmp     loc_18001DBD7
0x18001d7e6  mov     rax, [rsi]
0x18001d7e9  mov     rdi, [rax+38h]
0x18001d7ed  mov     rbx, [rbp+57h+var_A0]
0x18001d7f1  lea     rdx, off_18002B670; "AppInstallRule"
0x18001d7f8  lea     rcx, [rbp+57h+hstringHeader]
0x18001d7fc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d801  nop
0x18001d802  mov     r8, rbx
0x18001d805  mov     rdx, [rax+18h]
0x18001d809  mov     rcx, rsi
0x18001d80c  mov     rax, rdi
0x18001d80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d814  mov     ebx, eax
0x18001d816  test    eax, eax
0x18001d818  jns     short loc_18001D840
0x18001d81a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d821  jz      loc_18001DBE7
0x18001d827  lea     rax, aChrPprotection_6; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001d82e  mov     [rsp+0D0h+var_A8], rax
0x18001d833  mov     [rsp+0D0h+var_B0], 453h
0x18001d83b  jmp     loc_18001DBD7
0x18001d840  mov     rdi, [rbp+57h+var_90]
0x18001d844  mov     rax, [rdi]
0x18001d847  mov     rbx, [rax+50h]
0x18001d84b  lea     rcx, [rbp+57h+var_A0]
0x18001d84f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d854  lea     rdx, [rbp+57h+var_78]
0x18001d858  lea     rcx, [rbp+57h+hstringHeader]
0x18001d85c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d861  nop
0x18001d862  lea     r8, [rbp+57h+var_A0]
0x18001d866  mov     rdx, [rax+18h]
0x18001d86a  mov     rcx, rdi
0x18001d86d  mov     rax, rbx
0x18001d870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d875  mov     ebx, eax
0x18001d877  test    eax, eax
0x18001d879  jns     short loc_18001D8A1
0x18001d87b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d882  jz      loc_18001DBE7
0x18001d888  lea     rax, aChrPjsonvalues_9; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001d88f  mov     [rsp+0D0h+var_A8], rax
0x18001d894  mov     [rsp+0D0h+var_B0], 454h
0x18001d89c  jmp     loc_18001DBD7
0x18001d8a1  mov     rax, [rsi]
0x18001d8a4  mov     rdi, [rax+38h]
0x18001d8a8  mov     rbx, [rbp+57h+var_A0]
0x18001d8ac  lea     rdx, off_18002B668; "AppInstallRuleControlledByPolicy"
0x18001d8b3  lea     rcx, [rbp+57h+hstringHeader]
0x18001d8b7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d8bc  nop
0x18001d8bd  mov     r8, rbx
0x18001d8c0  mov     rdx, [rax+18h]
0x18001d8c4  mov     rcx, rsi
0x18001d8c7  mov     rax, rdi
0x18001d8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8cf  mov     ebx, eax
0x18001d8d1  test    eax, eax
0x18001d8d3  jns     short loc_18001D8FB
0x18001d8d5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d8dc  jz      loc_18001DBE7
0x18001d8e2  lea     rax, aChrPprotection_1; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001d8e9  mov     [rsp+0D0h+var_A8], rax
0x18001d8ee  mov     [rsp+0D0h+var_B0], 455h
0x18001d8f6  jmp     loc_18001DBD7
0x18001d8fb  mov     rdi, [rbp+57h+var_90]
0x18001d8ff  mov     rax, [rdi]
0x18001d902  mov     rbx, [rax+50h]
0x18001d906  lea     rcx, [rbp+57h+var_A0]
0x18001d90a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d90f  lea     rdx, [rbp+57h+var_70]
0x18001d913  lea     rcx, [rbp+57h+hstringHeader]
0x18001d917  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d91c  nop
0x18001d91d  lea     r8, [rbp+57h+var_A0]
0x18001d921  mov     rdx, [rax+18h]
0x18001d925  mov     rcx, rdi
0x18001d928  mov     rax, rbx
0x18001d92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d930  mov     ebx, eax
0x18001d932  test    eax, eax
0x18001d934  jns     short loc_18001D95C
0x18001d936  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d93d  jz      loc_18001DBE7
0x18001d943  lea     rax, aChrPjsonvalues_20; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001d94a  mov     [rsp+0D0h+var_A8], rax
0x18001d94f  mov     [rsp+0D0h+var_B0], 456h
0x18001d957  jmp     loc_18001DBD7
0x18001d95c  mov     rax, [rsi]
0x18001d95f  mov     rdi, [rax+38h]
0x18001d963  mov     rbx, [rbp+57h+var_A0]
0x18001d967  lea     rdx, off_18002B660; "BrowserSmartScreen"
0x18001d96e  lea     rcx, [rbp+57h+hstringHeader]
0x18001d972  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d977  nop
0x18001d978  mov     r8, rbx
0x18001d97b  mov     rdx, [rax+18h]
0x18001d97f  mov     rcx, rsi
0x18001d982  mov     rax, rdi
0x18001d985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d98a  mov     ebx, eax
0x18001d98c  test    eax, eax
0x18001d98e  jns     short loc_18001D9B6
0x18001d990  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d997  jz      loc_18001DBE7
0x18001d99d  lea     rax, aChrPprotection_13; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001d9a4  mov     [rsp+0D0h+var_A8], rax
0x18001d9a9  mov     [rsp+0D0h+var_B0], 457h
0x18001d9b1  jmp     loc_18001DBD7
0x18001d9b6  mov     rdi, [rbp+57h+var_90]
0x18001d9ba  mov     rax, [rdi]
0x18001d9bd  mov     rbx, [rax+50h]
0x18001d9c1  lea     rcx, [rbp+57h+var_A0]
0x18001d9c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d9ca  lea     rdx, [rbp+57h+var_68]
0x18001d9ce  lea     rcx, [rbp+57h+hstringHeader]
0x18001d9d2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d9d7  nop
0x18001d9d8  lea     r8, [rbp+57h+var_A0]
0x18001d9dc  mov     rdx, [rax+18h]
0x18001d9e0  mov     rcx, rdi
0x18001d9e3  mov     rax, rbx
0x18001d9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9eb  mov     ebx, eax
0x18001d9ed  test    eax, eax
0x18001d9ef  jns     short loc_18001DA17
0x18001d9f1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001d9f8  jz      loc_18001DBE7
0x18001d9fe  lea     rax, aChrPjsonvalues_47; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001da05  mov     [rsp+0D0h+var_A8], rax
0x18001da0a  mov     [rsp+0D0h+var_B0], 458h
0x18001da12  jmp     loc_18001DBD7
0x18001da17  mov     rax, [rsi]
0x18001da1a  mov     rdi, [rax+38h]
0x18001da1e  mov     rbx, [rbp+57h+var_A0]
0x18001da22  lea     rdx, off_18002B658; "BrowserSmartScreenControlledByPolicy"
0x18001da29  lea     rcx, [rbp+57h+hstringHeader]
0x18001da2d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001da32  nop
0x18001da33  mov     r8, rbx
0x18001da36  mov     rdx, [rax+18h]
0x18001da3a  mov     rcx, rsi
0x18001da3d  mov     rax, rdi
0x18001da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da45  mov     ebx, eax
0x18001da47  test    eax, eax
0x18001da49  jns     short loc_18001DA71
0x18001da4b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001da52  jz      loc_18001DBE7
0x18001da58  lea     rax, aChrPprotection_2; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001da5f  mov     [rsp+0D0h+var_A8], rax
0x18001da64  mov     [rsp+0D0h+var_B0], 459h
0x18001da6c  jmp     loc_18001DBD7
0x18001da71  mov     rdi, [rbp+57h+var_90]
0x18001da75  mov     rax, [rdi]
0x18001da78  mov     rbx, [rax+50h]
  ... truncated ...
```
