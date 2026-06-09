# CHandlerCache::_WorkerThreadProc(void)

- ea: `0x180002130`
- end: `0x18000284d`
- name: `?_WorkerThreadProc@CHandlerCache@@AEAAXXZ`
- size: `1821`
- prototype: `void __fastcall(CHandlerCache *__hidden this)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015f30`

## callees

- `0x180002130`
- `0x1800041d0`
- `0x180004a60`
- `0x180005d30`
- `0x180006010`
- `0x1800065d0`
- `0x180006920`
- `0x180008398`
- `0x180008584`
- `0x180008688`
- `0x180008a90`
- `0x180008abc`
- `0x180008b14`
- `0x18000977c`
- `0x180009d1c`
- `0x18000a714`
- `0x18000a98c`
- `0x180012e54`
- `0x1800132bc`
- `0x180015790`
- `0x180015918`
- `0x180015a18`
- `0x180022f90`
- `0x180024400`
- `0x180051bfc`
- `0x180051dd4`
- `0x180051e8c`
- `0x180052178`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002325`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000233d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002325`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000233d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000230a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000230a`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000236c`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000236c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002776`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002762`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800023ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800023ed`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000240c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000260c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000240c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000260c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000279b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000279b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800027bb`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18000258a`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x18000258a`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x180002598`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x180002598`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000223c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000223c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002560`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002560`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025a5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800024dd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800024dd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000254d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000254d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000227b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002824`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000227b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002824`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002439`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180002439`
- `USER32!PostThreadMessageW` at `0x18000278d`
- `USER32!PostThreadMessageW` at `0x18000278d`
- `ADVAPI32!RegEnumKeyW` at `0x180002223`
- `ADVAPI32!RegEnumKeyW` at `0x18000226c`
- `ADVAPI32!RegEnumKeyW` at `0x180002223`
- `ADVAPI32!RegEnumKeyW` at `0x18000226c`

## pseudocode

