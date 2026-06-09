# AppV::Client::Service::AppVClientImpl::ConfigurePackage(wchar_t *,wchar_t *,wchar_t *,wchar_t *,tagVARIANT,unsigned __int64 *)

- ea: `0x140021840`
- end: `0x14002207f`
- name: `?ConfigurePackage@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W000UtagVARIANT@@PEA_K@Z`
- size: `2111`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl *this, wchar_t *, wchar_t *, wchar_t *, wchar_t *pbstr, struct tagVARIANT *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140006061`
- `0x1400060e8`
- `0x140006304`
- `0x140007404`
- `0x140008224`
- `0x1400083b4`
- `0x1400090cc`
- `0x140018bec`
- `0x14001f964`
- `0x1400202a0`
- `0x140021840`
- `0x1400233dc`
- `0x140026dd0`
- `0x140028e00`
- `0x140029cb4`
- `0x14002a718`
- `0x1400360a0`
- `0x140039668`
- `0x14003a0e8`
- `0x14003a198`
- `0x14003a24c`
- `0x14003a4dc`
- `0x14003aacc`
- `0x14003ac7c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400219a1`
- `ADVAPI32!EventActivityIdControl` at `0x140021ad6`
- `ADVAPI32!EventActivityIdControl` at `0x14002204a`
- `ADVAPI32!EventActivityIdControl` at `0x1400219a1`
- `ADVAPI32!EventActivityIdControl` at `0x140021ad6`
- `ADVAPI32!EventActivityIdControl` at `0x14002204a`
- `KERNEL32!GetSystemTime` at `0x140021f68`
- `KERNEL32!GetSystemTime` at `0x140021f68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140021c1d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140021c1d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d1a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d45`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d70`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021da1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021de9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e0d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e3c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e6d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d1a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d45`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021d70`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021da1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021de9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e0d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e3c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140021e6d`
- `APPVPOLICY!__imp_CreatePackageMachinePolicyDocument` at `0x140021c61`
- `APPVPOLICY!__imp_CreatePackageMachinePolicyDocument` at `0x140021c61`
- `APPVPOLICY!__imp_CreatePackageMachinePolicyDocumentFromFile` at `0x140021ce6`
- `APPVPOLICY!__imp_CreatePackageMachinePolicyDocumentFromFile` at `0x140021ce6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400219ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1400219d4`
- `OLEAUT32!__imp_SysStringLen` at `0x140021c05`
- `OLEAUT32!__imp_SysStringLen` at `0x1400219ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1400219d4`
- `OLEAUT32!__imp_SysStringLen` at `0x140021c05`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x140021f35`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x140021f35`

## string_xrefs

- `0x140021d10`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400218fa`: `ConfigurePackage`
- `0x140021911`: `ConfigurePackage`
- `0x140021a08`: `ConfigurePackage`
- `0x140021a2d`: `ConfigurePackage`
- `0x140021fd7`: `ConfigurePackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AppV::Client::Service::AppVClientImpl::ConfigurePackage(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        wchar_t *pbstr,
        struct tagVARIANT *a6,
        unsigned __int64 *a7)
{
  _DWORD *v10; // rax
  unsigned int v11; // edi
  volatile signed __int32 *v12; // rbx
  int v14; // eax
  unsigned int v15; // r12d
  volatile signed __int32 *v16; // rbx
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  void **v20; // rdi
  __int64 v21; // rbx
  int v22; // eax
  __int64 v23; // r8
  unsigned __int64 v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rdx
  unsigned __int64 v27; // rbx
  char *v28; // rax
  const char *v29; // rax
  char *v30; // rax
  const char *v31; // rax
  char *v32; // rax
  const char *v33; // rax
  char *v34; // rax
  const char *v35; // rax
  int v36; // ecx
  __int64 *v37; // rdx
  char *v38; // rax
  const char *v39; // rax
  char *v40; // rax
  const char *v41; // rax
  char *v42; // rax
  const char *v43; // rax
  char *v44; // rax
  const char *v45; // rax
  volatile signed __int32 *v46; // rbx
  int v47; // eax
  _BYTE v48[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v49[8]; // [rsp+38h] [rbp-C8h] BYREF
  volatile signed __int32 *v50; // [rsp+40h] [rbp-C0h]
  struct tagVARIANT *v51; // [rsp+48h] [rbp-B8h]
  __int128 v52; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h]
  __int128 v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h]
  _BYTE v57[4]; // [rsp+88h] [rbp-78h] BYREF
  GUID ActivityId; // [rsp+8Ch] [rbp-74h] BYREF
  _QWORD v59[3]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v60; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v61; // [rsp+D8h] [rbp-28h] BYREF
  void *v62[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v63; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v64; // [rsp+100h] [rbp+0h]
  _QWORD v65[2]; // [rsp+108h] [rbp+8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+118h] [rbp+18h] BYREF
  char v67; // [rsp+128h] [rbp+28h]
  __int128 v68; // [rsp+130h] [rbp+30h]
  __int128 v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+150h] [rbp+50h]
  __int64 v71; // [rsp+158h] [rbp+58h]
  __int128 v72; // [rsp+160h] [rbp+60h]
  __int128 v73; // [rsp+170h] [rbp+70h]
  _QWORD v74[2]; // [rsp+180h] [rbp+80h] BYREF
  int v75; // [rsp+190h] [rbp+90h]
  _QWORD v76[16]; // [rsp+200h] [rbp+100h] BYREF

  v51 = a6;
  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(v57);
  v10 = operator new(0x18u);
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = &std::_Ref_count_obj2<AppMan::Shared::SlapiWrapper::productionSlapiProxy>::`vftable';
  *((_QWORD *)v10 + 2) = &AppMan::Shared::SlapiWrapper::productionSlapiProxy::`vftable';
  *(_QWORD *)&v54 = v10 + 4;
  *((_QWORD *)&v54 + 1) = v10;
  AppMan::Shared::SlapiWrapper::appManSlapiWrapper::appManSlapiWrapper(v49, &v54);
  if ( !(unsigned __int8)AppMan::Shared::SlapiWrapper::appManSlapiWrapper::IsProductEnabled(v49) )
  {
    AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)&v54,
      L"ConfigurePackage");
    AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(
      (AppV::Client::Service::SmartTelemetryPackageLogger *)v76,
      L"ConfigurePackage",
      a2,
      a3);
    v76[0] = &AppV::Client::Service::SmartTelemetryAddPackageSlapiLogger::`vftable';
    v11 = -2147164159;
    LODWORD(v55) = -2147164159;
    AppV::Client::Service::SmartTelemetryAddPackageSlapiLogger::~SmartTelemetryAddPackageSlapiLogger((AppV::Client::Service::SmartTelemetryAddPackageSlapiLogger *)v76);
    goto LABEL_3;
  }
  if ( a2 && SysStringLen(a2) && a3 && SysStringLen(a3) && a7 )
  {
    v48[0] = 0;
    if ( (paths::is_short_name_creation_enabled_on_package_root(v48) & 0x8000000000LL) != 0 && !v48[0] )
    {
      AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
        (AppV::Client::Service::SmartComMethodLogger *)&v54,
        L"ConfigurePackage");
      v11 = -2147164158;
      LODWORD(v55) = -2147164158;
LABEL_3:
      AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger((AppV::Client::Service::SmartComMethodLogger *)&v54);
      v12 = v50;
      if ( v50 )
      {
LABEL_4:
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
LABEL_7:
      if ( v57[0] )
        EventActivityIdControl(2u, &ActivityId);
      return v11;
    }
    AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(
      (AppV::Client::Service::SmartTelemetryPackageLogger *)v74,
      L"ConfigurePackage",
      a2,
      a3);
    v74[0] = &AppV::Client::Service::SmartTelemetryAddPackageLogger::`vftable';
    v48[0] = 0;
    v14 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
            (AppV::Client::Service::AppVClientImpl::APICaller *)v48,
            1,
            a7);
    v15 = v14;
    if ( v14 < 0 )
    {
      v75 = v14;
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v48);
      AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger((AppV::Client::Service::SmartTelemetryAddPackageLogger *)v74);
      v16 = v50;
      if ( v50 )
      {
        if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      if ( v57[0] )
        EventActivityIdControl(2u, &ActivityId);
      return v15;
    }
    AppV::Client::ActivityData::ActivityData((AppV::Client::ActivityData *)v59);
    v59[0] = &AppV::Client::ConfigurePackageData::`vftable';
    v60 = GUID_NULL;
    v61 = GUID_NULL;
    *(_OWORD *)v62 = 0;
    v63 = 0;
    v64 = 7;
    LOWORD(v62[0]) = 0;
    v65[0] = 0;
    v65[1] = 0;
    v67 = 1;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 7;
    LOWORD(v69) = 0;
    v72 = 0;
    v73 = 0;
    SystemTime = 0;
    PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                     a2,
                                     a3,
                                     &v60,
                                     &v61);
    if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
    {
      *a7 = PackageIDAndPackageVersionID;
      v75 = -2147024809;
      AppV::Client::ConfigurePackageData::~ConfigurePackageData((AppV::Client::ConfigurePackageData *)v59);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v48);
      AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger((AppV::Client::Service::SmartTelemetryAddPackageLogger *)v74);
      goto LABEL_90;
    }
    if ( a4 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a4[v19] );
      if ( v19 > v64 )
      {
        std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v62, v19, v18, a4);
      }
      else
      {
        v20 = v62;
        if ( v64 > 7 )
          v20 = (void **)v62[0];
        v63 = v19;
        v21 = 2 * v19;
        memmove_0(v20, a4, 2 * v19);
        *(_WORD *)((char *)v20 + v21) = 0;
      }
    }
    if ( pbstr && SysStringLen(pbstr) )
    {
      v22 = _o__wcsicmp(L"<DEFAULT>", pbstr);
      v55 = 0;
      v56 = 0;
      v54 = 0;
      if ( v22 )
      {
        v25 = -1;
        do
          ++v25;
        while ( pbstr[v25] );
        std::wstring::_Construct<1,wchar_t const *>(&v54, pbstr);
        LOBYTE(v26) = 1;
        v27 = CreatePackageMachinePolicyDocumentFromFile(&v54, v26, v65);
        std::wstring::~wstring(&v54);
        if ( (v27 & 0x8000000000LL) == 0 )
        {
          *a7 = v27;
          v28 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          if ( v28 )
            v29 = v28 + 1;
          else
            v29 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v29);
          v30 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
          if ( v30 )
            v31 = v30 + 1;
          else
            v31 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
          AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v31);
          if ( (v27 & 0x2000000000LL) == 0
            && ((v32 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
              ? (v33 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
              : (v33 = v32 + 1),
                (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v33),
                 (BYTE4(v27) & 0x1F) == 9)
             && ((v34 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
               ? (v35 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
               : (v35 = v34 + 1),
                 AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v35),
                 (_DWORD)v27 == 1)) )
          {
            if ( (byte_1400B0B81 & 0x40) == 0 )
              goto LABEL_81;
            v37 = APPV_CLIENT_Evt_ConfigurePackageFailedDeploymentConfigNotFound;
          }
          else
          {
            v38 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
            if ( v38 )
              v39 = v38 + 1;
            else
              v39 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
            AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v39);
            v40 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
            if ( v40 )
              v41 = v40 + 1;
            else
              v41 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
            AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v41);
            if ( (v27 & 0x2000000000LL) != 0
              || ((v42 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
                ? (v43 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
                : (v43 = v42 + 1),
                  (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v43),
                   (BYTE4(v27) & 0x1F) != 9)
               || ((v44 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
                 ? (v45 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
                 : (v45 = v44 + 1),
                   (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v45),
                    (_DWORD)v27 != 7)
                || (byte_1400B0B81 & 0x40) == 0)) )
            {
LABEL_81:
              v75 = -2147024809;
              AppV::Client::ConfigurePackageData::~ConfigurePackageData((AppV::Client::ConfigurePackageData *)v59);
              AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v48);
              AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger((AppV::Client::Service::SmartTelemetryAddPackageLogger *)v74);
              v46 = v50;
              if ( v50 )
                goto LABEL_91;
              goto LABEL_94;
            }
            v37 = APPV_CLIENT_Evt_ConfigurePackageFailedDeploymentConfigInvalid;
          }
          McTemplateU0jjz_EventWriteTransfer(v36, (_DWORD)v37, (unsigned int)&v60, (unsigned int)&v61, (__int64)pbstr);
          goto LABEL_81;
        }
      }
      else
      {
        std::wstring::_Construct<1,wchar_t const *>(&v54, L"(App-V Default)", 15);
        LOBYTE(v23) = 1;
        v24 = CreatePackageMachinePolicyDocument(&v60, &v54, v23, v65);
        std::wstring::~wstring(&v54);
        if ( (v24 & 0x8000000000LL) == 0 )
        {
          *a7 = v24;
          v11 = -2147418113;
          v75 = -2147418113;
          AppV::Client::ConfigurePackageData::~ConfigurePackageData((AppV::Client::ConfigurePackageData *)v59);
          AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v48);
          goto LABEL_41;
        }
      }
      if ( v51->vt )
      {
        if ( v51->vt != 7 || VariantTimeToSystemTime(v51->dblVal, &SystemTime) != 1 )
          goto LABEL_81;
      }
      else
      {
        GetSystemTime(&SystemTime);
      }
    }
    v52 = 0;
    v53 = 0;
    v47 = AppV::Client::Service::AppVClientImpl::RequestActivity(1, v59, &v52);
    v11 = AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(
            (unsigned int)v74,
            v47,
            (unsigned int)&v52,
            (_DWORD)a7,
            (__int64)v74);
    v75 = v11;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>(&v52);
    AppV::Client::ConfigurePackageData::~ConfigurePackageData((AppV::Client::ConfigurePackageData *)v59);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v48);
