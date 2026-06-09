# WindowsPerformanceRecorder::CControlManager::Stop(ushort *,IProfileCollection *,ITraceMergeProperties *)

- ea: `0x18005deb0`
- end: `0x18005eb8d`
- name: `?Stop@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAGPEAUIProfileCollection@@PEAUITraceMergeProperties@@@Z`
- size: `3293`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *this, unsigned __int16 *, struct IProfileCollection *, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)`
- caller_count: `0`
- callee_count: `56`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008330`
- `0x18001a61c`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c458`
- `0x18001c5dc`
- `0x18001c820`
- `0x18001d190`
- `0x18001d1bc`
- `0x18001d3d8`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x1800234f0`
- `0x180024270`
- `0x1800248d8`
- `0x1800328a8`
- `0x1800328f8`
- `0x1800329bc`
- `0x180035004`
- `0x1800359f4`
- `0x180035eec`
- `0x180036d08`
- `0x180036d94`
- `0x180037f3c`
- `0x180039084`
- `0x180039be8`
- `0x18003c270`
- `0x18003c6a4`
- `0x180040a04`
- `0x1800449a0`
- `0x180044e90`
- `0x180045cb4`
- `0x18004865c`
- `0x1800490f8`
- `0x1800493a0`
- `0x18004a664`
- `0x18004b024`
- `0x18004b128`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004ed10`
- `0x180057b84`
- `0x180059820`
- `0x180059970`
- `0x1800599c0`
- `0x180059e74`
- `0x180059fa8`
- `0x18005b310`
- `0x18005d068`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e544`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005e544`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005e9a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005ea3f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005e9a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005ea3f`

## string_xrefs

- `0x18005dfc0`: `COMGUARD`
- `0x18005e304`: `COMGUARD`
- `0x18005e393`: `COMGUARD`
- `0x18005e9e6`: `Fail to delete %ws`
- `0x18005ea0e`: `Fail to delete %ws`
- `0x18005ea29`: `Fail to delete %ws`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::Stop(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 *a2,
        struct IProfileCollection *a3,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **a4)
{
  WindowsPerformanceRecorder::CControlManager *v8; // r12
  int v9; // ebx
  int IsOtherObjectInstanceNameCompatible; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // rdi
  signed int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  int RunningProfileTraceType; // r15d
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  char *v22; // r13
  int v23; // eax
  const unsigned __int16 *v24; // r9
  bool v25; // r8
  char v26; // si
  bool v27; // r9
  void **v28; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v29; // rax
  const unsigned __int16 *FileName; // rax
  const unsigned __int16 *SessionName; // rax
  signed int v32; // eax
  int v33; // esi
  signed int v34; // eax
  WindowsPerformanceRecorder::CControlManager *v35; // rcx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v37; // rsi
  unsigned int v38; // edx
  __int64 v39; // rcx
  WindowsPerformanceRecorder::CControlManager *v40; // rcx
  const unsigned __int16 *v41; // r9
  const struct _GUID *v42; // r8
  const char *v43; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v44; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rax
  const unsigned __int16 *v48; // r9
  int v49; // eax
  int v50; // eax
  int v51; // esi
  unsigned __int16 *v52; // rdx
  char *v53; // r13
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **j; // r13
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v55; // rsi
  int v56; // eax
  WindowsPerformanceRecorder::Impl *v57; // rax
  const unsigned __int16 *v58; // rdx
  const WCHAR *v59; // rax
  int Error; // eax
  const char *v61; // rsi
  unsigned int v62; // eax
  int v63; // eax
  unsigned int v64; // eax
  char *v65; // rdi
  int Format; // [rsp+20h] [rbp-128h]
  struct IControlErrorInfo *v67; // [rsp+28h] [rbp-120h]
  int v68; // [rsp+40h] [rbp-108h]
  char v69; // [rsp+44h] [rbp-104h]
  unsigned int v70; // [rsp+48h] [rbp-100h]
  unsigned __int16 *v71; // [rsp+50h] [rbp-F8h] BYREF
  unsigned int v72; // [rsp+58h] [rbp-F0h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-E8h] BYREF
  void *Block; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v75; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v76; // [rsp+78h] [rbp-D0h]
  char *v77; // [rsp+80h] [rbp-C8h]
  __int64 (__fastcall **v78)(void *); // [rsp+88h] [rbp-C0h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v79; // [rsp+90h] [rbp-B8h] BYREF
  WindowsPerformanceRecorder::CControlManager *v80; // [rsp+98h] [rbp-B0h]
  __int64 v81; // [rsp+A0h] [rbp-A8h] BYREF
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v82; // [rsp+A8h] [rbp-A0h] BYREF
  char v83; // [rsp+B0h] [rbp-98h]
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v84; // [rsp+B8h] [rbp-90h]
  struct IProfileCollection *v85; // [rsp+C0h] [rbp-88h]
  unsigned __int16 *v86; // [rsp+C8h] [rbp-80h]
  unsigned __int16 *v87; // [rsp+D0h] [rbp-78h]
  __int128 v88; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v89; // [rsp+E8h] [rbp-60h]
  __int64 v90; // [rsp+F8h] [rbp-50h]
  ATL::CAtlException *v91; // [rsp+108h] [rbp-40h] BYREF

