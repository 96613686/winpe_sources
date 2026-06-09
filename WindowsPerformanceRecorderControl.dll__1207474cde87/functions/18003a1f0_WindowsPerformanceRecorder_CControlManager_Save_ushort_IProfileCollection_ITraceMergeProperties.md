# WindowsPerformanceRecorder::CControlManager::Save(ushort *,IProfileCollection *,ITraceMergeProperties *)

- ea: `0x18003a1f0`
- end: `0x18003af6d`
- name: `?Save@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAGPEAUIProfileCollection@@PEAUITraceMergeProperties@@@Z`
- size: `3453`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *this, unsigned __int16 *, struct IProfileCollection *, WindowsPerformanceRecorder::CETWProperties::CEventSession **)`
- caller_count: `0`
- callee_count: `55`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000829c`
- `0x180008330`
- `0x180016480`
- `0x18001a61c`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c458`
- `0x18001c820`
- `0x18001d190`
- `0x18001e2b8`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x180021810`
- `0x1800236b0`
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
- `0x18003a1f0`
- `0x18003c270`
- `0x18003c6a4`
- `0x180040a04`
- `0x1800449a0`
- `0x180044e90`
- `0x180045cb4`
- `0x1800490f8`
- `0x18004a1b0`
- `0x18004a664`
- `0x18004b024`
- `0x18004b128`
- `0x18004b17c`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004ed10`
- `0x180059820`
- `0x180059970`
- `0x1800599c0`
- `0x180059e74`
- `0x18005a020`
- `0x18005b310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a7fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003aa8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003a7fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003aa8a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003acdd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ad75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ae0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003acdd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ad75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ae0d`

## string_xrefs

- `0x18003a304`: `COMGUARD`
- `0x18003a50e`: `COMGUARD`
- `0x18003a59d`: `COMGUARD`
- `0x18003ad1c`: `Fail to delete %ws`
- `0x18003ad44`: `Fail to delete %ws`
- `0x18003ad5f`: `Fail to delete %ws`
- `0x18003ae41`: `Fail to delete %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::Save(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 *a2,
        struct IProfileCollection *a3,
        WindowsPerformanceRecorder::CETWProperties::CEventSession **a4)
{
  WindowsPerformanceRecorder::CControlManager *v8; // r13
  int v9; // ebx
  int IsOtherObjectInstanceNameCompatible; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // rsi
  signed int v15; // eax
  unsigned int v16; // ebx
  int RunningProfileTraceType; // eax
  int v18; // edi
  __int64 v19; // rbx
  int updated; // r15d
  const unsigned __int16 *v21; // r9
  bool v22; // r8
  signed int v23; // eax
  unsigned int v24; // edi
  signed int v25; // eax
  WindowsPerformanceRecorder::CControlManager *v26; // rcx
  void *v27; // rdi
  WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v29; // r12
  unsigned int v30; // edx
  __int64 v31; // rcx
  int v32; // edi
  const unsigned __int16 *SessionName; // r9
  char *v34; // r15
  const struct _GUID *v35; // r8
  const char *v36; // rax
  int v37; // ecx
  int v38; // edi
  const unsigned __int16 *v39; // rax
  const struct _GUID *v40; // r8
  const char *v41; // rax
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v42; // rax
  WindowsPerformanceRecorder::CETWProperties *v43; // rcx
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v44; // rdx
  int v45; // edx
  int v46; // eax
  int v47; // edx
  int v48; // eax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **k; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v50; // r12
  const unsigned __int16 *v51; // rax
  const struct _GUID *v52; // r8
  const char *v53; // rax
  char *v54; // r12
  __int64 v55; // r8
  int v56; // eax
  char v57; // r15
  int v58; // edi
  const unsigned __int16 *v59; // rdx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **m; // r12
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v61; // rdi
  WindowsPerformanceRecorder::Impl *FileName; // rax
  const unsigned __int16 *v63; // rdx
  const WCHAR *v64; // rax
  int Error; // eax
  const char *v66; // rdi
  unsigned int v67; // eax
  int v68; // eax
  unsigned int v69; // eax
  char *v70; // rsi
  char *v71; // r12
  const char *v72; // rdi
  const unsigned __int16 *v73; // rdx
  int v74; // eax
  unsigned int v75; // eax
  char *v76; // rdi
  int Format; // [rsp+20h] [rbp-128h]
  struct IControlErrorInfo *v78; // [rsp+28h] [rbp-120h]
  char v79; // [rsp+40h] [rbp-108h]
  signed int v80; // [rsp+44h] [rbp-104h] BYREF
  char *v81; // [rsp+48h] [rbp-100h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-F8h] BYREF
  void *Block; // [rsp+58h] [rbp-F0h] BYREF
  unsigned int v84; // [rsp+60h] [rbp-E8h]
  __int64 v85; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v86; // [rsp+70h] [rbp-D8h]
  unsigned __int64 v87; // [rsp+78h] [rbp-D0h] BYREF
  __int64 (__fastcall **v88)(void *); // [rsp+80h] [rbp-C8h] BYREF
  LPCWSTR v89; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v90; // [rsp+90h] [rbp-B8h] BYREF
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v91; // [rsp+98h] [rbp-B0h] BYREF
  char v92; // [rsp+A0h] [rbp-A8h]
  WindowsPerformanceRecorder::CControlManager *v93; // [rsp+A8h] [rbp-A0h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v94; // [rsp+B0h] [rbp-98h]
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v95; // [rsp+B8h] [rbp-90h]
  struct IProfileCollection *v96; // [rsp+C0h] [rbp-88h]
  WindowsPerformanceRecorder::CETWProperties *j; // [rsp+C8h] [rbp-80h]
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v98; // [rsp+D0h] [rbp-78h]
  __int128 v99; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v100; // [rsp+E8h] [rbp-60h]
  __int64 v101; // [rsp+F8h] [rbp-50h]
  ATL::CAtlException *v102; // [rsp+108h] [rbp-40h] BYREF

  v101 = -2;
  v94 = a4;
  v96 = a3;
  v89 = a2;
  v85 = 0;
  v8 = (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184);
  v9 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(
         &v85,
         (char *)this - 184);
  if ( v9 < 0 )
    goto LABEL_8;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 22) + 24LL))((char *)this - 176);
  WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo((char *)this - 80);
  if ( !a3 )
  {
    v9 = -2147467261;
LABEL_8:
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
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
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpFileName);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, a2);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v102) )
    {
      v80 = *(_DWORD *)v102;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18003AF27);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
      return (unsigned int)v80;
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
        (unsigned __int8)"Save",
        (const char *)0x4BC,
        v15,
        "COMGUARD",
        (const char *)v78);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
      return v16;
    }
  }
  v88 = &off_180090518;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, Perf_SaveProfiles_Begin, v14);
  v93 = v8;
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(v8);
  if ( RunningProfileTraceType )
  {
    updated = RunningProfileTraceType;
    goto LABEL_112;
  }
  v18 = *((_DWORD *)this + 96);
  if ( (v18 & 1) != 0 )
  {
    v79 = 0;
  }
  else
  {
    if ( (v18 & 8) == 0 )
    {
      if ( (v18 & 2) != 0 )
        updated = -984068086;
      else
        updated = -984076288;
      goto LABEL_112;
    }
    v79 = (*((_DWORD *)this + 96) & 2) != 0;
  }
  v19 = 0;
  v86 = 0;
  v81 = 0;
  v84 = 0;
  updated = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(v8);
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 352, (char *)this + 344);
  WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(
    v8,
    *((unsigned int *)this + 96));
  if ( updated >= 0 )
  {
    j = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
    v19 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(j);
    v86 = v19;
    updated = WindowsPerformanceRecorder::CETWProperties::Initialize(
                (WindowsPerformanceRecorder::CETWProperties *)v19,
                v96,
                v8,
                (*((_DWORD *)this + 96) & 0x10) != 0);
    if ( updated >= 0 )
    {
      v81 = *(char **)(v19 + 320);
      WindowsPerformanceRecorder::TelemetryUsage(
        (WindowsPerformanceRecorder *)0x2000,
        (unsigned __int64)"Save",
        v81,
        v21);
      if ( *(_DWORD *)(v19 + 256) == 1 || *(_DWORD *)(v19 + 256) == 2 )
      {
        if ( (*((_BYTE *)this + 384) & 8) != 0
          || (updated = WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(
                          v8,
                          (struct WindowsPerformanceRecorder::CETWProperties *)v19,
                          0),
              updated >= 0) )
        {
          updated = WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(
                      v8,
                      (struct WindowsPerformanceRecorder::CETWProperties *)v19,
                      0);
          if ( updated >= 0 )
            updated = WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(
                        v8,
                        (struct WindowsPerformanceRecorder::CETWProperties *)v19,
                        v22,
                        1);
        }
      }
      else
      {
        updated = -984068086;
      }
    }
  }
  WindowsPerformanceRecorder::CETWProperties::SortEventSessionsByType((WindowsPerformanceRecorder::CETWProperties *)v19);
  v90 = (__int64)v8;
  v91 = 0;
  v92 = 0;
  if ( updated < 0 )
    goto LABEL_89;
  v23 = WindowsPerformanceRecorder::CControlManager::CreateMarkSession(
          v8,
          (const struct WindowsPerformanceRecorder::CETWProperties *)v19,
          &v91);
  v24 = v23;
  if ( v23 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"Save",
      (const char *)0x526,
      v23,
      "COMGUARD",
      (const char *)v78);
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
    if ( v19 )
      (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
LABEL_33:
    v86 = 0;
    WindowsPerformanceRecorder::CControlManager::Save_::_2_::CPerfEventMacro::_CPerfEventMacro(&v88);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
    return v24;
  }
  v25 = WindowsPerformanceRecorder::CControlManager::CMarkSession::Start((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
  v24 = v25;
  if ( v25 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"Save",
      (const char *)0x527,
      v25,
      "COMGUARD",
      (const char *)v78);
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
    if ( v19 )
      (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
    goto LABEL_33;
  }
  WindowsPerformanceRecorder::CControlManager::LogMark(v26, *((_QWORD *)v91 + 14), L"Wpr_Initiated_Rundown");
  v99 = 0;
  v100 = 0;
  v87 = 0;
  v27 = 0;
  Block = 0;
  for ( i = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 8);
        i != *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 16);
        ++i )
  {
    v29 = *i;
    if ( *(_DWORD *)*i == 1 )
    {
      v99 = 0;
      v100 = 0;
      if ( (unsigned __int8)WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(v29, 2) )
        WindowsPerformanceRecorder::CControlManager::CaptureStateRundown(v31, v29, v30);
      if ( *((_BYTE *)v29 + 207) )
      {
        v32 = WindowsPerformanceRecorder::CControlManager::DisableHighVolumeSystemFlags(
                v31,
                (int)v29,
                (int)&v99,
                (int)&Block,
                (__int64)&v87);
        if ( v32 >= 0 )
        {
          v34 = v81;
        }
        else
        {
          SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v29);
          v34 = v81;
          WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
            v8,
            v32,
            v35,
            SessionName,
            (const unsigned __int16 *)v81,
            0);
          v36 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v29);
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"Save",
            (const char *)0x544,
            v32,
            "%ws: %ws",
            v36,
            v81);
        }
        updated = WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
                    (__int64)v8,
                    (const unsigned __int16 *)v34,
                    (__int64)v29,
                    *(_DWORD *)(v19 + 256),
                    0);
        if ( updated < 0 )
        {
          v38 = WindowsPerformanceRecorder::CControlManager::EnableHighVolumeSystemFlags(
                  v37,
                  (int)v29,
                  (int)&v99,
                  (int)&Block,
                  v87);
          if ( v38 >= 0 )
          {
            WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
              (__int64)v8,
              (const unsigned __int16 *)v81,
              (__int64)v29,
              *(_DWORD *)(v19 + 256),
              0);
          }
          else
          {
            v39 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v29);
            WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
              v8,
              v38,
              v40,
              v39,
              (const unsigned __int16 *)v81,
              0);
            v41 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v29);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)3,
              (unsigned __int8)"Save",
              (const char *)0x551,
              v38,
              "%ws: %ws",
              v41,
              v81);
          }
          free(Block);
          WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
          (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
          v86 = 0;
          WindowsPerformanceRecorder::CControlManager::Save_::_2_::CPerfEventMacro::_CPerfEventMacro(&v88);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
          WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
          return (unsigned int)updated;
        }
        v27 = Block;
      }
      break;
    }
  }
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::clear((char *)this + 360);
  v42 = *(struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 8);
  v43 = *(WindowsPerformanceRecorder::CETWProperties **)(v19 + 16);
  for ( j = v43; ; v43 = j )
  {
    v95 = v42;
    if ( v42 == (struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)v43 )
      break;
    v44 = *v42;
    v98 = *v42;
    if ( *(_DWORD *)(v19 + 256) != 1 || *(_DWORD *)v44 != 1 )
      goto LABEL_59;
    v80 = 0;
    v45 = WindowsPerformanceRecorder::CControlManager::SaveSystemRundown(
            (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184),
            (__int64)&Block,
            v87,
            *(_BYTE *)(v19 + 417));
    v84 += v80;
    v27 = Block;
    if ( v45 >= 0 )
    {
      v44 = v98;
LABEL_59:
      v80 = 0;
      v45 = WindowsPerformanceRecorder::CControlManager::SaveEventSession(
              (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184),
              (unsigned int *)&v80,
              (const unsigned __int16 *)v81,
              v44);
      v84 += v80;
      if ( v45 >= 0 )
        goto LABEL_63;
    }
    if ( updated >= 0 )
      updated = v45;
    v46 = ATL::AtlHresultFromWin32(0x4C7u);
    if ( v47 == v46 )
      break;
LABEL_63:
    v48 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(
            (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184),
            0);
    if ( v48 < 0 )
    {
      if ( updated >= 0 )
        updated = v48;
      break;
    }
    v42 = v95 + 1;
  }
  for ( k = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 8); ; ++k )
  {
    if ( k == *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 16) )
      goto LABEL_78;
    v50 = *k;
    if ( *(_DWORD *)*k == 1 )
      break;
  }
  if ( !*((_BYTE *)v50 + 207) )
  {
LABEL_78:
    v54 = v81;
    goto LABEL_79;
  }
  v80 = WindowsPerformanceRecorder::CControlManager::EnableHighVolumeSystemFlags(
          (int)v43,
          (int)v50,
          (int)&v99,
          (int)&Block,
          v87);
  if ( v80 >= 0 )
  {
    v55 = (__int64)v50;
    v54 = v81;
    v56 = WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
            (__int64)v8,
            (const unsigned __int16 *)v81,
            v55,
            *(_DWORD *)(v19 + 256),
            0);
    if ( v56 < 0 && updated >= 0 )
      updated = v56;
  }
  else
  {
    v51 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v50);
    WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
      v8,
      (int)v52,
      v52,
      v51,
      (const unsigned __int16 *)v81,
      0);
    v53 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v50);
    v54 = v81;
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"Save",
      (const char *)0x59A,
      v80,
      "%ws: %ws",
      v53,
      v81);
  }
