# DdcDeviceInfoHelper::GetDeviceInfoHeavy(Windows::Data::Json::IJsonObject *)

- ea: `0x180016aa4`
- end: `0x1800183bb`
- name: `?GetDeviceInfoHeavy@DdcDeviceInfoHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `6423`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001691c`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x1800036e8`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x18000d79c`
- `0x18000fc64`
- `0x18000fd48`
- `0x180013a58`
- `0x180014b14`
- `0x180015a4c`
- `0x180015d80`
- `0x180016aa4`
- `0x180019648`
- `0x18001992c`
- `0x180019b00`
- `0x180019d04`
- `0x18001a1c0`
- `0x18001aa08`
- `0x18001ad10`
- `0x18001b9e0`
- `0x18001bbe8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016bcf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016bcf`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180016d75`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180016d75`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180016c15`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180016c15`

## string_xrefs

- `0x180016baf`: `Windows.Data.Json.JsonValue`
- `0x18001731f`: `Windows.Data.Json.JsonValue`
- `0x1800174b0`: `Windows.Data.Json.JsonValue`
- `0x1800175dc`: `Windows.Data.Json.JsonValue`
- `0x18001762a`: `Windows.Data.Json.JsonValue`
- `0x180016c55`: `SystemProductName`
- `0x180016bfc`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001799a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x1800182f6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180016be8`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x180017351`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800174e2`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017611`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001773c`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017860`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017986`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017abb`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017bd3`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017cf2`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017e11`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017f2e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018052`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180018176`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001828e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016e97`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOs).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016ef2`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS).Get(), pJsonValue.Get()))`
- `0x180016f4d`: `CHR(pJsonValueStatics->CreateNumberValue(ePowerPlatformRole, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180016fa8`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_POWER_PLATFORM).Get(), pJsonValue.Get()))`
- `0x180017006`: `CHR(pJsonValueStatics->CreateNumberValue(dwOneCoreDeviceFamily, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017061`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_ONECORE_DEVICE_FAMILY).Get(), pJsonValue.Get()))`
- `0x1800170bf`: `CHR(pJsonValueStatics->CreateNumberValue(dwOneCoreDeviceForm, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001711a`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_ONECORE_DEVICE_FORM).Get(), pJsonValue.Get()))`
- `0x18001716e`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfResetProtectionCapable, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800171c9`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_RESET_PROTECTION_CAPABLE).Get(), pJsonValue.Get()))`
- `0x180017224`: `CHR(pJsonValueStatics->CreateNumberValue(*piChassisType, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001727f`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_CHASSIS_TYPE).Get(), pJsonValue.Get()))`
- `0x1800172ec`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemModelName).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800173b2`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MODEL_NAME).Get(), pJsonValue.Get()))`
- `0x18001741f`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemManufacturer).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001747e`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MANUFACTURER).Get(), pJsonValue.Get()))`
- `0x18001753d`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MANUFACTURER).Get(), pJsonValue.Get()))`
- `0x1800175b0`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemSerialNumber).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017673`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_SERIAL_NUMBER).Get(), pJsonValue.Get()))`
- `0x1800176e2`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOsEdition).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017797`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_EDITION).Get(), pJsonValue.Get()))`
- `0x180017806`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszReleaseShortName).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800178bb`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_RELEASE_SHORT_NAME).Get(), pJsonValue.Get()))`
- `0x18001792c`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOsLocale).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800179f0`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_LOCALE).Get(), pJsonValue.Get()))`
- `0x180017a61`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszShortOsVersion).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017b16`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_SHORT_OS_VERSION).Get(), pJsonValue.Get()))`
- `0x180017b79`: `CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfDeviceBatteryCapable, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017c2e`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_DEVICE_BATTERY_CAPABLE).Get(), pJsonValue.Get()))`
- `0x180017c98`: `CHR(pJsonValueStatics->CreateNumberValue(*pdwOsSku, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017d4d`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_SKU).Get(), pJsonValue.Get()))`
- `0x180017db7`: `CHR(pJsonValueStatics->CreateNumberValue((DWORD)*peOsGenuineState, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017e6c`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_GENUINE_STATE).Get(), pJsonValue.Get()))`
- `0x180017ed4`: `CHR(pJsonValueStatics->CreateNumberValue(*piOsReactivationPolicyState, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180017f89`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_REACTIVATION_POLICY_STATE).Get(), pJsonValue.Get()))`
- `0x180017ff8`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszLastMajorUpdateTime).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800180ad`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LAST_MAJOR_UPDATE_TIMESTAMP).Get(), pJsonValue.Get()))`
- `0x18001811c`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszCommonTargetingAttributes).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800181d1`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_COMMON_TARGETING_ATTRIBUTES).Get(), pJsonValue.Get()))`
- `0x180018238`: `CHR(pJsonValueStatics->CreateNumberValue(*pdwProductId, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800182e2`: `CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_PRODUCT_ID).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetDeviceInfoHeavy(struct Windows::Data::Json::IJsonObject *a1)
{
  const WCHAR *v2; // r14
  const WCHAR *v3; // r15
  const WCHAR *v4; // r12
  int v5; // edx
  int v6; // ecx
  int ActivationFactory; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  int *v14; // rdx
  int OsSku; // eax
  struct _tagSL_NONGENUINE_UI_OPTIONS *v16; // r8
  unsigned int *v17; // rdx
  int v18; // eax
  _SL_GENUINE_STATE *v19; // rdx
  int v20; // eax
  int *v21; // rdx
  int v22; // eax
  unsigned __int16 *v23; // rcx
  HKEY v24; // rcx
  int DWORDValue; // eax
  unsigned int *v26; // rdx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, PVOID, __int64 *); // rbx
  char v29; // r8
  HSTRING_HEADER *v30; // rax
  int v31; // edx
  int v32; // ecx
  char v33; // r8
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
  __int64 (__fastcall *v45)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v46; // rbx
  HSTRING_HEADER *v47; // rax
  int v48; // edx
  int v49; // ecx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64, __int64 *); // rbx
  __int64 v52; // rdx
  int v53; // edx
  int v54; // ecx
  char v55; // r8
  __int64 (__fastcall *v56)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v57; // rbx
  HSTRING_HEADER *v58; // rax
  int v59; // edx
  int v60; // ecx
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64, __int64 *); // rbx
  __int64 v63; // rdx
  int v64; // edx
  int v65; // ecx
  char v66; // r8
  __int64 (__fastcall *v67)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v68; // rbx
  HSTRING_HEADER *v69; // rax
  int v70; // edx
  int v71; // ecx
  __int64 v72; // rdi
  __int64 (__fastcall *v73)(__int64, _QWORD, __int64 *); // rbx
  int v74; // edx
  int v75; // ecx
  char v76; // r8
  __int64 (__fastcall *v77)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v78; // rbx
  HSTRING_HEADER *v79; // rax
  int v80; // edx
  int v81; // ecx
  __int64 v82; // rdi
  __int64 (__fastcall *v83)(__int64, __int64, __int64 *); // rbx
  __int64 v84; // rdx
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
  int v100; // edx
  int v101; // ecx
  __int64 (__fastcall *v102)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v103; // rbx
  HSTRING_HEADER *v104; // rax
  int v105; // edx
  int v106; // ecx
  __int64 v107; // rdi
  __int64 (__fastcall *v108)(__int64, PVOID, __int64 *); // rbx
  char v109; // r8
  HSTRING_HEADER *v110; // rax
  int v111; // edx
  int v112; // ecx
  char v113; // r8
  __int64 (__fastcall *v114)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v115; // rbx
  HSTRING_HEADER *v116; // rax
  int v117; // edx
  int v118; // ecx
  int v119; // edx
  int v120; // ecx
  char v121; // r8
  __int64 (__fastcall *v122)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v123; // rbx
  HSTRING_HEADER *v124; // rax
  int v125; // edx
  int v126; // ecx
  __int64 v127; // rdi
  __int64 (__fastcall *v128)(__int64, PVOID, __int64 *); // rbx
  char v129; // r8
  HSTRING_HEADER *v130; // rax
  int v131; // edx
  int v132; // ecx
  char v133; // r8
  int v134; // edx
  int v135; // ecx
  __int64 (__fastcall *v136)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v137; // rbx
  HSTRING_HEADER *v138; // rax
  int v139; // edx
  int v140; // ecx
  __int64 v141; // rdi
  __int64 (__fastcall *v142)(__int64, PVOID, __int64 *); // rbx
  char v143; // r8
  HSTRING_HEADER *v144; // rax
  int v145; // edx
  int v146; // ecx
  char v147; // r8
  int v148; // edx
  int v149; // ecx
  __int64 (__fastcall *v150)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v151; // rbx
  HSTRING_HEADER *v152; // rax
  int v153; // edx
  int v154; // ecx
  __int64 v155; // rdi
  __int64 (__fastcall *v156)(__int64, PVOID, __int64 *); // rbx
  char v157; // r8
  HSTRING_HEADER *v158; // rax
  int v159; // edx
  int v160; // ecx
  char v161; // r8
  int v162; // edx
  int v163; // ecx
  __int64 (__fastcall *v164)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v165; // rbx
  HSTRING_HEADER *v166; // rax
  int v167; // edx
  int v168; // ecx
  __int64 v169; // rdi
  __int64 (__fastcall *v170)(__int64, PVOID, __int64 *); // rbx
  char v171; // r8
  HSTRING_HEADER *v172; // rax
  int v173; // edx
  int v174; // ecx
  char v175; // r8
  int v176; // edx
  int v177; // ecx
  __int64 (__fastcall *v178)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v179; // rbx
  HSTRING_HEADER *v180; // rax
  int v181; // edx
  int v182; // ecx
  __int64 v183; // rdi
  __int64 (__fastcall *v184)(__int64, PVOID, __int64 *); // rbx
  char v185; // r8
  HSTRING_HEADER *v186; // rax
  int v187; // edx
  int v188; // ecx
  char v189; // r8
  int v190; // edx
  int v191; // ecx
  __int64 (__fastcall *v192)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v193; // rbx
  HSTRING_HEADER *v194; // rax
  int v195; // edx
  int v196; // ecx
  _BYTE *v197; // r14
  __int64 v198; // rdi
  __int64 (__fastcall *v199)(__int64, __int64, __int64 *); // rbx
  __int64 v200; // rdx
  int v201; // edx
  int v202; // ecx
  char v203; // r8
  int v204; // edx
  int v205; // ecx
  __int64 (__fastcall *v206)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v207; // rbx
  HSTRING_HEADER *v208; // rax
  int v209; // edx
  int v210; // ecx
  __int64 v211; // rdi
  __int64 (__fastcall *v212)(__int64, __int64, __int64 *); // rbx
  __int64 v213; // rdx
  int v214; // edx
  int v215; // ecx
  char v216; // r8
  int v217; // edx
  int v218; // ecx
  __int64 (__fastcall *v219)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v220; // rbx
  HSTRING_HEADER *v221; // rax
  int v222; // edx
  int v223; // ecx
  __int64 v224; // rdi
  __int64 (__fastcall *v225)(__int64, __int64, __int64 *); // rbx
  __int64 v226; // rdx
  int v227; // edx
  int v228; // ecx
  char v229; // r8
  int v230; // edx
  int v231; // ecx
  __int64 (__fastcall *v232)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v233; // rbx
  HSTRING_HEADER *v234; // rax
  int v235; // edx
  int v236; // ecx
  __int64 v237; // rdi
  __int64 (__fastcall *v238)(__int64, __int64, __int64 *); // rbx
  __int64 v239; // rdx
  int v240; // edx
  int v241; // ecx
  char v242; // r8
  int v243; // edx
  int v244; // ecx
  __int64 (__fastcall *v245)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v246; // rbx
  HSTRING_HEADER *v247; // rax
  int v248; // edx
  int v249; // ecx
  __int64 v250; // rdi
  __int64 (__fastcall *v251)(__int64, PVOID, __int64 *); // rbx
  char v252; // r8
  HSTRING_HEADER *v253; // rax
  int v254; // edx
  int v255; // ecx
  char v256; // r8
  int v257; // edx
  int v258; // ecx
  __int64 (__fastcall *v259)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v260; // rbx
  HSTRING_HEADER *v261; // rax
  int v262; // edx
  int v263; // ecx
  __int64 v264; // rdi
  __int64 (__fastcall *v265)(__int64, PVOID, __int64 *); // rbx
  char v266; // r8
  HSTRING_HEADER *v267; // rax
  int v268; // edx
  int v269; // ecx
  char v270; // r8
  int v271; // edx
  int v272; // ecx
  __int64 (__fastcall *v273)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v274; // rbx
  HSTRING_HEADER *v275; // rax
  int v276; // edx
  int v277; // ecx
  __int64 v278; // rdi
  __int64 (__fastcall *v279)(__int64, __int64, __int64 *); // rbx
  __int64 v280; // rdx
  int v281; // edx
  int v282; // ecx
  char v283; // r8
  int v284; // edx
  int v285; // ecx
  __int64 (__fastcall *v286)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v287; // rbx
  HSTRING_HEADER *v288; // rax
  int v289; // edx
  int v290; // ecx
  __int64 v291; // rcx
  __int64 v293; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v294; // [rsp+38h] [rbp-C8h] BYREF
  int v295; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v296; // [rsp+44h] [rbp-BCh] BYREF
  _SL_GENUINE_STATE v297; // [rsp+48h] [rbp-B8h] BYREF
  int v298; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v299; // [rsp+50h] [rbp-B0h] BYREF
  int v300; // [rsp+54h] [rbp-ACh] BYREF
  int v301; // [rsp+58h] [rbp-A8h] BYREF
  int v302[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v303; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME v305; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v306; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v307; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v308; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v309; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v310; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v311; // [rsp+A8h] [rbp-58h] BYREF
  int v312; // [rsp+B0h] [rbp-50h]
  const WCHAR *v313; // [rsp+B8h] [rbp-48h] BYREF
  const WCHAR *v314; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v315; // [rsp+C8h] [rbp-38h]
  _SL_GENUINE_STATE *v316; // [rsp+D0h] [rbp-30h]
  int *v317; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v319; // [rsp+F8h] [rbp-8h]
  _BYTE v320[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v321[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v322[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v323[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v324[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v325[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v326[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v327[26]; // [rsp+1D0h] [rbp+D0h] BYREF

  v302[0] = 0;
  std::wstring::wstring((__int64)v321);
  v2 = 0;
  v306 = 0;
  std::wstring::wstring((__int64)v320);
  v3 = 0;
  v307 = 0;
  std::wstring::wstring((__int64)v325);
  v4 = 0;
  v313 = 0;
  std::wstring::wstring((__int64)v324);
  v308 = 0;
  std::wstring::wstring((__int64)v323);
  v309 = 0;
  Block = 0;
  v303 = 0;
  v314 = L"Windows";
  v295 = 0;
  v300 = 0;
  v301 = 0;
  v296 = 0;
  v297 = SL_GEN_STATE_IS_GENUINE;
  v298 = 0;
  v305 = 0;
  *(_OWORD *)v326 = 0;
  memset(v327, 0, sizeof(v327));
  v310 = 0;
  std::wstring::wstring((__int64)v322);
  v311 = 0;
  v299 = 0;
  v293 = 0;
  v294 = 0;
  v319 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonValue",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v319, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v294);
  if ( ActivationFactory < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        49,
        "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
    goto LABEL_215;
  }
  v312 = PowerDeterminePlatformRoleEx(2);
  DdcDeviceInfoHelper::GetChassisType(v302);
  if ( (int)DdcRegistry::GetStringValue(
              0xFFFFFFFFLL,
              L"SYSTEM\\Platform\\DeviceTargetingInfo",
              L"PhoneManufacturerModelName",
              v321) >= 0
    || (int)DdcRegistry::GetStringValue(
              v8,
              L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation",
              L"SystemProductName",
              v321) >= 0 )
  {
    v306 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v2 = v306;
  }
  if ( (int)DdcRegistry::GetStringValue(v9, L"SYSTEM\\Platform\\DeviceTargetingInfo", L"PhoneManufacturer", v320) >= 0
    || (int)DdcRegistry::GetStringValue(
              v10,
              L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation",
              L"SystemManufacturer",
              v320) >= 0 )
  {
    v307 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v3 = v307;
  }
  if ( (int)DdcDeviceInfoHelper::GetOemSerialNumber(v325) >= 0 )
  {
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v313 = v4;
  }
  if ( (int)DdcRegistry::GetStringValue(v11, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", L"EditionID", v324) >= 0 )
    v308 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( (int)DdcRegistry::GetStringValue(v12, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", L"ReleaseId", v323) >= 0 )
    v309 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  DdcDeviceInfoHelper::GetOsLocale((unsigned __int16 **)&Block);
  DdcDeviceInfoHelper::GetShortOsVersion(&v303);
  v13 = DdcDeviceInfoHelper::DeviceBatteryCapable(&v295);
  v14 = &v295;
  if ( v13 < 0 )
    v14 = 0;
  *(_QWORD *)v302 = v14;
  RtlGetDeviceFamilyInfoEnum(0, &v300, &v301);
  OsSku = DdcDeviceInfoHelper::GetOsSku(&v296);
  v17 = &v296;
  if ( OsSku < 0 )
    v17 = 0;
  v315 = v17;
  v18 = DdcDeviceInfoHelper::SLIsGenuineLocalWrapper(0, &v297, v16);
  v19 = &v297;
  if ( v18 < 0 )
    v19 = 0;
  v316 = v19;
  v20 = DdcDeviceInfoHelper::OsReactivationPolicyState(&v298);
  v21 = &v298;
  if ( v20 < 0 )
    v21 = 0;
  v317 = v21;
  if ( (int)DdcDeviceInfoHelper::GetLastMajorUpdateTime(&v305) >= 0 )
  {
    v22 = StringCchPrintfW(v326, 0x15u, L"%llu", v305);
    v23 = v326;
    if ( v22 < 0 )
      v23 = 0;
    v310 = v23;
  }
  if ( (int)DdcDeviceInfoHelper::GetCommonTargetingAttributes((__int64)v322) >= 0 )
    v311 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  DWORDValue = DdcRegistry::GetDWORDValue(v24, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Product", L"Id", &v299);
  v26 = &v299;
  if ( DWORDValue < 0 )
    v26 = 0;
  v305 = (struct _FILETIME)v26;
  v27 = v294;
  v28 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
  v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v314, v29);
  ActivationFactory = v28(v27, v30[1].Reserved.Reserved1, &v293);
  if ( ActivationFactory >= 0 )
  {
    v34 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
    v35 = v293;
    v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)off_18002B608,
            v33);
    ActivationFactory = v34(a1, v36[1].Reserved.Reserved1, v35);
    if ( ActivationFactory >= 0 )
    {
      v39 = v294;
      v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
      ActivationFactory = v40(v39, v41, &v293);
      if ( ActivationFactory >= 0 )
      {
        v45 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
        v46 = v293;
        v47 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)off_18002B638,
                v44);
        ActivationFactory = v45(a1, v47[1].Reserved.Reserved1, v46);
        if ( ActivationFactory >= 0 )
        {
          v50 = v294;
          v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
          ActivationFactory = v51(v50, v52, &v293);
          if ( ActivationFactory >= 0 )
          {
            v56 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
            v57 = v293;
            v58 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_18002B5C0,
                    v55);
            ActivationFactory = v56(a1, v58[1].Reserved.Reserved1, v57);
            if ( ActivationFactory >= 0 )
            {
              v61 = v294;
              v62 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
              ActivationFactory = v62(v61, v63, &v293);
              if ( ActivationFactory >= 0 )
              {
                v67 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                v68 = v293;
                v69 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_18002B5B8,
                        v66);
                ActivationFactory = v67(a1, v69[1].Reserved.Reserved1, v68);
                if ( ActivationFactory >= 0 )
                {
                  v72 = v294;
                  v73 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v294 + 64LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                  ActivationFactory = v73(v72, 0, &v293);
                  if ( ActivationFactory >= 0 )
                  {
                    v77 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                    v78 = v293;
                    v79 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &hstringHeader,
                            (const WCHAR **)off_18002B5D0,
                            v76);
                    ActivationFactory = v77(a1, v79[1].Reserved.Reserved1, v78);
                    if ( ActivationFactory >= 0 )
                    {
                      v82 = v294;
                      v83 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                      ActivationFactory = v83(v82, v84, &v293);
                      if ( ActivationFactory >= 0 )
                      {
                        v88 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                        v89 = v293;
                        v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                &hstringHeader,
                                (const WCHAR **)off_18002B630,
                                v87);
                        ActivationFactory = v88(a1, v90[1].Reserved.Reserved1, v89);
                        if ( ActivationFactory >= 0 )
                        {
                          if ( v2 )
                          {
                            v93 = v294;
                            v94 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                            v96 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                    &hstringHeader,
                                    &v306,
                                    v95);
                            ActivationFactory = v94(v93, v96[1].Reserved.Reserved1, &v293);
                            if ( ActivationFactory < 0 )
                            {
                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v98,
                                  v97,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                                  216,
                                  "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemModelName).Get(), pJs"
                                  "onValue.ReleaseAndGetAddressOf()))");
                              goto LABEL_211;
                            }
                          }
                          else
                          {
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                            v319 = 0;
                            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                              &hstringHeader,
                              L"Windows.Data.Json.JsonValue",
                              0x1Cu,
                              0x1Bu);
                            ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                  v319,
                                                  &v293);
                            if ( ActivationFactory < 0 )
                            {
                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v101,
                                  v100,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                                  220,
                                  "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(),"
                                  " pJsonValue.ReleaseAndGetAddressOf()))");
                              goto LABEL_211;
                            }
                          }
                          v102 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                          v103 = v293;
                          v104 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                   &hstringHeader,
                                   (const WCHAR **)off_18002B628,
                                   v99);
                          ActivationFactory = v102(a1, v104[1].Reserved.Reserved1, v103);
                          if ( ActivationFactory >= 0 )
                          {
                            if ( v3 )
                            {
                              v107 = v294;
                              v108 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                              v110 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       &v307,
                                       v109);
                              ActivationFactory = v108(v107, v110[1].Reserved.Reserved1, &v293);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v112,
                                    v111,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    228,
                                    "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemManufacturer).Get()"
                                    ", pJsonValue.ReleaseAndGetAddressOf()))");
                                goto LABEL_211;
                              }
                              v114 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                              v115 = v293;
                              v116 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       (const WCHAR **)off_18002B620,
                                       v113);
                              ActivationFactory = v114(a1, v116[1].Reserved.Reserved1, v115);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v118,
                                    v117,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    229,
                                    "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MANUFACTURER).Get(), pJsonValue.Get()))");
                                goto LABEL_211;
                              }
                            }
                            else
                            {
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                              v319 = 0;
                              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                &hstringHeader,
                                L"Windows.Data.Json.JsonValue",
                                0x1Cu,
                                0x1Bu);
                              ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                    v319,
                                                    &v293);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v120,
                                    v119,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    233,
                                    "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get("
                                    "), pJsonValue.ReleaseAndGetAddressOf()))");
                                goto LABEL_211;
                              }
                              v122 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                              v123 = v293;
                              v124 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       (const WCHAR **)off_18002B620,
                                       v121);
                              ActivationFactory = v122(a1, v124[1].Reserved.Reserved1, v123);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v126,
                                    v125,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    234,
                                    "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MANUFACTURER).Get(), pJsonValue.Get()))");
                                goto LABEL_211;
                              }
                            }
                            if ( v4 )
                            {
                              v127 = v294;
                              v128 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                              v130 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       &v313,
                                       v129);
                              ActivationFactory = v128(v127, v130[1].Reserved.Reserved1, &v293);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v132,
                                    v131,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    240,
                                    "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOemSerialNumber).Get()"
                                    ", pJsonValue.ReleaseAndGetAddressOf()))");
                                goto LABEL_211;
                              }
                            }
                            else
                            {
                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                              v319 = 0;
                              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                &hstringHeader,
                                L"Windows.Data.Json.JsonValue",
                                0x1Cu,
                                0x1Bu);
                              ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                    v319,
                                                    &v293);
                              if ( ActivationFactory < 0 )
                              {
                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v135,
                                    v134,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    244,
                                    "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get("
                                    "), pJsonValue.ReleaseAndGetAddressOf()))");
                                goto LABEL_211;
                              }
                            }
                            v136 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                            v137 = v293;
                            v138 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                     &hstringHeader,
                                     (const WCHAR **)off_18002B618,
                                     v133);
                            ActivationFactory = v136(a1, v138[1].Reserved.Reserved1, v137);
                            if ( ActivationFactory >= 0 )
                            {
                              if ( v308 )
                              {
                                v141 = v294;
                                v142 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                v144 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                         &hstringHeader,
                                         &v308,
                                         v143);
                                ActivationFactory = v142(v141, v144[1].Reserved.Reserved1, &v293);
                                if ( ActivationFactory < 0 )
                                {
                                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v146,
                                      v145,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcd"
                                                    "eviceinfohelper.cpp",
                                      252,
                                      "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOsEdition).Get(), pJ"
                                      "sonValue.ReleaseAndGetAddressOf()))");
                                  goto LABEL_211;
                                }
                              }
                              else
                              {
                                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                v319 = 0;
                                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                  &hstringHeader,
                                  L"Windows.Data.Json.JsonValue",
                                  0x1Cu,
                                  0x1Bu);
                                ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                      v319,
                                                      &v293);
                                if ( ActivationFactory < 0 )
                                {
                                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v149,
                                      v148,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcd"
                                                    "eviceinfohelper.cpp",
                                      0,
                                      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Ge"
                                      "t(), pJsonValue.ReleaseAndGetAddressOf()))");
                                  goto LABEL_211;
                                }
                              }
                              v150 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                              v151 = v293;
                              v152 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                       &hstringHeader,
                                       (const WCHAR **)off_18002B5F0,
                                       v147);
                              ActivationFactory = v150(a1, v152[1].Reserved.Reserved1, v151);
                              if ( ActivationFactory >= 0 )
                              {
                                if ( v309 )
                                {
                                  v155 = v294;
                                  v156 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                  v158 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           &hstringHeader,
                                           &v309,
                                           v157);
                                  ActivationFactory = v156(v155, v158[1].Reserved.Reserved1, &v293);
                                  if ( ActivationFactory < 0 )
                                  {
                                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v160,
                                        v159,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\dd"
                                                      "cdeviceinfohelper.cpp",
                                        8,
                                        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszReleaseShortName)."
                                        "Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                    goto LABEL_211;
                                  }
                                }
                                else
                                {
                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                  v319 = 0;
                                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                    &hstringHeader,
                                    L"Windows.Data.Json.JsonValue",
                                    0x1Cu,
                                    0x1Bu);
                                  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                        v319,
                                                        &v293);
                                  if ( ActivationFactory < 0 )
                                  {
                                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v163,
                                        v162,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\dd"
                                                      "cdeviceinfohelper.cpp",
                                        12,
                                        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue)."
                                        "Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                    goto LABEL_211;
                                  }
                                }
                                v164 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                v165 = v293;
                                v166 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                         &hstringHeader,
                                         (const WCHAR **)off_18002B570,
                                         v161);
                                ActivationFactory = v164(a1, v166[1].Reserved.Reserved1, v165);
                                if ( ActivationFactory >= 0 )
                                {
                                  if ( Block )
                                  {
                                    v169 = v294;
                                    v170 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                    v172 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                             &hstringHeader,
                                             (const WCHAR **)&Block,
                                             v171);
                                    ActivationFactory = v170(v169, v172[1].Reserved.Reserved1, &v293);
                                    if ( ActivationFactory < 0 )
                                    {
                                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v174,
                                          v173,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcdeviceinfohelper.cpp",
                                          20,
                                          "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOsLocale).Get(),"
                                          " pJsonValue.ReleaseAndGetAddressOf()))");
                                      goto LABEL_211;
                                    }
                                  }
                                  else
                                  {
                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                    v319 = 0;
                                    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                      &hstringHeader,
                                      L"Windows.Data.Json.JsonValue",
                                      0x1Cu,
                                      0x1Bu);
                                    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                          v319,
                                                          &v293);
                                    if ( ActivationFactory < 0 )
                                    {
                                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v177,
                                          v176,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcdeviceinfohelper.cpp",
                                          24,
                                          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue"
                                          ").Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                      goto LABEL_213;
                                    }
                                  }
                                  v178 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                  v179 = v293;
                                  v180 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                           &hstringHeader,
                                           (const WCHAR **)off_18002B610,
                                           v175);
                                  ActivationFactory = v178(a1, v180[1].Reserved.Reserved1, v179);
                                  if ( ActivationFactory >= 0 )
                                  {
                                    if ( v303 )
                                    {
                                      v183 = v294;
                                      v184 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                      v186 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                               &hstringHeader,
                                               (const WCHAR **)&v303,
                                               v185);
                                      ActivationFactory = v184(v183, v186[1].Reserved.Reserved1, &v293);
                                      if ( ActivationFactory < 0 )
                                      {
                                        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                          McTemplateU0dsqs_EventWriteTransfer(
                                            v188,
                                            v187,
                                            ActivationFactory,
                                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib"
                                                          "\\ddcdeviceinfohelper.cpp",
                                            32,
                                            "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszShortOsVersion"
                                            ").Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                        goto LABEL_211;
                                      }
                                    }
                                    else
                                    {
                                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                      v319 = 0;
                                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                        &hstringHeader,
                                        L"Windows.Data.Json.JsonValue",
                                        0x1Cu,
                                        0x1Bu);
                                      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                            v319,
                                                            &v293);
                                      if ( ActivationFactory < 0 )
                                      {
                                        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                          McTemplateU0dsqs_EventWriteTransfer(
                                            v191,
                                            v190,
                                            ActivationFactory,
                                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib"
                                                          "\\ddcdeviceinfohelper.cpp",
                                            36,
                                            "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonVal"
                                            "ue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                        goto LABEL_211;
                                      }
                                    }
                                    v192 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                    v193 = v293;
                                    v194 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                             &hstringHeader,
                                             (const WCHAR **)off_18002B5E8,
                                             v189);
                                    ActivationFactory = v192(a1, v194[1].Reserved.Reserved1, v193);
                                    if ( ActivationFactory >= 0 )
                                    {
                                      v197 = *(_BYTE **)v302;
                                      if ( *(_QWORD *)v302 )
                                      {
                                        v198 = v294;
                                        v199 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 64LL);
                                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                        LOBYTE(v200) = *v197;
                                        ActivationFactory = v199(v198, v200, &v293);
                                        if ( ActivationFactory < 0 )
                                        {
                                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                            McTemplateU0dsqs_EventWriteTransfer(
                                              v202,
                                              v201,
                                              ActivationFactory,
                                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\l"
                                                            "ib\\ddcdeviceinfohelper.cpp",
                                              44,
                                              "CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfDeviceBatteryCapable"
                                              ", pJsonValue.ReleaseAndGetAddressOf()))");
                                          goto LABEL_211;
                                        }
                                      }
                                      else
                                      {
                                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                        v319 = 0;
                                        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                          &hstringHeader,
                                          L"Windows.Data.Json.JsonValue",
                                          0x1Cu,
                                          0x1Bu);
                                        ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                              v319,
                                                              &v293);
                                        if ( ActivationFactory < 0 )
                                        {
                                          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                            McTemplateU0dsqs_EventWriteTransfer(
                                              v205,
                                              v204,
                                              ActivationFactory,
                                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\l"
                                                            "ib\\ddcdeviceinfohelper.cpp",
                                              48,
                                              "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonV"
                                              "alue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                          goto LABEL_211;
                                        }
                                      }
                                      v206 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                      v207 = v293;
                                      v208 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                               &hstringHeader,
                                               (const WCHAR **)off_18002B5C8,
                                               v203);
                                      ActivationFactory = v206(a1, v208[1].Reserved.Reserved1, v207);
                                      if ( ActivationFactory >= 0 )
                                      {
                                        if ( v315 )
                                        {
                                          v211 = v294;
                                          v212 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
                                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                          ActivationFactory = v212(v211, v213, &v293);
                                          if ( ActivationFactory < 0 )
                                          {
                                            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                & 1) != 0 )
                                              McTemplateU0dsqs_EventWriteTransfer(
                                                v215,
                                                v214,
                                                ActivationFactory,
                                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\"
                                                              "lib\\ddcdeviceinfohelper.cpp",
                                                56,
                                                "CHR(pJsonValueStatics->CreateNumberValue(*pdwOsSku, pJsonValue.ReleaseAn"
                                                "dGetAddressOf()))");
                                            goto LABEL_211;
                                          }
                                        }
                                        else
                                        {
                                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                          v319 = 0;
                                          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                            &hstringHeader,
                                            L"Windows.Data.Json.JsonValue",
                                            0x1Cu,
                                            0x1Bu);
                                          ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                v319,
                                                                &v293);
                                          if ( ActivationFactory < 0 )
                                          {
                                            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                & 1) != 0 )
                                              McTemplateU0dsqs_EventWriteTransfer(
                                                v218,
                                                v217,
                                                ActivationFactory,
                                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\"
                                                              "lib\\ddcdeviceinfohelper.cpp",
                                                60,
                                                "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_Jso"
                                                "nValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                            goto LABEL_211;
                                          }
                                        }
                                        v219 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                        v220 = v293;
                                        v221 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                 &hstringHeader,
                                                 (const WCHAR **)off_18002B5B0,
                                                 v216);
                                        ActivationFactory = v219(a1, v221[1].Reserved.Reserved1, v220);
                                        if ( ActivationFactory >= 0 )
                                        {
                                          if ( v316 )
                                          {
                                            v224 = v294;
                                            v225 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
                                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                            ActivationFactory = v225(v224, v226, &v293);
                                            if ( ActivationFactory < 0 )
                                            {
                                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                  & 1) != 0 )
                                                McTemplateU0dsqs_EventWriteTransfer(
                                                  v228,
                                                  v227,
                                                  ActivationFactory,
                                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclien"
                                                                "t\\lib\\ddcdeviceinfohelper.cpp",
                                                  68,
                                                  "CHR(pJsonValueStatics->CreateNumberValue((DWORD)*peOsGenuineState, pJs"
                                                  "onValue.ReleaseAndGetAddressOf()))");
                                              goto LABEL_211;
                                            }
                                          }
                                          else
                                          {
                                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                            v319 = 0;
                                            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                              &hstringHeader,
                                              L"Windows.Data.Json.JsonValue",
                                              0x1Cu,
                                              0x1Bu);
                                            ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                  v319,
                                                                  &v293);
                                            if ( ActivationFactory < 0 )
                                            {
                                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                  & 1) != 0 )
                                                McTemplateU0dsqs_EventWriteTransfer(
                                                  v231,
                                                  v230,
                                                  ActivationFactory,
                                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclien"
                                                                "t\\lib\\ddcdeviceinfohelper.cpp",
                                                  72,
                                                  "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_J"
                                                  "sonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                              goto LABEL_211;
                                            }
                                          }
                                          v232 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                          v233 = v293;
                                          v234 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                   &hstringHeader,
                                                   (const WCHAR **)off_18002B5A8,
                                                   v229);
                                          ActivationFactory = v232(a1, v234[1].Reserved.Reserved1, v233);
                                          if ( ActivationFactory >= 0 )
                                          {
                                            if ( v317 )
                                            {
                                              v237 = v294;
                                              v238 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
                                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                              ActivationFactory = v238(v237, v239, &v293);
                                              if ( ActivationFactory < 0 )
                                              {
                                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                    & 1) != 0 )
                                                  McTemplateU0dsqs_EventWriteTransfer(
                                                    v241,
                                                    v240,
                                                    ActivationFactory,
                                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectorycli"
                                                                  "ent\\lib\\ddcdeviceinfohelper.cpp",
                                                    80,
                                                    "CHR(pJsonValueStatics->CreateNumberValue(*piOsReactivationPolicyStat"
                                                    "e, pJsonValue.ReleaseAndGetAddressOf()))");
                                                goto LABEL_211;
                                              }
                                            }
                                            else
                                            {
                                              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                              v319 = 0;
                                              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                                &hstringHeader,
                                                L"Windows.Data.Json.JsonValue",
                                                0x1Cu,
                                                0x1Bu);
                                              ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                    v319,
                                                                    &v293);
                                              if ( ActivationFactory < 0 )
                                              {
                                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                    & 1) != 0 )
                                                  McTemplateU0dsqs_EventWriteTransfer(
                                                    v244,
                                                    v243,
                                                    ActivationFactory,
                                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectorycli"
                                                                  "ent\\lib\\ddcdeviceinfohelper.cpp",
                                                    84,
                                                    "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json"
                                                    "_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                goto LABEL_211;
                                              }
                                            }
                                            v245 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                            v246 = v293;
                                            v247 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                     &hstringHeader,
                                                     (const WCHAR **)off_18002B5A0,
                                                     v242);
                                            ActivationFactory = v245(a1, v247[1].Reserved.Reserved1, v246);
                                            if ( ActivationFactory >= 0 )
                                            {
                                              if ( v310 )
                                              {
                                                v250 = v294;
                                                v251 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                v253 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                         &hstringHeader,
                                                         &v310,
                                                         v252);
                                                ActivationFactory = v251(v250, v253[1].Reserved.Reserved1, &v293);
                                                if ( ActivationFactory < 0 )
                                                {
                                                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                      & 1) != 0 )
                                                    McTemplateU0dsqs_EventWriteTransfer(
                                                      v255,
                                                      v254,
                                                      ActivationFactory,
                                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryc"
                                                                    "lient\\lib\\ddcdeviceinfohelper.cpp",
                                                      92,
                                                      "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszLast"
                                                      "MajorUpdateTime).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                  goto LABEL_211;
                                                }
                                              }
                                              else
                                              {
                                                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                v319 = 0;
                                                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                                  &hstringHeader,
                                                  L"Windows.Data.Json.JsonValue",
                                                  0x1Cu,
                                                  0x1Bu);
                                                ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                      v319,
                                                                      &v293);
                                                if ( ActivationFactory < 0 )
                                                {
                                                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                      & 1) != 0 )
                                                    McTemplateU0dsqs_EventWriteTransfer(
                                                      v258,
                                                      v257,
                                                      ActivationFactory,
                                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryc"
                                                                    "lient\\lib\\ddcdeviceinfohelper.cpp",
                                                      96,
                                                      "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Js"
                                                      "on_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                  goto LABEL_211;
                                                }
                                              }
                                              v259 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                              v260 = v293;
                                              v261 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                       &hstringHeader,
                                                       (const WCHAR **)off_18002B520,
                                                       v256);
                                              ActivationFactory = v259(a1, v261[1].Reserved.Reserved1, v260);
                                              if ( ActivationFactory >= 0 )
                                              {
                                                if ( v311 )
                                                {
                                                  v264 = v294;
                                                  v265 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v294 + 80LL);
                                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                  v267 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                           &hstringHeader,
                                                           &v311,
                                                           v266);
                                                  ActivationFactory = v265(v264, v267[1].Reserved.Reserved1, &v293);
                                                  if ( ActivationFactory < 0 )
                                                  {
                                                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                        & 1) != 0 )
                                                      McTemplateU0dsqs_EventWriteTransfer(
                                                        v269,
                                                        v268,
                                                        ActivationFactory,
                                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirector"
                                                                      "yclient\\lib\\ddcdeviceinfohelper.cpp",
                                                        104,
                                                        "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszCo"
                                                        "mmonTargetingAttributes).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                    goto LABEL_211;
                                                  }
                                                }
                                                else
                                                {
                                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                  v319 = 0;
                                                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                                    &hstringHeader,
                                                    L"Windows.Data.Json.JsonValue",
                                                    0x1Cu,
                                                    0x1Bu);
                                                  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                        v319,
                                                                        &v293);
                                                  if ( ActivationFactory < 0 )
                                                  {
                                                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                        & 1) != 0 )
                                                      McTemplateU0dsqs_EventWriteTransfer(
                                                        v272,
                                                        v271,
                                                        ActivationFactory,
                                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirector"
                                                                      "yclient\\lib\\ddcdeviceinfohelper.cpp",
                                                        108,
                                                        "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_"
                                                        "Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                    goto LABEL_211;
                                                  }
                                                }
                                                v273 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                                v274 = v293;
                                                v275 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                         &hstringHeader,
                                                         (const WCHAR **)off_18002B568,
                                                         v270);
                                                ActivationFactory = v273(a1, v275[1].Reserved.Reserved1, v274);
                                                if ( ActivationFactory >= 0 )
                                                {
                                                  if ( v305 )
                                                  {
                                                    v278 = v294;
                                                    v279 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v294 + 72LL);
                                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                    ActivationFactory = v279(v278, v280, &v293);
                                                    if ( ActivationFactory < 0 )
                                                    {
                                                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                          & 1) != 0 )
                                                        McTemplateU0dsqs_EventWriteTransfer(
                                                          v282,
                                                          v281,
                                                          ActivationFactory,
                                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirect"
                                                                        "oryclient\\lib\\ddcdeviceinfohelper.cpp",
                                                          116,
                                                          "CHR(pJsonValueStatics->CreateNumberValue(*pdwProductId, pJsonV"
                                                          "alue.ReleaseAndGetAddressOf()))");
                                                      goto LABEL_211;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
                                                    v319 = 0;
                                                    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                                                      &hstringHeader,
                                                      L"Windows.Data.Json.JsonValue",
                                                      0x1Cu,
                                                      0x1Bu);
                                                    ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>(
                                                                          v319,
                                                                          &v293);
                                                    if ( ActivationFactory < 0 )
                                                    {
                                                      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                          & 1) != 0 )
                                                        McTemplateU0dsqs_EventWriteTransfer(
                                                          v285,
                                                          v284,
                                                          ActivationFactory,
                                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirect"
                                                                        "oryclient\\lib\\ddcdeviceinfohelper.cpp",
                                                          120,
                                                          "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Dat"
                                                          "a_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
                                                      goto LABEL_211;
                                                    }
                                                  }
                                                  v286 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
                                                  v287 = v293;
                                                  v288 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                                           &hstringHeader,
                                                           (const WCHAR **)off_18002B560,
                                                           v283);
                                                  ActivationFactory = v286(a1, v288[1].Reserved.Reserved1, v287);
                                                  if ( ActivationFactory < 0
                                                    && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                      & 1) != 0 )
                                                  {
                                                    McTemplateU0dsqs_EventWriteTransfer(
                                                      v290,
                                                      v289,
                                                      ActivationFactory,
                                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryc"
                                                                    "lient\\lib\\ddcdeviceinfohelper.cpp",
                                                      123,
                                                      "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_PRODUCT_ID).G"
                                                      "et(), pJsonValue.Get()))");
                                                  }
                                                  goto LABEL_211;
                                                }
                                                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                    & 1) != 0 )
                                                  McTemplateU0dsqs_EventWriteTransfer(
                                                    v277,
                                                    v276,
                                                    ActivationFactory,
                                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectorycli"
                                                                  "ent\\lib\\ddcdeviceinfohelper.cpp",
                                                    111,
                                                    "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_COMMON_TARGETIN"
                                                    "G_ATTRIBUTES).Get(), pJsonValue.Get()))");
                                              }
                                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                       & 1) != 0 )
                                              {
                                                McTemplateU0dsqs_EventWriteTransfer(
                                                  v263,
                                                  v262,
                                                  ActivationFactory,
                                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclien"
                                                                "t\\lib\\ddcdeviceinfohelper.cpp",
                                                  99,
                                                  "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_LAST_MAJOR_UPDATE"
                                                  "_TIMESTAMP).Get(), pJsonValue.Get()))");
                                              }
                                            }
                                            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                     & 1) != 0 )
                                            {
                                              McTemplateU0dsqs_EventWriteTransfer(
                                                v249,
                                                v248,
                                                ActivationFactory,
                                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\"
                                                              "lib\\ddcdeviceinfohelper.cpp",
                                                87,
                                                "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_REACTIVATION_POL"
                                                "ICY_STATE).Get(), pJsonValue.Get()))");
                                            }
                                          }
                                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                   & 1) != 0 )
                                          {
                                            McTemplateU0dsqs_EventWriteTransfer(
                                              v236,
                                              v235,
                                              ActivationFactory,
                                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\l"
                                                            "ib\\ddcdeviceinfohelper.cpp",
                                              75,
                                              "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_GENUINE_STATE).Get"
                                              "(), pJsonValue.Get()))");
                                          }
                                        }
                                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                 & 1) != 0 )
                                        {
                                          McTemplateU0dsqs_EventWriteTransfer(
                                            v223,
                                            v222,
                                            ActivationFactory,
                                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib"
                                                          "\\ddcdeviceinfohelper.cpp",
                                            63,
                                            "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_SKU).Get(), pJsonValue.Get()))");
                                        }
                                      }
                                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                               & 1) != 0 )
                                      {
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v210,
                                          v209,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcdeviceinfohelper.cpp",
                                          51,
                                          "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_DEVICE_BATTERY_CAPABLE).G"
                                          "et(), pJsonValue.Get()))");
                                      }
                                    }
                                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    {
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v196,
                                        v195,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\dd"
                                                      "cdeviceinfohelper.cpp",
                                        39,
                                        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_SHORT_OS_VERSION).Get(), pJ"
                                        "sonValue.Get()))");
                                    }
                                  }
                                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  {
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v182,
                                      v181,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcd"
                                                    "eviceinfohelper.cpp",
                                      27,
                                      "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_LOCALE).Get(), pJsonValue.Get()))");
                                  }
                                }
                                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                {
                                  McTemplateU0dsqs_EventWriteTransfer(
                                    v168,
                                    v167,
                                    ActivationFactory,
                                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdev"
                                                  "iceinfohelper.cpp",
                                    15,
                                    "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_RELEASE_SHORT_NAME).Get(), pJsonValue.Get()))");
                                }
                              }
                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                              {
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v154,
                                  v153,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                                  3,
                                  "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS_EDITION).Get(), pJsonValue.Get()))");
                              }
                            }
                            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                            {
                              McTemplateU0dsqs_EventWriteTransfer(
                                v140,
                                v139,
                                ActivationFactory,
                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                                247,
                                "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_SERIAL_NUMBER).Get(), pJsonValue.Get()))");
                            }
                          }
                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v106,
                              v105,
                              ActivationFactory,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                              223,
                              "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OEM_MODEL_NAME).Get(), pJsonValue.Get()))");
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v92,
                            v91,
                            ActivationFactory,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                            211,
                            "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_CHASSIS_TYPE).Get(), pJsonValue.Get()))");
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v86,
                          v85,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                          204,
                          "CHR(pJsonValueStatics->CreateNumberValue(*piChassisType, pJsonValue.ReleaseAndGetAddressOf()))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v81,
                        v80,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                        199,
                        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_RESET_PROTECTION_CAPABLE).Get(), pJsonValue.Get()))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v75,
                      v74,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                      192,
                      "CHR(pJsonValueStatics->CreateBooleanValue((boolean)*pfResetProtectionCapable, pJsonValue.ReleaseAn"
                      "dGetAddressOf()))");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v71,
                    v70,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                    187,
                    "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_ONECORE_DEVICE_FORM).Get(), pJsonValue.Get()))");
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v65,
                  v64,
                  ActivationFactory,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                  186,
                  "CHR(pJsonValueStatics->CreateNumberValue(dwOneCoreDeviceForm, pJsonValue.ReleaseAndGetAddressOf()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v60,
                v59,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
                183,
                "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_ONECORE_DEVICE_FAMILY).Get(), pJsonValue.Get()))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v54,
              v53,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              182,
              "CHR(pJsonValueStatics->CreateNumberValue(dwOneCoreDeviceFamily, pJsonValue.ReleaseAndGetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v49,
            v48,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            179,
            "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_POWER_PLATFORM).Get(), pJsonValue.Get()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v43,
          v42,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          178,
          "CHR(pJsonValueStatics->CreateNumberValue(ePowerPlatformRole, pJsonValue.ReleaseAndGetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v38,
        v37,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        175,
        "CHR(pDeviceInfo->SetNamedValue(HStringReference(JSON_OS).Get(), pJsonValue.Get()))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v32,
      v31,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      174,
      "CHR(pJsonValueStatics->CreateStringValue(HStringReference(pwszOs).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
  }
