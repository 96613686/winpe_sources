# WinREAgent::Executor::ScheduleRepartition(bool,WinREAgent::TelemetrySession *)

- ea: `0x18000febc`
- end: `0x180011110`
- name: `?ScheduleRepartition@Executor@WinREAgent@@AEAAJ_NPEAVTelemetrySession@2@@Z`
- size: `4692`
- prototype: `int(WinREAgent::Executor *__hidden this, bool, struct WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ea90`

## callees

- `0x1800028e4`
- `0x180003df4`
- `0x180003f18`
- `0x180004048`
- `0x1800047cc`
- `0x1800049a4`
- `0x180004af8`
- `0x180004dd8`
- `0x1800050bc`
- `0x180005974`
- `0x180005c00`
- `0x180005cc0`
- `0x1800064a0`
- `0x180006500`
- `0x1800074b8`
- `0x180009354`
- `0x18000d540`
- `0x18000d620`
- `0x18000d6f0`
- `0x18000d8c0`
- `0x18000d92c`
- `0x18000febc`
- `0x1800119dc`
- `0x180011ef4`
- `0x180012d60`
- `0x180013e74`
- `0x180014ad8`
- `0x180023d30`
- `0x180024dc4`
- `0x1800250d8`
- `0x1800262bc`
- `0x18002dee0`
- `0x18002e06c`
- `0x18002e1f8`
- `0x180032824`
- `0x180033238`
- `0x180033394`
- `0x1800346cc`
- `0x18003717c`
- `0x180037344`
- `0x18003bbf4`
- `0x180047d1c`
- `0x18004e47c`
- `0x18005c8b8`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x1800101dd`
- `msvcrt!_wcstoui64` at `0x1800101dd`

## string_xrefs

- `0x18000ff7d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ffe2`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001002e`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180010091`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800100ee`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180010157`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800102bb`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180010838`: `Failed to allocate updateInPartitionOp`
- `0x18000ff84`: `WinREAgent::Executor::ScheduleRepartition`
- `0x18000ffe9`: `WinREAgent::Executor::ScheduleRepartition`
- `0x180010035`: `WinREAgent::Executor::ScheduleRepartition`
- `0x180010098`: `WinREAgent::Executor::ScheduleRepartition`
- `0x1800100f5`: `WinREAgent::Executor::ScheduleRepartition`
- `0x18001015e`: `WinREAgent::Executor::ScheduleRepartition`
- `0x1800102c2`: `WinREAgent::Executor::ScheduleRepartition`
- `0x1800100c9`: `InstallOnOSVolume`
- `0x1800101a4`: `WINREAGENT_NEW_PARTITION_SIZE`
- `0x1800102f0`: `Failed to create OneSettings infrastructure`
- `0x1800103b0`: `WinRECleanupCanDeleteList`
- `0x180010ffe`: `CreateNew`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WinREAgent::Executor::ScheduleRepartition(
        WinREAgent::Executor *this,
        unsigned __int8 a2,
        struct WinREAgent::TelemetrySession *a3)
{
  int v4; // esi
  __int64 v6; // rax
  int Info; // ebx
  PushButtonReset::Partition *v8; // rax
  struct PushButtonReset::PartitionInfo *v9; // rdx
  int v10; // ebx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rdi
  int EnvironmentVariableW; // eax
  unsigned int v18; // r12d
  wchar_t *v19; // rbx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rsi
  struct ISetupOneSettings **v22; // rax
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rcx
  int SetupOneSettings; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, const wchar_t *, __int64, int *); // rdi
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  int *v35; // rsi
  __int64 v36; // rdi
  char IsEnabled; // al
  int v38; // edi
  const unsigned __int16 *v39; // r9
  __int64 v40; // rax
  unsigned __int64 v41; // rcx
  __int64 v42; // rax
  WinREAgent::Executor *v43; // rsi
  __int64 v44; // rax
  __int64 v45; // rax
  const wchar_t *v46; // r8
  unsigned int v47; // edi
  unsigned __int64 v48; // rdi
  unsigned __int64 *v49; // r8
  int v50; // esi
  unsigned __int64 v51; // rsi
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rdi
  unsigned __int64 v54; // rsi
  __int64 v55; // rax
  WinREAgent::Repartition *v56; // rax
  unsigned int v57; // r12d
  unsigned int v58; // r12d
  const unsigned __int16 *v59; // r9
  bool v61; // [rsp+40h] [rbp-C0h] BYREF
  char v62[7]; // [rsp+41h] [rbp-BFh] BYREF
  _QWORD v63[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v64; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v65; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+68h] [rbp-98h]
  __int64 v67; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v68[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v69; // [rsp+88h] [rbp-78h] BYREF
  void **v70; // [rsp+90h] [rbp-70h] BYREF
  void *v71; // [rsp+98h] [rbp-68h]
  __int64 v72; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v73; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-50h]
  int v75; // [rsp+B8h] [rbp-48h] BYREF
  int v76; // [rsp+BCh] [rbp-44h] BYREF
  _QWORD v77[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v78[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v79; // [rsp+E8h] [rbp-18h]
  WinREAgent::Executor *v80; // [rsp+F0h] [rbp-10h]
  wchar_t *String; // [rsp+F8h] [rbp-8h] BYREF
  char v82[8]; // [rsp+100h] [rbp+0h] BYREF
  __int64 (__fastcall *v83)(); // [rsp+108h] [rbp+8h]
  struct WinREAgent::TelemetrySession *v84; // [rsp+110h] [rbp+10h]
  __int64 *v85; // [rsp+118h] [rbp+18h]
  _DWORD v86[32]; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v87[12]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v88; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v89; // [rsp+1F0h] [rbp+F0h]

  v4 = a2;
  v80 = this;
  PushButtonReset::Logging::Trace(0, L"Schedule repartition");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v67,
    (__int64)L"FailedToSchedule");
  v82[0] = 0;
  v83 = TraceCanRepartitionReason;
  v84 = a3;
  v85 = &v67;
  v77[1] = 0;
  v77[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  v6 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v77);
  Info = PushButtonReset::Partition::FindByFilePath(*((_QWORD *)this + 51) + 120LL, v6);
  if ( Info >= 0 )
  {
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v87);
    v8 = (PushButtonReset::Partition *)(*(__int64 (__fastcall **)(_QWORD *))(v77[0] + 24LL))(v77);
    Info = PushButtonReset::Partition::GetInfo(v8, (struct PushButtonReset::PartitionInfo *)v87);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        879,
        L"Failed to get info for WinRE partition");
LABEL_108:
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v87);
      goto LABEL_109;
    }
    PushButtonReset::PartitionInfo::PartitionInfo((PushButtonReset::PartitionInfo *)v86);
    Info = WinREAgent::WinREGetOSPartitionInfo((WinREAgent *)v86, v9);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        884,
        L"Failed to get info for OS partition");
LABEL_107:
      PushButtonReset::PartitionInfo::~PartitionInfo((PushButtonReset::PartitionInfo *)v86);
      goto LABEL_108;
    }
    v10 = v86[0];
    if ( v86[0] != v87[0] )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"NotOnOSDisk", 11);
      PushButtonReset::Logging::TraceErr(
        2,
        2147500037LL,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        892,
        L"OS and WinRE are not on same disk. OS disk: [%u], WinRE disk: [%u]",
        v10,
        v87[0]);
LABEL_9:
      Info = -2147467259;
      goto LABEL_107;
    }
    if ( v86[1] == v87[1] )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"InstallOnOSVolume", 17);
      PushButtonReset::Logging::TraceErr(
        2,
        2147500037LL,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        902,
        L"OS and WinRE are on same partition");
      goto LABEL_9;
    }
    v65 = 0;
    Info = PushButtonReset::File::GetSize(*((_QWORD *)this + 51) + 280LL, &v65);
    if ( Info < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Info,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        908,
        L"Failed to get size of [%s]",
        *(_QWORD *)(*((_QWORD *)this + 51) + 280LL));
      goto LABEL_107;
    }
    v14 = v65;
    v15 = winreEstimateBufferNeededOnPartition(v11, v65, v12, v13, v4);
    v16 = v15 + v14;
    if ( v15 + v14 < 0x1C200000 )
      v16 = 471859200;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String);
    EnvironmentVariableW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                             &String,
                             L"WINREAGENT_NEW_PARTITION_SIZE");
    v18 = 1;
    v19 = String;
    if ( EnvironmentVariableW )
    {
      PushButtonReset::Logging::Trace(0, L"Get new partition size from environment [%s]", String);
      v20 = _wcstoui64(v19, 0, 10);
      if ( v20 <= v16 )
        PushButtonReset::Logging::Trace(
          1,
          L"New partition size from environment is smaller than required size, ignore it");
      else
        v16 = v20;
    }
    v21 = (v16 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
    v73 = v21;
    PushButtonReset::Logging::Trace(0, L"Size for new WinRE file: [%llu]", v14);
    PushButtonReset::Logging::Trace(0, L"Required buufer for new WinRE partition: [%llu]", v15);
    PushButtonReset::Logging::Trace(0, L"Size for a new WinRE partition: [%llu]", v21);
    PushButtonReset::Logging::Trace(0, L"Size of current WinRE partition: [%llu]", v88);
    if ( a3 )
    {
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"NewPartitionFreeSpaceReq", v15);
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"NewPartitionRequiredSize", v21);
    }
    v63[1] = 0;
    v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
    memset(v78, 0, sizeof(v78));
    v79 = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl) )
    {
      v22 = (struct ISetupOneSettings **)(*(__int64 (__fastcall **)(_QWORD *))(v63[0] + 8LL))(v63);
      SetupOneSettings = CreateSetupOneSettings(v24, v23, v22);
      if ( SetupOneSettings < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)SetupOneSettings,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          967,
          L"Failed to create OneSettings infrastructure");
        (*(void (__fastcall **)(_QWORD *, _QWORD))(v63[0] + 48LL))(v63, 0);
      }
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::SetCount(
        v78,
        0);
      v65 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, unsigned __int64 *))(v63[0] + 64LL))(v63, &v65) )
      {
        v75 = 0x10000;
        v71 = operator new[](0x20000u);
        v70 = &RAII::CAutoDeleteArray<unsigned short>::`vftable';
        v26 = (*(__int64 (__fastcall **)(_QWORD *))(v63[0] + 24LL))(v63);
        v27 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, int *))(*(_QWORD *)v26 + 16LL);
        v28 = ((__int64 (__fastcall *)(void ***))v70[4])(&v70);
        v29 = v27(v26, L"WinRECleanupCanDeleteList", v28, &v75);
        if ( v29 >= 0 )
        {
          v76 = 0;
          v30 = ((__int64 (__fastcall *)(void ***))v70[4])(&v70);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v65,
            v30);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
            &v65,
            &v69,
            v31,
            &v76);
          while ( *(int *)(v69 - 16) > 0 )
          {
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
              v78,
              v69);
            v33 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                               &v65,
                               &v72,
                               v32,
                               &v76);
            v34 = (_QWORD *)(v33 - 24);
            v35 = (int *)(v69 - 24);
            if ( v33 - 24 != v69 - 24 )
            {
              if ( v35[4] >= 0 && *v34 == *(_QWORD *)v35 )
              {
                v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v34);
                ATL::CStringData::Release((ATL::CStringData *)v35);
                v69 = v36 + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v69, v33, *(unsigned int *)(v33 - 16));
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(v72 - 24));
          }
          ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v29,
            "WinREAgent::Executor::ScheduleRepartition",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            982,
            L"Faled to get block list of WinRE partition cleanup");
        }
        v70 = &RAII::CAutoDeleteArray<unsigned short>::`vftable';
        RAII::CAutoDeleteArray<unsigned short const *>::Release(&v70);
        v21 = v73;
      }
    }
    v61 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v64);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl);
    v38 = WinREAgent::WinREIsWinRECleanupAllowed(
            (_QWORD *)(*((_QWORD *)v80 + 51) + 120LL),
            (unsigned __int64)v78 & -(__int64)(IsEnabled != 0),
            &v61,
            &v64);
    if ( v38 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v38,
        "WinREAgent::Executor::ScheduleRepartition",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1010,
        L"Failed to check whether cleanup WinRE partition is allowed");
      ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
      v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
      RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
LABEL_106:
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
      Info = v38;
      goto LABEL_107;
    }
    if ( a3 )
    {
      v39 = L"True";
      if ( !v61 )
        v39 = L"False";
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"IsCleanupAllowed", v39);
      if ( *((_DWORD *)v64 - 4) )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"UnknownContentOnWinREPartition", v64);
    }
    v68[1] = 0;
    v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    if ( v21 > v88 )
    {
      PushButtonReset::Logging::Trace(0, L"Need a larger WinRE partition");
      v62[0] = 0;
      v38 = WinREAgent::WinRECanExtendWinREPartition(*((_QWORD *)v80 + 51) + 120LL, v62);
      if ( v38 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v38,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1073,
          L"Failed to check whether WinRE can be extended");
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        goto LABEL_106;
      }
      v46 = L"Yes";
      v47 = (unsigned __int8)v62[0];
      if ( !v62[0] )
        v46 = L"No";
      PushButtonReset::Logging::Trace(0, L"Can extend WinRE partition: [%s]", v46);
      if ( a3 )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"CanExtend", v47);
      if ( (_BYTE)v47 )
      {
        if ( !v61 )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"NotAllowCleanupWinREPartition", 29);
          PushButtonReset::Logging::TraceErr(
            2,
            2147942450LL,
            "WinREAgent::Executor::ScheduleRepartition",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1103,
            L"Cleanup WinRE partition is not allowed by policy");
          v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
          ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
          v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
          RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
          goto LABEL_48;
        }
        v18 = 2;
        v48 = v21 - v88;
      }
      else
      {
        if ( !v61 )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"NotAllowCleanupWinREPartition", 29);
          PushButtonReset::Logging::TraceErr(
            2,
            2147942450LL,
            "WinREAgent::Executor::ScheduleRepartition",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1092,
            L"Cleanup WinRE partition is not allowed by policy");
          v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
          ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
          v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
          RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
          goto LABEL_48;
        }
        v18 = 3;
        v48 = v21;
      }
      PushButtonReset::Logging::Trace(0, L"Size to extend WinRE: [%llu]", v48);
      v65 = 0;
      v69 = 0;
      v50 = WinREAgent::WinREOSResizeBound((WinREAgent *)&v69, &v65, v49);
      v75 = v50;
      if ( v50 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v50,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1114,
          L"Failed to get resize bound of OS partition");
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        Info = v50;
        goto LABEL_107;
      }
      v51 = v65;
      if ( v65 < 0x100000 )
        v51 = 0;
      PushButtonReset::Logging::Trace(0, L"Reclaimable space for OS: [%llu]", v69);
      PushButtonReset::Logging::Trace(0, L"Extendable space after OS: [%llu]", v51);
      if ( v48 <= v51 )
        v52 = 0;
      else
        v52 = v48 - v51;
      v65 = ((v52 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL) + 0x100000;
      if ( v51 <= v48 )
        v53 = 0;
      else
        v53 = v51 - v48;
      PushButtonReset::Logging::Trace(
        0,
        L"Size to shrink from OS: [%llu]",
        ((v52 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL) + 0x100000);
      if ( a3 )
      {
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"OSReclaimableSpace", v69);
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"OSExtendableSpace", v51);
        v54 = v65;
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"OSShrinkSize", v65);
        if ( v53 )
          WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"OSExtraExtendableSpace", v53);
      }
      else
      {
        v54 = v65;
      }
      if ( v69 < v54 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"NoSpaceForShrink", 16);
        PushButtonReset::Logging::TraceErr(
          2,
          2147942512LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1161,
          L"Not enough space to shrink from OS");
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        Info = -2147024784;
        goto LABEL_107;
      }
      if ( v53 > 0x6400000 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"UnallocatedSpaceIsTooBig", 24);
        PushButtonReset::Logging::TraceErr(
          2,
          2147500037LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1168,
          L"Additional extendable space exceeds threshold");
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        goto LABEL_9;
      }
      v71 = (void *)PbrNew<WinREAgent::Repartition,>();
      v70 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v70) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1175,
          L"Failed to allocate opRepartition");
        v70 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v70);
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        goto LABEL_51;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl) )
      {
        v55 = ((__int64 (__fastcall *)(void ***))v70[3])(&v70);
        WinREAgent::Repartition::SetCanDeleteList(v55, v78);
      }
      v56 = (WinREAgent::Repartition *)((__int64 (__fastcall *)(void ***))v70[3])(&v70);
      WinREAgent::Repartition::Commit(v56, v73, v54, v18);
      v72 = ((__int64 (__fastcall *)(void ***))v70[4])(&v70);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)v80 + 8,
        &v72);
      v71 = 0;
      v70 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v70);
      v38 = v75;
    }
    else
    {
      PushButtonReset::Logging::Trace(0, L"Try to cleanup current WinRE partition");
      if ( !v61 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"NotAllowCleanupWinREPartition", 29);
        PushButtonReset::Logging::TraceErr(
          2,
          2147942450LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1035,
          L"Cleanup WinRE partition is not allowed by policy");
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
LABEL_48:
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        Info = -2147024846;
        goto LABEL_107;
      }
      v74 = PbrNew<WinREAgent::CleanupWinRE,>();
      v73 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v73) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1043,
          L"Failed to allocate opCleanupWinRE");
        v73 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v73);
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
LABEL_51:
        ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
        Info = -2147024882;
        goto LABEL_107;
      }
      v40 = (*(__int64 (__fastcall **)(unsigned __int64 *))(v73 + 24))(&v73);
      if ( v88 <= v89 )
        v41 = 0;
      else
        v41 = v88 - v89;
      *(_QWORD *)(v40 + 144) = v41;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl'::`2'::impl) )
      {
        v42 = (*(__int64 (__fastcall **)(unsigned __int64 *))(v73 + 24))(&v73);
        WinREAgent::CleanupWinRE::SetCanDeleteList(v42, v78);
      }
      v43 = v80;
      v72 = (*(__int64 (__fastcall **)(unsigned __int64 *))(v73 + 32))(&v73);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)v43 + 8,
        &v72);
      v74 = 0;
      v66 = 0;
      v65 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      v44 = PbrNew<WinREAgent::UpdateInPartition,>();
      ((void (__fastcall *)(unsigned __int64 *, __int64))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(
        &v65,
        v44);
      if ( (*(unsigned __int8 (__fastcall **)(unsigned __int64 *))(v65 + 72))(&v65) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::ScheduleRepartition",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1058,
          L"Failed to allocate updateInPartitionOp");
        v65 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v65);
        v73 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v73);
        v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
        v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
        RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
        goto LABEL_51;
      }
      v45 = (*(__int64 (__fastcall **)(unsigned __int64 *))(v65 + 24))(&v65);
      WinREAgent::UpdateInPartition::Commit(v45, *((_QWORD *)v43 + 51) + 120LL, *((_QWORD *)v43 + 51) + 280LL);
      v72 = (*(__int64 (__fastcall **)(unsigned __int64 *))(v65 + 32))(&v65);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)v43 + 8,
        &v72);
      v66 = 0;
      v65 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v65);
      v73 = (unsigned __int64)&RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v73);
    }
    if ( a3 )
    {
      v57 = v18 - 1;
      if ( v57 )
      {
        v58 = v57 - 1;
        if ( v58 )
        {
          if ( v58 == 1 )
            v59 = L"CreateNew";
          else
            v59 = L"Invalid";
        }
        else
        {
          v59 = L"Extend";
        }
      }
      else
      {
        v59 = L"Cleanup";
      }
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"RepartitionMethod", v59);
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, L"Success", 7);
    v68[0] = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(v68);
    ATL::CStringData::Release((ATL::CStringData *)(v64 - 12));
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)v78);
    v63[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
    RAII::CAutoRelease<ISetupOneSettings *>::Release(v63);
    goto LABEL_106;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Info,
    "WinREAgent::Executor::ScheduleRepartition",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    875,
    L"Failed to get partition for WinRE");