  v90 = -2;
  v84 = a4;
  v85 = a3;
  v86 = a2;
  v75 = 0;
  v8 = (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184);
  v9 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(
         &v75,
         (char *)this - 184);
  if ( v9 < 0 )
    goto LABEL_8;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 22) + 24LL))((char *)this - 176);
  WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo((char *)this - 80);
  if ( !a3 )
  {
    v9 = -2147467261;
LABEL_8:
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
    return (unsigned int)v9;
  }
  IsOtherObjectInstanceNameCompatible = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
                                          (char *)this + 32,
                                          a3);
  if ( IsOtherObjectInstanceNameCompatible < 0
    || a4
    && (IsOtherObjectInstanceNameCompatible = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
                                                (char *)this + 32,
                                                a4),
        IsOtherObjectInstanceNameCompatible < 0) )
  {
    v9 = IsOtherObjectInstanceNameCompatible;
    goto LABEL_8;
  }
  ((void (__stdcall *)(void *))ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>)(&lpFileName);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, a2);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v91) )
    {
      LODWORD(v71) = *(_DWORD *)v91;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18005EB47);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
      return (unsigned int)v71;
    }
  }
  v14 = (char *)lpFileName;
  if ( *((_DWORD *)lpFileName - 4) )
  {
    v15 = ((__int64 (__fastcall *)(LPCWSTR, const unsigned __int16 *, unsigned int))WindowsPerformanceRecorder::Impl::TryAccessFileS)(
            lpFileName,
            v12,
            v13);
    v16 = v15;
    if ( v15 < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"Stop",
        (const char *)0x79B,
        v15,
        "COMGUARD",
        (const char *)v67);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
      return v16;
    }
  }
  v78 = off_180090E08;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, Perf_StopProfiles_Begin, v14);
  v80 = v8;
  v17 = 0;
  v76 = 0;
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(v8);
  v68 = RunningProfileTraceType;
  if ( RunningProfileTraceType )
  {
LABEL_122:
    WindowsPerformanceRecorder::CControlManager::Stop_::_2_::CPerfEventMacro::_CPerfEventMacro(&v78);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
    return (unsigned int)RunningProfileTraceType;
  }
  v69 = 0;
  v19 = *((_DWORD *)this + 96);
  if ( (v19 & 2) != 0 )
  {
    v20 = v19 & 8;
    if ( (v19 & 8) == 0 )
    {
      RunningProfileTraceType = -984068085;
      v68 = -984068085;
    }
  }
  else
  {
    v20 = v19 & 8;
  }
  if ( (v19 & 1) != 0 )
  {
    v87 = L"Normal";
LABEL_25:
    v21 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(v8);
    if ( v21 < 0 )
      RunningProfileTraceType = v21;
    v68 = RunningProfileTraceType;
    goto LABEL_28;
  }
  if ( !v20 )
  {
    RunningProfileTraceType = -984076288;
    goto LABEL_122;
  }
  v87 = L"Boot";
  if ( (v19 & 2) == 0 )
    goto LABEL_25;
  v69 = 1;
  if ( !*((_BYTE *)this + 336) )
    goto LABEL_25;