LABEL_211:
  if ( Block )
    operator delete(Block);
LABEL_213:
  if ( v303 )
    operator delete(v303);
LABEL_215:
  v291 = v294;
  if ( v294 )
  {
    v294 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v291 + 16LL))(v291);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v293);
  std::wstring::_Tidy_deallocate((__int64)v322);
  std::wstring::_Tidy_deallocate((__int64)v323);
  std::wstring::_Tidy_deallocate((__int64)v324);
  std::wstring::_Tidy_deallocate((__int64)v325);
  std::wstring::_Tidy_deallocate((__int64)v320);
  std::wstring::_Tidy_deallocate((__int64)v321);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180016aa4  push    rbp
0x180016aa6  push    rbx
0x180016aa7  push    rsi
0x180016aa8  push    rdi
0x180016aa9  push    r12
0x180016aab  push    r13
0x180016aad  push    r14
0x180016aaf  push    r15
0x180016ab1  lea     rbp, [rsp-108h]
0x180016ab9  sub     rsp, 208h
0x180016ac0  mov     rax, cs:__security_cookie
0x180016ac7  xor     rax, rsp
0x180016aca  mov     [rbp+140h+var_50], rax
0x180016ad1  mov     rsi, rcx
0x180016ad4  mov     [rsp+240h+var_1E0], 0
0x180016adc  lea     rcx, [rbp+140h+var_120]
0x180016ae0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016ae5  nop
0x180016ae6  xor     r14d, r14d
0x180016ae9  mov     [rbp+140h+var_1C0], r14
0x180016aed  lea     rcx, [rbp+140h+var_140]
0x180016af1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016af6  nop
0x180016af7  xor     r15d, r15d
0x180016afa  mov     [rbp+140h+var_1B8], r15
0x180016afe  lea     rcx, [rbp+140h+var_A0]
0x180016b05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016b0a  nop
0x180016b0b  xor     r12d, r12d
0x180016b0e  mov     [rbp+140h+var_188], r12
0x180016b12  lea     rcx, [rbp+140h+var_C0]
0x180016b19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016b1e  nop
0x180016b1f  mov     [rbp+140h+var_1B0], r12
0x180016b23  lea     rcx, [rbp+140h+var_E0]
0x180016b27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016b2c  nop
0x180016b2d  mov     [rbp+140h+var_1A8], r12
0x180016b31  mov     [rsp+240h+Block], r12
0x180016b36  mov     [rsp+240h+var_1D8], r12
0x180016b3b  lea     rax, aWindows; "Windows"
0x180016b42  mov     [rbp+140h+var_180], rax
0x180016b46  mov     [rsp+240h+var_200], r12d
0x180016b4b  mov     [rsp+240h+var_1EC], r12d
0x180016b50  mov     [rsp+240h+var_1E8], r12d
0x180016b55  mov     [rsp+240h+var_1FC], r12d
0x180016b5a  mov     [rsp+240h+var_1F8], r12d
0x180016b5f  mov     [rsp+240h+var_1F4], r12d
0x180016b64  mov     qword ptr [rsp+240h+var_1C8.dwLowDateTime], r12
0x180016b69  xorps   xmm0, xmm0
0x180016b6c  movups  xmmword ptr [rbp+140h+var_80], xmm0
0x180016b73  movups  xmmword ptr [rbp+140h+var_70], xmm0
0x180016b7a  movups  xmmword ptr [rbp+140h+var_70+0Ah], xmm0
0x180016b81  xor     edi, edi
0x180016b83  mov     [rbp+140h+var_1A0], rdi
0x180016b87  lea     rcx, [rbp+140h+var_100]
0x180016b8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016b90  nop
0x180016b91  mov     [rbp+140h+var_198], rdi
0x180016b95  mov     [rsp+240h+var_1F0], edi
0x180016b99  mov     [rsp+240h+var_210], rdi
0x180016b9e  mov     [rsp+240h+var_208], rdi
0x180016ba3  mov     [rbp+140h+var_148], rdi
0x180016ba7  lea     r9d, [r14+1Bh]; unsigned int
0x180016bab  lea     r8d, [r14+1Ch]; unsigned int
0x180016baf  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x180016bb6  lea     rcx, [rbp+140h+hstringHeader]; hstringHeader
0x180016bba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016bbf  lea     r8, [rsp+240h+var_208]
0x180016bc4  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180016bcb  mov     rcx, [rbp+140h+var_148]
0x180016bcf  call    cs:__imp_RoGetActivationFactory
0x180016bd5  mov     ebx, eax
0x180016bd7  test    eax, eax
0x180016bd9  jns     short loc_180016C10
0x180016bdb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016be2  jz      loc_18001832A
0x180016be8  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x180016bef  mov     [rsp+240h+var_218], rax
0x180016bf4  mov     [rsp+240h+var_220], 131h
0x180016bfc  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180016c03  mov     r8d, ebx
0x180016c06  call    McTemplateU0dsqs_EventWriteTransfer
0x180016c0b  jmp     loc_18001832A
0x180016c10  mov     ecx, 2
0x180016c15  call    cs:__imp_PowerDeterminePlatformRoleEx
0x180016c1b  mov     [rbp+140h+var_190], eax
0x180016c1e  lea     rcx, [rsp+240h+var_1E0]; int *
0x180016c23  call    ?GetChassisType@DdcDeviceInfoHelper@@CAJPEAH@Z; DdcDeviceInfoHelper::GetChassisType(int *)
0x180016c28  mov     r13d, [rsp+240h+var_1E0]
0x180016c2d  or      ecx, 0FFFFFFFFh
0x180016c30  test    eax, eax
0x180016c32  cmovs   r13d, ecx
0x180016c36  lea     r9, [rbp+140h+var_120]
0x180016c3a  lea     r8, aPhonemanufactu_0; "PhoneManufacturerModelName"
0x180016c41  lea     rdx, aSystemPlatform; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x180016c48  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016c4d  test    eax, eax
0x180016c4f  jns     short loc_180016C6C
0x180016c51  lea     r9, [rbp+140h+var_120]
0x180016c55  lea     r8, aSystemproductn; "SystemProductName"
0x180016c5c  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x180016c63  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016c68  test    eax, eax
0x180016c6a  js      short loc_180016C7C
0x180016c6c  lea     rcx, [rbp+140h+var_120]
0x180016c70  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016c75  mov     [rbp+140h+var_1C0], rax
0x180016c79  mov     r14, rax
0x180016c7c  lea     r9, [rbp+140h+var_140]
0x180016c80  lea     r8, aPhonemanufactu; "PhoneManufacturer"
0x180016c87  lea     rdx, aSystemPlatform; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x180016c8e  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016c93  test    eax, eax
0x180016c95  jns     short loc_180016CB2
0x180016c97  lea     r9, [rbp+140h+var_140]
0x180016c9b  lea     r8, aSystemmanufact; "SystemManufacturer"
0x180016ca2  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x180016ca9  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016cae  test    eax, eax
0x180016cb0  js      short loc_180016CC2
0x180016cb2  lea     rcx, [rbp+140h+var_140]
0x180016cb6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016cbb  mov     [rbp+140h+var_1B8], rax
0x180016cbf  mov     r15, rax
0x180016cc2  lea     rcx, [rbp+140h+var_A0]
0x180016cc9  call    ?GetOemSerialNumber@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcDeviceInfoHelper::GetOemSerialNumber(std::wstring *)
0x180016cce  test    eax, eax
0x180016cd0  js      short loc_180016CE5
0x180016cd2  lea     rcx, [rbp+140h+var_A0]
0x180016cd9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016cde  mov     r12, rax
0x180016ce1  mov     [rbp+140h+var_188], rax
0x180016ce5  lea     r9, [rbp+140h+var_C0]
0x180016cec  lea     r8, aEditionid; "EditionID"
0x180016cf3  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180016cfa  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016cff  test    eax, eax
0x180016d01  js      short loc_180016D13
0x180016d03  lea     rcx, [rbp+140h+var_C0]
0x180016d0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016d0f  mov     [rbp+140h+var_1B0], rax
0x180016d13  lea     r9, [rbp+140h+var_E0]
0x180016d17  lea     r8, aReleaseid; "ReleaseId"
0x180016d1e  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180016d25  call    ?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180016d2a  test    eax, eax
0x180016d2c  js      short loc_180016D3B
0x180016d2e  lea     rcx, [rbp+140h+var_E0]
0x180016d32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016d37  mov     [rbp+140h+var_1A8], rax
0x180016d3b  lea     rcx, [rsp+240h+Block]; unsigned __int16 **
0x180016d40  call    ?GetOsLocale@DdcDeviceInfoHelper@@CAJPEAPEAG@Z; DdcDeviceInfoHelper::GetOsLocale(ushort * *)
0x180016d45  lea     rcx, [rsp+240h+var_1D8]; unsigned __int16 **
0x180016d4a  call    ?GetShortOsVersion@DdcDeviceInfoHelper@@CAJPEAPEAG@Z; DdcDeviceInfoHelper::GetShortOsVersion(ushort * *)
0x180016d4f  lea     rcx, [rsp+240h+var_200]; int *
0x180016d54  call    ?DeviceBatteryCapable@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::DeviceBatteryCapable(int *)
0x180016d59  lea     rdx, [rsp+240h+var_200]
0x180016d5e  xor     ecx, ecx
0x180016d60  test    eax, eax
0x180016d62  cmovs   rdx, rcx
0x180016d66  mov     qword ptr [rsp+240h+var_1E0], rdx
0x180016d6b  lea     r8, [rsp+240h+var_1E8]
0x180016d70  lea     rdx, [rsp+240h+var_1EC]
0x180016d75  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180016d7b  lea     rcx, [rsp+240h+var_1FC]; unsigned int *
0x180016d80  call    ?GetOsSku@DdcDeviceInfoHelper@@CAJPEAK@Z; DdcDeviceInfoHelper::GetOsSku(ulong *)
0x180016d85  lea     rdx, [rsp+240h+var_1FC]
0x180016d8a  xor     ecx, ecx; struct _GUID *
0x180016d8c  test    eax, eax
0x180016d8e  cmovs   rdx, rcx
0x180016d92  mov     [rbp+140h+var_178], rdx
0x180016d96  lea     rdx, [rsp+240h+var_1F8]; enum _SL_GENUINE_STATE *
0x180016d9b  call    ?SLIsGenuineLocalWrapper@DdcDeviceInfoHelper@@CAJPEBU_GUID@@PEAW4_SL_GENUINE_STATE@@PEAU_tagSL_NONGENUINE_UI_OPTIONS@@@Z; DdcDeviceInfoHelper::SLIsGenuineLocalWrapper(_GUID const *,_SL_GENUINE_STATE *,_tagSL_NONGENUINE_UI_OPTIONS *)
0x180016da0  lea     rdx, [rsp+240h+var_1F8]
0x180016da5  xor     ecx, ecx
0x180016da7  test    eax, eax
0x180016da9  cmovs   rdx, rcx
0x180016dad  mov     [rbp+140h+var_170], rdx
0x180016db1  lea     rcx, [rsp+240h+var_1F4]; int *
0x180016db6  call    ?OsReactivationPolicyState@DdcDeviceInfoHelper@@CAJPEAH@Z; DdcDeviceInfoHelper::OsReactivationPolicyState(int *)
0x180016dbb  lea     rdx, [rsp+240h+var_1F4]
0x180016dc0  xor     ecx, ecx
0x180016dc2  test    eax, eax
0x180016dc4  cmovs   rdx, rcx
0x180016dc8  mov     [rbp+140h+var_168], rdx
0x180016dcc  lea     rcx, [rsp+240h+var_1C8]; struct _FILETIME *
0x180016dd1  call    ?GetLastMajorUpdateTime@DdcDeviceInfoHelper@@CAJPEAU_FILETIME@@@Z; DdcDeviceInfoHelper::GetLastMajorUpdateTime(_FILETIME *)
0x180016dd6  test    eax, eax
0x180016dd8  js      short loc_180016E08
0x180016dda  mov     r9, qword ptr [rsp+240h+var_1C8.dwLowDateTime]
0x180016ddf  lea     r8, aLlu; "%llu"
0x180016de6  mov     edx, 15h; unsigned __int64
0x180016deb  lea     rcx, [rbp+140h+var_80]; unsigned __int16 *
0x180016df2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016df7  lea     rcx, [rbp+140h+var_80]
0x180016dfe  test    eax, eax
0x180016e00  cmovs   rcx, rdi
0x180016e04  mov     [rbp+140h+var_1A0], rcx
0x180016e08  lea     rcx, [rbp+140h+var_100]
0x180016e0c  call    ?GetCommonTargetingAttributes@DdcDeviceInfoHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcDeviceInfoHelper::GetCommonTargetingAttributes(std::wstring &)
0x180016e11  test    eax, eax
0x180016e13  js      short loc_180016E22
0x180016e15  lea     rcx, [rbp+140h+var_100]
0x180016e19  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016e1e  mov     [rbp+140h+var_198], rax
0x180016e22  lea     r9, [rsp+240h+var_1F0]; unsigned int *
0x180016e27  lea     r8, aId; "Id"
0x180016e2e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016e35  call    ?GetDWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; DdcRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x180016e3a  lea     rdx, [rsp+240h+var_1F0]
0x180016e3f  xor     ecx, ecx
0x180016e41  test    eax, eax
0x180016e43  cmovs   rdx, rcx
0x180016e47  mov     qword ptr [rsp+240h+var_1C8.dwLowDateTime], rdx
0x180016e4c  mov     rdi, [rsp+240h+var_208]
0x180016e51  mov     rax, [rdi]
0x180016e54  mov     rbx, [rax+50h]
0x180016e58  lea     rcx, [rsp+240h+var_210]
0x180016e5d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e62  lea     rdx, [rbp+140h+var_180]
0x180016e66  lea     rcx, [rbp+140h+hstringHeader]
0x180016e6a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016e6f  nop
0x180016e70  lea     r8, [rsp+240h+var_210]
0x180016e75  mov     rdx, [rax+18h]
0x180016e79  mov     rcx, rdi
0x180016e7c  mov     rax, rbx
0x180016e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e84  mov     ebx, eax
0x180016e86  test    eax, eax
0x180016e88  jns     short loc_180016EB0
0x180016e8a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016e91  jz      loc_180018305
0x180016e97  lea     rax, aChrPjsonvalues_37; "CHR(pJsonValueStatics->CreateStringValu"...
0x180016e9e  mov     [rsp+240h+var_218], rax
0x180016ea3  mov     [rsp+240h+var_220], 1AEh
0x180016eab  jmp     loc_1800182F6
0x180016eb0  mov     rax, [rsi]
0x180016eb3  mov     rdi, [rax+38h]
0x180016eb7  mov     rbx, [rsp+240h+var_210]
0x180016ebc  lea     rdx, off_18002B608; "OS"
0x180016ec3  lea     rcx, [rbp+140h+hstringHeader]
0x180016ec7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016ecc  nop
0x180016ecd  mov     r8, rbx
0x180016ed0  mov     rdx, [rax+18h]
0x180016ed4  mov     rcx, rsi
0x180016ed7  mov     rax, rdi
0x180016eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016edf  mov     ebx, eax
0x180016ee1  test    eax, eax
0x180016ee3  jns     short loc_180016F0B
0x180016ee5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016eec  jz      loc_180018305
0x180016ef2  lea     rax, aChrPdeviceinfo_17; "CHR(pDeviceInfo->SetNamedValue(HStringR"...
0x180016ef9  mov     [rsp+240h+var_218], rax
0x180016efe  mov     [rsp+240h+var_220], 1AFh
0x180016f06  jmp     loc_1800182F6
0x180016f0b  mov     rdi, [rsp+240h+var_208]
0x180016f10  mov     rax, [rdi]
0x180016f13  mov     rbx, [rax+48h]
0x180016f17  lea     rcx, [rsp+240h+var_210]
0x180016f1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016f21  movd    xmm1, [rbp+140h+var_190]
0x180016f26  cvtdq2pd xmm1, xmm1
0x180016f2a  lea     r8, [rsp+240h+var_210]
0x180016f2f  mov     rcx, rdi
0x180016f32  mov     rax, rbx
0x180016f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3a  mov     ebx, eax
0x180016f3c  test    eax, eax
0x180016f3e  jns     short loc_180016F66
0x180016f40  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016f47  jz      loc_180018305
0x180016f4d  lea     rax, aChrPjsonvalues_6; "CHR(pJsonValueStatics->CreateNumberValu"...
0x180016f54  mov     [rsp+240h+var_218], rax
0x180016f59  mov     [rsp+240h+var_220], 1B2h
0x180016f61  jmp     loc_1800182F6
0x180016f66  mov     rax, [rsi]
0x180016f69  mov     rdi, [rax+38h]
0x180016f6d  mov     rbx, [rsp+240h+var_210]
0x180016f72  lea     rdx, off_18002B638; "PowerPlatformRole"
0x180016f79  lea     rcx, [rbp+140h+hstringHeader]
0x180016f7d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180016f82  nop
0x180016f83  mov     r8, rbx
0x180016f86  mov     rdx, [rax+18h]
0x180016f8a  mov     rcx, rsi
0x180016f8d  mov     rax, rdi
0x180016f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f95  mov     ebx, eax
0x180016f97  test    eax, eax
0x180016f99  jns     short loc_180016FC1
0x180016f9b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180016fa2  jz      loc_180018305
0x180016fa8  lea     rax, aChrPdeviceinfo_11; "CHR(pDeviceInfo->SetNamedValue(HStringR"...
0x180016faf  mov     [rsp+240h+var_218], rax
0x180016fb4  mov     [rsp+240h+var_220], 1B3h
0x180016fbc  jmp     loc_1800182F6
  ... truncated ...
```
