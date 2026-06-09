# AppV::Client::Service::AppVClientImpl::PublishPackage(wchar_t *,wchar_t *,wchar_t *,short,wchar_t *,tagVARIANT,unsigned __int64 *)

- ea: `0x14002b460`
- end: `0x14002be1e`
- name: `?PublishPackage@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W00F0UtagVARIANT@@PEA_K@Z`
- size: `2494`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl *this, wchar_t *, wchar_t *, wchar_t *, unsigned __int16, wchar_t *psz, struct tagVARIANT *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140008224`
- `0x140008e64`
- `0x1400090cc`
- `0x140010158`
- `0x1400165b4`
- `0x14001f0d0`
- `0x14001f7e4`
- `0x140020460`
- `0x140020bec`
- `0x1400233dc`
- `0x140026dd0`
- `0x140028a04`
- `0x140028e00`
- `0x14002a718`
- `0x14002b460`
- `0x1400360a0`
- `0x1400361e0`
- `0x140036680`
- `0x14003a198`
- `0x14003a24c`
- `0x14003a4dc`
- `0x14003b044`
- `0x14003becc`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14003e38c`
- `0x140046c58`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14002b96b`
- `ADVAPI32!EventActivityIdControl` at `0x14002bb41`
- `ADVAPI32!EventActivityIdControl` at `0x14002bdbd`
- `ADVAPI32!EventActivityIdControl` at `0x14002be03`
- `ADVAPI32!EventActivityIdControl` at `0x14002b96b`
- `ADVAPI32!EventActivityIdControl` at `0x14002bb41`
- `ADVAPI32!EventActivityIdControl` at `0x14002bdbd`
- `ADVAPI32!EventActivityIdControl` at `0x14002be03`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b4e5`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b4e5`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b50d`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b527`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b883`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b9bb`
- `OLEAUT32!__imp_SysStringLen` at `0x14002bc21`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b50d`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b527`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b883`
- `OLEAUT32!__imp_SysStringLen` at `0x14002b9bb`
- `OLEAUT32!__imp_SysStringLen` at `0x14002bc21`

## string_xrefs

- `0x14002b570`: `AppV::Client::Service::AppVClientImpl::PublishPackage`
- `0x14002b703`: `AppV::Client::Service::AppVClientImpl::PublishPackage`

## pseudocode