LABEL_79:
  free(v27);
  if ( updated >= 0 )
  {
    v57 = *(_DWORD *)(v19 + 256) == 2;
    if ( v94 )
    {
      updated = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
                  v8,
                  (struct WindowsPerformanceRecorder::CETWProperties *)v19,
                  (__int64)v89,
                  (__int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))v94,
                  0,
                  v79,
                  (struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)&v90,
                  *(_DWORD *)(v19 + 256) == 2);
    }
    else
    {
      ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(
        &Block,
        v96);
      if ( !Block )
      {
        ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
        WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
        (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
        v86 = 0;
        WindowsPerformanceRecorder::CControlManager::Save_::_2_::CPerfEventMacro::_CPerfEventMacro(&v88);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
        WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
        return 2147500034LL;
      }
      v87 = 0;
      v58 = (*(__int64 (__fastcall **)(void *, unsigned __int64 *))(*(_QWORD *)Block + 96LL))(Block, &v87);
      if ( v58 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v87);
        ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
        WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
        (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
        v86 = 0;
        WindowsPerformanceRecorder::CControlManager::Save_::_2_::CPerfEventMacro::_CPerfEventMacro(&v88);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
        WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
        return (unsigned int)v58;
      }
      updated = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
                  v8,
                  (struct WindowsPerformanceRecorder::CETWProperties *)v19,
                  (__int64)v89,
                  (__int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))v87,
                  0,
                  v79,
                  (struct WindowsPerformanceRecorder::CETWProperties::CEventSession **)&v90,
                  v57);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v87);
      ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&Block);
    }
    if ( updated < 0 )
      WindowsPerformanceRecorder::CControlManager::CleanupGeneratedFiles(v8, (const unsigned __int16 *)v54);
  }
