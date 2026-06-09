# UpdateManager::PerformPreRebootActions(void)

- ea: `0x14008a974`
- end: `0x14008b0b0`
- name: `?PerformPreRebootActions@UpdateManager@@QEAAJXZ`
- size: `1852`
- prototype: `__int64 __fastcall(UpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140166ee0`

## callees

- `0x14002cc9c`
- `0x140036d60`
- `0x1400407f8`
- `0x140041bec`
- `0x140045404`
- `0x14007a5d8`
- `0x14007a7dc`
- `0x14007a970`
- `0x14007ab1c`
- `0x14007e87c`
- `0x14008a974`
- `0x1400a4c60`
- `0x1400a516c`
- `0x1400a5368`
- `0x1400b7654`
- `0x1400b8788`
- `0x1400c679c`
- `0x1400c7188`
- `0x1400dbc80`
- `0x1400e3528`
- `0x1400eaf5c`
- `0x14011d50c`
- `0x14012d7d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008aa5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008ab5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008adca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008b025`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008aa5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008ab5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008adca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008b025`

## string_xrefs

- `0x14008aa3d`: `C:\__w\1\s\src\orchestrator\mostack\updatemanager\UpdateManager.cpp`
- `0x14008aa09`: `PerformPreRebootActions:  Lock acquired on m_workThreadMutex`
- `0x14008a9ab`: `PerformPreRebootActions:  Acquiring lock on m_workThreadMutex to let everyone know we are rebooting, and don't allow a new worker thread to start`
- `0x14008ab60`: `PerformPreRebootActions:  Releasing lock on m_workThreadMutex while non-reboot actions are canceled`
- `0x14008add0`: `PerformPreRebootActions:  Releasing lock on m_workThreadMutex, notify_all on m_workThreadCondition, and start background work thread`
- `0x14008ad77`: `PerformPreRebootActions:  Acquiring lock on m_workThreadMutex and set flags to allow the worker thread to start again`
- `0x14008ae1f`: `PerformPreRebootActions: StartWorkerIfNeeded completed`
- `0x14008aea0`: `PerformPreRebootActions:  Release lock on m_workThreadMutex and wait on m_workThreadCondition until signaled or the work thread is no longer running`
- `0x14008ae3b`: `PerformPreRebootActions:  Acquiring lock on m_workThreadMutex to wait until background thread has completed`
- `0x14008af11`: `PerformPreRebootActions:  Signaled m_workThreadCondition or predicate indicates background thread is no longer running`
- `0x14008b047`: `Pre-reboot actions complete.`
- `0x14008b02b`: `PerformPreRebootActions:  Releasing lock on m_workThreadMutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UpdateManager::PerformPreRebootActions(UpdateManager *this)
{
  _DWORD *v2; // r12
  char v3; // r15
  bool v4; // zf
  _QWORD *System; // rax
  _QWORD *v7; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  __int64 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int128 *v13; // rax
  __int64 **v14; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rax
  volatile signed __int32 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  __int64 v24; // rcx
  int v25; // [rsp+28h] [rbp-99h]
  char v26; // [rsp+28h] [rbp-99h]
  char v27; // [rsp+29h] [rbp-98h]
  int v28; // [rsp+2Ch] [rbp-95h] BYREF
  __int128 v29; // [rsp+30h] [rbp-91h] BYREF
  __int64 v30; // [rsp+40h] [rbp-81h]
  const wchar_t *v31; // [rsp+48h] [rbp-79h] BYREF
  __int64 v32; // [rsp+50h] [rbp-71h]
  __int128 v33; // [rsp+58h] [rbp-69h] BYREF
  __int128 v34; // [rsp+68h] [rbp-59h]
  _QWORD v35[2]; // [rsp+78h] [rbp-49h] BYREF
  _QWORD v36[2]; // [rsp+88h] [rbp-39h] BYREF
  const wchar_t *v37; // [rsp+98h] [rbp-29h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-21h]
  _QWORD v39[2]; // [rsp+A8h] [rbp-19h] BYREF
  _BYTE v40[8]; // [rsp+B8h] [rbp-9h] BYREF
  volatile signed __int32 *v41; // [rsp+C0h] [rbp-1h]
  __int128 v42; // [rsp+D8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  *(_QWORD *)&v42 = L"PerformPreRebootActions:  Acquiring lock on m_workThreadMutex to let everyone know we are rebooting,"
                     " and don't allow a new worker thread to start";
  *((_QWORD *)&v42 + 1) = 145;
  SystemInterface::LogVerbose<>(&v42);
  v42 = (unsigned __int64)this + 1008;
  if ( (unsigned int)mtx_do_lock((char *)this + 1008, 0) )
    goto LABEL_72;
  v2 = (_DWORD *)((char *)this + 1084);
  if ( *((_DWORD *)this + 271) == 0x7FFFFFFF )
    goto LABEL_74;
  v3 = 1;
  BYTE8(v42) = 1;
  *((_QWORD *)&v29 + 1) = L"PerformPreRebootActions:  Lock acquired on m_workThreadMutex";
  v30 = 60;
  SystemInterface::LogVerbose<>((char *)&v29 + 8);
  if ( *((_BYTE *)this + 726) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\UpdateManager.cpp",
      (const char *)0x8007139FLL,
      v25);
    v4 = (*((_DWORD *)this + 271))-- == 1;
    if ( v4 )
    {
      *((_DWORD *)this + 270) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 128);
    }
    return 2147947423LL;
  }
  System = (_QWORD *)SystemInterface::Providers::GetSystem(&v37);
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, const wchar_t **))(*(_QWORD *)*System + 40LL))(*System, &v31);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 272LL))(*v7);
  v8 = (volatile signed __int32 *)v32;
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = (volatile signed __int32 *)v38;
  if ( v38 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  *((_BYTE *)this + 726) = 1;
  *((_BYTE *)this + 1179) = 0;
  v4 = (*((_DWORD *)this + 271))-- == 1;
  if ( v4 )
  {
    *((_DWORD *)this + 270) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 128);
  }
  *(_QWORD *)&v42 = L"PerformPreRebootActions:  Releasing lock on m_workThreadMutex while non-reboot actions are canceled";
  *((_QWORD *)&v42 + 1) = 99;
  SystemInterface::LogVerbose<>(&v42);
  *((_QWORD *)&v29 + 1) = (char *)this + 144;
  v27 = 0;
  v30 = 0;
  v42 = (unsigned __int64)this + 144;
  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
  {
    if ( this != (UpdateManager *)-144LL )
    {
      mutex_extensions::shared_recursive_mutex::lock_shared((char *)this + 144);
      v26 = 1;
      BYTE8(v42) = 1;
      goto LABEL_22;
    }
LABEL_73:
    std::_Throw_system_error(1);
  }
  if ( this == (UpdateManager *)-144LL )
    goto LABEL_73;
  mutex_extensions::shared_recursive_mutex::lock((char *)this + 144);
  v27 = 1;
  LOBYTE(v30) = 1;
LABEL_22:
  v10 = (__int64 *)**((_QWORD **)this + 41);
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10[6] + 32LL))(v10[6]) )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10[4] + 24LL))(v10[4], v40);
      v12 = std::wstring::insert(v11, 0);
      v33 = 0;
      v34 = 0;
      v33 = *(_OWORD *)v12;
      v34 = *(_OWORD *)(v12 + 16);
      *(_WORD *)v12 = 0;
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
      v13 = &v33;
      if ( *((_QWORD *)&v34 + 1) > 7u )
        v13 = (__int128 *)v33;
      v36[0] = v13;
      v36[1] = v34;
      SystemInterface::Log<>(v36);
      std::wstring::~wstring(&v33);
      std::wstring::~wstring(v40);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::GetImpl'::`2'::impl) )
      {
        v35[0] = L"PreReboot";
        v35[1] = 9;
        UpdateDatabase::SetUpdateAbortReason(*((_QWORD *)this + 2), v10[4], v35);
      }
      Threads::Action<std::optional<ActionResult>>::Cancel(v10[14], 0);
    }
    v14 = (__int64 **)v10[2];
    if ( *((_BYTE *)v14 + 25) )
    {
      for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v10 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v10 = i;
      v10 = i;
    }
    else
    {
      v10 = (__int64 *)v10[2];
      for ( j = *v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v10 = j;
    }
  }
  ScanManager::CancelAllScans(*((_QWORD *)this + 97), 0);
  BrokerManager::Cancel(*((BrokerManager **)this + 98));
  if ( v26 )
    mutex_extensions::shared_recursive_mutex::unlock_shared((UpdateManager *)((char *)this + 144));
  if ( v27 )
    mutex_extensions::shared_recursive_mutex::unlock((UpdateManager *)((char *)this + 144));
  *(_QWORD *)&v42 = L"PerformPreRebootActions:  Acquiring lock on m_workThreadMutex and set flags to allow the worker thre"
                     "ad to start again";
  *((_QWORD *)&v42 + 1) = 117;
  SystemInterface::LogVerbose<>(&v42);
  if ( (unsigned int)mtx_do_lock((char *)this + 1008, 0) )
