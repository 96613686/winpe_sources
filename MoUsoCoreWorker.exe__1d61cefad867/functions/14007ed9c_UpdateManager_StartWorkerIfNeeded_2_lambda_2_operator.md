# _UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2_::operator()

- ea: `0x14007ed9c`
- end: `0x14007f892`
- name: `_UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2_::operator()`
- size: `2806`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400b2260`

## callees

- `0x140040184`
- `0x1400433b0`
- `0x140045404`
- `0x140057a20`
- `0x14007a5d8`
- `0x14007a7dc`
- `0x14007ae84`
- `0x14007b494`
- `0x14007d4b4`
- `0x14007ed9c`
- `0x14008353c`
- `0x14008b224`
- `0x1400a4c60`
- `0x1400a516c`
- `0x1400abd70`
- `0x1400b7618`
- `0x1400b7654`
- `0x1400b8984`
- `0x1400c679c`
- `0x1400c6ef0`
- `0x1400c7188`
- `0x14012d7d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ee4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f026`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f0bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f5ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ee4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f026`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f0bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007f5ce`

## string_xrefs

- `0x14007f84a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007f86b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007f1fc`: `UpdateManagerPauseWaitTimeInMins`
- `0x14007f3a7`: `UpdateManagerPauseWaitTimeInMins`
- `0x14007ee55`: `Background Worker Thread:  Releasing lock on m_workThreadMutex and calling notify_all on m_workThreadCondition`
- `0x14007edcb`: `Background Worker Thread:  Acquiring lock on m_workThreadMutex to set flags for worker thread state`
- `0x14007ef48`: `Background Worker Thread:  Release lock on m_workThreadMutex and wait on m_workThreadCondition for anyone to signal that data has changed`
- `0x14007eeed`: `Background Worker Thread:  Acquiring lock on m_workThreadMutex in 'while' loop`
- `0x14007f02c`: `Background Worker Thread:  Release lock on m_workThreadMutex before calling WorkerThread() to unblock other notifiers during work`
- `0x14007efdb`: `Background Worker Thread:  m_workThreadCondition signaled, reacquiring lock on m_workThreadMutex`
- `0x14007f0c5`: `Background Worker Thread:  Release lock on m_workThreadMutex at end of while loop`
- `0x14007f054`: `Background Worker Thread:  Acquiring lock on m_workThreadMutex to see if we have been notified, or if we should keep running`
- `0x14007f7fa`: `UpdateManager:WaitForRevertsToComplete timed out waiting for current revert to finish`
- `0x14007f7d9`: `UpdateManager:WaitForAsyncWorkQueueToComplete timed out waiting for update work thread to finish`
- `0x14007f52c`: `Background Worker Thread: IPU cache thread complete`
- `0x14007f501`: `Background Worker Thread: Waiting for IPU cache thread to complete...`
- `0x14007f5d4`: `Background Worker Thread:  Release lock on m_workThreadMutex to notify_all on m_workThreadCondition`
- `0x14007f548`: `Background Worker Thread:  Acquiring lock on m_workThreadMutex to mark thread as ending, and allow UpdateManager to start a new Worker if it needs to`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2_::operator()(UpdateManager **a1)
{
  UpdateManager *v2; // rdi
  bool v3; // zf
  _QWORD *System; // rax
  volatile signed __int32 *v5; // rdi
  __int64 v6; // rdi
  UpdateManager *v7; // rsi
  UpdateManager *v8; // rax
  UpdateManager *v9; // r14
  volatile signed __int32 *v10; // rdi
  UpdateManager *v11; // rax
  __int64 v12; // rcx
  UpdateManager *v13; // rdi
  int v14; // eax
  int v15; // eax
  RTL_SRWLOCK *v16; // rcx
  __int64 v17; // rcx
  char IsEnabled; // al
  mutex_extensions::shared_recursive_mutex *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, const wchar_t **, _QWORD *); // r14
  __int16 *traits_2_unsigned_short; // rax
  const char *v26; // r9
  const wchar_t *v27; // r11
  __int64 v28; // rax
  int v29; // esi
  volatile signed __int32 *v30; // rdi
  volatile signed __int32 *v31; // rdi
  UpdateManager *v32; // rdi
  _QWORD *v33; // rsi
  __int64 v34; // rdx
  int v35; // eax
  char v36; // cl
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, const wchar_t **, _QWORD *); // r14
  __int16 *v42; // rax
  const char *v43; // r9
  const wchar_t *v44; // r11
  __int64 v45; // rax
  int v46; // esi
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  UpdateManager *v49; // rdi
  _QWORD *v50; // rsi
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rcx
  __int64 result; // rax
  _QWORD *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdi
  void (__fastcall *v58)(__int64, __int64, const wchar_t **); // rsi
  const wchar_t **v59; // rax
  const wchar_t *v60; // rcx
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rdx
  volatile signed __int32 *v64; // rdi
  volatile signed __int32 *v65; // rdi
  volatile signed __int32 *v66; // rdi
  _QWORD v67[2]; // [rsp+20h] [rbp-99h] BYREF
  mutex_extensions::shared_recursive_mutex *v68[2]; // [rsp+30h] [rbp-89h] BYREF
  const wchar_t *pExceptionObject; // [rsp+40h] [rbp-79h] BYREF
  __int64 v70; // [rsp+48h] [rbp-71h]
  const wchar_t *v71; // [rsp+60h] [rbp-59h] BYREF
  __int64 v72; // [rsp+68h] [rbp-51h]
  const wchar_t *v73; // [rsp+70h] [rbp-49h] BYREF
  __int64 v74; // [rsp+78h] [rbp-41h]
  _QWORD v75[2]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v76[2]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v77[5]; // [rsp+A0h] [rbp-19h] BYREF
  char v78; // [rsp+C8h] [rbp+Fh]
  __int128 v79; // [rsp+D0h] [rbp+17h] BYREF
  __int64 (__fastcall ***v80)(_QWORD, __int64); // [rsp+E0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v68[0] = (mutex_extensions::shared_recursive_mutex *)L"Background Worker Thread:  Acquiring lock on m_workThreadMutex to"
                                                        " set flags for worker thread state";
  v68[1] = (mutex_extensions::shared_recursive_mutex *)99;
  SystemInterface::LogVerbose<>(v68);
  v2 = *a1;
  if ( (unsigned int)mtx_do_lock((char *)*a1 + 1008, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v2 + 271) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 271) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *((_BYTE *)*a1 + 1176) = 1;
  *((_BYTE *)*a1 + 1178) = 1;
  *((_BYTE *)*a1 + 1177) = 0;
  v3 = (*((_DWORD *)v2 + 271))-- == 1;
  if ( v3 )
  {
    *((_DWORD *)v2 + 270) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v2 + 128);
  }
  v68[0] = (mutex_extensions::shared_recursive_mutex *)L"Background Worker Thread:  Releasing lock on m_workThreadMutex an"
                                                        "d calling notify_all on m_workThreadCondition";
  v68[1] = (mutex_extensions::shared_recursive_mutex *)110;
  SystemInterface::LogVerbose<>(v68);
  std::condition_variable_any::notify_all((UpdateManager *)((char *)*a1 + 1088));
  v80 = 0;
  System = (_QWORD *)SystemInterface::Providers::GetSystem(&pExceptionObject);
  (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)*System + 120LL))(
    *System,
    &v80);
  v5 = (volatile signed __int32 *)v70;
  if ( v70 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v70 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v77[4] = a1;
  v78 = 1;
  while ( 1 )
  {
    v68[0] = (mutex_extensions::shared_recursive_mutex *)L"Background Worker Thread:  Acquiring lock on m_workThreadMutex in 'while' loop";
    v68[1] = (mutex_extensions::shared_recursive_mutex *)78;
    SystemInterface::LogVerbose<>(v68);
    v79 = 0;
    v6 = (__int64)*a1 + 1008;
    *(_QWORD *)&v79 = v6;
    BYTE8(v79) = 0;
    if ( (unsigned int)mtx_do_lock(v6, 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v6 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v6 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v79) = 1;
    v76[0] = L"Background Worker Thread:  Release lock on m_workThreadMutex and wait on m_workThreadCondition for anyone t"
              "o signal that data has changed";
    v76[1] = 137;
    SystemInterface::LogVerbose<>(v76);
    v7 = *a1;
    v8 = a1[1];
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
    v9 = *a1;
    v10 = (volatile signed __int32 *)a1[1];
    while ( !*((_BYTE *)v9 + 1180) && !*((_BYTE *)v9 + 1188) )
      std::condition_variable_any::wait<std::unique_lock<std::recursive_mutex>>((char *)v7 + 1088, &v79);
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v77[0] = L"Background Worker Thread:  m_workThreadCondition signaled, reacquiring lock on m_workThreadMutex";
    v77[1] = 96;
    SystemInterface::LogVerbose<>(v77);
    v11 = *a1;
    if ( *((_BYTE *)*a1 + 1188) )
      break;
    *((_BYTE *)v11 + 1180) = 0;
    if ( BYTE8(v79) )
    {
      v12 = v79;
      v3 = (*(_DWORD *)(v79 + 76))-- == 1;
      if ( v3 )
      {
        *(_DWORD *)(v12 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v12 + 16));
      }
    }
    v71 = L"Background Worker Thread:  Release lock on m_workThreadMutex before calling WorkerThread() to unblock other no"
           "tifiers during work";
    v72 = 129;
    SystemInterface::LogVerbose<>(&v71);
    if ( !UpdateManager::WorkerThread(*a1) )
    {
      v73 = L"Background Worker Thread:  Acquiring lock on m_workThreadMutex to see if we have been notified, or if we sho"
             "uld keep running";
      v74 = 124;
      SystemInterface::LogVerbose<>(&v73);
      v13 = *a1;
      if ( (unsigned int)mtx_do_lock((char *)*a1 + 1008, 0) )
        goto LABEL_121;
      v14 = *((_DWORD *)v13 + 271);
      if ( v14 == 0x7FFFFFFF )
        goto LABEL_123;
      if ( !*((_BYTE *)*a1 + 1180) )
      {
        *((_BYTE *)*a1 + 1178) = 0;
        v3 = (*((_DWORD *)v13 + 271))-- == 1;
        if ( !v3 )
          goto LABEL_39;
        *((_DWORD *)v13 + 270) = -1;
        v16 = (RTL_SRWLOCK *)((char *)v13 + 1024);
        goto LABEL_38;
      }
      v15 = v14 - 1;
      *((_DWORD *)v13 + 271) = v15;
      if ( !v15 )
      {
        *((_DWORD *)v13 + 270) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v13 + 128);
      }
    }
    pExceptionObject = L"Background Worker Thread:  Release lock on m_workThreadMutex at end of while loop";
    v70 = 81;
    SystemInterface::LogVerbose<>(&pExceptionObject);
  }
  *((_BYTE *)v11 + 1178) = 0;
  if ( BYTE8(v79) )
  {
    v17 = v79;
    v3 = (*(_DWORD *)(v79 + 76))-- == 1;
    if ( v3 )
    {
      *(_DWORD *)(v17 + 72) = -1;
      v16 = (RTL_SRWLOCK *)(v17 + 16);
LABEL_38:
      ReleaseSRWLockExclusive(v16);
    }
  }
LABEL_39:
  if ( *((_BYTE *)*a1 + 1188) )
    UpdateManager::CancelAllActions(*a1, *((unsigned int *)*a1 + 296));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
  {
    WorkQueue::WaitToIdle((UpdateManager *)((char *)*a1 + 576));
  }
  else
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::GetImpl'::`2'::impl);
    v19 = (UpdateManager *)((char *)*a1 + 144);
    v68[0] = v19;
    v68[1] = 0;
    if ( IsEnabled )
    {
      mutex_extensions::shared_recursive_mutex::lock((char *)v19);
      LOBYTE(v68[1]) = 1;
      if ( *((_BYTE *)*a1 + 568) )
      {
        v20 = SystemInterface::Providers::GetSystem(&v71);
        v21 = *(_QWORD *)v20 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v20 + 8LL) + 4LL);
        v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v21 + 40LL))(v21, &v73);
        v23 = *(_QWORD *)v22;
        v24 = *(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD *))(**(_QWORD **)v22 + 56LL);
        LODWORD(v67[0]) = 30;
        traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                               L"UpdateManagerPauseWaitTimeInMins",
                                               word_1403FE5D2,
                                               0);
        if ( traits_2_unsigned_short == word_1403FE5D2
          || (v28 = ((char *)traits_2_unsigned_short - (char *)v27) >> 1, v28 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v26);
        }
        pExceptionObject = v27;
        v70 = v28;
        v29 = v24(v23, &pExceptionObject, v67);
        v30 = (volatile signed __int32 *)v74;
        if ( v74 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v74 + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        v31 = (volatile signed __int32 *)v72;
        if ( v72 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v72 + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        v32 = *a1;
        LODWORD(v67[0]) = v29;
        v33 = (_QWORD *)std::_To_absolute_time<int,std::ratio<60,1>>(&v79, v67);
        if ( *((_BYTE *)*a1 + 568) )
        {
          while ( 1 )
          {
            std::chrono::steady_clock::now(v67);
            if ( *v33 == v67[0] || *v33 < v67[0] )
              v34 = 0;
            else
              v34 = *v33 - v67[0];
            v75[0] = v34;
            v35 = std::condition_variable_any::wait_for<std::unique_lock<mutex_extensions::shared_recursive_mutex>,__int64,std::ratio<1,1000000000>>(
                    (char *)v32 + 480,
                    v68,
                    v75);
            v36 = *((_BYTE *)*a1 + 568);
            if ( v35 == 1 )
              break;
            if ( !v36 )
              goto LABEL_83;
          }
          if ( v36 )
          {
            std::runtime_error::runtime_error(
              (std::runtime_error *)&pExceptionObject,
              "UpdateManager:WaitForAsyncWorkQueueToComplete timed out waiting for update work thread to finish");
            throw (std::runtime_error *)&pExceptionObject;
          }
        }
      }
    }
    else
    {
      mutex_extensions::shared_recursive_mutex::lock((char *)v19);
      LOBYTE(v68[1]) = 1;
      if ( *((_QWORD *)*a1 + 56) )
      {
        v37 = SystemInterface::Providers::GetSystem(&v71);
        v38 = *(_QWORD *)v37 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v37 + 8LL) + 4LL);
        v39 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v38 + 40LL))(v38, &v73);
        v40 = *(_QWORD *)v39;
        v41 = *(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD *))(**(_QWORD **)v39 + 56LL);
        LODWORD(v67[0]) = 30;
        v42 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"UpdateManagerPauseWaitTimeInMins",
                           word_1403FE5D2,
                           0);
        if ( v42 == word_1403FE5D2 || (v45 = ((char *)v42 - (char *)v44) >> 1, v45 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v43);
        pExceptionObject = v44;
        v70 = v45;
        v46 = v41(v40, &pExceptionObject, v67);
        v47 = (volatile signed __int32 *)v74;
        if ( v74 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v74 + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v48 = (volatile signed __int32 *)v72;
        if ( v72 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v72 + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
        v49 = *a1;
        LODWORD(v67[0]) = v46;
        v50 = (_QWORD *)std::_To_absolute_time<int,std::ratio<60,1>>(&v79, v67);
        if ( *((_QWORD *)*a1 + 56) )
        {
          while ( 1 )
          {
            std::chrono::steady_clock::now(v75);
            if ( *v50 == v75[0] || *v50 < v75[0] )
              v51 = 0;
            else
              v51 = *v50 - v75[0];
            v67[0] = v51;
            v52 = std::condition_variable_any::wait_for<std::unique_lock<mutex_extensions::shared_recursive_mutex>,__int64,std::ratio<1,1000000000>>(
                    (char *)v49 + 360,
                    v68,
                    v67);
            v53 = *((_QWORD *)*a1 + 56);
            if ( v52 == 1 )
              break;
            if ( !v53 )
              goto LABEL_83;
          }
          if ( v53 )
          {
            std::runtime_error::runtime_error(
              (std::runtime_error *)&pExceptionObject,
              "UpdateManager:WaitForRevertsToComplete timed out waiting for current revert to finish");
            throw (std::runtime_error *)&pExceptionObject;
          }
        }
      }
    }
LABEL_83:
    if ( LOBYTE(v68[1]) )
      mutex_extensions::shared_recursive_mutex::unlock(v68[0]);
  }
  if ( *((_DWORD *)*a1 + 300) )
  {
    pExceptionObject = L"Background Worker Thread: Waiting for IPU cache thread to complete...";
    v70 = 69;
    SystemInterface::LogVerbose<>(&pExceptionObject);
    std::thread::join((UpdateManager *)((char *)*a1 + 1192));
  }
  pExceptionObject = L"Background Worker Thread: IPU cache thread complete";
  v70 = 51;
  SystemInterface::LogVerbose<>(&pExceptionObject);
  pExceptionObject = L"Background Worker Thread:  Acquiring lock on m_workThreadMutex to mark thread as ending, and allow "
                      "UpdateManager to start a new Worker if it needs to";
  v70 = 149;
  SystemInterface::LogVerbose<>(&pExceptionObject);
  *(_OWORD *)v68 = 0;
  v13 = *a1;
  v68[0] = (UpdateManager *)((char *)*a1 + 1008);
  LOBYTE(v68[1]) = 0;
  if ( (unsigned int)mtx_do_lock(v68[0], 0) )
