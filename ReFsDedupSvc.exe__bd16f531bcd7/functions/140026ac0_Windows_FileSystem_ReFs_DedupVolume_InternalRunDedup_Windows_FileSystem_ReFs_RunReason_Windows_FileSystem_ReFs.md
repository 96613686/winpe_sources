# Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(Windows::FileSystem::ReFs::RunReason,Windows::FileSystem::ReFs::VolumePersistedSchedule const &,wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>)

- ea: `0x140026ac0`
- end: `0x14002744a`
- name: `?InternalRunDedup@DedupVolume@ReFs@FileSystem@Windows@@AEAA?AVVolumePersistedResults@234@W4RunReason@234@AEBVVolumePersistedSchedule@234@V?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `2442`
- prototype: `Windows::FileSystem::ReFs::VolumePersistedResults *__fastcall(Windows::FileSystem::ReFs::DedupVolume *this, Windows::FileSystem::ReFs::VolumePersistedResults *, int, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400287f4`
- `0x1400288f0`

## callees

- `0x140004870`
- `0x1400057e0`
- `0x1400057f8`
- `0x14000d7b0`
- `0x14000dee8`
- `0x140016bf8`
- `0x140018f9c`
- `0x140019600`
- `0x14001b7f8`
- `0x14001c114`
- `0x14001c148`
- `0x14001fa14`
- `0x140022380`
- `0x14002246c`
- `0x1400235cc`
- `0x140023b04`
- `0x140023f88`
- `0x1400246a0`
- `0x140025ea8`
- `0x140025f5c`
- `0x140026894`
- `0x140026ac0`
- `0x1400276fc`
- `0x140027d2c`
- `0x14002879c`
- `0x140028c48`
- `0x140029c4c`
- `0x14002b88c`
- `0x14002b8d8`
- `0x14002c200`
- `0x14002cc40`
- `0x14002cd10`
- `0x14002d37c`
- `0x140040fd4`
- `0x14005fa08`
- `0x14005fb54`
- `0x1400627cc`
- `0x1400628c4`
- `0x1400628f8`
- `0x1400656dc`
- `0x14007a6fc`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140027178`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140027178`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140026e89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140026e89`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140026e4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140026e4a`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140026ccc`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400272d4`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140026ccc`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400272d4`

## string_xrefs

- `0x140026c80`: `Dedup operation already running`
- `0x14002742c`: `Dedup operation already running`
- `0x140026dbb`: `Unable to get compression status`
- `0x140026fdc`: `class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)`
- `0x14002702b`: `class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)`
- `0x14002714b`: `class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)`
- `0x1400271b2`: `class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)`
- `0x1400271f1`: `Failed to cancel compression`
- `0x140027221`: `Failed wait on compression completion`

## pseudocode

```c
Windows::FileSystem::ReFs::VolumePersistedResults *__fastcall Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup(
        Windows::FileSystem::ReFs::DedupVolume *this,
        Windows::FileSystem::ReFs::VolumePersistedResults *a2,
        int a3,
        _QWORD *a4,
        _QWORD *a5)
{
  char v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rax
  char v11; // al
  const WCHAR *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int *Status; // rax
  unsigned int *CompressionStatus; // rax
  unsigned int v17; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v19; // rdx
  int v20; // rax^4
  __int64 v21; // rcx
  _DWORD *v22; // rcx
  CDedupOptimizer *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  _QWORD *v26; // rax
  __int128 v27; // xmm1
  __int128 v28; // xmm2
  __int128 v29; // xmm3
  __int128 v30; // xmm4
  __int64 v31; // rax
  int v32; // ecx
  void *v33; // rdx
  char *v34; // r12
  unsigned int v35; // eax
  DWORD v36; // r15d
  _QWORD *v37; // rax
  __int64 v38; // rax
  const WCHAR *v39; // rax
  unsigned int v40; // r8d
  const char *v41; // r9
  wil *v43; // rcx
  const char *v45; // r9
  unsigned int v46; // eax
  __int64 v47; // rax
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  _QWORD *v53; // rdx
  __int64 v54; // rax
  char *v55; // [rsp+28h] [rbp-210h]
  char *v56; // [rsp+28h] [rbp-210h]
  char *v57; // [rsp+28h] [rbp-210h]
  char *v58; // [rsp+28h] [rbp-210h]
  char *v59; // [rsp+30h] [rbp-208h] BYREF
  __int64 v60; // [rsp+40h] [rbp-1F8h] BYREF
  const char *v61; // [rsp+48h] [rbp-1F0h]
  const char *v62; // [rsp+50h] [rbp-1E8h]
  struct _FILETIME pftDueTime[2]; // [rsp+60h] [rbp-1D8h] BYREF
  const char *v64; // [rsp+70h] [rbp-1C8h]
  struct _TP_TIMER *v65; // [rsp+80h] [rbp-1B8h] BYREF
  int v66; // [rsp+88h] [rbp-1B0h]
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+90h] [rbp-1A8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+98h] [rbp-1A0h] BYREF
  _BYTE v69[16]; // [rsp+A0h] [rbp-198h] BYREF
  char *v70; // [rsp+B0h] [rbp-188h] BYREF
  char v71; // [rsp+B8h] [rbp-180h]
  __int128 v72; // [rsp+C0h] [rbp-178h] BYREF
  __int128 v73; // [rsp+D0h] [rbp-168h]
  __int128 v74; // [rsp+E0h] [rbp-158h]
  __int128 v75; // [rsp+F0h] [rbp-148h]
  __int128 v76; // [rsp+100h] [rbp-138h]
  void *v77[4]; // [rsp+110h] [rbp-128h] BYREF
  char v78; // [rsp+130h] [rbp-108h] BYREF
  char v79; // [rsp+131h] [rbp-107h]
  __int16 v80; // [rsp+132h] [rbp-106h]
  int v81; // [rsp+134h] [rbp-104h]
  int v82; // [rsp+138h] [rbp-100h]
  int v83; // [rsp+13Ch] [rbp-FCh]
  __int64 v84; // [rsp+140h] [rbp-F8h]
  _BYTE v85[24]; // [rsp+148h] [rbp-F0h] BYREF
  _BYTE v86[32]; // [rsp+160h] [rbp-D8h] BYREF
  _BYTE v87[32]; // [rsp+180h] [rbp-B8h] BYREF
  _OWORD v88[4]; // [rsp+1A0h] [rbp-98h] BYREF
  __int128 v89; // [rsp+1E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  LODWORD(v60) = a3;
  LODWORD(v65) = Windows::FileSystem::ReFs::DedupVolume::Kind(this);
  Windows::FileSystem::ReFs::VolumePersistedResults::VolumePersistedResults(a2);
  v66 = 1;
  Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>(
    v77,
    a4[1] - *a4);
  memcpy_0(v77[0], (const void *)*a4, a4[1] - *a4);
  v8 = 0;
  BYTE1(v59) = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(
    &v70,
    (char *)this + 56);
  LOBYTE(v59) = *(_BYTE *)(*((_QWORD *)this + 20) + 28LL);
  std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v70);
  v9 = *((_QWORD *)this + 26);
  if ( v9 )
  {
    LODWORD(v72) = 0;
    *((_QWORD *)&v72 + 1) = 0;
    v73 = 0u;
    v74 = 0u;
    v75 = 0u;
    *(_QWORD *)&v76 = 0;
    BYTE8(v76) = 0;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 8LL))(v9, &v72);
    if ( (_DWORD)v72 == 6 )
    {
      v10 = *((_QWORD *)this + 26);
      if ( !v10 || *(_DWORD *)(v10 + 8) == 2 || !*(_BYTE *)(v10 + 473) )
      {
        v45 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942570LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
          v45,
          (int)"Dedup operation already running",
          v55);
      }
      Windows::FileSystem::ReFs::DedupVolume::Cancel(this);
    }
  }
  v70 = (char *)this + 24;
  v71 = 0;
  v11 = std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::try_lock(&v70);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x226,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
    (const char *)0x800700AALL,
    v11 ^ 1,
    (bool)"Dedup operation already running",
    v59);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
  if ( !GetDiskFreeSpaceExW(v12, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x22A, v13, v14);
  *(_ULARGE_INTEGER *)(*(_QWORD *)a2 + 56LL) = TotalNumberOfBytes;
  *(_QWORD *)(*(_QWORD *)a2 + 64LL) = TotalNumberOfBytes.QuadPart - TotalNumberOfFreeBytes.QuadPart;
  if ( (_BYTE)v59 )
    *((_BYTE *)v77[0] + 73) = 1;
  *(_DWORD *)(*(_QWORD *)a2 + 44LL) = Windows::FileSystem::ReFs::layer_cast<enum RefsDedup::DedupType,enum winrt::Windows::Private::Storage::DedupKind>(&v65);
  *(_DWORD *)(*(_QWORD *)a2 + 48LL) = v60;
  Status = (unsigned int *)RefsDedup::GetStatus(pftDueTime, *((_QWORD *)this + 26), *(_QWORD *)a2 + 72LL);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x23C,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
    (const char *)*Status,
    (int)"Unable to get dedup status",
    v56);
  if ( Windows::FileSystem::ReFs::DedupVolume::CompressionEnabled(this)
    && *(_DWORD *)(*(_QWORD *)a2 + 156LL) != *(_DWORD *)(*a4 + 36LL) )
  {
    CompressionStatus = (unsigned int *)RefsDedup::GetCompressionStatus(
                                          pftDueTime,
                                          (char *)this + 104,
                                          *(_QWORD *)a2 + 152LL);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
      (const char *)*CompressionStatus,
      (int)"Unable to get compression status",
      v57);
  }
  v17 = Windows::FileSystem::ReFs::layer_cast<enum RefsDedup::DedupType,enum winrt::Windows::Private::Storage::DedupKind>(&v65);
  Windows::FileSystem::ReFs::EventLog::DedupJobStarted(v17, (unsigned int)v60, (char *)this + 72, v77, a2);
  std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(
    v69,
    (char *)this + 184);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x249,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
    (const char *)*((unsigned int *)this + 50),
    (int)"In error recovery",
    v57);
  try
  {
    ThreadpoolTimer = CreateThreadpoolTimer(Windows::FileSystem::ReFs::DedupVolume::NativeTimerCallBack, this, 0);
    v65 = ThreadpoolTimer;
    v19 = *(_QWORD *)(*a4 + 64LL);
    if ( v19 )
    {
      pftDueTime[0] = (struct _FILETIME)-v19;
      pftDueTime[1] = 0;
      SetThreadpoolTimerEx(ThreadpoolTimer, pftDueTime, 0, 0);
    }
    winrt::clock::now(&v60);
    v20 = HIDWORD(v60);
    v21 = *(_QWORD *)a2;
    *(_DWORD *)(v21 + 24) = v60;
    *(_DWORD *)(v21 + 28) = v20;
    v78 = 1;
    v22 = (_DWORD *)*a4;
    if ( *(_BYTE *)(*a4 + 73LL) || (v79 = 0, (_BYTE)v59) )
      v79 = 1;
    v80 = 0;
    v81 = v22[19];
    v82 = v22[20];
    v83 = v22[21];
    v84 = *((_QWORD *)v22 + 11);
    Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::GetExcludedFolders<std::wstring>(v22, v85);
    Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::GetExcludedExtensions<std::wstring>(*a4, v86);
    LODWORD(v72) = 0;
    *((_QWORD *)&v72 + 1) = 0;
    v73 = 0u;
    v74 = 0u;
    v75 = 0u;
    *(_QWORD *)&v76 = 0;
    BYTE8(v76) = 0;
    v23 = (CDedupOptimizer *)*((_QWORD *)this + 26);
    if ( v23 )
    {
      if ( *((_DWORD *)v23 + 2) != 2 )
      {
        v25 = CDedupOptimizer::Run(v23, (const struct RefsDedup::RunParameters *)&v78, (bool *)&v59 + 1);
        ConvertWin32ToDedupHresult(&v60, v25);
        v8 = BYTE1(v59);
LABEL_26:
        pftDueTime[0].dwLowDateTime = 614;
        pftDueTime[0].dwHighDateTime = 9;
        pftDueTime[1] = (struct _FILETIME)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp";
        v64 = "class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::In"
              "ternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePers"
              "istedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)";
        Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(this, v69, v60, pftDueTime);
        v26 = (_QWORD *)RefsDedup::GetStatus(pftDueTime, *((_QWORD *)this + 26), &v72);
        v60 = 0x900000267LL;
        v61 = "onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp";
        v62 = "class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::In"
              "ternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePers"
              "istedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)";
        Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(this, v69, *v26, &v60);
        v27 = v73;
        v28 = v74;
        v29 = v75;
        v30 = v76;
        v31 = *(_QWORD *)a2;
        *(_OWORD *)(v31 + 72) = v72;
        *(_OWORD *)(v31 + 88) = v27;
        *(_OWORD *)(v31 + 104) = v28;
        *(_OWORD *)(v31 + 120) = v29;
        *(_OWORD *)(v31 + 136) = v30;
        if ( (_BYTE)v59 && v8 )
          Windows::FileSystem::ReFs::DedupVolume::SetFirstRun(this, 0);
        v32 = 0;
        if ( (_DWORD)v72 == 3 )
          v32 = -2147023673;
        *(_DWORD *)(*(_QWORD *)a2 + 40LL) = v32;
        if ( *(int *)(*(_QWORD *)a2 + 40LL) >= 0 && Windows::FileSystem::ReFs::DedupVolume::CompressionEnabled(this) )
        {
          memset_0(v88, 0, 0x50u);
          wil::details::ResetEvent(*((wil::details **)this + 27), v33);
          if ( *(_DWORD *)(*a4 + 36LL) < 2u )
          {
            ConvertWin32ToDedupHresult(&v60, 0);
            v34 = (char *)this + 104;
          }
          else
          {
            v34 = (char *)this + 104;
            v35 = DedupUtil::CompressVolume((char *)this + 104);
            ConvertWin32ToDedupHresult(&v60, v35);
          }
          pftDueTime[0].dwLowDateTime = 635;
          pftDueTime[0].dwHighDateTime = 13;
          pftDueTime[1] = (struct _FILETIME)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp";
          v64 = "class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::"
                "InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::Volume"
                "PersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)";
          Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(this, v69, v60, pftDueTime);
          while ( 1 )
          {
            v36 = WaitForSingleObject(*((HANDLE *)this + 27), 0xEA60u);
            v37 = (_QWORD *)RefsDedup::GetCompressionStatus(pftDueTime, (char *)this + 104, v88);
            v60 = 0x1100000280LL;
            v61 = "onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp";
            v62 = "class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume"
                  "::InternalRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::Vo"
                  "lumePersistedSchedule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)";
            Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(this, v69, *v37, &v60);
            if ( !v36 )
              break;
            wil::details::in1diag3::FailFast_IfMsg(
              retaddr,
              (void *)0x28A,
              (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
              (const char *)(v36 != 258),
              (bool)"Failed wait on compression completion",
              v58);
            if ( !BYTE8(v89) )
              goto LABEL_40;
          }
          wil::details::in1diag3::FailFast_IfMsg(
            retaddr,
            (void *)0x285,
            (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp",
            (const char *)(BYTE8(v89) != 0),
            (bool)"Failed to cancel compression",
            v58);
          *(_DWORD *)(*(_QWORD *)a2 + 40LL) = -2147217403;
LABEL_40:
          v38 = *(_QWORD *)a2;
          *(_OWORD *)(v38 + 152) = v88[0];
          *(_OWORD *)(v38 + 168) = v88[1];
          *(_OWORD *)(v38 + 184) = v88[2];
          *(_OWORD *)(v38 + 200) = v88[3];
          *(_OWORD *)(v38 + 216) = v89;
        }
        else
        {
          v34 = (char *)this + 104;
        }
        *(_QWORD *)(*(_QWORD *)a2 + 32LL) = *(_QWORD *)winrt::clock::now(pftDueTime);
        v39 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
        if ( !GetDiskFreeSpaceExW(v39, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
          wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x298, v40, v41);
        *(_QWORD *)(*(_QWORD *)a2 + 64LL) = TotalNumberOfBytes.QuadPart - TotalNumberOfFreeBytes.QuadPart;
        if ( *a5 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a5 + 32LL))(*a5, *(unsigned int *)(*(_QWORD *)a2 + 40LL));
        Windows::FileSystem::ReFs::DedupVolume::SaveResults(this, a2);
        Windows::FileSystem::ReFs::VolumePersistedSchedule::LoadFrom(
          (struct Windows::FileSystem::ReFs::VolumePersistedSchedule *)v87,
          (__int64)this + 72);
        *(_OWORD *)&pftDueTime[0].dwLowDateTime = *(_OWORD *)Windows::FileSystem::ReFs::VolumePersistedSchedule::NextRunTime(
                                                               v87,
                                                               &v60,
                                                               (char *)this + 72);
        Windows::FileSystem::ReFs::EventLog::DedupJobStopped((char *)this + 72, a2, pftDueTime);
        v66 = 0;
        goto LABEL_52;
      }
      v24 = 0;
    }
    else
    {
      v24 = 87;
    }
    ConvertWin32ToDedupHresult(&v60, v24);
    goto LABEL_26;
  }
  catch ( ... )
  {
    v46 = wil::ResultFromCaughtException(v43);
    v47 = Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::operator->(
            a2,
            v46);
    *(_DWORD *)(v47 + 40) = v48;
    v49 = winrt::clock::now(pftDueTime);
    v50 = wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
            &v60,
            v49);
    v51 = winrt::file_time::operator _FILETIME(v50, &v65);
    v52 = Windows::FileSystem::ReFs::VolumePersistedState<Windows::FileSystem::ReFs::VolumePersistedResults,Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSvcResults>::operator->(
            a2,
            v51);
    *(_QWORD *)(v52 + 32) = *v53;
    v54 = Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup_::_39_::_lambda_1_::_lambda_1_(pftDueTime, this, a2);
    v60 = 0x9000002AELL;
    v61 = "onecore\\base\\fs\\refsdedupsvc\\exe\\dedupvolume.cpp";
    v62 = "class Windows::FileSystem::ReFs::VolumePersistedResults __cdecl Windows::FileSystem::ReFs::DedupVolume::Intern"
          "alRunDedup(enum Windows::FileSystem::ReFs::RunReason,const class Windows::FileSystem::ReFs::VolumePersistedSch"
          "edule &,class wil::com_ptr_t<struct ITaskHandlerStatus,struct wil::err_exception_policy>)";
    Microsoft::Win32::Service::try_and_log_if_failed__Windows::FileSystem::ReFs::DedupVolume::InternalRunDedup_::_39_::_lambda_1___(
      v54,
      &v60);
    Windows::FileSystem::ReFs::EventLog::DedupJobFailed(
      (Windows::FileSystem::ReFs::DedupVolume *)((char *)this + 72),
      a2);
    throw;
  }
LABEL_52:
  std::vector<unsigned char>::_Tidy(v87);
  RefsDedup::RunParameters::~RunParameters((RefsDedup::RunParameters *)&v78);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v65);
  std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(v69);
  std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v70);
  std::vector<unsigned char>::_Tidy(v77);
  wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(a5);
  return a2;
}

