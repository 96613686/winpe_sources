# WinREAgent::WinREServicingManager::InternalLoad(ushort)

- ea: `0x180019b84`
- end: `0x18001a715`
- name: `?InternalLoad@WinREServicingManager@WinREAgent@@AEAAJG@Z`
- size: `2961`
- prototype: `__int64 __fastcall(WinREAgent::WinREServicingManager *__hidden this, unsigned __int16)`
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001b044`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cb0`
- `0x180005cc0`
- `0x1800089d0`
- `0x18000b75c`
- `0x18000d6f0`
- `0x18000d800`
- `0x18000d92c`
- `0x18001586c`
- `0x180019b84`
- `0x18001b1e0`
- `0x18001f194`
- `0x18001f358`
- `0x18002da30`
- `0x18002ec64`
- `0x18003717c`
- `0x180037344`
- `0x18004bb04`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x1800520a4`
- `0x180052194`
- `0x1800522e8`
- `0x180052400`
- `0x180052528`
- `0x1800528fc`
- `0x18006c652`
- `0x18006f010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18001a229`
- `KERNEL32!WideCharToMultiByte` at `0x18001a33e`
- `KERNEL32!WideCharToMultiByte` at `0x18001a229`
- `KERNEL32!WideCharToMultiByte` at `0x18001a33e`
- `KERNEL32!GetLastError` at `0x18001a23a`
- `KERNEL32!GetLastError` at `0x18001a281`
- `KERNEL32!GetLastError` at `0x18001a348`
- `KERNEL32!GetLastError` at `0x18001a38f`
- `KERNEL32!GetLastError` at `0x18001a23a`
- `KERNEL32!GetLastError` at `0x18001a281`
- `KERNEL32!GetLastError` at `0x18001a348`
- `KERNEL32!GetLastError` at `0x18001a38f`
- `KERNEL32!HeapAlloc` at `0x18001a2e1`
- `KERNEL32!HeapAlloc` at `0x18001a2e1`
- `KERNEL32!GetProcessHeap` at `0x18001a2d3`
- `KERNEL32!GetProcessHeap` at `0x18001a2d3`

## string_xrefs

- `0x180019d44`: `Failed to get suspend file path`
- `0x180019bf7`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019c90`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019d00`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019d58`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019da1`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019e19`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019eb4`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019f45`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a267`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a375`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a418`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a582`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a5f9`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001a664`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x180019be3`: `Failed to create log directory path`
- `0x180019c7c`: `Failed to create dir [%s]`
- `0x18001a04b`: `Scheduled`
- `0x180019bfe`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019c97`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019d07`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019d5f`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019da8`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019e20`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019ebb`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x180019f4c`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a26e`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a37c`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a41f`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a589`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a600`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a66b`: `WinREAgent::WinREServicingManager::InternalLoad`
- `0x18001a07f`: `Failed to load Scheduled state`
- `0x18001a4fb`: `Exit WinREAgent::WinREServicingManager::InternalLoad`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WinREAgent::WinREServicingManager::InternalLoad(
        WinREAgent::WinREServicingManager *this,
        unsigned __int16 a2)
{
  unsigned int v2; // ebx
  int LogDir; // ebx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  signed int Root; // edi
  __int64 v10; // rbx
  ATL::CStringData *v11; // rcx
  PushButtonReset::SerializeDocument *v12; // rbx
  struct PushButtonReset::SerializeNode **v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  PushButtonReset::SerializeNode *v19; // rbx
  struct PushButtonReset::SerializeNode **v20; // rax
  struct WinREAgent::Executor **v21; // rbx
  struct PushButtonReset::SerializeNode *v22; // rax
  __int64 v23; // rbx
  int Property; // esi
  const WCHAR *v25; // rbx
  int v26; // eax
  SIZE_T cbMultiByte; // rsi
  signed int LastError; // eax
  signed int v29; // eax
  HANDLE ProcessHeap; // rax
  void *v31; // rax
  CHAR *lpMultiByteStr; // rax
  signed int v33; // eax
  signed int v34; // eax
  char *v35; // rsi
  struct WinREAgent::TelemetrySession **v36; // rdi
  const char *v37; // rax
  unsigned int v38; // edi
  WinREAgent::TelemetrySession *v39; // rax
  const unsigned __int16 *v40; // [rsp+40h] [rbp-39h] BYREF
  __int64 v41; // [rsp+48h] [rbp-31h] BYREF
  LPCWCH lpWideCharStr; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v43[2]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v44[2]; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v45[2]; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v46[9]; // [rsp+88h] [rbp+Fh] BYREF
  unsigned int v47; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v48; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v49; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v41);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v41,
    L"%c:\\",
    v2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v40);
  LogDir = WinREAgent::WorkDir::GetLogDir((__int64)&v41, (__int64)&v40);
  if ( LogDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LogDir,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1146,
      L"Failed to create log directory path");
