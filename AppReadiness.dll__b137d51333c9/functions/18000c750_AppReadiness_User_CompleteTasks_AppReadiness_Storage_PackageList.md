# AppReadiness::User::CompleteTasks(AppReadiness::Storage::PackageList &)

- ea: `0x18000c750`
- end: `0x18000d175`
- name: `?CompleteTasks@User@AppReadiness@@IEAA_NAEAVPackageList@Storage@2@@Z`
- size: `2597`
- prototype: `bool __fastcall(AppReadiness::User *__hidden this, struct AppReadiness::Storage::PackageList *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180002958`
- `0x180002a48`
- `0x180005068`
- `0x180005270`
- `0x180009d00`
- `0x18000a45c`
- `0x18000a470`
- `0x18000c750`
- `0x18000d17c`
- `0x18000d1c4`
- `0x18000e1d8`
- `0x18000e2d4`
- `0x18000e4a0`
- `0x1800171a0`
- `0x18001ecd4`
- `0x180022a70`
- `0x1800253f4`
- `0x1800269b4`
- `0x180027a4c`
- `0x18002b63c`
- `0x18002beec`
- `0x18002c40c`
- `0x18003235c`
- `0x180033d30`
- `0x1800340c8`
- `0x1800387b4`
- `0x18003e210`
- `0x18003e234`
- `0x18003ecb4`
- `0x18004a178`
- `0x18004a5e4`
- `0x18004a74c`
- `0x18005da6c`
- `0x18005f40c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cae6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cae6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c7b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c7b1`
- `ntdll!NtQuerySystemTime` at `0x18000ca70`
- `ntdll!NtQuerySystemTime` at `0x18000ca70`

## string_xrefs

- `0x18000caae`: `AppReadiness::User::MarkPackageError`
- `0x18000d0ff`: `AppReadiness::User::MarkPackageError`
- `0x18000caa2`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18000d0f3`: `onecoreuap\shell\appreadiness\src\core\user.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_BOOL8 __fastcall AppReadiness::User::CompleteTasks(
        AppReadiness::User *this,
        struct AppReadiness::Storage::PackageList *a2)
{
  struct AppReadiness::Storage::PackageList *v2; // rsi
  _QWORD *v4; // rbx
  char *v5; // rbx
  char *v6; // rdi
  AppReadiness::BrokerSession *v7; // rcx
  bool v8; // si
  std::_Ref_count_base *v9; // rbx
  char *v10; // rbx
  char *v11; // rdi
  void *QuadPart; // rcx
  unsigned __int64 v13; // rdx
  __int64 v15; // rcx
  __int64 *v16; // r8
  __int64 v17; // rdx
  signed __int32 v18; // eax
  signed __int32 v19; // ett
  __int64 v20; // r15
  volatile signed __int32 *v21; // r12
  __int64 v22; // rcx
  ULONG v23; // eax
  _OWORD *v24; // rdx
  __int64 *v25; // r14
  __int64 v26; // rsi
  __int64 i; // rdi
  __int64 v28; // rdx
  NTSTATUS v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r14
  __int64 k; // rdi
  char v34; // al
  char v35; // r10
  _QWORD *v36; // rsi
  _QWORD *v37; // r14
  _QWORD *m; // rdi
  __int64 v39; // r14
  __int64 j; // rdi
  int v41; // edx
  std::_Ref_count_base *v42; // r9
  int v43; // edi
  __int64 v44; // rax
  __int64 v45; // r8
  const wchar_t *v46; // rdx
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  unsigned int v49; // eax
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 n; // rbx
  __int64 v53; // rdi
  _QWORD *v54; // r9
  _QWORD *v55; // r8
  _QWORD *v56; // rax
  _QWORD *v57; // r9
  int v58; // r8d
  __int64 v59; // rdx
  std::_Ref_count_base *v60; // rcx
  bool v61; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v62; // [rsp+44h] [rbp-BCh]
  signed int v63; // [rsp+48h] [rbp-B8h]
  __int64 v64; // [rsp+50h] [rbp-B0h] BYREF
  _LARGE_INTEGER SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v66; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG v67; // [rsp+68h] [rbp-98h] BYREF
  __int128 v68; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+80h] [rbp-80h]
  void *v70; // [rsp+88h] [rbp-78h] BYREF
  char *v71; // [rsp+90h] [rbp-70h]
  char *v72; // [rsp+98h] [rbp-68h]
  __int128 v73; // [rsp+A0h] [rbp-60h] BYREF
  AppReadiness::BrokerSession *v74; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v75; // [rsp+B8h] [rbp-48h]
  __int64 v76; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v77; // [rsp+C8h] [rbp-38h]
  int v78; // [rsp+D0h] [rbp-30h]
  struct _EVENT_DATA_DESCRIPTOR *p_pExceptionObject; // [rsp+D8h] [rbp-28h]
  char *v80; // [rsp+E0h] [rbp-20h]
  char v81[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v82[8]; // [rsp+F0h] [rbp-10h] BYREF
  char v83[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v84; // [rsp+100h] [rbp+0h]
  struct _EVENT_DATA_DESCRIPTOR pExceptionObject; // [rsp+110h] [rbp+10h] BYREF
  __int128 v86; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  __int64 *v89; // [rsp+140h] [rbp+40h]
  __int64 v90; // [rsp+148h] [rbp+48h]

  v2 = a2;
  v66 = (unsigned __int64)a2;
  std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(&v70);
  std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(&v68);
  AppReadiness::User::GetBrokerSession(this, &v74, 0);
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  v80 = (char *)this + 56;
  v4 = (_QWORD *)*((_QWORD *)this + 41);
  while ( v4 != *((_QWORD **)this + 42) )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 64LL))(*v4) )
    {
      v15 = *v4;
      v64 = v15;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      if ( v71 == v72 )
      {
        std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<AppReadiness::ITask>>(
          &v70,
          (__int64)v71,
          (__int64)&v64);
      }
      else
      {
        Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(v71, &v64);
        v71 += 8;
      }
      if ( v64 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v16 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v4 + 80LL))(*v4, v83);
      v73 = 0;
      v17 = v16[1];
      if ( v17 )
      {
        v18 = *(_DWORD *)(v17 + 8);
        while ( v18 )
        {
          v19 = v18;
          v18 = _InterlockedCompareExchange((volatile signed __int32 *)(v17 + 8), v18 + 1, v18);
          if ( v19 == v18 )
          {
            v20 = *v16;
            *(_QWORD *)&v73 = *v16;
            v21 = (volatile signed __int32 *)v16[1];
            *((_QWORD *)&v73 + 1) = v21;
            goto LABEL_31;
          }
        }
      }
      v21 = (volatile signed __int32 *)*((_QWORD *)&v73 + 1);
      v20 = v73;