LABEL_28:
  v22 = 0;
  v77 = 0;
  v70 = 0;
  v72 = 0;
  WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(
    v8,
    *((_DWORD *)this + 96));
  if ( RunningProfileTraceType < 0 )
    goto LABEL_50;
  v79 = (WindowsPerformanceRecorder::CETWProperties::CEventSession *)operator new(0x1A8u);
  v17 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(v79);
  v76 = v17;
  v23 = WindowsPerformanceRecorder::CETWProperties::Initialize(
          (WindowsPerformanceRecorder::CETWProperties *)v17,
          v85,
          v8,
          (*((_DWORD *)this + 96) & 0x10) != 0);
  RunningProfileTraceType = v23;
  if ( v23 < 0 )
    goto LABEL_49;
  v22 = *(char **)(v17 + 320);
  v77 = v22;
  WindowsPerformanceRecorder::TelemetryUsage((WindowsPerformanceRecorder *)0x2000, (unsigned __int64)"Stop", v22, v24);
  if ( *(_DWORD *)(v17 + 256) != 2 )
  {
    RunningProfileTraceType = -984068085;
    v68 = -984068085;
    goto LABEL_50;
  }
  if ( (*((_BYTE *)this + 384) & 8) == 0
    && (v23 = WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(
                v8,
                (struct WindowsPerformanceRecorder::CETWProperties *)v17,
                0),
        RunningProfileTraceType = v23,
        v23 < 0)
    || (v23 = WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(
                v8,
                (struct WindowsPerformanceRecorder::CETWProperties *)v17,
                0),
        RunningProfileTraceType = v23,
        v23 < 0) )
  {
LABEL_49:
    v68 = v23;
    goto LABEL_50;
  }
  if ( !v69 || *((_BYTE *)this + 336) )
  {
    v26 = 0;
    if ( v69 )
    {
      v27 = 0;
      goto LABEL_39;
    }
  }
  else
  {
    v26 = 1;
  }
  v27 = 1;
LABEL_39:
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(
                              v8,
                              (struct WindowsPerformanceRecorder::CETWProperties *)v17,
                              v25,
                              v27);
  v68 = RunningProfileTraceType;
  if ( RunningProfileTraceType >= 0 && v26 )
  {
    v28 = *(void ***)(v17 + 8);
    v29 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession **)(v17 + 16);
    v79 = v29;
    while ( v28 != (void **)v29 )
    {
      Block = *v28;
      FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)Block);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&v71,
        (char *)FileName);
      RunningProfileTraceType = WindowsPerformanceRecorder::Impl::GetFileNameWithTag(&v71, L"Shutdown");
      v68 = RunningProfileTraceType;
      if ( RunningProfileTraceType < 0
        || (SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)Block),
            RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(
                                        v8,
                                        (const unsigned __int16 *)v22,
                                        SessionName,
                                        v71),
            v68 = RunningProfileTraceType,
            RunningProfileTraceType < 0) )
      {
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v71);
        break;
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v71);
      ++v28;
      v29 = v79;
    }
  }
LABEL_50:
  v81 = (__int64)v8;
  v82 = 0;
  v83 = 0;
  if ( RunningProfileTraceType < 0 )
    goto LABEL_95;
  WindowsPerformanceRecorder::CETWProperties::SortEventSessionsByType((WindowsPerformanceRecorder::CETWProperties *)v17);
  v32 = WindowsPerformanceRecorder::CControlManager::CreateMarkSession(
          v8,
          (const struct WindowsPerformanceRecorder::CETWProperties *)v17,
          &v82);
  v33 = v32;
  if ( v32 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"Stop",
      (const char *)0x820,
      v32,
      "COMGUARD",
      (const char *)v67);
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
    if ( v17 )
      goto LABEL_88;
    goto LABEL_89;
  }
  v34 = WindowsPerformanceRecorder::CControlManager::CMarkSession::Start((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
  v33 = v34;
  if ( v34 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"Stop",
      (const char *)0x821,
      v34,
      "COMGUARD",
      (const char *)v67);
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
    if ( v17 )
      goto LABEL_88;
    goto LABEL_89;
  }
  WindowsPerformanceRecorder::CControlManager::LogMark(v35, *((_QWORD *)v82 + 14), L"Wpr_Initiated_Rundown");
  v88 = 0;
  v89 = 0;
  v79 = 0;
  for ( i = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 8);
        i != *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 16);
        ++i )
  {
    v37 = *i;
    if ( *(_DWORD *)*i == 1 )
    {
      if ( (unsigned __int8)WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(*i, 2) )
        WindowsPerformanceRecorder::CControlManager::CaptureStateRundown(v39, v37, v38);
      v88 = 0;
      v89 = 0;
      Block = 0;
      RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::DisableHighVolumeSystemFlags(
                                  v39,
                                  (int)v37,
                                  (int)&v88,
                                  (int)&Block,
                                  (__int64)&v79);
      v68 = RunningProfileTraceType;
      if ( RunningProfileTraceType < 0 )
      {
        v41 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v37);
        WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
          v8,
          RunningProfileTraceType,
          v42,
          v41,
          (const unsigned __int16 *)v22,
          0);
        v43 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v37);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"Stop",
          (const char *)0x838,
          RunningProfileTraceType,
          "%ws: %ws",
          v43,
          v22);
        RunningProfileTraceType = 0;
        v68 = 0;
      }
      WindowsPerformanceRecorder::CControlManager::DisableHighVolumeMemorySystemFlags(v40, v37);
      WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
        (__int64)v8,
        (const unsigned __int16 *)v22,
        (__int64)v37,
        2,
        0);
      free(Block);
      break;
    }
  }
  v44 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 8);
  v45 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 16);
  Block = v45;
  while ( v44 != v45 )
  {
    v79 = *v44;
    LODWORD(v71) = 0;
    v46 = WindowsPerformanceRecorder::CControlManager::StopEventSession(
            v8,
            (unsigned int *)&v71,
            (const unsigned __int16 *)v22,
            v79);
    v70 += (unsigned int)v71;
    v72 = v70;
    if ( v46 < 0
      || (WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v79),
          v47 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v79),
          v46 = WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(
                  v8,
                  (const unsigned __int16 *)v22,
                  v47,
                  v48),
          v46 < 0) )
    {
      if ( RunningProfileTraceType >= 0 )
        RunningProfileTraceType = v46;
      v68 = RunningProfileTraceType;
    }
    v49 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(v8, 0);
    if ( v49 < 0 )
    {
      if ( RunningProfileTraceType >= 0 )
      {
        RunningProfileTraceType = v49;
        v68 = v49;
      }
      break;
    }
    ++v44;
    v45 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)Block;
  }
  v50 = WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(
          v8,
          (struct WindowsPerformanceRecorder::CETWProperties *)v17);
  if ( v50 < 0 )
  {
    if ( RunningProfileTraceType >= 0 )
    {
      RunningProfileTraceType = v50;
      v68 = v50;
    }
    goto LABEL_95;
  }
  if ( RunningProfileTraceType < 0 )
  {
    v68 = RunningProfileTraceType;
    goto LABEL_95;
  }
  if ( v84 )
  {
    RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
                                v8,
                                (struct WindowsPerformanceRecorder::CETWProperties *)v17,
                                (__int64)v86,
                                (__int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))v84,
                                0,
                                v69,
                                (struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)&v81,
                                0);
    v68 = RunningProfileTraceType;
