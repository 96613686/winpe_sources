# VolInfo::Format(Windows::Data::Json::IJsonValue * *)

- ea: `0x180020d2c`
- end: `0x180021665`
- name: `?Format@VolInfo@@QEAAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `2361`
- prototype: `__int64 __fastcall(VolInfo *__hidden this, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002166c`

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
- `0x180014410`
- `0x18002099c`
- `0x180020d2c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e7e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020d7d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020dc9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020d7d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180020dc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800215ec`

## string_xrefs

- `0x180020e5f`: `Windows.Data.Json.JsonValue`
- `0x180020e08`: `Windows.Data.Json.JsonObject`
- `0x180020e97`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180020e39`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x1800215ba`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x180020daa`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdriveshelper.cpp`
- `0x180020d96`: `CHR(StringFromCLSID(this->StorageId, &pocGuidStorageId))`
- `0x180020de2`: `CHR(StringFromCLSID(this->BitLockerKeyId, &pocGuidBlKeyId))`
- `0x180020ef8`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pocGuidStorageId).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180020f56`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_ID).Get(), pJsonValue.Get()))`
- `0x180020faf`: `CHR(pJsonValueStatics->CreateNumberValue(this->Store, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002100d`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_TYPE).Get(), pJsonValue.Get()))`
- `0x180021068`: `CHR(pJsonValueStatics->CreateNumberValue(this->DeviceInstance, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800210c6`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DEVICE_INSTANCE).Get(), pJsonValue.Get()))`
- `0x180021127`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(this->Name).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180021185`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DEVICE_NAME).Get(), pJsonValue.Get()))`
- `0x180021211`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(to_wstring(this->FreeSpace).c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18002126f`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_FREE_SPACE).Get(), pJsonValue.Get()))`
- `0x1800212fb`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(to_wstring(this->TotalSize).c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180021359`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_TOTAL_SPACE).Get(), pJsonValue.Get()))`
- `0x1800213ba`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pocGuidBlKeyId).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180021418`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_KEYID).Get(), pJsonValue.Get()))`
- `0x180021474`: `CHR(pJsonValueStatics->CreateNumberValue(static_cast<double>(this->BitLockerState), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800214d2`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_STATE).Get(), pJsonValue.Get()))`
- `0x18002152b`: `CHR(pJsonValueStatics->CreateBooleanValue(!!(this->BitLockerCapable), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180021585`: `CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_CAPABLE).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall VolInfo::Format(VolInfo *this, struct Windows::Data::Json::IJsonValue **a2)
{
  int v4; // edx
  int v5; // ecx
  int ActivationFactory; // ebx
  int v7; // edx
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 *); // rbx
  char v15; // r8
  HSTRING_HEADER *v16; // rax
  int v17; // edx
  int v18; // ecx
  char v19; // r8
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64); // rdi
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
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v33)(_QWORD, GUID *, __int64); // rdi
  __int64 v34; // rbx
  HSTRING_HEADER *v35; // rax
  int v36; // edx
  int v37; // ecx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64 *); // rbx
  int v40; // edx
  int v41; // ecx
  char v42; // r8
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64); // rdi
  __int64 v45; // rbx
  HSTRING_HEADER *v46; // rax
  int v47; // edx
  int v48; // ecx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, _QWORD, __int64 *); // rbx
  __int64 v51; // rax
  int v52; // edx
  int v53; // ecx
  char v54; // r8
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v56)(_QWORD, GUID *, __int64); // rdi
  __int64 v57; // rbx
  HSTRING_HEADER *v58; // rax
  int v59; // edx
  int v60; // ecx
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, PVOID, __int64 *); // rbx
  char v63; // r8
  HSTRING_HEADER *v64; // rax
  int v65; // edx
  int v66; // ecx
  char v67; // r8
  __int64 (__fastcall ***v68)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v69)(_QWORD, GUID *, __int64); // rdi
  __int64 v70; // rbx
  HSTRING_HEADER *v71; // rax
  int v72; // edx
  int v73; // ecx
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, PVOID, __int64 *); // rbx
  char v76; // r8
  HSTRING_HEADER *v77; // rax
  int v78; // edx
  int v79; // ecx
  char v80; // r8
  __int64 (__fastcall ***v81)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v82)(_QWORD, GUID *, __int64); // rdi
  __int64 v83; // rbx
  HSTRING_HEADER *v84; // rax
  int v85; // edx
  int v86; // ecx
  __int64 v87; // rdi
  __int64 (__fastcall *v88)(__int64, PVOID, __int64 *); // rbx
  char v89; // r8
  HSTRING_HEADER *v90; // rax
  int v91; // edx
  int v92; // ecx
  char v93; // r8
  __int64 (__fastcall ***v94)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v95)(_QWORD, GUID *, __int64); // rdi
  __int64 v96; // rbx
  HSTRING_HEADER *v97; // rax
  int v98; // edx
  int v99; // ecx
  __int64 v100; // rdi
  __int64 (__fastcall *v101)(__int64, __int64, __int64 *); // rbx
  __int64 v102; // rdx
  int v103; // edx
  int v104; // ecx
  char v105; // r8
  __int64 (__fastcall ***v106)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v107)(_QWORD, GUID *, __int64); // rdi
  __int64 v108; // rbx
  HSTRING_HEADER *v109; // rax
  int v110; // edx
  int v111; // ecx
  __int64 v112; // rdi
  __int64 (__fastcall *v113)(__int64, __int64, __int64 *); // rbx
  __int64 v114; // rdx
  int v115; // edx
  int v116; // ecx
  char v117; // r8
  __int64 (__fastcall ***v118)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v119)(_QWORD, GUID *, __int64); // rdi
  __int64 v120; // rbx
  HSTRING_HEADER *v121; // rax
  int v122; // edx
  int v123; // ecx
  int v124; // edx
  int v125; // ecx
  struct Windows::Data::Json::IJsonValue *v126; // rax
  __int64 v127; // rcx
  __int64 (__fastcall ***v128)(_QWORD, GUID *, __int64); // rcx
  __int64 v130; // [rsp+30h] [rbp-49h] BYREF
  __int64 (__fastcall ***v131)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-41h] BYREF
  __int64 v132; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::Data::Json::IJsonValue *v133; // [rsp+48h] [rbp-31h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-29h] BYREF
  LPOLESTR v135; // [rsp+58h] [rbp-21h] BYREF
  const WCHAR *v136; // [rsp+60h] [rbp-19h] BYREF
  HSTRING_HEADER v137; // [rsp+68h] [rbp-11h] BYREF
  __int64 v138; // [rsp+80h] [rbp+7h]
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v140; // [rsp+A0h] [rbp+27h]

  v131 = 0;
  v133 = 0;
  v130 = 0;
  v132 = 0;
  lpsz = 0;
  v135 = 0;
  ActivationFactory = StringFromCLSID((const IID *const)this, &lpsz);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = StringFromCLSID((const IID *const)((char *)this + 568), &v135);
    if ( ActivationFactory >= 0 )
    {
      v140 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v140, &v131);
      if ( ActivationFactory >= 0 )
      {
        v140 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        ActivationFactory = RoGetActivationFactory(v140, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v132);
        if ( ActivationFactory >= 0 )
        {
          v13 = v132;
          v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v132 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
          v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v137, (const WCHAR **)&lpsz, v15);
          ActivationFactory = v14(v13, v16[1].Reserved.Reserved1, &v130);
          if ( ActivationFactory >= 0 )
          {
            v20 = v131;
            v21 = (*v131)[7];
            v22 = v130;
            v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &v137,
                    (const WCHAR **)off_18002B738,
                    v19);
            ActivationFactory = v21(v20, (GUID *)v23[1].Reserved.Reserved1, v22);
            if ( ActivationFactory >= 0 )
            {
              v26 = v132;
              v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v132 + 72LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
              ActivationFactory = v27(v26, v28, &v130);
              if ( ActivationFactory >= 0 )
              {
                v32 = v131;
                v33 = (*v131)[7];
                v34 = v130;
                v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &v137,
                        (const WCHAR **)off_18002B730,
                        v31);
                ActivationFactory = v33(v32, (GUID *)v35[1].Reserved.Reserved1, v34);
                if ( ActivationFactory >= 0 )
                {
                  v38 = v132;
                  v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v132 + 72LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                  ActivationFactory = v39(v38, *((unsigned int *)this + 5), &v130);
                  if ( ActivationFactory >= 0 )
                  {
                    v43 = v131;
                    v44 = (*v131)[7];
                    v45 = v130;
                    v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &v137,
                            (const WCHAR **)off_18002B728,
                            v42);
                    ActivationFactory = v44(v43, (GUID *)v46[1].Reserved.Reserved1, v45);
                    if ( ActivationFactory >= 0 )
                    {
                      v49 = v132;
                      v50 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v132 + 80LL);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                      v51 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v137, (PCWSTR)this + 12);
                      ActivationFactory = v50(v49, *(_QWORD *)(v51 + 24), &v130);
                      if ( ActivationFactory >= 0 )
                      {
                        v55 = v131;
                        v56 = (*v131)[7];
                        v57 = v130;
                        v58 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                &v137,
                                (const WCHAR **)off_18002B720,
                                v54);
                        ActivationFactory = v56(v55, (GUID *)v58[1].Reserved.Reserved1, v57);
                        if ( ActivationFactory >= 0 )
                        {
                          v61 = v132;
                          v62 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v132 + 80LL);
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                          std::_Integral_to_string<unsigned short,unsigned __int64>(
                            &hstringHeader,
                            *((_QWORD *)this + 69));
                          v136 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                          v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v137, &v136, v63);
                          ActivationFactory = v62(v61, v64[1].Reserved.Reserved1, &v130);
                          v138 = 0;
                          std::wstring::_Tidy_deallocate((__int64)&hstringHeader);
                          if ( ActivationFactory >= 0 )
                          {
                            v68 = v131;
                            v69 = (*v131)[7];
                            v70 = v130;
                            v71 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                    &v137,
                                    (const WCHAR **)off_18002B718,
                                    v67);
                            ActivationFactory = v69(v68, (GUID *)v71[1].Reserved.Reserved1, v70);
                            if ( ActivationFactory >= 0 )
                            {
                              v74 = v132;
                              v75 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v132 + 80LL);
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                              std::_Integral_to_string<unsigned short,unsigned __int64>(
                                &hstringHeader,
                                *((_QWORD *)this + 68));
                              v136 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                              v77 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v137, &v136, v76);
                              ActivationFactory = v75(v74, v77[1].Reserved.Reserved1, &v130);
                              v138 = 0;
                              std::wstring::_Tidy_deallocate((__int64)&hstringHeader);
                              if ( ActivationFactory >= 0 )
                              {
                                v81 = v131;
                                v82 = (*v131)[7];
                                v83 = v130;
                                v84 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                        &v137,
                                        (const WCHAR **)off_18002B710,
                                        v80);
                                ActivationFactory = v82(v81, (GUID *)v84[1].Reserved.Reserved1, v83);
                                if ( ActivationFactory >= 0 )
                                {
                                  v87 = v132;
                                  v88 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v132 + 80LL);
                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                                  v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                          &v137,
                                          (const WCHAR **)&v135,
                                          v89);
                                  ActivationFactory = v88(v87, v90[1].Reserved.Reserved1, &v130);
                                  if ( ActivationFactory >= 0 )
                                  {
                                    v94 = v131;
                                    v95 = (*v131)[7];
                                    v96 = v130;
                                    v97 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                            &v137,
                                            (const WCHAR **)off_18002B6F8,
                                            v93);
                                    ActivationFactory = v95(v94, (GUID *)v97[1].Reserved.Reserved1, v96);
                                    if ( ActivationFactory >= 0 )
                                    {
                                      v100 = v132;
                                      v101 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v132 + 72LL);
                                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                                      ActivationFactory = v101(v100, v102, &v130);
                                      if ( ActivationFactory >= 0 )
                                      {
                                        v106 = v131;
                                        v107 = (*v131)[7];
                                        v108 = v130;
                                        v109 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                 &v137,
                                                 (const WCHAR **)off_18002B708,
                                                 v105);
                                        ActivationFactory = v107(v106, (GUID *)v109[1].Reserved.Reserved1, v108);
                                        if ( ActivationFactory >= 0 )
                                        {
                                          v112 = v132;
                                          v113 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v132 + 64LL);
                                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
                                          LOBYTE(v114) = *((_DWORD *)this + 141) != 0;
                                          ActivationFactory = v113(v112, v114, &v130);
                                          if ( ActivationFactory >= 0 )
                                          {
                                            v118 = v131;
                                            v119 = (*v131)[7];
                                            v120 = v130;
                                            v121 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                     &v137,
                                                     (const WCHAR **)off_18002B700,
                                                     v117);
                                            ActivationFactory = v119(v118, (GUID *)v121[1].Reserved.Reserved1, v120);
                                            if ( ActivationFactory >= 0 )
                                            {
                                              ActivationFactory = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                                                                    &v131,
                                                                    (__int64)&v133);
                                              if ( ActivationFactory >= 0 )
                                              {
                                                v126 = v133;
                                                v133 = 0;
                                                *a2 = v126;
                                              }
                                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                       & 1) != 0 )
                                              {
                                                McTemplateU0dsqs_EventWriteTransfer(
                                                  v125,
                                                  v124,
                                                  ActivationFactory,
                                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclien"
                                                                "t\\lib\\ddcdriveshelper.cpp",
                                                  176,
                                                  "CHR(pJsonObject.As(&pJsonObjectAsValue))");
                                              }
                                            }
                                            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                     & 1) != 0 )
                                            {
                                              McTemplateU0dsqs_EventWriteTransfer(
                                                v123,
                                                v122,
                                                ActivationFactory,
                                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\"
                                                              "lib\\ddcdriveshelper.cpp",
                                                174,
                                                "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_CAPABLE)"
                                                ".Get(), pJsonValue.Get()))");
                                            }
                                          }
                                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                   & 1) != 0 )
                                          {
                                            McTemplateU0dsqs_EventWriteTransfer(
                                              v116,
                                              v115,
                                              ActivationFactory,
                                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\l"
                                                            "ib\\ddcdriveshelper.cpp",
                                              173,
                                              "CHR(pJsonValueStatics->CreateBooleanValue(!!(this->BitLockerCapable), pJso"
                                              "nValue.ReleaseAndGetAddressOf()))");
                                          }
                                        }
                                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                 & 1) != 0 )
                                        {
                                          McTemplateU0dsqs_EventWriteTransfer(
                                            v111,
                                            v110,
                                            ActivationFactory,
                                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib"
                                                          "\\ddcdriveshelper.cpp",
                                            170,
                                            "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_STATE).Get()"
                                            ", pJsonValue.Get()))");
                                        }
                                      }
                                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                               & 1) != 0 )
                                      {
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v104,
                                          v103,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcdriveshelper.cpp",
                                          169,
                                          "CHR(pJsonValueStatics->CreateNumberValue(static_cast<double>(this->BitLockerSt"
                                          "ate), pJsonValue.ReleaseAndGetAddressOf()))");
                                      }
                                    }
                                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    {
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v99,
                                        v98,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\dd"
                                                      "cdriveshelper.cpp",
                                        166,
                                        "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_BL_KEYID).Get(), pJ"
                                        "sonValue.Get()))");
                                    }
                                  }
                                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  {
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v92,
                                      v91,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                                      165,
                                      "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pocGuidBlKeyId).Get(), p"
                                      "JsonValue.ReleaseAndGetAddressOf()))");
                                  }
                                }
                                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                {
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v86,
                                    v85,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                                    162,
                                    "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_TOTAL_SPACE).Get(), pJsonValue.Get()))");
                                }
                              }
                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                              {
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v79,
                                  v78,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                                  161,
                                  "CHR(pJsonValueStatics->CreateStringValue(HStringReference(to_wstring(this->TotalSize)."
                                  "c_str()).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                              }
                            }
                            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                            {
                              McTemplateU0dsqs_EventWriteTransfer(
                                v73,
                                v72,
                                ActivationFactory,
                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                                158,
                                "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_FREE_SPACE).Get(), pJsonValue.Get()))");
                            }
                          }
                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v66,
                              v65,
                              ActivationFactory,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                              157,
                              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(to_wstring(this->FreeSpace).c_st"
                              "r()).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v60,
                            v59,
                            ActivationFactory,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                            154,
                            "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DEVICE_NAME).Get(), pJsonValue.Get()))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v53,
                          v52,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                          153,
                          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(this->Name).Get(), pJsonValue.Releas"
                          "eAndGetAddressOf()))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v48,
                        v47,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                        150,
                        "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_DEVICE_INSTANCE).Get(), pJsonValue.Get()))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v41,
                      v40,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                      149,
                      "CHR(pJsonValueStatics->CreateNumberValue(this->DeviceInstance, pJsonValue.ReleaseAndGetAddressOf()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v37,
                    v36,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                    146,
                    "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_TYPE).Get(), pJsonValue.Get()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v30,
                  v29,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                  145,
                  "CHR(pJsonValueStatics->CreateNumberValue(this->Store, pJsonValue.ReleaseAndGetAddressOf()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v25,
                v24,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
                142,
                "CHR(pJsonObject->SetNamedValue(HStringReference(JSON_STORAGE_ID).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              v17,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
              141,
              "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pocGuidStorageId).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v12,
            v11,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
            138,
            "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics"
            ".GetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
          137,
          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
        135,
        "CHR(StringFromCLSID(this->BitLockerKeyId, &pocGuidBlKeyId))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
      134,
      "CHR(StringFromCLSID(this->StorageId, &pocGuidStorageId))");
  }
  CoTaskMemFree(lpsz);
  CoTaskMemFree(v135);
  v127 = v132;
  if ( v132 )
  {
    v132 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v130);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  v128 = v131;
  if ( v131 )
  {
    v131 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v128)[2])(v128);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180020d2c  mov     [rsp-8+arg_10], rbx
0x180020d31  mov     [rsp-8+arg_18], rsi
0x180020d36  push    rbp
0x180020d37  push    rdi
0x180020d38  push    r12
0x180020d3a  push    r14
0x180020d3c  push    r15
0x180020d3e  lea     rbp, [rsp-37h]
0x180020d43  sub     rsp, 0B0h
0x180020d4a  mov     rax, cs:__security_cookie
0x180020d51  xor     rax, rsp
0x180020d54  mov     [rbp+57h+var_28], rax
0x180020d58  mov     r15, rdx
0x180020d5b  mov     r14, rcx
0x180020d5e  xor     r12d, r12d
0x180020d61  mov     [rbp+57h+var_98], r12
0x180020d65  mov     [rbp+57h+var_88], r12
0x180020d69  mov     [rbp+57h+var_A0], r12
0x180020d6d  mov     [rbp+57h+var_90], r12
0x180020d71  mov     [rbp+57h+lpsz], r12
0x180020d75  mov     [rbp+57h+var_78], r12
0x180020d79  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180020d7d  call    cs:__imp_StringFromCLSID
0x180020d83  mov     ebx, eax
0x180020d85  test    eax, eax
0x180020d87  jns     short loc_180020DBE
0x180020d89  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020d90  jz      loc_1800215DE
0x180020d96  lea     rax, aChrStringfromc_0; "CHR(StringFromCLSID(this->StorageId, &p"...
0x180020d9d  mov     [rsp+0D0h+var_A8], rax
0x180020da2  mov     [rsp+0D0h+var_B0], 86h
0x180020daa  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180020db1  mov     r8d, ebx
0x180020db4  call    McTemplateU0dsqs_EventWriteTransfer
0x180020db9  jmp     loc_1800215DE
0x180020dbe  lea     rcx, [r14+238h]; rclsid
0x180020dc5  lea     rdx, [rbp+57h+var_78]; lplpsz
0x180020dc9  call    cs:__imp_StringFromCLSID
0x180020dcf  mov     ebx, eax
0x180020dd1  test    eax, eax
0x180020dd3  jns     short loc_180020DF8
0x180020dd5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020ddc  jz      loc_1800215DE
0x180020de2  lea     rax, aChrStringfromc_1; "CHR(StringFromCLSID(this->BitLockerKeyI"...
0x180020de9  mov     [rsp+0D0h+var_A8], rax
0x180020dee  mov     [rsp+0D0h+var_B0], 87h
0x180020df6  jmp     short loc_180020DAA
0x180020df8  mov     [rbp+57h+var_30], r12
0x180020dfc  mov     edi, 1Ch
0x180020e01  mov     r9d, edi; unsigned int
0x180020e04  lea     r8d, [rdi+1]; unsigned int
0x180020e08  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180020e0f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020e13  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020e18  nop
0x180020e19  lea     rdx, [rbp+57h+var_98]
0x180020e1d  mov     rcx, [rbp+57h+var_30]
0x180020e21  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180020e26  mov     ebx, eax
0x180020e28  test    eax, eax
0x180020e2a  jns     short loc_180020E52
0x180020e2c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020e33  jz      loc_1800215DE
0x180020e39  lea     rax, aChrActivateins_5; "CHR(ActivateInstance(HStringReference(R"...
0x180020e40  mov     [rsp+0D0h+var_A8], rax
0x180020e45  mov     [rsp+0D0h+var_B0], 89h
0x180020e4d  jmp     loc_180020DAA
0x180020e52  mov     [rbp+57h+var_30], r12
0x180020e56  mov     r9d, 1Bh; unsigned int
0x180020e5c  mov     r8d, edi; unsigned int
0x180020e5f  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180020e66  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020e6a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020e6f  lea     r8, [rbp+57h+var_90]
0x180020e73  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180020e7a  mov     rcx, [rbp+57h+var_30]
0x180020e7e  call    cs:__imp_RoGetActivationFactory
0x180020e84  mov     ebx, eax
0x180020e86  test    eax, eax
0x180020e88  jns     short loc_180020EB0
0x180020e8a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020e91  jz      loc_1800215DE
0x180020e97  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180020e9e  mov     [rsp+0D0h+var_A8], rax
0x180020ea3  mov     [rsp+0D0h+var_B0], 8Ah
0x180020eab  jmp     loc_180020DAA
0x180020eb0  mov     rdi, [rbp+57h+var_90]
0x180020eb4  mov     rax, [rdi]
0x180020eb7  mov     rbx, [rax+50h]
0x180020ebb  lea     rcx, [rbp+57h+var_A0]
0x180020ebf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020ec4  lea     rdx, [rbp+57h+lpsz]
0x180020ec8  lea     rcx, [rbp+57h+var_68]
0x180020ecc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020ed1  nop
0x180020ed2  lea     r8, [rbp+57h+var_A0]
0x180020ed6  mov     rdx, [rax+18h]
0x180020eda  mov     rcx, rdi
0x180020edd  mov     rax, rbx
0x180020ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ee5  mov     ebx, eax
0x180020ee7  test    eax, eax
0x180020ee9  jns     short loc_180020F11
0x180020eeb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020ef2  jz      loc_1800215DE
0x180020ef8  lea     rax, aChrPjsonvalues_63; "CHR(pJsonValueStatics->CreateStringValu"...
0x180020eff  mov     [rsp+0D0h+var_A8], rax
0x180020f04  mov     [rsp+0D0h+var_B0], 8Dh
0x180020f0c  jmp     loc_180020DAA
0x180020f11  mov     rsi, [rbp+57h+var_98]
0x180020f15  mov     rax, [rsi]
0x180020f18  mov     rdi, [rax+38h]
0x180020f1c  mov     rbx, [rbp+57h+var_A0]
0x180020f20  lea     rdx, off_18002B738; "VolumeIdentifier"
0x180020f27  lea     rcx, [rbp+57h+var_68]
0x180020f2b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020f30  nop
0x180020f31  mov     r8, rbx
0x180020f34  mov     rdx, [rax+18h]
0x180020f38  mov     rcx, rsi
0x180020f3b  mov     rax, rdi
0x180020f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f43  mov     ebx, eax
0x180020f45  test    eax, eax
0x180020f47  jns     short loc_180020F6F
0x180020f49  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020f50  jz      loc_1800215DE
0x180020f56  lea     rax, aChrPjsonobject_27; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180020f5d  mov     [rsp+0D0h+var_A8], rax
0x180020f62  mov     [rsp+0D0h+var_B0], 8Eh
0x180020f6a  jmp     loc_180020DAA
0x180020f6f  mov     rdi, [rbp+57h+var_90]
0x180020f73  mov     rax, [rdi]
0x180020f76  mov     rbx, [rax+48h]
0x180020f7a  lea     rcx, [rbp+57h+var_A0]
0x180020f7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020f83  movd    xmm1, dword ptr [r14+10h]
0x180020f89  cvtdq2pd xmm1, xmm1
0x180020f8d  lea     r8, [rbp+57h+var_A0]
0x180020f91  mov     rcx, rdi
0x180020f94  mov     rax, rbx
0x180020f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f9c  mov     ebx, eax
0x180020f9e  test    eax, eax
0x180020fa0  jns     short loc_180020FC8
0x180020fa2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180020fa9  jz      loc_1800215DE
0x180020faf  lea     rax, aChrPjsonvalues_42; "CHR(pJsonValueStatics->CreateNumberValu"...
0x180020fb6  mov     [rsp+0D0h+var_A8], rax
0x180020fbb  mov     [rsp+0D0h+var_B0], 91h
0x180020fc3  jmp     loc_180020DAA
0x180020fc8  mov     rsi, [rbp+57h+var_98]
0x180020fcc  mov     rax, [rsi]
0x180020fcf  mov     rdi, [rax+38h]
0x180020fd3  mov     rbx, [rbp+57h+var_A0]
0x180020fd7  lea     rdx, off_18002B730; "StorageType"
0x180020fde  lea     rcx, [rbp+57h+var_68]
0x180020fe2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020fe7  nop
0x180020fe8  mov     r8, rbx
0x180020feb  mov     rdx, [rax+18h]
0x180020fef  mov     rcx, rsi
0x180020ff2  mov     rax, rdi
0x180020ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ffa  mov     ebx, eax
0x180020ffc  test    eax, eax
0x180020ffe  jns     short loc_180021026
0x180021000  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021007  jz      loc_1800215DE
0x18002100d  lea     rax, aChrPjsonobject_2; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x180021014  mov     [rsp+0D0h+var_A8], rax
0x180021019  mov     [rsp+0D0h+var_B0], 92h
0x180021021  jmp     loc_180020DAA
0x180021026  mov     rdi, [rbp+57h+var_90]
0x18002102a  mov     rax, [rdi]
0x18002102d  mov     rbx, [rax+48h]
0x180021031  lea     rcx, [rbp+57h+var_A0]
0x180021035  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002103a  mov     edx, [r14+14h]
0x18002103e  xorps   xmm1, xmm1
0x180021041  cvtsi2sd xmm1, rdx
0x180021046  lea     r8, [rbp+57h+var_A0]
0x18002104a  mov     rcx, rdi
0x18002104d  mov     rax, rbx
0x180021050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021055  mov     ebx, eax
0x180021057  test    eax, eax
0x180021059  jns     short loc_180021081
0x18002105b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021062  jz      loc_1800215DE
0x180021068  lea     rax, aChrPjsonvalues_68; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18002106f  mov     [rsp+0D0h+var_A8], rax
0x180021074  mov     [rsp+0D0h+var_B0], 95h
0x18002107c  jmp     loc_180020DAA
0x180021081  mov     rsi, [rbp+57h+var_98]
0x180021085  mov     rax, [rsi]
0x180021088  mov     rdi, [rax+38h]
0x18002108c  mov     rbx, [rbp+57h+var_A0]
0x180021090  lea     rdx, off_18002B728; "DriveLetter"
0x180021097  lea     rcx, [rbp+57h+var_68]
0x18002109b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800210a0  nop
0x1800210a1  mov     r8, rbx
0x1800210a4  mov     rdx, [rax+18h]
0x1800210a8  mov     rcx, rsi
0x1800210ab  mov     rax, rdi
0x1800210ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210b3  mov     ebx, eax
0x1800210b5  test    eax, eax
0x1800210b7  jns     short loc_1800210DF
0x1800210b9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800210c0  jz      loc_1800215DE
0x1800210c6  lea     rax, aChrPjsonobject_28; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x1800210cd  mov     [rsp+0D0h+var_A8], rax
0x1800210d2  mov     [rsp+0D0h+var_B0], 96h
0x1800210da  jmp     loc_180020DAA
0x1800210df  mov     rdi, [rbp+57h+var_90]
0x1800210e3  mov     rax, [rdi]
0x1800210e6  mov     rbx, [rax+50h]
0x1800210ea  lea     rcx, [rbp+57h+var_A0]
0x1800210ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800210f3  lea     rdx, [r14+18h]; sourceString
0x1800210f7  lea     rcx, [rbp+57h+var_68]; hstringHeader
0x1800210fb  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x180021100  nop
0x180021101  lea     r8, [rbp+57h+var_A0]
0x180021105  mov     rdx, [rax+18h]
0x180021109  mov     rcx, rdi
0x18002110c  mov     rax, rbx
0x18002110f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021114  mov     ebx, eax
0x180021116  test    eax, eax
0x180021118  jns     short loc_180021140
0x18002111a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021121  jz      loc_1800215DE
0x180021127  lea     rax, aChrPjsonvalues_60; "CHR(pJsonValueStatics->CreateStringValu"...
0x18002112e  mov     [rsp+0D0h+var_A8], rax
0x180021133  mov     [rsp+0D0h+var_B0], 99h
0x18002113b  jmp     loc_180020DAA
0x180021140  mov     rsi, [rbp+57h+var_98]
0x180021144  mov     rax, [rsi]
0x180021147  mov     rdi, [rax+38h]
0x18002114b  mov     rbx, [rbp+57h+var_A0]
0x18002114f  lea     rdx, off_18002B720; "DriveName"
0x180021156  lea     rcx, [rbp+57h+var_68]
0x18002115a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002115f  nop
0x180021160  mov     r8, rbx
0x180021163  mov     rdx, [rax+18h]
0x180021167  mov     rcx, rsi
0x18002116a  mov     rax, rdi
0x18002116d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021172  mov     ebx, eax
0x180021174  test    eax, eax
0x180021176  jns     short loc_18002119E
0x180021178  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002117f  jz      loc_1800215DE
0x180021185  lea     rax, aChrPjsonobject_20; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18002118c  mov     [rsp+0D0h+var_A8], rax
0x180021191  mov     [rsp+0D0h+var_B0], 9Ah
0x180021199  jmp     loc_180020DAA
0x18002119e  mov     rdi, [rbp+57h+var_90]
0x1800211a2  mov     rax, [rdi]
0x1800211a5  mov     rbx, [rax+50h]
0x1800211a9  lea     rcx, [rbp+57h+var_A0]
0x1800211ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800211b2  mov     rdx, [r14+228h]
0x1800211b9  lea     rcx, [rbp+57h+hstringHeader]
0x1800211bd  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x1800211c2  nop
0x1800211c3  lea     rcx, [rbp+57h+hstringHeader]
0x1800211c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800211cc  mov     [rbp+57h+var_70], rax
0x1800211d0  lea     rdx, [rbp+57h+var_70]
0x1800211d4  lea     rcx, [rbp+57h+var_68]
0x1800211d8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800211dd  nop
0x1800211de  lea     r8, [rbp+57h+var_A0]
0x1800211e2  mov     rdx, [rax+18h]
0x1800211e6  mov     rcx, rdi
0x1800211e9  mov     rax, rbx
0x1800211ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211f1  mov     ebx, eax
0x1800211f3  mov     [rbp+57h+var_50], r12
0x1800211f7  lea     rcx, [rbp+57h+hstringHeader]
0x1800211fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021200  test    ebx, ebx
0x180021202  jns     short loc_18002122A
0x180021204  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002120b  jz      loc_1800215DE
0x180021211  lea     rax, aChrPjsonvalues_11; "CHR(pJsonValueStatics->CreateStringValu"...
0x180021218  mov     [rsp+0D0h+var_A8], rax
0x18002121d  mov     [rsp+0D0h+var_B0], 9Dh
0x180021225  jmp     loc_180020DAA
0x18002122a  mov     rsi, [rbp+57h+var_98]
0x18002122e  mov     rax, [rsi]
0x180021231  mov     rdi, [rax+38h]
0x180021235  mov     rbx, [rbp+57h+var_A0]
0x180021239  lea     rdx, off_18002B718; "StorageFree"
0x180021240  lea     rcx, [rbp+57h+var_68]
  ... truncated ...
```