LABEL_31:
      v22 = v84;
      if ( v84 && _InterlockedExchangeAdd((volatile signed __int32 *)(v84 + 12), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 88LL))(*v4);
      v62 = v23;
      if ( v20 && v23 )
      {
        v63 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 72LL))(*v4);
        if ( v63 == -2147467260 )
          goto LABEL_45;
        v24 = (_OWORD *)(v20 + 40);
        pExceptionObject.Ptr = (ULONGLONG)AppReadiness::Storage::MatchPackageFamilyName;
        v86 = 0;
        v87 = 0;
        v88 = 0;
        if ( *(_QWORD *)(v20 + 64) > 7u )
          v24 = *(_OWORD **)v24;
        std::wstring::_Construct<2,unsigned short const *>(&v86, v24, *(_QWORD *)(v20 + 56));
        SystemTime.QuadPart = (LONGLONG)&pExceptionObject;
        v25 = (__int64 *)((char *)v2 + 8);
        v26 = *((_QWORD *)v2 + 2);
        for ( i = *v25; i != v26; i += 40 )
        {
          if ( ((__int64 (__fastcall *)(__int128 *, __int64))pExceptionObject.Ptr)(&v86, i) )
            break;
        }
        std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(&v86);
        if ( i != *(_QWORD *)(v66 + 16) )
          std::vector<std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>>::erase(v25, v81, i);
        if ( v63 < 0 )
        {
LABEL_45:
          LODWORD(v64) = v62;
          SystemTime.QuadPart = 0;
          v29 = NtQuerySystemTime(&SystemTime);
          v30 = ResultFromWin32FromStatus(v29);
          if ( v30 < 0 )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)&pExceptionObject,
              v30,
              "NtQuerySystemTime(&currentTime)",
              "AppReadiness::User::MarkPackageError",
              "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
              1217);
            throw (Windows::HResultException *)&pExceptionObject;
          }
          if ( (unsigned __int64)(SystemTime.QuadPart + 3000000000LL) < SystemTime.QuadPart )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)&pExceptionObject,
              -2147024362,
              "ULongLongAdd(currentTime.QuadPart, c_ErrorRetryDelay, &retryAfter.QuadPart)",
              "AppReadiness::User::MarkPackageError",
              "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
              1219);
            throw (Windows::HResultException *)&pExceptionObject;
          }
          v67 = SystemTime.QuadPart + 3000000000LL;
          pExceptionObject.Ptr = (ULONGLONG)AppReadiness::FindPackageErrorInfo;
          std::tuple<enum AppReadiness::Storage::PackageOperation,std::_Ph<1>>::tuple<enum AppReadiness::Storage::PackageOperation,std::_Ph<1>>(
            (__int64)&pExceptionObject.Size,
            v31,
            &v64);
          std::shared_ptr<AppReadiness::PackageInfo>::shared_ptr<AppReadiness::PackageInfo>(&v86, &v73);
          p_pExceptionObject = &pExceptionObject;
          v39 = *((_QWORD *)this + 32);
          for ( j = *((_QWORD *)this + 31); j != v39; j += 32 )
          {
            if ( ((__int64 (__fastcall *)(__int128 *, _QWORD, __int64))pExceptionObject.Ptr)(
                   &v86,
                   pExceptionObject.Reserved,
                   j) )
            {
              break;
            }
          }
          std::_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>::~_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>(&pExceptionObject);
          if ( j == *((_QWORD *)this + 32) )
          {
            if ( v21 )
              _InterlockedIncrement(v21 + 2);
            *(_QWORD *)&v86 = v20;
            *((_QWORD *)&v86 + 1) = v21;
            pExceptionObject.Size = v63;
            pExceptionObject.Reserved = v62;
            pExceptionObject.Ptr = v67;
            if ( *((_QWORD *)this + 32) == *((_QWORD *)this + 33) )
            {
              std::vector<AppReadiness::ErrorInfo>::_Emplace_reallocate<AppReadiness::ErrorInfo const &>(
                (__int64 *)this + 31,
                *((_QWORD *)this + 32),
                (const struct AppReadiness::ErrorInfo *)&pExceptionObject);
              v42 = (std::_Ref_count_base *)*((_QWORD *)&v86 + 1);
              v35 = v62;
            }
            else
            {
              AppReadiness::ErrorInfo::ErrorInfo(
                *((AppReadiness::ErrorInfo **)this + 32),
                (const struct AppReadiness::ErrorInfo *)&pExceptionObject);
              *((_QWORD *)this + 32) += 32LL;
            }
            if ( v42 )
            {
              std::_Ref_count_base::_Decref(v42);
              v35 = v62;
            }
            v34 = v63;
          }
          else
          {
            *(_QWORD *)j = v67;
            v34 = v63;
            *(_DWORD *)(j + 8) = v63;
            v35 = v62;
          }
          if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100) != 0 )
          {
            v54 = (_QWORD *)(v20 + 40);
            if ( *(_QWORD *)(v20 + 64) > 7u )
              v54 = (_QWORD *)*v54;
            v55 = (_QWORD *)((char *)this + 64);
            if ( *((_QWORD *)this + 11) > 7u )
              v55 = (_QWORD *)*v55;
            McTemplateU0zzqdm_EventWriteTransfer(
              (unsigned int)&v67,
              v41,
              (_DWORD)v55,
              (_DWORD)v54,
              v35,
              v34,
              (__int64)&v67);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v56 = (_QWORD *)(v20 + 40);
            if ( *(_QWORD *)(v20 + 64) > 7u )
              v56 = (_QWORD *)*v56;
            v57 = (_QWORD *)((char *)this + 64);
            if ( *((_QWORD *)this + 11) > 7u )
              v57 = (_QWORD *)*v57;
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
              (_DWORD)v57,
              (__int64)v56);
          }
        }
        else
        {
          LODWORD(v64) = v62;
          pExceptionObject.Ptr = (ULONGLONG)AppReadiness::FindPackageErrorInfo;
          std::tuple<enum AppReadiness::Storage::PackageOperation,std::_Ph<1>>::tuple<enum AppReadiness::Storage::PackageOperation,std::_Ph<1>>(
            (__int64)&pExceptionObject.Size,
            v28,
            &v64);
          v86 = 0;
          if ( v21 )
            _InterlockedIncrement(v21 + 2);
          *(_QWORD *)&v86 = v20;
          *((_QWORD *)&v86 + 1) = v21;
          SystemTime.QuadPart = (LONGLONG)&pExceptionObject;
          v32 = *((_QWORD *)this + 32);
          for ( k = *((_QWORD *)this + 31); k != v32; k += 32 )
          {
            if ( ((__int64 (__fastcall *)(__int128 *, _QWORD, __int64))pExceptionObject.Ptr)(
                   &v86,
                   pExceptionObject.Reserved,
                   k) )
            {
              break;
            }
          }
          std::_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>::~_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,enum AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>(&pExceptionObject);
          if ( k != *((_QWORD *)this + 32) )
          {
            *((_BYTE *)this + 217) = 1;
            std::vector<AppReadiness::ErrorInfo>::erase((char *)this + 248, v82, k);
          }
        }
        if ( (*(_BYTE *)(v20 + 140) & 2) != 0 && v74 && (v62 == 1 || v62 == 2) )
        {
          std::shared_ptr<AppReadiness::PackageInfo>::shared_ptr<AppReadiness::PackageInfo>(&v76, &v73);
          v78 = v58;
          v59 = *((_QWORD *)&v68 + 1);
          if ( *((_QWORD *)&v68 + 1) == v69 )
          {
            std::vector<std::pair<std::shared_ptr<AppReadiness::PackageInfo>,enum AppReadiness::BrokerPackageOperation>>::_Emplace_reallocate<std::pair<std::shared_ptr<AppReadiness::PackageInfo>,enum AppReadiness::BrokerPackageOperation>>(
              &v68,
              *((__int64 *)&v68 + 1),
              (__int64)&v76);
            v60 = v77;
          }
          else
          {
            **((_QWORD **)&v68 + 1) = v76;
            *(_QWORD *)(v59 + 8) = v77;
            v60 = 0;
            v77 = 0;
            *(_DWORD *)(v59 + 16) = v58;
            *((_QWORD *)&v68 + 1) += 24LL;
          }
          if ( v60 )
            std::_Ref_count_base::_Decref(v60);
        }
      }
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x2000) != 0 )
      {
        v43 = ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 3) - 1;
        v44 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 24LL))(*v4);
        v46 = (const wchar_t *)v44;
        if ( *(_QWORD *)(v44 + 24) > 7u )
          v46 = *(const wchar_t **)v44;
        v47 = (const wchar_t *)((char *)this + 64);
        if ( *((_QWORD *)this + 11) > 7u )
          v47 = *(const wchar_t **)v47;
        LODWORD(v64) = v43;
        if ( v47 )
        {
          v48 = -1;
          do
            ++v48;
          while ( v47[v48] );
          v49 = 2 * v48 + 2;
        }
        else
        {
          v49 = 10;
          v47 = L"NULL";
        }
        *(_QWORD *)&v86 = v47;
        *((_QWORD *)&v86 + 1) = v49;
        if ( v46 )
        {
          v50 = -1;
          do
            ++v50;
          while ( v46[v50] );
          v51 = 2 * v50 + 2;
        }
        else
        {
          v51 = 10;
          v46 = L"NULL";
        }
        v87 = v46;
        v88 = v51;
        v89 = &v64;
        v90 = 4;
        McGenEventWrite_EventWriteTransfer(
          (__int64)v47,
          (const EVENT_DESCRIPTOR *)User_RemoveTask,
          v45,
          4u,
          &pExceptionObject);
      }
      v36 = v4;
      v37 = (_QWORD *)*((_QWORD *)this + 42);
      for ( m = v4 + 1; m != v37; ++m )
        Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(v36++, m);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*((_QWORD *)this + 42) - 8LL);
      *((_QWORD *)this + 42) -= 8LL;
      *((_BYTE *)this + 376) = 1;
      v2 = (struct AppReadiness::Storage::PackageList *)v66;
      if ( v21 )
      {
        if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v21);
        }
      }
    }
    else
    {
      ++v4;
    }
  }
  if ( this != (AppReadiness::User *)-56LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
  v5 = (char *)v70;
  v6 = v71;
  if ( v70 != v71 )
  {
    do
    {
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v5 + 136LL))(*(_QWORD *)v5, 0x40000) )
        AppReadiness::LogTaskCompletion(this, *(_QWORD *)v5);
      v5 += 8;
    }
    while ( v5 != v6 );
  }
  v7 = v74;
  if ( v74 )
  {
    v53 = *((_QWORD *)&v68 + 1);
    for ( n = v68; n != v53; v7 = v74 )
    {
      AppReadiness::BrokerSession::Mark(v7);
      n += 24;
    }
    v61 = 0;
    AppReadiness::BrokerSession::CheckAndCompleteIterationIfNecessary(v7, 0, &v61);
    if ( v61 )
      AppReadiness::User::ClearBrokerSession(this);
  }
  v8 = v70 != v71;
  v9 = v75;
  if ( v75 && _InterlockedExchangeAdd((volatile signed __int32 *)v75 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v9)(v9);
    std::_Ref_count_base::_Decwref(v9);
  }
  if ( (_QWORD)v68 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::shared_ptr<AppReadiness::PackageInfo>,enum AppReadiness::BrokerPackageOperation>>>(
      v68,
      *((__int64 *)&v68 + 1));
    std::_Deallocate<16>((void *)v68, 8 * ((v69 - (__int64)v68) >> 3));
    v68 = 0;
    v69 = 0;
  }
  v10 = (char *)v70;
  if ( v70 )
  {
    v11 = v71;
    if ( v70 != v71 )
    {
      do
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v10);
        v10 += 8;
      }
      while ( v10 != v11 );
    }
    QuadPart = v70;
    v13 = (v72 - (_BYTE *)v70) & 0xFFFFFFFFFFFFFFF8uLL;
    v66 = v13;
    SystemTime.QuadPart = (LONGLONG)v70;
    if ( v13 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&SystemTime, &v66);
      QuadPart = (void *)SystemTime.QuadPart;
      v13 = v66;
    }
    operator delete(QuadPart, v13);
  }
  return v8;
}