LABEL_92:
    if ( RunningProfileTraceType < 0 )
      WindowsPerformanceRecorder::CControlManager::CleanupGeneratedFiles(v8, (const unsigned __int16 *)v22);
LABEL_95:
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
    v51 = 0;
    v52 = v87;
    if ( v87 && v17 )
    {
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        v51 = WindowsPerformanceRecorder::CControlManager::ClearStateInRegistry(v8, v87);
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_ellipsis(4) )
        {
          LODWORD(v71) = -2147024882;
          v14 = (char *)lpFileName;
          v17 = v76;
          RunningProfileTraceType = v68;
          v70 = v72;
          v51 = -2147024882;
          v8 = v80;
          __eh34_try_continuation(4, &loc_18005E84F);
          goto LABEL_100;
        }
      }
    }
    if ( v51 >= 0 )
    {
      if ( RunningProfileTraceType >= 0 )
      {
LABEL_115:
        if ( !v69 || !*((_BYTE *)this + 336) || RunningProfileTraceType < 0 )
          WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(v8, RunningProfileTraceType, v70);
        if ( v17 )
          (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
        goto LABEL_122;
      }
LABEL_102:
      if ( v17 )
      {
        v84 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 16);
        for ( j = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v17 + 8); j != v84; ++j )
        {
          v55 = *j;
          if ( (int)WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(v8, *j) >= 0 )
          {
            LODWORD(v71) = 0;
            v56 = WindowsPerformanceRecorder::CControlManager::StopEventSession(
                    v8,
                    (unsigned int *)&v71,
                    (const unsigned __int16 *)v77,
                    v55);
            v72 = v56;
            v70 += (unsigned int)v71;
            if ( v56 < 0 )
            {
              WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
                v8,
                v56,
                &IID_IControlManager,
                (const unsigned __int16 *)v77,
                0);
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)3,
                (unsigned __int8)"Stop",
                (const char *)0x8AE,
                v72,
                "%ws",
                v77);
            }
          }
          v57 = (WindowsPerformanceRecorder::Impl *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v55);
          if ( WindowsPerformanceRecorder::Impl::FileExists(v57, v58) )
          {
            v59 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v55);
            if ( !DeleteFileW(v59) )
            {
              Error = ATL::AtlHresultFromLastError();
              WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
                v8,
                Error,
                &IID_IControlManager,
                (const unsigned __int16 *)v77,
                0);
              v61 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v55);
              v62 = ATL::AtlHresultFromLastError();
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)3,
                (unsigned __int8)"Stop",
                (const char *)0x8B7,
                v62,
                "Fail to delete %ws",
                v61);
            }
          }
        }
      }
      if ( WindowsPerformanceRecorder::Impl::FileExists((WindowsPerformanceRecorder::Impl *)v14, v52)
        && !DeleteFileW((LPCWSTR)v14) )
      {
        v63 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
          v8,
          v63,
          &IID_IControlManager,
          (const unsigned __int16 *)v77,
          0);
        v64 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"Stop",
          (const char *)0x8C2,
          v64,
          "Fail to delete %ws",
          v14);
      }
      v65 = v77;
      WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
        v8,
        (unsigned int)RunningProfileTraceType,
        1,
        &IID_IControlManager,
        v77);
      WindowsPerformanceRecorder::TelemetryError(
        (WindowsPerformanceRecorder *)0x2000,
        (unsigned __int64)"Stop",
        v65,
        (const unsigned __int16 *)(unsigned int)RunningProfileTraceType,
        Format);
      goto LABEL_115;
    }
