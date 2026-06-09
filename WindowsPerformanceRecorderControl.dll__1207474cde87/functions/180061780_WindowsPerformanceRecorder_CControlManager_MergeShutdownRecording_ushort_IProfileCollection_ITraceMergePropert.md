# WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording(ushort *,IProfileCollection *,ITraceMergeProperties *)

- ea: `0x180061780`
- end: `0x180061f54`
- name: `?MergeShutdownRecording@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAGPEAUIProfileCollection@@PEAUITraceMergeProperties@@@Z`
- size: `2004`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int16 *, struct IProfileCollection *, struct ITraceMergeProperties *)`
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008330`
- `0x18001a61c`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c458`
- `0x18001c820`
- `0x18001d190`
- `0x18001d3d8`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x1800248d8`
- `0x1800328a8`
- `0x1800328f8`
- `0x1800329bc`
- `0x180035004`
- `0x180036d08`
- `0x180036df0`
- `0x180037f3c`
- `0x180039084`
- `0x18003c270`
- `0x180040a04`
- `0x18004865c`
- `0x1800490f8`
- `0x18004a664`
- `0x18004b024`
- `0x18004b128`
- `0x18004b39c`
- `0x18004ed10`
- `0x1800599c0`
- `0x18005c0dc`
- `0x1800602d0`
- `0x180060684`
- `0x180061780`
- `0x180071b28`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061db8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061e4b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061db8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061e4b`

## string_xrefs

- `0x180061d8f`: `Fail to delete %ws`
- `0x180061e81`: `Fail to delete %ws`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        unsigned __int16 *a2,
        struct IProfileCollection *a3,
        struct ITraceMergeProperties *a4)
{
  WindowsPerformanceRecorder::CControlManager *v7; // r15
  unsigned __int16 *v8; // r12
  int v9; // ebx
  int IsOtherObjectInstanceNameCompatible; // eax
  int v11; // r14d
  __int64 v12; // rbx
  const char *v13; // r13
  char v14; // di
  int v16; // eax
  int v17; // eax
  int v18; // eax
  const unsigned __int16 *v19; // r9
  int v20; // eax
  bool v21; // zf
  _BYTE *v22; // rdi
  bool v23; // r14
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v24; // rdi
  WindowsPerformanceRecorder::CETWProperties *v25; // rax
  const unsigned __int16 *SessionName; // rax
  const unsigned __int16 *v27; // r9
  int v28; // edi
  int v29; // edi
  unsigned __int16 *v30; // rdx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v31; // r15
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v32; // rbx
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v33; // rdi
  WindowsPerformanceRecorder::Impl *FileName; // rax
  const unsigned __int16 *v35; // rdx
  const WCHAR *v36; // rax
  int Error; // eax
  const char *v38; // rdi
  unsigned int v39; // eax
  const char *v40; // rdi
  int v41; // eax
  unsigned int v42; // eax
  bool Format; // [rsp+20h] [rbp-D8h]
  int Formata; // [rsp+20h] [rbp-D8h]
  bool v45; // [rsp+30h] [rbp-C8h]
  bool v46; // [rsp+40h] [rbp-B8h]
  int v47; // [rsp+44h] [rbp-B4h]
  int v48; // [rsp+48h] [rbp-B0h]
  struct ITraceMergeProperties *v49; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A0h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-98h] BYREF
  WindowsPerformanceRecorder::CETWProperties *v52; // [rsp+68h] [rbp-90h] BYREF
  __int64 v53; // [rsp+70h] [rbp-88h]
  unsigned __int16 *v54; // [rsp+78h] [rbp-80h]
  unsigned __int16 *v55; // [rsp+80h] [rbp-78h]
  const char *v56; // [rsp+88h] [rbp-70h]
  __int64 v57; // [rsp+90h] [rbp-68h] BYREF
  _QWORD v58[2]; // [rsp+98h] [rbp-60h] BYREF
  ATL::CAtlException *v59; // [rsp+A8h] [rbp-50h] BYREF

  v58[1] = -2;
  v7 = this;
  v57 = 0;
  v8 = (unsigned __int16 *)((char *)this - 192);
  v55 = (unsigned __int16 *)((char *)this - 192);
  v9 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(
         &v57,
         (char *)this - 192);
  if ( v9 < 0 )
    goto LABEL_12;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v7 - 23) + 24LL))((char *)v7 - 184);
  WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo((char *)v7 - 88);
  IsOtherObjectInstanceNameCompatible = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
                                          (char *)v7 + 24,
                                          a3);
  if ( IsOtherObjectInstanceNameCompatible < 0
    || a4
    && (IsOtherObjectInstanceNameCompatible = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
                                                (char *)v7 + 24,
                                                a4),
        IsOtherObjectInstanceNameCompatible < 0) )
  {
    v9 = IsOtherObjectInstanceNameCompatible;
LABEL_12:
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v57);
    return (unsigned int)v9;
  }
  v11 = 0;
  v48 = 0;
  v47 = 0;
  ((void (__stdcall *)(void *))ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>)(&lpFileName);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, a2);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v59) )
    {
      v47 = *(_DWORD *)v59;
      v7 = this;
      v11 = *(_DWORD *)v59;
      v48 = *(_DWORD *)v59;
      v8 = v55;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180061855);
    }
  }
  v54 = v8;
  v58[0] = off_180090F68;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &WindowsPerformanceRecorderControlProvider_Context,
      Perf_MergeShutdownProfiles_Begin,
      lpFileName);
  v12 = 0;
  v53 = 0;
  v50 = 0;
  v13 = 0;
  v56 = 0;
  v55 = 0;
  v14 = 0;
  v46 = 0;
  if ( v11 >= 0 )
  {
    LODWORD(v49) = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType((WindowsPerformanceRecorder::CControlManager *)v8);
    if ( (int)v49 < 0 )
    {
      WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording_::_2_::CPerfEventMacro::_CPerfEventMacro(v58);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
      v9 = (int)v49;
      goto LABEL_12;
    }
    v16 = *((_DWORD *)v7 + 94);
    if ( (v16 & 2) != 0 )
    {
      v55 = L"Normal";
      if ( (v16 & 8) != 0 )
      {
        v14 = 1;
        v46 = 1;
        if ( *((_BYTE *)v7 + 328) )
        {
LABEL_21:
          if ( !a2 || !a3 )
          {
            v11 = -2147467261;
            v48 = -2147467261;
            v47 = -2147467261;
          }
          goto LABEL_24;
        }
      }
    }
    else
    {
      v11 = -984068080;
    }
  }
  v17 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin((WindowsPerformanceRecorder::CControlManager *)v8);
  if ( v17 < 0 )
  {
    v11 = v17;
    v48 = v17;
    v47 = v17;
    goto LABEL_24;
  }
  v48 = v11;
  v47 = v11;
  if ( v11 >= 0 )
    goto LABEL_21;
LABEL_24:
  if ( v11 < 0 )
    goto LABEL_56;
  WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(
    (WindowsPerformanceRecorder::CControlManager *)v8,
    *((_DWORD *)v7 + 94));
  v52 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
  v12 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(v52);
  v53 = v12;
  v50 = v12;
  v18 = WindowsPerformanceRecorder::CETWProperties::Initialize(
          (WindowsPerformanceRecorder::CETWProperties *)v12,
          a3,
          (struct WindowsPerformanceRecorder::CControlManager *)v8,
          (*((_DWORD *)v7 + 94) & 2) != 0);
  v11 = v18;
  v48 = v18;
  if ( v18 < 0 )
    goto LABEL_55;
  v13 = *(const char **)(v12 + 320);
  v56 = v13;
  WindowsPerformanceRecorder::TelemetryUsage(
    (WindowsPerformanceRecorder *)0x2000,
    (unsigned __int64)"MergeShutdownRecording",
    v13,
    v19);
  v20 = *(_DWORD *)(v12 + 256);
  if ( v20 == 1 )
  {
    if ( (*((_BYTE *)v7 + 376) & 0x20) != 0 )
      goto LABEL_28;
LABEL_34:
    v11 = -984068080;
    v48 = -984068080;
    v47 = -984068080;
    goto LABEL_56;
  }
  if ( v20 == 2 && (*((_BYTE *)v7 + 376) & 0x20) != 0 )
    goto LABEL_34;
LABEL_28:
  v18 = WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(
          (WindowsPerformanceRecorder::CControlManager *)v8,
          (struct WindowsPerformanceRecorder::CETWProperties *)v12,
          0);
  v11 = v18;
  v48 = v18;
  if ( v18 < 0 )
  {
LABEL_55:
    v47 = v18;
    goto LABEL_56;
  }
  v21 = v14 == 0;
  v22 = (char *)v7 + 328;
  if ( !v21 && *v22 )
  {
    v23 = v46;
    goto LABEL_36;
  }
  *((_QWORD *)v7 + 28) = 0;
  *((_QWORD *)v7 + 29) = 0;
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned __int64,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,unsigned __int64>>,0>>::clear((char *)v7 + 240);
  v23 = v46;
  if ( v46 )
  {
LABEL_36:
    if ( *v22 )
      goto LABEL_42;
  }
  v24 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v12 + 8);
  v25 = *(WindowsPerformanceRecorder::CETWProperties **)(v12 + 16);
  v52 = v25;
  while ( v24 != (WindowsPerformanceRecorder::CETWProperties::CEventSession **)v25 )
  {
    WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(*v24);
    SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v24);
    v11 = WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(
            (WindowsPerformanceRecorder::CControlManager *)v8,
            (const unsigned __int16 *)v13,
            SessionName,
            v27);
    v48 = v11;
    v47 = v11;
    if ( v11 < 0 )
      goto LABEL_56;
    ++v24;
    v25 = v52;
  }
  v23 = v46;
LABEL_42:
  if ( a4 )
  {
    v11 = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
            (WindowsPerformanceRecorder::CControlManager *)v8,
            (struct WindowsPerformanceRecorder::CETWProperties *)v12,
            a2,
            a4,
            Format,
            v23,
            v45);
    v48 = v11;
    v47 = v11;
LABEL_53:
    if ( v11 < 0 )
      WindowsPerformanceRecorder::CControlManager::CleanupGeneratedFiles(
        (WindowsPerformanceRecorder::CControlManager *)v8,
        (const unsigned __int16 *)v13);
LABEL_56:
    v29 = 0;
    v30 = v55;
    if ( v55 )
    {
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        v29 = WindowsPerformanceRecorder::CControlManager::ClearStateInRegistry(
                (WindowsPerformanceRecorder::CControlManager *)v8,
                v55);
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_ellipsis(4) )
        {
          LODWORD(v49) = -2147024882;
          v7 = this;
          v11 = v47;
          v12 = v50;
          v53 = v50;
          v13 = v56;
          v8 = v54;
          v29 = -2147024882;
          __eh34_try_continuation(4, &loc_180061CF3);
          goto LABEL_60;
        }
      }
    }
    if ( v29 >= 0 )
    {
      if ( v11 >= 0 )
      {
LABEL_75:
        if ( !v46 || !*((_BYTE *)v7 + 328) || v11 < 0 )
          WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(
            (WindowsPerformanceRecorder::CControlManager *)v8,
            v11,
            0);
        if ( v12 )
          (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
        WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording_::_2_::CPerfEventMacro::_CPerfEventMacro(v58);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
        WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v57);
        return (unsigned int)v11;
      }
LABEL_63:
      if ( v12 && *(_QWORD *)(v12 + 8) != *(_QWORD *)(v12 + 16) )
      {
        v31 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v12 + 8);
        v32 = *(WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v12 + 16);
        do
        {
          v33 = *v31;
          FileName = (WindowsPerformanceRecorder::Impl *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(*v31);
          if ( WindowsPerformanceRecorder::Impl::FileExists(FileName, v35) )
          {
            v36 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v33);
            if ( !DeleteFileW(v36) )
            {
              Error = ATL::AtlHresultFromLastError();
              WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
                (WindowsPerformanceRecorder::CControlManager *)v8,
                Error,
                &IID_IControlManager,
                (const unsigned __int16 *)v13,
                0);
              v38 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v33);
              v39 = ATL::AtlHresultFromLastError();
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)3,
                (unsigned __int8)"MergeShutdownRecording",
                (const char *)0x21E,
                v39,
                "Fail to delete %ws",
                v38);
            }
          }
          ++v31;
        }
        while ( v31 != v32 );
        v12 = v53;
        v11 = v48;
        v7 = this;
      }
      v40 = (const char *)lpFileName;
      if ( WindowsPerformanceRecorder::Impl::FileExists((WindowsPerformanceRecorder::Impl *)lpFileName, v30)
        && !DeleteFileW((LPCWSTR)v40) )
      {
        v41 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
          (WindowsPerformanceRecorder::CControlManager *)v8,
          v41,
          &IID_IControlManager,
          (const unsigned __int16 *)v13,
          0);
        v42 = ATL::AtlHresultFromLastError();
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"MergeShutdownRecording",
          (const char *)0x229,
          v42,
          "Fail to delete %ws",
          v40);
      }
      WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
        v8,
        (unsigned int)v11,
        1,
        &IID_IControlManager,
        v13);
      WindowsPerformanceRecorder::TelemetryError(
        (WindowsPerformanceRecorder *)0x2000,
        (unsigned __int64)"MergeShutdownRecording",
        v13,
        (const unsigned __int16 *)(unsigned int)v11,
        Formata);
      goto LABEL_75;
    }
LABEL_60:
    WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
      (WindowsPerformanceRecorder::CControlManager *)v8,
      v29,
      &IID_IControlManager,
      (const unsigned __int16 *)v13,
      0);
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"MergeShutdownRecording",
      (const char *)0x20D,
      v29,
      "%ws",
      v13);
    if ( v11 >= 0 )
      v11 = v29;
    v48 = v11;
    goto LABEL_63;
  }
  ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(
    &v52,
    (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))a3);
  if ( !v52 )
  {
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v52);
    if ( v12 )
      (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
    v50 = 0;
    WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording_::_2_::CPerfEventMacro::_CPerfEventMacro(v58);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
    WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v57);
    return 2147500034LL;
  }
  v49 = 0;
  v28 = (*(__int64 (__fastcall **)(WindowsPerformanceRecorder::CETWProperties *, struct ITraceMergeProperties **))(*(_QWORD *)v52 + 96LL))(
          v52,
          &v49);
  if ( v28 >= 0 )
  {
    v11 = WindowsPerformanceRecorder::CControlManager::MergeEventSessions(
            (WindowsPerformanceRecorder::CControlManager *)v8,
            (struct WindowsPerformanceRecorder::CETWProperties *)v12,
            a2,
            v49,
            Format,
            v23,
            v45);
    v48 = v11;
    v47 = v11;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v52);
    goto LABEL_53;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v52);
  if ( v12 )
    (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
  v50 = 0;
  WindowsPerformanceRecorder::CControlManager::MergeShutdownRecording_::_2_::CPerfEventMacro::_CPerfEventMacro(v58);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpFileName);
  WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v57);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180061780  mov     rax, rsp
0x180061783  mov     [rax+20h], r9
0x180061787  mov     [rax+18h], r8
0x18006178b  mov     [rax+10h], rdx
0x18006178f  mov     [rax+8], rcx
0x180061793  push    rbx
0x180061794  push    rdi
0x180061795  push    r12
0x180061797  push    r13
0x180061799  push    r14
0x18006179b  push    r15
0x18006179d  sub     rsp, 0C8h
0x1800617a4  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800617ac  mov     rdi, r9
0x1800617af  mov     r14, r8
0x1800617b2  mov     r13, rdx
0x1800617b5  mov     r15, rcx
0x1800617b8  mov     qword ptr [rax-68h], 0
0x1800617c0  lea     r12, [rcx-0C0h]
0x1800617c7  mov     [rsp+0F8h+var_78], r12
0x1800617cf  mov     rdx, r12
0x1800617d2  lea     rcx, [rax-68h]
0x1800617d6  call    ??$Acquire@VCControlManager@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCControlManager@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(WindowsPerformanceRecorder::CControlManager *)
0x1800617db  mov     ebx, eax
0x1800617dd  test    eax, eax
0x1800617df  js      loc_1800618FD
0x1800617e5  lea     rcx, [r15-0B8h]
0x1800617ec  mov     rax, [rcx]
0x1800617ef  mov     rax, [rax+18h]
0x1800617f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617f8  lea     rcx, [r15-58h]
0x1800617fc  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x180061801  mov     rdx, r14
0x180061804  lea     rcx, [r15+18h]
0x180061808  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18006180d  test    eax, eax
0x18006180f  jns     short loc_180061818
0x180061811  mov     ebx, eax
0x180061813  jmp     loc_1800618FD
0x180061818  test    rdi, rdi
0x18006181b  jz      short loc_18006182D
0x18006181d  mov     rdx, rdi
0x180061820  lea     rcx, [r15+18h]
0x180061824  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x180061829  test    eax, eax
0x18006182b  js      short loc_180061811
0x18006182d  xor     r14d, r14d
0x180061830  mov     [rsp+0F8h+var_B0], r14d
0x180061835  mov     [rsp+0F8h+var_B4], r14d
0x18006183a  lea     rcx, [rsp+0F8h+lpFileName]; void *
0x18006183f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180061844  nop
0x180061845  mov     rdx, r13
0x180061848  lea     rcx, [rsp+0F8h+lpFileName]
0x18006184d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180061852  nop
0x180061853  jmp     short loc_18006186F
0x180061855  mov     r15, [rsp+0F8h+arg_0]
0x18006185d  mov     r14d, [rsp+0F8h+var_B4]
0x180061862  mov     [rsp+0F8h+var_B0], r14d
0x180061867  mov     r12, [rsp+0F8h+var_78]
0x18006186f  mov     [rsp+0F8h+var_80], r12
0x180061874  lea     rax, off_180090F68
0x18006187b  mov     [rsp+0F8h+var_60], rax
0x180061883  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 4
0x18006188a  jz      short loc_1800618A5
0x18006188c  mov     r8, [rsp+0F8h+lpFileName]
0x180061891  lea     rdx, Perf_MergeShutdownProfiles_Begin
0x180061898  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18006189f  call    McTemplateU0z_EventWriteTransfer
0x1800618a4  nop
0x1800618a5  xor     ebx, ebx
0x1800618a7  mov     [rsp+0F8h+var_88], rbx
0x1800618ac  mov     [rsp+0F8h+var_A0], rbx
0x1800618b1  xor     r13d, r13d
0x1800618b4  mov     [rsp+0F8h+var_70], r13
0x1800618bc  mov     [rsp+0F8h+var_78], r13
0x1800618c4  xor     dil, dil
0x1800618c7  mov     [rsp+0F8h+var_B8], dil
0x1800618cc  test    r14d, r14d
0x1800618cf  js      short loc_180061948
0x1800618d1  mov     rcx, r12; this
0x1800618d4  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x1800618d9  mov     dword ptr [rsp+0F8h+var_A8], eax
0x1800618dd  test    eax, eax
0x1800618df  jns     short loc_180061911
0x1800618e1  lea     rcx, [rsp+0F8h+var_60]
0x1800618e9  call    _WindowsPerformanceRecorder__CControlManager__MergeShutdownRecording____2___CPerfEventMacro___CPerfEventMacro
0x1800618ee  nop
0x1800618ef  lea     rcx, [rsp+0F8h+lpFileName]; this
0x1800618f4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800618f9  mov     ebx, dword ptr [rsp+0F8h+var_A8]
0x1800618fd  lea     rcx, [rsp+0F8h+var_68]; this
0x180061905  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x18006190a  mov     eax, ebx
0x18006190c  jmp     loc_180061F42
0x180061911  mov     eax, [r15+178h]
0x180061918  test    al, 2
0x18006191a  jz      short loc_180061942
0x18006191c  lea     rcx, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x180061923  mov     [rsp+0F8h+var_78], rcx
0x18006192b  test    al, 8
0x18006192d  jz      short loc_180061948
0x18006192f  mov     dil, 1
0x180061932  mov     [rsp+0F8h+var_B8], dil
0x180061937  cmp     [r15+148h], r13b
0x18006193e  jz      short loc_180061948
0x180061940  jmp     short loc_180061970
0x180061942  mov     r14d, 0C5585010h
0x180061948  mov     rcx, r12; this
0x18006194b  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x180061950  test    eax, eax
0x180061952  jns     short loc_180061961
0x180061954  mov     r14d, eax
0x180061957  mov     [rsp+0F8h+var_B0], eax
0x18006195b  mov     [rsp+0F8h+var_B4], eax
0x18006195f  jmp     short loc_180061994
0x180061961  mov     [rsp+0F8h+var_B0], r14d
0x180061966  mov     [rsp+0F8h+var_B4], r14d
0x18006196b  test    r14d, r14d
0x18006196e  js      short loc_180061994
0x180061970  cmp     [rsp+0F8h+arg_8], r13
0x180061978  jz      short loc_180061984
0x18006197a  cmp     [rsp+0F8h+arg_10], r13
0x180061982  jnz     short loc_180061994
0x180061984  mov     r14d, 80004003h
0x18006198a  mov     [rsp+0F8h+var_B0], r14d
0x18006198f  mov     [rsp+0F8h+var_B4], r14d
0x180061994  test    r14d, r14d
0x180061997  js      loc_180061C9E
0x18006199d  mov     edx, [r15+178h]
0x1800619a4  mov     rcx, r12
0x1800619a7  call    ?SetTemporaryTraceDirectoryToCurrentTracingDirectory@CControlManager@WindowsPerformanceRecorder@@AEAAXUCTraceType@IControlInfo@Status@2@@Z; WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(WindowsPerformanceRecorder::Status::IControlInfo::CTraceType)
0x1800619ac  mov     ecx, 1A8h; Size
0x1800619b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800619b6  mov     [rsp+0F8h+var_90], rax
0x1800619bb  mov     rcx, rax; this
0x1800619be  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x1800619c3  mov     rbx, rax
0x1800619c6  mov     [rsp+0F8h+var_88], rax
0x1800619cb  mov     [rsp+0F8h+var_A0], rax
0x1800619d0  mov     r9d, [r15+178h]
0x1800619d7  shr     r9d, 1
0x1800619da  and     r9b, 1; bool
0x1800619de  mov     r8, r12; struct WindowsPerformanceRecorder::CControlManager *
0x1800619e1  mov     rdx, [rsp+0F8h+arg_10]; struct IProfileCollection *
0x1800619e9  mov     rcx, rax; this
0x1800619ec  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x1800619f1  mov     r14d, eax
0x1800619f4  mov     [rsp+0F8h+var_B0], eax
0x1800619f8  test    eax, eax
0x1800619fa  js      loc_180061C9A
0x180061a00  mov     r13, [rbx+140h]
0x180061a07  mov     [rsp+0F8h+var_70], r13
0x180061a0f  mov     r8, r13; char *
0x180061a12  lea     rdx, aMergeshutdownr; "MergeShutdownRecording"
0x180061a19  mov     ecx, 2000h; this
0x180061a1e  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x180061a23  mov     eax, [rbx+100h]
0x180061a29  cmp     eax, 1
0x180061a2c  jnz     short loc_180061A6D
0x180061a2e  test    byte ptr [r15+178h], 20h
0x180061a36  jz      short loc_180061A7C
0x180061a38  xor     r8d, r8d; bool
0x180061a3b  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x180061a3e  mov     rcx, r12; this
0x180061a41  call    ?ValidateWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x180061a46  mov     r14d, eax
0x180061a49  mov     [rsp+0F8h+var_B0], eax
0x180061a4d  test    eax, eax
0x180061a4f  js      loc_180061C9A
0x180061a55  test    dil, dil
0x180061a58  lea     rdi, [r15+148h]
0x180061a5f  jz      short loc_180061A91
0x180061a61  cmp     byte ptr [rdi], 0
0x180061a64  jz      short loc_180061A91
0x180061a66  mov     r14b, [rsp+0F8h+var_B8]
0x180061a6b  jmp     short loc_180061ABD
0x180061a6d  cmp     eax, 2
0x180061a70  jnz     short loc_180061A38
0x180061a72  test    byte ptr [r15+178h], 20h
0x180061a7a  jz      short loc_180061A38
0x180061a7c  mov     r14d, 0C5585010h
0x180061a82  mov     [rsp+0F8h+var_B0], r14d
0x180061a87  mov     [rsp+0F8h+var_B4], r14d
0x180061a8c  jmp     loc_180061C9E
0x180061a91  mov     qword ptr [r15+0E0h], 0
0x180061a9c  mov     qword ptr [r15+0E8h], 0
0x180061aa7  lea     rcx, [r15+0F0h]
0x180061aae  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_KU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,unsigned __int64>>,0>>::clear(void)
0x180061ab3  mov     r14b, [rsp+0F8h+var_B8]
0x180061ab8  test    r14b, r14b
0x180061abb  jz      short loc_180061AC2
0x180061abd  cmp     byte ptr [rdi], 0
0x180061ac0  jnz     short loc_180061B18
0x180061ac2  mov     rdi, [rbx+8]
0x180061ac6  mov     rax, [rbx+10h]
0x180061aca  mov     [rsp+0F8h+var_90], rax
0x180061acf  cmp     rdi, rax
0x180061ad2  jz      short loc_180061B13
0x180061ad4  mov     rcx, [rdi]; this
0x180061ad7  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x180061adc  mov     r9, rax
0x180061adf  mov     rcx, [rdi]; this
0x180061ae2  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180061ae7  mov     r8, rax; unsigned __int16 *
0x180061aea  mov     rdx, r13; unsigned __int16 *
0x180061aed  mov     rcx, r12; this
0x180061af0  call    ?AdjustControlProgressHandler@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG00@Z; WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(ushort const *,ushort const *,ushort const *)
0x180061af5  mov     r14d, eax
0x180061af8  mov     [rsp+0F8h+var_B0], eax
0x180061afc  mov     [rsp+0F8h+var_B4], eax
0x180061b00  test    eax, eax
0x180061b02  js      loc_180061C9E
0x180061b08  add     rdi, 8
0x180061b0c  mov     rax, [rsp+0F8h+var_90]
0x180061b11  jmp     short loc_180061ACF
0x180061b13  mov     r14b, [rsp+0F8h+var_B8]
0x180061b18  mov     r9, [rsp+0F8h+arg_18]; struct ITraceMergeProperties *
0x180061b20  test    r9, r9
0x180061b23  jnz     loc_180061C65
0x180061b29  mov     rdx, [rsp+0F8h+arg_10]
0x180061b31  lea     rcx, [rsp+0F8h+var_90]
0x180061b36  call    ??0?$CComQIPtr@UIProfileCollection2@@$1?_GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(IUnknown *)
0x180061b3b  nop
0x180061b3c  mov     rcx, [rsp+0F8h+var_90]
0x180061b41  test    rcx, rcx
0x180061b44  jnz     short loc_180061BA2
0x180061b46  lea     rcx, [rsp+0F8h+var_90]
0x180061b4b  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180061b50  nop
0x180061b51  test    rbx, rbx
0x180061b54  jz      short loc_180061B69
0x180061b56  mov     rax, [rbx]
0x180061b59  mov     edx, 1
0x180061b5e  mov     rcx, rbx
0x180061b61  mov     rax, [rax]
0x180061b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b69  mov     [rsp+0F8h+var_A0], 0
0x180061b72  lea     rcx, [rsp+0F8h+var_60]
0x180061b7a  call    _WindowsPerformanceRecorder__CControlManager__MergeShutdownRecording____2___CPerfEventMacro___CPerfEventMacro
0x180061b7f  nop
0x180061b80  lea     rcx, [rsp+0F8h+lpFileName]; this
0x180061b85  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061b8a  nop
0x180061b8b  lea     rcx, [rsp+0F8h+var_68]; this
0x180061b93  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x180061b98  mov     eax, 80004002h
0x180061b9d  jmp     loc_180061F42
0x180061ba2  mov     [rsp+0F8h+var_A8], 0
0x180061bab  mov     rax, [rcx]
0x180061bae  lea     rdx, [rsp+0F8h+var_A8]
0x180061bb3  mov     rax, [rax+60h]
0x180061bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bbc  mov     edi, eax
0x180061bbe  test    eax, eax
0x180061bc0  jns     short loc_180061C26
0x180061bc2  lea     rcx, [rsp+0F8h+var_A8]
0x180061bc7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061bcc  nop
0x180061bcd  lea     rcx, [rsp+0F8h+var_90]
0x180061bd2  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180061bd7  nop
0x180061bd8  test    rbx, rbx
0x180061bdb  jz      short loc_180061BF0
0x180061bdd  mov     rax, [rbx]
0x180061be0  mov     edx, 1
0x180061be5  mov     rcx, rbx
0x180061be8  mov     rax, [rax]
0x180061beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bf0  mov     [rsp+0F8h+var_A0], 0
0x180061bf9  lea     rcx, [rsp+0F8h+var_60]
0x180061c01  call    _WindowsPerformanceRecorder__CControlManager__MergeShutdownRecording____2___CPerfEventMacro___CPerfEventMacro
0x180061c06  nop
0x180061c07  lea     rcx, [rsp+0F8h+lpFileName]; this
0x180061c0c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061c11  nop
0x180061c12  lea     rcx, [rsp+0F8h+var_68]; this
0x180061c1a  call    ??1CAPIAutoLock@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock(void)
0x180061c1f  mov     eax, edi
0x180061c21  jmp     loc_180061F42
0x180061c26  mov     byte ptr [rsp+0F8h+var_D0], r14b; bool
0x180061c2b  mov     r9, [rsp+0F8h+var_A8]; struct ITraceMergeProperties *
0x180061c30  mov     r8, [rsp+0F8h+arg_8]; unsigned __int16 *
0x180061c38  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x180061c3b  mov     rcx, r12; this
0x180061c3e  call    ?MergeEventSessions@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@PEAGPEAUITraceMergeProperties@@_N33@Z; WindowsPerformanceRecorder::CControlManager::MergeEventSessions(WindowsPerformanceRecorder::CETWProperties &,ushort *,ITraceMergeProperties *,bool,bool,bool)
0x180061c43  mov     r14d, eax
0x180061c46  mov     [rsp+0F8h+var_B0], eax
0x180061c4a  mov     [rsp+0F8h+var_B4], eax
0x180061c4e  lea     rcx, [rsp+0F8h+var_A8]
0x180061c53  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180061c58  nop
0x180061c59  lea     rcx, [rsp+0F8h+var_90]
0x180061c5e  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180061c63  jmp     short loc_180061C88
0x180061c65  mov     byte ptr [rsp+0F8h+var_D0], r14b; bool
0x180061c6a  mov     r8, [rsp+0F8h+arg_8]; unsigned __int16 *
0x180061c72  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x180061c75  mov     rcx, r12; this
  ... truncated ...
```