LABEL_72:
    std::_Throw_Cpp_error(5);
  if ( *v2 == 0x7FFFFFFF )
  {
LABEL_74:
    *v2 = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *(_WORD *)((char *)this + 1179) = 257;
  v4 = (*v2)-- == 1;
  if ( v4 )
  {
    *((_DWORD *)this + 270) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 128);
  }
  *(_QWORD *)&v42 = L"PerformPreRebootActions:  Releasing lock on m_workThreadMutex, notify_all on m_workThreadCondition, "
                     "and start background work thread";
  *((_QWORD *)&v42 + 1) = 132;
  SystemInterface::LogVerbose<>(&v42);
  std::condition_variable_any::notify_all((UpdateManager *)((char *)this + 1088));
  *(_QWORD *)&v42 = L"PerformPreRebootActions: Calling StartWorkerIfNeeded";
  *((_QWORD *)&v42 + 1) = 52;
  SystemInterface::LogVerbose<>(&v42);
  UpdateManager::StartWorkerIfNeeded(this);
  *(_QWORD *)&v42 = L"PerformPreRebootActions: StartWorkerIfNeeded completed";
  *((_QWORD *)&v42 + 1) = 54;
  SystemInterface::LogVerbose<>(&v42);
  *((_QWORD *)&v29 + 1) = L"PerformPreRebootActions:  Acquiring lock on m_workThreadMutex to wait until background thread has completed";
  v30 = 107;
  SystemInterface::LogVerbose<>((char *)&v29 + 8);
  v42 = (unsigned __int64)this + 1008;
  if ( (unsigned int)mtx_do_lock((char *)this + 1008, 0) )
    std::_Throw_Cpp_error(5);
  if ( *v2 == 0x7FFFFFFF )
  {
    *v2 = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v42) = 1;
  if ( *((_BYTE *)this + 1178) )
  {
    v28 = 1;
    do
    {
      v39[0] = L"PerformPreRebootActions:  Release lock on m_workThreadMutex and wait on m_workThreadCondition until signa"
                "led or the work thread is no longer running";
      v39[1] = 148;
      SystemInterface::LogVerbose<>(v39);
      v17 = (_QWORD *)std::_To_absolute_time<int,std::ratio<60,1>>((char *)&v29 + 8, &v28);
      do
      {
        if ( !*((_BYTE *)this + 1178) )
          break;
        std::chrono::steady_clock::now(v35);
        if ( *v17 == v35[0] || *v17 < v35[0] )
          v18 = 0;
        else
          v18 = *v17 - v35[0];
        v36[0] = v18;
      }
      while ( (unsigned int)std::condition_variable_any::wait_for<std::unique_lock<std::recursive_mutex>,__int64,std::ratio<1,1000000000>>(
                              (char *)this + 1088,
                              &v42,
                              v36) != 1 );
      v37 = L"PerformPreRebootActions:  Signaled m_workThreadCondition or predicate indicates background thread is no longer running";
      v38 = 118;
      SystemInterface::LogVerbose<>(&v37);
      v31 = L"Refreshing shutdown hint.";
      v32 = 25;
      SystemInterface::Log<>(&v31);
      v19 = SystemInterface::Providers::GetSystem(&v33);
      v20 = *(_QWORD *)v19 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v19 + 8LL) + 4LL);
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 80LL))(v20, v40);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 40LL))(*v21);
      v22 = v41;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      v23 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
      if ( *((_QWORD *)&v33 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
    }
    while ( *((_BYTE *)this + 1178) );
    v3 = BYTE8(v42);
  }
  if ( v3 )
  {
    v24 = v42;
    v4 = (*(_DWORD *)(v42 + 76))-- == 1;
    if ( v4 )
    {
      *(_DWORD *)(v24 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v24 + 16));
    }
  }
  v31 = L"PerformPreRebootActions:  Releasing lock on m_workThreadMutex";
  v32 = 61;
  SystemInterface::LogVerbose<>(&v31);
  v31 = L"Pre-reboot actions complete.";
  v32 = 28;
  SystemInterface::Log<>(&v31);
  return 0;
}

