# AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask(ATL::CComPtr<ITaskService> const &,ATL::CComPtr<ITaskFolder> const &,AppV::Client::Publishing::Configurations::ServerProperties const &,bool,bool)

- ea: `0x14005f7c8`
- end: `0x140060212`
- name: `?CreateTask@ServerTaskRecord@Configurations@Publishing@Client@AppV@@CA_KAEBV?$CComPtr@UITaskService@@@ATL@@AEBV?$CComPtr@UITaskFolder@@@7@AEBUServerProperties@2345@_N3@Z`
- size: `2634`
- prototype: `__int64 __fastcall(__int64, OLECHAR ***, unsigned int *, char, char)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005f734`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a08`
- `0x140006a94`
- `0x140008e64`
- `0x14000a2e8`
- `0x140010158`
- `0x1400165b4`
- `0x140018bec`
- `0x14001d6e4`
- `0x140020c60`
- `0x14003becc`
- `0x14003c034`
- `0x14003c414`
- `0x14003c5d4`
- `0x14003c660`
- `0x140040698`
- `0x140042bc0`
- `0x14004564c`
- `0x14005ea80`
- `0x14005f7c8`
- `0x140060f20`
- `0x140062dd8`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005fdd1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400600de`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005fdd1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400600de`
- `OLEAUT32!__imp_SysAllocString` at `0x14005fe9e`
- `OLEAUT32!__imp_SysAllocString` at `0x14005feec`
- `OLEAUT32!__imp_SysAllocString` at `0x14005fe9e`
- `OLEAUT32!__imp_SysAllocString` at `0x14005feec`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ff7f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ff93`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ff7f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ff93`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe44`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe58`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe6e`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe44`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe58`
- `OLEAUT32!__imp_VariantInit` at `0x14005fe6e`
- `OLEAUT32!__imp_VariantClear` at `0x14005ff9e`
- `OLEAUT32!__imp_VariantClear` at `0x14005ffb0`
- `OLEAUT32!__imp_VariantClear` at `0x14005ffc2`
- `OLEAUT32!__imp_VariantClear` at `0x14005ff9e`
- `OLEAUT32!__imp_VariantClear` at `0x14005ffb0`
- `OLEAUT32!__imp_VariantClear` at `0x14005ffc2`

## string_xrefs