LABEL_109:
  v77[0] = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v77);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl2<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)v82);
  ATL::CStringData::Release((ATL::CStringData *)(v67 - 24));
  return (unsigned int)Info;
}

```

## disassembly

```asm
0x18000febc  mov     [rsp-8+arg_18], rbx
0x18000fec1  push    rbp
0x18000fec2  push    rsi
0x18000fec3  push    rdi
0x18000fec4  push    r12
0x18000fec6  push    r13
0x18000fec8  push    r14
0x18000feca  push    r15
0x18000fecc  lea     rbp, [rsp-130h]
0x18000fed4  sub     rsp, 230h
0x18000fedb  mov     rax, cs:__security_cookie
0x18000fee2  xor     rax, rsp
0x18000fee5  mov     [rbp+160h+var_40], rax
0x18000feec  mov     r13, r8
0x18000feef  movzx   esi, dl
0x18000fef2  mov     rdi, rcx
0x18000fef5  mov     [rbp+160h+var_170], rcx
0x18000fef9  lea     rdx, aScheduleRepart; "Schedule repartition"
0x18000ff00  xor     ecx, ecx
0x18000ff02  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000ff07  lea     rdx, aFailedtoschedu; "FailedToSchedule"
0x18000ff0e  lea     rcx, [rsp+260h+var_1F0]
0x18000ff13  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000ff18  nop
0x18000ff19  xor     r14d, r14d
0x18000ff1c  mov     [rbp+160h+var_160], r14b
0x18000ff20  lea     rax, TraceCanRepartitionReason
0x18000ff27  mov     [rbp+160h+var_158], rax
0x18000ff2b  mov     [rbp+160h+var_150], r13
0x18000ff2f  lea     rax, [rsp+260h+var_1F0]
0x18000ff34  mov     [rbp+160h+var_148], rax
0x18000ff38  mov     [rbp+160h+var_198], r14
0x18000ff3c  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x18000ff43  mov     [rbp+160h+var_1A0], rax
0x18000ff47  lea     rcx, [rbp+160h+var_1A0]
0x18000ff4b  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000ff50  mov     rcx, [rdi+198h]
0x18000ff57  add     rcx, 78h ; 'x'
0x18000ff5b  mov     rdx, rax
0x18000ff5e  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x18000ff63  mov     ebx, eax
0x18000ff65  test    eax, eax
0x18000ff67  jns     short loc_18000FF9B
0x18000ff69  lea     rax, aFailedToGetPar_0; "Failed to get partition for WinRE"
0x18000ff70  mov     [rsp+260h+var_238], rax
0x18000ff75  mov     [rsp+260h+var_240], 36Bh
0x18000ff7d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ff84  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x18000ff8b  mov     edx, ebx
0x18000ff8d  lea     ecx, [r14+2]
0x18000ff91  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ff96  jmp     loc_1800110B7
0x18000ff9b  lea     rcx, [rbp+160h+var_C0]; this
0x18000ffa2  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18000ffa7  nop
0x18000ffa8  mov     rax, [rbp+160h+var_1A0]
0x18000ffac  lea     rcx, [rbp+160h+var_1A0]
0x18000ffb0  mov     rax, [rax+18h]
0x18000ffb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb9  lea     rdx, [rbp+160h+var_C0]; struct PushButtonReset::PartitionInfo *
0x18000ffc0  mov     rcx, rax; this
0x18000ffc3  call    ?GetInfo@Partition@PushButtonReset@@QEAAJPEAUPartitionInfo@2@@Z; PushButtonReset::Partition::GetInfo(PushButtonReset::PartitionInfo *)
0x18000ffc8  mov     ebx, eax
0x18000ffca  test    eax, eax
0x18000ffcc  jns     short loc_180010001
0x18000ffce  lea     rax, aFailedToGetInf_0; "Failed to get info for WinRE partition"
0x18000ffd5  mov     [rsp+260h+var_238], rax
0x18000ffda  mov     [rsp+260h+var_240], 36Fh
0x18000ffe2  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ffe9  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x18000fff0  mov     edx, ebx
0x18000fff2  mov     ecx, 2
0x18000fff7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000fffc  jmp     loc_1800110AA
0x180010001  lea     rcx, [rbp+160h+var_140]; this
0x180010005  call    ??0PartitionInfo@PushButtonReset@@QEAA@XZ; PushButtonReset::PartitionInfo::PartitionInfo(void)
0x18001000a  nop
0x18001000b  lea     rcx, [rbp+160h+var_140]; this
0x18001000f  call    ?WinREGetOSPartitionInfo@WinREAgent@@YAJPEAUPartitionInfo@PushButtonReset@@@Z; WinREAgent::WinREGetOSPartitionInfo(PushButtonReset::PartitionInfo *)
0x180010014  mov     ebx, eax
0x180010016  test    eax, eax
0x180010018  jns     short loc_18001004D
0x18001001a  lea     rax, aFailedToGetInf_3; "Failed to get info for OS partition"
0x180010021  mov     [rsp+260h+var_238], rax
0x180010026  mov     [rsp+260h+var_240], 374h
0x18001002e  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180010035  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x18001003c  mov     edx, ebx
0x18001003e  mov     ecx, 2
0x180010043  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180010048  jmp     loc_1800110A0
0x18001004d  mov     ebx, [rbp+160h+var_140]
0x180010050  cmp     ebx, [rbp+160h+var_C0]
0x180010056  jz      short loc_1800100B8
0x180010058  mov     r8d, 0Bh
0x18001005e  lea     rdx, aNotonosdisk; "NotOnOSDisk"
0x180010065  lea     rcx, [rsp+260h+var_1F0]
0x18001006a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001006f  mov     eax, [rbp+160h+var_C0]
0x180010075  mov     [rsp+260h+var_228], eax
0x180010079  mov     dword ptr [rsp+260h+var_230], ebx
0x18001007d  lea     rax, aOsAndWinreAreN; "OS and WinRE are not on same disk. OS d"...
0x180010084  mov     [rsp+260h+var_238], rax
0x180010089  mov     [rsp+260h+var_240], 37Ch
0x180010091  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180010098  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x18001009f  mov     edx, 80004005h
0x1800100a4  mov     ecx, 2
0x1800100a9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800100ae  mov     ebx, 80004005h
0x1800100b3  jmp     loc_1800110A0
0x1800100b8  mov     eax, [rbp+160h+var_BC]
0x1800100be  cmp     [rbp+160h+var_13C], eax
0x1800100c1  jnz     short loc_18001010D
0x1800100c3  mov     r8d, 11h
0x1800100c9  lea     rdx, aInstallonosvol; "InstallOnOSVolume"
0x1800100d0  lea     rcx, [rsp+260h+var_1F0]
0x1800100d5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800100da  lea     rax, aOsAndWinreAreO; "OS and WinRE are on same partition"
0x1800100e1  mov     [rsp+260h+var_238], rax
0x1800100e6  mov     [rsp+260h+var_240], 386h
0x1800100ee  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800100f5  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x1800100fc  mov     edx, 80004005h
0x180010101  mov     ecx, 2
0x180010106  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001010b  jmp     short loc_1800100AE
0x18001010d  mov     [rsp+260h+var_200], r14
0x180010112  mov     rcx, [rdi+198h]
0x180010119  add     rcx, 118h
0x180010120  lea     rdx, [rsp+260h+var_200]
0x180010125  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18001012a  mov     ebx, eax
0x18001012c  test    eax, eax
0x18001012e  jns     short loc_180010176
0x180010130  mov     rcx, [rdi+198h]
0x180010137  mov     rdx, [rcx+118h]
0x18001013e  mov     [rsp+260h+var_230], rdx
0x180010143  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x18001014a  mov     [rsp+260h+var_238], rax
0x18001014f  mov     [rsp+260h+var_240], 38Ch
0x180010157  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001015e  lea     r8, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x180010165  mov     edx, ebx
0x180010167  mov     ecx, 2
0x18001016c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180010171  jmp     loc_1800110A0
0x180010176  mov     [rsp+260h+var_240], esi
0x18001017a  mov     r15, [rsp+260h+var_200]
0x18001017f  mov     rdx, r15
0x180010182  call    winreEstimateBufferNeededOnPartition
0x180010187  mov     r14, rax
0x18001018a  lea     rdi, [rax+r15]
0x18001018e  mov     eax, 1C200000h
0x180010193  cmp     rdi, rax
0x180010196  cmovb   rdi, rax
0x18001019a  lea     rcx, [rbp+160h+String]
0x18001019e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800101a3  nop
0x1800101a4  lea     rdx, aWinreagentNewP; "WINREAGENT_NEW_PARTITION_SIZE"
0x1800101ab  lea     rcx, [rbp+160h+String]
0x1800101af  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800101b4  mov     r12d, 1
0x1800101ba  mov     rbx, [rbp+160h+String]
0x1800101be  test    eax, eax
0x1800101c0  jz      short loc_1800101FC
0x1800101c2  mov     r8, rbx
0x1800101c5  lea     rdx, aGetNewPartitio; "Get new partition size from environment"...
0x1800101cc  xor     ecx, ecx
0x1800101ce  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800101d3  xor     edx, edx; EndPtr
0x1800101d5  lea     r8d, [r12+9]; Radix
0x1800101da  mov     rcx, rbx; String
0x1800101dd  call    cs:__imp__wcstoui64
0x1800101e3  cmp     rax, rdi
0x1800101e6  jbe     short loc_1800101ED
0x1800101e8  mov     rdi, rax
0x1800101eb  jmp     short loc_1800101FC
0x1800101ed  lea     rdx, aNewPartitionSi; "New partition size from environment is "...
0x1800101f4  mov     ecx, r12d
0x1800101f7  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800101fc  lea     rsi, [rdi+0FFFFFh]
0x180010203  and     rsi, 0FFFFFFFFFFF00000h
0x18001020a  mov     [rbp+160h+var_1B8], rsi
0x18001020e  mov     r8, r15
0x180010211  lea     rdx, aSizeForNewWinr; "Size for new WinRE file: [%llu]"
0x180010218  xor     ecx, ecx
0x18001021a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001021f  mov     r8, r14
0x180010222  lea     rdx, aRequiredBuufer; "Required buufer for new WinRE partition"...
0x180010229  xor     ecx, ecx
0x18001022b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180010230  mov     r8, rsi
0x180010233  lea     rdx, aSizeForANewWin; "Size for a new WinRE partition: [%llu]"
0x18001023a  xor     ecx, ecx
0x18001023c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180010241  mov     r8, [rbp+160h+var_90]
0x180010248  lea     rdx, aSizeOfCurrentW; "Size of current WinRE partition: [%llu]"
0x18001024f  xor     ecx, ecx
0x180010251  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180010256  xor     edi, edi
0x180010258  test    r13, r13
0x18001025b  jz      short loc_18001028F
0x18001025d  mov     r9, r14; unsigned __int64
0x180010260  lea     r8, aNewpartitionfr; "NewPartitionFreeSpaceReq"
0x180010267  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18001026e  mov     rcx, r13; this
0x180010271  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x180010276  mov     r9, rsi; unsigned __int64
0x180010279  lea     r8, aNewpartitionre; "NewPartitionRequiredSize"
0x180010280  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180010287  mov     rcx, r13; this
0x18001028a  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0_K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,unsigned __int64)
0x18001028f  mov     [rsp+260h+var_210], rdi
0x180010294  lea     rax, ??_7?$CAutoRelease@PEAUISetupOneSettings@@@RAII@@6B@; const RAII::CAutoRelease<ISetupOneSettings *>::`vftable'
0x18001029b  mov     [rsp+260h+var_218], rax
0x1800102a0  mov     [rbp+160h+var_190], rdi
0x1800102a4  mov     [rbp+160h+var_188], rdi
0x1800102a8  mov     [rbp+160h+var_180], rdi
0x1800102ac  mov     [rbp+160h+var_178], edi
0x1800102af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::GetImpl(void)'::`2'::impl
0x1800102b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_SaveCanDeleteList>::__private_IsEnabled(void)
0x1800102bb  lea     r14, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800102c2  lea     r15, aWinreagentExec_19; "WinREAgent::Executor::ScheduleRepartiti"...
0x1800102c9  test    al, al
0x1800102cb  jz      loc_1800104D9
0x1800102d1  mov     rax, [rsp+260h+var_218]
0x1800102d6  lea     rcx, [rsp+260h+var_218]
0x1800102db  mov     rax, [rax+8]
0x1800102df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e4  mov     r8, rax; struct ISetupOneSettings **
0x1800102e7  call    ?CreateSetupOneSettings@@YAJPEBG0PEAPEAUISetupOneSettings@@@Z; CreateSetupOneSettings(ushort const *,ushort const *,ISetupOneSettings * *)
0x1800102ec  test    eax, eax
0x1800102ee  jns     short loc_18001032A
0x1800102f0  lea     rcx, aFailedToCreate_34; "Failed to create OneSettings infrastruc"...
0x1800102f7  mov     [rsp+260h+var_238], rcx
0x1800102fc  mov     [rsp+260h+var_240], 3C7h
0x180010304  mov     r9, r14
0x180010307  mov     r8, r15
0x18001030a  mov     edx, eax
0x18001030c  mov     ecx, r12d
0x18001030f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180010314  mov     rax, [rsp+260h+var_218]
0x180010319  xor     edx, edx
0x18001031b  lea     rcx, [rsp+260h+var_218]
0x180010320  mov     rax, [rax+30h]
0x180010324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010329  nop
0x18001032a  xor     edx, edx
0x18001032c  lea     rcx, [rbp+160h+var_190]
0x180010330  call    ?SetCount@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::SetCount(unsigned __int64,int)
0x180010335  nop
0x180010336  mov     [rsp+260h+var_200], rdi
0x18001033b  mov     rax, [rsp+260h+var_218]
0x180010340  lea     rdx, [rsp+260h+var_200]
0x180010345  lea     rcx, [rsp+260h+var_218]
0x18001034a  mov     rax, [rax+40h]
0x18001034e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010353  test    al, al
0x180010355  jz      loc_1800104D9
0x18001035b  mov     [rbp+160h+var_1A8], 10000h
0x180010362  mov     ecx, 20000h; unsigned __int64
0x180010367  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001036c  mov     [rbp+160h+var_1C8], rax
0x180010370  lea     rax, ??_7?$CAutoDeleteArray@G@RAII@@6B@; const RAII::CAutoDeleteArray<ushort>::`vftable'
0x180010377  mov     [rbp+160h+var_1D0], rax
0x18001037b  mov     rax, [rsp+260h+var_218]
0x180010380  lea     rcx, [rsp+260h+var_218]
0x180010385  mov     rax, [rax+18h]
0x180010389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001038e  mov     rsi, rax
0x180010391  mov     rcx, [rax]
0x180010394  mov     rdi, [rcx+10h]
0x180010398  mov     rcx, [rbp+160h+var_1D0]
0x18001039c  mov     rax, [rcx+20h]
0x1800103a0  lea     rcx, [rbp+160h+var_1D0]
0x1800103a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103a9  lea     r9, [rbp+160h+var_1A8]
0x1800103ad  mov     r8, rax
0x1800103b0  lea     rdx, aWinrecleanupca; "WinRECleanupCanDeleteList"
0x1800103b7  mov     rcx, rsi
0x1800103ba  mov     rax, rdi
0x1800103bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103c2  xor     edi, edi
0x1800103c4  test    eax, eax
0x1800103c6  jns     short loc_1800103F1
0x1800103c8  lea     rcx, aFaledToGetBloc; "Faled to get block list of WinRE partit"...
0x1800103cf  mov     [rsp+260h+var_238], rcx
0x1800103d4  mov     [rsp+260h+var_240], 3D6h
0x1800103dc  mov     r9, r14
0x1800103df  mov     r8, r15
0x1800103e2  mov     edx, eax
0x1800103e4  mov     ecx, r12d
0x1800103e7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800103ec  jmp     loc_1800104C1
0x1800103f1  mov     [rbp+160h+var_1A4], edi
0x1800103f4  mov     rax, [rbp+160h+var_1D0]
0x1800103f8  lea     rcx, [rbp+160h+var_1D0]
0x1800103fc  mov     rax, [rax+20h]
0x180010400  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