LABEL_100:
    v53 = v77;
    WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
      v8,
      v51,
      &IID_IControlManager,
      (const unsigned __int16 *)v77,
      0);
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"Stop",
      (const char *)0x899,
      v51,
      "%ws",
      v53);
    if ( RunningProfileTraceType >= 0 )
      RunningProfileTraceType = v51;
    goto LABEL_102;
  }
  ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(
    &Block,
    (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v85);
  if ( Block )
  {
    v71 = 0;
    v33 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **))(*(_QWORD *)Block + 96LL))(Block, &v71);
    if ( v33 < 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
      WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
      if ( v17 )
LABEL_88:
        (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
LABEL_89:
      v76 = 0;
      WindowsPerformanceRecorder::CControlManager::Stop_::_2_::CPerfEventMacro::_CPerfEventMacro(&v78);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
      return (unsigned int)v33;
    }
    RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
                                v8,
                                (struct WindowsPerformanceRecorder::CETWProperties *)v17,
                                (__int64)v86,
                                (__int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))v71,
                                0,
                                v69,
                                (struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)&v81,
                                0);
    v68 = RunningProfileTraceType;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
    goto LABEL_92;
  }
  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
  WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v81);
  if ( v17 )
    (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
  v76 = 0;
  WindowsPerformanceRecorder::CControlManager::Stop_::_2_::CPerfEventMacro::_CPerfEventMacro(&v78);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
  WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v75);
  return 2147500034LL;
}