- `0x14005fd01`: `Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%`
- `0x14005fc5c`: `InstallPath`
- `0x14005fdca`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x14005fde1`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x1400600d7`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x1400600ee`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x14005f980`: `Configuration value for Sync On Batteries is %1%`
- `0x14005f94f`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask`
- `0x14005fcd0`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask`
- `0x14005ffdb`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask`
- `0x14005fa90`: ` -PublishFromXML`
- `0x14006000c`: `Task Folder couldn't register the task.\n HResult: %1%\n XML: %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask(
        __int64 a1,
        OLECHAR ***a2,
        unsigned int *a3,
        char a4,
        char a5)
{
  unsigned __int64 v8; // rdi
  BSTR v9; // r12
  bool v10; // zf
  __int64 v11; // r8
  __int64 *v12; // r9
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 *v15; // r9
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 *v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rbx
  char *v35; // rax
  const char *v36; // rax
  unsigned __int64 FileId; // rax
  __int64 v38; // rbx
  OLECHAR **v39; // r13
  __int128 v40; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v42; // xmm8
  IRecordInfo *v43; // xmm9_8
  int v44; // r8d
  int v45; // r9d
  __int128 v46; // xmm10
  IRecordInfo *v47; // xmm11_8
  OLECHAR *v48; // rcx
  OLECHAR *v49; // rdi
  BSTR v50; // rax
  __int64 TaskName; // rax
  OLECHAR *v52; // rbx
  BSTR v53; // rdx
  BSTR v54; // rax
  HRESULT v55; // eax
  HRESULT v56; // eax
  HRESULT v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  OLECHAR *v61; // rcx
  __int64 v62; // rbx
  char *v63; // rax
  const char *v64; // rax
  unsigned __int64 v65; // rax
  int v67; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v68; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v69; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+68h] [rbp-A0h] BYREF
  OLECHAR *v71; // [rsp+70h] [rbp-98h] BYREF
  BSTR v72; // [rsp+78h] [rbp-90h]
  BSTR v73; // [rsp+80h] [rbp-88h]
  VARIANTARG v74; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v75; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v77; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v78; // [rsp+E8h] [rbp-20h]
  __int128 v79; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v80; // [rsp+108h] [rbp+0h]
  OLECHAR psz[4]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 v82; // [rsp+130h] [rbp+28h]
  _BYTE v83[32]; // [rsp+138h] [rbp+30h] BYREF
  int v84; // [rsp+158h] [rbp+50h]
  _OWORD Src[2]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v86; // [rsp+188h] [rbp+80h] BYREF
  _QWORD v87[4]; // [rsp+198h] [rbp+90h] BYREF
  _OWORD v88[2]; // [rsp+1B8h] [rbp+B0h] BYREF

  v8 = -(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFF4uLL;
  v9 = 0;
  if ( !*((_BYTE *)a3 + v8 + 84) )
    return 0x8000000000LL;
  if ( *((_BYTE *)a3 + 5) )
  {
    if ( a5 )
      goto LABEL_8;
  }
  else if ( a5 )
  {
    v10 = *(unsigned int *)((char *)a3 + v8 + 88) == 0;
    goto LABEL_7;
  }
  v10 = *((_BYTE *)a3 + v8 + 85) == 0;
LABEL_7:
  if ( v10 )
    return 0x8000000000LL;
LABEL_8:
  std::wstring::wstring(psz, &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskXml);
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  v12 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskUsersGroupXml;
  if ( a4 )
  {
    if ( a5 )
      v12 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskSystemUserXml;
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerTaskRunner,
      v11,
      v12);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerMultiInstancesPolicy,
      v13,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskSingleInstance);
    v15 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskCommandScript;
  }
  else
  {
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerTaskRunner,
      v11,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskUsersGroupXml);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerMultiInstancesPolicy,
      v16,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskMultiInstances);
    v15 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskCommandExe;
  }
  appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
    psz,
    AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForSyncCommand,
    v14,
    v15);
  v67 = 0;
  v77 = 0;
  v78 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v77, L"Client\\PowerManagement\\SyncOnBatteriesEnabled", 45);
  AppV::ClientConfiguration::GetConfigurationValue(&v77, &v67);
  std::wstring::~wstring(&v77);
  std::string::string(v83, "AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask");
  v84 = 433;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
  v79 = 0;
  v80 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v79, L"Configuration value for Sync On Batteries is %1%", 48);
  v18 = AppV::Log::fmt(v17, &v86, &v79);
  v19 = AppV::LogFormatter::operator%<unsigned long>(v18, &v67);
  v77 = 0;
  v78 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v77, L"Publishing", 10);
  AppV::DecoratedLog::operator()(v83, 8, &v77, v19);
  std::wstring::~wstring(&v77);
  *(_QWORD *)&v86 = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v87);
  std::wstring::~wstring(&v79);
  std::string::~string(v83);
  v20 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskEnableSyncOnBatteries;
  if ( !v67 )
    v20 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskDisableSyncOnBatteries;
  appv::string::replace_all(
    psz,
    AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerSyncOnBatteriesPolicy,
    v20);
  if ( !*((_BYTE *)a3 + 5) )
  {
    AppV::Client::Publishing::Configurations::ServerTaskRecord::UIntToString(&v77, *a3);
    std::wstring::append(Src);
    std::wstring::~wstring(&v77);
  }
  if ( a4 )
    std::wstring::append(Src, L" -Global");
  if ( *((_BYTE *)a3 + 5) )
  {
    std::wstring::append(Src, L" -PublishFromXML");
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v77, &qword_140088C88, 0);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForLogonTrigger,
      v21,
      &v77);
    std::wstring::~wstring(&v77);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicTrigger,
      v22,
      &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskRegistrationTriggerXml);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerRestartOnFailurePolicy,
      v23,
      &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskRestartOnFailureSettingXml);
  }
  std::wstring::append(Src, L" -NetworkCostAware");
  if ( !*((_BYTE *)a3 + 5) )
  {
    if ( a5 )
    {
      std::wstring::wstring(&v77, &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskDailyTriggerXml);
      if ( !*(unsigned int *)((char *)a3 + v8 + 92) )
        std::wstring::operator=(
          &v77,
          &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskHourlyTriggerXml);
      v25 = AppV::Client::Publishing::Configurations::ServerTaskRecord::UIntToString(
              &v79,
              *(unsigned int *)((char *)a3 + v8 + 88));
      appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
        &v77,
        AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicInterval,
        v26,
        v25);
      std::wstring::~wstring(&v79);
      appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
        psz,
        AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicTrigger,
        v27,
        &v77);
      std::wstring::append(Src, L" -HidePublishingRefreshUI");
      std::wstring::~wstring(&v77);
    }
    else if ( *((_BYTE *)a3 + v8 + 85) )
    {
      appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
        psz,
        AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForLogonTrigger,
        v24,
        &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskLogonTriggerXml);
    }
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v77, &qword_140088C88, 0);
    appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
      psz,
      AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerRestartOnFailurePolicy,
      v28,
      &v77);
    std::wstring::~wstring(&v77);
  }
  appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
    psz,
    AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForCmdArguments,
    v24,
    Src);
  v88[0] = 0;
  v88[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v88[0]) = 0;
  v79 = 0;
  v80 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v79, L"InstallPath", 11);
  v77 = 0;
  v78 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v77, L"SOFTWARE\\Microsoft\\AppV\\Client", 30);
  v68 = softgrid::registry::RegReadString(-2147483646, &v77, &v79, v88);
  std::wstring::~wstring(&v77);
  std::wstring::~wstring(&v79);
  if ( v68 )
  {
    std::string::string(v83, "AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask");
    v84 = 507;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v79 = 0;
    v80 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v79,
      L"Couldn't read registry string.\n winerr = %1%\n sub key: %2%\n value name: %3%",
      75);
    v31 = AppV::Log::fmt(v30, &v86, &v79);
    v32 = AppV::LogFormatter::operator%<unsigned long>(v31, &v68);
    v33 = AppV::LogFormatter::operator%<wchar_t const *>(v32, off_140072480);
    v34 = AppV::LogFormatter::operator%<wchar_t const *>(v33, &off_140072488);
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v77, L"Publishing", 10);
    AppV::DecoratedLog::operator()(v83, 1, &v77, v34);
    std::wstring::~wstring(&v77);
    *(_QWORD *)&v86 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v87);
    std::wstring::~wstring(&v79);
    std::string::~string(v83);
    v35 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v35 )
      v36 = v35 + 1;
    else
      v36 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v36);
    v38 = v68 | (FileId << 52) | 0x3F2700000000LL;
