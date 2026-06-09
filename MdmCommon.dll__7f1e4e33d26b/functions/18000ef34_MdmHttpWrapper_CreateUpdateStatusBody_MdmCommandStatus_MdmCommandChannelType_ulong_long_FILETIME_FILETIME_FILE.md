# MdmHttpWrapper::CreateUpdateStatusBody(MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000ef34`
- end: `0x180010737`
- name: `?CreateUpdateStatusBody@MdmHttpWrapper@@CAJW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@3PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@5555PEAH666AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `6147`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, unsigned int *, __int64, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, struct Windows::Data::Json::IJsonValue *, _DWORD *, _DWORD *, _DWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012038`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001550`
- `0x18000611c`
- `0x18000624c`
- `0x180006274`
- `0x180006548`
- `0x18000acf4`
- `0x18000ad84`
- `0x18000b350`
- `0x18000ba7c`
- `0x18000ef34`
- `0x180010740`
- `0x180011414`
- `0x18001d510`
- `0x18001d51c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800103e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800103e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f31a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f50e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fa02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fb0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fc34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fdcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ffb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001017b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800102c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f069`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f220`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f31a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f50e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f978`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fa02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fb0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fc34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fcb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fdcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ffb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001017b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800102c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f70e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f70e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000f145`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000f145`

## string_xrefs

- `0x18000f11c`: `Windows.Data.Json.JsonValue`
- `0x18000fc2d`: `Windows.Data.Json.JsonValue`
- `0x18000fd45`: `Windows.Data.Json.JsonValue`
- `0x18000f062`: `Windows.Data.Json.JsonObject`
- `0x18000f0aa`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`
- `0x18000f0e9`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))`
- `0x18000f164`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001036a`: `CHR(pJsonObject.As(&pJsonObjectAsValue))`
- `0x1800103c2`: `CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))`
- `0x18000f1d6`: `CHR(pJsonValueStatics->CreateNumberValue((DWORD)eCommandStatus, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f25e`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"StatusCode").Get(), pJsonValue.Get()))`
- `0x18000f2d0`: `CHR(pJsonValueStatics->CreateNumberValue((DWORD)eCommandSource, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f358`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ChannelType").Get(), pJsonValue.Get()))`
- `0x18000f3ca`: `CHR(pJsonValueStatics->CreateNumberValue(dwRetries, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f452`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Retries").Get(), pJsonValue.Get()))`
- `0x18000f4c4`: `CHR(pJsonValueStatics->CreateNumberValue((DWORD)hrErrorCode, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f54c`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ErrorCode").Get(), pJsonValue.Get()))`
- `0x18000f668`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f806`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f9b8`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000fb4b`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000f6f0`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ReceivedTime").Get(), pJsonValue.Get()))`
- `0x18000f849`: `UpdatedTime`
- `0x18000f88e`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"UpdatedTime").Get(), pJsonValue.Get()))`
- `0x18000fa40`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"WorkStartedTime").Get(), pJsonValue.Get()))`
- `0x18000fcf5`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"WorkStartedTime").Get(), pJsonValue.Get()))`
- `0x18000fbd7`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"WorkFinishedTime").Get(), pJsonValue.Get()))`
- `0x18000fe0d`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"WorkFinishedTime").Get(), pJsonValue.Get()))`
- `0x18000fc6d`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000fd85`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000fe5f`: `CHR(CreateLocationEntity(pLocation, MdmLocationTechnique_Active, pJsonLocation.GetAddressOf()))`
- `0x18000fee7`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"Location").Get(), pJsonLocation.Get()))`
- `0x18000ff68`: `CHR(pJsonValueStatics->CreateNumberValue(dBatteryLevel, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18000fff0`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"BatteryLevel").Get(), pJsonValue.Get()))`
- `0x180010084`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"AuthorizedCids").Get(), pAuthorizedCids))`
- `0x180010131`: `CHR(CreateConnectedAccountsEntity(pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x1800101b9`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"ConnectedAccounts").Get(), pJsonValue.Get()))`
- `0x18001027e`: `CHR(pJsonValueStatics->CreateNumberValue(dwStatusFlags, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x180010300`: `CHR(pJsonObject->SetNamedValue(HStringReference(L"StatusFlags").Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateUpdateStatusBody(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        unsigned int *a8,
        __int64 a9,
        struct Windows::Data::Json::IJsonValue *a10,
        struct Windows::Data::Json::IJsonValue *a11,
        struct Windows::Data::Json::IJsonValue *a12,
        struct Windows::Data::Json::IJsonValue *a13,
        _DWORD *a14,
        _DWORD *a15,
        _DWORD *a16,
        _DWORD *a17,
        __int64 a18)
{
  int v18; // ecx
  __int64 v19; // rdx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int ActivationFactory; // edi
  int v24; // eax
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v29)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v30; // r14
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  __int64 *v34; // rbx
  __int64 (__fastcall *v35)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue *v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v38)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v39; // r14
  HRESULT v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  __int64 *v43; // rbx
  __int64 (__fastcall *v44)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue *v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v47)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v48; // r14
  HRESULT v49; // eax
  int v50; // edx
  unsigned int v51; // r8d
  __int64 *v52; // rbx
  __int64 (__fastcall *v53)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue *v54; // rcx
  __int64 (__fastcall ***v55)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v56)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v57; // r14
  HRESULT v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  unsigned int v61; // r8d
  __int64 *v62; // rbx
  __int64 v63; // rdi
  struct Windows::Data::Json::IJsonValue *v64; // rcx
  unsigned __int64 v65; // r13
  unsigned __int64 v66; // rdx
  HRESULT v67; // eax
  int v68; // edx
  unsigned int v69; // r8d
  __int64 (__fastcall ***v70)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v71)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v72; // r14
  HRESULT v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  unsigned int v76; // r8d
  __int64 *v77; // rbx
  __int64 v78; // rdi
  struct Windows::Data::Json::IJsonValue *v79; // rcx
  unsigned __int64 v80; // rdx
  HRESULT v81; // eax
  int v82; // edx
  unsigned int v83; // r8d
  __int64 (__fastcall ***v84)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v85)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v86; // r14
  HRESULT v87; // eax
  int v88; // edx
  unsigned int v89; // r8d
  _QWORD *v90; // r15
  unsigned int v91; // r8d
  __int64 *v92; // rbx
  __int64 v93; // rdi
  struct Windows::Data::Json::IJsonValue *v94; // rcx
  unsigned __int64 v95; // rdx
  HRESULT v96; // eax
  int v97; // edx
  unsigned int v98; // r8d
  __int64 (__fastcall ***v99)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v100)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v101; // r14
  HRESULT v102; // eax
  int v103; // edx
  unsigned int v104; // r8d
  unsigned int v105; // r8d
  __int64 *v106; // rbx
  __int64 v107; // rdi
  struct Windows::Data::Json::IJsonValue *v108; // rcx
  unsigned __int64 v109; // rdx
  HRESULT v110; // eax
  int v111; // edx
  unsigned int v112; // r8d
  __int64 (__fastcall ***v113)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v114)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v115; // r14
  HRESULT v116; // eax
  int v117; // edx
  unsigned int v118; // r8d
  struct Windows::Data::Json::IJsonValue *v119; // rcx
  HRESULT v120; // eax
  int v121; // edx
  unsigned int v122; // r8d
  __int64 (__fastcall ***v123)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v124)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v125; // r14
  HRESULT v126; // eax
  int v127; // edx
  unsigned int v128; // r8d
  struct Windows::Data::Json::IJsonValue *v129; // rcx
  HRESULT v130; // eax
  int v131; // edx
  unsigned int v132; // r8d
  __int64 (__fastcall ***v133)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v134)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v135; // r14
  HRESULT v136; // eax
  int v137; // edx
  unsigned int v138; // r8d
  __int64 (__fastcall ***v139)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v140)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 v141; // r14
  HRESULT v142; // eax
  int v143; // edx
  unsigned int v144; // r8d
  __int64 v145; // rdx
  __int64 *v146; // rbx
  __int64 (__fastcall *v147)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **); // rdi
  struct Windows::Data::Json::IJsonValue *v148; // rcx
  __int64 (__fastcall ***v149)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v150)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v151; // r14
  HRESULT v152; // eax
  int v153; // edx
  unsigned int v154; // r8d
  __int64 v155; // r14
  __int64 (__fastcall ***v156)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v157)(_QWORD, _QWORD, _QWORD); // rdi
  HRESULT v158; // eax
  int v159; // edx
  unsigned int v160; // r8d
  struct Windows::Data::Json::IJsonValue *v161; // rbx
  struct Windows::Data::Json::IJsonValue *v162; // rdi
  struct Windows::Data::Json::IJsonValue *v163; // r14
  struct Windows::Data::Json::IJsonValue *v164; // r15
  struct Windows::Data::Json::IJsonValue *v165; // rcx
  __int64 (__fastcall ***v166)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v167)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v168; // r14
  HRESULT v169; // eax
  int v170; // edx
  unsigned int v171; // r8d
  unsigned int v172; // ebx
  __int64 *v173; // rdi
  __int64 (__fastcall *v174)(__int64 *, _QWORD, struct Windows::Data::Json::IJsonValue **); // r15
  struct Windows::Data::Json::IJsonValue *v175; // rcx
  __int64 (__fastcall ***v176)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall **v177)(_QWORD, _QWORD, _QWORD); // rdi
  struct Windows::Data::Json::IJsonValue *v178; // r15
  HRESULT v179; // eax
  int v180; // edx
  unsigned int v181; // r8d
  __int64 (__fastcall ***v182)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v183)(_QWORD, GUID *, _QWORD **); // rdi
  _QWORD *v184; // rcx
  _QWORD *v185; // rdi
  __int64 (__fastcall *v186)(_QWORD *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v188; // r12
  unsigned __int64 v189; // r15
  char *v190; // r14
  __int64 v191; // rbx
  __int64 v192; // rdx
  size_t v193; // rcx
  _QWORD *v194; // r14
  void *v195; // rax
  __int64 v196; // rax
  _QWORD *v197; // rbx
  char *v198; // rax
  char *v199; // rcx
  __int64 v200; // rcx
  __int64 *v201; // rcx
  struct Windows::Data::Json::IJsonValue *v202; // rcx
  _QWORD *v203; // rcx
  __int64 (__fastcall ***v204)(_QWORD, _QWORD, _QWORD); // rcx
  char v206; // [rsp+20h] [rbp-138h]
  const char *v207; // [rsp+28h] [rbp-130h]
  struct Windows::Data::Json::IJsonValue *v208; // [rsp+30h] [rbp-128h] BYREF
  __int64 (__fastcall ***v209)(_QWORD, GUID *, _QWORD **); // [rsp+38h] [rbp-120h] BYREF
  __int64 *v210; // [rsp+40h] [rbp-118h] BYREF
  __int64 v211; // [rsp+48h] [rbp-110h]
  HSTRING v212; // [rsp+50h] [rbp-108h] BYREF
  _QWORD *v213; // [rsp+58h] [rbp-100h] BYREF
  __int64 v214; // [rsp+60h] [rbp-F8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-F0h] BYREF
  double v216; // [rsp+70h] [rbp-E8h] BYREF
  _QWORD *v217; // [rsp+78h] [rbp-E0h]
  __int64 v218; // [rsp+80h] [rbp-D8h]
  unsigned int *v219; // [rsp+88h] [rbp-D0h]
  __int64 v220; // [rsp+90h] [rbp-C8h]
  struct Windows::Data::Json::IJsonValue *v221; // [rsp+98h] [rbp-C0h]
  struct Windows::Data::Json::IJsonValue *v222; // [rsp+A0h] [rbp-B8h]
  struct Windows::Data::Json::IJsonValue *v223; // [rsp+A8h] [rbp-B0h]
  struct Windows::Data::Json::IJsonValue *v224; // [rsp+B0h] [rbp-A8h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-88h] BYREF
  WCHAR sourceString[24]; // [rsp+D8h] [rbp-80h] BYREF

  v217 = a6;
  v18 = a7;
  v218 = a7;
  v219 = a8;
  v220 = a9;
  v221 = a10;
  v222 = a11;
  v223 = a12;
  LODWORD(v19) = (_DWORD)a13;
  v224 = a13;
  v211 = a18;
  SystemTimeAsFileTime = 0;
  v209 = 0;
  v213 = 0;
  v208 = 0;
  v210 = 0;
  v214 = 0;
  v212 = 0;
  memset(sourceString, 0, 42);
  v216 = DOUBLE_N1_0;
  if ( a6 )
  {
    if ( a7 )
      goto LABEL_3;
LABEL_6:
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_232;
    v207 = "CBR((pftWorkStarted != nullptr && pftWorkFinished != nullptr) || (pftWorkStarted == nullptr && pftWorkFinished == nullptr))";
    v206 = -45;
    goto LABEL_8;
  }
  if ( a7 )
    goto LABEL_6;
LABEL_3:
  string = 0;
  v20 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    __debugbreak();
  }
  v24 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v209);
  ActivationFactory = v24;
  if ( v24 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v207 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), pJsonObject.GetAddressOf()))";
      v206 = -43;