LABEL_3:
    ATL::CStringData::Release((ATL::CStringData *)(v40 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
    return (unsigned int)LogDir;
  }
  if ( !(unsigned __int8)PushButtonReset::Directory::Exists(&v40) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v48,
      (__int64)&pszFormat);
    LogDir = PushButtonReset::Directory::Create(&v40, 0, &v48);
    ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::InternalLoad",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1151,
        L"Failed to create dir [%s]",
        v40);
      goto LABEL_3;
    }
  }
  LOBYTE(v47) = 0;
  v6 = PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &,bool>(
         &v40,
         (bool *)&v47);
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, v6);
  if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1155,
      L"Failed to allocate m_logAutoRelease");
LABEL_9:
    LogDir = -2147024882;
    goto LABEL_3;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v49);
  LogDir = WinREAgent::WorkDir::GetSuspendFile(&v41, &v49);
  if ( LogDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LogDir,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1160,
      L"Failed to get suspend file path");
LABEL_62:
    ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
    goto LABEL_3;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists(&v49) )
  {
    v7 = v49;
    PushButtonReset::Logging::TraceErr(
      2,
      2147943568LL,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1166,
      L"[%s] doesn't exist, there is no servicing manager suspended",
      v49);
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
    LogDir = -2147023728;
    goto LABEL_3;
  }
  v44[1] = 0;
  v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
  v8 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v44);
  Root = PushButtonReset::SerializeDocument::Load(&v49, v8);
  if ( Root < 0 )
  {
    v10 = v49;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1172,
      L"Failed to load [%s]",
      v49);
LABEL_16:
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
    v11 = (ATL::CStringData *)(v10 - 24);
LABEL_17:
    ATL::CStringData::Release(v11);
    LogDir = Root;
    goto LABEL_3;
  }
  v43[1] = 0;
  v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  v12 = (PushButtonReset::SerializeDocument *)(*(__int64 (__fastcall **)(_QWORD *))(v44[0] + 24LL))(v44);
  v13 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 8LL))(v43);
  Root = PushButtonReset::SerializeDocument::GetRoot(v12, v13);
  if ( Root < 0 )
  {
    v10 = v49;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1177,
      L"Failed to get root node from [%s]",
      v49);
    v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
    goto LABEL_16;
  }
  LODWORD(v48) = 0;
  v47 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&lpWideCharStr,
    (__int64)L"MajorVersion");
  LogDir = PushButtonReset::SerializeNode::GetProperty(v14, &lpWideCharStr, &v48);
  ATL::CStringData::Release((ATL::CStringData *)(lpWideCharStr - 12));
  if ( LogDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LogDir,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1182,
      L"Failed to load MajorVersion");
    goto LABEL_61;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&lpWideCharStr,
    (__int64)L"MinorVersion");
  LogDir = PushButtonReset::SerializeNode::GetProperty(v15, &lpWideCharStr, &v47);
  ATL::CStringData::Release((ATL::CStringData *)(lpWideCharStr - 12));
  if ( LogDir < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LogDir,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1185,
      L"Failed to load MinorVersion");