LABEL_57:
    std::wstring::~wstring(v88);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(psz);
    return v38;
  }
  appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
    psz,
    AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForAppVClientPath,
    v29,
    v88);
  v70 = 0;
  v39 = *a2;
  v71 = *v39;
  VariantInit(&pvarg);
  v40 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v75);
  v42 = *(_OWORD *)&v75.vt;
  v43 = v75.pRecInfo;
  VariantInit(&v74);
  v46 = *(_OWORD *)&v74.vt;
  v47 = v74.pRecInfo;
  if ( v82 <= 7 )
  {
    v48 = psz;
    goto LABEL_38;
  }
  v48 = *(OLECHAR **)psz;
  if ( *(_QWORD *)psz )
  {
LABEL_38:
    v50 = SysAllocString(v48);
    v49 = v50;
    v72 = v50;
    if ( !v50 )
      ATL::AtlThrowImpl(-2147024882);
    v9 = v50;
    goto LABEL_40;
  }
  v49 = 0;
  v72 = 0;
LABEL_40:
  LOBYTE(v45) = a5;
  LOBYTE(v44) = a4;
  TaskName = AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskName(
               (unsigned int)v83,
               *a3,
               v44,
               v45,
               0);
  if ( *(_QWORD *)(TaskName + 24) > 7u )
    TaskName = *(_QWORD *)TaskName;
  if ( TaskName )
  {
    v54 = SysAllocString((const OLECHAR *)TaskName);
    v52 = v54;
    v73 = v54;
    if ( !v54 )
      ATL::AtlThrowImpl(-2147024882);
    v53 = v54;
  }
  else
  {
    v52 = 0;
    v73 = 0;
    v53 = 0;
  }
  v86 = v40;
  v87[0] = pRecInfo;
  v79 = v42;
  *(_QWORD *)&v80 = v43;
  v77 = v46;
  *(_QWORD *)&v78 = v47;
  LODWORD(v69) = (*((__int64 (__fastcall **)(OLECHAR **, BSTR, BSTR, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))v71
                  + 16))(
                   v39,
                   v53,
                   v9,
                   2,
                   &v77,
                   &v79,
                   3,
                   &v86,
                   &v70);
  SysFreeString(v52);
  std::wstring::~wstring(v83);
  SysFreeString(v49);
  v55 = VariantClear(&v74);
  if ( v55 < 0 )
    _com_issue_error(v55);
  v56 = VariantClear(&v75);
  if ( v56 < 0 )
    _com_issue_error(v56);
  v57 = VariantClear(&pvarg);
  if ( v57 < 0 )
    _com_issue_error(v57);
  if ( (int)v69 < 0 )
  {
    std::string::string(v83, "AppV::Client::Publishing::Configurations::ServerTaskRecord::CreateTask");
    v84 = 531;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v79 = 0;
    v80 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v79,
      L"Task Folder couldn't register the task.\n HResult: %1%\n XML: %2%",
      63);
    v59 = AppV::Log::fmt(v58, &v86, &v79);
    v60 = AppV::LogFormatter::operator%<long>(v59, &v69);
    v61 = psz;
    if ( v82 > 7 )
      v61 = *(OLECHAR **)psz;
    v71 = v61;
    v62 = AppV::LogFormatter::operator%<wchar_t const *>(v60, &v71);
    v77 = 0;
    v78 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v77, L"Publishing", 10);
    AppV::DecoratedLog::operator()(v83, 1, &v77, v62);
    std::wstring::~wstring(&v77);
    *(_QWORD *)&v86 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v87);
    std::wstring::~wstring(&v79);
    std::string::~string(v83);
    v63 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v63 )
      v64 = v63 + 1;
    else
      v64 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    v65 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v64);
    v38 = (unsigned int)v69 | (v65 << 52) | 0x422700000000LL;
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    goto LABEL_57;
  }
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  std::wstring::~wstring(v88);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(psz);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005f7c8  mov     rax, rsp
0x14005f7cb  mov     [rax+8], rbx
0x14005f7cf  push    rbp
0x14005f7d0  push    rsi
0x14005f7d1  push    rdi
0x14005f7d2  push    r12
0x14005f7d4  push    r13
0x14005f7d6  push    r14
0x14005f7d8  push    r15
0x14005f7da  lea     rbp, [rax-178h]
0x14005f7e1  sub     rsp, 240h
0x14005f7e8  movaps  xmmword ptr [rax-48h], xmm6
0x14005f7ec  movaps  xmmword ptr [rax-58h], xmm7
0x14005f7f0  movaps  xmmword ptr [rax-68h], xmm8
0x14005f7f5  movaps  xmmword ptr [rax-78h], xmm9
0x14005f7fa  movaps  xmmword ptr [rax-88h], xmm10
0x14005f802  movaps  xmmword ptr [rax-98h], xmm11
0x14005f80a  mov     rax, cs:__security_cookie
0x14005f811  xor     rax, rsp
0x14005f814  mov     [rbp+170h+var_A0], rax
0x14005f81b  mov     r15b, r9b
0x14005f81e  mov     rsi, r8
0x14005f821  mov     r13, rdx
0x14005f824  mov     r14b, [rbp+170h+arg_20]
0x14005f82b  mov     al, r9b
0x14005f82e  neg     al
0x14005f830  sbb     rdi, rdi
0x14005f833  and     rdi, 0FFFFFFFFFFFFFFF4h
0x14005f837  xor     r12d, r12d
0x14005f83a  cmp     [rdi+r8+54h], r12b
0x14005f83f  jz      loc_140060192
0x14005f845  cmp     [r8+5], r12b
0x14005f849  jnz     short loc_14005F857
0x14005f84b  test    r14b, r14b
0x14005f84e  jz      short loc_14005F85C
0x14005f850  cmp     [rdi+r8+58h], r12d
0x14005f855  jmp     short loc_14005F861
0x14005f857  test    r14b, r14b
0x14005f85a  jnz     short loc_14005F867
0x14005f85c  cmp     [rdi+r8+55h], r12b
0x14005f861  jz      loc_140060192
0x14005f867  lea     rdx, ?sm_taskXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskXml
0x14005f86e  lea     rcx, [rbp+170h+psz]
0x14005f872  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14005f877  nop
0x14005f878  xorps   xmm0, xmm0
0x14005f87b  movups  [rbp+170h+Src], xmm0
0x14005f87f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14005f887  movdqu  [rbp+170h+var_108], xmm1
0x14005f88c  mov     word ptr [rbp+170h+Src], r12w
0x14005f891  lea     rdx, ?sm_markerTaskRunner@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerTaskRunner
0x14005f898  lea     rcx, [rbp+170h+psz]
0x14005f89c  lea     r9, ?sm_taskUsersGroupXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskUsersGroupXml
0x14005f8a3  test    r15b, r15b
0x14005f8a6  jz      short loc_14005F8D9
0x14005f8a8  test    r14b, r14b
0x14005f8ab  jz      short loc_14005F8B4
0x14005f8ad  lea     r9, ?sm_taskSystemUserXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskSystemUserXml
0x14005f8b4  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005f8b9  lea     r9, ?sm_taskSingleInstance@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskSingleInstance
0x14005f8c0  lea     rdx, ?sm_markerMultiInstancesPolicy@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerMultiInstancesPolicy
0x14005f8c7  lea     rcx, [rbp+170h+psz]
0x14005f8cb  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005f8d0  lea     r9, ?sm_taskCommandScript@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskCommandScript
0x14005f8d7  jmp     short loc_14005F8FC
0x14005f8d9  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005f8de  lea     r9, ?sm_taskMultiInstances@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskMultiInstances
0x14005f8e5  lea     rdx, ?sm_markerMultiInstancesPolicy@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerMultiInstancesPolicy
0x14005f8ec  lea     rcx, [rbp+170h+psz]
0x14005f8f0  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005f8f5  lea     r9, ?sm_taskCommandExe@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskCommandExe
0x14005f8fc  lea     rdx, ?sm_markerForSyncCommand@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForSyncCommand
0x14005f903  lea     rcx, [rbp+170h+psz]
0x14005f907  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005f90c  mov     [rsp+270h+var_220], r12d
0x14005f911  xorps   xmm0, xmm0
0x14005f914  movups  [rbp+170h+var_1A0], xmm0
0x14005f918  xorps   xmm1, xmm1
0x14005f91b  movdqu  [rbp+170h+var_190], xmm1
0x14005f920  mov     r8d, 2Dh ; '-'
0x14005f926  lea     rdx, aClientPowerman_0; "Client\\PowerManagement\\SyncOnBatterie"...
0x14005f92d  lea     rcx, [rbp+170h+var_1A0]
0x14005f931  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005f936  nop
0x14005f937  lea     rdx, [rsp+270h+var_220]
0x14005f93c  lea     rcx, [rbp+170h+var_1A0]
0x14005f940  call    ?GetConfigurationValue@ClientConfiguration@AppV@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAK@Z; AppV::ClientConfiguration::GetConfigurationValue(std::wstring const &,ulong &)
0x14005f945  nop
0x14005f946  lea     rcx, [rbp+170h+var_1A0]
0x14005f94a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005f94f  lea     rdx, aAppvClientPubl_3; "AppV::Client::Publishing::Configuration"...
0x14005f956  lea     rcx, [rbp+170h+var_140]
0x14005f95a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005f95f  mov     [rbp+170h+var_120], 1B1h
0x14005f966  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005f96b  xorps   xmm0, xmm0
0x14005f96e  movups  [rbp+170h+var_180], xmm0
0x14005f972  xorps   xmm1, xmm1
0x14005f975  movdqu  [rbp+170h+var_170], xmm1
0x14005f97a  mov     r8d, 30h ; '0'
0x14005f980  lea     rdx, aConfigurationV; "Configuration value for Sync On Batteri"...
0x14005f987  lea     rcx, [rbp+170h+var_180]
0x14005f98b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005f990  nop
0x14005f991  lea     r8, [rbp+170h+var_180]
0x14005f995  lea     rdx, [rbp+170h+var_F0]
0x14005f99c  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005f9a1  nop
0x14005f9a2  lea     rdx, [rsp+270h+var_220]
0x14005f9a7  mov     rcx, rax
0x14005f9aa  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14005f9af  mov     rbx, rax
0x14005f9b2  xorps   xmm0, xmm0
0x14005f9b5  movups  [rbp+170h+var_1A0], xmm0
0x14005f9b9  xorps   xmm1, xmm1
0x14005f9bc  movdqu  [rbp+170h+var_190], xmm1
0x14005f9c1  mov     r8d, 0Ah
0x14005f9c7  lea     rdx, aPublishing; "Publishing"
0x14005f9ce  lea     rcx, [rbp+170h+var_1A0]
0x14005f9d2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005f9d7  nop
0x14005f9d8  mov     r9, rbx
0x14005f9db  lea     r8, [rbp+170h+var_1A0]
0x14005f9df  mov     edx, 8
0x14005f9e4  lea     rcx, [rbp+170h+var_140]
0x14005f9e8  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005f9ed  nop
0x14005f9ee  lea     rcx, [rbp+170h+var_1A0]
0x14005f9f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005f9f7  nop
0x14005f9f8  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005f9ff  mov     qword ptr [rbp+170h+var_F0], rax
0x14005fa06  lea     rcx, [rbp+170h+var_E0]
0x14005fa0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fa12  nop
0x14005fa13  lea     rcx, [rbp+170h+var_180]
0x14005fa17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fa1c  nop
0x14005fa1d  lea     rcx, [rbp+170h+var_140]
0x14005fa21  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005fa26  lea     r8, ?sm_taskEnableSyncOnBatteries@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskEnableSyncOnBatteries
0x14005fa2d  lea     rax, ?sm_taskDisableSyncOnBatteries@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskDisableSyncOnBatteries
0x14005fa34  cmp     [rsp+270h+var_220], r12d
0x14005fa39  cmovz   r8, rax
0x14005fa3d  lea     rdx, ?sm_markerSyncOnBatteriesPolicy@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerSyncOnBatteriesPolicy
0x14005fa44  lea     rcx, [rbp+170h+psz]
0x14005fa48  call    ?replace_all@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@1@Z; appv::string::replace_all(std::wstring &,std::wstring const &,std::wstring const &)
0x14005fa4d  cmp     [rsi+5], r12b
0x14005fa51  jnz     short loc_14005FA75
0x14005fa53  mov     edx, [rsi]
0x14005fa55  lea     rcx, [rbp+170h+var_1A0]
0x14005fa59  call    ?UIntToString@ServerTaskRecord@Configurations@Publishing@Client@AppV@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; AppV::Client::Publishing::Configurations::ServerTaskRecord::UIntToString(uint)
0x14005fa5e  nop
0x14005fa5f  mov     rdx, rax
0x14005fa62  lea     rcx, [rbp+170h+Src]; Src
0x14005fa66  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14005fa6b  nop
0x14005fa6c  lea     rcx, [rbp+170h+var_1A0]
0x14005fa70  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fa75  test    r15b, r15b
0x14005fa78  jz      short loc_14005FA8A
0x14005fa7a  lea     rdx, aGlobal; " -Global"
0x14005fa81  lea     rcx, [rbp+170h+Src]; Src
0x14005fa85  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14005fa8a  cmp     [rsi+5], r12b
0x14005fa8e  jz      short loc_14005FB0F
0x14005fa90  lea     rdx, aPublishfromxml_1; " -PublishFromXML"
0x14005fa97  lea     rcx, [rbp+170h+Src]; Src
0x14005fa9b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14005faa0  xorps   xmm0, xmm0
0x14005faa3  movups  [rbp+170h+var_1A0], xmm0
0x14005faa7  xorps   xmm1, xmm1
0x14005faaa  movdqu  [rbp+170h+var_190], xmm1
0x14005faaf  xor     r8d, r8d
0x14005fab2  lea     rdx, qword_140088C88
0x14005fab9  lea     rcx, [rbp+170h+var_1A0]
0x14005fabd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005fac2  nop
0x14005fac3  lea     r9, [rbp+170h+var_1A0]
0x14005fac7  lea     rdx, ?sm_markerForLogonTrigger@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForLogonTrigger
0x14005face  lea     rcx, [rbp+170h+psz]
0x14005fad2  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fad7  nop
0x14005fad8  lea     rcx, [rbp+170h+var_1A0]
0x14005fadc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fae1  lea     r9, ?sm_taskRegistrationTriggerXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskRegistrationTriggerXml
0x14005fae8  lea     rdx, ?sm_markerForPeriodicTrigger@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicTrigger
0x14005faef  lea     rcx, [rbp+170h+psz]
0x14005faf3  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005faf8  lea     r9, ?sm_taskRestartOnFailureSettingXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskRestartOnFailureSettingXml
0x14005faff  lea     rdx, ?sm_markerRestartOnFailurePolicy@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerRestartOnFailurePolicy
0x14005fb06  lea     rcx, [rbp+170h+psz]
0x14005fb0a  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fb0f  lea     rdx, aNetworkcostawa; " -NetworkCostAware"
0x14005fb16  lea     rcx, [rbp+170h+Src]; Src
0x14005fb1a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14005fb1f  cmp     [rsi+5], r12b
0x14005fb23  jnz     loc_14005FC14
0x14005fb29  test    r14b, r14b
0x14005fb2c  jz      loc_14005FBB5
0x14005fb32  lea     rdx, ?sm_taskDailyTriggerXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskDailyTriggerXml
0x14005fb39  lea     rcx, [rbp+170h+var_1A0]
0x14005fb3d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14005fb42  nop
0x14005fb43  cmp     [rdi+rsi+5Ch], r12d
0x14005fb48  jnz     short loc_14005FB5A
0x14005fb4a  lea     rdx, ?sm_taskHourlyTriggerXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskHourlyTriggerXml
0x14005fb51  lea     rcx, [rbp+170h+var_1A0]
0x14005fb55  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14005fb5a  mov     edx, [rdi+rsi+58h]
0x14005fb5e  lea     rcx, [rbp+170h+var_180]
0x14005fb62  call    ?UIntToString@ServerTaskRecord@Configurations@Publishing@Client@AppV@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; AppV::Client::Publishing::Configurations::ServerTaskRecord::UIntToString(uint)
0x14005fb67  nop
0x14005fb68  mov     r9, rax
0x14005fb6b  lea     rdx, ?sm_markerForPeriodicInterval@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicInterval
0x14005fb72  lea     rcx, [rbp+170h+var_1A0]
0x14005fb76  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fb7b  nop
0x14005fb7c  lea     rcx, [rbp+170h+var_180]
0x14005fb80  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fb85  lea     r9, [rbp+170h+var_1A0]
0x14005fb89  lea     rdx, ?sm_markerForPeriodicTrigger@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForPeriodicTrigger
0x14005fb90  lea     rcx, [rbp+170h+psz]
0x14005fb94  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fb99  lea     rdx, aHidepublishing; " -HidePublishingRefreshUI"
0x14005fba0  lea     rcx, [rbp+170h+Src]; Src
0x14005fba4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14005fba9  nop
0x14005fbaa  lea     rcx, [rbp+170h+var_1A0]
0x14005fbae  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fbb3  jmp     short loc_14005FBD3
0x14005fbb5  cmp     [rdi+rsi+55h], r12b
0x14005fbba  jz      short loc_14005FBD3
0x14005fbbc  lea     r9, ?sm_taskLogonTriggerXml@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_taskLogonTriggerXml
0x14005fbc3  lea     rdx, ?sm_markerForLogonTrigger@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForLogonTrigger
0x14005fbca  lea     rcx, [rbp+170h+psz]
0x14005fbce  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fbd3  xorps   xmm0, xmm0
0x14005fbd6  movups  [rbp+170h+var_1A0], xmm0
0x14005fbda  xorps   xmm1, xmm1
0x14005fbdd  movdqu  [rbp+170h+var_190], xmm1
0x14005fbe2  xor     r8d, r8d
0x14005fbe5  lea     rdx, qword_140088C88
0x14005fbec  lea     rcx, [rbp+170h+var_1A0]
0x14005fbf0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005fbf5  nop
0x14005fbf6  lea     r9, [rbp+170h+var_1A0]
0x14005fbfa  lea     rdx, ?sm_markerRestartOnFailurePolicy@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerRestartOnFailurePolicy
0x14005fc01  lea     rcx, [rbp+170h+psz]
0x14005fc05  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fc0a  nop
0x14005fc0b  lea     rcx, [rbp+170h+var_1A0]
0x14005fc0f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fc14  lea     r9, [rbp+170h+Src]
0x14005fc18  lea     rdx, ?sm_markerForCmdArguments@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_markerForCmdArguments
0x14005fc1f  lea     rcx, [rbp+170h+psz]
0x14005fc23  call    ??$replace_nth_helper@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@string@appv@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@H1@Z; appv::string::replace_nth_helper<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring &,std::wstring const &,int,std::wstring const &)
0x14005fc28  xorps   xmm0, xmm0
0x14005fc2b  movups  [rbp+170h+var_C0], xmm0
0x14005fc32  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14005fc3a  movdqu  [rbp+170h+var_B0], xmm1
0x14005fc42  mov     word ptr [rbp+170h+var_C0], r12w
0x14005fc4a  movups  [rbp+170h+var_180], xmm0
0x14005fc4e  xorps   xmm1, xmm1
0x14005fc51  movdqu  [rbp+170h+var_170], xmm1
0x14005fc56  mov     r8d, 0Bh
0x14005fc5c  lea     rdx, aInstallpath; "InstallPath"
0x14005fc63  lea     rcx, [rbp+170h+var_180]
0x14005fc67  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005fc6c  nop
0x14005fc6d  xorps   xmm0, xmm0
0x14005fc70  movups  [rbp+170h+var_1A0], xmm0
0x14005fc74  xorps   xmm1, xmm1
0x14005fc77  movdqu  [rbp+170h+var_190], xmm1
0x14005fc7c  mov     r8d, 1Eh
0x14005fc82  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\AppV\\Client"
0x14005fc89  lea     rcx, [rbp+170h+var_1A0]
0x14005fc8d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005fc92  nop
0x14005fc93  lea     r9, [rbp+170h+var_C0]
0x14005fc9a  lea     r8, [rbp+170h+var_180]
0x14005fc9e  lea     rdx, [rbp+170h+var_1A0]
0x14005fca2  mov     rcx, 0FFFFFFFF80000002h
0x14005fca9  call    ?RegReadString@registry@softgrid@@YAJPEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV45@K@Z; softgrid::registry::RegReadString(HKEY__ *,std::wstring const &,std::wstring const &,std::wstring &,ulong)
0x14005fcae  mov     [rsp+270h+var_21C], eax
0x14005fcb2  lea     rcx, [rbp+170h+var_1A0]
0x14005fcb6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fcbb  nop
0x14005fcbc  lea     rcx, [rbp+170h+var_180]
0x14005fcc0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005fcc5  cmp     [rsp+270h+var_21C], r12d
0x14005fcca  jz      loc_14005FE17
0x14005fcd0  lea     rdx, aAppvClientPubl_3; "AppV::Client::Publishing::Configuration"...
0x14005fcd7  lea     rcx, [rbp+170h+var_140]
0x14005fcdb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005fce0  mov     [rbp+170h+var_120], 1FBh
0x14005fce7  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005fcec  xorps   xmm0, xmm0
0x14005fcef  movups  [rbp+170h+var_180], xmm0
0x14005fcf3  xorps   xmm1, xmm1
  ... truncated ...
```
