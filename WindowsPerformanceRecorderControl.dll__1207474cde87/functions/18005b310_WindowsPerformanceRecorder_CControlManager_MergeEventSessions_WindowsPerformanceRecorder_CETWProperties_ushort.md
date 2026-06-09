# WindowsPerformanceRecorder::CControlManager::MergeEventSessions(WindowsPerformanceRecorder::CETWProperties &,ushort *,ITraceMergeProperties *,bool,bool,WindowsPerformanceRecorder::CControlManager::CMarkSession &&,bool)

- ea: `0x18005b310`
- end: `0x18005c0d5`
- name: `?MergeEventSessions@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@PEAGPEAUITraceMergeProperties@@_N3$$QEAVCMarkSession@12@3@Z`
- size: `3525`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *this, struct WindowsPerformanceRecorder::CETWProperties *, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, LPCWSTR *), char, char, struct WindowsPerformanceRecorder::CETWProperties::CEventSession **, char)`
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003a1f0`
- `0x18005c0dc`
- `0x18005deb0`

## callees

- `0x1800024d0`
- `0x180008330`
- `0x18000a154`
- `0x180015e2c`
- `0x180016480`
- `0x18001a8c8`
- `0x18001c458`
- `0x18001c820`
- `0x18001d190`
- `0x18001e6e0`
- `0x180021810`
- `0x1800234f0`
- `0x18002c3f0`
- `0x180040a04`
- `0x1800493a0`
- `0x18004b17c`
- `0x18004b39c`
- `0x18004b7f8`
- `0x18004bca4`
- `0x18004ece0`
- `0x1800576f8`
- `0x180057994`
- `0x180057a2c`
- `0x180059d74`
- `0x180059e74`
- `0x18005b1f0`
- `0x18005b310`
- `0x18005d540`
- `0x18005d7b0`
- `0x18005eb94`
- `0x18005fce8`
- `0x1800602d0`
- `0x180074b44`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005bb99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005bb99`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005bec9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c03e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005bec9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c03e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005baaf`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005baaf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005be2b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005bfd7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005be2b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005bfd7`

## string_xrefs

- `0x18005b3e8`: `COMGUARD`
- `0x18005b517`: `COMGUARD`
- `0x18005b5da`: `COMGUARD`
- `0x18005b647`: `COMGUARD`
- `0x18005b6b9`: `COMGUARD`
- `0x18005b971`: `COMGUARD`
- `0x18005bd3a`: `COMGUARD`
- `0x18005be00`: `Fail to delete %ws`
- `0x18005bff3`: `Fail to delete %ws`
- `0x18005c01b`: `Fail to delete %ws`
- `0x18005b74b`: `XPERF_NGenPdbsCachePath`
- `0x18005b7aa`: `XPERF_NGenPdbsPath`
- `0x18005b812`: `XPERF_EmbeddedPdbPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
        WindowsPerformanceRecorder::CControlManager *this,
        struct WindowsPerformanceRecorder::CETWProperties *a2,
        __int64 a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, LPCWSTR *),
        char a5,
        char a6,
        struct WindowsPerformanceRecorder::CETWProperties::CEventSession **a7,
        char a8)
{
  __int64 v11; // r12
  __int64 v12; // rdi
  int v13; // r13d
  signed int v14; // eax
  __int64 v15; // r12
  _QWORD *v16; // rdi
  char v18; // si
  struct WindowsPerformanceRecorder::CETWProperties *v19; // rbx
  signed int v20; // eax
  unsigned int v21; // ebx
  signed int MarkSession; // eax
  unsigned int v23; // ebx
  signed int v24; // eax
  unsigned int v25; // ebx
  signed int v26; // eax
  unsigned int v27; // ebx
  const unsigned __int16 *v28; // r8
  int FileNameWithTag; // ebx
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  _QWORD *v32; // rbx
  int v33; // edi
  signed int v34; // eax
  unsigned int v35; // ebx
  const unsigned __int16 *v36; // rdx
  struct WindowsPerformanceRecorder::CETWProperties *v37; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v38; // rcx
  const unsigned __int16 *FileName; // rbx
  _QWORD *v40; // rax
  struct IUnknown *v41; // r10
  __int64 v42; // rdx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v43; // r9
  WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // r8
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v45; // rcx
  const unsigned __int16 *v46; // rax
  int v47; // edx
  _QWORD *v48; // r9
  _QWORD *j; // r8
  int v50; // r15d
  __int64 v51; // r9
  size_t v52; // rax
  int v53; // ebx
  __int64 v54; // rsi
  int v55; // eax
  int v56; // ebx
  size_t v57; // rbx
  int v58; // eax
  __int64 v59; // r8
  int v60; // r15d
  struct WindowsPerformanceRecorder::CETWProperties *v61; // rbx
  signed int v62; // eax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **k; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v64; // rsi
  __int64 m; // rsi
  const unsigned __int16 *v66; // rbx
  int v67; // eax
  const char *v68; // rbx
  unsigned int v69; // eax
  signed int v70; // eax
  const char *v71; // rbx
  unsigned int Error; // eax
  char *v73; // [rsp+28h] [rbp-110h]
  char *v74; // [rsp+28h] [rbp-110h]
  int v75[2]; // [rsp+40h] [rbp-F8h] BYREF
  size_t Size; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v77; // [rsp+50h] [rbp-E8h] BYREF
  struct WindowsPerformanceRecorder::CETWProperties *v78; // [rsp+58h] [rbp-E0h]
  char v79[4]; // [rsp+60h] [rbp-D8h] BYREF
  struct IUnknown *v80; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v81[32]; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE v82[32]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v83[32]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-68h]
  _QWORD *v85; // [rsp+D8h] [rbp-60h]
  LPCWSTR lpFileName[2]; // [rsp+E8h] [rbp-50h] BYREF

  v84 = -2;
  v78 = a2;
  v11 = *((_QWORD *)a2 + 2);
  v12 = *((_QWORD *)a2 + 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v75);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
  v77 = 0;
  lpFileName[0] = 0;
  v13 = (**a4)(a4, &GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7, lpFileName);
  if ( v13 < 0 )
    goto LABEL_4;
  v14 = (*(__int64 (__fastcall **)(LPCWSTR, __int64 *))(*(_QWORD *)lpFileName[0] + 24LL))(lpFileName[0], &v77);
  v13 = v14;
  if ( v14 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"MergeEventSessions",
      (const char *)0x10DD,
      v14,
      "COMGUARD",
      v73);