LABEL_61:
    v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
    goto LABEL_62;
  }
  if ( (_DWORD)v48 == 1 && v47 == 4 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v48,
      (__int64)L"TargetRoot");
    LogDir = PushButtonReset::SerializeNode::GetProperty(v16, &v48, (char *)this + 56);
    ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::InternalLoad",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1199,
        L"Failed to Load Target root");
      goto LABEL_61;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v48,
      (__int64)L"Scheduled");
    LogDir = PushButtonReset::SerializeNode::GetProperty(v17, &v48, (char *)this + 65);
    ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::InternalLoad",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1202,
        L"Failed to load Scheduled state");
      goto LABEL_61;
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v48,
      (__int64)L"Staged");
    LogDir = PushButtonReset::SerializeNode::GetProperty(v18, &v48, (char *)this + 66);
    ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::InternalLoad",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1205,
        L"Failed to load Staged state");
      goto LABEL_61;
    }
    (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 5) + 48LL))((char *)this + 40, 0);
    v45[1] = 0;
    v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    v19 = (PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
    v20 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 8LL))(v45);
    LogDir = PushButtonReset::SerializeNode::SelectChild(v19, v20, L"Executor");
    if ( LogDir < 0 )
    {
      if ( LogDir != -2147023728 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1221,
          L"Failed to look up node for Executor");
        goto LABEL_60;
      }
    }
    else
    {
      v21 = (struct WinREAgent::Executor **)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 8LL))((char *)this + 40);
      v22 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 32LL))(v45);
      LogDir = WinREAgent::Executor::Load(v22, v21);
      if ( LogDir < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1213,
          L"Failed to Executor");
LABEL_60:
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v45);
        goto LABEL_61;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpWideCharStr);
    v23 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 24LL))(v43);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v48,
      (__int64)L"CVString");
    Property = PushButtonReset::SerializeNode::GetProperty(v23, &v48, &lpWideCharStr);
    ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
    v25 = lpWideCharStr;
    if ( Property < 0 )
    {
      if ( Property != -2147023728 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Property,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1257,
          L"Failed to look up node for CV");
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v45);
        v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
        v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
        ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
        LogDir = Property;
        goto LABEL_3;
      }
      v38 = 0;
      PushButtonReset::Logging::Trace(0, L"There is no CV saved, skip resuming telemetry");
      v35 = (char *)this + 24;
    }
    else
    {
      v26 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, 0, 0, 0, 0);
      cbMultiByte = v26;
      if ( !v26 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1234,
          L"Failed to get UTF-8 length for CV string [%s]",
          v25);
        v29 = GetLastError();
        Root = v29;
        if ( v29 > 0 )
          Root = (unsigned __int16)v29 | 0x80070000;
