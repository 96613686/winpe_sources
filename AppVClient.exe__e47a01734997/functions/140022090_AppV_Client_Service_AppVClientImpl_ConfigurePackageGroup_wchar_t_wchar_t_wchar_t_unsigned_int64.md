# AppV::Client::Service::AppVClientImpl::ConfigurePackageGroup(wchar_t *,wchar_t *,wchar_t *,unsigned __int64 *)

- ea: `0x140022090`
- end: `0x140022881`
- name: `?ConfigurePackageGroup@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W00PEA_K@Z`
- size: `2033`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl *this, wchar_t *, wchar_t *, wchar_t *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `34`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140007834`
- `0x140008224`
- `0x1400083b4`
- `0x140008e64`
- `0x1400090cc`
- `0x140010158`
- `0x140018bec`
- `0x140019ff0`
- `0x14001f964`
- `0x1400203e4`
- `0x140022090`
- `0x1400233dc`
- `0x140026dd0`
- `0x140028e00`
- `0x140029cb4`
- `0x14002a718`
- `0x1400360a0`
- `0x14003a0e8`
- `0x14003a494`
- `0x14003a4dc`
- `0x14003a6d8`
- `0x14003a9f4`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14003d01c`
- `0x140047648`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400221de`
- `ADVAPI32!EventActivityIdControl` at `0x140022855`
- `ADVAPI32!EventActivityIdControl` at `0x1400221de`
- `ADVAPI32!EventActivityIdControl` at `0x140022855`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002258a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400225b2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400225e5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002261a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022666`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002268e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400226c1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400226f6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002258a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400225b2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400225e5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002261a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140022666`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002268e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400226c1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400226f6`
- `APPVPOLICY!__imp_CreatePackageGroupDescriptorDocumentFromFile` at `0x140022557`
- `APPVPOLICY!__imp_CreatePackageGroupDescriptorDocumentFromFile` at `0x140022557`
- `OLEAUT32!__imp_SysStringLen` at `0x1400221f9`
- `OLEAUT32!__imp_SysStringLen` at `0x140022215`
- `OLEAUT32!__imp_SysStringLen` at `0x14002222f`
- `OLEAUT32!__imp_SysStringLen` at `0x1400221f9`
- `OLEAUT32!__imp_SysStringLen` at `0x140022215`
- `OLEAUT32!__imp_SysStringLen` at `0x14002222f`

## string_xrefs

