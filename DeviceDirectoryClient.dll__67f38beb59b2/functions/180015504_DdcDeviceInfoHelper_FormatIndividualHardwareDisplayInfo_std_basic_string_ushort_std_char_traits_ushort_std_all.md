# DdcDeviceInfoHelper::FormatIndividualHardwareDisplayInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Data::Json::IJsonValue * *)

- ea: `0x180015504`
- end: `0x180015a46`
- name: `?FormatIndividualHardwareDisplayInfo@DdcDeviceInfoHelper@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `1346`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015120`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800139c8`
- `0x180013b38`
- `0x180015504`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800155fc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800155fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800159fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800159fa`

## string_xrefs

- `0x1800155dd`: `Windows.Data.Json.JsonValue`
- `0x180015573`: `Windows.Data.Json.JsonObject`
- `0x1800155b8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180015693`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180015615`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x1800155a4`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18001567f`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceId.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800156ec`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_ID).Get(), pJsonValue.Get()))`
- `0x180015756`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceName.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800157b4`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_NAME).Get(), pJsonValue.Get()))`
- `0x180015821`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceDescription.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001587f`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_DESCRIPTION).Get(), pJsonValue.Get()))`
- `0x1800158ed`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrMemory.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180015947`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_MEMORY).Get(), pJsonValue.Get()))`
- `0x18001597c`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::FormatIndividualHardwareDisplayInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rdi
  int v9; // edx
  int v10; // ecx
  int ActivationFactory; // ebx
  int v12; // edx
  int v13; // ecx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, PVOID, __int64 *); // rbx
  char v16; // r8
  HSTRING_HEADER *v17; // rax
  int v18; // edx
  int v19; // ecx
  char v20; // r8
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64); // rdi
  __int64 v23; // rbx
  HSTRING_HEADER *v24; // rax
  int v25; // edx
  int v26; // ecx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, PVOID, __int64 *); // rbx
  char v29; // r8
  HSTRING_HEADER *v30; // rax
  int v31; // edx
  int v32; // ecx
  char v33; // r8
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64); // rdi
  __int64 v36; // rbx
  HSTRING_HEADER *v37; // rax
  int v38; // edx
  int v39; // ecx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, PVOID, __int64 *); // rbx
  char v42; // r8
  HSTRING_HEADER *v43; // rax
  int v44; // edx
  int v45; // ecx
  char v46; // r8
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v48)(_QWORD, GUID *, __int64); // rdi
  __int64 v49; // rbx
  HSTRING_HEADER *v50; // rax
  int v51; // edx
  int v52; // ecx
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, PVOID, __int64 *); // rbx
  char v55; // r8
  HSTRING_HEADER *v56; // rax
  int v57; // edx
  int v58; // ecx
  char v59; // r8
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v61)(_QWORD, GUID *, __int64); // rdi
  __int64 v62; // rbx
  HSTRING_HEADER *v63; // rax
  int v64; // edx
  int v65; // ecx
  int v66; // edx
  int v67; // ecx
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64); // rcx
  __int64 v73; // [rsp+38h] [rbp-69h] BYREF
  __int64 (__fastcall ***v74)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-61h] BYREF
  __int64 v75; // [rsp+48h] [rbp-59h] BYREF
  const WCHAR *v76; // [rsp+50h] [rbp-51h] BYREF
  _QWORD v77[6]; // [rsp+58h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-19h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-1h]

  v5 = a4;
  v77[2] = a1;
  v77[3] = a2;
  v77[4] = a3;
  v77[5] = a4;
  v77[1] = 0;
  v74 = 0;
  v77[0] = 0;
  v73 = 0;
  v75 = 0;
  v79 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v79, &v74);
  if ( ActivationFactory >= 0 )
  {
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonValue",
      0x1Cu,
      0x1Bu);
    ActivationFactory = RoGetActivationFactory(v79, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v75);
    if ( ActivationFactory >= 0 )
    {
      v14 = v75;
      v15 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v75 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
      v76 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v76, v16);
      ActivationFactory = v15(v14, v17[1].Reserved.Reserved1, &v73);
      if ( ActivationFactory >= 0 )
      {
        v21 = v74;
        v22 = (*v74)[7];
        v23 = v73;
        v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_18002B550,
                v20);
        ActivationFactory = v22(v21, (GUID *)v24[1].Reserved.Reserved1, v23);
        if ( ActivationFactory >= 0 )
        {
          v27 = v75;
          v28 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v75 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
          v76 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v76, v29);
          ActivationFactory = v28(v27, v30[1].Reserved.Reserved1, &v73);
          if ( ActivationFactory >= 0 )
          {
            v34 = v74;
            v35 = (*v74)[7];
            v36 = v73;
            v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_18002B548,
                    v33);
            ActivationFactory = v35(v34, (GUID *)v37[1].Reserved.Reserved1, v36);
            if ( ActivationFactory >= 0 )
            {
              v40 = v75;
              v41 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v75 + 80LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
              v76 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
              v43 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v76, v42);
              ActivationFactory = v41(v40, v43[1].Reserved.Reserved1, &v73);
              if ( ActivationFactory >= 0 )
              {
                v47 = v74;
                v48 = (*v74)[7];
                v49 = v73;
                v50 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_18002B540,
                        v46);
                ActivationFactory = v48(v47, (GUID *)v50[1].Reserved.Reserved1, v49);
                if ( ActivationFactory >= 0 )
                {
                  v53 = v75;
                  v54 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v75 + 80LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
                  v76 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                  v56 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v76, v55);
                  ActivationFactory = v54(v53, v56[1].Reserved.Reserved1, &v73);
                  if ( ActivationFactory >= 0 )
                  {
                    v60 = v74;
                    v61 = (*v74)[7];
                    v62 = v73;
                    v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &hstringHeader,
                            (const WCHAR **)off_18002B538,
                            v59);
                    ActivationFactory = v61(v60, (GUID *)v63[1].Reserved.Reserved1, v62);
                    if ( ActivationFactory >= 0 )
                    {
                      ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                            &v74,
                                            (__int64)v77);
                      if ( ActivationFactory >= 0 )
                      {
                        v68 = v77[0];
                        v77[0] = 0;
                        *a5 = v68;
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v67,
                          v66,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                          31,
                          "CHR(pJsonObject.As(&pJsonObjectAsValue))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v65,
                        v64,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                        29,
                        "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_MEMORY).Get(), pJsonValue.Get()))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v58,
                      v57,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                      28,
                      "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrMemory.c_str()).Get(), pJsonValue.Re"
                      "leaseAndGetAddressOf()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v52,
                    v51,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                    25,
                    "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_DESCRIPTION).Get(), pJsonValue.Get()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v45,
                  v44,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                  24,
                  "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceDescription.c_str()).Get(), pJsonV"
                  "alue.ReleaseAndGetAddressOf()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v39,
                v38,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                21,
                "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_NAME).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v32,
              v31,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              20,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceName.c_str()).Get(), pJsonValue.Releas"
              "eAndGetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v26,
            v25,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            17,
            "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_DISPLAY_ID).Get(), pJsonValue.Get()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v19,
          v18,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          16,
          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wstrDeviceId.c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
      }
      v5 = a4;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v13,
        v12,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        13,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      12,
      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))");
  }
  v69 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v77);
  v70 = v74;
  if ( v74 )
  {
    v74 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v70)[2])(v70);
  }
  WindowsDeleteString(0);
  std::wstring::_Tidy_deallocate(a1);
  std::wstring::_Tidy_deallocate(a2);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(v5);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180015504  push    rbp
0x180015506  push    rbx
0x180015507  push    rsi
0x180015508  push    rdi
0x180015509  push    r12
0x18001550b  push    r13
0x18001550d  push    r14
0x18001550f  push    r15
0x180015511  lea     rbp, [rsp-17h]
0x180015516  sub     rsp, 0B8h
0x18001551d  mov     rax, cs:__security_cookie
0x180015524  xor     rax, rsp
0x180015527  mov     [rbp+4Fh+var_48], rax
0x18001552b  mov     rdi, r9
0x18001552e  mov     [rbp+4Fh+var_C0], r9
0x180015532  mov     r13, r8
0x180015535  mov     r12, rdx
0x180015538  mov     r15, rcx
0x18001553b  mov     [rbp+4Fh+var_88], rcx
0x18001553f  mov     [rbp+4Fh+var_80], rdx
0x180015543  mov     [rbp+4Fh+var_78], r8
0x180015547  mov     [rbp+4Fh+var_70], r9
0x18001554b  mov     r14, [rbp+4Fh+arg_20]
0x18001554f  xor     eax, eax
0x180015551  mov     [rbp+4Fh+var_90], rax
0x180015555  mov     [rbp+4Fh+var_B0], rax
0x180015559  mov     [rbp+4Fh+var_98], rax
0x18001555d  mov     [rbp+4Fh+var_B8], rax
0x180015561  mov     [rbp+4Fh+var_A8], rax
0x180015565  mov     [rbp+4Fh+var_50], rax
0x180015569  lea     esi, [rax+1Ch]
0x18001556c  mov     r9d, esi; unsigned int
0x18001556f  lea     r8d, [rax+1Dh]; unsigned int
0x180015573  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001557a  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18001557e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015583  nop
0x180015584  lea     rdx, [rbp+4Fh+var_B0]
0x180015588  mov     rcx, [rbp+4Fh+var_50]
0x18001558c  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180015591  mov     ebx, eax
0x180015593  test    eax, eax
0x180015595  jns     short loc_1800155CC
0x180015597  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001559e  jz      loc_1800159A8
0x1800155a4  lea     rax, aChrActivateins_5; "CHR(ActivateInstance(HStringReference(R"...
0x1800155ab  mov     [rsp+0F0h+var_C8], rax
0x1800155b0  mov     [rsp+0F0h+var_D0], 30Ch
0x1800155b8  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800155bf  mov     r8d, ebx
0x1800155c2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800155c7  jmp     loc_1800159A8
0x1800155cc  mov     [rbp+4Fh+var_50], 0
0x1800155d4  mov     r9d, 1Bh; unsigned int
0x1800155da  mov     r8d, esi; unsigned int
0x1800155dd  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800155e4  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800155e8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800155ed  lea     r8, [rbp+4Fh+var_A8]
0x1800155f1  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1800155f8  mov     rcx, [rbp+4Fh+var_50]
0x1800155fc  call    cs:__imp_RoGetActivationFactory
0x180015602  mov     ebx, eax
0x180015604  test    eax, eax
0x180015606  jns     short loc_18001562B
0x180015608  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001560f  jz      loc_1800159A8
0x180015615  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001561c  mov     [rsp+0F0h+var_C8], rax
0x180015621  mov     [rsp+0F0h+var_D0], 30Dh
0x180015629  jmp     short loc_1800155B8
0x18001562b  mov     rdi, [rbp+4Fh+var_A8]
0x18001562f  mov     rax, [rdi]
0x180015632  mov     rbx, [rax+50h]
0x180015636  lea     rcx, [rbp+4Fh+var_B8]
0x18001563a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001563f  mov     rcx, r15
0x180015642  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015647  mov     [rbp+4Fh+var_A0], rax
0x18001564b  lea     rdx, [rbp+4Fh+var_A0]
0x18001564f  lea     rcx, [rbp+4Fh+hstringHeader]
0x180015653  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015658  nop
0x180015659  lea     r8, [rbp+4Fh+var_B8]
0x18001565d  mov     rdx, [rax+18h]
0x180015661  mov     rcx, rdi
0x180015664  mov     rax, rbx
0x180015667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001566c  mov     ebx, eax
0x18001566e  test    eax, eax
0x180015670  jns     short loc_1800156A7
0x180015672  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015679  jz      loc_1800159A4
0x18001567f  lea     rax, aChrPjsonvalues_19; "CHR(pJsonValueStatics->CreateStringValu"...
0x180015686  mov     [rsp+0F0h+var_C8], rax
0x18001568b  mov     [rsp+0F0h+var_D0], 310h
0x180015693  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001569a  mov     r8d, ebx
0x18001569d  call    McTemplateU0dsqs_EventWriteTransfer
0x1800156a2  jmp     loc_1800159A4
0x1800156a7  mov     rsi, [rbp+4Fh+var_B0]
0x1800156ab  mov     rax, [rsi]
0x1800156ae  mov     rdi, [rax+38h]
0x1800156b2  mov     rbx, [rbp+4Fh+var_B8]
0x1800156b6  lea     rdx, off_18002B550; "GraphicCardId"
0x1800156bd  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800156c1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800156c6  nop
0x1800156c7  mov     r8, rbx
0x1800156ca  mov     rdx, [rax+18h]
0x1800156ce  mov     rcx, rsi
0x1800156d1  mov     rax, rdi
0x1800156d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d9  mov     ebx, eax
0x1800156db  test    eax, eax
0x1800156dd  jns     short loc_180015702
0x1800156df  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800156e6  jz      loc_1800159A4
0x1800156ec  lea     rax, aChrPjsonobject_29; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800156f3  mov     [rsp+0F0h+var_C8], rax
0x1800156f8  mov     [rsp+0F0h+var_D0], 311h
0x180015700  jmp     short loc_180015693
0x180015702  mov     rdi, [rbp+4Fh+var_A8]
0x180015706  mov     rax, [rdi]
0x180015709  mov     rbx, [rax+50h]
0x18001570d  lea     rcx, [rbp+4Fh+var_B8]
0x180015711  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015716  mov     rcx, r12
0x180015719  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001571e  mov     [rbp+4Fh+var_A0], rax
0x180015722  lea     rdx, [rbp+4Fh+var_A0]
0x180015726  lea     rcx, [rbp+4Fh+hstringHeader]
0x18001572a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001572f  nop
0x180015730  lea     r8, [rbp+4Fh+var_B8]
0x180015734  mov     rdx, [rax+18h]
0x180015738  mov     rcx, rdi
0x18001573b  mov     rax, rbx
0x18001573e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015743  mov     ebx, eax
0x180015745  test    eax, eax
0x180015747  jns     short loc_18001576F
0x180015749  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015750  jz      loc_1800159A4
0x180015756  lea     rax, aChrPjsonvalues_34; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001575d  mov     [rsp+0F0h+var_C8], rax
0x180015762  mov     [rsp+0F0h+var_D0], 314h
0x18001576a  jmp     loc_180015693
0x18001576f  mov     rsi, [rbp+4Fh+var_B0]
0x180015773  mov     rax, [rsi]
0x180015776  mov     rdi, [rax+38h]
0x18001577a  mov     rbx, [rbp+4Fh+var_B8]
0x18001577e  lea     rdx, off_18002B548; "DisplayName"
0x180015785  lea     rcx, [rbp+4Fh+hstringHeader]
0x180015789  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001578e  nop
0x18001578f  mov     r8, rbx
0x180015792  mov     rdx, [rax+18h]
0x180015796  mov     rcx, rsi
0x180015799  mov     rax, rdi
0x18001579c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a1  mov     ebx, eax
0x1800157a3  test    eax, eax
0x1800157a5  jns     short loc_1800157CD
0x1800157a7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800157ae  jz      loc_1800159A4
0x1800157b4  lea     rax, aChrPjsonobject_32; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800157bb  mov     [rsp+0F0h+var_C8], rax
0x1800157c0  mov     [rsp+0F0h+var_D0], 315h
0x1800157c8  jmp     loc_180015693
0x1800157cd  mov     rdi, [rbp+4Fh+var_A8]
0x1800157d1  mov     rax, [rdi]
0x1800157d4  mov     rbx, [rax+50h]
0x1800157d8  lea     rcx, [rbp+4Fh+var_B8]
0x1800157dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800157e1  mov     rcx, r13
0x1800157e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800157e9  mov     [rbp+4Fh+var_A0], rax
0x1800157ed  lea     rdx, [rbp+4Fh+var_A0]
0x1800157f1  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800157f5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800157fa  nop
0x1800157fb  lea     r8, [rbp+4Fh+var_B8]
0x1800157ff  mov     rdx, [rax+18h]
0x180015803  mov     rcx, rdi
0x180015806  mov     rax, rbx
0x180015809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580e  mov     ebx, eax
0x180015810  test    eax, eax
0x180015812  jns     short loc_18001583A
0x180015814  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001581b  jz      loc_1800159A4
0x180015821  lea     rax, aChrPjsonvalues_3; "CHR(pJsonValueStatics->CreateStringValu"...
0x180015828  mov     [rsp+0F0h+var_C8], rax
0x18001582d  mov     [rsp+0F0h+var_D0], 318h
0x180015835  jmp     loc_180015693
0x18001583a  mov     rsi, [rbp+4Fh+var_B0]
0x18001583e  mov     rax, [rsi]
0x180015841  mov     rdi, [rax+38h]
0x180015845  mov     rbx, [rbp+4Fh+var_B8]
0x180015849  lea     rdx, off_18002B540; "Description"
0x180015850  lea     rcx, [rbp+4Fh+hstringHeader]
0x180015854  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015859  nop
0x18001585a  mov     r8, rbx
0x18001585d  mov     rdx, [rax+18h]
0x180015861  mov     rcx, rsi
0x180015864  mov     rax, rdi
0x180015867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001586c  mov     ebx, eax
0x18001586e  test    eax, eax
0x180015870  jns     short loc_180015898
0x180015872  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015879  jz      loc_1800159A4
0x18001587f  lea     rax, aChrPjsonobject_5; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180015886  mov     [rsp+0F0h+var_C8], rax
0x18001588b  mov     [rsp+0F0h+var_D0], 319h
0x180015893  jmp     loc_180015693
0x180015898  mov     rdi, [rbp+4Fh+var_A8]
0x18001589c  mov     rax, [rdi]
0x18001589f  mov     rbx, [rax+50h]
0x1800158a3  lea     rcx, [rbp+4Fh+var_B8]
0x1800158a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800158ac  mov     rcx, [rbp+4Fh+var_C0]
0x1800158b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800158b5  mov     [rbp+4Fh+var_A0], rax
0x1800158b9  lea     rdx, [rbp+4Fh+var_A0]
0x1800158bd  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800158c1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800158c6  nop
0x1800158c7  lea     r8, [rbp+4Fh+var_B8]
0x1800158cb  mov     rdx, [rax+18h]
0x1800158cf  mov     rcx, rdi
0x1800158d2  mov     rax, rbx
0x1800158d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158da  mov     ebx, eax
0x1800158dc  test    eax, eax
0x1800158de  jns     short loc_180015906
0x1800158e0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800158e7  jz      loc_1800159A4
0x1800158ed  lea     rax, aChrPjsonvalues_75; "CHR(pJsonValueStatics->CreateStringValu"...
0x1800158f4  mov     [rsp+0F0h+var_C8], rax
0x1800158f9  mov     [rsp+0F0h+var_D0], 31Ch
0x180015901  jmp     loc_180015693
0x180015906  mov     rsi, [rbp+4Fh+var_B0]
0x18001590a  mov     rax, [rsi]
0x18001590d  mov     rdi, [rax+38h]
0x180015911  mov     rbx, [rbp+4Fh+var_B8]
0x180015915  lea     rdx, off_18002B538; "InstalledMemory"
0x18001591c  lea     rcx, [rbp+4Fh+hstringHeader]
0x180015920  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015925  nop
0x180015926  mov     r8, rbx
0x180015929  mov     rdx, [rax+18h]
0x18001592d  mov     rcx, rsi
0x180015930  mov     rax, rdi
0x180015933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015938  mov     ebx, eax
0x18001593a  test    eax, eax
0x18001593c  jns     short loc_180015960
0x18001593e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015945  jz      short loc_1800159A4
0x180015947  lea     rax, aChrPjsonobject_6; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18001594e  mov     [rsp+0F0h+var_C8], rax
0x180015953  mov     [rsp+0F0h+var_D0], 31Dh
0x18001595b  jmp     loc_180015693
0x180015960  lea     rdx, [rbp+4Fh+var_98]
0x180015964  lea     rcx, [rbp+4Fh+var_B0]
0x180015968  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18001596d  mov     ebx, eax
0x18001596f  test    eax, eax
0x180015971  jns     short loc_180015995
0x180015973  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001597a  jz      short loc_1800159A4
0x18001597c  lea     rax, aChrPjsonobject_7; "CHR(pJsonObject.As(&pJsonObjectAsValue)"...
0x180015983  mov     [rsp+0F0h+var_C8], rax
0x180015988  mov     [rsp+0F0h+var_D0], 31Fh
0x180015990  jmp     loc_180015693
0x180015995  mov     rax, [rbp+4Fh+var_98]
0x180015999  mov     [rbp+4Fh+var_98], 0
0x1800159a1  mov     [r14], rax
0x1800159a4  mov     rdi, [rbp+4Fh+var_C0]
0x1800159a8  mov     rcx, [rbp+4Fh+var_A8]
0x1800159ac  test    rcx, rcx
0x1800159af  jz      short loc_1800159C6
0x1800159b1  mov     [rbp+4Fh+var_A8], 0
0x1800159b9  mov     rax, [rcx]
0x1800159bc  mov     rax, [rax+10h]
0x1800159c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c5  nop
0x1800159c6  lea     rcx, [rbp+4Fh+var_B8]
0x1800159ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800159cf  nop
0x1800159d0  lea     rcx, [rbp+4Fh+var_98]
0x1800159d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800159d9  nop
0x1800159da  mov     rcx, [rbp+4Fh+var_B0]
0x1800159de  test    rcx, rcx
0x1800159e1  jz      short loc_1800159F8
0x1800159e3  mov     [rbp+4Fh+var_B0], 0
  ... truncated ...
```