```c
__int64 __fastcall AppV::Client::Service::AppVClientImpl::PublishPackage(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        unsigned __int16 a5,
        wchar_t *psz,
        struct tagVARIANT *a7,
        unsigned __int64 *a8)
{
  BSTR *v11; // rax
  BSTR *v12; // rdi
  BSTR v13; // rax
  unsigned __int64 PackageIDAndPackageVersionID; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  bool v18; // zf
  __int64 MachinePackageSequencerVersion; // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  UINT v25; // eax
  UINT v26; // ebx
  unsigned __int64 v27; // rax
  unsigned int v28; // ebx
  char v30; // dl
  int v31; // eax
  int v32; // ecx
  int v33; // r12d
  volatile signed __int32 *v34; // rbx
  volatile signed __int32 *v35; // rcx
  volatile signed __int32 *v36; // rbx
  unsigned __int64 v37; // rax
  volatile signed __int32 *v38; // rdi
  int v39; // eax
  unsigned int v40; // edi
  volatile signed __int32 *v41; // rbx
  char v42; // [rsp+50h] [rbp-B0h] BYREF
  bool v43; // [rsp+51h] [rbp-AFh] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  BSTR *v45; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v46; // [rsp+68h] [rbp-98h] BYREF
  void **v47; // [rsp+78h] [rbp-88h] BYREF
  int v48; // [rsp+80h] [rbp-80h]
  char v49; // [rsp+84h] [rbp-7Ch]
  __int64 v50; // [rsp+88h] [rbp-78h]
  struct tagVARIANT *v51; // [rsp+90h] [rbp-70h]
  wchar_t *v52; // [rsp+98h] [rbp-68h] BYREF
  __int128 v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h]
  __int128 v55; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v56; // [rsp+C8h] [rbp-38h]
  __int128 v57; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v58; // [rsp+E8h] [rbp-18h]
  char v59[4]; // [rsp+F8h] [rbp-8h] BYREF
  GUID ActivityId; // [rsp+FCh] [rbp-4h] BYREF
  _OWORD v61[2]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID v62; // [rsp+140h] [rbp+40h] BYREF
  struct _GUID v63; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v64[32]; // [rsp+160h] [rbp+60h] BYREF
  int v65; // [rsp+180h] [rbp+80h]
  struct _GUID v66; // [rsp+190h] [rbp+90h] BYREF
  struct _GUID v67; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v68[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v69; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v70[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v71[32]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v72[2]; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v73; // [rsp+230h] [rbp+130h]
  bool v74; // [rsp+2A0h] [rbp+1A0h]
  bool v75; // [rsp+2A1h] [rbp+1A1h]
  char v76[40]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v77[24]; // [rsp+2D0h] [rbp+1D0h] BYREF
  struct _GUID v78; // [rsp+2E8h] [rbp+1E8h]
  struct _GUID v79; // [rsp+2F8h] [rbp+1F8h]
  __int64 v80; // [rsp+378h] [rbp+278h]
  volatile signed __int32 *v81; // [rsp+380h] [rbp+280h]
  __int128 v82; // [rsp+388h] [rbp+288h]

  v52 = psz;
  v51 = a7;
  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(v59);
  v11 = (BSTR *)operator new(0x18u);
  v12 = v11;
  if ( !v11 || (v11[1] = 0, *((_DWORD *)v11 + 4) = 1, v13 = SysAllocString(psz), (*v12 = v13) == 0) && psz )
    _com_issue_error(-2147024882);
  v45 = v12;
  if ( !a2 || !SysStringLen(a2) || !a3 || !SysStringLen(a3) || !a8 )
  {
    AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)&v57,
      L"PublishPackage");
    LODWORD(v58) = -2147024809;
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger((AppV::Client::Service::SmartComMethodLogger *)&v57);
    _bstr_t::~_bstr_t((_bstr_t *)&v45);
    v18 = v59[0] == 0;
    goto LABEL_68;
  }
  v62 = GUID_NULL;
  v63 = GUID_NULL;
  PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                   a2,
                                   a3,
                                   &v62,
                                   &v63);
  if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
  {
    std::string::string(v64, "AppV::Client::Service::AppVClientImpl::PublishPackage");
    v65 = 767;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v55 = 0;
    v56 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v55, L"Failed to convert package/version GUID string to GUID: %1%", 58);
    v16 = AppV::Log::fmt(v15, &v66, &v55);
    v44 = PackageIDAndPackageVersionID;
    v17 = AppV::LogFormatter::operator%(v16, &v44);
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v57, L"Client", 6);
    AppV::DecoratedLog::operator()(v64, 1, &v57, v17);
    std::wstring::~wstring(&v57);
    *(_QWORD *)&v66.Data1 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v67);
    std::wstring::~wstring(&v55);
    std::string::~string(v64);
    *a8 = PackageIDAndPackageVersionID;
    AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)&v57,
      L"PublishPackage");
    LODWORD(v58) = -2147024809;
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger((AppV::Client::Service::SmartComMethodLogger *)&v57);
    _bstr_t::~_bstr_t((_bstr_t *)&v45);
    v18 = v59[0] == 0;
LABEL_68:
    if ( !v18 )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v55, &qword_140088C88, 0);
  v70[0] = v62;
  v70[1] = v63;
  std::wstring::wstring(v71, &v55);
  std::wstring::~wstring(&v55);
  v61[0] = 0;
  v61[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v61[0]) = 0;
  MachinePackageSequencerVersion = AppV::Client::PackageRegistry::GetMachinePackageSequencerVersion(v70, v61);
  std::string::string(v64, "AppV::Client::Service::AppVClientImpl::PublishPackage");
  if ( (MachinePackageSequencerVersion & 0x8000000000LL) != 0 )
  {
    v65 = 778;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v57, L"Got sequencer version %1%", 25);
    v21 = AppV::Log::fmt(v20, &v66, &v57);
    AppV::LogFormatter::perform_substitution<std::wstring>(v21, v61);
    v55 = 0;
    v56 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v55, L"Client", 6);
    v22 = 4;
  }
  else
  {
    v65 = 782;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v57,
      L"Failed to get sequencer version with error %1% but continue",
      59);
    v24 = AppV::Log::fmt(v23, &v66, &v57);
    v44 = MachinePackageSequencerVersion;
    v21 = AppV::LogFormatter::operator%(v24, &v44);
    v55 = 0;
    v56 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v55, L"Client", 6);
    v22 = 2;
  }
  AppV::DecoratedLog::operator()(v64, v22, &v55, v21);
  std::wstring::~wstring(&v55);
  *(_QWORD *)&v66.Data1 = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(&v67);
  std::wstring::~wstring(&v57);
  std::string::~string(v64);
  v44 = std::wstring::wstring(&v55, v61);
  v25 = 0;
  v43 = a5 != 0;
  if ( *v12 )
    v25 = SysStringLen(*v12);
  v26 = v25;
  AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(
    (AppV::Client::Service::SmartTelemetryPackageLogger *)v72,
    L"PublishPackage",
    a2,
    a3);
  v72[0] = &AppV::Client::Service::SmartTelemetryPublishPackageLogger::`vftable';
  v74 = v26 != 0;
  v75 = v43;
  std::wstring::wstring(v76, v44);
  std::wstring::~wstring(v44);
  v42 = 0;
  v43 = 0;
  v27 = AppV::Client::Service::AppVClientImpl::RequireAdminPublishEnabled(&v43);
  v28 = v27;
  if ( (v27 & 0x8000000000LL) == 0 )
  {
    *a8 = v27;
    if ( (v27 & 0x2000000000LL) != 0 )
    {
      if ( (int)v27 > 0 )
        v28 = (unsigned __int16)v27 | 0x80070000;
    }
    else
    {
      v28 = -2147418113;
    }
    v73 = v28;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)&v42);
    goto LABEL_22;
  }
  v30 = a5 == 0xFFFF || v43 || a4 && SysStringLen(a4);
  v31 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
          (AppV::Client::Service::AppVClientImpl::APICaller *)&v42,
          v30,
          a8);
  v28 = v31;
  if ( v31 < 0 )
  {
    v73 = v31;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)&v42);