```c
void __fastcall CHandlerCache::_WorkerThreadProc(CHandlerCache *this)
{
  LPCRITICAL_SECTION v1; // rdi
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  HANDLE OwningThread; // rsi
  struct _DSA *v4; // rbx
  DWORD i; // r15d
  HDSA v6; // rbx
  int j; // r15d
  int v8; // eax
  HANDLE EventW; // rax
  HANDLE WaitableTimer; // r13
  bool v11; // r12
  HANDLE v12; // rbx
  int Error; // esi
  DWORD v14; // eax
  LSTATUS v15; // eax
  DWORD v16; // eax
  int v17; // ebx
  char DebugInfo; // bl
  __int32 v19; // eax
  char v20; // r15
  int *v21; // rbx
  int v22; // ebx
  struct _DPA *v23; // rcx
  int v24; // esi
  struct _DPA *v25; // rcx
  int v26; // eax
  HDSA v27; // r14
  char SpinCount; // bl
  _DWORD *p_Type; // rax
  int v30; // ebx
  int k; // esi
  CHandlerCollectionInfo *Ptr; // rax
  unsigned int v33; // edx
  struct _DPA *v34; // rcx
  struct _DPA *v35; // rcx
  CSyncTrayIconManager *v36; // rcx
  int v37; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HDSA hdsa; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v41; // [rsp+60h] [rbp-A0h]
  HKEY v42; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v43[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v44; // [rsp+78h] [rbp-88h]
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  v1 = CHandlerCache::s_pSelf;
  v2 = (__int64 (__fastcall *)(__int64, __int64))qword_180070208;
  hKey = 0;
  OwningThread = CHandlerCache::s_pSelf[10].OwningThread;
  if ( qword_180070208 == -1 )
  {
    GetProcFromComCtl32(&qword_180070208, 320);
    v2 = (__int64 (__fastcall *)(__int64, __int64))qword_180070208;
  }
  if ( v2 )
  {
    hdsa = (HDSA)v2(16, 8);
    v4 = hdsa;
    if ( hdsa )
    {
      if ( (int)StringCchPrintfW(
                  Name,
                  0x104u,
                  L"%ws\\%ws",
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
                  L"HandlerCollections") >= 0 )
        CSettingsBase::OpenKey(HKEY_LOCAL_MACHINE, Name, &hKey);
      if ( hKey )
      {
        for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x104u); ++i )
        {
          pclsid = 0;
          if ( !CLSIDFromString(Name, &pclsid) )
            DSA_InsertItem(v4, 0x7FFFFFFF, &pclsid);
        }
        RegCloseKey(hKey);
      }
      _InterlockedExchange((volatile __int32 *)&v1[2].OwningThread, 0);
      _InterlockedIncrement((volatile signed __int32 *)&v1[9].SpinCount + 1);
      CHandlerCache::_MarkHandlerCollectionsToBePurged(v1, &hdsa);
      v6 = hdsa;
      for ( j = 0; ; ++j )
      {
        v8 = v6 ? *(_DWORD *)v6 : 0;
        if ( j >= v8 )
          break;
        pclsid = 0;
        if ( DSA_GetItem(v6, j, &pclsid) )
          CHandlerCache::_RefreshHandlerCollection(v1, &pclsid, OwningThread != 0);
      }
      CDSA_Base<unsigned short [64]>::Destroy(&hdsa);
      CHandlerCache::Release((CHandlerCache *)v1);
      CHandlerCache::_UpdateAggregateStatus((CHandlerCache *)v1);
    }
  }
  if ( OwningThread )
    SetEvent(OwningThread);
  *(_OWORD *)hHandle = 0;
  hHandle[0] = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v41 = 0;
  hHandle[1] = EventW;
  v42 = 0;
  v43[0] = 0;
  v44 = 0;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x100002u);
  v11 = WaitableTimer != 0;
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          v12 = hHandle[0];
          Error = -2147024809;
          if ( hHandle[0] )
          {
            Error = 0;
            if ( v42
              || (Error = StringCchPrintfW(
                            Name,
                            0x104u,
                            L"%ws\\%ws",
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
                            L"HandlerCollections"),
                  Error >= 0)
              && (Error = CSettingsBase::OpenKey(HKEY_LOCAL_MACHINE, Name, &v42), Error >= 0) )
            {
              v14 = WaitForSingleObject(v12, 0);
              if ( v14 == -1 )
              {
                Error = ResultFromKnownLastError();
                goto LABEL_42;
              }
              if ( v41 )
              {
                if ( v14 )
                  goto LABEL_42;
              }
              else if ( v14 )
              {
                goto LABEL_35;
              }
              ResetEvent(v12);
              v41 = 0;
LABEL_35:
              Error = -2147024809;
              if ( v42 )
              {
                v15 = RegNotifyChangeKeyValue(v42, 1, 1u, v12, 1);
                if ( !v15 )
                {
                  Error = 0;
LABEL_40:
                  v41 = 1;
LABEL_42:
                  if ( Error < 0 )
                    goto LABEL_54;
                  Error = CBaseHandlerKeys::MonitorForChanges((CBaseHandlerKeys *)v43, hHandle[1], L"Handlers");
                  goto LABEL_44;
                }
                Error = ResultFromKnownError(v15);
              }
              if ( Error < 0 )
                goto LABEL_54;
              goto LABEL_40;
            }
          }
LABEL_44:
          if ( Error >= 0 )
          {
            LODWORD(hKey) = 0;
            if ( v11 )
            {
              if ( (int)WaitCoalesced(WaitableTimer, 2u, hHandle, 0xBB8u, 0x3E8u, v37, (unsigned int *)&hKey) >= 0 )
              {
                v16 = (unsigned int)hKey;
LABEL_49:
                if ( v16 )
                {
                  if ( v16 == 1 )
                    CHandlerCache::_RefreshHandlerCollection(v1, &GUID_NULL, 0);
                }
                else
                {
                  CHandlerCache::_RefreshHandlerCollections((CHandlerCache *)v1, 0);
                }
                goto LABEL_58;
              }
              v11 = 0;
            }
            v16 = WaitForMultipleObjects(2u, hHandle, 0, 0xBB8u);
            goto LABEL_49;
          }
LABEL_54:
          if ( v11 )
          {
            LODWORD(hKey) = 0;
            if ( (int)WaitCoalesced(WaitableTimer, 0, 0, 0x1F4u, 0x64u, v37, (unsigned int *)&hKey) >= 0 )
              goto LABEL_58;
            v11 = 0;
          }
          Sleep(0x1F4u);
LABEL_58:
          if ( _InterlockedExchange((volatile __int32 *)&v1[2].OwningThread, (__int32)v1[2].OwningThread) )
            break;
          EnterCriticalSection(v1);
          DebugInfo = (char)v1[10].DebugInfo;
          LeaveCriticalSection(v1);
          v19 = _InterlockedExchange((volatile __int32 *)&v1[9].SpinCount + 1, HIDWORD(v1[9].SpinCount));
          if ( DebugInfo != 1 || v19 )
          {
            v20 = 0;
            EnterCriticalSection(v1);
            ResetEvent(*(HANDLE *)&v1[10].LockCount);
            if ( !v1[1].OwningThread )
              CDPA_Base<SYNCMGR_EVENTINFO,CTContainer_PolicyUnOwned<SYNCMGR_EVENTINFO>>::Create(&v1[1].OwningThread, 8);
            v21 = (int *)v1[1].OwningThread;
            if ( v21 )
            {
              v22 = *v21;
              if ( v22 )
              {
                v20 = 1;
                DPA_EnumCallback(*(HDPA *)&v1[1].LockCount, CHandlerCache::s_PrepUpdateCB, &v1[1].OwningThread);
              }
            }
            else
            {
              v22 = 0;
            }
            v23 = (struct _DPA *)v1[1].OwningThread;
            if ( v23 )
            {
              DPA_DestroyCallback(v23, DPA_ReleaseCB<CHandlerInfo>, 0);
              v1[1].OwningThread = 0;
            }
            EnterCriticalSection(v1);
            v24 = 0;
            while ( 1 )
            {
              v25 = (struct _DPA *)v1[1].DebugInfo;
              v26 = v25 ? *(_DWORD *)v25 : 0;
              if ( v24 >= v26 )
                break;
              hdsa = (HDSA)DPA_GetPtr(v25, v24);
              v27 = hdsa;
              CHandlerCollectionInfo::UpdateState(hdsa);
              if ( *(_DWORD *)v27 == 5 )
              {
                DPA_DeletePtr((HDPA)v1[1].DebugInfo, v24);
                SafeRelease<CHandlerCollectionInfo>(&hdsa);
              }
              else
              {
                *(_DWORD *)v27 = 0;
                ++v24;
              }
            }
            LeaveCriticalSection(v1);
            if ( v22 )
              CHandlerCache::_UpdateAggregateStatus((CHandlerCache *)v1);
            SpinCount = v1[9].SpinCount;
            LeaveCriticalSection(v1);
            if ( SpinCount == 1 )
              CHandlerCache::_SendStatusUpdateNotice(v1);
            if ( v20 == 1 )
              CHandlerCache::_SendUpdates((CHandlerCache *)v1);
            EnterCriticalSection(v1);
            p_Type = &v1[1].DebugInfo->Type;
            if ( p_Type )
            {
              v30 = *p_Type;
              for ( k = 0; k < v30; ++k )
              {
                Ptr = (CHandlerCollectionInfo *)DPA_GetPtr((HDPA)v1[1].DebugInfo, k);
                CHandlerCollectionInfo::UpdateAfterSendingNotifications(Ptr);
              }
            }
            LeaveCriticalSection(v1);
          }
          else
          {
            CHandlerCache::_CloseIfIdle((CHandlerCache *)v1);
          }
        }
        v17 = v1[2].SpinCount;
      }
      while ( GetTickCount() - v17 <= 0x2710 );
      if ( !_InterlockedExchange((volatile __int32 *)&v1[9].SpinCount + 1, HIDWORD(v1[9].SpinCount)) )
        break;
      _InterlockedExchange((volatile __int32 *)&v1[2].OwningThread, 0);
    }
    _InterlockedDecrement(&g_cRefThisDll);
    if ( !CoReleaseServerProcess() )
      break;
    CoAddRefServerProcess();
    _InterlockedIncrement(&g_cRefThisDll);
    LODWORD(v1[2].SpinCount) = GetTickCount();
  }
  EnterCriticalSection(&g_DllCriticalSection);
  byte_180070BB0 = 1;
  LeaveCriticalSection(&g_DllCriticalSection);
  PostThreadMessageW(idThread, 0x12u, 0, 0);
  if ( WaitableTimer )
    CloseHandle(WaitableTimer);
  if ( hHandle[0] )
    CloseHandle(hHandle[0]);
  if ( hHandle[1] )
    CloseHandle(hHandle[1]);
  v34 = *(struct _DPA **)&v1[1].LockCount;
  if ( v34 )
  {
    DPA_DestroyCallback(v34, DPA_ReleaseCB<CAdviseSet>, 0);
    *(_QWORD *)&v1[1].LockCount = 0;
  }
  v35 = (struct _DPA *)v1[1].OwningThread;
  if ( v35 )
  {
    DPA_DestroyCallback(v35, DPA_ReleaseCB<CHandlerInfo>, 0);
    v1[1].OwningThread = 0;
  }
  v36 = (CSyncTrayIconManager *)v1[11].DebugInfo;
  if ( v36 )
    CSyncTrayIconManager::ShutdownTrayIconThread(v36, v33);
  if ( v44 )
    RegCloseKey(v44);
  if ( v42 )
    RegCloseKey(v42);
}

```