```

## disassembly

```asm
0x140026ac0  mov     rax, rsp
0x140026ac3  mov     [rax+18h], rbx
0x140026ac7  mov     [rax+20h], rsi
0x140026acb  mov     [rax+10h], rdx
0x140026acf  mov     [rax+8], rcx
0x140026ad3  push    rdi
0x140026ad4  push    r12
0x140026ad6  push    r13
0x140026ad8  push    r14
0x140026ada  push    r15
0x140026adc  sub     rsp, 210h
0x140026ae3  movaps  xmmword ptr [rax-38h], xmm6
0x140026ae7  mov     rax, cs:__security_cookie
0x140026aee  xor     rax, rsp
0x140026af1  mov     [rsp+238h+var_48], rax
0x140026af9  mov     r15, r9
0x140026afc  mov     dword ptr [rsp+238h+var_1F8], r8d
0x140026b01  mov     rdi, rdx
0x140026b04  mov     rbx, rcx
0x140026b07  mov     r14d, 1
0x140026b0d  mov     [rsp+238h+var_1B0], r14d
0x140026b15  call    ?Kind@DedupVolume@ReFs@FileSystem@Windows@@QEAA?AW4DedupKind@Storage@Private@4winrt@@XZ; Windows::FileSystem::ReFs::DedupVolume::Kind(void)
0x140026b1a  mov     dword ptr [rsp+238h+var_1B8], eax
0x140026b21  mov     rcx, rdi; this
0x140026b24  call    ??0VolumePersistedResults@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::VolumePersistedResults::VolumePersistedResults(void)
0x140026b29  nop
0x140026b2a  mov     [rsp+238h+var_1B0], r14d
0x140026b32  mov     rdx, [r15+8]
0x140026b36  sub     rdx, [r15]
0x140026b39  lea     rcx, [rsp+238h+var_128]
0x140026b41  call    ??0?$BlobMem@UOnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@_K@Z; Windows::FileSystem::ReFs::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>::BlobMem<Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule>(unsigned __int64)
0x140026b46  mov     r8, [r15+8]
0x140026b4a  sub     r8, [r15]; Size
0x140026b4d  mov     rdx, [r15]; Src
0x140026b50  mov     rcx, [rsp+238h+var_128]; void *
0x140026b58  call    memcpy_0
0x140026b5d  nop
0x140026b5e  xor     esi, esi
0x140026b60  mov     r12b, sil
0x140026b63  mov     byte ptr [rsp+238h+var_208+1], sil
0x140026b68  mov     qword ptr [rsp+238h+TotalNumberOfBytes], rsi
0x140026b70  mov     qword ptr [rsp+238h+TotalNumberOfFreeBytes], rsi
0x140026b78  lea     rdx, [rbx+38h]
0x140026b7c  lea     rcx, [rsp+238h+var_188]
0x140026b84  call    ??0?$shared_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@AEAVOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@Z; std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(Microsoft::Win32::Locks::OwnerTrackingSharedMutex &)
0x140026b89  mov     rax, [rbx+0A0h]
0x140026b90  mov     al, [rax+1Ch]
0x140026b93  mov     byte ptr [rsp+238h+var_208], al; char *
0x140026b97  lea     rcx, [rsp+238h+var_188]
0x140026b9f  call    ??1?$shared_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@XZ; std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(void)
0x140026ba4  mov     rcx, [rbx+0D0h]
0x140026bab  xorps   xmm6, xmm6
0x140026bae  test    rcx, rcx
0x140026bb1  jz      loc_140026C54
0x140026bb7  mov     dword ptr [rsp+238h+var_178], esi
0x140026bbe  mov     qword ptr [rsp+238h+var_178+8], rsi
0x140026bc6  mov     qword ptr [rsp+238h+var_168], rsi
0x140026bce  mov     qword ptr [rsp+238h+var_168+8], rsi
0x140026bd6  mov     qword ptr [rsp+238h+var_158], rsi
0x140026bde  mov     qword ptr [rsp+238h+var_158+8], rsi
0x140026be6  mov     qword ptr [rsp+238h+var_148], rsi
0x140026bee  mov     qword ptr [rsp+238h+var_148+8], rsi
0x140026bf6  movsd   qword ptr [rsp+238h+var_138], xmm6
0x140026bff  mov     byte ptr [rsp+238h+var_138+8], sil
0x140026c07  mov     rax, [rcx]
0x140026c0a  lea     rdx, [rsp+238h+var_178]
0x140026c12  mov     rax, [rax+8]
0x140026c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026c1b  cmp     dword ptr [rsp+238h+var_178], 6
0x140026c23  jnz     short loc_140026C54
0x140026c25  mov     rax, [rbx+0D0h]
0x140026c2c  test    rax, rax
0x140026c2f  jz      loc_140027417
0x140026c35  cmp     dword ptr [rax+8], 2
0x140026c39  jz      loc_140027417
0x140026c3f  cmp     [rax+1D9h], sil
0x140026c46  jz      loc_140027417
0x140026c4c  mov     rcx, rbx; this
0x140026c4f  call    ?Cancel@DedupVolume@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::DedupVolume::Cancel(void)
0x140026c54  lea     rax, [rbx+18h]
0x140026c58  mov     [rsp+238h+var_188], rax
0x140026c60  mov     [rsp+238h+var_180], sil
0x140026c68  lea     rcx, [rsp+238h+var_188]
0x140026c70  call    ?try_lock@?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA_NXZ; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::try_lock(void)
0x140026c75  xor     al, r14b
0x140026c78  mov     rcx, [rsp+238h]; this
0x140026c80  lea     rdx, aDedupOperation; "Dedup operation already running"
0x140026c87  mov     [rsp+238h+var_210], rdx; char *
0x140026c8c  mov     [rsp+238h+var_218], al; char
0x140026c90  mov     r9d, 800700AAh; char *
0x140026c96  lea     rsi, aOnecoreBaseFsR_17; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x140026c9d  mov     r8, rsi; unsigned int
0x140026ca0  mov     edx, 226h; void *
0x140026ca5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140026caa  lea     r13, [rbx+48h]
0x140026cae  lea     rcx, [r13+20h]
0x140026cb2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140026cb7  lea     r9, [rsp+238h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x140026cbf  lea     r8, [rsp+238h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x140026cc7  xor     edx, edx; lpFreeBytesAvailableToCaller
0x140026cc9  mov     rcx, rax; lpDirectoryName
0x140026ccc  call    cs:__imp_GetDiskFreeSpaceExW
0x140026cd3  nop     dword ptr [rax+rax+00h]
0x140026cd8  mov     rcx, [rsp+238h]; this
0x140026ce0  test    eax, eax
0x140026ce2  jnz     short loc_140026CEE
0x140026ce4  mov     edx, 22Ah; void *
0x140026ce9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140026cee  mov     rcx, [rdi]
0x140026cf1  mov     rax, qword ptr [rsp+238h+TotalNumberOfBytes]
0x140026cf9  mov     [rcx+38h], rax
0x140026cfd  mov     rcx, qword ptr [rsp+238h+TotalNumberOfBytes]
0x140026d05  sub     rcx, qword ptr [rsp+238h+TotalNumberOfFreeBytes]
0x140026d0d  mov     rax, [rdi]
0x140026d10  mov     [rax+40h], rcx
0x140026d14  cmp     byte ptr [rsp+238h+var_208], 0
0x140026d19  jz      short loc_140026D27
0x140026d1b  mov     rax, [rsp+238h+var_128]
0x140026d23  mov     [rax+49h], r14b
0x140026d27  lea     rcx, [rsp+238h+var_1B8]
0x140026d2f  call    ??$layer_cast@W4DedupType@RefsDedup@@W4DedupKind@Storage@Private@Windows@winrt@@@ReFs@FileSystem@Windows@@YA?AW4DedupType@RefsDedup@@AEBW4DedupKind@Storage@Private@2winrt@@@Z; Windows::FileSystem::ReFs::layer_cast<RefsDedup::DedupType,winrt::Windows::Private::Storage::DedupKind>(winrt::Windows::Private::Storage::DedupKind const &)
0x140026d34  mov     rcx, [rdi]
0x140026d37  mov     [rcx+2Ch], eax
0x140026d3a  mov     rax, [rdi]
0x140026d3d  mov     ecx, dword ptr [rsp+238h+var_1F8]
0x140026d41  mov     [rax+30h], ecx
0x140026d44  mov     r8, [rdi]
0x140026d47  add     r8, 48h ; 'H'
0x140026d4b  mov     rdx, [rbx+0D0h]
0x140026d52  lea     rcx, [rsp+238h+pftDueTime]
0x140026d57  call    ?GetStatus@RefsDedup@@YA?AU?$pair@JW4DedupErrorType@RefsDedup@@@std@@PEAUDEDUP_HANDLE__@1@AEAURunStatus@1@@Z; RefsDedup::GetStatus(RefsDedup::DEDUP_HANDLE__ *,RefsDedup::RunStatus &)
0x140026d5c  mov     rcx, [rsp+238h]; this
0x140026d64  lea     rdx, aUnableToGetDed; "Unable to get dedup status"
0x140026d6b  mov     qword ptr [rsp+238h+var_218], rdx; int
0x140026d70  mov     r9d, [rax]; char *
0x140026d73  mov     r8, rsi; unsigned int
0x140026d76  mov     edx, 23Ch; void *
0x140026d7b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140026d80  mov     rcx, rbx; this
0x140026d83  call    ?CompressionEnabled@DedupVolume@ReFs@FileSystem@Windows@@AEAA_NXZ; Windows::FileSystem::ReFs::DedupVolume::CompressionEnabled(void)
0x140026d88  test    al, al
0x140026d8a  jz      short loc_140026DD7
0x140026d8c  mov     r8, [rdi]
0x140026d8f  mov     rax, [r15]
0x140026d92  mov     ecx, [rax+24h]
0x140026d95  cmp     [r8+9Ch], ecx
0x140026d9c  jz      short loc_140026DD7
0x140026d9e  add     r8, 98h
0x140026da5  lea     rdx, [rbx+68h]
0x140026da9  lea     rcx, [rsp+238h+pftDueTime]
0x140026dae  call    ?GetCompressionStatus@RefsDedup@@YA?AU?$pair@JW4DedupErrorType@RefsDedup@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEAUCompressionInfo@1@@Z; RefsDedup::GetCompressionStatus(std::wstring const &,RefsDedup::CompressionInfo &)
0x140026db3  mov     rcx, [rsp+238h]; this
0x140026dbb  lea     rdx, aUnableToGetCom; "Unable to get compression status"
0x140026dc2  mov     qword ptr [rsp+238h+var_218], rdx; int
0x140026dc7  mov     r9d, [rax]; char *
0x140026dca  mov     r8, rsi; unsigned int
0x140026dcd  mov     edx, 243h; void *
0x140026dd2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140026dd7  lea     rcx, [rsp+238h+var_1B8]
0x140026ddf  call    ??$layer_cast@W4DedupType@RefsDedup@@W4DedupKind@Storage@Private@Windows@winrt@@@ReFs@FileSystem@Windows@@YA?AW4DedupType@RefsDedup@@AEBW4DedupKind@Storage@Private@2winrt@@@Z; Windows::FileSystem::ReFs::layer_cast<RefsDedup::DedupType,winrt::Windows::Private::Storage::DedupKind>(winrt::Windows::Private::Storage::DedupKind const &)
0x140026de4  mov     ecx, eax
0x140026de6  mov     qword ptr [rsp+238h+var_218], rdi
0x140026deb  lea     r9, [rsp+238h+var_128]
0x140026df3  mov     r8, r13
0x140026df6  mov     edx, dword ptr [rsp+238h+var_1F8]
0x140026dfa  call    ?DedupJobStarted@EventLog@ReFs@FileSystem@Windows@@SAXW4DedupType@RefsDedup@@W4RunReason@234@AEBVVolumePath@234@AEBVVolumePersistedSchedule@234@AEBVVolumePersistedResults@234@@Z; Windows::FileSystem::ReFs::EventLog::DedupJobStarted(RefsDedup::DedupType,Windows::FileSystem::ReFs::RunReason,Windows::FileSystem::ReFs::VolumePath const &,Windows::FileSystem::ReFs::VolumePersistedSchedule const &,Windows::FileSystem::ReFs::VolumePersistedResults const &)
0x140026dff  lea     rdx, [rbx+0B8h]
0x140026e06  lea     rcx, [rsp+238h+var_198]
0x140026e0e  call    ??0?$shared_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@AEAVOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@Z; std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(Microsoft::Win32::Locks::OwnerTrackingSharedMutex &)
0x140026e13  nop
0x140026e14  mov     rcx, [rsp+238h]; this
0x140026e1c  lea     rax, aInErrorRecover; "In error recovery"
0x140026e23  mov     qword ptr [rsp+238h+var_218], rax; int
0x140026e28  mov     r9d, [rbx+0C8h]; char *
0x140026e2f  mov     r8, rsi; unsigned int
0x140026e32  mov     edx, 249h; void *
0x140026e37  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140026e3c  nop
0x140026e3d  xor     r8d, r8d; pcbe
0x140026e40  mov     rdx, rbx; pv
0x140026e43  lea     rcx, ?NativeTimerCallBack@DedupVolume@ReFs@FileSystem@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140026e4a  call    cs:__imp_CreateThreadpoolTimer
0x140026e51  nop     dword ptr [rax+rax+00h]
0x140026e56  mov     [rsp+238h+var_1B8], rax
0x140026e5e  mov     rcx, [r15]
0x140026e61  mov     rdx, [rcx+40h]
0x140026e65  test    rdx, rdx
0x140026e68  jz      short loc_140026E95
0x140026e6a  neg     rdx
0x140026e6d  mov     qword ptr [rsp+238h+pftDueTime.dwLowDateTime], rdx
0x140026e72  mov     qword ptr [rsp+238h+pftDueTime.dwLowDateTime+8], 0
0x140026e7b  xor     r9d, r9d; msWindowLength
0x140026e7e  xor     r8d, r8d; msPeriod
0x140026e81  lea     rdx, [rsp+238h+pftDueTime]; pftDueTime
0x140026e86  mov     rcx, rax; pti
0x140026e89  call    cs:__imp_SetThreadpoolTimerEx
0x140026e90  nop     dword ptr [rax+rax+00h]
0x140026e95  lea     rcx, [rsp+238h+var_1F8]
0x140026e9a  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x140026e9f  mov     rax, [rsp+238h+var_1F8]
0x140026ea4  mov     rcx, [rdi]
0x140026ea7  mov     [rcx+18h], eax
0x140026eaa  shr     rax, 20h
0x140026eae  mov     [rcx+1Ch], eax
0x140026eb1  mov     [rsp+238h+var_108], r14b
0x140026eb9  mov     rcx, [r15]
0x140026ebc  xor     eax, eax
0x140026ebe  cmp     [rcx+49h], al
0x140026ec1  jnz     short loc_140026ED0
0x140026ec3  cmp     byte ptr [rsp+238h+var_208], al
0x140026ec7  mov     [rsp+238h+var_107], al
0x140026ece  jz      short loc_140026ED8
0x140026ed0  mov     [rsp+238h+var_107], r14b
0x140026ed8  mov     [rsp+238h+var_106], ax
0x140026ee0  mov     eax, [rcx+4Ch]
0x140026ee3  mov     [rsp+238h+var_104], eax
0x140026eea  mov     eax, [rcx+50h]
0x140026eed  mov     [rsp+238h+var_100], eax
0x140026ef4  mov     eax, [rcx+54h]
0x140026ef7  mov     [rsp+238h+var_FC], eax
0x140026efe  mov     rax, [rcx+58h]
0x140026f02  mov     [rsp+238h+var_F8], rax
0x140026f0a  lea     rdx, [rsp+238h+var_F0]
0x140026f12  call    ??$GetExcludedFolders@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@OnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::GetExcludedFolders<std::wstring>(void)
0x140026f17  nop
0x140026f18  lea     rdx, [rsp+238h+var_D8]
0x140026f20  mov     rcx, [r15]
0x140026f23  call    ??$GetExcludedExtensions@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@OnDiskSchedule@PersistedData_v1@ReFs@FileSystem@Windows@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Windows::FileSystem::ReFs::PersistedData_v1::OnDiskSchedule::GetExcludedExtensions<std::wstring>(void)
0x140026f28  nop
0x140026f29  xor     eax, eax
0x140026f2b  mov     dword ptr [rsp+238h+var_178], eax
0x140026f32  mov     qword ptr [rsp+238h+var_178+8], rax
0x140026f3a  mov     qword ptr [rsp+238h+var_168], rax
0x140026f42  mov     qword ptr [rsp+238h+var_168+8], rax
0x140026f4a  mov     qword ptr [rsp+238h+var_158], rax
0x140026f52  mov     qword ptr [rsp+238h+var_158+8], rax
0x140026f5a  mov     qword ptr [rsp+238h+var_148], rax
0x140026f62  mov     qword ptr [rsp+238h+var_148+8], rax
0x140026f6a  movsd   qword ptr [rsp+238h+var_138], xmm6
0x140026f73  mov     byte ptr [rsp+238h+var_138+8], al
0x140026f7a  mov     rcx, [rbx+0D0h]; this
0x140026f81  test    rcx, rcx
0x140026f84  jnz     short loc_140026F95
0x140026f86  lea     edx, [rax+57h]
0x140026f89  lea     rcx, [rsp+238h+var_1F8]
0x140026f8e  call    ConvertWin32ToDedupHresult
0x140026f93  jmp     short loc_140026FC2
0x140026f95  cmp     dword ptr [rcx+8], 2
0x140026f99  jnz     short loc_140026F9F
0x140026f9b  xor     edx, edx
0x140026f9d  jmp     short loc_140026F89
0x140026f9f  lea     r8, [rsp+238h+var_208+1]; bool *
0x140026fa4  lea     rdx, [rsp+238h+var_108]; struct RefsDedup::RunParameters *
0x140026fac  call    ?Run@CDedupOptimizer@@QEAAKAEBURunParameters@RefsDedup@@AEA_N@Z; CDedupOptimizer::Run(RefsDedup::RunParameters const &,bool &)
0x140026fb1  mov     edx, eax
0x140026fb3  lea     rcx, [rsp+238h+var_1F8]
0x140026fb8  call    ConvertWin32ToDedupHresult
0x140026fbd  mov     r12b, byte ptr [rsp+238h+var_208+1]
0x140026fc2  mov     r8, [rsp+238h+var_1F8]
0x140026fc7  mov     [rsp+238h+pftDueTime.dwLowDateTime], 266h
0x140026fcf  mov     [rsp+238h+pftDueTime.dwHighDateTime], 9
0x140026fd7  mov     qword ptr [rsp+238h+pftDueTime.dwLowDateTime+8], rsi
0x140026fdc  lea     rax, aClassWindowsFi_0; "class Windows::FileSystem::ReFs::Volume"...
0x140026fe3  mov     [rsp+238h+var_1C8], rax
0x140026fe8  lea     r9, [rsp+238h+pftDueTime]
0x140026fed  lea     rdx, [rsp+238h+var_198]
0x140026ff5  mov     rcx, rbx
0x140026ff8  call    ?recover_and_throw_if_failed@DedupVolume@ReFs@FileSystem@Windows@@AEAAXAEAV?$shared_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@U?$pair@JW4DedupErrorType@RefsDedup@@@6@Usource_location@6@@Z; Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex> &,std::pair<long,RefsDedup::DedupErrorType>,std::source_location)
0x140026ffd  lea     r8, [rsp+238h+var_178]
0x140027005  mov     rdx, [rbx+0D0h]
0x14002700c  lea     rcx, [rsp+238h+pftDueTime]
0x140027011  call    ?GetStatus@RefsDedup@@YA?AU?$pair@JW4DedupErrorType@RefsDedup@@@std@@PEAUDEDUP_HANDLE__@1@AEAURunStatus@1@@Z; RefsDedup::GetStatus(RefsDedup::DEDUP_HANDLE__ *,RefsDedup::RunStatus &)
0x140027016  mov     dword ptr [rsp+238h+var_1F8], 267h
0x14002701e  mov     dword ptr [rsp+238h+var_1F8+4], 9
0x140027026  mov     [rsp+238h+var_1F0], rsi
0x14002702b  lea     rcx, aClassWindowsFi_0; "class Windows::FileSystem::ReFs::Volume"...
0x140027032  mov     [rsp+238h+var_1E8], rcx
0x140027037  lea     r9, [rsp+238h+var_1F8]
0x14002703c  mov     r8, [rax]
0x14002703f  lea     rdx, [rsp+238h+var_198]
0x140027047  mov     rcx, rbx
0x14002704a  call    ?recover_and_throw_if_failed@DedupVolume@ReFs@FileSystem@Windows@@AEAAXAEAV?$shared_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@U?$pair@JW4DedupErrorType@RefsDedup@@@6@Usource_location@6@@Z; Windows::FileSystem::ReFs::DedupVolume::recover_and_throw_if_failed(std::shared_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex> &,std::pair<long,RefsDedup::DedupErrorType>,std::source_location)
0x14002704f  movaps  xmm0, [rsp+238h+var_178]
0x140027057  movaps  xmm1, [rsp+238h+var_168]
0x14002705f  movaps  xmm2, [rsp+238h+var_158]
0x140027067  movaps  xmm3, [rsp+238h+var_148]
0x14002706f  movaps  xmm4, [rsp+238h+var_138]
0x140027077  mov     rax, [rdi]
0x14002707a  movups  xmmword ptr [rax+48h], xmm0
0x14002707e  movups  xmmword ptr [rax+58h], xmm1
0x140027082  movups  xmmword ptr [rax+68h], xmm2
0x140027086  movups  xmmword ptr [rax+78h], xmm3
0x14002708a  movups  xmmword ptr [rax+88h], xmm4
0x140027091  cmp     byte ptr [rsp+238h+var_208], 0
0x140027096  jz      short loc_1400270A7
0x140027098  test    r12b, r12b
0x14002709b  jz      short loc_1400270A7
0x14002709d  xor     edx, edx; bool
0x14002709f  mov     rcx, rbx; this
0x1400270a2  call    ?SetFirstRun@DedupVolume@ReFs@FileSystem@Windows@@AEAAX_N@Z; Windows::FileSystem::ReFs::DedupVolume::SetFirstRun(bool)
  ... truncated ...
```