LABEL_22:
    AppV::Client::Service::SmartTelemetryPublishPackageLogger::~SmartTelemetryPublishPackageLogger((AppV::Client::Service::SmartTelemetryPublishPackageLogger *)v72);
    std::wstring::~wstring(v61);
    std::wstring::~wstring(v71);
    _bstr_t::~_bstr_t((_bstr_t *)&v45);
    if ( v59[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v28;
  }
  LODWORD(v44) = 4;
  v46 = 0;
  v69 = 0;
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v55, &qword_140088C88, 0);
  v66 = v62;
  v67 = v63;
  std::wstring::wstring(v68, &v55);
  v33 = AppV::Client::Service::AppVClientImpl::SelectPublishPackagePolicy(
          v32,
          (unsigned int)&v66,
          a5,
          (unsigned int)&v52,
          (__int64)v51,
          (__int64)&v44,
          (__int64)&v46,
          (__int64)&v69,
          (__int64)a8);
  std::wstring::~wstring(v68);
  std::wstring::~wstring(&v55);
  if ( v33 >= 0 )
  {
    AppV::Client::PublishPackageData::PublishPackageData(v77, (unsigned int)v44);
    v78 = v62;
    v79 = v63;
    v35 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL));
      v35 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    }
    v80 = v46;
    v36 = v81;
    v81 = v35;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v82 = v69;
    v47 = &AppV::Client::Impersonator::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 0;
    if ( !a5 )
    {
      if ( a4 )
      {
        if ( SysStringLen(a4) )
        {
          v37 = AppV::Client::Service::AppVClientImpl::ImpersonateToUser((struct AppV::Client::Impersonator *)&v47, a4);
          v28 = v37;
          if ( (v37 & 0x8000000000LL) == 0 )
          {
            *a8 = v37;
            if ( (v37 & 0x2000000000LL) != 0 )
            {
              if ( (int)v37 > 0 )
                v28 = (unsigned __int16)v37 | 0x80070000;
            }
            else
            {
              v28 = -2147467259;
            }
            v73 = v28;
            AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v47);
            AppV::Client::PublishPackageData::~PublishPackageData((AppV::Client::PublishPackageData *)v77);
            v38 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
            if ( *((_QWORD *)&v46 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
                if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
              }
            }
            AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)&v42);
            goto LABEL_22;
          }
        }
      }
    }
    v53 = 0;
    v54 = 0;
    v39 = AppV::Client::Service::AppVClientImpl::RequestActivity(8, v77, &v53);
    v40 = AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(
            (unsigned int)v72,
            v39,
            (unsigned int)&v53,
            (_DWORD)a8,
            (__int64)v72);
    v73 = v40;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>(&v53);
    AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v47);
    AppV::Client::PublishPackageData::~PublishPackageData((AppV::Client::PublishPackageData *)v77);
    v41 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)&v42);
    AppV::Client::Service::SmartTelemetryPublishPackageLogger::~SmartTelemetryPublishPackageLogger((AppV::Client::Service::SmartTelemetryPublishPackageLogger *)v72);
    std::wstring::~wstring(v61);
    std::wstring::~wstring(v71);
    _bstr_t::~_bstr_t((_bstr_t *)&v45);
    if ( v59[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v40;
  }
  else
  {
    v73 = v33;
    v34 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)&v42);
    AppV::Client::Service::SmartTelemetryPublishPackageLogger::~SmartTelemetryPublishPackageLogger((AppV::Client::Service::SmartTelemetryPublishPackageLogger *)v72);
    std::wstring::~wstring(v61);
    std::wstring::~wstring(v71);
    _bstr_t::~_bstr_t((_bstr_t *)&v45);
    if ( v59[0] )
      EventActivityIdControl(2u, &ActivityId);
    return (unsigned int)v33;
  }
}