```

## disassembly

```asm
0x14008a974  mov     rax, rsp
0x14008a977  mov     [rax+10h], rbx
0x14008a97b  mov     [rax+18h], rsi
0x14008a97f  mov     [rax+20h], rdi
0x14008a983  push    rbp
0x14008a984  push    r12
0x14008a986  push    r13
0x14008a988  push    r14
0x14008a98a  push    r15
0x14008a98c  lea     rbp, [rax-5Fh]
0x14008a990  sub     rsp, 0F0h
0x14008a997  mov     rax, cs:__security_cookie
0x14008a99e  xor     rax, rsp
0x14008a9a1  mov     [rbp+57h+var_30], rax
0x14008a9a5  mov     r14, rcx
0x14008a9a8  xor     r13d, r13d
0x14008a9ab  lea     rax, aPerformprerebo_2; "PerformPreRebootActions:  Acquiring loc"...
0x14008a9b2  mov     qword ptr [rbp+57h+var_40], rax
0x14008a9b6  mov     qword ptr [rbp+57h+var_40+8], 91h
0x14008a9be  lea     rcx, [rbp+57h+var_40]
0x14008a9c2  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008a9c7  xorps   xmm0, xmm0
0x14008a9ca  movups  [rbp+57h+var_40], xmm0
0x14008a9ce  lea     rsi, [r14+3F0h]
0x14008a9d5  mov     qword ptr [rbp+57h+var_40], rsi
0x14008a9d9  mov     byte ptr [rbp+57h+var_40+8], r13b
0x14008a9dd  xor     edx, edx
0x14008a9df  mov     rcx, rsi
0x14008a9e2  call    mtx_do_lock
0x14008a9e7  test    eax, eax
0x14008a9e9  jnz     loc_14008B07D
0x14008a9ef  lea     r12, [rsi+4Ch]
0x14008a9f3  cmp     dword ptr [r12], 7FFFFFFFh
0x14008a9fb  jz      loc_14008B091
0x14008aa01  lea     r15d, [r13+1]
0x14008aa05  mov     byte ptr [rbp+57h+var_40+8], r15b
0x14008aa09  lea     rax, aPerformprerebo_9; "PerformPreRebootActions:  Lock acquired"...
0x14008aa10  mov     qword ptr [rsp+110h+var_E8+8], rax
0x14008aa15  mov     [rsp+110h+var_D8], 3Ch ; '<'
0x14008aa1e  lea     rcx, [rsp+110h+var_E8+8]
0x14008aa23  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008aa28  cmp     [r14+2D6h], r13b
0x14008aa2f  jz      short loc_14008AA93
0x14008aa31  mov     rcx, [rbp+5Fh]; this
0x14008aa35  mov     ebx, 8007139Fh
0x14008aa3a  mov     r9d, ebx; char *
0x14008aa3d  lea     r8, aCW1SSrcOrchest_34; "C:\\__w\\1\\s\\src\\orchestrator\\mosta"...
0x14008aa44  mov     edx, 76Eh; void *
0x14008aa49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14008aa4e  nop
0x14008aa4f  or      edi, 0FFFFFFFFh
0x14008aa52  add     [rsi+4Ch], edi
0x14008aa55  jnz     short loc_14008AA64
0x14008aa57  mov     [rsi+48h], edi
0x14008aa5a  lea     rcx, [rsi+10h]; SRWLock
0x14008aa5e  call    cs:__imp_ReleaseSRWLockExclusive
0x14008aa64  mov     eax, ebx
0x14008aa66  mov     rcx, [rbp+57h+var_30]
0x14008aa6a  xor     rcx, rsp; StackCookie
0x14008aa6d  call    __security_check_cookie
0x14008aa72  lea     r11, [rsp+110h+var_20]
0x14008aa7a  mov     rbx, [r11+38h]
0x14008aa7e  mov     rsi, [r11+40h]
0x14008aa82  mov     rdi, [r11+48h]
0x14008aa86  mov     rsp, r11
0x14008aa89  pop     r15
0x14008aa8b  pop     r14
0x14008aa8d  pop     r13
0x14008aa8f  pop     r12
0x14008aa91  pop     rbp
0x14008aa92  retn
0x14008aa93  lea     rcx, [rbp+57h+var_80]
0x14008aa97  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14008aa9c  nop
0x14008aa9d  mov     rcx, [rax]
0x14008aaa0  mov     rax, [rcx]
0x14008aaa3  lea     rdx, [rbp+57h+var_D0]
0x14008aaa7  mov     rax, [rax+28h]
0x14008aaab  call    _guard_dispatch_icall
0x14008aab0  nop
0x14008aab1  mov     rcx, [rax]
0x14008aab4  mov     rax, [rcx]
0x14008aab7  mov     rax, [rax+110h]
0x14008aabe  call    _guard_dispatch_icall
0x14008aac3  nop
0x14008aac4  or      edi, 0FFFFFFFFh
0x14008aac7  mov     rbx, [rbp+57h+var_C8]
0x14008aacb  test    rbx, rbx
0x14008aace  jz      short loc_14008AB04
0x14008aad0  mov     eax, edi
0x14008aad2  lock xadd [rbx+8], eax
0x14008aad7  add     eax, edi
0x14008aad9  jnz     short loc_14008AB04
0x14008aadb  mov     rax, [rbx]
0x14008aade  mov     rcx, rbx
0x14008aae1  mov     rax, [rax]
0x14008aae4  call    _guard_dispatch_icall
0x14008aae9  mov     eax, edi
0x14008aaeb  lock xadd [rbx+0Ch], eax
0x14008aaf0  add     eax, edi
0x14008aaf2  jnz     short loc_14008AB04
0x14008aaf4  mov     rax, [rbx]
0x14008aaf7  mov     rcx, rbx
0x14008aafa  mov     rax, [rax+8]
0x14008aafe  call    _guard_dispatch_icall
0x14008ab03  nop
0x14008ab04  mov     rbx, [rbp+57h+var_78]
0x14008ab08  test    rbx, rbx
0x14008ab0b  jz      short loc_14008AB40
0x14008ab0d  mov     eax, edi
0x14008ab0f  lock xadd [rbx+8], eax
0x14008ab14  add     eax, edi
0x14008ab16  jnz     short loc_14008AB40
0x14008ab18  mov     rax, [rbx]
0x14008ab1b  mov     rcx, rbx
0x14008ab1e  mov     rax, [rax]
0x14008ab21  call    _guard_dispatch_icall
0x14008ab26  mov     eax, edi
0x14008ab28  lock xadd [rbx+0Ch], eax
0x14008ab2d  add     eax, edi
0x14008ab2f  jnz     short loc_14008AB40
0x14008ab31  mov     rax, [rbx]
0x14008ab34  mov     rcx, rbx
0x14008ab37  mov     rax, [rax+8]
0x14008ab3b  call    _guard_dispatch_icall
0x14008ab40  mov     [r14+2D6h], r15b
0x14008ab47  mov     [r14+49Bh], r13b
0x14008ab4e  add     [rsi+4Ch], edi
0x14008ab51  jnz     short loc_14008AB60
0x14008ab53  mov     [rsi+48h], edi
0x14008ab56  lea     rcx, [rsi+10h]; SRWLock
0x14008ab5a  call    cs:__imp_ReleaseSRWLockExclusive
0x14008ab60  lea     rax, aPerformprerebo_3; "PerformPreRebootActions:  Releasing loc"...
0x14008ab67  mov     qword ptr [rbp+57h+var_40], rax
0x14008ab6b  mov     qword ptr [rbp+57h+var_40+8], 63h ; 'c'
0x14008ab73  lea     rcx, [rbp+57h+var_40]
0x14008ab77  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008ab7c  xorps   xmm0, xmm0
0x14008ab7f  movups  [rsp+110h+var_E8+8], xmm0
0x14008ab84  lea     r13, [r14+90h]
0x14008ab8b  mov     qword ptr [rsp+110h+var_E8+8], r13
0x14008ab90  xor     ebx, ebx
0x14008ab92  mov     [rsp+110h+var_EF], bl
0x14008ab96  mov     byte ptr [rsp+110h+var_D8], bl
0x14008ab9a  movups  [rbp+57h+var_40], xmm0
0x14008ab9e  mov     qword ptr [rbp+57h+var_40], r13
0x14008aba2  mov     [rsp+110h+var_F0], bl
0x14008aba6  mov     byte ptr [rbp+57h+var_40+8], bl
0x14008aba9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl(void)'::`2'::impl
0x14008abb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(void)
0x14008abb5  test    al, al
0x14008abb7  jz      short loc_14008ABD6
0x14008abb9  test    r13, r13
0x14008abbc  jz      loc_14008B088
0x14008abc2  mov     rcx, r13; this
0x14008abc5  call    ?lock_shared@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::lock_shared(void)
0x14008abca  mov     al, r15b
0x14008abcd  mov     [rsp+110h+var_F0], al
0x14008abd1  mov     byte ptr [rbp+57h+var_40+8], al
0x14008abd4  jmp     short loc_14008ABF2
0x14008abd6  test    r13, r13
0x14008abd9  jz      loc_14008B088
0x14008abdf  mov     rcx, r13; this
0x14008abe2  call    ?lock@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::lock(void)
0x14008abe7  mov     al, r15b
0x14008abea  mov     [rsp+110h+var_EF], al
0x14008abee  mov     byte ptr [rsp+110h+var_D8], al
0x14008abf2  mov     rbx, [r14+148h]
0x14008abf9  mov     rbx, [rbx]
0x14008abfc  xor     ecx, ecx
0x14008abfe  cmp     [rbx+19h], cl
0x14008ac01  jnz     loc_14008AD3C
0x14008ac07  mov     rcx, [rbx+30h]
0x14008ac0b  mov     rax, [rcx]
0x14008ac0e  mov     rax, [rax+20h]
0x14008ac12  call    _guard_dispatch_icall
0x14008ac17  xor     edx, edx
0x14008ac19  test    al, al
0x14008ac1b  jnz     loc_14008ACF4
0x14008ac21  mov     rcx, [rbx+20h]
0x14008ac25  mov     rax, [rcx]
0x14008ac28  lea     rdx, [rbp+57h+var_60]
0x14008ac2c  mov     rax, [rax+18h]
0x14008ac30  call    _guard_dispatch_icall
0x14008ac35  nop
0x14008ac36  mov     r9d, 1Fh
0x14008ac3c  lea     r8, aCancelingNonRe; "Canceling non-reboot action on "
0x14008ac43  xor     edx, edx
0x14008ac45  mov     rcx, rax
0x14008ac48  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x14008ac4d  xorps   xmm0, xmm0
0x14008ac50  movups  [rbp+57h+var_C0], xmm0
0x14008ac54  xorps   xmm1, xmm1
0x14008ac57  movdqu  [rbp+57h+var_B0], xmm1
0x14008ac5c  movups  xmm0, xmmword ptr [rax]
0x14008ac5f  movups  [rbp+57h+var_C0], xmm0
0x14008ac63  movups  xmm1, xmmword ptr [rax+10h]
0x14008ac67  movups  [rbp+57h+var_B0], xmm1
0x14008ac6b  xor     ecx, ecx
0x14008ac6d  mov     [rax], cx
0x14008ac70  mov     [rax+10h], rcx
0x14008ac74  mov     qword ptr [rax+18h], 7
0x14008ac7c  lea     rax, [rbp+57h+var_C0]
0x14008ac80  cmp     qword ptr [rbp+57h+var_B0+8], 7
0x14008ac85  cmova   rax, qword ptr [rbp+57h+var_C0]
0x14008ac8a  mov     [rbp+57h+var_90], rax
0x14008ac8e  mov     rax, qword ptr [rbp+57h+var_B0]
0x14008ac92  mov     [rbp+57h+var_88], rax
0x14008ac96  lea     rcx, [rbp+57h+var_90]
0x14008ac9a  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x14008ac9f  nop
0x14008aca0  lea     rcx, [rbp+57h+var_C0]
0x14008aca4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008aca9  nop
0x14008acaa  lea     rcx, [rbp+57h+var_60]
0x14008acae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008acb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::GetImpl(void)'::`2'::impl
0x14008acba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_DB_Improvements>::__private_IsEnabled(void)
0x14008acbf  test    al, al
0x14008acc1  jz      short loc_14008ACE7
0x14008acc3  lea     rax, aPrereboot; "PreReboot"
0x14008acca  mov     [rbp+57h+var_A0], rax
0x14008acce  mov     [rbp+57h+var_98], 9
0x14008acd6  lea     r8, [rbp+57h+var_A0]
0x14008acda  mov     rdx, [rbx+20h]
0x14008acde  mov     rcx, [r14+10h]
0x14008ace2  call    ?SetUpdateAbortReason@UpdateDatabase@@QEAAXAEBVUpdate@@V?$basic_zstring_view@_W@wil@@@Z; UpdateDatabase::SetUpdateAbortReason(Update const &,wil::basic_zstring_view<wchar_t>)
0x14008ace7  xor     edx, edx
0x14008ace9  mov     rcx, [rbx+70h]
0x14008aced  call    ?Cancel@?$Action@V?$optional@UActionResult@@@std@@@Threads@@QEAAXW4CancelReason@@@Z; Threads::Action<std::optional<ActionResult>>::Cancel(CancelReason)
0x14008acf2  xor     edx, edx
0x14008acf4  mov     rcx, [rbx+10h]
0x14008acf8  cmp     [rcx+19h], dl
0x14008acfb  jz      short loc_14008AD1A
0x14008acfd  mov     rax, [rbx+8]
0x14008ad01  jmp     short loc_14008AD10
0x14008ad03  cmp     rbx, [rax+10h]
0x14008ad07  jnz     short loc_14008AD15
0x14008ad09  mov     rbx, rax
0x14008ad0c  mov     rax, [rax+8]
0x14008ad10  cmp     [rax+19h], dl
0x14008ad13  jz      short loc_14008AD03
0x14008ad15  mov     rbx, rax
0x14008ad18  jmp     short loc_14008AD33
0x14008ad1a  mov     rbx, rcx
0x14008ad1d  mov     rcx, [rcx]
0x14008ad20  cmp     [rcx+19h], dl
0x14008ad23  jnz     short loc_14008AD33
0x14008ad25  mov     rbx, rcx
0x14008ad28  mov     rax, [rcx]
0x14008ad2b  mov     rcx, rax
0x14008ad2e  cmp     [rax+19h], dl
0x14008ad31  jz      short loc_14008AD25
0x14008ad33  cmp     [rbx+19h], dl
0x14008ad36  jz      loc_14008AC07
0x14008ad3c  xor     edx, edx
0x14008ad3e  mov     rcx, [r14+308h]
0x14008ad45  call    ?CancelAllScans@ScanManager@@QEAAXW4CancelReason@@@Z; ScanManager::CancelAllScans(CancelReason)
0x14008ad4a  mov     rcx, [r14+310h]; this
0x14008ad51  call    ?Cancel@BrokerManager@@QEAAXXZ; BrokerManager::Cancel(void)
0x14008ad56  nop
0x14008ad57  xor     ebx, ebx
0x14008ad59  cmp     [rsp+110h+var_F0], bl
0x14008ad5d  jz      short loc_14008AD68
0x14008ad5f  mov     rcx, r13; this
0x14008ad62  call    ?unlock_shared@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::unlock_shared(void)
0x14008ad67  nop
0x14008ad68  cmp     [rsp+110h+var_EF], bl
0x14008ad6c  jz      short loc_14008AD77
0x14008ad6e  mov     rcx, r13; this
0x14008ad71  call    ?unlock@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::unlock(void)
0x14008ad76  nop
0x14008ad77  lea     rax, aPerformprerebo_7; "PerformPreRebootActions:  Acquiring loc"...
0x14008ad7e  mov     qword ptr [rbp+57h+var_40], rax
0x14008ad82  mov     qword ptr [rbp+57h+var_40+8], 75h ; 'u'
0x14008ad8a  lea     rcx, [rbp+57h+var_40]
0x14008ad8e  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008ad93  xor     edx, edx
0x14008ad95  mov     rcx, rsi
0x14008ad98  call    mtx_do_lock
0x14008ad9d  test    eax, eax
0x14008ad9f  jnz     loc_14008B07D
0x14008ada5  cmp     dword ptr [r12], 7FFFFFFFh
0x14008adad  jz      loc_14008B091
0x14008adb3  mov     word ptr [r14+49Bh], 101h
0x14008adbd  add     [r12], edi
0x14008adc1  jnz     short loc_14008ADD0
0x14008adc3  mov     [rsi+48h], edi
0x14008adc6  lea     rcx, [rsi+10h]; SRWLock
0x14008adca  call    cs:__imp_ReleaseSRWLockExclusive
0x14008add0  lea     rax, aPerformprerebo_1; "PerformPreRebootActions:  Releasing loc"...
0x14008add7  mov     qword ptr [rbp+57h+var_40], rax
0x14008addb  mov     qword ptr [rbp+57h+var_40+8], 84h
0x14008ade3  lea     rcx, [rbp+57h+var_40]
0x14008ade7  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008adec  lea     r13, [r14+440h]
0x14008adf3  mov     rcx, r13; this
0x14008adf6  call    ?notify_all@condition_variable_any@std@@QEAAXXZ; std::condition_variable_any::notify_all(void)
0x14008adfb  lea     rax, aPerformprerebo_4; "PerformPreRebootActions: Calling StartW"...
0x14008ae02  mov     qword ptr [rbp+57h+var_40], rax
  ... truncated ...
```