LABEL_43:
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v45);
        v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
        v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
        v11 = (ATL::CStringData *)(v49 - 24);
        goto LABEL_17;
      }
      ProcessHeap = GetProcessHeap();
      v46[1] = HeapAlloc(ProcessHeap, 0, cbMultiByte);
      v46[0] = &RAII::CAutoPbrHeapFree<char *>::`vftable';
      v31 = (void *)RAII::CAutoCleanupBase<void *>::operator->(v46);
      memset_0(v31, 0, cbMultiByte);
      lpMultiByteStr = (CHAR *)(*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 32LL))(v46);
      if ( !WideCharToMultiByte(0xFDE9u, 0, v25, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
      {
        v33 = GetLastError();
        if ( v33 > 0 )
          v33 = (unsigned __int16)v33 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v33,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1244,
          L"Failed to get UTF-8 value for CV string [%s]",
          v25);
        v34 = GetLastError();
        Root = v34;
        if ( v34 > 0 )
          Root = (unsigned __int16)v34 | 0x80070000;
        v46[0] = &RAII::CAutoPbrHeapFree<char *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v46);
        goto LABEL_43;
      }
      v35 = (char *)this + 24;
      v36 = (struct WinREAgent::TelemetrySession **)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 8LL))((char *)this + 24);
      v37 = (const char *)(*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 32LL))(v46);
      v38 = WinREAgent::TelemetrySession::Create(v37, v36);
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 72LL))((char *)this + 24) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::WinREServicingManager::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1248,
          L"Failed to allocate m_telemetry");
        v46[0] = &RAII::CAutoPbrHeapFree<char *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v46);
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v45);
        v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
        v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
        ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
        goto LABEL_9;
      }
      v46[0] = &RAII::CAutoPbrHeapFree<char *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v46);
    }
    *((_BYTE *)this + 64) = 1;
    v48 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64 *))(*(_QWORD *)v35 + 64LL))(v35, &v48) )
    {
      v39 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v35 + 24LL))(v35);
      WinREAgent::TelemetrySession::TraceSessionLoaded(v39);
    }
    PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::InternalLoad");
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
    v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v45);
    v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
    ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v40 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
    return v38;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943705LL,
      "WinREAgent::WinREServicingManager::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1190,
      L"Version mismatch, saved Servicing manager is in a different version");
    PushButtonReset::Logging::Trace(0, L"  Expected : [%u.%u]", 1);
    PushButtonReset::Logging::Trace(0, L"       Get : [%u.%u]", (unsigned int)v48, v47);
    v43[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v43);
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v44);
    ATL::CStringData::Release((ATL::CStringData *)(v49 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v40 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
    return 2147943705LL;
  }
}

```

## disassembly