LABEL_4:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(lpFileName);
LABEL_7:
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
    return (unsigned int)v13;
  }
  v15 = (v11 - v12) >> 3;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(lpFileName);
  v16 = 0;
  if ( *(_BYTE *)(v77 + 58) )
  {
    v13 = 1;
    goto LABEL_7;
  }
  if ( *((_QWORD *)this + 48) )
  {
    if ( *((_BYTE *)this + 520) == 1 )
    {
      v18 = 0;
      v19 = v78;
    }
    else
    {
      std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::clear((char *)this + 496);
      if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 48) + 72LL))(
             *((_QWORD *)this + 48),
             0xFFFFFFFFLL) )
      {
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
        return 3310903299LL;
      }
      v20 = WindowsPerformanceRecorder::CControlManager::StoreTraceMergeTexts(this);
      v21 = v20;
      if ( v20 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"MergeEventSessions",
          (const char *)0x10FB,
          v20,
          "COMGUARD",
          v73);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
        return v21;
      }
      v18 = 1;
      v19 = v78;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &Size,
        *((_QWORD *)v78 + 41));
      std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::push_back(
        (char *)this + 496,
        &Size);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Size);
      v16 = 0;
    }
    if ( !a5 )
    {
      if ( !a7[1] )
      {
        MarkSession = WindowsPerformanceRecorder::CControlManager::CreateMarkSession(this, v19, a7 + 1);
        v23 = MarkSession;
        if ( MarkSession < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"MergeEventSessions",
            (const char *)0x1104,
            MarkSession,
            "COMGUARD",
            v73);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
          return v23;
        }
        v24 = WindowsPerformanceRecorder::CControlManager::CMarkSession::Start((WindowsPerformanceRecorder::CControlManager::CMarkSession *)a7);
        v25 = v24;
        if ( v24 < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"MergeEventSessions",
            (const char *)0x1105,
            v24,
            "COMGUARD",
            v73);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
          WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
          return v25;
        }
      }
      v26 = WindowsPerformanceRecorder::CControlManager::LogTraceMergeSessionText(this, a7[1]);
      v27 = v26;
      v16 = 0;
      if ( v26 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"MergeEventSessions",
          (const char *)0x1108,
          v26,
          "COMGUARD",
          v73);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
        return v27;
      }
    }
    if ( v18 )
    {
      if ( *((_BYTE *)v78 + 304)
        && *((_BYTE *)this + 448)
        && ((v28 = (const unsigned __int16 *)*((_QWORD *)this + 57), *((_DWORD *)v28 - 4))
         && (FileNameWithTag = WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(
                                 (WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83,
                                 L"XPERF_NGenPdbsCachePath",
                                 v28),
             FileNameWithTag < 0)
         || (v30 = (const unsigned __int16 *)*((_QWORD *)this + 58), *((_DWORD *)v30 - 4))
         && (FileNameWithTag = WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(
                                 (WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82,
                                 L"XPERF_NGenPdbsPath",
                                 v30),
             FileNameWithTag < 0))
        || *((_BYTE *)this + 472)
        && (v31 = (const unsigned __int16 *)*((_QWORD *)this + 60), *((_DWORD *)v31 - 4))
        && (FileNameWithTag = WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(
                                (WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81,
                                L"XPERF_EmbeddedPdbPath",
                                v31),
            FileNameWithTag < 0) )
      {
LABEL_48:
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
        WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
        return (unsigned int)FileNameWithTag;
      }
    }
    v32 = (_QWORD *)((char *)this + 488);
  }
  else
  {
    v32 = (_QWORD *)((char *)this + 488);
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 488, a3);
    if ( !*(_DWORD *)(*((_QWORD *)this + 61) - 16LL) )
    {
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
      return 3310880265LL;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(lpFileName);
    v33 = WindowsPerformanceRecorder::Impl::ConvertToFullPath(lpFileName, *v32);
    if ( v33 < 0 )
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)lpFileName);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
      return (unsigned int)v33;
    }
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 488, lpFileName);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)lpFileName);
    v16 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::operator=(v75, v32);
  if ( a7[1] )
  {
    v34 = WindowsPerformanceRecorder::CControlManager::CMarkSession::Stop((WindowsPerformanceRecorder::CControlManager::CMarkSession *)a7);
    v35 = v34;
    if ( v34 < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"MergeEventSessions",
        (const char *)0x113B,
        v34,
        "COMGUARD",
        v73);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
      WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
      return v35;
    }
  }
  if ( a6 || *((_BYTE *)this + 520) )
  {
    v36 = L"Shutdown";
    if ( !a5 )
      v36 = L"Boot";
    FileNameWithTag = WindowsPerformanceRecorder::Impl::GetFileNameWithTag(v75, v36);
    if ( FileNameWithTag < 0 )
      goto LABEL_48;
  }
  v37 = v78;
  if ( *((_DWORD *)v78 + 64) == 1 )
    LODWORD(v15) = ((__int64)(*((_QWORD *)this + 69) - *((_QWORD *)this + 68)) >> 3) + v15;
  v38 = a7[1];
  if ( v38 )
  {
    FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v38);
    if ( FileName )
      LODWORD(v15) = v15 + 1;
  }
  else
  {
    FileName = 0;
  }
  Size = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&Size, (unsigned int)v15, 8) < 0
    || (v40 = malloc(Size), v16 = v40, v85 = v40, v41 = 0, !v40) )
  {
    v56 = -2147024882;
    goto LABEL_133;
  }
  v42 = 0;
  if ( FileName )
  {
    *v40 = FileName;
    v42 = 1;
  }
  v43 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)v37 + 2);
  for ( i = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)v37 + 1); i != v43; ++i )
  {
    if ( (unsigned int)v42 < (unsigned int)v15 )
    {
      v45 = *i;
      if ( *(_DWORD *)*i != 5 || *((_BYTE *)v45 + 210) == (_BYTE)v41 )
      {
        v46 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v45);
        v16[v47] = v46;
        v42 = (unsigned int)(v47 + 1);
      }
      else
      {
        LODWORD(v15) = v15 - 1;
      }
    }
  }
  v48 = (_QWORD *)*((_QWORD *)this + 69);
  for ( j = (_QWORD *)*((_QWORD *)this + 68); j != v48; ++j )
  {
    if ( (unsigned int)v42 < (unsigned int)v15 )
    {
      v16[(unsigned int)v42] = *j;
      v42 = (unsigned int)(v42 + 1);
    }
  }
  v50 = (int)v41;
  LODWORD(lpFileName[0]) = (_DWORD)v41;
  v51 = v77;
  v52 = **(_QWORD **)(v77 + 40);
  Size = v52;
  while ( *(_BYTE *)(v52 + 25) == (_BYTE)v41 )
  {
    v50 |= *(_DWORD *)(*(_QWORD *)(v52 + 32) + 8LL);
    LODWORD(lpFileName[0]) = v50;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&Size);
    v52 = Size;
  }
  v53 = (int)v41;
  v54 = *(_QWORD *)v75;
  if ( (_DWORD)v15 )
  {
    while ( 1 )
    {
      v55 = _o__wcsicmp(v54, v16[v53]);
      v41 = 0;
      if ( !v55 )
        break;
      if ( ++v53 >= (unsigned int)v15 )
      {
        v51 = v77;
        goto LABEL_79;
      }
    }
    v56 = -984063998;
    goto LABEL_133;
  }