```

## disassembly

```asm
0x14002b460  mov     [rsp-8+arg_0], rbx
0x14002b465  push    rbp
0x14002b466  push    rsi
0x14002b467  push    rdi
0x14002b468  push    r12
0x14002b46a  push    r13
0x14002b46c  push    r14
0x14002b46e  push    r15
0x14002b470  lea     rbp, [rsp-370h]
0x14002b478  sub     rsp, 470h
0x14002b47f  mov     rax, cs:__security_cookie
0x14002b486  xor     rax, rsp
0x14002b489  mov     [rbp+3A0h+var_40], rax
0x14002b490  mov     r15, r9
0x14002b493  mov     r13, r8
0x14002b496  mov     r12, rdx
0x14002b499  mov     rbx, [rbp+3A0h+psz]
0x14002b4a0  mov     [rbp+3A0h+var_408], rbx
0x14002b4a4  mov     rax, [rbp+3A0h+arg_30]
0x14002b4ab  mov     [rbp+3A0h+var_410], rax
0x14002b4af  mov     r14, [rbp+3A0h+arg_38]
0x14002b4b6  lea     rcx, [rbp+3A0h+var_3A8]
0x14002b4ba  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x14002b4bf  mov     ecx, 18h; Size
0x14002b4c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002b4c9  mov     rdi, rax
0x14002b4cc  xor     esi, esi
0x14002b4ce  test    rax, rax
0x14002b4d1  jz      loc_14002BE13
0x14002b4d7  mov     [rax+8], rsi
0x14002b4db  mov     dword ptr [rax+10h], 1
0x14002b4e2  mov     rcx, rbx; psz
0x14002b4e5  call    cs:__imp_SysAllocString
0x14002b4eb  mov     [rdi], rax
0x14002b4ee  test    rax, rax
0x14002b4f1  jnz     short loc_14002B4FC
0x14002b4f3  test    rbx, rbx
0x14002b4f6  jnz     loc_14002BE13
0x14002b4fc  mov     [rsp+4A0h+var_440], rdi
0x14002b501  test    r12, r12
0x14002b504  jz      loc_14002BDCA
0x14002b50a  mov     rcx, r12; pbstr
0x14002b50d  call    cs:__imp_SysStringLen
0x14002b513  test    eax, eax
0x14002b515  jz      loc_14002BDCA
0x14002b51b  test    r13, r13
0x14002b51e  jz      loc_14002BDCA
0x14002b524  mov     rcx, r13; pbstr
0x14002b527  call    cs:__imp_SysStringLen
0x14002b52d  test    eax, eax
0x14002b52f  jz      loc_14002BDCA
0x14002b535  test    r14, r14
0x14002b538  jz      loc_14002BDCA
0x14002b53e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002b545  movdqu  xmmword ptr [rbp+3A0h+var_360.Data1], xmm0
0x14002b54a  movdqu  xmmword ptr [rbp+3A0h+var_350.Data1], xmm0
0x14002b54f  lea     r9, [rbp+3A0h+var_350]; struct _GUID *
0x14002b553  lea     r8, [rbp+3A0h+var_360]; struct _GUID *
0x14002b557  mov     rdx, r13; wchar_t *
0x14002b55a  mov     rcx, r12; wchar_t *
0x14002b55d  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x14002b562  mov     rsi, rax
0x14002b565  bt      rax, 27h ; '''
0x14002b56a  jb      loc_14002B67E
0x14002b570  lea     rdx, aAppvClientServ_42; "AppV::Client::Service::AppVClientImpl::"...
0x14002b577  lea     rcx, [rbp+3A0h+var_340]
0x14002b57b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b580  mov     [rbp+3A0h+var_320], 2FFh
0x14002b58a  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14002b58f  xorps   xmm0, xmm0
0x14002b592  movups  [rbp+3A0h+var_3E8], xmm0
0x14002b596  xorps   xmm1, xmm1
0x14002b599  movdqu  [rbp+3A0h+var_3D8], xmm1
0x14002b59e  mov     r8d, 3Ah ; ':'
0x14002b5a4  lea     rdx, aFailedToConver; "Failed to convert package/version GUID "...
0x14002b5ab  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b5af  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b5b4  lea     r8, [rbp+3A0h+var_3E8]
0x14002b5b8  lea     rdx, [rbp+3A0h+var_310]
0x14002b5bf  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14002b5c4  mov     [rsp+4A0h+var_448], rsi
0x14002b5c9  lea     rdx, [rsp+4A0h+var_448]
0x14002b5ce  mov     rcx, rax
0x14002b5d1  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14002b5d6  mov     rbx, rax
0x14002b5d9  xorps   xmm0, xmm0
0x14002b5dc  movups  [rbp+3A0h+var_3C8], xmm0
0x14002b5e0  xorps   xmm1, xmm1
0x14002b5e3  movdqu  [rbp+3A0h+var_3B8], xmm1
0x14002b5e8  mov     r8d, 6
0x14002b5ee  lea     rdx, aClient; "Client"
0x14002b5f5  lea     rcx, [rbp+3A0h+var_3C8]
0x14002b5f9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b5fe  mov     r9, rbx
0x14002b601  lea     r8, [rbp+3A0h+var_3C8]
0x14002b605  mov     edx, 1
0x14002b60a  lea     rcx, [rbp+3A0h+var_340]
0x14002b60e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14002b613  lea     rcx, [rbp+3A0h+var_3C8]
0x14002b617  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b61c  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14002b623  mov     qword ptr [rbp+3A0h+var_310], rax
0x14002b62a  lea     rcx, [rbp+3A0h+var_300]
0x14002b631  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b636  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b63a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b63f  lea     rcx, [rbp+3A0h+var_340]
0x14002b643  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b648  mov     [r14], rsi
0x14002b64b  lea     rdx, aPublishpackage_2; "PublishPackage"
0x14002b652  lea     rcx, [rbp+3A0h+var_3C8]; this
0x14002b656  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x14002b65b  mov     dword ptr [rbp+3A0h+var_3B8], 80070057h
0x14002b662  lea     rcx, [rbp+3A0h+var_3C8]; this
0x14002b666  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x14002b66b  lea     rcx, [rsp+4A0h+var_440]; this
0x14002b670  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b675  cmp     [rbp+3A0h+var_3A8], 0
0x14002b679  jmp     loc_14002BDF8
0x14002b67e  xorps   xmm0, xmm0
0x14002b681  movups  [rbp+3A0h+var_3E8], xmm0
0x14002b685  xorps   xmm1, xmm1
0x14002b688  movdqu  [rbp+3A0h+var_3D8], xmm1
0x14002b68d  xor     r8d, r8d
0x14002b690  lea     rdx, qword_140088C88
0x14002b697  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b69b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b6a0  movups  xmm0, xmmword ptr [rbp+3A0h+var_360.Data1]
0x14002b6a4  movdqu  [rbp+3A0h+var_2C0], xmm0
0x14002b6ac  movups  xmm1, xmmword ptr [rbp+3A0h+var_350.Data1]
0x14002b6b0  movdqu  [rbp+3A0h+var_2B0], xmm1
0x14002b6b8  lea     rdx, [rbp+3A0h+var_3E8]
0x14002b6bc  lea     rcx, [rbp+3A0h+var_2A0]
0x14002b6c3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002b6c8  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b6cc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b6d1  xorps   xmm0, xmm0
0x14002b6d4  movups  [rbp+3A0h+var_380], xmm0
0x14002b6d8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14002b6e0  movdqu  [rbp+3A0h+var_370], xmm1
0x14002b6e5  xor     eax, eax
0x14002b6e7  mov     word ptr [rbp+3A0h+var_380], ax
0x14002b6eb  lea     rdx, [rbp+3A0h+var_380]
0x14002b6ef  lea     rcx, [rbp+3A0h+var_2C0]
0x14002b6f6  call    ?GetMachinePackageSequencerVersion@PackageRegistry@Client@AppV@@SA_KAEBUPackageIdentity@23@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Client::PackageRegistry::GetMachinePackageSequencerVersion(AppV::Client::PackageIdentity const &,std::wstring &)
0x14002b6fb  mov     rbx, rax
0x14002b6fe  mov     esi, 2
0x14002b703  lea     rdx, aAppvClientServ_42; "AppV::Client::Service::AppVClientImpl::"...
0x14002b70a  lea     rcx, [rbp+3A0h+var_340]
0x14002b70e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b713  bt      rbx, 27h ; '''
0x14002b718  jnb     short loc_14002B796
0x14002b71a  mov     [rbp+3A0h+var_320], 30Ah
0x14002b724  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14002b729  xorps   xmm0, xmm0
0x14002b72c  movups  [rbp+3A0h+var_3C8], xmm0
0x14002b730  xorps   xmm1, xmm1
0x14002b733  movdqu  [rbp+3A0h+var_3B8], xmm1
0x14002b738  lea     r8d, [rsi+17h]
0x14002b73c  lea     rdx, aGotSequencerVe; "Got sequencer version %1%"
0x14002b743  lea     rcx, [rbp+3A0h+var_3C8]
0x14002b747  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b74c  lea     r8, [rbp+3A0h+var_3C8]
0x14002b750  lea     rdx, [rbp+3A0h+var_310]
0x14002b757  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14002b75c  mov     rbx, rax
0x14002b75f  lea     rdx, [rbp+3A0h+var_380]
0x14002b763  mov     rcx, rax
0x14002b766  call    ??$perform_substitution@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogFormatter@AppV@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::LogFormatter::perform_substitution<std::wstring>(std::wstring const &)
0x14002b76b  xorps   xmm0, xmm0
0x14002b76e  movups  [rbp+3A0h+var_3E8], xmm0
0x14002b772  xorps   xmm1, xmm1
0x14002b775  movdqu  [rbp+3A0h+var_3D8], xmm1
0x14002b77a  lea     r8d, [rsi+4]
0x14002b77e  lea     rdx, aClient; "Client"
0x14002b785  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b789  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b78e  lea     edx, [rsi+2]
0x14002b791  jmp     loc_14002B816
0x14002b796  mov     [rbp+3A0h+var_320], 30Eh
0x14002b7a0  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14002b7a5  xorps   xmm0, xmm0
0x14002b7a8  movups  [rbp+3A0h+var_3C8], xmm0
0x14002b7ac  xorps   xmm1, xmm1
0x14002b7af  movdqu  [rbp+3A0h+var_3B8], xmm1
0x14002b7b4  mov     r8d, 3Bh ; ';'
0x14002b7ba  lea     rdx, aFailedToGetSeq; "Failed to get sequencer version with er"...
0x14002b7c1  lea     rcx, [rbp+3A0h+var_3C8]
0x14002b7c5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b7ca  lea     r8, [rbp+3A0h+var_3C8]
0x14002b7ce  lea     rdx, [rbp+3A0h+var_310]
0x14002b7d5  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14002b7da  mov     [rsp+4A0h+var_448], rbx
0x14002b7df  lea     rdx, [rsp+4A0h+var_448]
0x14002b7e4  mov     rcx, rax
0x14002b7e7  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14002b7ec  mov     rbx, rax
0x14002b7ef  xorps   xmm0, xmm0
0x14002b7f2  movups  [rbp+3A0h+var_3E8], xmm0
0x14002b7f6  xorps   xmm1, xmm1
0x14002b7f9  movdqu  [rbp+3A0h+var_3D8], xmm1
0x14002b7fe  mov     r8d, 6
0x14002b804  lea     rdx, aClient; "Client"
0x14002b80b  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b80f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002b814  mov     edx, esi
0x14002b816  mov     r9, rbx
0x14002b819  lea     r8, [rbp+3A0h+var_3E8]
0x14002b81d  lea     rcx, [rbp+3A0h+var_340]
0x14002b821  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14002b826  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b82a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b82f  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14002b836  mov     qword ptr [rbp+3A0h+var_310], rax
0x14002b83d  lea     rcx, [rbp+3A0h+var_300]
0x14002b844  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b849  lea     rcx, [rbp+3A0h+var_3C8]
0x14002b84d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b852  lea     rcx, [rbp+3A0h+var_340]
0x14002b856  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b85b  lea     rdx, [rbp+3A0h+var_380]
0x14002b85f  lea     rcx, [rbp+3A0h+var_3E8]
0x14002b863  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002b868  mov     [rsp+4A0h+var_448], rax
0x14002b86d  xor     eax, eax
0x14002b86f  cmp     [rbp+3A0h+arg_20], ax
0x14002b876  setnz   [rsp+4A0h+var_44F]
0x14002b87b  mov     rcx, [rdi]; pbstr
0x14002b87e  test    rcx, rcx
0x14002b881  jz      short loc_14002B889
0x14002b883  call    cs:__imp_SysStringLen
0x14002b889  mov     ebx, eax
0x14002b88b  mov     r9, r13; wchar_t *
0x14002b88e  mov     r8, r12; wchar_t *
0x14002b891  lea     rdx, aPublishpackage_2; "PublishPackage"
0x14002b898  lea     rcx, [rbp+3A0h+var_280]; this
0x14002b89f  call    ??0SmartTelemetryPackageLogger@Service@Client@AppV@@QEAA@PEB_WPEA_W1@Z; AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(wchar_t const *,wchar_t *,wchar_t *)
0x14002b8a4  lea     rax, ??_7SmartTelemetryPublishPackageLogger@Service@Client@AppV@@6B@; const AppV::Client::Service::SmartTelemetryPublishPackageLogger::`vftable'
0x14002b8ab  mov     [rbp+3A0h+var_280], rax
0x14002b8b2  xor     r13d, r13d
0x14002b8b5  test    ebx, ebx
0x14002b8b7  setnz   [rbp+3A0h+var_200]
0x14002b8be  mov     al, [rsp+4A0h+var_44F]
0x14002b8c2  mov     [rbp+3A0h+var_1FF], al
0x14002b8c8  mov     rdx, [rsp+4A0h+var_448]
0x14002b8cd  lea     rcx, [rbp+3A0h+var_1F8]
0x14002b8d4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002b8d9  mov     rcx, [rsp+4A0h+var_448]
0x14002b8de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b8e3  mov     [rsp+4A0h+var_450], r13b
0x14002b8e8  mov     [rsp+4A0h+var_44F], r13b
0x14002b8ed  lea     rcx, [rsp+4A0h+var_44F]; bool *
0x14002b8f2  call    ?RequireAdminPublishEnabled@AppVClientImpl@Service@Client@AppV@@CA_KAEA_N@Z; AppV::Client::Service::AppVClientImpl::RequireAdminPublishEnabled(bool &)
0x14002b8f7  mov     rbx, rax
0x14002b8fa  bt      rax, 27h ; '''
0x14002b8ff  jb      loc_14002B99D
0x14002b905  mov     [r14], rax
0x14002b908  bt      rax, 25h ; '%'
0x14002b90d  jnb     short loc_14002B91E
0x14002b90f  test    eax, eax
0x14002b911  jle     short loc_14002B923
0x14002b913  movzx   ebx, ax
0x14002b916  or      ebx, 80070000h
0x14002b91c  jmp     short loc_14002B923
0x14002b91e  mov     ebx, 8000FFFFh
0x14002b923  mov     [rbp+3A0h+var_270], ebx
0x14002b929  lea     rcx, [rsp+4A0h+var_450]; this
0x14002b92e  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002b933  nop
0x14002b934  lea     rcx, [rbp+3A0h+var_280]; this
0x14002b93b  call    ??1SmartTelemetryPublishPackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryPublishPackageLogger::~SmartTelemetryPublishPackageLogger(void)
0x14002b940  lea     rcx, [rbp+3A0h+var_380]
0x14002b944  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b949  lea     rcx, [rbp+3A0h+var_2A0]
0x14002b950  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b955  lea     rcx, [rsp+4A0h+var_440]; this
0x14002b95a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002b95f  cmp     [rbp+3A0h+var_3A8], r13b
0x14002b963  jz      short loc_14002B971
0x14002b965  lea     rdx, [rbp+3A0h+ActivityId]; ActivityId
0x14002b969  mov     ecx, esi; ControlCode
0x14002b96b  call    cs:__imp_EventActivityIdControl
0x14002b971  mov     eax, ebx
0x14002b973  mov     rcx, [rbp+3A0h+var_40]
0x14002b97a  xor     rcx, rsp; StackCookie
0x14002b97d  call    __security_check_cookie
0x14002b982  mov     rbx, [rsp+4A0h+arg_0]
0x14002b98a  add     rsp, 470h
0x14002b991  pop     r15
0x14002b993  pop     r14
0x14002b995  pop     r13
0x14002b997  pop     r12
0x14002b999  pop     rdi
0x14002b99a  pop     rsi
0x14002b99b  pop     rbp
0x14002b99c  retn
0x14002b99d  or      eax, 0FFFFFFFFh
0x14002b9a0  movzx   edi, [rbp+3A0h+arg_20]
0x14002b9a7  cmp     ax, di
0x14002b9aa  jz      short loc_14002B9CA
  ... truncated ...
```