```

## disassembly

```asm
0x18000c750  mov     [rsp-8+arg_10], rbx
0x18000c755  push    rbp
0x18000c756  push    rsi
0x18000c757  push    rdi
0x18000c758  push    r12
0x18000c75a  push    r13
0x18000c75c  push    r14
0x18000c75e  push    r15
0x18000c760  lea     rbp, [rsp-60h]
0x18000c765  sub     rsp, 160h
0x18000c76c  mov     rax, cs:__security_cookie
0x18000c773  xor     rax, rsp
0x18000c776  mov     [rbp+90h+var_40], rax
0x18000c77a  mov     rsi, rdx
0x18000c77d  mov     [rsp+190h+var_130], rdx
0x18000c782  mov     r13, rcx
0x18000c785  lea     rcx, [rbp+90h+var_108]
0x18000c789  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x18000c78e  nop
0x18000c78f  lea     rcx, [rsp+190h+var_120]
0x18000c794  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x18000c799  nop
0x18000c79a  xor     r8d, r8d
0x18000c79d  lea     rdx, [rbp+90h+var_E0]
0x18000c7a1  mov     rcx, r13
0x18000c7a4  call    ?GetBrokerSession@User@AppReadiness@@IEAA?AV?$shared_ptr@VBrokerSession@AppReadiness@@@std@@_N@Z; AppReadiness::User::GetBrokerSession(bool)
0x18000c7a9  nop
0x18000c7aa  lea     rdi, [r13+38h]
0x18000c7ae  mov     rcx, rdi; SRWLock
0x18000c7b1  call    cs:__imp_AcquireSRWLockExclusive
0x18000c7b7  mov     [rbp+90h+var_B0], rdi
0x18000c7bb  mov     rbx, [r13+148h]
0x18000c7c2  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000c7c9  lea     rdi, AppReadiness__Storage__MatchPackageFamilyName
0x18000c7d0  cmp     rbx, [r13+150h]
0x18000c7d7  jz      short loc_18000C7F6
0x18000c7d9  mov     rcx, [rbx]
0x18000c7dc  mov     rax, [rcx]
0x18000c7df  mov     rax, [rax+40h]
0x18000c7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e8  test    al, al
0x18000c7ea  jnz     loc_18000C8C0
0x18000c7f0  add     rbx, 8
0x18000c7f4  jmp     short loc_18000C7D0
0x18000c7f6  lea     rdi, [r13+38h]
0x18000c7fa  test    rdi, rdi
0x18000c7fd  jnz     loc_18000CAE3
0x18000c803  mov     rbx, [rbp+90h+var_108]
0x18000c807  mov     rdi, [rbp+90h+var_100]
0x18000c80b  cmp     rbx, rdi
0x18000c80e  jnz     loc_18000CEFF
0x18000c814  mov     rcx, [rbp+90h+var_E0]; this
0x18000c818  test    rcx, rcx
0x18000c81b  jnz     loc_18000CE5D
0x18000c821  mov     rax, [rbp+90h+var_100]
0x18000c825  cmp     [rbp+90h+var_108], rax
0x18000c829  setnz   sil
0x18000c82d  mov     rbx, [rbp+90h+var_D8]
0x18000c831  test    rbx, rbx
0x18000c834  jz      short loc_18000C846
0x18000c836  lock xadd [rbx+8], r14d
0x18000c83c  cmp     r14d, 1
0x18000c840  jz      loc_18000CE99
0x18000c846  mov     rcx, qword ptr [rsp+190h+var_120]
0x18000c84b  test    rcx, rcx
0x18000c84e  jnz     loc_18000CEB4
0x18000c854  mov     rbx, [rbp+90h+var_108]
0x18000c858  test    rbx, rbx
0x18000c85b  jz      short loc_18000C895
0x18000c85d  mov     rdi, [rbp+90h+var_100]
0x18000c861  cmp     rbx, rdi
0x18000c864  jnz     loc_18000CAF1
0x18000c86a  mov     rcx, [rbp+90h+var_108]; void *
0x18000c86e  mov     rdx, [rbp+90h+var_F8]
0x18000c872  sub     rdx, rcx
0x18000c875  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000c879  mov     [rsp+190h+var_130], rdx
0x18000c87e  mov     qword ptr [rsp+190h+SystemTime], rcx
0x18000c883  cmp     rdx, 1000h
0x18000c88a  jnb     loc_18000D157
0x18000c890  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c895  movzx   eax, sil
0x18000c899  mov     rcx, [rbp+90h+var_40]
0x18000c89d  xor     rcx, rsp; StackCookie
0x18000c8a0  call    __security_check_cookie
0x18000c8a5  mov     rbx, [rsp+190h+arg_10]
0x18000c8ad  add     rsp, 160h
0x18000c8b4  pop     r15
0x18000c8b6  pop     r14
0x18000c8b8  pop     r13
0x18000c8ba  pop     r12
0x18000c8bc  pop     rdi
0x18000c8bd  pop     rsi
0x18000c8be  pop     rbp
0x18000c8bf  retn
0x18000c8c0  mov     rcx, [rbx]
0x18000c8c3  mov     [rsp+190h+var_140], rcx
0x18000c8c8  test    rcx, rcx
0x18000c8cb  jz      short loc_18000C8DA
0x18000c8cd  mov     rax, [rcx]
0x18000c8d0  mov     rax, [rax+8]
0x18000c8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d9  nop
0x18000c8da  mov     rcx, [rbp+90h+var_100]
0x18000c8de  cmp     rcx, [rbp+90h+var_F8]
0x18000c8e2  jz      loc_18000CFE0
0x18000c8e8  lea     rdx, [rsp+190h+var_140]
0x18000c8ed  call    ??0?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::ComPtr<AppReadiness::ITask>(Microsoft::WRL::ComPtr<AppReadiness::ITask> &&)
0x18000c8f2  add     [rbp+90h+var_100], 8
0x18000c8f7  mov     rcx, [rsp+190h+var_140]
0x18000c8fc  test    rcx, rcx
0x18000c8ff  jz      short loc_18000C90E
0x18000c901  mov     rax, [rcx]
0x18000c904  mov     rax, [rax+10h]
0x18000c908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90d  nop
0x18000c90e  mov     rcx, [rbx]
0x18000c911  mov     rax, [rcx]
0x18000c914  lea     rdx, [rbp+90h+var_98]
0x18000c918  mov     rax, [rax+50h]
0x18000c91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c921  mov     r8, rax
0x18000c924  xorps   xmm0, xmm0
0x18000c927  movdqu  [rbp+90h+var_F0], xmm0
0x18000c92c  mov     rdx, [rax+8]
0x18000c930  test    rdx, rdx
0x18000c933  jz      loc_18000CE50
0x18000c939  mov     eax, [rdx+8]
0x18000c93c  test    eax, eax
0x18000c93e  jz      loc_18000CE50
0x18000c944  lea     ecx, [rax+1]
0x18000c947  lock cmpxchg [rdx+8], ecx
0x18000c94c  jnz     short loc_18000C93C
0x18000c94e  mov     r15, [r8]
0x18000c951  mov     qword ptr [rbp+90h+var_F0], r15
0x18000c955  mov     r12, [r8+8]
0x18000c959  mov     qword ptr [rbp+90h+var_F0+8], r12
0x18000c95d  mov     rcx, [rbp+90h+var_90]
0x18000c961  test    rcx, rcx
0x18000c964  jz      short loc_18000C977
0x18000c966  mov     eax, r14d
0x18000c969  lock xadd [rcx+0Ch], eax
0x18000c96e  cmp     eax, 1
0x18000c971  jz      loc_18000CFF6
0x18000c977  mov     rcx, [rbx]
0x18000c97a  mov     rax, [rcx]
0x18000c97d  mov     rax, [rax+58h]
0x18000c981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c986  mov     [rsp+190h+var_14C], eax
0x18000c98a  test    r15, r15
0x18000c98d  jz      loc_18000CBDF
0x18000c993  test    eax, eax
0x18000c995  jz      loc_18000CBDF
0x18000c99b  mov     rdx, [rbx]
0x18000c99e  mov     rcx, [rdx]
0x18000c9a1  mov     rax, [rcx+48h]
0x18000c9a5  mov     rcx, rdx
0x18000c9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ad  mov     [rsp+190h+var_148], eax
0x18000c9b1  xor     r8d, r8d
0x18000c9b4  cmp     eax, 80004004h
0x18000c9b9  jz      loc_18000CA5E
0x18000c9bf  lea     rdx, [r15+28h]
0x18000c9c3  mov     [rbp+90h+pExceptionObject], rdi
0x18000c9c7  xorps   xmm0, xmm0
0x18000c9ca  movups  [rbp+90h+var_70], xmm0
0x18000c9ce  mov     [rbp+90h+var_60], r8
0x18000c9d2  mov     [rbp+90h+var_58], r8
0x18000c9d6  mov     r8, [rdx+10h]
0x18000c9da  cmp     qword ptr [rdx+18h], 7
0x18000c9df  ja      loc_18000CADB
0x18000c9e5  lea     rcx, [rbp+90h+var_70]
0x18000c9e9  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18000c9ee  lea     rax, [rbp+90h+pExceptionObject]
0x18000c9f2  mov     qword ptr [rsp+190h+SystemTime], rax
0x18000c9f7  lea     r14, [rsi+8]
0x18000c9fb  mov     rsi, [r14+8]
0x18000c9ff  mov     rdi, [r14]
0x18000ca02  cmp     rdi, rsi
0x18000ca05  jz      short loc_18000CA2D
0x18000ca07  nop     word ptr [rax+rax+00000000h]
0x18000ca10  mov     rdx, rdi
0x18000ca13  lea     rcx, [rbp+90h+var_70]
0x18000ca17  mov     rax, [rbp+90h+pExceptionObject]
0x18000ca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca20  test    al, al
0x18000ca22  jnz     short loc_18000CA2D
0x18000ca24  add     rdi, 28h ; '('
0x18000ca28  cmp     rdi, rsi
0x18000ca2b  jnz     short loc_18000CA10
0x18000ca2d  lea     rcx, [rbp+90h+var_70]
0x18000ca31  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18000ca36  mov     rax, [rsp+190h+var_130]
0x18000ca3b  cmp     rdi, [rax+10h]
0x18000ca3f  jz      short loc_18000CA50
0x18000ca41  mov     r8, rdi
0x18000ca44  lea     rdx, [rbp+90h+var_A8]
0x18000ca48  mov     rcx, r14
0x18000ca4b  call    ?erase@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@@std@@@std@@@2@@Z; std::vector<std::pair<std::wstring,AppReadiness::Storage::PackageOperation>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<std::wstring,AppReadiness::Storage::PackageOperation>>>>)
0x18000ca50  cmp     [rsp+190h+var_148], 0
0x18000ca55  jge     loc_18000CB07
0x18000ca5b  xor     r8d, r8d
0x18000ca5e  mov     eax, [rsp+190h+var_14C]
0x18000ca62  mov     dword ptr [rsp+190h+var_140], eax
0x18000ca66  mov     qword ptr [rsp+190h+SystemTime], r8
0x18000ca6b  lea     rcx, [rsp+190h+SystemTime]; SystemTime
0x18000ca70  call    cs:__imp_NtQuerySystemTime
0x18000ca76  mov     ecx, eax; int
0x18000ca78  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000ca7d  test    eax, eax
0x18000ca7f  js      loc_18000D0EB
0x18000ca85  mov     ecx, 0B2D05E00h
0x18000ca8a  add     rcx, qword ptr [rsp+190h+SystemTime]
0x18000ca8f  cmp     rcx, qword ptr [rsp+190h+SystemTime]
0x18000ca94  jnb     loc_18000CC8A
0x18000ca9a  mov     [rsp+190h+var_168], 4C3h; int
0x18000caa2  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000caa9  mov     [rsp+190h+var_170], rcx; char *
0x18000caae  lea     r9, aAppreadinessUs_3; "AppReadiness::User::MarkPackageError"
0x18000cab5  lea     r8, aUlonglongaddCu; "ULongLongAdd(currentTime.QuadPart, c_Er"...
0x18000cabc  mov     edx, 80070216h; int
0x18000cac1  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18000cac5  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000caca  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000cad1  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18000cad5  call    _CxxThrowException_0
0x18000cadb  mov     rdx, [rdx]
0x18000cade  jmp     loc_18000C9E5
0x18000cae3  mov     rcx, rdi; SRWLock
0x18000cae6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000caec  jmp     loc_18000C803
0x18000caf1  mov     rcx, rbx
0x18000caf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000caf9  add     rbx, 8
0x18000cafd  cmp     rbx, rdi
0x18000cb00  jnz     short loc_18000CAF1
0x18000cb02  jmp     loc_18000C86A
0x18000cb07  mov     eax, [rsp+190h+var_14C]
0x18000cb0b  mov     dword ptr [rsp+190h+var_140], eax
0x18000cb0f  lea     rax, AppReadiness__FindPackageErrorInfo
0x18000cb16  mov     [rbp+90h+pExceptionObject], rax
0x18000cb1a  lea     r8, [rsp+190h+var_140]
0x18000cb1f  lea     rcx, [rbp+90h+var_78]
0x18000cb23  call    ??$?0U_Exact_args_t@std@@AEAW4PackageOperation@Storage@AppReadiness@@AEBU?$_Ph@$00@1@$0A@@?$tuple@W4PackageOperation@Storage@AppReadiness@@U?$_Ph@$00@std@@@std@@QEAA@U_Exact_args_t@1@AEAW4PackageOperation@Storage@AppReadiness@@AEBU?$_Ph@$00@1@@Z; std::tuple<AppReadiness::Storage::PackageOperation,std::_Ph<1>>::tuple<AppReadiness::Storage::PackageOperation,std::_Ph<1>>(std::_Exact_args_t,AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &)
0x18000cb28  xorps   xmm0, xmm0
0x18000cb2b  movdqu  [rbp+90h+var_70], xmm0
0x18000cb30  test    r12, r12
0x18000cb33  jz      short loc_18000CB3B
0x18000cb35  lock inc dword ptr [r12+8]
0x18000cb3b  mov     qword ptr [rbp+90h+var_70], r15
0x18000cb3f  mov     qword ptr [rbp+90h+var_70+8], r12
0x18000cb43  lea     rax, [rbp+90h+pExceptionObject]
0x18000cb47  mov     qword ptr [rsp+190h+SystemTime], rax
0x18000cb4c  mov     r14, [r13+100h]
0x18000cb53  mov     rdi, [r13+0F8h]
0x18000cb5a  cmp     rdi, r14
0x18000cb5d  jnz     loc_18000D007
0x18000cb63  lea     rcx, [rbp+90h+pExceptionObject]
0x18000cb67  call    ??1?$_Binder@U_Unforced@std@@P6A_NAEBV?$shared_ptr@VPackageInfo@AppReadiness@@@2@W4PackageOperation@Storage@AppReadiness@@AEBUErrorInfo@6@@ZAEBV32@AEAW4456@AEBU?$_Ph@$00@2@@std@@QEAA@XZ; std::_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>::~_Binder<std::_Unforced,bool (*)(std::shared_ptr<AppReadiness::PackageInfo> const &,AppReadiness::Storage::PackageOperation,AppReadiness::ErrorInfo const &),std::shared_ptr<AppReadiness::PackageInfo> const &,AppReadiness::Storage::PackageOperation &,std::_Ph<1> const &>(void)
0x18000cb6c  cmp     rdi, [r13+100h]
0x18000cb73  jz      short loc_18000CBCA
0x18000cb75  mov     byte ptr [r13+0D9h], 1
0x18000cb7d  mov     r8, rdi
0x18000cb80  lea     rdx, [rbp+90h+var_A0]
0x18000cb84  lea     rcx, [r13+0F8h]
0x18000cb8b  call    ?erase@?$vector@UErrorInfo@AppReadiness@@V?$allocator@UErrorInfo@AppReadiness@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UErrorInfo@AppReadiness@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UErrorInfo@AppReadiness@@@std@@@std@@@2@@Z; std::vector<AppReadiness::ErrorInfo>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<AppReadiness::ErrorInfo>>>)
0x18000cb90  jmp     short loc_18000CBCA
0x18000cb92  mov     rax, [rsp+190h+var_128]
0x18000cb97  mov     [rdi], rax
0x18000cb9a  mov     eax, [rsp+190h+var_148]
0x18000cb9e  mov     [rdi+8], eax
0x18000cba1  mov     r10d, [rsp+190h+var_14C]
0x18000cba6  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 1
0x18000cbad  jnz     loc_18000CF2D
0x18000cbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbba  lea     rax, WPP_GLOBAL_Control
0x18000cbc1  cmp     rcx, rax
0x18000cbc4  jnz     loc_18000D076
0x18000cbca  test    byte ptr [r15+8Ch], 2
0x18000cbd2  jnz     loc_18000CFA1
0x18000cbd8  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000cbdf  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 20h
0x18000cbe6  jnz     loc_18000CD62
0x18000cbec  mov     rsi, rbx
0x18000cbef  mov     r14, [r13+150h]
0x18000cbf6  lea     rdi, [rbx+8]
0x18000cbfa  cmp     rdi, r14
0x18000cbfd  jz      short loc_18000CC18
0x18000cbff  nop
0x18000cc00  mov     rdx, rdi
0x18000cc03  mov     rcx, rsi
0x18000cc06  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x18000cc0b  add     rsi, 8
0x18000cc0f  add     rdi, 8
0x18000cc13  cmp     rdi, r14
0x18000cc16  jnz     short loc_18000CC00
0x18000cc18  mov     rcx, [r13+150h]
0x18000cc1f  sub     rcx, 8
0x18000cc23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cc28  add     qword ptr [r13+150h], 0FFFFFFFFFFFFFFF8h
  ... truncated ...
```