LABEL_79:
  if ( *(_BYTE *)(v51 + 32) != (_BYTE)v41 && a8 == (_BYTE)v41 && *(_BYTE *)(v51 + 57) != (_BYTE)v41 )
  {
    v56 = -984087009;
LABEL_133:
    free(v16);
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
    WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
    return (unsigned int)v56;
  }
  v80 = v41;
  Size = (size_t)v41;
  v56 = ATL::CComObject<WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender>::CreateInstance(&Size, v42);
  if ( v56 >= 0 )
  {
    v57 = Size;
    (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 8LL))(Size);
    *(_QWORD *)(v57 + 80) = this;
    *(_BYTE *)(v57 + 88) = a5;
    v58 = (**(__int64 (__fastcall ***)(size_t, GUID *, struct IUnknown **))v57)(
            v57,
            &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
            &v80);
    v56 = 0;
    if ( v58 < 0 )
      v56 = v58;
  }
  ATL::CComPtrBase<ATL::CComObject<WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender>>::~CComPtrBase<ATL::CComObject<WindowsPerformanceRecorder::Impl::CControlManagerEventTraceExtender>>(&Size);
  if ( v56 < 0 )
  {
LABEL_88:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    goto LABEL_133;
  }
  *(_DWORD *)v79 = 0;
  if ( (*(_BYTE *)(v77 + 56) || *((_BYTE *)this + 573)) && Performance::COSVersionInfo::IsWin8AndUp() )
  {
    v50 |= 0x10000000u;
    LODWORD(lpFileName[0]) = v50;
  }
  v60 = v50 | 0x40000000;
  if ( !*(_BYTE *)(v77 + 57) )
    v60 = (int)lpFileName[0];
  v61 = v78;
  if ( *((_BYTE *)v78 + 304) )
  {
    if ( *((_BYTE *)this + 448) )
      v60 |= 0x80u;
    if ( *((_BYTE *)this + 472) )
      v60 |= 0x100u;
  }
  if ( (_DWORD)v15 )
  {
    Size = (size_t)&off_18008EB00;
    if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &WindowsPerformanceRecorderControlProvider_Context,
        Perf_ExternalCall_Begin,
        v59,
        1,
        lpFileName);
    v62 = MergeEtlExWithErrorContext(v15, (int)v16, v54, v60, 0, (__int64)v79, v80);
    v56 = v62;
    if ( v62 < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"MergeEventSessions",
        (const char *)0x11B6,
        v62,
        "COMGUARD",
        v74);
      WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&Size);
      goto LABEL_88;
    }
    WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&Size);
    v61 = v78;
  }
  if ( *(_DWORD *)v79 )
  {
    WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
      this,
      -984063999,
      &IID_IControlManager,
      *((const unsigned __int16 **)v61 + 40),
      0);
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"MergeEventSessions",
      (const char *)0x11BC,
      0xC5586001,
      "%ws",
      *((const char **)v61 + 40));
  }
  for ( k = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)v61 + 1);
        k != *((WindowsPerformanceRecorder::CETWProperties::CEventSession ***)v61 + 2);
        ++k )
  {
    v64 = *k;
    if ( *(_DWORD *)*k == 5 && *((_BYTE *)v64 + 210) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &Size,
        v75);
      v56 = WindowsPerformanceRecorder::Impl::GetFileNameWithTag(&Size, L"HyperV");
      if ( v56 < 0 )
      {
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Size);
        goto LABEL_88;
      }
      lpFileName[0] = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v64);
      v70 = MergeEtlExWithErrorContext(1, (int)lpFileName, Size, v60, 0, (__int64)v79, v80);
      if ( v70 < 0 )
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"MergeEventSessions",
          (const char *)0x11CD,
          v70,
          "Fail to Merge %ws",
          (const char *)lpFileName[0]);
      if ( !a8 && *(_BYTE *)(v77 + 32) && !DeleteFileW(lpFileName[0]) )
      {
        v71 = (const char *)lpFileName[0];
        Error = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"MergeEventSessions",
          (const char *)0x11D4,
          Error,
          "Fail to delete %ws",
          v71);
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Size);
      v61 = v78;
      break;
    }
  }
  if ( !a8 )
  {
    if ( *(_BYTE *)(v77 + 32) )
    {
      for ( m = 0; (unsigned int)m < (unsigned int)v15; v61 = v78 )
      {
        if ( !DeleteFileW((LPCWSTR)v16[m]) )
        {
          v66 = (const unsigned __int16 *)*((_QWORD *)v61 + 40);
          v67 = ATL::AtlHresultFromLastError();
          WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
            this,
            v67,
            &IID_IControlManager,
            v66,
            0);
          v68 = (const char *)v16[m];
          v69 = ATL::AtlHresultFromLastError();
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"MergeEventSessions",
            (const char *)0x11E4,
            v69,
            "Fail to delete %ws",
            v68);
        }
        m = (unsigned int)(m + 1);
      }
    }
  }
  if ( a6 )
  {
    if ( ++*((_BYTE *)this + 520) == 2 )
      *((_BYTE *)this + 520) = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
  free(v16);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v81);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v82);
  WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable((WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable *)v83);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)v75);
  return 0;
}