LABEL_41:
    AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger((AppV::Client::Service::SmartTelemetryAddPackageLogger *)v74);
    v12 = v50;
    if ( v50 )
      goto LABEL_4;
    goto LABEL_7;
  }
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)&v54,
    L"ConfigurePackage");
  LODWORD(v55) = -2147024809;
  AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger((AppV::Client::Service::SmartComMethodLogger *)&v54);
LABEL_90:
  v46 = v50;
  if ( v50 )
  {
LABEL_91:
    if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
LABEL_94:
  if ( v57[0] )
    EventActivityIdControl(2u, &ActivityId);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140021840  mov     [rsp-8+arg_0], rbx
0x140021845  push    rbp
0x140021846  push    rsi
0x140021847  push    rdi
0x140021848  push    r12
0x14002184a  push    r13
0x14002184c  push    r14
0x14002184e  push    r15
0x140021850  lea     rbp, [rsp-190h]
0x140021858  sub     rsp, 290h
0x14002185f  mov     rax, cs:__security_cookie
0x140021866  xor     rax, rsp
0x140021869  mov     [rbp+1C0h+var_40], rax
0x140021870  mov     r13, r9
0x140021873  mov     rdi, r8
0x140021876  mov     rbx, rdx
0x140021879  mov     r15, [rbp+1C0h+pbstr]
0x140021880  mov     rax, [rbp+1C0h+arg_28]
0x140021887  mov     [rsp+2C0h+var_278], rax
0x14002188c  mov     r14, [rbp+1C0h+arg_30]
0x140021893  lea     rcx, [rbp+1C0h+var_238]
0x140021897  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x14002189c  mov     ecx, 18h; Size
0x1400218a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400218a6  mov     dword ptr [rax+8], 1
0x1400218ad  mov     dword ptr [rax+0Ch], 1
0x1400218b4  lea     rcx, ??_7?$_Ref_count_obj2@VproductionSlapiProxy@SlapiWrapper@Shared@AppMan@@@std@@6B@; const std::_Ref_count_obj2<AppMan::Shared::SlapiWrapper::productionSlapiProxy>::`vftable'
0x1400218bb  mov     [rax], rcx
0x1400218be  lea     rcx, [rax+10h]
0x1400218c2  lea     rdx, ??_7productionSlapiProxy@SlapiWrapper@Shared@AppMan@@6B@; const AppMan::Shared::SlapiWrapper::productionSlapiProxy::`vftable'
0x1400218c9  mov     [rcx], rdx
0x1400218cc  mov     qword ptr [rsp+2C0h+var_258], rcx
0x1400218d1  mov     qword ptr [rsp+2C0h+var_258+8], rax
0x1400218d6  lea     rdx, [rsp+2C0h+var_258]
0x1400218db  lea     rcx, [rsp+2C0h+var_288]
0x1400218e0  call    ??0appManSlapiWrapper@SlapiWrapper@Shared@AppMan@@QEAA@V?$shared_ptr@VslapiProxy@SlapiWrapper@Shared@AppMan@@@std@@@Z; AppMan::Shared::SlapiWrapper::appManSlapiWrapper::appManSlapiWrapper(std::shared_ptr<AppMan::Shared::SlapiWrapper::slapiProxy>)
0x1400218e5  lea     rcx, [rsp+2C0h+var_288]
0x1400218ea  call    ?IsProductEnabled@appManSlapiWrapper@SlapiWrapper@Shared@AppMan@@QEAA_NW4appManProduct@234@@Z; AppMan::Shared::SlapiWrapper::appManSlapiWrapper::IsProductEnabled(AppMan::Shared::SlapiWrapper::appManProduct)
0x1400218ef  xor     r12d, r12d
0x1400218f2  test    al, al
0x1400218f4  jnz     loc_1400219AE
0x1400218fa  lea     rdx, aConfigurepacka_1; "ConfigurePackage"
0x140021901  lea     rcx, [rsp+2C0h+var_258]; this
0x140021906  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x14002190b  mov     r9, rdi; wchar_t *
0x14002190e  mov     r8, rbx; wchar_t *
0x140021911  lea     rdx, aConfigurepacka_1; "ConfigurePackage"
0x140021918  lea     rcx, [rbp+1C0h+var_C0]; this
0x14002191f  call    ??0SmartTelemetryPackageLogger@Service@Client@AppV@@QEAA@PEB_WPEA_W1@Z; AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(wchar_t const *,wchar_t *,wchar_t *)
0x140021924  lea     rax, ??_7SmartTelemetryAddPackageSlapiLogger@Service@Client@AppV@@6B@; const AppV::Client::Service::SmartTelemetryAddPackageSlapiLogger::`vftable'
0x14002192b  mov     [rbp+1C0h+var_C0], rax
0x140021932  mov     edi, 8004E001h
0x140021937  mov     dword ptr [rsp+2C0h+var_248], edi
0x14002193b  lea     rcx, [rbp+1C0h+var_C0]; this
0x140021942  call    ??1SmartTelemetryAddPackageSlapiLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryAddPackageSlapiLogger::~SmartTelemetryAddPackageSlapiLogger(void)
0x140021947  lea     rcx, [rsp+2C0h+var_258]; this
0x14002194c  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140021951  mov     rbx, [rsp+2C0h+var_280]
0x140021956  test    rbx, rbx
0x140021959  jz      short loc_140021992
0x14002195b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002195f  mov     eax, esi
0x140021961  lock xadd [rbx+8], eax
0x140021966  add     eax, esi
0x140021968  jnz     short loc_140021992
0x14002196a  mov     rax, [rbx]
0x14002196d  mov     rcx, rbx
0x140021970  mov     rax, [rax]
0x140021973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021978  mov     eax, esi
0x14002197a  lock xadd [rbx+0Ch], eax
0x14002197f  add     eax, esi
0x140021981  jnz     short loc_140021992
0x140021983  mov     rax, [rbx]
0x140021986  mov     rcx, rbx
0x140021989  mov     rax, [rax+8]
0x14002198d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021992  cmp     [rbp+1C0h+var_238], r12b
0x140021996  jz      short loc_1400219A7
0x140021998  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x14002199c  mov     ecx, 2; ControlCode
0x1400219a1  call    cs:__imp_EventActivityIdControl
0x1400219a7  mov     eax, edi
0x1400219a9  jmp     loc_140022055
0x1400219ae  test    rbx, rbx
0x1400219b1  jz      loc_140021FD7
0x1400219b7  mov     rcx, rbx; pbstr
0x1400219ba  call    cs:__imp_SysStringLen
0x1400219c0  test    eax, eax
0x1400219c2  jz      loc_140021FD7
0x1400219c8  test    rdi, rdi
0x1400219cb  jz      loc_140021FD7
0x1400219d1  mov     rcx, rdi; pbstr
0x1400219d4  call    cs:__imp_SysStringLen
0x1400219da  test    eax, eax
0x1400219dc  jz      loc_140021FD7
0x1400219e2  test    r14, r14
0x1400219e5  jz      loc_140021FD7
0x1400219eb  mov     [rsp+2C0h+var_290], r12b
0x1400219f0  lea     rcx, [rsp+2C0h+var_290]
0x1400219f5  call    paths__is_short_name_creation_enabled_on_package_root
0x1400219fa  bt      rax, 27h ; '''
0x1400219ff  jnb     short loc_140021A27
0x140021a01  cmp     [rsp+2C0h+var_290], r12b
0x140021a06  jnz     short loc_140021A27
0x140021a08  lea     rdx, aConfigurepacka_1; "ConfigurePackage"
0x140021a0f  lea     rcx, [rsp+2C0h+var_258]; this
0x140021a14  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x140021a19  mov     edi, 8004E002h
0x140021a1e  mov     dword ptr [rsp+2C0h+var_248], edi
0x140021a22  jmp     loc_140021947
0x140021a27  mov     r9, rdi; wchar_t *
0x140021a2a  mov     r8, rbx; wchar_t *
0x140021a2d  lea     rdx, aConfigurepacka_1; "ConfigurePackage"
0x140021a34  lea     rcx, [rbp+1C0h+var_140]; this
0x140021a3b  call    ??0SmartTelemetryPackageLogger@Service@Client@AppV@@QEAA@PEB_WPEA_W1@Z; AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(wchar_t const *,wchar_t *,wchar_t *)
0x140021a40  lea     rax, ??_7SmartTelemetryAddPackageLogger@Service@Client@AppV@@6B@; const AppV::Client::Service::SmartTelemetryAddPackageLogger::`vftable'
0x140021a47  mov     [rbp+1C0h+var_140], rax
0x140021a4e  mov     [rsp+2C0h+var_290], r12b
0x140021a53  mov     r8, r14; unsigned __int64 *
0x140021a56  mov     dl, 1; bool
0x140021a58  lea     rcx, [rsp+2C0h+var_290]; this
0x140021a5d  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x140021a62  mov     r12d, eax
0x140021a65  test    eax, eax
0x140021a67  jns     short loc_140021AE4
0x140021a69  mov     [rbp+1C0h+var_130], eax
0x140021a6f  lea     rcx, [rsp+2C0h+var_290]; this
0x140021a74  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140021a79  nop
0x140021a7a  lea     rcx, [rbp+1C0h+var_140]; this
0x140021a81  call    ??1SmartTelemetryAddPackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger(void)
0x140021a86  mov     rbx, [rsp+2C0h+var_280]
0x140021a8b  test    rbx, rbx
0x140021a8e  jz      short loc_140021AC7
0x140021a90  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140021a94  mov     eax, esi
0x140021a96  lock xadd [rbx+8], eax
0x140021a9b  add     eax, esi
0x140021a9d  jnz     short loc_140021AC7
0x140021a9f  mov     rax, [rbx]
0x140021aa2  mov     rcx, rbx
0x140021aa5  mov     rax, [rax]
0x140021aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021aad  mov     eax, esi
0x140021aaf  lock xadd [rbx+0Ch], eax
0x140021ab4  add     eax, esi
0x140021ab6  jnz     short loc_140021AC7
0x140021ab8  mov     rax, [rbx]
0x140021abb  mov     rcx, rbx
0x140021abe  mov     rax, [rax+8]
0x140021ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021ac7  cmp     [rbp+1C0h+var_238], 0
0x140021acb  jz      short loc_140021ADC
0x140021acd  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x140021ad1  mov     ecx, 2; ControlCode
0x140021ad6  call    cs:__imp_EventActivityIdControl
0x140021adc  mov     eax, r12d
0x140021adf  jmp     loc_140022055
0x140021ae4  lea     rcx, [rbp+1C0h+var_210]; this
0x140021ae8  call    ??0ActivityData@Client@AppV@@QEAA@XZ; AppV::Client::ActivityData::ActivityData(void)
0x140021aed  lea     rax, ??_7ConfigurePackageData@Client@AppV@@6B@; const AppV::Client::ConfigurePackageData::`vftable'
0x140021af4  mov     [rbp+1C0h+var_210], rax
0x140021af8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140021aff  movdqu  xmmword ptr [rbp+1C0h+var_1F8.Data1], xmm0
0x140021b04  movdqu  xmmword ptr [rbp+1C0h+var_1E8.Data1], xmm0
0x140021b09  xorps   xmm0, xmm0
0x140021b0c  movups  xmmword ptr [rbp+1C0h+var_1D8], xmm0
0x140021b10  xor     r12d, r12d
0x140021b13  mov     [rbp+1C0h+var_1C8], r12
0x140021b17  lea     ecx, [r12+7]
0x140021b1c  mov     [rbp+1C0h+var_1C0], rcx
0x140021b20  mov     word ptr [rbp+1C0h+var_1D8], r12w
0x140021b25  mov     [rbp+1C0h+var_1B8], r12
0x140021b29  mov     [rbp+1C0h+var_1B0], r12
0x140021b2d  mov     [rbp+1C0h+var_198], 1
0x140021b31  movdqa  [rbp+1C0h+var_190], xmm0
0x140021b36  xorps   xmm1, xmm1
0x140021b39  movups  [rbp+1C0h+var_180], xmm1
0x140021b3d  mov     [rbp+1C0h+var_170], r12
0x140021b41  mov     [rbp+1C0h+var_168], rcx
0x140021b45  mov     word ptr [rbp+1C0h+var_180], r12w
0x140021b4a  movdqa  [rbp+1C0h+var_160], xmm0
0x140021b4f  movdqa  [rbp+1C0h+var_150], xmm1
0x140021b54  movups  xmmword ptr [rbp+1C0h+SystemTime.wYear], xmm0
0x140021b58  lea     r9, [rbp+1C0h+var_1E8]; struct _GUID *
0x140021b5c  lea     r8, [rbp+1C0h+var_1F8]; struct _GUID *
0x140021b60  mov     rdx, rdi; wchar_t *
0x140021b63  mov     rcx, rbx; wchar_t *
0x140021b66  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x140021b6b  bt      rax, 27h ; '''
0x140021b70  jb      short loc_140021BA5
0x140021b72  mov     [r14], rax
0x140021b75  mov     [rbp+1C0h+var_130], 80070057h
0x140021b7f  lea     rcx, [rbp+1C0h+var_210]; this
0x140021b83  call    ??1ConfigurePackageData@Client@AppV@@UEAA@XZ; AppV::Client::ConfigurePackageData::~ConfigurePackageData(void)
0x140021b88  nop
0x140021b89  lea     rcx, [rsp+2C0h+var_290]; this
0x140021b8e  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140021b93  nop
0x140021b94  lea     rcx, [rbp+1C0h+var_140]; this
0x140021b9b  call    ??1SmartTelemetryAddPackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger(void)
0x140021ba0  jmp     loc_140021FFA
0x140021ba5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140021ba9  test    r13, r13
0x140021bac  jz      short loc_140021BF9
0x140021bae  mov     rdx, rsi
0x140021bb1  inc     rdx
0x140021bb4  cmp     [r13+rdx*2+0], r12w
0x140021bba  jnz     short loc_140021BB1
0x140021bbc  cmp     rdx, [rbp+1C0h+var_1C0]
0x140021bc0  ja      short loc_140021BED
0x140021bc2  lea     rdi, [rbp+1C0h+var_1D8]
0x140021bc6  cmp     [rbp+1C0h+var_1C0], 7
0x140021bcb  cmova   rdi, [rbp+1C0h+var_1D8]
0x140021bd0  mov     [rbp+1C0h+var_1C8], rdx
0x140021bd4  lea     rbx, [rdx+rdx]
0x140021bd8  mov     r8, rbx; Size
0x140021bdb  mov     rdx, r13; Src
0x140021bde  mov     rcx, rdi; void *
0x140021be1  call    memmove_0
0x140021be6  mov     [rbx+rdi], r12w
0x140021beb  jmp     short loc_140021BF9
0x140021bed  mov     r9, r13
0x140021bf0  lea     rcx, [rbp+1C0h+var_1D8]
0x140021bf4  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140021bf9  test    r15, r15
0x140021bfc  jz      loc_140021F6E
0x140021c02  mov     rcx, r15; pbstr
0x140021c05  call    cs:__imp_SysStringLen
0x140021c0b  test    eax, eax
0x140021c0d  jz      loc_140021F6E
0x140021c13  mov     rdx, r15
0x140021c16  lea     rcx, aDefault_0; "<DEFAULT>"
0x140021c1d  call    cs:__imp__o__wcsicmp
0x140021c23  xorps   xmm0, xmm0
0x140021c26  mov     [rsp+2C0h+var_248], r12
0x140021c2b  mov     [rbp+1C0h+var_240], r12
0x140021c2f  movups  [rsp+2C0h+var_258], xmm0
0x140021c34  test    eax, eax
0x140021c36  jnz     loc_140021CC1
0x140021c3c  lea     r8d, [rax+0Fh]
0x140021c40  lea     rdx, aAppVDefault; "(App-V Default)"
0x140021c47  lea     rcx, [rsp+2C0h+var_258]
0x140021c4c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140021c51  lea     r9, [rbp+1C0h+var_1B8]
0x140021c55  mov     r8b, 1
0x140021c58  lea     rdx, [rsp+2C0h+var_258]
0x140021c5d  lea     rcx, [rbp+1C0h+var_1F8]
0x140021c61  call    cs:__imp_CreatePackageMachinePolicyDocument
0x140021c67  mov     rbx, rax
0x140021c6a  lea     rcx, [rsp+2C0h+var_258]
0x140021c6f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140021c74  bt      rbx, 27h ; '''
0x140021c79  jb      loc_140021EF6
0x140021c7f  mov     [r14], rbx
0x140021c82  mov     edi, 8000FFFFh
0x140021c87  mov     [rbp+1C0h+var_130], edi
0x140021c8d  lea     rcx, [rbp+1C0h+var_210]; this
0x140021c91  call    ??1ConfigurePackageData@Client@AppV@@UEAA@XZ; AppV::Client::ConfigurePackageData::~ConfigurePackageData(void)
0x140021c96  nop
0x140021c97  lea     rcx, [rsp+2C0h+var_290]; this
0x140021c9c  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140021ca1  nop
0x140021ca2  lea     rcx, [rbp+1C0h+var_140]; this
0x140021ca9  call    ??1SmartTelemetryAddPackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryAddPackageLogger::~SmartTelemetryAddPackageLogger(void)
0x140021cae  mov     rbx, [rsp+2C0h+var_280]
0x140021cb3  test    rbx, rbx
0x140021cb6  jz      loc_140021992
0x140021cbc  jmp     loc_14002195F
0x140021cc1  mov     r8, rsi
0x140021cc4  inc     r8
0x140021cc7  cmp     [r15+r8*2], r12w
0x140021ccc  jnz     short loc_140021CC4
0x140021cce  mov     rdx, r15
0x140021cd1  lea     rcx, [rsp+2C0h+var_258]
0x140021cd6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140021cdb  lea     r8, [rbp+1C0h+var_1B8]
0x140021cdf  mov     dl, 1
0x140021ce1  lea     rcx, [rsp+2C0h+var_258]
0x140021ce6  call    cs:__imp_CreatePackageMachinePolicyDocumentFromFile
0x140021cec  mov     rbx, rax
0x140021cef  lea     rcx, [rsp+2C0h+var_258]
0x140021cf4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140021cf9  bt      rbx, 27h ; '''
0x140021cfe  jb      loc_140021EF6
0x140021d04  mov     [r14], rbx
0x140021d07  mov     r14d, 5Ch ; '\'
0x140021d0d  mov     edx, r14d; Ch
0x140021d10  lea     rdi, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140021d17  mov     rcx, rdi; Str
0x140021d1a  call    cs:__imp_strrchr
0x140021d20  test    rax, rax
0x140021d23  jz      short loc_140021D2A
0x140021d25  inc     rax
0x140021d28  jmp     short loc_140021D2D
0x140021d2a  mov     rax, rdi
0x140021d2d  mov     rdx, rax; char *
0x140021d30  lea     r13, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; AppV::FileLookUp MeyersSingleton<AppV::FileLookUp>::instance_
0x140021d37  mov     rcx, r13; this
  ... truncated ...
```