LABEL_8:
      McTemplateU0dsqs_EventWriteTransfer(
        v18,
        v19,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
        v206,
        (__int64)v207);
      goto LABEL_232;
    }
    goto LABEL_232;
  }
  string = 0;
  v25 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v210);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **))(*v210 + 72))(
                          v210,
                          v19,
                          &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateNumberValue((DWORD)eCommandStatus, pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -40;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v29 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v30 = v208;
    string = 0;
    v31 = WindowsCreateStringReference(L"StatusCode", 0xAu, &hstringHeader, &string);
    if ( v31 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v29)[7](
                          v28,
                          string,
                          v30);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"StatusCode\").Get(), pJsonValue.Get()))";
        v206 = -39;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v34 = v210;
    v35 = *(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **))(*v210 + 72);
    v36 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *, _QWORD))(*(_QWORD *)v36 + 16LL))(
        v36,
        *(_QWORD *)v36);
    }
    ActivationFactory = v35(v34, v19, &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateNumberValue((DWORD)eCommandSource, pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -38;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v38 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v39 = v208;
    string = 0;
    v40 = WindowsCreateStringReference(L"ChannelType", 0xBu, &hstringHeader, &string);
    if ( v40 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v38)[7](
                          v37,
                          string,
                          v39);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ChannelType\").Get(), pJsonValue.Get()))";
        v206 = -37;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v43 = v210;
    v44 = *(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **))(*v210 + 72);
    v45 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *, _QWORD))(*(_QWORD *)v45 + 16LL))(
        v45,
        *(_QWORD *)v45);
    }
    ActivationFactory = v44(v43, v19, &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateNumberValue(dwRetries, pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -35;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v47 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v48 = v208;
    string = 0;
    v49 = WindowsCreateStringReference(L"Retries", 7u, &hstringHeader, &string);
    if ( v49 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v49, v50, v51);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v47)[7](
                          v46,
                          string,
                          v48);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Retries\").Get(), pJsonValue.Get()))";
        v206 = -34;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v52 = v210;
    v53 = *(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **))(*v210 + 72);
    v54 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *, _QWORD))(*(_QWORD *)v54 + 16LL))(
        v54,
        *(_QWORD *)v54);
    }
    ActivationFactory = v53(v52, v19, &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateNumberValue((DWORD)hrErrorCode, pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -33;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v55 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v56 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v57 = v208;
    string = 0;
    v58 = WindowsCreateStringReference(L"ErrorCode", 9u, &hstringHeader, &string);
    if ( v58 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v56)[7](
                          v55,
                          string,
                          v57);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ErrorCode\").Get(), pJsonValue.Get()))";
        v206 = -32;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    ActivationFactory = StringCchPrintfW(sourceString, 0x15u, L"%llu", a5);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(StringCchPrintfW(wszTimestamp, (sizeof(*RtlpNumberOf(wszTimestamp))), L\"%llu\", ftConverter.ullTime))";
        v206 = -29;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v62 = v210;
    v63 = *v210;
    v64 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = -1;
    v66 = -1;
    do
      ++v66;
    while ( sourceString[v66] );
    if ( v66 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v66, v61);
      __debugbreak();
    }
    if ( (int)v66 + 1 < (unsigned int)v66 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v66, v61);
      __debugbreak();
    }
    v67 = WindowsCreateStringReference(sourceString, v66, &hstringHeader, &string);
    if ( v67 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v67, v68, v69);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct Windows::Data::Json::IJsonValue **))(v63 + 80))(
                          v62,
                          string,
                          &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -28;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v70 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v71 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v72 = v208;
    string = 0;
    v73 = WindowsCreateStringReference(L"ReceivedTime", 0xCu, &hstringHeader, &string);
    if ( v73 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v71)[7](
                          v70,
                          string,
                          v72);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ReceivedTime\").Get(), pJsonValue.Get()))";
        v206 = -27;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    ActivationFactory = StringCchPrintfW(sourceString, 0x15u, L"%llu", SystemTimeAsFileTime);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(StringCchPrintfW(wszTimestamp, (sizeof(*RtlpNumberOf(wszTimestamp))), L\"%llu\", ftConverter.ullTime))";
        v206 = -23;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v77 = v210;
    v78 = *v210;
    v79 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = -1;
    do
      ++v80;
    while ( sourceString[v80] );
    if ( v80 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v80, v76);
      JUMPOUT(0x180010736LL);
    }
    if ( (int)v80 + 1 < (unsigned int)v80 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v80, v76);
      __debugbreak();
    }
    v81 = WindowsCreateStringReference(sourceString, v80, &hstringHeader, &string);
    if ( v81 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v81, v82, v83);
      __debugbreak();
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct Windows::Data::Json::IJsonValue **))(v78 + 80))(
                          v77,
                          string,
                          &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = -22;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v84 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v85 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v86 = v208;
    string = 0;
    v87 = WindowsCreateStringReference(L"UpdatedTime", 0xBu, &hstringHeader, &string);
    if ( v87 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v87, v88, v89);
      __debugbreak();
    }
    ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v85)[7](
                          v84,
                          string,
                          v86);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"UpdatedTime\").Get(), pJsonValue.Get()))";
        v206 = -21;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    if ( v217 && (v90 = (_QWORD *)v218) != 0 )
    {
      ActivationFactory = StringCchPrintfW(sourceString, 0x15u, L"%llu", *v217);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(StringCchPrintfW(wszTimestamp, (sizeof(*RtlpNumberOf(wszTimestamp))), L\"%llu\", ftConverter.ullTime))";
          v206 = -16;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v92 = v210;
      v93 = *v210;
      v94 = v208;
      if ( v208 )
      {
        v208 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v94 + 16LL))(v94);
      }
      v95 = -1;
      do
        ++v95;
      while ( sourceString[v95] );
      if ( v95 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v95, v91);
        __debugbreak();
      }
      if ( (int)v95 + 1 < (unsigned int)v95 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v95, v91);
        __debugbreak();
      }
      v96 = WindowsCreateStringReference(sourceString, v95, &hstringHeader, &string);
      if ( v96 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v96, v97, v98);
        __debugbreak();
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct Windows::Data::Json::IJsonValue **))(v93 + 80))(
                            v92,
                            string,
                            &v208);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
          v206 = -15;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v99 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v100 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v101 = v208;
      string = 0;
      v102 = WindowsCreateStringReference(L"WorkStartedTime", 0xFu, &hstringHeader, &string);
      if ( v102 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v102, v103, v104);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v100)[7](
                            v99,
                            string,
                            v101);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"WorkStartedTime\").Get(), pJsonValue.Get()))";
          v206 = -14;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      ActivationFactory = StringCchPrintfW(sourceString, 0x15u, L"%llu", *v90);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(StringCchPrintfW(wszTimestamp, (sizeof(*RtlpNumberOf(wszTimestamp))), L\"%llu\", ftConverter.ullTime))";
          v206 = -11;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v106 = v210;
      v107 = *v210;
      v108 = v208;
      if ( v208 )
      {
        v208 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v108 + 16LL))(v108);
      }
      v109 = -1;
      do
        ++v109;
      while ( sourceString[v109] );
      if ( v109 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v109, v105);
        __debugbreak();
      }
      if ( (int)v109 + 1 < (unsigned int)v109 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v109, v105);
        __debugbreak();
      }
      v110 = WindowsCreateStringReference(sourceString, v109, &hstringHeader, &string);
      if ( v110 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v110, v111, v112);
        __debugbreak();
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct Windows::Data::Json::IJsonValue **))(v107 + 80))(
                            v106,
                            string,
                            &v208);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonValueStatics->CreateStringValue(HStringReference(wszTimestamp).Get(), pJsonValue.ReleaseAndGetAddressOf()))";
          v206 = -10;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v113 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v114 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v115 = v208;
      string = 0;
      v116 = WindowsCreateStringReference(L"WorkFinishedTime", 0x10u, &hstringHeader, &string);
      if ( v116 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v116, v117, v118);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v114)[7](
                            v113,
                            string,
                            v115);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"WorkFinishedTime\").Get(), pJsonValue.Get()))";
          v206 = -9;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
    }
    else
    {
      v119 = v208;
      if ( v208 )
      {
        v208 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v119 + 16LL))(v119);
      }
      string = 0;
      v120 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v120 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v120, v121, v122);
        __debugbreak();
      }
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)string, &v208);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Relea"
                 "seAndGetAddressOf()))";
          v206 = -5;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v123 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v124 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v125 = v208;
      string = 0;
      v126 = WindowsCreateStringReference(L"WorkStartedTime", 0xFu, &hstringHeader, &string);
      if ( v126 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v126, v127, v128);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v124)[7](
                            v123,
                            string,
                            v125);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"WorkStartedTime\").Get(), pJsonValue.Get()))";
          v206 = -4;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v129 = v208;
      if ( v208 )
      {
        v208 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v129 + 16LL))(v129);
      }
      string = 0;
      v130 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v130 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v130, v131, v132);
        __debugbreak();
      }
      ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonValue>((__int64)string, &v208);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValue.Relea"
                 "seAndGetAddressOf()))";
          v206 = -2;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v133 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v134 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v135 = v208;
      string = 0;
      v136 = WindowsCreateStringReference(L"WorkFinishedTime", 0x10u, &hstringHeader, &string);
      if ( v136 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v136, v137, v138);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v134)[7](
                            v133,
                            string,
                            v135);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"WorkFinishedTime\").Get(), pJsonValue.Get()))";
          v206 = -1;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
    }
    if ( v219 )
    {
      ActivationFactory = MdmHttpWrapper::CreateLocationEntity(v219, 0, &v214);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(CreateLocationEntity(pLocation, MdmLocationTechnique_Active, pJsonLocation.GetAddressOf()))";
          v206 = 4;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v139 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v140 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v141 = v214;
      string = 0;
      v142 = WindowsCreateStringReference(L"Location", 8u, &hstringHeader, &string);
      if ( v142 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v142, v143, v144);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v140)[7](v139, string, v141);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"Location\").Get(), pJsonLocation.Get()))";
          v206 = 5;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      MdmHttpWrapper::GetBatteryLevel(&v216);
      v146 = v210;
      v147 = *(__int64 (__fastcall **)(__int64 *, __int64, struct Windows::Data::Json::IJsonValue **))(*v210 + 72);
      v148 = v208;
      if ( v208 )
      {
        v208 = 0;
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v148 + 16LL))(v148);
      }
      ActivationFactory = v147(v146, v145, &v208);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonValueStatics->CreateNumberValue(dBatteryLevel, pJsonValue.ReleaseAndGetAddressOf()))";
          v206 = 12;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v149 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v150 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      v151 = v208;
      string = 0;
      v152 = WindowsCreateStringReference(L"BatteryLevel", 0xCu, &hstringHeader, &string);
      if ( v152 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v152, v153, v154);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v150)[7](
                            v149,
                            string,
                            v151);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"BatteryLevel\").Get(), pJsonValue.Get()))";
          v206 = 13;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
    }
    v155 = v220;
    if ( v220 )
    {
      v156 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v157 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
      string = 0;
      v158 = WindowsCreateStringReference(L"AuthorizedCids", 0xEu, &hstringHeader, &string);
      if ( v158 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v158, v159, v160);
        __debugbreak();
      }
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, __int64))v157)[7](v156, string, v155);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"AuthorizedCids\").Get(), pAuthorizedCids))";
          v206 = 18;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
    }
    v161 = v221;
    if ( v221 )
    {
      v162 = v222;
      if ( v222 )
      {
        v163 = v223;
        if ( v223 )
        {
          v164 = v224;
          if ( v224 )
          {
            v165 = v208;
            if ( v208 )
            {
              v208 = 0;
              (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v165 + 16LL))(v165);
            }
            ActivationFactory = MdmHttpWrapper::CreateConnectedAccountsEntity(v161, v162, v163, v164, &v208);
            if ( ActivationFactory < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              {
                v207 = "CHR(CreateConnectedAccountsEntity(pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pJson"
                       "Value.ReleaseAndGetAddressOf()))";
                v206 = 23;
                goto LABEL_8;
              }
              goto LABEL_232;
            }
            v166 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
            v167 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
            v168 = v208;
            string = 0;
            v169 = WindowsCreateStringReference(L"ConnectedAccounts", 0x11u, &hstringHeader, &string);
            if ( v169 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v169, v170, v171);
              __debugbreak();
            }
            ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v167)[7](
                                  v166,
                                  string,
                                  v168);
            if ( ActivationFactory < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              {
                v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"ConnectedAccounts\").Get(), pJsonValue.Get()))";
                v206 = 24;
                goto LABEL_8;
              }
              goto LABEL_232;
            }
          }
        }
      }
    }
    v172 = 0;
    if ( a14 )
      v172 = *a14 == 0;
    if ( a15 && !*a15 )
      v172 |= 2u;
    if ( a16 && *a16 )
      v172 |= 4u;
    if ( a17 && *a17 )
      v172 |= 8u;
    v173 = v210;
    v174 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct Windows::Data::Json::IJsonValue **))(*v210 + 72);
    v175 = v208;
    if ( v208 )
    {
      v208 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *, _QWORD))(*(_QWORD *)v175 + 16LL))(
        v175,
        *(_QWORD *)v175);
    }
    ActivationFactory = v174(v173, v172, &v208);
    if ( ActivationFactory < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v207 = "CHR(pJsonValueStatics->CreateNumberValue(dwStatusFlags, pJsonValue.ReleaseAndGetAddressOf()))";
        v206 = 47;
        goto LABEL_8;
      }
      goto LABEL_232;
    }
    v176 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
    v177 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v209;
    v178 = v208;
    string = 0;
    v179 = WindowsCreateStringReference(L"StatusFlags", 0xBu, &hstringHeader, &string);
    if ( v179 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v179, v180, v181);
    }
    else
    {
      ActivationFactory = ((__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Data::Json::IJsonValue *))v177)[7](
                            v176,
                            string,
                            v178);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject->SetNamedValue(HStringReference(L\"StatusFlags\").Get(), pJsonValue.Get()))";
          v206 = 48;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v182 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
      v183 = **v209;
      v184 = v213;
      if ( v213 )
      {
        v213 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v184 + 16LL))(v184, *v184);
      }
      ActivationFactory = v183(v182, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v213);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObject.As(&pJsonObjectAsValue))";
          v206 = 50;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      v185 = v213;
      v186 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v213 + 56LL);
      WindowsDeleteString(v212);
      v212 = 0;
      ActivationFactory = v186(v185, &v212);
      if ( ActivationFactory < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v207 = "CHR(pJsonObjectAsValue->Stringify(hstrBody.GetAddressOf()))";
          v206 = 51;
          goto LABEL_8;
        }
        goto LABEL_232;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v212, 0);
      v188 = StringRawBuffer;
      do
        ++v65;
      while ( StringRawBuffer[v65] );
      v189 = *(_QWORD *)(v211 + 24);
      if ( v65 <= v189 )
      {
        if ( v189 <= 7 )
          v190 = (char *)v211;
        else
          v190 = *(char **)v211;
        *(_QWORD *)(v211 + 16) = v65;
        memmove_0(v190, StringRawBuffer, 2 * v65);
        *(_WORD *)&v190[2 * v65] = 0;
        goto LABEL_232;
      }
      v191 = 0x7FFFFFFFFFFFFFFELL;
      if ( v65 <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( (v65 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v192 = v189 >> 1, v189 <= 0x7FFFFFFFFFFFFFFELL - (v189 >> 1)) )
        {
          v191 = v65 | 7;
          if ( (v65 | 7) < v192 + v189 )
            v191 = v192 + v189;
          if ( (unsigned __int64)(v191 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            __scrt_throw_std_bad_array_new_length();
          v193 = 2 * (v191 + 1);
          if ( !v193 )
          {
            v194 = 0;
            goto LABEL_225;
          }
        }
        else
        {
          v193 = -2;
        }
        if ( v193 < 0x1000 )
        {
          v194 = operator new(v193);
        }
        else
        {
          if ( v193 + 39 < v193 )
            __scrt_throw_std_bad_array_new_length();
          v195 = operator new(v193 + 39);
          if ( !v195 )
LABEL_228:
            __fastfail(5u);
          v194 = (_QWORD *)(((unsigned __int64)v195 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v194 - 1) = v195;
        }
LABEL_225:
        v196 = v211;
        *(_QWORD *)(v211 + 16) = v65;
        *(_QWORD *)(v196 + 24) = v191;
        memcpy_0(v194, v188, 2 * v65);
        *((_WORD *)v194 + v65) = 0;
        v197 = (_QWORD *)v211;
        if ( v189 > 7 )
        {
          v198 = *(char **)v211;
          if ( 2 * v189 + 2 < 0x1000 )
          {
            v199 = *(char **)v211;
          }
          else
          {
            v199 = (char *)*((_QWORD *)v198 - 1);
            if ( (unsigned __int64)(v198 - v199 - 8) > 0x1F )
              goto LABEL_228;
          }
          operator delete(v199);
        }
        *v197 = v194;
        goto LABEL_232;
      }
    }
    std::_Xlen_string();
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v207 = "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics."
           "GetAddressOf()))";
    v206 = -42;
    goto LABEL_8;
  }
LABEL_232:
  WindowsDeleteString(v212);
  v212 = 0;
  v200 = v214;
  if ( v214 )
  {
    v214 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v200 + 16LL))(v200);
  }
  v201 = v210;
  if ( v210 )
  {
    v210 = 0;
    (*(void (__fastcall **)(__int64 *))(*v201 + 16))(v201);
  }
  v202 = v208;
  if ( v208 )
  {
    v208 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v202 + 16LL))(v202);
  }
  v203 = v213;
  if ( v213 )
  {
    v213 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v203 + 16LL))(v203);
  }
  v204 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
  if ( v209 )
  {
    v209 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v204)[2])(v204);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000ef34  mov     r11, rsp