LABEL_121:
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v13 + 271) == 0x7FFFFFFF )
  {
LABEL_123:
    *((_DWORD *)v13 + 271) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  LOBYTE(v68[1]) = 1;
  *((_BYTE *)*a1 + 1177) = 1;
  UpdateManager::SetWorking(*a1);
  v3 = (*((_DWORD *)v13 + 271))-- == 1;
  if ( v3 )
  {
    *((_DWORD *)v13 + 270) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v13 + 128);
  }
  pExceptionObject = L"Background Worker Thread:  Release lock on m_workThreadMutex to notify_all on m_workThreadCondition";
  v70 = 99;
  SystemInterface::LogVerbose<>(&pExceptionObject);
  std::condition_variable_any::notify_all((UpdateManager *)((char *)*a1 + 1088));
  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl);
  if ( (_BYTE)result )
  {
    v55 = (_QWORD *)SystemInterface::Providers::GetSystem(&v71);
    v56 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t **))(*(_QWORD *)*v55 + 40LL))(*v55, &v73);
    v57 = *(_QWORD *)v56;
    v58 = *(void (__fastcall **)(__int64, __int64, const wchar_t **))(**(_QWORD **)v56 + 224LL);
    v59 = (const wchar_t **)MetricsHelper::Report((char *)*a1 + 800, v77);
    v60 = (const wchar_t *)v59;
    v61 = (__int64)v59[2];
    if ( (unsigned __int64)v59[3] > 7 )
      v60 = *v59;
    if ( *((_QWORD *)*a1 + 102) )
      v62 = (__int64)(*(_QWORD *)(**((_QWORD **)*a1 + 101) + 56LL) - *(_QWORD *)(**((_QWORD **)*a1 + 101) + 48LL)) >> 3;
    else
      v62 = 0;
    pExceptionObject = v60;
    v70 = v61;
    v58(v57, v62, &pExceptionObject);
    result = std::wstring::~wstring(v77, v63);
    v64 = (volatile signed __int32 *)v74;
    if ( v74 )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v74 + 8));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
        result = (unsigned int)_InterlockedDecrement(v64 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
      }
    }
    v65 = (volatile signed __int32 *)v72;
    if ( v72 )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v72 + 8));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
        result = (unsigned int)_InterlockedDecrement(v65 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
      }
    }
  }
  *a1 = 0;
  v66 = (volatile signed __int32 *)a1[1];
  a1[1] = 0;
  if ( v66 )
  {
    result = (unsigned int)_InterlockedDecrement(v66 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
      result = (unsigned int)_InterlockedDecrement(v66 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
    }
  }
  if ( v80 )
    return (**v80)(v80, 1);
  return result;
}