- `0x140022580`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400220d8`: `ConfigurePackageGroup`
- `0x140022150`: `ConfigurePackageGroup`
- `0x14002232f`: `AppV::Client::Service::AppVClientImpl::ConfigurePackageGroup`

## pseudocode

```c
__int64 __fastcall AppV::Client::Service::AppVClientImpl::ConfigurePackageGroup(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        unsigned __int64 *a5)
{
  _DWORD *v6; // rax
  __int64 AddedPackages; // rsi
  volatile signed __int32 *v8; // rdi
  int v10; // eax
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rbx
  _QWORD *v17; // rcx
  _QWORD *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // rdi
  char *v23; // rax
  const char *v24; // rax
  char *v25; // rax
  const char *v26; // rax
  char *v27; // rax
  const char *v28; // rax
  char *v29; // rax
  const char *v30; // rax
  int v31; // ecx
  __int64 *v32; // rdx
  char *v33; // rax
  const char *v34; // rax
  char *v35; // rax
  const char *v36; // rax
  char *v37; // rax
  const char *v38; // rax
  char *v39; // rax
  const char *v40; // rax
  volatile signed __int32 *v41; // rdi
  int v42; // eax
  _BYTE v43[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v46; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v47[8]; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  BSTR *p_pbstr; // [rsp+78h] [rbp-88h]
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+90h] [rbp-70h]
  _BYTE v53[16]; // [rsp+A0h] [rbp-60h] BYREF
  int v54; // [rsp+B0h] [rbp-50h]
  __int128 v55; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-10h]
  _BYTE v57[4]; // [rsp+F8h] [rbp-8h] BYREF
  GUID ActivityId; // [rsp+FCh] [rbp-4h] BYREF
  __int128 v59; // [rsp+120h] [rbp+20h] BYREF
  __int64 v60; // [rsp+130h] [rbp+30h]
  __int64 v61; // [rsp+138h] [rbp+38h]
  __int128 v62; // [rsp+140h] [rbp+40h] BYREF
  __int64 v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+158h] [rbp+58h]
  _QWORD v65[3]; // [rsp+160h] [rbp+60h] BYREF
  struct _GUID v66; // [rsp+178h] [rbp+78h] BYREF
  struct _GUID v67; // [rsp+188h] [rbp+88h] BYREF
  __int64 v68; // [rsp+198h] [rbp+98h] BYREF
  __int128 v69; // [rsp+1A0h] [rbp+A0h]
  __int128 v70; // [rsp+1B0h] [rbp+B0h]
  __int128 v71; // [rsp+1C0h] [rbp+C0h]
  __int64 v72; // [rsp+1D0h] [rbp+D0h]
  _BYTE v73[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v74; // [rsp+200h] [rbp+100h]
  void **v75; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v76[40]; // [rsp+218h] [rbp+118h] BYREF
  _QWORD v77[16]; // [rsp+240h] [rbp+140h] BYREF

  pbstr = a2;
  v46 = a3;
  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(v57);
  AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(
    (AppV::Client::Service::SmartTelemetryActivityLogger *)v53,
    L"ConfigurePackageGroup");
  v6 = operator new(0x18u);
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<AppMan::Shared::SlapiWrapper::productionSlapiProxy>::`vftable';
  *((_QWORD *)v6 + 2) = &AppMan::Shared::SlapiWrapper::productionSlapiProxy::`vftable';
  Block[0] = v6 + 4;
  Block[1] = v6;
  AppMan::Shared::SlapiWrapper::appManSlapiWrapper::appManSlapiWrapper(v47, Block);
  if ( !(unsigned __int8)AppMan::Shared::SlapiWrapper::appManSlapiWrapper::IsProductEnabled(v47) )
  {
    AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(
      (AppV::Client::Service::SmartTelemetryPackageLogger *)v77,
      L"ConfigurePackageGroup",
      pbstr,
      v46);
    v77[0] = &AppV::Client::Service::SmartTelemetryAddPackageGroupSlapiLogger::`vftable';
    LODWORD(AddedPackages) = -2147164159;
    v54 = -2147164159;
    AppV::Client::Service::SmartTelemetryAddPackageGroupSlapiLogger::~SmartTelemetryAddPackageGroupSlapiLogger((AppV::Client::Service::SmartTelemetryAddPackageGroupSlapiLogger *)v77);
    goto LABEL_3;
  }
  if ( pbstr && SysStringLen(pbstr) && v46 && SysStringLen(v46) && a4 && SysStringLen(a4) && a5 )
  {
    v43[0] = 0;
    v10 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
            (AppV::Client::Service::AppVClientImpl::APICaller *)v43,
            1,
            a5);
    LODWORD(AddedPackages) = v10;
    if ( v10 < 0 )
    {
      v54 = v10;
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v43);
      goto LABEL_3;
    }
    AppV::Client::ActivityData::ActivityData((AppV::Client::ActivityData *)v65);
    v65[0] = &AppV::Client::ConfigurePackageGroupData::`vftable';
    v66 = GUID_NULL;
    v67 = GUID_NULL;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                     pbstr,
                                     v46,
                                     &v66,
                                     &v67);
    if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
    {
      *a5 = PackageIDAndPackageVersionID;
      v54 = -2147024809;
      AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData((AppV::Client::ConfigurePackageGroupData *)v65);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v43);
      goto LABEL_76;
    }
    v51 = 0;
    v52 = 0;
    AddedPackages = AppV::Client::GetAddedPackages(v12, &v51);
    if ( (AddedPackages & 0x8000000000LL) == 0 )
    {
      std::string::string(v73, "AppV::Client::Service::AppVClientImpl::ConfigurePackageGroup");
      v74 = 1546;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v59 = 0;
      v60 = 0;
      v61 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        &v59,
        L"Failed to get added package list for groupId = %1, versionId = %2. Error = %3%.",
        79);
      v14 = AppV::Log::fmt(v13, &v75, &v59);
      ++*(_DWORD *)(v14 + 8);
      AppV::LogFormatter::build_substitution_list(v14, Block);
      v15 = Block[0];
      if ( Block[0] )
      {
        v49 = v14;
        p_pbstr = &pbstr;
        std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_>(
          &v62,
          Block[0],
          0,
          &v49);
        v15 = Block[0];
      }
      Block[0] = 0;
      if ( v15 )
      {
        do
        {
          v16 = (_QWORD *)*v15;
          operator delete(v15);
          v15 = v16;
        }
        while ( v16 );
      }
      ++*(_DWORD *)(v14 + 8);
      AppV::LogFormatter::build_substitution_list(v14, Block);
      v17 = Block[0];
      if ( Block[0] )
      {
        v49 = v14;
        p_pbstr = &v46;
        std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_>(
          &v62,
          Block[0],
          0,
          &v49);
        v17 = Block[0];
      }
      Block[0] = 0;
      if ( v17 )
      {
        do
        {
          v18 = (_QWORD *)*v17;
          operator delete(v17);
          v17 = v18;
        }
        while ( v18 );
      }
      Block[0] = (void *)AddedPackages;
      v19 = AppV::LogFormatter::operator%(v14, Block);
      v62 = 0;
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v62, L"Client", 6);
      AppV::DecoratedLog::operator()(v73, 1, &v62, v19);
      std::wstring::~wstring(&v62);
      v75 = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v76);
      std::wstring::~wstring(&v59);
      std::string::~string(v73);
      if ( (int)AddedPackages > 0 )
        LODWORD(AddedPackages) = (unsigned __int16)AddedPackages | 0x80070000;
      v54 = AddedPackages;
      std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(&v51);
      AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData((AppV::Client::ConfigurePackageGroupData *)v65);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v43);