## disassembly

```asm
0x180002130  push    rbp
0x180002132  push    rbx
0x180002133  push    rsi
0x180002134  push    rdi
0x180002135  push    r12
0x180002137  push    r13
0x180002139  push    r14
0x18000213b  push    r15
0x18000213d  lea     rbp, [rsp-1B8h]
0x180002145  sub     rsp, 2B8h
0x18000214c  mov     rax, cs:__security_cookie
0x180002153  xor     rax, rsp
0x180002156  mov     [rbp+1F0h+var_50], rax
0x18000215d  mov     rdi, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180002164  mov     rax, cs:qword_180070208
0x18000216b  mov     [rsp+2F0h+hKey], 0
0x180002174  mov     rsi, [rdi+1A0h]
0x18000217b  test    rsi, rsi
0x18000217e  setnz   r14b
0x180002182  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002186  jnz     short loc_1800021A0
0x180002188  mov     edx, 140h
0x18000218d  lea     rcx, qword_180070208
0x180002194  call    _GetProcFromComCtl32
0x180002199  mov     rax, cs:qword_180070208
0x1800021a0  lea     r15, ?s_szHandlerCollections_regkey@CSettingsBase@@1QBGB; "HandlerCollections"
0x1800021a7  test    rax, rax
0x1800021aa  jz      loc_180002302
0x1800021b0  mov     edx, 8
0x1800021b5  mov     ecx, 10h
0x1800021ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021bf  mov     [rsp+2F0h+hdsa], rax
0x1800021c4  mov     rbx, rax
0x1800021c7  test    rax, rax
0x1800021ca  jz      loc_180002302
0x1800021d0  lea     r9, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800021d7  mov     qword ptr [rsp+2F0h+fAsynchronous], r15
0x1800021dc  lea     r8, aWsWs; "%ws\\%ws"
0x1800021e3  mov     edx, 104h; unsigned __int64
0x1800021e8  lea     rcx, [rbp+1F0h+Name]; unsigned __int16 *
0x1800021ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800021f1  test    eax, eax
0x1800021f3  js      short loc_18000220A
0x1800021f5  lea     r8, [rsp+2F0h+hKey]; HKEY *
0x1800021fa  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180002201  lea     rdx, [rbp+1F0h+Name]; unsigned __int16 *
0x180002205  call    ?OpenKey@CSettingsBase@@KAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSettingsBase::OpenKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000220a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000220f  test    rcx, rcx
0x180002212  jz      short loc_180002281
0x180002214  mov     r9d, 104h; cchName
0x18000221a  lea     r8, [rbp+1F0h+Name]; lpName
0x18000221e  xor     edx, edx; dwIndex
0x180002220  xor     r15d, r15d
0x180002223  call    cs:__imp_RegEnumKeyW
0x180002229  test    eax, eax
0x18000222b  jnz     short loc_180002276
0x18000222d  xorps   xmm0, xmm0
0x180002230  lea     rdx, [rbp+1F0h+pclsid]; pclsid
0x180002234  lea     rcx, [rbp+1F0h+Name]; lpsz
0x180002238  movups  xmmword ptr [rbp+1F0h+pclsid.Data1], xmm0
0x18000223c  call    cs:__imp_CLSIDFromString
0x180002242  test    eax, eax
0x180002244  jnz     short loc_180002257
0x180002246  lea     r8, [rbp+1F0h+pclsid]; pitem
0x18000224a  mov     edx, 7FFFFFFFh; i
0x18000224f  mov     rcx, rbx; hdsa
0x180002252  call    DSA_InsertItem
0x180002257  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000225c  lea     r8, [rbp+1F0h+Name]; lpName
0x180002260  inc     r15d
0x180002263  mov     r9d, 104h; cchName
0x180002269  mov     edx, r15d; dwIndex
0x18000226c  call    cs:__imp_RegEnumKeyW
0x180002272  test    eax, eax
0x180002274  jz      short loc_18000222D
0x180002276  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000227b  call    cs:__imp_RegCloseKey
0x180002281  xor     eax, eax
0x180002283  xchg    eax, [rdi+60h]
0x180002286  lock inc dword ptr [rdi+18Ch]
0x18000228d  lea     rdx, [rsp+2F0h+hdsa]
0x180002292  mov     rcx, rdi; lpCriticalSection
0x180002295  call    ?_MarkHandlerCollectionsToBePurged@CHandlerCache@@AEAAXAEBV?$CDSA@U_GUID@@@@@Z; CHandlerCache::_MarkHandlerCollectionsToBePurged(CDSA<_GUID> const &)
0x18000229a  mov     rbx, [rsp+2F0h+hdsa]
0x18000229f  xor     r15d, r15d
0x1800022a2  test    rbx, rbx
0x1800022a5  jz      short loc_1800022AB
0x1800022a7  mov     eax, [rbx]
0x1800022a9  jmp     short loc_1800022AD
0x1800022ab  xor     eax, eax
0x1800022ad  cmp     r15d, eax
0x1800022b0  jge     short loc_1800022E1
0x1800022b2  xorps   xmm0, xmm0
0x1800022b5  lea     r8, [rbp+1F0h+pclsid]; pitem
0x1800022b9  mov     edx, r15d; i
0x1800022bc  mov     rcx, rbx; hdsa
0x1800022bf  movups  xmmword ptr [rbp+1F0h+pclsid.Data1], xmm0
0x1800022c3  call    DSA_GetItem
0x1800022c8  test    eax, eax
0x1800022ca  jz      short loc_1800022DC
0x1800022cc  movzx   r8d, r14b; bool
0x1800022d0  lea     rdx, [rbp+1F0h+pclsid]; struct _GUID *
0x1800022d4  mov     rcx, rdi; lpCriticalSection
0x1800022d7  call    ?_RefreshHandlerCollection@CHandlerCache@@AEAAJAEBU_GUID@@_N@Z; CHandlerCache::_RefreshHandlerCollection(_GUID const &,bool)
0x1800022dc  inc     r15d
0x1800022df  jmp     short loc_1800022A2
0x1800022e1  lea     rcx, [rsp+2F0h+hdsa]
0x1800022e6  call    ?Destroy@?$CDSA_Base@$$BY0EA@G@@QEAAHXZ; CDSA_Base<ushort [64]>::Destroy(void)
0x1800022eb  mov     rcx, rdi; this
0x1800022ee  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x1800022f3  mov     rcx, rdi; this
0x1800022f6  call    ?_UpdateAggregateStatus@CHandlerCache@@AEAAXXZ; CHandlerCache::_UpdateAggregateStatus(void)
0x1800022fb  lea     r15, ?s_szHandlerCollections_regkey@CSettingsBase@@1QBGB; "HandlerCollections"
0x180002302  test    rsi, rsi
0x180002305  jz      short loc_180002310
0x180002307  mov     rcx, rsi; hEvent
0x18000230a  call    cs:__imp_SetEvent
0x180002310  xorps   xmm0, xmm0
0x180002313  xor     r9d, r9d; lpName
0x180002316  xor     r8d, r8d; bInitialState
0x180002319  mov     edx, 1; bManualReset
0x18000231e  xor     ecx, ecx; lpEventAttributes
0x180002320  movups  xmmword ptr [rsp+2F0h+hHandle], xmm0
0x180002325  call    cs:__imp_CreateEventW
0x18000232b  xor     r9d, r9d; lpName
0x18000232e  xor     r8d, r8d; bInitialState
0x180002331  mov     edx, 1; bManualReset
0x180002336  mov     [rsp+2F0h+hHandle], rax
0x18000233b  xor     ecx, ecx; lpEventAttributes
0x18000233d  call    cs:__imp_CreateEventW
0x180002343  xor     r14d, r14d
0x180002346  mov     [rsp+2F0h+var_290], 0
0x18000234b  mov     r9d, 100002h; dwDesiredAccess
0x180002351  mov     [rsp+2F0h+hHandle+8], rax
0x180002356  xor     r8d, r8d; dwFlags
0x180002359  mov     [rsp+2F0h+var_288], r14
0x18000235e  xor     edx, edx; lpTimerName
0x180002360  mov     [rsp+2F0h+var_280], r14b
0x180002365  xor     ecx, ecx; lpTimerAttributes
0x180002367  mov     [rsp+2F0h+var_278], r14
0x18000236c  call    cs:__imp_CreateWaitableTimerExW
0x180002372  test    rax, rax
0x180002375  mov     r13, rax
0x180002378  setnz   r12b
0x18000237c  nop     dword ptr [rax+00h]
0x180002380  mov     rbx, [rsp+2F0h+hHandle]
0x180002385  mov     esi, 80070057h
0x18000238a  test    rbx, rbx
0x18000238d  jz      loc_180002487
0x180002393  cmp     [rsp+2F0h+var_288], 0
0x180002399  mov     esi, r14d
0x18000239c  jnz     short loc_1800023E8
0x18000239e  lea     r9, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800023a5  mov     qword ptr [rsp+2F0h+fAsynchronous], r15
0x1800023aa  lea     r8, aWsWs; "%ws\\%ws"
0x1800023b1  mov     edx, 104h; unsigned __int64
0x1800023b6  lea     rcx, [rbp+1F0h+Name]; unsigned __int16 *
0x1800023ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800023bf  mov     esi, eax
0x1800023c1  test    eax, eax
0x1800023c3  js      loc_180002487
0x1800023c9  lea     r8, [rsp+2F0h+var_288]; HKEY *
0x1800023ce  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800023d5  lea     rdx, [rbp+1F0h+Name]; unsigned __int16 *
0x1800023d9  call    ?OpenKey@CSettingsBase@@KAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSettingsBase::OpenKey(HKEY__ *,ushort const *,HKEY__ * *)
0x1800023de  mov     esi, eax
0x1800023e0  test    eax, eax
0x1800023e2  js      loc_180002487
0x1800023e8  xor     edx, edx; dwMilliseconds
0x1800023ea  mov     rcx, rbx; hHandle
0x1800023ed  call    cs:__imp_WaitForSingleObject
0x1800023f3  cmp     eax, 0FFFFFFFFh
0x1800023f6  jz      short loc_180002460
0x1800023f8  cmp     [rsp+2F0h+var_290], 0
0x1800023fd  jz      short loc_180002405
0x1800023ff  test    eax, eax
0x180002401  jz      short loc_180002409
0x180002403  jmp     short loc_180002467
0x180002405  test    eax, eax
0x180002407  jnz     short loc_180002417
0x180002409  mov     rcx, rbx; hEvent
0x18000240c  call    cs:__imp_ResetEvent
0x180002412  mov     [rsp+2F0h+var_290], 0
0x180002417  mov     rcx, [rsp+2F0h+var_288]; hKey
0x18000241c  mov     esi, 80070057h
0x180002421  test    rcx, rcx
0x180002424  jz      short loc_180002451
0x180002426  mov     edx, 1; bWatchSubtree
0x18000242b  mov     [rsp+2F0h+fAsynchronous], 1; fAsynchronous
0x180002433  mov     r8d, edx; dwNotifyFilter
0x180002436  mov     r9, rbx; hEvent
0x180002439  call    cs:__imp_RegNotifyChangeKeyValue
0x18000243f  test    eax, eax
0x180002441  jnz     short loc_180002448
0x180002443  mov     esi, r14d
0x180002446  jmp     short loc_180002459
0x180002448  mov     ecx, eax; unsigned int
0x18000244a  call    ?ResultFromKnownError@@YAJK@Z; ResultFromKnownError(ulong)
0x18000244f  mov     esi, eax
0x180002451  test    esi, esi
0x180002453  js      loc_180002512
0x180002459  mov     [rsp+2F0h+var_290], 1
0x18000245e  jmp     short loc_180002467
0x180002460  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180002465  mov     esi, eax
0x180002467  test    esi, esi
0x180002469  js      loc_180002512
0x18000246f  mov     rdx, [rsp+2F0h+hHandle+8]; void *
0x180002474  lea     r8, ?s_szHandlers_regkey@CSettingsBase@@1QBGB; "Handlers"
0x18000247b  lea     rcx, [rsp+2F0h+var_280]; this
0x180002480  call    ?MonitorForChanges@CBaseHandlerKeys@@IEAAJPEAXPEBG@Z; CBaseHandlerKeys::MonitorForChanges(void *,ushort const *)
0x180002485  mov     esi, eax
0x180002487  test    esi, esi
0x180002489  js      loc_180002512
0x18000248f  mov     dword ptr [rsp+2F0h+hKey], r14d
0x180002494  test    r12b, r12b
0x180002497  jz      short loc_1800024CA
0x180002499  lea     rax, [rsp+2F0h+hKey]
0x18000249e  mov     r9d, 0BB8h; unsigned int
0x1800024a4  mov     [rsp+2F0h+var_2C0], rax; unsigned int *
0x1800024a9  lea     r8, [rsp+2F0h+hHandle]; void **
0x1800024ae  mov     edx, 2; unsigned int
0x1800024b3  mov     [rsp+2F0h+fAsynchronous], 3E8h; unsigned int
0x1800024bb  mov     rcx, r13; hTimer
0x1800024be  call    ?WaitCoalesced@@YAJPEAXIPEBQEAXKKHPEAK@Z; WaitCoalesced(void *,uint,void * const *,ulong,ulong,int,ulong *)
0x1800024c3  test    eax, eax
0x1800024c5  jns     short loc_1800024F3
0x1800024c7  xor     r12b, r12b
0x1800024ca  mov     r9d, 0BB8h; dwMilliseconds
0x1800024d0  lea     rdx, [rsp+2F0h+hHandle]; lpHandles
0x1800024d5  xor     r8d, r8d; bWaitAll
0x1800024d8  mov     ecx, 2; nCount
0x1800024dd  call    cs:__imp_WaitForMultipleObjects
0x1800024e3  test    eax, eax
0x1800024e5  jnz     short loc_1800024F9
0x1800024e7  xor     edx, edx; hEvent
0x1800024e9  mov     rcx, rdi; this
0x1800024ec  call    ?_RefreshHandlerCollections@CHandlerCache@@AEAAXPEAX@Z; CHandlerCache::_RefreshHandlerCollections(void *)
0x1800024f1  jmp     short loc_180002553
0x1800024f3  mov     eax, dword ptr [rsp+2F0h+hKey]
0x1800024f7  jmp     short loc_1800024E3
0x1800024f9  cmp     eax, 1
0x1800024fc  jnz     short loc_180002553
0x1800024fe  xor     r8d, r8d; bool
0x180002501  lea     rdx, GUID_NULL; struct _GUID *
0x180002508  mov     rcx, rdi; lpCriticalSection
0x18000250b  call    ?_RefreshHandlerCollection@CHandlerCache@@AEAAJAEBU_GUID@@_N@Z; CHandlerCache::_RefreshHandlerCollection(_GUID const &,bool)
0x180002510  jmp     short loc_180002553
0x180002512  test    r12b, r12b
0x180002515  jz      short loc_180002548
0x180002517  lea     rax, [rsp+2F0h+hKey]
0x18000251c  mov     dword ptr [rsp+2F0h+hKey], r14d
0x180002521  mov     [rsp+2F0h+var_2C0], rax; unsigned int *
0x180002526  mov     r9d, 1F4h; unsigned int
0x18000252c  xor     r8d, r8d; void **
0x18000252f  mov     [rsp+2F0h+fAsynchronous], 64h ; 'd'; unsigned int
0x180002537  xor     edx, edx; unsigned int
0x180002539  mov     rcx, r13; hTimer
0x18000253c  call    ?WaitCoalesced@@YAJPEAXIPEBQEAXKKHPEAK@Z; WaitCoalesced(void *,uint,void * const *,ulong,ulong,int,ulong *)
0x180002541  test    eax, eax
0x180002543  jns     short loc_180002553
0x180002545  xor     r12b, r12b
0x180002548  mov     ecx, 1F4h; dwMilliseconds
0x18000254d  call    cs:__imp_Sleep
0x180002553  mov     eax, [rdi+60h]
0x180002556  xchg    eax, [rdi+60h]
0x180002559  test    eax, eax
0x18000255b  jz      short loc_1800025BE
0x18000255d  mov     ebx, [rdi+70h]
0x180002560  call    cs:__imp_GetTickCount
0x180002566  sub     eax, ebx
0x180002568  cmp     eax, 2710h
0x18000256d  jbe     loc_180002380
0x180002573  mov     eax, [rdi+18Ch]
0x180002579  xchg    eax, [rdi+18Ch]
0x18000257f  test    eax, eax
0x180002581  jnz     short loc_1800025B3
0x180002583  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000258a  call    cs:__imp_CoReleaseServerProcess
0x180002590  test    eax, eax
0x180002592  jz      loc_18000275B
0x180002598  call    cs:__imp_CoAddRefServerProcess
0x18000259e  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800025a5  call    cs:__imp_GetTickCount
0x1800025ab  mov     [rdi+70h], eax
0x1800025ae  jmp     loc_180002380
0x1800025b3  mov     eax, r14d
0x1800025b6  xchg    eax, [rdi+60h]
0x1800025b9  jmp     loc_180002380
0x1800025be  mov     rcx, rdi; lpCriticalSection
0x1800025c1  call    cs:__imp_EnterCriticalSection
0x1800025c7  movzx   ebx, byte ptr [rdi+190h]
0x1800025ce  mov     rcx, rdi; lpCriticalSection
0x1800025d1  call    cs:__imp_LeaveCriticalSection
0x1800025d7  mov     eax, [rdi+18Ch]
0x1800025dd  xchg    eax, [rdi+18Ch]
0x1800025e3  cmp     bl, 1
0x1800025e6  jnz     short loc_1800025F9
0x1800025e8  test    eax, eax
  ... truncated ...
```