LABEL_89:
  WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup((WindowsPerformanceRecorder::CControlManager::CMarkSession *)&v90);
  if ( updated < 0 )
  {
    if ( v19 )
    {
      v94 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 16);
      for ( m = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v19 + 8); m != v94; ++m )
      {
        v61 = *m;
        FileName = (WindowsPerformanceRecorder::Impl *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(*m);
        if ( WindowsPerformanceRecorder::Impl::FileExists(FileName, v63) )
        {
          v64 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v61);
          if ( !DeleteFileW(v64) )
          {
            Error = ATL::AtlHresultFromLastError();
            WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
              v8,
              Error,
              &IID_IControlManager,
              (const unsigned __int16 *)v81,
              0);
            v66 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v61);
            v67 = ATL::AtlHresultFromLastError();
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)3,
              (unsigned __int8)"Save",
              (const char *)0x5E2,
              v67,
              "Fail to delete %ws",
              v66);
          }
        }
      }
    }
    if ( WindowsPerformanceRecorder::Impl::FileExists((WindowsPerformanceRecorder::Impl *)v14, v59)
      && !DeleteFileW((LPCWSTR)v14) )
    {
      v68 = ATL::AtlHresultFromLastError();
      WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
        v8,
        v68,
        &IID_IControlManager,
        (const unsigned __int16 *)v81,
        0);
      v69 = ATL::AtlHresultFromLastError();
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        (unsigned __int8)"Save",
        (const char *)0x5ED,
        v69,
        "Fail to delete %ws",
        v14);
    }
    v70 = (char *)*((_QWORD *)this + 45);
    v71 = (char *)*((_QWORD *)this + 46);
    while ( v70 != v71 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v89,
        v70);
      v72 = (const char *)v89;
      if ( WindowsPerformanceRecorder::Impl::FileExists((WindowsPerformanceRecorder::Impl *)v89, v73)
        && !DeleteFileW((LPCWSTR)v72) )
      {
        v74 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
          v8,
          v74,
          &IID_IControlManager,
          (const unsigned __int16 *)v81,
          0);
        v75 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"Save",
          (const char *)0x5FA,
          v75,
          "Fail to delete %ws",
          v72);
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v89);
      v70 += 8;
    }
    v76 = v81;
    WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
      v8,
      (unsigned int)updated,
      1,
      &IID_IControlManager,
      v81);
    WindowsPerformanceRecorder::TelemetryError(
      (WindowsPerformanceRecorder *)0x2000,
      (unsigned __int64)"Save",
      v76,
      (const unsigned __int16 *)(unsigned int)updated,
      Format);
  }
  WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(v8, updated, v84);
  if ( v19 )
    (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
LABEL_112:
  WindowsPerformanceRecorder::CControlManager::Save_::_2_::CPerfEventMacro::_CPerfEventMacro(&v88);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
  WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v85);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18003a1f0  mov     rax, rsp