```

## disassembly

```asm
0x18005b310  mov     rax, rsp
0x18005b313  push    rbx
0x18005b314  push    rsi
0x18005b315  push    rdi
0x18005b316  push    r12
0x18005b318  push    r13
0x18005b31a  push    r14
0x18005b31c  push    r15
0x18005b31e  sub     rsp, 100h
0x18005b325  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18005b32d  mov     rax, cs:__security_cookie
0x18005b334  xor     rax, rsp
0x18005b337  mov     [rsp+138h+var_40], rax
0x18005b33f  mov     rbx, r9
0x18005b342  mov     rsi, r8
0x18005b345  mov     [rsp+138h+var_E0], rdx
0x18005b34a  mov     r14, rcx
0x18005b34d  mov     r15, [rsp+138h+arg_30]
0x18005b355  mov     r12, [rdx+10h]
0x18005b359  mov     rdi, [rdx+8]
0x18005b35d  lea     rcx, [rsp+138h+var_F8]; void *
0x18005b362  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005b367  nop
0x18005b368  lea     rcx, [rsp+138h+var_88]; this
0x18005b370  call    ??0CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable(void)
0x18005b375  nop
0x18005b376  lea     rcx, [rsp+138h+var_A8]; this
0x18005b37e  call    ??0CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable(void)
0x18005b383  nop
0x18005b384  lea     rcx, [rsp+138h+var_C8]; this
0x18005b389  call    ??0CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::CAutoEnvironmentVariable(void)
0x18005b38e  nop
0x18005b38f  mov     [rsp+138h+var_E8], 0
0x18005b398  mov     [rsp+138h+lpFileName], 0
0x18005b3a4  mov     rax, [rbx]
0x18005b3a7  lea     r8, [rsp+138h+lpFileName]
0x18005b3af  lea     rdx, _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7
0x18005b3b6  mov     rcx, rbx
0x18005b3b9  mov     rax, [rax]
0x18005b3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3c1  mov     r13d, eax
0x18005b3c4  test    eax, eax
0x18005b3c6  js      short loc_18005B40F
0x18005b3c8  mov     rcx, [rsp+138h+lpFileName]
0x18005b3d0  mov     rax, [rcx]
0x18005b3d3  lea     rdx, [rsp+138h+var_E8]
0x18005b3d8  mov     rax, [rax+18h]
0x18005b3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3e1  mov     r13d, eax
0x18005b3e4  test    eax, eax
0x18005b3e6  jns     short loc_18005B41E
0x18005b3e8  lea     rcx, aComguard; "COMGUARD"
0x18005b3ef  mov     [rsp+138h+Format], rcx; Format
0x18005b3f4  mov     r9d, eax; unsigned int
0x18005b3f7  mov     r8d, 10DDh; char *
0x18005b3fd  lea     rdx, aMergeeventsess; "MergeEventSessions"
0x18005b404  mov     ecx, 2; this
0x18005b409  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b40e  nop
0x18005b40f  lea     rcx, [rsp+138h+lpFileName]
0x18005b417  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005b41c  jmp     short loc_18005B443
0x18005b41e  sub     r12, rdi
0x18005b421  sar     r12, 3
0x18005b425  lea     rcx, [rsp+138h+lpFileName]
0x18005b42d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005b432  mov     rax, [rsp+138h+var_E8]
0x18005b437  xor     edi, edi
0x18005b439  cmp     [rax+3Ah], dil
0x18005b43d  jz      short loc_18005B47C
0x18005b43f  lea     r13d, [rdi+1]
0x18005b443  lea     rcx, [rsp+138h+var_C8]; this
0x18005b448  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b44d  nop
0x18005b44e  lea     rcx, [rsp+138h+var_A8]; this
0x18005b456  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b45b  nop
0x18005b45c  lea     rcx, [rsp+138h+var_88]; this
0x18005b464  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b469  nop
0x18005b46a  lea     rcx, [rsp+138h+var_F8]; this
0x18005b46f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b474  mov     eax, r13d
0x18005b477  jmp     loc_18005C0B2
0x18005b47c  cmp     [r14+180h], rdi
0x18005b483  jz      loc_18005B86D
0x18005b489  mov     r13d, 1
0x18005b48f  cmp     [r14+208h], r13b
0x18005b496  jnz     short loc_18005B4A5
0x18005b498  mov     sil, dil
0x18005b49b  mov     rbx, [rsp+138h+var_E0]
0x18005b4a0  jmp     loc_18005B5AA
0x18005b4a5  lea     rdi, [r14+1F0h]
0x18005b4ac  mov     rcx, rdi
0x18005b4af  call    ?clear@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAAXXZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::clear(void)
0x18005b4b4  mov     rcx, [r14+180h]
0x18005b4bb  mov     rax, [rcx]
0x18005b4be  or      edx, 0FFFFFFFFh
0x18005b4c1  mov     rax, [rax+48h]
0x18005b4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4ca  test    eax, eax
0x18005b4cc  jz      short loc_18005B509
0x18005b4ce  lea     rcx, [rsp+138h+var_C8]; this
0x18005b4d3  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b4d8  nop
0x18005b4d9  lea     rcx, [rsp+138h+var_A8]; this
0x18005b4e1  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b4e6  nop
0x18005b4e7  lea     rcx, [rsp+138h+var_88]; this
0x18005b4ef  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b4f4  nop
0x18005b4f5  lea     rcx, [rsp+138h+var_F8]; this
0x18005b4fa  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b4ff  mov     eax, 0C5586003h
0x18005b504  jmp     loc_18005C0B2
0x18005b509  mov     rcx, r14; this
0x18005b50c  call    ?StoreTraceMergeTexts@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::StoreTraceMergeTexts(void)
0x18005b511  mov     ebx, eax
0x18005b513  test    eax, eax
0x18005b515  jns     short loc_18005B576
0x18005b517  lea     rcx, aComguard; "COMGUARD"
0x18005b51e  mov     [rsp+138h+Format], rcx; Format
0x18005b523  mov     r9d, eax; unsigned int
0x18005b526  mov     r8d, 10FBh; char *
0x18005b52c  lea     rdx, aMergeeventsess; "MergeEventSessions"
0x18005b533  mov     ecx, 2; this
0x18005b538  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b53d  nop
0x18005b53e  lea     rcx, [rsp+138h+var_C8]; this
0x18005b543  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b548  nop
0x18005b549  lea     rcx, [rsp+138h+var_A8]; this
0x18005b551  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b556  nop
0x18005b557  lea     rcx, [rsp+138h+var_88]; this
0x18005b55f  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b564  nop
0x18005b565  lea     rcx, [rsp+138h+var_F8]; this
0x18005b56a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b56f  mov     eax, ebx
0x18005b571  jmp     loc_18005C0B2
0x18005b576  mov     sil, r13b
0x18005b579  mov     rbx, [rsp+138h+var_E0]
0x18005b57e  mov     rdx, [rbx+148h]
0x18005b585  lea     rcx, [rsp+138h+Size]
0x18005b58a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005b58f  nop
0x18005b590  lea     rdx, [rsp+138h+Size]
0x18005b595  mov     rcx, rdi
0x18005b598  call    ?push_back@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAAX$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::push_back(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18005b59d  nop
0x18005b59e  lea     rcx, [rsp+138h+Size]; this
0x18005b5a3  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b5a8  xor     edi, edi
0x18005b5aa  cmp     [rsp+138h+arg_20], dil
0x18005b5b2  jnz     loc_18005B716
0x18005b5b8  lea     rdi, [r15+8]
0x18005b5bc  cmp     qword ptr [rdi], 0
0x18005b5c0  jnz     loc_18005B6A6
0x18005b5c6  mov     r8, rdi; struct WindowsPerformanceRecorder::CETWProperties::CEventSession **
0x18005b5c9  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005b5cc  mov     rcx, r14; this
0x18005b5cf  call    ?CreateMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBVCETWProperties@2@PEAPEAUCEventSession@32@@Z; WindowsPerformanceRecorder::CControlManager::CreateMarkSession(WindowsPerformanceRecorder::CETWProperties const &,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)
0x18005b5d4  mov     ebx, eax
0x18005b5d6  test    eax, eax
0x18005b5d8  jns     short loc_18005B639
0x18005b5da  lea     rcx, aComguard; "COMGUARD"
0x18005b5e1  mov     [rsp+138h+Format], rcx; Format
0x18005b5e6  mov     r9d, eax; unsigned int
0x18005b5e9  mov     r8d, 1104h; char *
0x18005b5ef  lea     rdx, aMergeeventsess; "MergeEventSessions"
0x18005b5f6  mov     ecx, 2; this
0x18005b5fb  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b600  nop
0x18005b601  lea     rcx, [rsp+138h+var_C8]; this
0x18005b606  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b60b  nop
0x18005b60c  lea     rcx, [rsp+138h+var_A8]; this
0x18005b614  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b619  nop
0x18005b61a  lea     rcx, [rsp+138h+var_88]; this
0x18005b622  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b627  nop
0x18005b628  lea     rcx, [rsp+138h+var_F8]; this
0x18005b62d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b632  mov     eax, ebx
0x18005b634  jmp     loc_18005C0B2
0x18005b639  mov     rcx, r15; this
0x18005b63c  call    ?Start@CMarkSession@CControlManager@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Start(void)
0x18005b641  mov     ebx, eax
0x18005b643  test    eax, eax
0x18005b645  jns     short loc_18005B6A6
0x18005b647  lea     rcx, aComguard; "COMGUARD"
0x18005b64e  mov     [rsp+138h+Format], rcx; Format
0x18005b653  mov     r9d, eax; unsigned int
0x18005b656  mov     r8d, 1105h; char *
0x18005b65c  lea     rdx, aMergeeventsess; "MergeEventSessions"
0x18005b663  mov     ecx, 2; this
0x18005b668  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b66d  nop
0x18005b66e  lea     rcx, [rsp+138h+var_C8]; this
0x18005b673  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b678  nop
0x18005b679  lea     rcx, [rsp+138h+var_A8]; this
0x18005b681  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b686  nop
0x18005b687  lea     rcx, [rsp+138h+var_88]; this
0x18005b68f  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b694  nop
0x18005b695  lea     rcx, [rsp+138h+var_F8]; this
0x18005b69a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b69f  mov     eax, ebx
0x18005b6a1  jmp     loc_18005C0B2
0x18005b6a6  mov     rdx, [rdi]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18005b6a9  mov     rcx, r14; this
0x18005b6ac  call    ?LogTraceMergeSessionText@CControlManager@WindowsPerformanceRecorder@@AEAAJPEAUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::LogTraceMergeSessionText(WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x18005b6b1  mov     ebx, eax
0x18005b6b3  xor     edi, edi
0x18005b6b5  test    eax, eax
0x18005b6b7  jns     short loc_18005B716
0x18005b6b9  lea     rcx, aComguard; "COMGUARD"
0x18005b6c0  mov     [rsp+138h+Format], rcx; Format
0x18005b6c5  mov     r9d, eax; unsigned int
0x18005b6c8  mov     r8d, 1108h; char *
0x18005b6ce  lea     rdx, aMergeeventsess; "MergeEventSessions"
0x18005b6d5  lea     ecx, [rdi+2]; this
0x18005b6d8  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b6dd  nop
0x18005b6de  lea     rcx, [rsp+138h+var_C8]; this
0x18005b6e3  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b6e8  nop
0x18005b6e9  lea     rcx, [rsp+138h+var_A8]; this
0x18005b6f1  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b6f6  nop
0x18005b6f7  lea     rcx, [rsp+138h+var_88]; this
0x18005b6ff  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b704  nop
0x18005b705  lea     rcx, [rsp+138h+var_F8]; this
0x18005b70a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b70f  mov     eax, ebx
0x18005b711  jmp     loc_18005C0B2
0x18005b716  test    sil, sil
0x18005b719  jz      loc_18005B861
0x18005b71f  mov     rax, [rsp+138h+var_E0]
0x18005b724  cmp     [rax+130h], dil
0x18005b72b  jz      loc_18005B7FC
0x18005b731  cmp     [r14+1C0h], dil
0x18005b738  jz      loc_18005B7FC
0x18005b73e  mov     r8, [r14+1C8h]; unsigned __int16 *
0x18005b745  cmp     [r8-10h], edi
0x18005b749  jz      short loc_18005B79D
0x18005b74b  lea     rdx, aXperfNgenpdbsc; "XPERF_NGenPdbsCachePath"
0x18005b752  lea     rcx, [rsp+138h+var_88]; this
0x18005b75a  call    ?Set@CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAAJPEBG0@Z; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(ushort const *,ushort const *)
0x18005b75f  mov     ebx, eax
0x18005b761  test    eax, eax
0x18005b763  jns     short loc_18005B79D
0x18005b765  lea     rcx, [rsp+138h+var_C8]; this
0x18005b76a  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b76f  nop
0x18005b770  lea     rcx, [rsp+138h+var_A8]; this
0x18005b778  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b77d  nop
0x18005b77e  lea     rcx, [rsp+138h+var_88]; this
0x18005b786  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b78b  nop
0x18005b78c  lea     rcx, [rsp+138h+var_F8]; this
0x18005b791  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b796  mov     eax, ebx
0x18005b798  jmp     loc_18005C0B2
0x18005b79d  mov     r8, [r14+1D0h]; unsigned __int16 *
0x18005b7a4  cmp     [r8-10h], edi
0x18005b7a8  jz      short loc_18005B7FC
0x18005b7aa  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x18005b7b1  lea     rcx, [rsp+138h+var_A8]; this
0x18005b7b9  call    ?Set@CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAAJPEBG0@Z; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(ushort const *,ushort const *)
0x18005b7be  mov     ebx, eax
0x18005b7c0  test    eax, eax
0x18005b7c2  jns     short loc_18005B7FC
0x18005b7c4  lea     rcx, [rsp+138h+var_C8]; this
0x18005b7c9  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b7ce  nop
0x18005b7cf  lea     rcx, [rsp+138h+var_A8]; this
0x18005b7d7  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b7dc  nop
0x18005b7dd  lea     rcx, [rsp+138h+var_88]; this
0x18005b7e5  call    ??1CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::~CAutoEnvironmentVariable(void)
0x18005b7ea  nop
0x18005b7eb  lea     rcx, [rsp+138h+var_F8]; this
0x18005b7f0  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005b7f5  mov     eax, ebx
0x18005b7f7  jmp     loc_18005C0B2
0x18005b7fc  cmp     [r14+1D8h], dil
0x18005b803  jz      short loc_18005B861
0x18005b805  mov     r8, [r14+1E0h]; unsigned __int16 *
0x18005b80c  cmp     [r8-10h], edi
0x18005b810  jz      short loc_18005B861
0x18005b812  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x18005b819  lea     rcx, [rsp+138h+var_C8]; this
0x18005b81e  call    ?Set@CAutoEnvironmentVariable@Impl@WindowsPerformanceRecorder@@QEAAJPEBG0@Z; WindowsPerformanceRecorder::Impl::CAutoEnvironmentVariable::Set(ushort const *,ushort const *)
  ... truncated ...
```