```asm
0x180019b84  mov     [rsp-8+arg_0], rbx
0x180019b89  push    rbp
0x180019b8a  push    rsi
0x180019b8b  push    rdi
0x180019b8c  push    r12
0x180019b8e  push    r13
0x180019b90  push    r14
0x180019b92  push    r15
0x180019b94  lea     rbp, [rsp-27h]
0x180019b99  sub     rsp, 0A0h
0x180019ba0  movzx   ebx, dx
0x180019ba3  mov     r14, rcx
0x180019ba6  lea     rcx, [rbp+57h+var_88]
0x180019baa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019baf  nop
0x180019bb0  mov     r8d, ebx
0x180019bb3  lea     rdx, aC; "%c:\\"
0x180019bba  lea     rcx, [rbp+57h+var_88]
0x180019bbe  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180019bc3  lea     rcx, [rbp+57h+var_90]
0x180019bc7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019bcc  nop
0x180019bcd  lea     rdx, [rbp+57h+var_90]
0x180019bd1  lea     rcx, [rbp+57h+var_88]
0x180019bd5  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180019bda  mov     ebx, eax
0x180019bdc  xor     r15d, r15d
0x180019bdf  test    eax, eax
0x180019be1  jns     short loc_180019C33
0x180019be3  lea     rax, aFailedToCreate_44; "Failed to create log directory path"
0x180019bea  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019bef  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 47Ah
0x180019bf7  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019bfe  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019c05  mov     edx, ebx
0x180019c07  lea     ecx, [r15+2]
0x180019c0b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019c10  nop
0x180019c11  mov     rcx, [rbp+57h+var_90]
0x180019c15  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019c19  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019c1e  nop
0x180019c1f  mov     rcx, [rbp+57h+var_88]
0x180019c23  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019c27  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019c2c  mov     eax, ebx
0x180019c2e  jmp     loc_18001A6FA
0x180019c33  lea     rcx, [rbp+57h+var_90]
0x180019c37  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180019c3c  test    al, al
0x180019c3e  jnz     short loc_180019CAF
0x180019c40  lea     rdx, pszFormat
0x180019c47  lea     rcx, [rbp+57h+arg_10]
0x180019c4b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019c50  nop
0x180019c51  lea     r8, [rbp+57h+arg_10]
0x180019c55  xor     edx, edx
0x180019c57  lea     rcx, [rbp+57h+var_90]
0x180019c5b  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180019c60  mov     ebx, eax
0x180019c62  mov     rcx, [rbp+57h+arg_10]
0x180019c66  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019c6a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019c6f  test    ebx, ebx
0x180019c71  jns     short loc_180019CAF
0x180019c73  mov     rcx, [rbp+57h+var_90]
0x180019c77  mov     [rsp+0D0h+lpDefaultChar], rcx
0x180019c7c  lea     rax, aFailedToCreate_24; "Failed to create dir [%s]"
0x180019c83  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019c88  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 47Fh
0x180019c90  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019c97  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019c9e  mov     edx, ebx
0x180019ca0  mov     ecx, 2
0x180019ca5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019caa  jmp     loc_180019C11
0x180019caf  mov     byte ptr [rbp+57h+arg_8], r15b
0x180019cb3  lea     rdx, [rbp+57h+arg_8]
0x180019cb7  lea     rcx, [rbp+57h+var_90]
0x180019cbb  call    ??$PbrNew@VLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@@YAPEAVLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEA_N@Z; PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &&)
0x180019cc0  mov     r8, rax
0x180019cc3  lea     rbx, [r14+8]
0x180019cc7  mov     rdx, [rbx]
0x180019cca  mov     rax, [rdx+30h]
0x180019cce  mov     rdx, r8
0x180019cd1  mov     rcx, rbx
0x180019cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cd9  mov     rax, [rbx]
0x180019cdc  mov     rcx, rbx
0x180019cdf  mov     rax, [rax+48h]
0x180019ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ce8  test    al, al
0x180019cea  jz      short loc_180019D27
0x180019cec  lea     rax, aFailedToAlloca_15; "Failed to allocate m_logAutoRelease"
0x180019cf3  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019cf8  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 483h
0x180019d00  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019d07  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019d0e  mov     edx, 8007000Eh
0x180019d13  mov     ecx, 2
0x180019d18  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019d1d  mov     ebx, 8007000Eh
0x180019d22  jmp     loc_180019C11
0x180019d27  lea     rcx, [rbp+57h+arg_18]
0x180019d2b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019d30  nop
0x180019d31  lea     rdx, [rbp+57h+arg_18]
0x180019d35  lea     rcx, [rbp+57h+var_88]
0x180019d39  call    ?GetSuspendFile@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetSuspendFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180019d3e  mov     ebx, eax
0x180019d40  test    eax, eax
0x180019d42  jns     short loc_180019D77
0x180019d44  lea     rax, aFailedToGetSus; "Failed to get suspend file path"
0x180019d4b  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019d50  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 488h
0x180019d58  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019d5f  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019d66  mov     edx, ebx
0x180019d68  mov     ecx, 2
0x180019d6d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019d72  jmp     loc_18001A63E
0x180019d77  lea     rcx, [rbp+57h+arg_18]
0x180019d7b  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180019d80  test    al, al
0x180019d82  jnz     short loc_180019DD2
0x180019d84  mov     rbx, [rbp+57h+arg_18]
0x180019d88  mov     [rsp+0D0h+lpDefaultChar], rbx
0x180019d8d  lea     rax, aSDoesnTExistTh; "[%s] doesn't exist, there is no servici"...
0x180019d94  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019d99  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 48Eh
0x180019da1  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019da8  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019daf  mov     edx, 80070490h
0x180019db4  mov     ecx, 2
0x180019db9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019dbe  nop
0x180019dbf  lea     rcx, [rbx-18h]; this
0x180019dc3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019dc8  mov     ebx, 80070490h
0x180019dcd  jmp     loc_180019C11
0x180019dd2  mov     [rbp+57h+var_60], r15
0x180019dd6  lea     r13, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x180019ddd  mov     [rbp+57h+var_68], r13
0x180019de1  lea     rcx, [rbp+57h+var_68]
0x180019de5  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180019dea  mov     rdx, rax
0x180019ded  lea     rcx, [rbp+57h+arg_18]
0x180019df1  call    ?Load@SerializeDocument@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeDocument::Load(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeDocument * *)
0x180019df6  mov     edi, eax
0x180019df8  test    eax, eax
0x180019dfa  jns     short loc_180019E52
0x180019dfc  mov     rbx, [rbp+57h+arg_18]
0x180019e00  mov     [rsp+0D0h+lpDefaultChar], rbx
0x180019e05  lea     rax, aFailedToLoadS; "Failed to load [%s]"
0x180019e0c  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019e11  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 494h
0x180019e19  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019e20  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019e27  mov     edx, edi
0x180019e29  mov     ecx, 2
0x180019e2e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019e33  nop
0x180019e34  mov     [rbp+57h+var_68], r13
0x180019e38  lea     rcx, [rbp+57h+var_68]
0x180019e3c  call    ?Release@?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(void)
0x180019e41  nop
0x180019e42  lea     rcx, [rbx-18h]; this
0x180019e46  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019e4b  mov     ebx, edi
0x180019e4d  jmp     loc_180019C11
0x180019e52  mov     [rbp+57h+var_70], r15
0x180019e56  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x180019e5d  mov     [rbp+57h+var_78], r12
0x180019e61  mov     rax, [rbp+57h+var_68]
0x180019e65  lea     rcx, [rbp+57h+var_68]
0x180019e69  mov     rax, [rax+18h]
0x180019e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e72  mov     rbx, rax
0x180019e75  mov     rcx, [rbp+57h+var_78]
0x180019e79  mov     rax, [rcx+8]
0x180019e7d  lea     rcx, [rbp+57h+var_78]
0x180019e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e86  mov     rdx, rax; struct PushButtonReset::SerializeNode **
0x180019e89  mov     rcx, rbx; this
0x180019e8c  call    ?GetRoot@SerializeDocument@PushButtonReset@@QEAAJPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeDocument::GetRoot(PushButtonReset::SerializeNode * *)
0x180019e91  mov     edi, eax
0x180019e93  test    eax, eax
0x180019e95  jns     short loc_180019EE1
0x180019e97  mov     rbx, [rbp+57h+arg_18]
0x180019e9b  mov     [rsp+0D0h+lpDefaultChar], rbx
0x180019ea0  lea     rax, aFailedToGetRoo_2; "Failed to get root node from [%s]"
0x180019ea7  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019eac  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 499h
0x180019eb4  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019ebb  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019ec2  mov     edx, edi
0x180019ec4  mov     ecx, 2
0x180019ec9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019ece  nop
0x180019ecf  mov     [rbp+57h+var_78], r12
0x180019ed3  lea     rcx, [rbp+57h+var_78]
0x180019ed7  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180019edc  jmp     loc_180019E34
0x180019ee1  mov     dword ptr [rbp+57h+arg_10], r15d
0x180019ee5  mov     [rbp+57h+arg_8], r15d
0x180019ee9  mov     rax, [rbp+57h+var_78]
0x180019eed  lea     rcx, [rbp+57h+var_78]
0x180019ef1  mov     rax, [rax+18h]
0x180019ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019efa  mov     rbx, rax
0x180019efd  lea     rdx, aMajorversion; "MajorVersion"
0x180019f04  lea     rcx, [rbp+57h+lpWideCharStr]
0x180019f08  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019f0d  nop
0x180019f0e  lea     r8, [rbp+57h+arg_10]
0x180019f12  lea     rdx, [rbp+57h+lpWideCharStr]
0x180019f16  mov     rcx, rbx
0x180019f19  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAK@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *)
0x180019f1e  mov     ebx, eax
0x180019f20  mov     rcx, [rbp+57h+lpWideCharStr]
0x180019f24  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019f28  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019f2d  test    ebx, ebx
0x180019f2f  jns     short loc_180019F64
0x180019f31  lea     rax, aFailedToLoadMa; "Failed to load MajorVersion"
0x180019f38  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019f3d  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 49Eh
0x180019f45  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180019f4c  lea     r8, aWinreagentWinr_14; "WinREAgent::WinREServicingManager::Inte"...
0x180019f53  mov     edx, ebx
0x180019f55  mov     ecx, 2
0x180019f5a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180019f5f  jmp     loc_18001A622
0x180019f64  mov     rax, [rbp+57h+var_78]
0x180019f68  lea     rcx, [rbp+57h+var_78]
0x180019f6c  mov     rax, [rax+18h]
0x180019f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f75  mov     rbx, rax
0x180019f78  lea     rdx, aMinorversion; "MinorVersion"
0x180019f7f  lea     rcx, [rbp+57h+lpWideCharStr]
0x180019f83  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019f88  nop
0x180019f89  lea     r8, [rbp+57h+arg_8]
0x180019f8d  lea     rdx, [rbp+57h+lpWideCharStr]
0x180019f91  mov     rcx, rbx
0x180019f94  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAK@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *)
0x180019f99  mov     ebx, eax
0x180019f9b  mov     rcx, [rbp+57h+lpWideCharStr]
0x180019f9f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019fa3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019fa8  test    ebx, ebx
0x180019faa  jns     short loc_180019FC2
0x180019fac  lea     rax, aFailedToLoadMi; "Failed to load MinorVersion"
0x180019fb3  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x180019fb8  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 4A1h
0x180019fc0  jmp     short loc_180019F45
0x180019fc2  cmp     dword ptr [rbp+57h+arg_10], 1
0x180019fc6  jnz     loc_18001A650
0x180019fcc  cmp     [rbp+57h+arg_8], 4
0x180019fd0  jnz     loc_18001A650
0x180019fd6  mov     rax, [rbp+57h+var_78]
0x180019fda  lea     rcx, [rbp+57h+var_78]
0x180019fde  mov     rax, [rax+18h]
0x180019fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fe7  mov     rbx, rax
0x180019fea  lea     rdx, aTargetroot; "TargetRoot"
0x180019ff1  lea     rcx, [rbp+57h+arg_10]
0x180019ff5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180019ffa  nop
0x180019ffb  lea     r8, [r14+38h]
0x180019fff  lea     rdx, [rbp+57h+arg_10]
0x18001a003  mov     rcx, rbx
0x18001a006  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001a00b  mov     ebx, eax
0x18001a00d  mov     rcx, [rbp+57h+arg_10]
0x18001a011  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a015  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a01a  test    ebx, ebx
0x18001a01c  jns     short loc_18001A037
0x18001a01e  lea     rax, aFailedToLoadTa; "Failed to Load Target root"
0x18001a025  mov     qword ptr [rsp+0D0h+cbMultiByte], rax
0x18001a02a  mov     dword ptr [rsp+0D0h+lpMultiByteStr], 4AFh
0x18001a032  jmp     loc_180019F45
0x18001a037  mov     rax, [rbp+57h+var_78]
0x18001a03b  lea     rcx, [rbp+57h+var_78]
0x18001a03f  mov     rax, [rax+18h]
0x18001a043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a048  mov     rbx, rax
0x18001a04b  lea     rdx, aScheduled; "Scheduled"
0x18001a052  lea     rcx, [rbp+57h+arg_10]
0x18001a056  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001a05b  nop
0x18001a05c  lea     r8, [r14+41h]
0x18001a060  lea     rdx, [rbp+57h+arg_10]
0x18001a064  mov     rcx, rbx
0x18001a067  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x18001a06c  mov     ebx, eax
0x18001a06e  mov     rcx, [rbp+57h+arg_10]
0x18001a072  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a076  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
  ... truncated ...
```