LABEL_3:
      v8 = v48;
      if ( v48 )
      {
LABEL_4:
        if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
LABEL_7:
      AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v53);
      if ( v57[0] )
        EventActivityIdControl(2u, &ActivityId);
      return (unsigned int)AddedPackages;
    }
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v20 = -1;
    do
      ++v20;
    while ( a4[v20] );
    std::wstring::_Construct<1,wchar_t const *>(&v59, a4);
    LOBYTE(v21) = 1;
    v22 = CreatePackageGroupDescriptorDocumentFromFile(&v59, v21, &v51, &v68);
    std::wstring::~wstring(&v59);
    if ( (v22 & 0x8000000000LL) != 0 )
    {
      v55 = 0;
      v56 = 0;
      v42 = AppV::Client::Service::AppVClientImpl::RequestActivity(31, v65, &v55);
      LODWORD(AddedPackages) = AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(
                                 (unsigned int)v53,
                                 v42,
                                 (unsigned int)&v55,
                                 (_DWORD)a5,
                                 (__int64)v53);
      v54 = AddedPackages;
      std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>(&v55);
      std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(&v51);
      AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData((AppV::Client::ConfigurePackageGroupData *)v65);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v43);
      v8 = v48;
      if ( v48 )
        goto LABEL_4;
      goto LABEL_7;
    }
    *a5 = v22;
    v23 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v23 )
      v24 = v23 + 1;
    else
      v24 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v24);
    v25 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v25 )
      v26 = v25 + 1;
    else
      v26 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v26);
    if ( (v22 & 0x2000000000LL) == 0
      && ((v27 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
        ? (v28 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
        : (v28 = v27 + 1),
          (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v28),
           (BYTE4(v22) & 0x1F) == 9)
       && ((v29 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
         ? (v30 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
         : (v30 = v29 + 1),
           AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v30),
           (_DWORD)v22 == 1)) )
    {
      if ( (byte_1400B0B81 & 0x40) == 0 )
        goto LABEL_71;
      v32 = APPV_CLIENT_Evt_ConfigurePackageGroupFailedDescriptorNotFound;
    }
    else
    {
      v33 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v33 )
        v34 = v33 + 1;
      else
        v34 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v34);
      v35 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v35 )
        v36 = v35 + 1;
      else
        v36 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v36);
      if ( (v22 & 0x2000000000LL) != 0
        || ((v37 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
          ? (v38 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
          : (v38 = v37 + 1),
            (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v38),
             (BYTE4(v22) & 0x1F) != 9)
         || ((v39 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
           ? (v40 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
           : (v40 = v39 + 1),
             (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v40),
              (_DWORD)v22 != 7)
          || (byte_1400B0B81 & 0x40) == 0)) )
      {
LABEL_71:
        v54 = -2147024809;
        std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(&v51);
        AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData((AppV::Client::ConfigurePackageGroupData *)v65);
        AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v43);
        v41 = v48;
        if ( v48 )
          goto LABEL_77;
        goto LABEL_80;
      }
      v32 = APPV_CLIENT_Evt_ConfigurePackageGroupFailedDescriptorInvalid;
    }
    McTemplateU0jjz_EventWriteTransfer(v31, (_DWORD)v32, (unsigned int)&v66, (unsigned int)&v67, (__int64)a4);
    goto LABEL_71;
  }
  v54 = -2147024809;