0x18003a1f3  mov     [rax+8], rcx
0x18003a1f7  push    rdi
0x18003a1f8  push    r12
0x18003a1fa  push    r13
0x18003a1fc  push    r14
0x18003a1fe  push    r15
0x18003a200  sub     rsp, 120h
0x18003a207  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x18003a20f  mov     [rax+10h], rbx
0x18003a213  mov     [rax+18h], rsi
0x18003a217  mov     rax, cs:__security_cookie
0x18003a21e  xor     rax, rsp
0x18003a221  mov     [rsp+148h+var_38], rax
0x18003a229  mov     rdi, r9
0x18003a22c  mov     [rsp+148h+var_98], r9
0x18003a234  mov     rsi, r8
0x18003a237  mov     [rsp+148h+var_88], r8
0x18003a23f  mov     r15, rdx
0x18003a242  mov     [rsp+148h+var_C0], rdx
0x18003a24a  mov     r12, rcx
0x18003a24d  xor     r14d, r14d
0x18003a250  mov     [rsp+148h+var_E0], r14
0x18003a255  lea     r13, [rcx-0B8h]
0x18003a25c  mov     rdx, r13
0x18003a25f  lea     rcx, [rsp+148h+var_E0]
0x18003a264  call    ??$Acquire@VCControlManager@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCControlManager@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(WindowsPerformanceRecorder::CControlManager *)
0x18003a269  mov     ebx, eax
0x18003a26b  test    eax, eax
0x18003a26d  js      short loc_18003A2C2
0x18003a26f  lea     rcx, [r12-0B0h]
0x18003a277  mov     rax, [rcx]
0x18003a27a  mov     rax, [rax+18h]
0x18003a27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a283  lea     rcx, [r12-50h]
0x18003a288  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x18003a28d  test    rsi, rsi
0x18003a290  jnz     short loc_18003A299
0x18003a292  mov     ebx, 80004003h
0x18003a297  jmp     short loc_18003A2C2
0x18003a299  mov     rdx, rsi
0x18003a29c  lea     rcx, [r12+20h]
0x18003a2a1  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18003a2a6  test    eax, eax
0x18003a2a8  js      short loc_18003A2C0
0x18003a2aa  test    rdi, rdi
0x18003a2ad  jz      short loc_18003A2D3
0x18003a2af  mov     rdx, rdi
0x18003a2b2  lea     rcx, [r12+20h]
0x18003a2b7  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18003a2bc  test    eax, eax
0x18003a2be  jns     short loc_18003A2D3
0x18003a2c0  mov     ebx, eax
0x18003a2c2  lea     rcx, [rsp+148h+var_E0]; this
0x18003a2c7  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18003a2cc  mov     eax, ebx
0x18003a2ce  jmp     loc_18003AF40
0x18003a2d3  lea     rcx, [rsp+148h+lpFileName]; void *
0x18003a2d8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003a2dd  nop
0x18003a2de  mov     rdx, r15
0x18003a2e1  lea     rcx, [rsp+148h+lpFileName]
0x18003a2e6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003a2eb  mov     rsi, [rsp+148h+lpFileName]
0x18003a2f0  cmp     [rsi-10h], r14d
0x18003a2f4  jz      short loc_18003A347
0x18003a2f6  mov     rcx, rsi; lpFileName
0x18003a2f9  call    ?TryAccessFileS@Impl@WindowsPerformanceRecorder@@YAJPEBGK@Z; WindowsPerformanceRecorder::Impl::TryAccessFileS(ushort const *,ulong)
0x18003a2fe  mov     ebx, eax
0x18003a300  test    eax, eax
0x18003a302  jns     short loc_18003A347
0x18003a304  lea     rcx, aComguard; "COMGUARD"
0x18003a30b  mov     [rsp+148h+Format], rcx; Format
0x18003a310  mov     r9d, eax; unsigned int
0x18003a313  mov     r8d, 4BCh; char *
0x18003a319  lea     rdx, aSave; "Save"
0x18003a320  mov     ecx, 2; this
0x18003a325  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003a32a  nop
0x18003a32b  lea     rcx, [rsp+148h+lpFileName]; this
0x18003a330  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003a335  nop
0x18003a336  lea     rcx, [rsp+148h+var_E0]; this
0x18003a33b  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18003a340  mov     eax, ebx
0x18003a342  jmp     loc_18003AF40
0x18003a347  lea     rax, off_180090518
0x18003a34e  mov     [rsp+148h+var_C8], rax
0x18003a356  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 4
0x18003a35d  jz      short loc_18003A376
0x18003a35f  mov     r8, rsi
0x18003a362  lea     rdx, Perf_SaveProfiles_Begin
0x18003a369  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18003a370  call    McTemplateU0z_EventWriteTransfer
0x18003a375  nop
0x18003a376  mov     [rsp+148h+var_A0], r13
0x18003a37e  mov     rcx, r13; this
0x18003a381  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x18003a386  test    eax, eax
0x18003a388  jnz     loc_18003AEFC
0x18003a38e  mov     edi, [r12+180h]
0x18003a396  test    dil, 1
0x18003a39a  jz      short loc_18003A3A3
0x18003a39c  mov     byte ptr [rsp+148h+var_108], r14b
0x18003a3a1  jmp     short loc_18003A3B7
0x18003a3a3  test    dil, 8
0x18003a3a7  jz      loc_18003AEE6
0x18003a3ad  shr     edi, 1
0x18003a3af  and     dil, 1
0x18003a3b3  mov     dword ptr [rsp+148h+var_108], edi
0x18003a3b7  mov     rbx, r14
0x18003a3ba  mov     [rsp+148h+var_D8], rbx
0x18003a3bf  mov     [rsp+148h+var_100], r14
0x18003a3c4  mov     [rsp+148h+var_E8], r14d
0x18003a3c9  mov     rcx, r13; this
0x18003a3cc  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x18003a3d1  mov     r15d, eax
0x18003a3d4  lea     rdx, [r12+158h]
0x18003a3dc  lea     rcx, [r12+160h]
0x18003a3e4  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18003a3e9  mov     edx, [r12+180h]
0x18003a3f1  mov     rcx, r13
0x18003a3f4  call    ?SetTemporaryTraceDirectoryToCurrentTracingDirectory@CControlManager@WindowsPerformanceRecorder@@AEAAXUCTraceType@IControlInfo@Status@2@@Z; WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(WindowsPerformanceRecorder::Status::IControlInfo::CTraceType)
0x18003a3f9  test    r15d, r15d
0x18003a3fc  js      loc_18003A4CC
0x18003a402  mov     ecx, 1A8h; Size
0x18003a407  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a40c  mov     [rsp+148h+var_80], rax
0x18003a414  mov     rcx, rax; this
0x18003a417  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18003a41c  mov     rbx, rax
0x18003a41f  mov     [rsp+148h+var_D8], rax
0x18003a424  mov     r9d, [r12+180h]
0x18003a42c  shr     r9d, 4
0x18003a430  and     r9b, 1; bool
0x18003a434  mov     r8, r13; struct WindowsPerformanceRecorder::CControlManager *
0x18003a437  mov     rdx, [rsp+148h+var_88]; struct IProfileCollection *
0x18003a43f  mov     rcx, rax; this
0x18003a442  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18003a447  mov     r15d, eax
0x18003a44a  test    eax, eax
0x18003a44c  js      short loc_18003A4CC
0x18003a44e  mov     rdi, [rbx+140h]
0x18003a455  mov     [rsp+148h+var_100], rdi
0x18003a45a  mov     r8, rdi; char *
0x18003a45d  lea     rdx, aSave; "Save"
0x18003a464  mov     ecx, 2000h; this
0x18003a469  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x18003a46e  mov     ecx, [rbx+100h]
0x18003a474  sub     ecx, 1
0x18003a477  jz      short loc_18003A486
0x18003a479  cmp     ecx, 1
0x18003a47c  jz      short loc_18003A486
0x18003a47e  mov     r15d, 0C558500Ah
0x18003a484  jmp     short loc_18003A4CC
0x18003a486  test    byte ptr [r12+180h], 8
0x18003a48f  jnz     short loc_18003A4A6
0x18003a491  xor     r8d, r8d; bool
0x18003a494  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18003a497  mov     rcx, r13; this
0x18003a49a  call    ?ValidateWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18003a49f  mov     r15d, eax
0x18003a4a2  test    eax, eax
0x18003a4a4  js      short loc_18003A4CC
0x18003a4a6  xor     r8d, r8d; bool
0x18003a4a9  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18003a4ac  mov     rcx, r13; this
0x18003a4af  call    ?ValidateWithRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18003a4b4  mov     r15d, eax
0x18003a4b7  test    eax, eax
0x18003a4b9  js      short loc_18003A4CC
0x18003a4bb  mov     r9b, 1; bool
0x18003a4be  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18003a4c1  mov     rcx, r13; this
0x18003a4c4  call    ?SetProgressHandlerRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N1@Z; WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool,bool)
0x18003a4c9  mov     r15d, eax
0x18003a4cc  mov     rcx, rbx; this
0x18003a4cf  call    ?SortEventSessionsByType@CETWProperties@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CETWProperties::SortEventSessionsByType(void)
0x18003a4d4  mov     [rsp+148h+var_B8], r13
0x18003a4dc  mov     [rsp+148h+var_B0], r14
0x18003a4e4  mov     [rsp+148h+var_A8], r14b
0x18003a4ec  test    r15d, r15d
0x18003a4ef  js      loc_18003AC49
0x18003a4f5  lea     r8, [rsp+148h+var_B0]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession **
0x18003a4fd  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18003a500  mov     rcx, r13; this
0x18003a503  call    ?CreateMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBVCETWProperties@2@PEAPEAUCEventSession@32@@Z; WindowsPerformanceRecorder::CControlManager::CreateMarkSession(WindowsPerformanceRecorder::CETWProperties const &,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)
0x18003a508  mov     edi, eax
0x18003a50a  test    eax, eax
0x18003a50c  jns     short loc_18003A58A
0x18003a50e  lea     rcx, aComguard; "COMGUARD"
0x18003a515  mov     [rsp+148h+Format], rcx; Format
0x18003a51a  mov     r9d, eax; unsigned int
0x18003a51d  mov     r8d, 526h; char *
0x18003a523  lea     rdx, aSave; "Save"
0x18003a52a  mov     ecx, 2; this
0x18003a52f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003a534  nop
0x18003a535  lea     rcx, [rsp+148h+var_B8]; this
0x18003a53d  call    ?Cleanup@CMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAXXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup(void)
0x18003a542  nop
0x18003a543  test    rbx, rbx
0x18003a546  jz      short loc_18003A55B
0x18003a548  mov     rax, [rbx]
0x18003a54b  mov     edx, 1
0x18003a550  mov     rcx, rbx
0x18003a553  mov     rax, [rax]
0x18003a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a55b  mov     [rsp+148h+var_D8], r14
0x18003a560  lea     rcx, [rsp+148h+var_C8]
0x18003a568  call    _WindowsPerformanceRecorder__CControlManager__Save____2___CPerfEventMacro___CPerfEventMacro
0x18003a56d  nop
0x18003a56e  lea     rcx, [rsp+148h+lpFileName]; this
0x18003a573  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003a578  nop
0x18003a579  lea     rcx, [rsp+148h+var_E0]; this
0x18003a57e  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18003a583  mov     eax, edi
0x18003a585  jmp     loc_18003AF40
0x18003a58a  lea     rcx, [rsp+148h+var_B8]; this
0x18003a592  call    ?Start@CMarkSession@CControlManager@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Start(void)
0x18003a597  mov     edi, eax
0x18003a599  test    eax, eax
0x18003a59b  jns     short loc_18003A619
0x18003a59d  lea     rcx, aComguard; "COMGUARD"
0x18003a5a4  mov     [rsp+148h+Format], rcx; Format
0x18003a5a9  mov     r9d, eax; unsigned int
0x18003a5ac  mov     r8d, 527h; char *
0x18003a5b2  lea     rdx, aSave; "Save"
0x18003a5b9  mov     ecx, 2; this
0x18003a5be  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003a5c3  nop
0x18003a5c4  lea     rcx, [rsp+148h+var_B8]; this
0x18003a5cc  call    ?Cleanup@CMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAXXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup(void)
0x18003a5d1  nop
0x18003a5d2  test    rbx, rbx
0x18003a5d5  jz      short loc_18003A5EA
0x18003a5d7  mov     rax, [rbx]
0x18003a5da  mov     edx, 1
0x18003a5df  mov     rcx, rbx
0x18003a5e2  mov     rax, [rax]
0x18003a5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5ea  mov     [rsp+148h+var_D8], r14
0x18003a5ef  lea     rcx, [rsp+148h+var_C8]
0x18003a5f7  call    _WindowsPerformanceRecorder__CControlManager__Save____2___CPerfEventMacro___CPerfEventMacro
0x18003a5fc  nop
0x18003a5fd  lea     rcx, [rsp+148h+lpFileName]; this
0x18003a602  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003a607  nop
0x18003a608  lea     rcx, [rsp+148h+var_E0]; this
0x18003a60d  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18003a612  mov     eax, edi
0x18003a614  jmp     loc_18003AF40
0x18003a619  lea     r8, aWprInitiatedRu; "Wpr_Initiated_Rundown"
0x18003a620  mov     rdx, [rsp+148h+var_B0]
0x18003a628  mov     rdx, [rdx+70h]; unsigned __int64
0x18003a62c  call    ?LogMark@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KPEBG@Z; WindowsPerformanceRecorder::CControlManager::LogMark(unsigned __int64,ushort const *)
0x18003a631  xorps   xmm0, xmm0
0x18003a634  movups  [rsp+148h+var_70], xmm0
0x18003a63c  movups  [rsp+148h+var_60], xmm0
0x18003a644  mov     [rsp+148h+var_D0], r14
0x18003a649  mov     rdi, r14
0x18003a64c  mov     [rsp+148h+Block], r14
0x18003a651  mov     rax, [rbx+8]
0x18003a655  cmp     rax, [rbx+10h]
0x18003a659  jz      loc_18003A859
0x18003a65f  mov     r12, [rax]
0x18003a662  cmp     dword ptr [r12], 1
0x18003a667  jnz     loc_18003AA2A
0x18003a66d  xorps   xmm0, xmm0
0x18003a670  movups  [rsp+148h+var_70], xmm0
0x18003a678  movups  [rsp+148h+var_60], xmm0
0x18003a680  mov     edx, 2
0x18003a685  mov     rcx, r12
0x18003a688  call    ?HasSystemKeywordType@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBA_NW4SystemKeywordType@3@@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(WindowsPerformanceRecorder::SystemKeywordType)
0x18003a68d  test    al, al
0x18003a68f  jz      short loc_18003A69C
0x18003a691  mov     r8d, edx
0x18003a694  mov     rdx, r12
0x18003a697  call    ?CaptureStateRundown@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAUCEventSession@CETWProperties@2@W4SystemKeywordType@2@@Z; WindowsPerformanceRecorder::CControlManager::CaptureStateRundown(WindowsPerformanceRecorder::CETWProperties::CEventSession &,WindowsPerformanceRecorder::SystemKeywordType)
0x18003a69c  cmp     [r12+0CFh], r14b
0x18003a6a4  jz      loc_18003A859
0x18003a6aa  lea     rax, [rsp+148h+var_D0]
0x18003a6af  mov     [rsp+148h+Format], rax
0x18003a6b4  lea     r9, [rsp+148h+Block]
0x18003a6b9  lea     r8, [rsp+148h+var_70]
0x18003a6c1  mov     rdx, r12
0x18003a6c4  call    ?DisableHighVolumeSystemFlags@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAUCEventSession@CETWProperties@2@AEAU_PERFINFO_GROUPMASK@@AEAV?$CHeapPtr@KVCCRTAllocator@ATL@@@ATL@@AEA_K@Z; WindowsPerformanceRecorder::CControlManager::DisableHighVolumeSystemFlags(WindowsPerformanceRecorder::CETWProperties::CEventSession &,_PERFINFO_GROUPMASK &,ATL::CHeapPtr<ulong,ATL::CCRTAllocator> &,unsigned __int64 &)
0x18003a6c9  mov     edi, eax
0x18003a6cb  test    eax, eax
0x18003a6cd  jns     short loc_18003A72D
0x18003a6cf  mov     rcx, r12; this
0x18003a6d2  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003a6d7  mov     r9, rax; unsigned __int16 *
0x18003a6da  mov     [rsp+148h+var_120], r14; struct IControlErrorInfo *
0x18003a6df  mov     r15, [rsp+148h+var_100]
0x18003a6e4  mov     [rsp+148h+Format], r15; unsigned __int16 *
0x18003a6e9  mov     edx, edi; int
0x18003a6eb  mov     rcx, r13; this
0x18003a6ee  call    ?AddCollectorControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBG1PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(long,_GUID const &,ushort const *,ushort const *,IControlErrorInfo *)
  ... truncated ...
```