```

## disassembly

```asm
0x14007ed9c  mov     [rsp-8+arg_8], rbx
0x14007eda1  mov     [rsp-8+arg_10], rsi
0x14007eda6  push    rbp
0x14007eda7  push    rdi
0x14007eda8  push    r12
0x14007edaa  push    r14
0x14007edac  push    r15
0x14007edae  lea     rbp, [rsp-37h]
0x14007edb3  sub     rsp, 0F0h
0x14007edba  mov     rax, cs:__security_cookie
0x14007edc1  xor     rax, rsp
0x14007edc4  mov     [rbp+57h+var_28], rax
0x14007edc8  mov     rbx, rcx
0x14007edcb  lea     rax, aBackgroundWork_0; "Background Worker Thread:  Acquiring lo"...
0x14007edd2  mov     [rsp+110h+var_E0], rax
0x14007edd7  mov     [rsp+110h+var_E0+8], 63h ; 'c'
0x14007ede0  lea     rcx, [rsp+110h+var_E0]
0x14007ede5  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007edea  mov     rdi, [rbx]
0x14007eded  lea     rcx, [rdi+3F0h]
0x14007edf4  xor     edx, edx
0x14007edf6  call    mtx_do_lock
0x14007edfb  xor     r15d, r15d
0x14007edfe  test    eax, eax
0x14007ee00  jnz     loc_14007F826
0x14007ee06  cmp     dword ptr [rdi+43Ch], 7FFFFFFFh
0x14007ee10  jz      loc_14007F831
0x14007ee16  mov     rax, [rbx]
0x14007ee19  mov     byte ptr [rax+498h], 1
0x14007ee20  mov     rax, [rbx]
0x14007ee23  mov     byte ptr [rax+49Ah], 1
0x14007ee2a  mov     rax, [rbx]
0x14007ee2d  mov     [rax+499h], r15b
0x14007ee34  or      r12, 0FFFFFFFFFFFFFFFFh
0x14007ee38  add     [rdi+43Ch], r12d
0x14007ee3f  jnz     short loc_14007EE55
0x14007ee41  mov     [rdi+438h], r12d
0x14007ee48  lea     rcx, [rdi+400h]; SRWLock
0x14007ee4f  call    cs:__imp_ReleaseSRWLockExclusive
0x14007ee55  lea     rax, aBackgroundWork_4; "Background Worker Thread:  Releasing lo"...
0x14007ee5c  mov     [rsp+110h+var_E0], rax
0x14007ee61  mov     [rsp+110h+var_E0+8], 6Eh ; 'n'
0x14007ee6a  lea     rcx, [rsp+110h+var_E0]
0x14007ee6f  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007ee74  mov     rcx, [rbx]
0x14007ee77  add     rcx, 440h; this
0x14007ee7e  call    ?notify_all@condition_variable_any@std@@QEAAXXZ; std::condition_variable_any::notify_all(void)
0x14007ee83  mov     [rbp+57h+var_30], r15
0x14007ee87  lea     rcx, [rbp+57h+pExceptionObject]
0x14007ee8b  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14007ee90  nop
0x14007ee91  mov     rcx, [rax]
0x14007ee94  mov     rax, [rcx]
0x14007ee97  lea     rdx, [rbp+57h+var_30]
0x14007ee9b  mov     rax, [rax+78h]
0x14007ee9f  call    _guard_dispatch_icall
0x14007eea4  nop
0x14007eea5  mov     rdi, [rbp+57h+var_C8]
0x14007eea9  test    rdi, rdi
0x14007eeac  jz      short loc_14007EEE5
0x14007eeae  mov     eax, r12d
0x14007eeb1  lock xadd [rdi+8], eax
0x14007eeb6  add     eax, r12d
0x14007eeb9  jnz     short loc_14007EEE5
0x14007eebb  mov     rax, [rdi]
0x14007eebe  mov     rcx, rdi
0x14007eec1  mov     rax, [rax]
0x14007eec4  call    _guard_dispatch_icall
0x14007eec9  mov     eax, r12d
0x14007eecc  lock xadd [rdi+0Ch], eax
0x14007eed1  add     eax, r12d
0x14007eed4  jnz     short loc_14007EEE5
0x14007eed6  mov     rax, [rdi]
0x14007eed9  mov     rcx, rdi
0x14007eedc  mov     rax, [rax+8]
0x14007eee0  call    _guard_dispatch_icall
0x14007eee5  mov     [rbp+57h+var_50], rbx
0x14007eee9  mov     [rbp+57h+var_48], 1
0x14007eeed  lea     rax, aBackgroundWork_8; "Background Worker Thread:  Acquiring lo"...
0x14007eef4  mov     [rsp+110h+var_E0], rax
0x14007eef9  mov     [rsp+110h+var_E0+8], 4Eh ; 'N'
0x14007ef02  lea     rcx, [rsp+110h+var_E0]
0x14007ef07  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007ef0c  xorps   xmm0, xmm0
0x14007ef0f  movups  [rbp+57h+var_40], xmm0
0x14007ef13  mov     rdi, [rbx]
0x14007ef16  add     rdi, 3F0h
0x14007ef1d  mov     qword ptr [rbp+57h+var_40], rdi
0x14007ef21  mov     byte ptr [rbp+57h+var_40+8], r15b
0x14007ef25  xor     edx, edx
0x14007ef27  mov     rcx, rdi
0x14007ef2a  call    mtx_do_lock
0x14007ef2f  test    eax, eax
0x14007ef31  jnz     loc_14007F81B
0x14007ef37  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x14007ef3e  jz      loc_14007F7C7
0x14007ef44  mov     byte ptr [rbp+57h+var_40+8], 1
0x14007ef48  lea     rax, aBackgroundWork_9; "Background Worker Thread:  Release lock"...
0x14007ef4f  mov     [rbp+57h+var_80], rax
0x14007ef53  mov     [rbp+57h+var_78], 89h
0x14007ef5b  lea     rcx, [rbp+57h+var_80]
0x14007ef5f  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007ef64  mov     rsi, [rbx]
0x14007ef67  mov     rax, [rbx+8]
0x14007ef6b  test    rax, rax
0x14007ef6e  jz      short loc_14007EF74
0x14007ef70  lock inc dword ptr [rax+8]
0x14007ef74  mov     r14, [rbx]
0x14007ef77  mov     rdi, [rbx+8]
0x14007ef7b  cmp     [r14+49Ch], r15b
0x14007ef82  jnz     short loc_14007EF9F
0x14007ef84  cmp     [r14+4A4h], r15b
0x14007ef8b  jnz     short loc_14007EF9F
0x14007ef8d  lea     rdx, [rbp+57h+var_40]
0x14007ef91  lea     rcx, [rsi+440h]
0x14007ef98  call    ??$wait@V?$unique_lock@Vrecursive_mutex@std@@@std@@@condition_variable_any@std@@QEAAXAEAV?$unique_lock@Vrecursive_mutex@std@@@1@@Z; std::condition_variable_any::wait<std::unique_lock<std::recursive_mutex>>(std::unique_lock<std::recursive_mutex> &)
0x14007ef9d  jmp     short loc_14007EF7B
0x14007ef9f  test    rdi, rdi
0x14007efa2  jz      short loc_14007EFDB
0x14007efa4  mov     eax, r12d
0x14007efa7  lock xadd [rdi+8], eax
0x14007efac  add     eax, r12d
0x14007efaf  jnz     short loc_14007EFDB
0x14007efb1  mov     rax, [rdi]
0x14007efb4  mov     rcx, rdi
0x14007efb7  mov     rax, [rax]
0x14007efba  call    _guard_dispatch_icall
0x14007efbf  mov     eax, r12d
0x14007efc2  lock xadd [rdi+0Ch], eax
0x14007efc7  add     eax, r12d
0x14007efca  jnz     short loc_14007EFDB
0x14007efcc  mov     rax, [rdi]
0x14007efcf  mov     rcx, rdi
0x14007efd2  mov     rax, [rax+8]
0x14007efd6  call    _guard_dispatch_icall
0x14007efdb  lea     rax, aBackgroundWork_2; "Background Worker Thread:  m_workThread"...
0x14007efe2  mov     [rbp+57h+var_70], rax
0x14007efe6  mov     [rbp+57h+var_68], 60h ; '`'
0x14007efee  lea     rcx, [rbp+57h+var_70]
0x14007eff2  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007eff7  mov     rax, [rbx]
0x14007effa  cmp     [rax+4A4h], r15b
0x14007f001  jnz     loc_14007F106
0x14007f007  mov     [rax+49Ch], r15b
0x14007f00e  cmp     byte ptr [rbp+57h+var_40+8], r15b
0x14007f012  jz      short loc_14007F02C
0x14007f014  mov     rcx, qword ptr [rbp+57h+var_40]
0x14007f018  add     [rcx+4Ch], r12d
0x14007f01c  jnz     short loc_14007F02C
0x14007f01e  mov     [rcx+48h], r12d
0x14007f022  add     rcx, 10h; SRWLock
0x14007f026  call    cs:__imp_ReleaseSRWLockExclusive
0x14007f02c  lea     rax, aBackgroundWork_6; "Background Worker Thread:  Release lock"...
0x14007f033  mov     [rbp+57h+var_B0], rax
0x14007f037  mov     [rbp+57h+var_A8], 81h
0x14007f03f  lea     rcx, [rbp+57h+var_B0]
0x14007f043  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007f048  mov     rcx, [rbx]; this
0x14007f04b  call    ?WorkerThread@UpdateManager@@AEAA_NXZ; UpdateManager::WorkerThread(void)
0x14007f050  test    al, al
0x14007f052  jnz     short loc_14007F0C5
0x14007f054  lea     rax, aBackgroundWork_5; "Background Worker Thread:  Acquiring lo"...
0x14007f05b  mov     [rbp+57h+var_A0], rax
0x14007f05f  mov     [rbp+57h+var_98], 7Ch ; '|'
0x14007f067  lea     rcx, [rbp+57h+var_A0]
0x14007f06b  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007f070  mov     rdi, [rbx]
0x14007f073  lea     rcx, [rdi+3F0h]
0x14007f07a  xor     edx, edx
0x14007f07c  call    mtx_do_lock
0x14007f081  test    eax, eax
0x14007f083  jnz     loc_14007F85C
0x14007f089  mov     eax, [rdi+43Ch]
0x14007f08f  cmp     eax, 7FFFFFFFh
0x14007f094  jz      loc_14007F87D
0x14007f09a  mov     rcx, [rbx]
0x14007f09d  cmp     [rcx+49Ch], r15b
0x14007f0a4  jz      short loc_14007F0E6
0x14007f0a6  sub     eax, 1
0x14007f0a9  mov     [rdi+43Ch], eax
0x14007f0af  jnz     short loc_14007F0C5
0x14007f0b1  mov     [rdi+438h], r12d
0x14007f0b8  lea     rcx, [rdi+400h]; SRWLock
0x14007f0bf  call    cs:__imp_ReleaseSRWLockExclusive
0x14007f0c5  lea     rax, aBackgroundWork_1; "Background Worker Thread:  Release lock"...
0x14007f0cc  mov     [rbp+57h+pExceptionObject], rax
0x14007f0d0  mov     [rbp+57h+var_C8], 51h ; 'Q'
0x14007f0d8  lea     rcx, [rbp+57h+pExceptionObject]
0x14007f0dc  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007f0e1  jmp     loc_14007EEED
0x14007f0e6  mov     [rcx+49Ah], r15b
0x14007f0ed  sub     dword ptr [rdi+43Ch], 1
0x14007f0f4  jnz     short loc_14007F12B
0x14007f0f6  mov     [rdi+438h], r12d
0x14007f0fd  lea     rcx, [rdi+400h]
0x14007f104  jmp     short loc_14007F125
0x14007f106  mov     [rax+49Ah], r15b
0x14007f10d  cmp     byte ptr [rbp+57h+var_40+8], r15b
0x14007f111  jz      short loc_14007F12B
0x14007f113  mov     rcx, qword ptr [rbp+57h+var_40]
0x14007f117  add     [rcx+4Ch], r12d
0x14007f11b  jnz     short loc_14007F12B
0x14007f11d  mov     [rcx+48h], r12d
0x14007f121  add     rcx, 10h; SRWLock
0x14007f125  call    cs:__imp_ReleaseSRWLockExclusive
0x14007f12b  mov     rcx, [rbx]
0x14007f12e  cmp     [rcx+4A4h], r15b
0x14007f135  jz      short loc_14007F142
0x14007f137  mov     edx, [rcx+4A0h]
0x14007f13d  call    ?CancelAllActions@UpdateManager@@AEAAXW4CancelReason@@@Z; UpdateManager::CancelAllActions(CancelReason)
0x14007f142  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl(void)'::`2'::impl
0x14007f149  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(void)
0x14007f14e  test    al, al
0x14007f150  jz      short loc_14007F166
0x14007f152  mov     rcx, [rbx]
0x14007f155  add     rcx, 240h; this
0x14007f15c  call    ?WaitToIdle@WorkQueue@@QEAAXXZ; WorkQueue::WaitToIdle(void)
0x14007f161  jmp     loc_14007F4F5
0x14007f166  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::GetImpl(void)'::`2'::impl
0x14007f16d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::__private_IsEnabled(void)
0x14007f172  mov     rcx, [rbx]
0x14007f175  add     rcx, 90h; this
0x14007f17c  xorps   xmm0, xmm0
0x14007f17f  movups  xmmword ptr [rsp+110h+var_E0], xmm0
0x14007f184  mov     [rsp+110h+var_E0], rcx
0x14007f189  mov     byte ptr [rsp+110h+var_E0+8], r15b
0x14007f18e  test    al, al
0x14007f190  jz      loc_14007F341
0x14007f196  call    ?lock@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::lock(void)
0x14007f19b  mov     byte ptr [rsp+110h+var_E0+8], 1
0x14007f1a0  mov     rax, [rbx]
0x14007f1a3  cmp     [rax+238h], r15b
0x14007f1aa  jz      loc_14007F332
0x14007f1b0  lea     rcx, [rbp+57h+var_B0]
0x14007f1b4  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14007f1b9  nop
0x14007f1ba  mov     rdx, [rax]
0x14007f1bd  mov     rax, [rdx+8]
0x14007f1c1  movsxd  rcx, dword ptr [rax+4]
0x14007f1c5  add     rdx, 8
0x14007f1c9  add     rcx, rdx
0x14007f1cc  mov     rax, [rcx]
0x14007f1cf  lea     rdx, [rbp+57h+var_A0]
0x14007f1d3  mov     rax, [rax+28h]
0x14007f1d7  call    _guard_dispatch_icall
0x14007f1dc  nop
0x14007f1dd  mov     rdi, [rax]
0x14007f1e0  mov     rax, [rdi]
0x14007f1e3  mov     r14, [rax+38h]
0x14007f1e7  mov     dword ptr [rsp+110h+var_F0], 1Eh
0x14007f1ef  xor     r8d, r8d
0x14007f1f2  lea     rsi, word_1403FE5D2
0x14007f1f9  mov     rdx, rsi
0x14007f1fc  lea     r11, aUpdatemanagerp; "UpdateManagerPauseWaitTimeInMins"
0x14007f203  mov     rcx, r11
0x14007f206  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14007f20b  cmp     rax, rsi
0x14007f20e  jz      loc_14007F846
0x14007f214  sub     rax, r11
0x14007f217  sar     rax, 1
0x14007f21a  cmp     rax, r12
0x14007f21d  jz      loc_14007F846
0x14007f223  mov     [rbp+57h+pExceptionObject], r11
0x14007f227  mov     [rbp+57h+var_C8], rax
0x14007f22b  lea     r8, [rsp+110h+var_F0]
0x14007f230  lea     rdx, [rbp+57h+pExceptionObject]
0x14007f234  mov     rcx, rdi
0x14007f237  mov     rax, r14
0x14007f23a  call    _guard_dispatch_icall
0x14007f23f  mov     esi, eax
0x14007f241  mov     rdi, [rbp+57h+var_98]
0x14007f245  test    rdi, rdi
0x14007f248  jz      short loc_14007F282
0x14007f24a  mov     ecx, r12d
0x14007f24d  lock xadd [rdi+8], ecx
0x14007f252  add     ecx, r12d
0x14007f255  jnz     short loc_14007F282
0x14007f257  mov     rdx, [rdi]
0x14007f25a  mov     rcx, rdi
0x14007f25d  mov     rax, [rdx]
0x14007f260  call    _guard_dispatch_icall
0x14007f265  mov     eax, r12d
0x14007f268  lock xadd [rdi+0Ch], eax
0x14007f26d  add     eax, r12d
0x14007f270  jnz     short loc_14007F282
0x14007f272  mov     rax, [rdi]
0x14007f275  mov     rcx, rdi
0x14007f278  mov     rax, [rax+8]
0x14007f27c  call    _guard_dispatch_icall
0x14007f281  nop
0x14007f282  mov     rdi, [rbp+57h+var_A8]
0x14007f286  test    rdi, rdi
0x14007f289  jz      short loc_14007F2C2
0x14007f28b  mov     eax, r12d
0x14007f28e  lock xadd [rdi+8], eax
0x14007f293  add     eax, r12d
0x14007f296  jnz     short loc_14007F2C2
0x14007f298  mov     rax, [rdi]
0x14007f29b  mov     rcx, rdi
0x14007f29e  mov     rax, [rax]
  ... truncated ...
```