LABEL_76:
  v41 = v48;
  if ( v48 )
  {
LABEL_77:
    if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
      if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
    }
  }
LABEL_80:
  AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v53);
  if ( v57[0] )
    EventActivityIdControl(2u, &ActivityId);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140022090  push    rbp
0x140022092  push    rbx
0x140022093  push    rsi
0x140022094  push    rdi
0x140022095  push    r12
0x140022097  push    r14
0x140022099  push    r15
0x14002209b  lea     rbp, [rsp-1D0h]
0x1400220a3  sub     rsp, 2D0h
0x1400220aa  mov     rax, cs:__security_cookie
0x1400220b1  xor     rax, rsp
0x1400220b4  mov     [rbp+200h+var_40], rax
0x1400220bb  mov     r15, r9
0x1400220be  mov     [rsp+300h+pbstr], rdx
0x1400220c3  mov     [rsp+300h+var_2B0], r8
0x1400220c8  mov     r14, [rbp+200h+arg_20]
0x1400220cf  lea     rcx, [rbp+200h+var_208]
0x1400220d3  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x1400220d8  lea     rdx, aConfigurepacka_3; "ConfigurePackageGroup"
0x1400220df  lea     rcx, [rbp+200h+var_260]; this
0x1400220e3  call    ??0SmartTelemetryActivityLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(wchar_t const *)
0x1400220e8  mov     ecx, 18h; Size
0x1400220ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400220f2  mov     dword ptr [rax+8], 1
0x1400220f9  mov     dword ptr [rax+0Ch], 1
0x140022100  lea     rcx, ??_7?$_Ref_count_obj2@VproductionSlapiProxy@SlapiWrapper@Shared@AppMan@@@std@@6B@; const std::_Ref_count_obj2<AppMan::Shared::SlapiWrapper::productionSlapiProxy>::`vftable'
0x140022107  mov     [rax], rcx
0x14002210a  lea     rcx, [rax+10h]
0x14002210e  lea     rdx, ??_7productionSlapiProxy@SlapiWrapper@Shared@AppMan@@6B@; const AppMan::Shared::SlapiWrapper::productionSlapiProxy::`vftable'
0x140022115  mov     [rcx], rdx
0x140022118  mov     [rsp+300h+Block], rcx
0x14002211d  mov     [rsp+300h+var_2C0], rax
0x140022122  lea     rdx, [rsp+300h+Block]
0x140022127  lea     rcx, [rsp+300h+var_2A8]
0x14002212c  call    ??0appManSlapiWrapper@SlapiWrapper@Shared@AppMan@@QEAA@V?$shared_ptr@VslapiProxy@SlapiWrapper@Shared@AppMan@@@std@@@Z; AppMan::Shared::SlapiWrapper::appManSlapiWrapper::appManSlapiWrapper(std::shared_ptr<AppMan::Shared::SlapiWrapper::slapiProxy>)
0x140022131  lea     rcx, [rsp+300h+var_2A8]
0x140022136  call    ?IsProductEnabled@appManSlapiWrapper@SlapiWrapper@Shared@AppMan@@QEAA_NW4appManProduct@234@@Z; AppMan::Shared::SlapiWrapper::appManSlapiWrapper::IsProductEnabled(AppMan::Shared::SlapiWrapper::appManProduct)
0x14002213b  xor     r12d, r12d
0x14002213e  test    al, al
0x140022140  jnz     loc_1400221EB
0x140022146  mov     r9, [rsp+300h+var_2B0]; wchar_t *
0x14002214b  mov     r8, [rsp+300h+pbstr]; wchar_t *
0x140022150  lea     rdx, aConfigurepacka_3; "ConfigurePackageGroup"
0x140022157  lea     rcx, [rbp+200h+var_C0]; this
0x14002215e  call    ??0SmartTelemetryPackageLogger@Service@Client@AppV@@QEAA@PEB_WPEA_W1@Z; AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(wchar_t const *,wchar_t *,wchar_t *)
0x140022163  lea     rax, ??_7SmartTelemetryAddPackageGroupSlapiLogger@Service@Client@AppV@@6B@; const AppV::Client::Service::SmartTelemetryAddPackageGroupSlapiLogger::`vftable'
0x14002216a  mov     [rbp+200h+var_C0], rax
0x140022171  mov     esi, 8004E001h
0x140022176  mov     [rbp+200h+var_250], esi
0x140022179  lea     rcx, [rbp+200h+var_C0]; this
0x140022180  call    ??1SmartTelemetryAddPackageGroupSlapiLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryAddPackageGroupSlapiLogger::~SmartTelemetryAddPackageGroupSlapiLogger(void)
0x140022185  mov     rdi, [rsp+300h+var_2A0]
0x14002218a  test    rdi, rdi
0x14002218d  jz      short loc_1400221C6
0x14002218f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140022193  mov     eax, ebx
0x140022195  lock xadd [rdi+8], eax
0x14002219a  add     eax, ebx
0x14002219c  jnz     short loc_1400221C6
0x14002219e  mov     rax, [rdi]
0x1400221a1  mov     rcx, rdi
0x1400221a4  mov     rax, [rax]
0x1400221a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400221ac  mov     eax, ebx
0x1400221ae  lock xadd [rdi+0Ch], eax
0x1400221b3  add     eax, ebx
0x1400221b5  jnz     short loc_1400221C6
0x1400221b7  mov     rax, [rdi]
0x1400221ba  mov     rcx, rdi
0x1400221bd  mov     rax, [rax+8]
0x1400221c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400221c6  lea     rcx, [rbp+200h+var_260]; this
0x1400221ca  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x1400221cf  cmp     [rbp+200h+var_208], r12b
0x1400221d3  jz      short loc_1400221E4
0x1400221d5  lea     rdx, [rbp+200h+ActivityId]; ActivityId
0x1400221d9  mov     ecx, 2; ControlCode
0x1400221de  call    cs:__imp_EventActivityIdControl
0x1400221e4  mov     eax, esi
0x1400221e6  jmp     loc_140022860
0x1400221eb  mov     rcx, [rsp+300h+pbstr]; pbstr
0x1400221f0  test    rcx, rcx
0x1400221f3  jz      loc_1400227F5
0x1400221f9  call    cs:__imp_SysStringLen
0x1400221ff  test    eax, eax
0x140022201  jz      loc_1400227F5
0x140022207  mov     rcx, [rsp+300h+var_2B0]; pbstr
0x14002220c  test    rcx, rcx
0x14002220f  jz      loc_1400227F5
0x140022215  call    cs:__imp_SysStringLen
0x14002221b  test    eax, eax
0x14002221d  jz      loc_1400227F5
0x140022223  test    r15, r15
0x140022226  jz      loc_1400227F5
0x14002222c  mov     rcx, r15; pbstr
0x14002222f  call    cs:__imp_SysStringLen
0x140022235  test    eax, eax
0x140022237  jz      loc_1400227F5
0x14002223d  test    r14, r14
0x140022240  jz      loc_1400227F5
0x140022246  mov     [rsp+300h+var_2D0], r12b
0x14002224b  mov     r8, r14; unsigned __int64 *
0x14002224e  mov     dl, 1; bool
0x140022250  lea     rcx, [rsp+300h+var_2D0]; this
0x140022255  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x14002225a  mov     esi, eax
0x14002225c  test    eax, eax
0x14002225e  jns     short loc_140022273
0x140022260  mov     [rbp+200h+var_250], eax
0x140022263  lea     rcx, [rsp+300h+var_2D0]; this
0x140022268  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002226d  nop
0x14002226e  jmp     loc_140022185
0x140022273  lea     rcx, [rbp+200h+var_1A0]; this
0x140022277  call    ??0ActivityData@Client@AppV@@QEAA@XZ; AppV::Client::ActivityData::ActivityData(void)
0x14002227c  lea     rax, ??_7ConfigurePackageGroupData@Client@AppV@@6B@; const AppV::Client::ConfigurePackageGroupData::`vftable'
0x140022283  mov     [rbp+200h+var_1A0], rax
0x140022287  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002228e  movdqu  xmmword ptr [rbp+200h+var_188.Data1], xmm0
0x140022293  movdqu  xmmword ptr [rbp+200h+var_178.Data1], xmm0
0x14002229b  mov     [rbp+200h+var_168], r12
0x1400222a2  xorps   xmm0, xmm0
0x1400222a5  movdqa  [rbp+200h+var_160], xmm0
0x1400222ad  xorps   xmm1, xmm1
0x1400222b0  movdqa  [rbp+200h+var_150], xmm1
0x1400222b8  movdqa  [rbp+200h+var_140], xmm0
0x1400222c0  mov     [rbp+200h+var_130], r12
0x1400222c7  lea     r9, [rbp+200h+var_178]; struct _GUID *
0x1400222ce  lea     r8, [rbp+200h+var_188]; struct _GUID *
0x1400222d2  mov     rdx, [rsp+300h+var_2B0]; wchar_t *
0x1400222d7  mov     rcx, [rsp+300h+pbstr]; wchar_t *
0x1400222dc  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x1400222e1  bt      rax, 27h ; '''
0x1400222e6  jb      short loc_14002230C
0x1400222e8  mov     [r14], rax
0x1400222eb  mov     [rbp+200h+var_250], 80070057h
0x1400222f2  lea     rcx, [rbp+200h+var_1A0]; this
0x1400222f6  call    ??1ConfigurePackageGroupData@Client@AppV@@UEAA@XZ; AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData(void)
0x1400222fb  nop
0x1400222fc  lea     rcx, [rsp+300h+var_2D0]; this
0x140022301  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140022306  nop
0x140022307  jmp     loc_1400227FC
0x14002230c  xorps   xmm0, xmm0
0x14002230f  movdqu  [rbp+200h+var_280], xmm0
0x140022314  mov     [rbp+200h+var_270], r12
0x140022318  lea     rdx, [rbp+200h+var_280]
0x14002231c  call    ?GetAddedPackages@Client@AppV@@YA_KAEAVControllerRequests@12@AEAV?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@@Z; AppV::Client::GetAddedPackages(AppV::Client::ControllerRequests &,std::vector<AppV::Client::PackageIdentity> &)
0x140022321  mov     rsi, rax
0x140022324  bt      rax, 27h ; '''
0x140022329  jb      loc_14002251A
0x14002232f  lea     rdx, aAppvClientServ_39; "AppV::Client::Service::AppVClientImpl::"...
0x140022336  lea     rcx, [rbp+200h+var_120]
0x14002233d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140022342  mov     [rbp+200h+var_100], 60Ah
0x14002234c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140022351  xorps   xmm0, xmm0
0x140022354  movups  [rbp+200h+var_1E0], xmm0
0x140022358  mov     [rbp+200h+var_1D0], r12
0x14002235c  mov     [rbp+200h+var_1C8], r12
0x140022360  mov     r8d, 4Fh ; 'O'
0x140022366  lea     rdx, aFailedToGetAdd; "Failed to get added package list for gr"...
0x14002236d  lea     rcx, [rbp+200h+var_1E0]
0x140022371  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140022376  lea     r8, [rbp+200h+var_1E0]
0x14002237a  lea     rdx, [rbp+200h+var_F8]
0x140022381  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140022386  mov     rdi, rax
0x140022389  mov     r8d, [rax+8]
0x14002238d  lea     ecx, [r8+1]
0x140022391  mov     [rax+8], ecx
0x140022394  lea     rdx, [rsp+300h+Block]
0x140022399  mov     rcx, rax
0x14002239c  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x1400223a1  mov     rcx, [rsp+300h+Block]
0x1400223a6  test    rcx, rcx
0x1400223a9  jz      short loc_1400223D3
0x1400223ab  mov     r8, r12
0x1400223ae  mov     [rsp+300h+var_290], rdi
0x1400223b3  lea     rax, [rsp+300h+pbstr]
0x1400223b8  mov     [rsp+300h+var_288], rax
0x1400223bd  lea     r9, [rsp+300h+var_290]
0x1400223c2  mov     rdx, rcx
0x1400223c5  lea     rcx, [rbp+200h+var_1C0]
0x1400223c9  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_040842e831ae1b296ee7ecb49762fd0a_@@@std@@YA?AV_lambda_040842e831ae1b296ee7ecb49762fd0a_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_)
0x1400223ce  mov     rcx, [rsp+300h+Block]; Block
0x1400223d3  mov     [rsp+300h+Block], r12
0x1400223d8  mov     r14d, 20h ; ' '
0x1400223de  test    rcx, rcx
0x1400223e1  jz      short loc_1400223F6
0x1400223e3  mov     rbx, [rcx]
0x1400223e6  mov     rdx, r14
0x1400223e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400223ee  mov     rcx, rbx
0x1400223f1  test    rbx, rbx
0x1400223f4  jnz     short loc_1400223E3
0x1400223f6  mov     r8d, [rdi+8]
0x1400223fa  lea     eax, [r8+1]
0x1400223fe  mov     [rdi+8], eax
0x140022401  lea     rdx, [rsp+300h+Block]
0x140022406  mov     rcx, rdi
0x140022409  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14002240e  mov     rcx, [rsp+300h+Block]
0x140022413  test    rcx, rcx
0x140022416  jz      short loc_140022440
0x140022418  mov     r8, r12
0x14002241b  mov     [rsp+300h+var_290], rdi
0x140022420  lea     rax, [rsp+300h+var_2B0]
0x140022425  mov     [rsp+300h+var_288], rax
0x14002242a  lea     r9, [rsp+300h+var_290]
0x14002242f  mov     rdx, rcx
0x140022432  lea     rcx, [rbp+200h+var_1C0]
0x140022436  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_040842e831ae1b296ee7ecb49762fd0a_@@@std@@YA?AV_lambda_040842e831ae1b296ee7ecb49762fd0a_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_040842e831ae1b296ee7ecb49762fd0a_)
0x14002243b  mov     rcx, [rsp+300h+Block]; Block
0x140022440  mov     [rsp+300h+Block], r12
0x140022445  test    rcx, rcx
0x140022448  jz      short loc_14002245D
0x14002244a  mov     rbx, [rcx]
0x14002244d  mov     rdx, r14
0x140022450  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140022455  mov     rcx, rbx
0x140022458  test    rbx, rbx
0x14002245b  jnz     short loc_14002244A
0x14002245d  mov     [rsp+300h+Block], rsi
0x140022462  lea     rdx, [rsp+300h+Block]
0x140022467  mov     rcx, rdi
0x14002246a  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14002246f  mov     rbx, rax
0x140022472  xorps   xmm0, xmm0
0x140022475  movups  [rbp+200h+var_1C0], xmm0
0x140022479  mov     [rbp+200h+var_1B0], r12
0x14002247d  mov     [rbp+200h+var_1A8], r12
0x140022481  mov     r8d, 6
0x140022487  lea     rdx, aClient; "Client"
0x14002248e  lea     rcx, [rbp+200h+var_1C0]
0x140022492  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140022497  mov     r9, rbx
0x14002249a  lea     r8, [rbp+200h+var_1C0]
0x14002249e  mov     edx, 1
0x1400224a3  lea     rcx, [rbp+200h+var_120]
0x1400224aa  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400224af  lea     rcx, [rbp+200h+var_1C0]
0x1400224b3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400224b8  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400224bf  mov     [rbp+200h+var_F8], rax
0x1400224c6  lea     rcx, [rbp+200h+var_E8]
0x1400224cd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400224d2  lea     rcx, [rbp+200h+var_1E0]
0x1400224d6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400224db  lea     rcx, [rbp+200h+var_120]
0x1400224e2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400224e7  test    esi, esi
0x1400224e9  jle     short loc_1400224F4
0x1400224eb  movzx   esi, si
0x1400224ee  or      esi, 80070000h
0x1400224f4  mov     [rbp+200h+var_250], esi
0x1400224f7  lea     rcx, [rbp+200h+var_280]
0x1400224fb  call    ??1?$vector@UPackageIdentity@Client@AppV@@V?$allocator@UPackageIdentity@Client@AppV@@@std@@@std@@QEAA@XZ; std::vector<AppV::Client::PackageIdentity>::~vector<AppV::Client::PackageIdentity>(void)
0x140022500  lea     rcx, [rbp+200h+var_1A0]; this
0x140022504  call    ??1ConfigurePackageGroupData@Client@AppV@@UEAA@XZ; AppV::Client::ConfigurePackageGroupData::~ConfigurePackageGroupData(void)
0x140022509  nop
0x14002250a  lea     rcx, [rsp+300h+var_2D0]; this
0x14002250f  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140022514  nop
0x140022515  jmp     loc_140022185
0x14002251a  xorps   xmm0, xmm0
0x14002251d  movups  [rbp+200h+var_1E0], xmm0
0x140022521  mov     [rbp+200h+var_1D0], r12
0x140022525  mov     [rbp+200h+var_1C8], r12
0x140022529  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002252d  mov     r8, rbx
0x140022530  inc     r8
0x140022533  cmp     [r15+r8*2], r12w
0x140022538  jnz     short loc_140022530
0x14002253a  mov     rdx, r15
0x14002253d  lea     rcx, [rbp+200h+var_1E0]
0x140022541  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140022546  lea     r9, [rbp+200h+var_168]
0x14002254d  lea     r8, [rbp+200h+var_280]
0x140022551  mov     dl, 1
0x140022553  lea     rcx, [rbp+200h+var_1E0]
0x140022557  call    cs:__imp_CreatePackageGroupDescriptorDocumentFromFile
0x14002255d  mov     rdi, rax
0x140022560  lea     rcx, [rbp+200h+var_1E0]
0x140022564  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140022569  bt      rdi, 27h ; '''
0x14002256e  jb      loc_140022780
0x140022574  mov     [r14], rdi
0x140022577  mov     r14d, 5Ch ; '\'
0x14002257d  mov     edx, r14d; Ch
0x140022580  lea     rsi, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140022587  mov     rcx, rsi; Str
0x14002258a  call    cs:__imp_strrchr
0x140022590  test    rax, rax
0x140022593  jz      short loc_14002259A
0x140022595  inc     rax
0x140022598  jmp     short loc_14002259D
0x14002259a  mov     rax, rsi
0x14002259d  mov     rdx, rax; char *
0x1400225a0  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
  ... truncated ...
```