```

## disassembly

```asm
0x18005deb0  mov     rax, rsp
0x18005deb3  mov     [rax+8], rcx
0x18005deb7  push    rdi
0x18005deb8  push    r12
0x18005deba  push    r13
0x18005debc  push    r14
0x18005debe  push    r15
0x18005dec0  sub     rsp, 120h
0x18005dec7  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x18005decf  mov     [rax+10h], rbx
0x18005ded3  mov     [rax+18h], rsi
0x18005ded7  mov     rax, cs:__security_cookie
0x18005dede  xor     rax, rsp
0x18005dee1  mov     [rsp+148h+var_38], rax
0x18005dee9  mov     rdi, r9
0x18005deec  mov     [rsp+148h+var_90], r9
0x18005def4  mov     r15, r8
0x18005def7  mov     [rsp+148h+var_88], r8
0x18005deff  mov     r13, rdx
0x18005df02  mov     [rsp+148h+var_80], rdx
0x18005df0a  mov     rsi, rcx
0x18005df0d  xor     r14d, r14d
0x18005df10  mov     [rsp+148h+var_D8], r14
0x18005df15  lea     r12, [rcx-0B8h]
0x18005df1c  mov     rdx, r12
0x18005df1f  lea     rcx, [rsp+148h+var_D8]
0x18005df24  call    ??$Acquire@VCControlManager@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCControlManager@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(WindowsPerformanceRecorder::CControlManager *)
0x18005df29  mov     ebx, eax
0x18005df2b  test    eax, eax
0x18005df2d  js      short loc_18005DF7E
0x18005df2f  lea     rcx, [rsi-0B0h]
0x18005df36  mov     rax, [rcx]
0x18005df39  mov     rax, [rax+18h]
0x18005df3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df42  lea     rcx, [rsi-50h]
0x18005df46  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x18005df4b  test    r15, r15
0x18005df4e  jnz     short loc_18005DF57
0x18005df50  mov     ebx, 80004003h
0x18005df55  jmp     short loc_18005DF7E
0x18005df57  mov     rdx, r15
0x18005df5a  lea     rcx, [rsi+20h]
0x18005df5e  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18005df63  test    eax, eax
0x18005df65  js      short loc_18005DF7C
0x18005df67  test    rdi, rdi
0x18005df6a  jz      short loc_18005DF8F
0x18005df6c  mov     rdx, rdi
0x18005df6f  lea     rcx, [rsi+20h]
0x18005df73  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18005df78  test    eax, eax
0x18005df7a  jns     short loc_18005DF8F
0x18005df7c  mov     ebx, eax
0x18005df7e  lea     rcx, [rsp+148h+var_D8]; this
0x18005df83  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18005df88  mov     eax, ebx
0x18005df8a  jmp     loc_18005EB60
0x18005df8f  lea     rcx, [rsp+148h+lpFileName]; void *
0x18005df94  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005df99  nop
0x18005df9a  mov     rdx, r13
0x18005df9d  lea     rcx, [rsp+148h+lpFileName]
0x18005dfa2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18005dfa7  mov     rdi, [rsp+148h+lpFileName]
0x18005dfac  cmp     [rdi-10h], r14d
0x18005dfb0  jz      short loc_18005E003
0x18005dfb2  mov     rcx, rdi; lpFileName
0x18005dfb5  call    ?TryAccessFileS@Impl@WindowsPerformanceRecorder@@YAJPEBGK@Z; WindowsPerformanceRecorder::Impl::TryAccessFileS(ushort const *,ulong)
0x18005dfba  mov     ebx, eax
0x18005dfbc  test    eax, eax
0x18005dfbe  jns     short loc_18005E003
0x18005dfc0  lea     rcx, aComguard; "COMGUARD"
0x18005dfc7  mov     [rsp+148h+Format], rcx; Format
0x18005dfcc  mov     r9d, eax; unsigned int
0x18005dfcf  mov     r8d, 79Bh; char *
0x18005dfd5  lea     rdx, aStop_0; "Stop"
0x18005dfdc  mov     ecx, 2; this
0x18005dfe1  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005dfe6  nop
0x18005dfe7  lea     rcx, [rsp+148h+lpFileName]; this
0x18005dfec  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005dff1  nop
0x18005dff2  lea     rcx, [rsp+148h+var_D8]; this
0x18005dff7  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18005dffc  mov     eax, ebx
0x18005dffe  jmp     loc_18005EB60
0x18005e003  lea     rax, off_180090E08
0x18005e00a  mov     [rsp+148h+var_C0], rax
0x18005e012  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 4
0x18005e019  jz      short loc_18005E032
0x18005e01b  mov     r8, rdi
0x18005e01e  lea     rdx, Perf_StopProfiles_Begin
0x18005e025  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18005e02c  call    McTemplateU0z_EventWriteTransfer
0x18005e031  nop
0x18005e032  mov     [rsp+148h+var_B0], r12
0x18005e03a  mov     rbx, r14
0x18005e03d  mov     [rsp+148h+var_D0], rbx
0x18005e042  mov     rcx, r12; this
0x18005e045  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x18005e04a  mov     r15d, eax
0x18005e04d  mov     [rsp+148h+var_108], eax
0x18005e051  test    eax, eax
0x18005e053  jnz     loc_18005EB1F
0x18005e059  mov     [rsp+148h+var_104], r14b
0x18005e05e  mov     ecx, [rsi+180h]
0x18005e064  mov     edx, ecx
0x18005e066  and     edx, 2
0x18005e069  mov     eax, ecx
0x18005e06b  jz      short loc_18005E07F
0x18005e06d  and     eax, 8
0x18005e070  jnz     short loc_18005E082
0x18005e072  mov     r15d, 0C558500Bh
0x18005e078  mov     [rsp+148h+var_108], r15d
0x18005e07d  jmp     short loc_18005E082
0x18005e07f  and     eax, 8
0x18005e082  test    cl, 1
0x18005e085  jz      short loc_18005E098
0x18005e087  lea     rax, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18005e08e  mov     [rsp+148h+var_78], rax
0x18005e096  jmp     short loc_18005E0C1
0x18005e098  test    eax, eax
0x18005e09a  jz      loc_18005EB19
0x18005e0a0  lea     rax, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18005e0a7  mov     [rsp+148h+var_78], rax
0x18005e0af  test    edx, edx
0x18005e0b1  jz      short loc_18005E0C1
0x18005e0b3  mov     [rsp+148h+var_104], 1
0x18005e0b8  cmp     [rsi+150h], r14b
0x18005e0bf  jnz     short loc_18005E0D4
0x18005e0c1  mov     rcx, r12; this
0x18005e0c4  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x18005e0c9  test    eax, eax
0x18005e0cb  cmovs   r15d, eax
0x18005e0cf  mov     [rsp+148h+var_108], r15d
0x18005e0d4  mov     r13, r14
0x18005e0d7  mov     [rsp+148h+var_C8], r14
0x18005e0df  mov     eax, r14d
0x18005e0e2  mov     [rsp+148h+var_100], eax
0x18005e0e6  mov     [rsp+148h+var_F0], eax
0x18005e0ea  mov     edx, [rsi+180h]
0x18005e0f0  mov     rcx, r12
0x18005e0f3  call    ?SetTemporaryTraceDirectoryToCurrentTracingDirectory@CControlManager@WindowsPerformanceRecorder@@AEAAXUCTraceType@IControlInfo@Status@2@@Z; WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(WindowsPerformanceRecorder::Status::IControlInfo::CTraceType)
0x18005e0f8  test    r15d, r15d
0x18005e0fb  js      loc_18005E2C2
0x18005e101  mov     ecx, 1A8h; Size
0x18005e106  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e10b  mov     [rsp+148h+var_B8], rax
0x18005e113  mov     rcx, rax; this
0x18005e116  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18005e11b  mov     rbx, rax
0x18005e11e  mov     [rsp+148h+var_D0], rax
0x18005e123  mov     r9d, [rsi+180h]
0x18005e12a  shr     r9d, 4
0x18005e12e  and     r9b, 1; bool
0x18005e132  mov     r8, r12; struct WindowsPerformanceRecorder::CControlManager *
0x18005e135  mov     rdx, [rsp+148h+var_88]; struct IProfileCollection *
0x18005e13d  mov     rcx, rax; this
0x18005e140  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18005e145  mov     r15d, eax
0x18005e148  test    eax, eax
0x18005e14a  js      loc_18005E2BE
0x18005e150  mov     r13, [rbx+140h]
0x18005e157  mov     [rsp+148h+var_C8], r13
0x18005e15f  mov     r8, r13; char *
0x18005e162  lea     rdx, aStop_0; "Stop"
0x18005e169  mov     ecx, 2000h; this
0x18005e16e  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x18005e173  cmp     dword ptr [rbx+100h], 2
0x18005e17a  jz      short loc_18005E18C
0x18005e17c  mov     r15d, 0C558500Bh
0x18005e182  mov     [rsp+148h+var_108], r15d
0x18005e187  jmp     loc_18005E2C2
0x18005e18c  test    byte ptr [rsi+180h], 8
0x18005e193  jnz     short loc_18005E1AE
0x18005e195  xor     r8d, r8d; bool
0x18005e198  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005e19b  mov     rcx, r12; this
0x18005e19e  call    ?ValidateWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18005e1a3  mov     r15d, eax
0x18005e1a6  test    eax, eax
0x18005e1a8  js      loc_18005E2BE
0x18005e1ae  xor     r8d, r8d; bool
0x18005e1b1  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005e1b4  mov     rcx, r12; this
0x18005e1b7  call    ?ValidateWithRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18005e1bc  mov     r15d, eax
0x18005e1bf  test    eax, eax
0x18005e1c1  js      loc_18005E2BE
0x18005e1c7  mov     al, [rsp+148h+var_104]
0x18005e1cb  test    al, al
0x18005e1cd  jz      loc_18005E29F
0x18005e1d3  cmp     [rsi+150h], r14b
0x18005e1da  jnz     loc_18005E29F
0x18005e1e0  mov     sil, 1
0x18005e1e3  mov     r9b, 1; bool
0x18005e1e6  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005e1e9  mov     rcx, r12; this
0x18005e1ec  call    ?SetProgressHandlerRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N1@Z; WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool,bool)
0x18005e1f1  mov     r15d, eax
0x18005e1f4  mov     [rsp+148h+var_108], eax
0x18005e1f8  test    eax, eax
0x18005e1fa  js      loc_18005E2C2
0x18005e200  test    sil, sil
0x18005e203  jz      loc_18005E2C2
0x18005e209  mov     rsi, [rbx+8]
0x18005e20d  mov     rax, [rbx+10h]
0x18005e211  mov     [rsp+148h+var_B8], rax
0x18005e219  cmp     rsi, rax
0x18005e21c  jz      loc_18005E2C2
0x18005e222  mov     rax, [rsi]
0x18005e225  mov     [rsp+148h+Block], rax
0x18005e22a  mov     rcx, rax; this
0x18005e22d  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x18005e232  mov     rdx, rax
0x18005e235  lea     rcx, [rsp+148h+var_F8]
0x18005e23a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005e23f  nop
0x18005e240  lea     rdx, ?sc_wchShutdownFileNameTag@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Shutdown"
0x18005e247  lea     rcx, [rsp+148h+var_F8]
0x18005e24c  call    ?GetFileNameWithTag@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::Impl::GetFileNameWithTag(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x18005e251  mov     r15d, eax
0x18005e254  mov     [rsp+148h+var_108], eax
0x18005e258  test    eax, eax
0x18005e25a  js      short loc_18005E2B2
0x18005e25c  mov     rcx, [rsp+148h+Block]; this
0x18005e261  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005e266  mov     r9, [rsp+148h+var_F8]; unsigned __int16 *
0x18005e26b  mov     r8, rax; unsigned __int16 *
0x18005e26e  mov     rdx, r13; unsigned __int16 *
0x18005e271  mov     rcx, r12; this
0x18005e274  call    ?AdjustControlProgressHandler@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG00@Z; WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(ushort const *,ushort const *,ushort const *)
0x18005e279  mov     r15d, eax
0x18005e27c  mov     [rsp+148h+var_108], eax
0x18005e280  test    eax, eax
0x18005e282  js      short loc_18005E2B2
0x18005e284  lea     rcx, [rsp+148h+var_F8]; this
0x18005e289  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005e28e  add     rsi, 8
0x18005e292  mov     rax, [rsp+148h+var_B8]
0x18005e29a  jmp     loc_18005E219
0x18005e29f  mov     sil, r14b
0x18005e2a2  test    al, al
0x18005e2a4  jz      loc_18005E1E3
0x18005e2aa  mov     r9b, r14b
0x18005e2ad  jmp     loc_18005E1E6
0x18005e2b2  lea     rcx, [rsp+148h+var_F8]; this
0x18005e2b7  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005e2bc  jmp     short loc_18005E2C2
0x18005e2be  mov     [rsp+148h+var_108], eax
0x18005e2c2  mov     [rsp+148h+var_A8], r12
0x18005e2ca  mov     [rsp+148h+var_A0], r14
0x18005e2d2  mov     [rsp+148h+var_98], r14b
0x18005e2da  test    r15d, r15d
0x18005e2dd  js      loc_18005E7ED
0x18005e2e3  mov     rcx, rbx; this
0x18005e2e6  call    ?SortEventSessionsByType@CETWProperties@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CETWProperties::SortEventSessionsByType(void)
0x18005e2eb  lea     r8, [rsp+148h+var_A0]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession **
0x18005e2f3  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005e2f6  mov     rcx, r12; this
0x18005e2f9  call    ?CreateMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBVCETWProperties@2@PEAPEAUCEventSession@32@@Z; WindowsPerformanceRecorder::CControlManager::CreateMarkSession(WindowsPerformanceRecorder::CETWProperties const &,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)
0x18005e2fe  mov     esi, eax
0x18005e300  test    eax, eax
0x18005e302  jns     short loc_18005E380
0x18005e304  lea     rcx, aComguard; "COMGUARD"
0x18005e30b  mov     [rsp+148h+Format], rcx; Format
0x18005e310  mov     r9d, eax; unsigned int
0x18005e313  mov     r8d, 820h; char *
0x18005e319  lea     rdx, aStop_0; "Stop"
0x18005e320  mov     ecx, 2; this
0x18005e325  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005e32a  nop
0x18005e32b  lea     rcx, [rsp+148h+var_A8]; this
0x18005e333  call    ?Cleanup@CMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAXXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup(void)
0x18005e338  nop
0x18005e339  test    rbx, rbx
0x18005e33c  jz      short loc_18005E351
0x18005e33e  mov     rax, [rbx]
0x18005e341  mov     edx, 1
0x18005e346  mov     rcx, rbx
0x18005e349  mov     rax, [rax]
0x18005e34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e351  mov     [rsp+148h+var_D0], r14
0x18005e356  lea     rcx, [rsp+148h+var_C0]
0x18005e35e  call    _WindowsPerformanceRecorder__CControlManager__Stop____2___CPerfEventMacro___CPerfEventMacro
0x18005e363  nop
0x18005e364  lea     rcx, [rsp+148h+lpFileName]; this
0x18005e369  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005e36e  nop
0x18005e36f  lea     rcx, [rsp+148h+var_D8]; this
0x18005e374  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18005e379  mov     eax, esi
0x18005e37b  jmp     loc_18005EB60
0x18005e380  lea     rcx, [rsp+148h+var_A8]; this
0x18005e388  call    ?Start@CMarkSession@CControlManager@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Start(void)
0x18005e38d  mov     esi, eax
0x18005e38f  test    eax, eax
0x18005e391  jns     short loc_18005E40F
0x18005e393  lea     rcx, aComguard; "COMGUARD"
0x18005e39a  mov     [rsp+148h+Format], rcx; Format
  ... truncated ...
```