0x18000ef37  push    rbx
0x18000ef38  push    rsi
0x18000ef39  push    rdi
0x18000ef3a  push    r12
0x18000ef3c  push    r13
0x18000ef3e  push    r14
0x18000ef40  push    r15
0x18000ef42  sub     rsp, 120h
0x18000ef49  movaps  xmmword ptr [r11-48h], xmm6
0x18000ef4e  mov     rax, cs:__security_cookie
0x18000ef55  xor     rax, rsp
0x18000ef58  mov     [rsp+158h+var_50], rax
0x18000ef60  mov     r13d, r9d
0x18000ef63  mov     r12d, r8d
0x18000ef66  mov     r15d, edx
0x18000ef69  mov     r14d, ecx
0x18000ef6c  mov     rax, [rsp+158h+arg_28]
0x18000ef74  mov     [rsp+158h+var_E0], rax
0x18000ef79  mov     rcx, [rsp+158h+arg_30]
0x18000ef81  mov     [rsp+158h+var_D8], rcx
0x18000ef89  mov     rdx, [rsp+158h+arg_38]
0x18000ef91  mov     [rsp+158h+var_D0], rdx
0x18000ef99  mov     rdx, [rsp+158h+arg_40]
0x18000efa1  mov     [rsp+158h+var_C8], rdx
0x18000efa9  mov     rdx, [rsp+158h+arg_48]
0x18000efb1  mov     [rsp+158h+var_C0], rdx
0x18000efb9  mov     rdx, [rsp+158h+arg_50]
0x18000efc1  mov     [rsp+158h+var_B8], rdx
0x18000efc9  mov     rdx, [rsp+158h+arg_58]
0x18000efd1  mov     [rsp+158h+var_B0], rdx
0x18000efd9  mov     rdx, [rsp+158h+arg_60]
0x18000efe1  mov     [rsp+158h+var_A8], rdx
0x18000efe9  mov     rbx, [rsp+158h+arg_88]
0x18000eff1  mov     [rsp+158h+var_110], rbx
0x18000eff6  xor     esi, esi
0x18000eff8  mov     qword ptr [rsp+158h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18000effd  mov     [rsp+158h+var_120], rsi
0x18000f002  mov     [rsp+158h+var_100], rsi
0x18000f007  mov     [rsp+158h+var_128], rsi
0x18000f00c  mov     [rsp+158h+var_118], rsi
0x18000f011  mov     [rsp+158h+var_F8], rsi
0x18000f016  mov     [rsp+158h+var_108], rsi
0x18000f01b  xorps   xmm0, xmm0
0x18000f01e  movups  xmmword ptr [r11-80h], xmm0
0x18000f023  movups  xmmword ptr [r11-70h], xmm0
0x18000f028  movups  xmmword ptr [r11-66h], xmm0
0x18000f02d  movsd   xmm6, cs:__real@bff0000000000000
0x18000f035  movsd   [rsp+158h+var_E8], xmm6
0x18000f03b  test    rax, rax
0x18000f03e  jz      short loc_18000F079
0x18000f040  test    rcx, rcx
0x18000f043  jz      short loc_18000F07E
0x18000f045  mov     [rsp+158h+string], rsi
0x18000f04d  lea     r9, [rsp+158h+string]; string
0x18000f055  lea     r8, [rsp+158h+hstringHeader]; hstringHeader
0x18000f05d  mov     edx, 1Ch; length
0x18000f062  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000f069  call    cs:__imp_WindowsCreateStringReference
0x18000f06f  test    eax, eax
0x18000f071  js      loc_180010622
0x18000f077  jmp     short loc_18000F0BE
0x18000f079  test    rcx, rcx
0x18000f07c  jz      short loc_18000F045
0x18000f07e  mov     edi, 80070057h
0x18000f083  mov     r14d, 1
0x18000f089  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f090  jz      loc_18001054E
0x18000f096  lea     rax, aCbrPftworkstar; "CBR((pftWorkStarted != nullptr && pftWo"...
0x18000f09d  mov     [rsp+158h+var_130], rax
0x18000f0a2  mov     dword ptr [rsp+158h+var_138], 3D3h
0x18000f0aa  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000f0b1  mov     r8d, edi
0x18000f0b4  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f0b9  jmp     loc_18001054E
0x18000f0be  lea     rdx, [rsp+158h+var_120]
0x18000f0c3  mov     rcx, [rsp+158h+string]
0x18000f0cb  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18000f0d0  mov     edi, eax
0x18000f0d2  test    eax, eax
0x18000f0d4  jns     short loc_18000F0FF
0x18000f0d6  mov     r14d, 1
0x18000f0dc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f0e3  jz      loc_18001054E
0x18000f0e9  lea     rax, aChrActivateins_1; "CHR(ActivateInstance(HStringReference(R"...
0x18000f0f0  mov     [rsp+158h+var_130], rax
0x18000f0f5  mov     dword ptr [rsp+158h+var_138], 3D5h
0x18000f0fd  jmp     short loc_18000F0AA
0x18000f0ff  mov     [rsp+158h+string], rsi
0x18000f107  lea     r9, [rsp+158h+string]; string
0x18000f10f  lea     r8, [rsp+158h+hstringHeader]; hstringHeader
0x18000f117  mov     edx, 1Bh; length
0x18000f11c  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18000f123  call    cs:__imp_WindowsCreateStringReference
0x18000f129  test    eax, eax
0x18000f12b  js      loc_18001062A
0x18000f131  lea     r8, [rsp+158h+var_118]
0x18000f136  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000f13d  mov     rcx, [rsp+158h+string]
0x18000f145  call    cs:__imp_RoGetActivationFactory
0x18000f14b  mov     edi, eax
0x18000f14d  test    eax, eax
0x18000f14f  jns     short loc_18000F17D
0x18000f151  mov     r14d, 1
0x18000f157  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f15e  jz      loc_18001054E
0x18000f164  lea     rax, aChrGetactivati; "CHR(GetActivationFactory(HStringReferen"...
0x18000f16b  mov     [rsp+158h+var_130], rax
0x18000f170  mov     dword ptr [rsp+158h+var_138], 3D6h
0x18000f178  jmp     loc_18000F0AA
0x18000f17d  mov     rbx, [rsp+158h+var_118]
0x18000f182  mov     rax, [rbx]
0x18000f185  mov     rdi, [rax+48h]
0x18000f189  mov     rcx, [rsp+158h+var_128]
0x18000f18e  test    rcx, rcx
0x18000f191  jz      short loc_18000F1A5
0x18000f193  mov     [rsp+158h+var_128], rsi
0x18000f198  mov     rdx, [rcx]
0x18000f19b  mov     rax, [rdx+10h]
0x18000f19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a4  nop
0x18000f1a5  xorps   xmm1, xmm1
0x18000f1a8  cvtsi2sd xmm1, r14
0x18000f1ad  lea     r8, [rsp+158h+var_128]
0x18000f1b2  mov     rcx, rbx
0x18000f1b5  mov     rax, rdi
0x18000f1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1bd  mov     edi, eax
0x18000f1bf  test    eax, eax
0x18000f1c1  jns     short loc_18000F1EF
0x18000f1c3  mov     r14d, 1
0x18000f1c9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f1d0  jz      loc_18001054E
0x18000f1d6  lea     rax, aChrPjsonvalues_16; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000f1dd  mov     [rsp+158h+var_130], rax
0x18000f1e2  mov     dword ptr [rsp+158h+var_138], 3D8h
0x18000f1ea  jmp     loc_18000F0AA
0x18000f1ef  mov     rbx, [rsp+158h+var_120]
0x18000f1f4  mov     rdi, [rbx]
0x18000f1f7  mov     r14, [rsp+158h+var_128]
0x18000f1fc  mov     [rsp+158h+string], rsi
0x18000f204  lea     r9, [rsp+158h+string]; string
0x18000f20c  lea     r8, [rsp+158h+hstringHeader]; hstringHeader
0x18000f214  mov     edx, 0Ah; length
0x18000f219  lea     rcx, aStatuscode; "StatusCode"
0x18000f220  call    cs:__imp_WindowsCreateStringReference
0x18000f226  test    eax, eax
0x18000f228  js      loc_180010632
0x18000f22e  mov     r8, r14
0x18000f231  mov     rdx, [rsp+158h+string]
0x18000f239  mov     rcx, rbx
0x18000f23c  mov     rax, [rdi+38h]
0x18000f240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f245  mov     edi, eax
0x18000f247  test    eax, eax
0x18000f249  jns     short loc_18000F277
0x18000f24b  mov     r14d, 1
0x18000f251  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f258  jz      loc_18001054E
0x18000f25e  lea     rax, aChrPjsonobject_26; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f265  mov     [rsp+158h+var_130], rax
0x18000f26a  mov     dword ptr [rsp+158h+var_138], 3D9h
0x18000f272  jmp     loc_18000F0AA
0x18000f277  mov     rbx, [rsp+158h+var_118]
0x18000f27c  mov     rax, [rbx]
0x18000f27f  mov     rdi, [rax+48h]
0x18000f283  mov     rcx, [rsp+158h+var_128]
0x18000f288  test    rcx, rcx
0x18000f28b  jz      short loc_18000F29F
0x18000f28d  mov     [rsp+158h+var_128], rsi
0x18000f292  mov     rdx, [rcx]
0x18000f295  mov     rax, [rdx+10h]
0x18000f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f29e  nop
0x18000f29f  xorps   xmm1, xmm1
0x18000f2a2  cvtsi2sd xmm1, r15
0x18000f2a7  lea     r8, [rsp+158h+var_128]
0x18000f2ac  mov     rcx, rbx
0x18000f2af  mov     rax, rdi
0x18000f2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2b7  mov     edi, eax
0x18000f2b9  test    eax, eax
0x18000f2bb  jns     short loc_18000F2E9
0x18000f2bd  mov     r14d, 1
0x18000f2c3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f2ca  jz      loc_18001054E
0x18000f2d0  lea     rax, aChrPjsonvalues_9; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000f2d7  mov     [rsp+158h+var_130], rax
0x18000f2dc  mov     dword ptr [rsp+158h+var_138], 3DAh
0x18000f2e4  jmp     loc_18000F0AA
0x18000f2e9  mov     rbx, [rsp+158h+var_120]
0x18000f2ee  mov     rdi, [rbx]
0x18000f2f1  mov     r14, [rsp+158h+var_128]
0x18000f2f6  mov     [rsp+158h+string], rsi
0x18000f2fe  lea     r9, [rsp+158h+string]; string
0x18000f306  lea     r8, [rsp+158h+hstringHeader]; hstringHeader
0x18000f30e  mov     edx, 0Bh; length
0x18000f313  lea     rcx, aChanneltype; "ChannelType"
0x18000f31a  call    cs:__imp_WindowsCreateStringReference
0x18000f320  test    eax, eax
0x18000f322  js      loc_18001063A
0x18000f328  mov     r8, r14
0x18000f32b  mov     rdx, [rsp+158h+string]
0x18000f333  mov     rcx, rbx
0x18000f336  mov     rax, [rdi+38h]
0x18000f33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f33f  mov     edi, eax
0x18000f341  test    eax, eax
0x18000f343  jns     short loc_18000F371
0x18000f345  mov     r14d, 1
0x18000f34b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f352  jz      loc_18001054E
0x18000f358  lea     rax, aChrPjsonobject_8; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f35f  mov     [rsp+158h+var_130], rax
0x18000f364  mov     dword ptr [rsp+158h+var_138], 3DBh
0x18000f36c  jmp     loc_18000F0AA
0x18000f371  mov     rbx, [rsp+158h+var_118]
0x18000f376  mov     rax, [rbx]
0x18000f379  mov     rdi, [rax+48h]
0x18000f37d  mov     rcx, [rsp+158h+var_128]
0x18000f382  test    rcx, rcx
0x18000f385  jz      short loc_18000F399
0x18000f387  mov     [rsp+158h+var_128], rsi
0x18000f38c  mov     rdx, [rcx]
0x18000f38f  mov     rax, [rdx+10h]
0x18000f393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f398  nop
0x18000f399  xorps   xmm1, xmm1
0x18000f39c  cvtsi2sd xmm1, r12
0x18000f3a1  lea     r8, [rsp+158h+var_128]
0x18000f3a6  mov     rcx, rbx
0x18000f3a9  mov     rax, rdi
0x18000f3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b1  mov     edi, eax
0x18000f3b3  test    eax, eax
0x18000f3b5  jns     short loc_18000F3E3
0x18000f3b7  mov     r14d, 1
0x18000f3bd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f3c4  jz      loc_18001054E
0x18000f3ca  lea     rax, aChrPjsonvalues_5; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000f3d1  mov     [rsp+158h+var_130], rax
0x18000f3d6  mov     dword ptr [rsp+158h+var_138], 3DDh
0x18000f3de  jmp     loc_18000F0AA
0x18000f3e3  mov     rbx, [rsp+158h+var_120]
0x18000f3e8  mov     rdi, [rbx]
0x18000f3eb  mov     r14, [rsp+158h+var_128]
0x18000f3f0  mov     [rsp+158h+string], rsi
0x18000f3f8  lea     r9, [rsp+158h+string]; string
0x18000f400  lea     r8, [rsp+158h+hstringHeader]; hstringHeader
0x18000f408  mov     edx, 7; length
0x18000f40d  lea     rcx, aRetries; "Retries"
0x18000f414  call    cs:__imp_WindowsCreateStringReference
0x18000f41a  test    eax, eax
0x18000f41c  js      loc_180010642
0x18000f422  mov     r8, r14
0x18000f425  mov     rdx, [rsp+158h+string]
0x18000f42d  mov     rcx, rbx
0x18000f430  mov     rax, [rdi+38h]
0x18000f434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f439  mov     edi, eax
0x18000f43b  test    eax, eax
0x18000f43d  jns     short loc_18000F46B
0x18000f43f  mov     r14d, 1
0x18000f445  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f44c  jz      loc_18001054E
0x18000f452  lea     rax, aChrPjsonobject_24; "CHR(pJsonObject->SetNamedValue(HStringR"...
0x18000f459  mov     [rsp+158h+var_130], rax
0x18000f45e  mov     dword ptr [rsp+158h+var_138], 3DEh
0x18000f466  jmp     loc_18000F0AA
0x18000f46b  mov     rbx, [rsp+158h+var_118]
0x18000f470  mov     rax, [rbx]
0x18000f473  mov     rdi, [rax+48h]
0x18000f477  mov     rcx, [rsp+158h+var_128]
0x18000f47c  test    rcx, rcx
0x18000f47f  jz      short loc_18000F493
0x18000f481  mov     [rsp+158h+var_128], rsi
0x18000f486  mov     rdx, [rcx]
0x18000f489  mov     rax, [rdx+10h]
0x18000f48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f492  nop
0x18000f493  xorps   xmm1, xmm1
0x18000f496  cvtsi2sd xmm1, r13
0x18000f49b  lea     r8, [rsp+158h+var_128]
0x18000f4a0  mov     rcx, rbx
0x18000f4a3  mov     rax, rdi
0x18000f4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ab  mov     edi, eax
0x18000f4ad  test    eax, eax
0x18000f4af  jns     short loc_18000F4DD
0x18000f4b1  mov     r14d, 1
0x18000f4b7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r14b
0x18000f4be  jz      loc_18001054E
0x18000f4c4  lea     rax, aChrPjsonvalues_7; "CHR(pJsonValueStatics->CreateNumberValu"...
0x18000f4cb  mov     [rsp+158h+var_130], rax
0x18000f4d0  mov     dword ptr [rsp+158h+var_138], 3DFh
0x18000f4d8  jmp     loc_18000F0AA
0x18000f4dd  mov     rbx, [rsp+158h+var_120]
0x18000f4e2  mov     rdi, [rbx]
0x18000f4e5  mov     r14, [rsp+158h+var_128]
0x18000f4ea  mov     [rsp+158h+string], rsi
  ... truncated ...
```
