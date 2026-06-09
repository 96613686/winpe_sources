# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetCurrentResult(bool,tagVARIANT *)

- ea: `0x18001b320`
- end: `0x18001c1b2`
- name: `?GetCurrentResult@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJ_NPEAUtagVARIANT@@@Z`
- size: `3730`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this, char, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000334c`
- `0x18000b150`
- `0x1800109f0`
- `0x180010be4`
- `0x18001b320`
- `0x18001c1b4`
- `0x18001f72c`
- `0x18001f82c`
- `0x180020004`
- `0x180023a78`
- `0x180024ba8`
- `0x180024c30`
- `0x180024d00`
- `0x1800256ac`
- `0x18002a794`
- `0x18002eaac`
- `0x180037f10`
- `0x18003d864`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004a088`
- `0x18004a0f8`
- `0x18004b640`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001b8e0`
- `KERNEL32!WaitForSingleObject` at `0x18001b8e0`
- `KERNEL32!DeleteFileW` at `0x18001c01c`
- `KERNEL32!DeleteFileW` at `0x18001c069`
- `KERNEL32!DeleteFileW` at `0x18001c01c`
- `KERNEL32!DeleteFileW` at `0x18001c069`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b991`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bb83`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b991`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001bb83`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b966`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b966`
- `KERNEL32!LeaveCriticalSection` at `0x18001b77f`
- `KERNEL32!LeaveCriticalSection` at `0x18001b821`
- `KERNEL32!LeaveCriticalSection` at `0x18001b9fc`
- `KERNEL32!LeaveCriticalSection` at `0x18001baa6`
- `KERNEL32!LeaveCriticalSection` at `0x18001bb56`
- `KERNEL32!LeaveCriticalSection` at `0x18001bbf6`
- `KERNEL32!LeaveCriticalSection` at `0x18001c171`
- `KERNEL32!LeaveCriticalSection` at `0x18001b77f`
- `KERNEL32!LeaveCriticalSection` at `0x18001b821`
- `KERNEL32!LeaveCriticalSection` at `0x18001b9fc`
- `KERNEL32!LeaveCriticalSection` at `0x18001baa6`
- `KERNEL32!LeaveCriticalSection` at `0x18001bb56`
- `KERNEL32!LeaveCriticalSection` at `0x18001bbf6`
- `KERNEL32!LeaveCriticalSection` at `0x18001c171`
- `KERNEL32!EnterCriticalSection` at `0x18001b38a`
- `KERNEL32!EnterCriticalSection` at `0x18001b420`
- `KERNEL32!EnterCriticalSection` at `0x18001b38a`
- `KERNEL32!EnterCriticalSection` at `0x18001b420`
- `KERNEL32!GetLastError` at `0x18001c02d`
- `KERNEL32!GetLastError` at `0x18001c07a`
- `KERNEL32!GetLastError` at `0x18001c02d`
- `KERNEL32!GetLastError` at `0x18001c07a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf82`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bf82`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0fc`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c0c7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001c0c7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c0d7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001c0d7`

## string_xrefs

- `0x18001bea5`: `No ETL files generated during collection session - nothing to merge.`
- `0x18001c03c`: `Failed to delete ETL file: %s. Error code: %d`
- `0x18001c087`: `Failed to delete merged ETL file: %s. Error code: %d`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetCurrentResult(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        char a2,
        struct tagVARIANT *a3)
{
  __int64; // rax
  int started; // r14d
  _QWORD *v6; // r14
  signed __int64 v7; // rdi
  signed __int64 v8; // rax
  signed __int64 v9; // rbx
  __int64 v10; // r15
  _DWORD *v11; // rax
  __int64 *v12; // rax
  __int64 *v13; // rbx
  __int64 *v14; // rdx
  void **v15; // rdi
  void **v16; // rcx
  __int64 v17; // r13
  _OWORD *v18; // rax
  _OWORD *v19; // rdi
  _QWORD *v20; // rcx
  __int64 *v21; // rbx
  __int64 *v22; // r15
  _QWORD *v23; // r12
  _OWORD *v24; // rax
  void ***v25; // rax
  __int64 v26; // r13
  void **v27; // rbx
  __int64 v28; // rdx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *v31; // r15
  struct _RTL_CRITICAL_SECTION *v32; // rdi
  _BYTE *v33; // rbx
  signed __int64 v34; // r15
  __int64 v35; // rsi
  _BYTE *v36; // rbx
  signed __int64 v37; // rdi
  __int64 v38; // rsi
  void *v39; // rcx
  _BYTE *v40; // rbx
  signed __int64 v41; // r15
  __int64 v42; // rsi
  _BYTE *v43; // rbx
  signed __int64 v44; // r15
  __int64 v45; // rsi
  _BYTE *v46; // rbx
  signed __int64 v47; // rdi
  __int64 v48; // rsi
  _BYTE *v49; // rbx
  __int64 v50; // rdi
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *i; // rbx
  int v52; // eax
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v54; // rbx
  unsigned int v55; // edi
  Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *v56; // rcx
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController **v57; // r14
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController **v58; // r12
  DiagHubCommon::LogStream *v59; // rdi
  DiagHubCommon::LogStream *v60; // rdi
  struct tagVARIANT *v61; // rdi
  OLECHAR *v62; // rcx
  BSTR v63; // rax
  UINT v64; // eax
  void (*v65)(void *); // [rsp+20h] [rbp-3D8h]
  bool v67; // [rsp+30h] [rbp-3C8h]
  unsigned __int16 *v68; // [rsp+38h] [rbp-3C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-3B8h] BYREF
  __int128 v70; // [rsp+48h] [rbp-3B0h] BYREF
  __int64 v71; // [rsp+58h] [rbp-3A0h]
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *v72; // [rsp+60h] [rbp-398h] BYREF
  unsigned int v73; // [rsp+68h] [rbp-390h]
  LPCWSTR lpFileName; // [rsp+70h] [rbp-388h] BYREF
  int *v75; // [rsp+78h] [rbp-380h] BYREF
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *v76; // [rsp+80h] [rbp-378h]
  int *v77; // [rsp+88h] [rbp-370h]
  __int64 v78; // [rsp+90h] [rbp-368h]
  __int128 v79; // [rsp+98h] [rbp-360h]
  LPCRITICAL_SECTION v80; // [rsp+A8h] [rbp-350h]
  _QWORD v81[3]; // [rsp+B0h] [rbp-348h] BYREF
  __int64 *v82; // [rsp+C8h] [rbp-330h]
  signed __int64 v83; // [rsp+D0h] [rbp-328h]
  signed __int64 v84; // [rsp+D8h] [rbp-320h]
  signed __int64 v85; // [rsp+E0h] [rbp-318h]
  struct tagVARIANT *v86; // [rsp+E8h] [rbp-310h]
  _QWORD v87[4]; // [rsp+F0h] [rbp-308h] BYREF
  char *v88; // [rsp+110h] [rbp-2E8h]
  int v89; // [rsp+118h] [rbp-2E0h]
  int v90; // [rsp+120h] [rbp-2D8h] BYREF
  char v91; // [rsp+124h] [rbp-2D4h] BYREF
  struct DhPackaging::IDhPackage *v92; // [rsp+128h] [rbp-2D0h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp-2C8h] BYREF
  _BYTE v94[16]; // [rsp+140h] [rbp-2B8h] BYREF
  char v95; // [rsp+150h] [rbp-2A8h] BYREF
  _BYTE v96[104]; // [rsp+158h] [rbp-2A0h] BYREF
  __int64 v97; // [rsp+1C0h] [rbp-238h] BYREF
  __int64 v98; // [rsp+1C8h] [rbp-230h]
  __int64 v99; // [rsp+3C0h] [rbp-38h] BYREF

  v86 = a3;
  v72 = this;
  lpFileName = (LPCWSTR)this;
  if ( *((_BYTE *)this + 3576) )
  {
     = 3775987731LL;
    goto LABEL_145;
  }
  v80 = (LPCRITICAL_SECTION)((char *)this + 3536);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3536));
  if ( (*((_BYTE *)this + 856) & 4) != 0 )
  {
    started = -2147019873;
    goto LABEL_128;
  }
  started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(this);
  v90 = started;
  if ( started < 0 )
  {
    _mm_lfence();
    goto LABEL_128;
  }
  _mm_lfence();
  v70 = 0;
  v71 = 0;
  v73 = *((_DWORD *)this + 215);
  `eh vector constructor iterator'(
    v94,
    0x80u,
    5u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::EtwSessionInformation,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 3496);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3496));
  v6 = (_QWORD *)((char *)this + 2888);
  v7 = v96 - (_BYTE *)this;
  v84 = v96 - (_BYTE *)this;
  v8 = v94 - (_BYTE *)this;
  v85 = v94 - (_BYTE *)this;
  v9 = &v95 - (char *)this;
  v83 = &v95 - (char *)this;
  v10 = 5;
  v68 = (unsigned __int16 *)5;
  do
  {
    Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
      (char *)v6 + v8 - 2888,
      v6 - 4);
    v11 = (_DWORD *)((char *)v6 + v9 - 2888);
    if ( v6 - 2 != (_QWORD *)v11 )
    {
      v88 = (char *)(v6 - 2);
      *((_DWORD *)v6 - 4) = *v11;
      v12 = *(__int64 **)((char *)v6 + v7 - 2888);
      v82 = v12;
      v13 = (__int64 *)*v12;
      v14 = v6 - 1;
      v15 = (void **)*(v6 - 1);
      v16 = (void **)*v15;
      while ( 1 )
      {
        if ( v16 == v15 )
        {
          v77 = (int *)(v6 - 1);
          v17 = 0;
          v78 = 0;
          v79 = 0;
          if ( v13 == v12 )
          {
            v19 = (_OWORD *)*((_QWORD *)&v79 + 1);
            v20 = (_QWORD *)v79;
          }
          else
          {
            v75 = (int *)(v6 - 1);
            v76 = 0;
            v18 = operator new(0x20u);
            v19 = v18;
            v18[1] = *((_OWORD *)v13 + 1);
            v76 = 0;
            *((_QWORD *)&v79 + 1) = v18;
            v20 = v18;
            *(_QWORD *)&v79 = v18;
            v17 = 1;
            v78 = 1;
            v21 = (__int64 *)*v13;
            v22 = v82;
            if ( v21 != v82 )
            {
              v23 = v18;
              do
              {
                v76 = 0;
                v24 = operator new(0x20u);
                v24[1] = *((_OWORD *)v21 + 1);
                *v23 = v24;
                *((_QWORD *)v24 + 1) = v23;
                v76 = 0;
                v23 = v24;
                *(_QWORD *)&v79 = v24;
                v78 = ++v17;
                v21 = (__int64 *)*v21;
              }
              while ( v21 != v22 );
              v20 = v24;
            }
            v14 = v6 - 1;
            v10 = (__int64)v68;
          }
          v28 = *v14;
          if ( v17 )
          {
            v29 = *(_QWORD **)(v28 + 8);
            *((_QWORD *)v19 + 1) = v29;
            *v29 = v19;
            *v20 = v28;
            *(_QWORD *)(v28 + 8) = v20;
            *v6 += v17;
          }
          goto LABEL_26;
        }
        if ( v13 == v12 )
          break;
        *((_OWORD *)v16 + 1) = *((_OWORD *)v13 + 1);
        v16 = (void **)*v16;
        v13 = (__int64 *)*v13;
      }
      if ( v16 != v15 )
      {
        v25 = (void ***)v16[1];
        *v25 = v15;
        v15[1] = v25;
        v26 = 0;
        do
        {
          v27 = (void **)*v16;
          operator delete(v16);
          v16 = v27;
          ++v26;
        }
        while ( v27 != v15 );
        *v6 -= v26;
      }
LABEL_26:
      v30 = std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Desired_grow_bucket_count(
              v6 - 2,
              *v6);
      std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Forced_rehash(
        v6 - 2,
        v30);
      v9 = v83;
      v7 = v84;
    }
    v6 += 16;
    v68 = (unsigned __int16 *)--v10;
    v8 = v85;
  }
  while ( v10 );
  v77 = &v90;
  v78 = (__int64)v94;
  v31 = v72;
  *(_QWORD *)&v79 = v72;
  _InterlockedIncrement((volatile signed __int32 *)v72 + 215);
  v32 = lpCriticalSection;
  if ( !a2 )
  {
    v67 = 0;
    v81[0] = &v90;
    v81[1] = v94;
    v81[2] = v72;
    if ( *((_BYTE *)v72 + 3578) )
    {
      started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(
                  v72,
                  (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)v94,
                  (const unsigned __int16 **)&v68);
      v90 = started;
      if ( started < 0 )
      {
        _mm_lfence();
        DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
        if ( v90 < 0 )
        {
          v33 = v94;
          v34 = v31 - (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)v94;
          v35 = 5;
          do
          {
            Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
              &v33[v34 + 2856],
              v33);
            v33 += 128;
            --v35;
          }
          while ( v35 );
        }
        goto LABEL_58;
      }
      if ( v68 )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::vector<unsigned short const *>::push_back(&v70, &v68);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            _mm_lfence();
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001B7C5);
            DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
            if ( v90 < 0 )
            {
              v36 = v94;
              v37 = (char *)lpFileName - v94;
              v38 = 5;
              do
              {
                Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
                  &v36[v37 + 2856],
                  v36);
                v36 += 128;
                --v38;
              }
              while ( v38 );
            }
LABEL_40:
            LeaveCriticalSection(lpCriticalSection);
            `eh vector destructor iterator'(
              v94,
              0x80u,
              5u,
              (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
            goto LABEL_41;
          }
        }
      }
    }
    v91 = 0;
    v87[0] = &v90;
    v87[1] = &v91;
    v87[2] = v94;
    v87[3] = v31;
    if ( *((_BYTE *)v31 + 3936)
      && v97
      && v98
      && *(_QWORD *)(v97 + 16)
      && (v39 = *(void **)(v98 + 32)) != 0
      && WaitForSingleObject(v39, 0) )
    {
      Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
        (char *)v31 + 2984,
        &v97);
      v67 = 1;
      v91 = 1;
    }
    else
    {
      started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(
                  v31,
                  (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)&v97,
                  (const unsigned __int16 **)&v68);
      v90 = started;
      if ( started < 0 )
      {
        _mm_lfence();
        DiagHubCommon::ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___::_ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___(v87);
        DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
        if ( v90 < 0 )
        {
          v43 = v94;
          v44 = v31 - (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)v94;
          v45 = 5;
          do
          {
            Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
              &v43[v44 + 2856],
              v43);
            v43 += 128;
            --v45;
          }
          while ( v45 );
        }
LABEL_58:
        LeaveCriticalSection(v32);
        `eh vector destructor iterator'(
          v94,
          0x80u,
          5u,
          (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
LABEL_127:
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(&v70);
        goto LABEL_128;
      }
      if ( v68 )
      {
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          std::vector<unsigned short const *>::push_back(&v70, &v68);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            _mm_lfence();
            __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18001BAEC);
            DiagHubCommon::ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___::_ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___(v87);
            DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
            if ( v90 < 0 )
            {
              v46 = v94;
              v47 = (char *)lpFileName - v94;
              v48 = 5;
              do
              {
                Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
                  &v46[v47 + 2856],
                  v46);
                v46 += 128;
                --v48;
              }
              while ( v48 );
            }
            goto LABEL_40;
          }
        }
      }
    }
    v75 = &v90;
    v76 = v31;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
      L"Starting new session with counter %d prior to shutting down previous",
      *((unsigned int *)v31 + 215));
    v88 = (char *)v31 + 2848;
    v89 = 1;
    AcquireSRWLockExclusive((PSRWLOCK)v31 + 356);
    started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StartAllConfiguredEtwSessions_Unsafe(
                v31,
                v67);
    v90 = started;
    if ( started < 0 )
    {
      _mm_lfence();
      ReleaseSRWLockExclusive((PSRWLOCK)v31 + 356);
      DiagHubCommon::ScopeGuard__lambda_e393b748e22ad456cb5cd095565287f5___::_ScopeGuard__lambda_e393b748e22ad456cb5cd095565287f5___(&v75);
      DiagHubCommon::ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___::_ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___(v87);
      DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
      if ( v90 < 0 )
      {
        v40 = v94;
        v41 = v31 - (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)v94;
        v42 = 5;
        do
        {
          Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
            &v40[v41 + 2856],
            v40);
          v40 += 128;
          --v42;
        }
        while ( v42 );
      }
      goto LABEL_58;
    }
    _mm_lfence();
    ReleaseSRWLockExclusive((PSRWLOCK)v31 + 356);
    DiagHubCommon::ScopeGuard__lambda_e393b748e22ad456cb5cd095565287f5___::_ScopeGuard__lambda_e393b748e22ad456cb5cd095565287f5___(&v75);
    DiagHubCommon::ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___::_ScopeGuard__lambda_40824cb0f28bd260ad9fc55d2afee6a7___(v87);
    DiagHubCommon::ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___::_ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___(v81);
  }
  if ( v90 < 0 )
  {
    v49 = v94;
    v50 = 5;
    do
    {
      Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(
        &v49[v31 - (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)v94 + 2856],
        v49);
      v49 += 128;
      --v50;
    }
    while ( v50 );
    v32 = lpCriticalSection;
  }
  LeaveCriticalSection(v32);
  started = 0;
  for ( i = (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)v94;
        i != (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)&v99;
        i = (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *)((char *)i + 128) )
  {
    lpCriticalSection = 0;
    v52 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(
            v31,
            i,
            (const unsigned __int16 **)&lpCriticalSection);
    v90 = v52;
    if ( v52 < 0 )
      started = v52;
    if ( lpCriticalSection )
    {
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        std::vector<unsigned short const *>::push_back(&v70, &lpCriticalSection);
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_18001BC4E);
          `eh vector destructor iterator'(
            v94,
            0x80u,
            5u,
            (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
LABEL_41:
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(&v70);
          started = -2147024882;
LABEL_128:
          LeaveCriticalSection(v80);
           = (unsigned int)started;
LABEL_145:
          ;
        }
      }
    }
  }
  v90 = started;
  if ( started >= 0 )
  {
    v92 = 0;
    if ( (*((_BYTE *)v31 + 856) & 4) != 0 )
    {
      started = -2147019873;
      v90 = -2147019873;
    }
    else
    {
      started = Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::GetPackageResult(
                  (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)((char *)v31 + 880),
                  &GUID_03779dc9_70da_4063_808f_43ee228b18c4,
                  (void **)&v92);
      v90 = started;
      if ( started >= 0 )
      {
        Instance = ATL::CAtlStringMgr::GetInstance();
        if ( !Instance )
          ATL::AtlThrowImpl(-2147467259);
        v54 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                            + 24);
        lpFileName = v54;
        if ( (_QWORD)v70 == *((_QWORD *)&v70 + 1) )
        {
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"No ETL files generated during collection session - nothing to merge.");
          v55 = v73;
        }
        else
        {
          _mm_lfence();
          started = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                      *((Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)v31 + 491),
                      (const unsigned __int16 **)&v72);
          v90 = started;
          if ( started < 0 )
          {
            _mm_lfence();
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v54 - 3) + 8LL))(*((_QWORD *)v54 - 3));
            }
            if ( !v92 )
              goto LABEL_126;
            goto LABEL_125;
          }
          _mm_lfence();
          v55 = v73;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &lpFileName,
            L"%ssc.user_aux.%d.etl",
            v72,
            v73);
          v54 = lpFileName;
          started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddEtwSessionResultsToPackage(
                      v31,
                      &v70,
                      lpFileName,
                      v92);
          v90 = started;
          if ( started < 0 )
          {
            _mm_lfence();
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v54 - 3) + 8LL))(*((_QWORD *)v54 - 3));
            }
            if ( !v92 )
              goto LABEL_126;
            goto LABEL_125;
          }
        }
        _mm_lfence();
        v56 = (Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent *)*((_QWORD *)v31 + 337);
        if ( v56
          && (started = Microsoft::DiagnosticsHub::StandardCollector::ManagedInformationAgent::GetCurrentResult(
                          v56,
                          v92),
              v90 = started,
              started < 0) )
        {
          _mm_lfence();
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v54 - 3) + 8LL))(*((_QWORD *)v54 - 3));
          }
          if ( !v92 )
            goto LABEL_126;
        }
        else
        {
          _mm_lfence();
          bstrString = 0;
          started = Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::CommitResult(
                      v31,
                      0,
                      v55,
                      &bstrString);
          v90 = started;
          if ( started >= 0 )
          {
            _mm_lfence();
            if ( !*((_BYTE *)v31 + 3938) )
            {
              v57 = (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController **)v70;
              if ( (_QWORD)v70 != *((_QWORD *)&v70 + 1) )
              {
                v58 = (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController **)*((_QWORD *)&v70 + 1);
                do
                {
                  v72 = *v57;
                  if ( !DeleteFileW((LPCWSTR)v72) )
                  {
                    v59 = _logger;
                    LODWORD(v65) = GetLastError();
                    DiagHubCommon::LogStream::Write(
                      (DiagHubCommon::LogStream *)((char *)v59 + 56),
                      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                      L"Failed to delete ETL file: %s. Error code: %d",
                      v72,
                      v65);
                  }
                  ++v57;
                }
                while ( v57 != v58 );
              }
              if ( *((int *)v54 - 4) > 0 && !DeleteFileW(v54) )
              {
                v60 = _logger;
                LODWORD(v65) = GetLastError();
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)v60 + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                  L"Failed to delete merged ETL file: %s. Error code: %d",
                  v54,
                  v65);
              }
            }
            started = -2147467261;
            v61 = v86;
            v62 = bstrString;
            if ( v86 )
            {
              v86->vt = 8;
              if ( v62 )
              {
                v64 = SysStringByteLen(v62);
                v63 = SysAllocStringByteLen((LPCSTR)bstrString, v64);
                v62 = bstrString;
              }
              else
              {
                v63 = 0;
              }
              v61->llVal = (LONGLONG)v63;
              if ( v63 || (started = -2147024882, !v62) )
                started = 0;
            }
            SysFreeString(v62);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v54 - 3) + 8LL))(*((_QWORD *)v54 - 3));
            }
            if ( !v92 )
              goto LABEL_126;
          }
          else
          {
            _mm_lfence();
            SysFreeString(bstrString);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v54 - 2, 0xFFFFFFFF) <= 1 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v54 - 3) + 8LL))(*((_QWORD *)v54 - 3));
            }
            if ( !v92 )
              goto LABEL_126;
          }
        }
LABEL_125:
        (*(void (__fastcall **)(struct DhPackaging::IDhPackage *))(*(_QWORD *)v92 + 16LL))(v92);
        goto LABEL_126;
      }
    }
    _mm_lfence();
    if ( v92 )
      goto LABEL_125;
  }
LABEL_126:
  `eh vector destructor iterator'(
    v94,
    0x80u,
    5u,
    (void (*)(void *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation);
  goto LABEL_127;
}

```

## disassembly

```asm
0x18001b320  mov     [rsp+arg_8], rbx
0x18001b325  mov     [rsp+arg_18], rsi
0x18001b32a  push    rdi
0x18001b32b  push    r12
0x18001b32d  push    r13
0x18001b32f  push    r14
0x18001b331  push    r15
0x18001b333  sub     rsp, 3D0h
0x18001b33a  mov     rax, cs:__security_cookie
0x18001b341  xor     rax, rsp
0x18001b344  mov     [rsp+3F8h+var_38], rax
0x18001b34c  mov     [rsp+3F8h+var_310], r8
0x18001b354  mov     [rsp+3F8h+var_3C8], dl
0x18001b358  mov     r15, rcx
0x18001b35b  mov     [rsp+3F8h+var_398], rcx
0x18001b360  mov     [rsp+3F8h+lpFileName], rcx
0x18001b365  mov     al, [rcx+0DF8h]
0x18001b36b  xor     esi, esi
0x18001b36d  test    al, al
0x18001b36f  jz      short loc_18001B37B
0x18001b371  mov     eax, 0E1110013h
0x18001b376  jmp     loc_18001C17A
0x18001b37b  add     rcx, 0DD0h; lpCriticalSection
0x18001b382  mov     [rsp+3F8h+var_350], rcx
0x18001b38a  call    cs:__imp_EnterCriticalSection
0x18001b390  nop
0x18001b391  test    byte ptr [r15+358h], 4
0x18001b399  jz      short loc_18001B3A6
0x18001b39b  mov     r14d, 8007139Fh
0x18001b3a1  jmp     loc_18001C169
0x18001b3a6  mov     rcx, r15; this
0x18001b3a9  call    ?EmitMachineInfo@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJXZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EmitMachineInfo(void)
0x18001b3ae  mov     r14d, eax
0x18001b3b1  mov     [rsp+3F8h+var_2D8], eax
0x18001b3b8  test    eax, eax
0x18001b3ba  jns     short loc_18001B3C4
0x18001b3bc  lfence
0x18001b3bf  jmp     loc_18001C169
0x18001b3c4  lfence
0x18001b3c7  xorps   xmm1, xmm1
0x18001b3ca  movdqu  [rsp+3F8h+var_3B0], xmm1
0x18001b3d0  mov     [rsp+3F8h+var_3A0], rsi
0x18001b3d5  mov     eax, [r15+35Ch]
0x18001b3dc  mov     [rsp+3F8h+var_390], eax
0x18001b3e0  lea     rax, ??1EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::~EtwSessionInformation(void)
0x18001b3e7  mov     [rsp+3F8h+var_3D8], rax; void (*)(void *)
0x18001b3ec  lea     r9, ??0EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001b3f3  mov     r13d, 5
0x18001b3f9  mov     r8d, r13d; unsigned __int64
0x18001b3fc  lea     r12d, [r13+7Bh]
0x18001b400  mov     edx, r12d; unsigned __int64
0x18001b403  lea     rcx, [rsp+3F8h+var_2B8]; void *
0x18001b40b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001b410  nop
0x18001b411  lea     rdi, [r15+0DA8h]
0x18001b418  mov     [rsp+3F8h+lpCriticalSection], rdi
0x18001b41d  mov     rcx, rdi; lpCriticalSection
0x18001b420  call    cs:__imp_EnterCriticalSection
0x18001b426  nop
0x18001b427  lea     r14, [r15+0B48h]
0x18001b42e  lea     rdi, [rsp+3F8h+var_2A0]
0x18001b436  sub     rdi, r15
0x18001b439  mov     [rsp+3F8h+var_320], rdi
0x18001b441  lea     rax, [rsp+3F8h+var_2B8]
0x18001b449  sub     rax, r15
0x18001b44c  mov     [rsp+3F8h+var_318], rax
0x18001b454  lea     rbx, [rsp+3F8h+var_2A8]
0x18001b45c  sub     rbx, r15
0x18001b45f  mov     [rsp+3F8h+var_328], rbx
0x18001b467  mov     r15d, r13d
0x18001b46a  mov     [rsp+3F8h+var_3C0], r13
0x18001b46f  lea     rdx, [r14-20h]
0x18001b473  lea     rcx, [rax-0B48h]
0x18001b47a  add     rcx, r14
0x18001b47d  call    ??4EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAAEAU01234@$$QEAU01234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &&)
0x18001b482  lea     rcx, [r14-10h]
0x18001b486  lea     rax, [r14-0B48h]
0x18001b48d  add     rax, rbx
0x18001b490  cmp     rcx, rax
0x18001b493  jz      loc_18001B66F
0x18001b499  mov     [rsp+3F8h+var_2E8], rcx
0x18001b4a1  mov     eax, [rax]
0x18001b4a3  mov     [rcx], eax
0x18001b4a5  mov     rax, [rdi+r14-0B48h]
0x18001b4ad  mov     [rsp+3F8h+var_330], rax
0x18001b4b5  mov     rbx, [rax]
0x18001b4b8  lea     rdx, [r14-8]
0x18001b4bc  mov     rdi, [rdx]
0x18001b4bf  mov     rcx, [rdi]
0x18001b4c2  jmp     short loc_18001B4DC
0x18001b4c4  cmp     rbx, rax
0x18001b4c7  jz      loc_18001B5C5
0x18001b4cd  movups  xmm0, xmmword ptr [rbx+10h]
0x18001b4d1  movdqu  xmmword ptr [rcx+10h], xmm0
0x18001b4d6  mov     rcx, [rcx]; Block
0x18001b4d9  mov     rbx, [rbx]
0x18001b4dc  cmp     rcx, rdi
0x18001b4df  jnz     short loc_18001B4C4
0x18001b4e1  mov     [rsp+3F8h+var_370], rdx
0x18001b4e9  mov     r13, rsi
0x18001b4ec  mov     [rsp+3F8h+var_368], rsi
0x18001b4f4  xorps   xmm0, xmm0
0x18001b4f7  movdqu  [rsp+3F8h+var_360], xmm0
0x18001b500  cmp     rbx, rax
0x18001b503  jz      loc_18001B5F5
0x18001b509  mov     [rsp+3F8h+var_380], rdx
0x18001b50e  mov     [rsp+3F8h+var_378], rsi
0x18001b516  mov     ecx, 20h ; ' '; Size
0x18001b51b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b520  mov     rdi, rax
0x18001b523  movups  xmm0, xmmword ptr [rbx+10h]
0x18001b527  movdqu  xmmword ptr [rax+10h], xmm0
0x18001b52c  mov     [rsp+3F8h+var_378], rsi
0x18001b534  mov     qword ptr [rsp+3F8h+var_360+8], rax
0x18001b53c  mov     rcx, rax
0x18001b53f  mov     qword ptr [rsp+3F8h+var_360], rax
0x18001b547  mov     r13d, 1
0x18001b54d  mov     [rsp+3F8h+var_368], r13
0x18001b555  mov     rbx, [rbx]
0x18001b558  mov     r15, [rsp+3F8h+var_330]
0x18001b560  cmp     rbx, r15
0x18001b563  jz      short loc_18001B5BA
0x18001b565  mov     r12, rax
0x18001b568  mov     [rsp+3F8h+var_378], rsi
0x18001b570  mov     ecx, 20h ; ' '; Size
0x18001b575  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b57a  movups  xmm0, xmmword ptr [rbx+10h]
0x18001b57e  movdqu  xmmword ptr [rax+10h], xmm0
0x18001b583  mov     [r12], rax
0x18001b587  mov     [rax+8], r12
0x18001b58b  mov     [rsp+3F8h+var_378], rsi
0x18001b593  mov     r12, rax
0x18001b596  mov     qword ptr [rsp+3F8h+var_360], rax
0x18001b59e  inc     r13
0x18001b5a1  mov     [rsp+3F8h+var_368], r13
0x18001b5a9  mov     rbx, [rbx]
0x18001b5ac  cmp     rbx, r15
0x18001b5af  jnz     short loc_18001B568
0x18001b5b1  mov     r12d, 80h
0x18001b5b7  mov     rcx, rax
0x18001b5ba  lea     rdx, [r14-8]
0x18001b5be  mov     r15, [rsp+3F8h+var_3C0]
0x18001b5c3  jmp     short loc_18001B605
0x18001b5c5  cmp     rcx, rdi
0x18001b5c8  jz      short loc_18001B646
0x18001b5ca  mov     rax, [rcx+8]
0x18001b5ce  mov     [rax], rdi
0x18001b5d1  mov     [rdi+8], rax
0x18001b5d5  mov     r13, rsi
0x18001b5d8  mov     rbx, [rcx]
0x18001b5db  mov     edx, 20h ; ' '
0x18001b5e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b5e5  mov     rcx, rbx
0x18001b5e8  inc     r13
0x18001b5eb  cmp     rbx, rdi
0x18001b5ee  jnz     short loc_18001B5D8
0x18001b5f0  sub     [r14], r13
0x18001b5f3  jmp     short loc_18001B646
0x18001b5f5  mov     rdi, qword ptr [rsp+3F8h+var_360+8]
0x18001b5fd  mov     rcx, qword ptr [rsp+3F8h+var_360]
0x18001b605  mov     rdx, [rdx]
0x18001b608  test    r13, r13
0x18001b60b  jz      short loc_18001B625
0x18001b60d  mov     rax, [rdx+8]
0x18001b611  mov     [rdi+8], rax
0x18001b615  mov     [rax], rdi
0x18001b618  mov     [rcx], rdx
0x18001b61b  mov     [rdx+8], rcx
0x18001b61f  add     [r14], r13
0x18001b622  mov     r13, rsi
0x18001b625  test    r13, r13
0x18001b628  jz      short loc_18001B646
0x18001b62a  mov     [rdi+8], rsi
0x18001b62e  mov     [rcx], rsi
0x18001b631  mov     rcx, rdi; Block
0x18001b634  mov     rdi, [rdi]
0x18001b637  mov     edx, 20h ; ' '
0x18001b63c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b641  test    rdi, rdi
0x18001b644  jnz     short loc_18001B631
0x18001b646  lea     rcx, [r14-10h]
0x18001b64a  mov     rdx, [r14]
0x18001b64d  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18001b652  mov     rdx, rax
0x18001b655  lea     rcx, [r14-10h]
0x18001b659  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Forced_rehash(unsigned __int64)
0x18001b65e  nop
0x18001b65f  mov     rbx, [rsp+3F8h+var_328]
0x18001b667  mov     rdi, [rsp+3F8h+var_320]
0x18001b66f  add     r14, r12
0x18001b672  sub     r15, 1
0x18001b676  mov     [rsp+3F8h+var_3C0], r15
0x18001b67b  mov     rax, [rsp+3F8h+var_318]
0x18001b683  jnz     loc_18001B46F
0x18001b689  lea     rax, [rsp+3F8h+var_2D8]
0x18001b691  mov     [rsp+3F8h+var_370], rax
0x18001b699  lea     rax, [rsp+3F8h+var_2B8]
0x18001b6a1  mov     [rsp+3F8h+var_368], rax
0x18001b6a9  mov     r15, [rsp+3F8h+var_398]
0x18001b6ae  mov     qword ptr [rsp+3F8h+var_360], r15
0x18001b6b6  lock inc dword ptr [r15+35Ch]
0x18001b6be  cmp     [rsp+3F8h+var_3C8], sil
0x18001b6c3  mov     rdi, [rsp+3F8h+lpCriticalSection]
0x18001b6c8  mov     r13d, 5
0x18001b6ce  jnz     loc_18001BBB1
0x18001b6d4  mov     [rsp+3F8h+var_3C8], sil
0x18001b6d9  lea     rax, [rsp+3F8h+var_2D8]
0x18001b6e1  mov     [rsp+3F8h+var_348], rax
0x18001b6e9  lea     rax, [rsp+3F8h+var_2B8]
0x18001b6f1  mov     [rsp+3F8h+var_340], rax
0x18001b6f9  mov     [rsp+3F8h+var_338], r15
0x18001b701  cmp     [r15+0DFAh], sil
0x18001b708  jz      loc_18001B858
0x18001b70e  lea     r8, [rsp+3F8h+var_3C0]; unsigned __int16 **
0x18001b713  lea     rdx, [rsp+3F8h+var_2B8]; struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation *
0x18001b71b  mov     rcx, r15; this
0x18001b71e  call    ?StopSuppliedEtwSession@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAUEtwSessionInformation@1234@PEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StopSuppliedEtwSession(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &,ushort const * *)
0x18001b723  mov     r14d, eax
0x18001b726  mov     [rsp+3F8h+var_2D8], eax
0x18001b72d  test    eax, eax
0x18001b72f  jns     short loc_18001B7A6
0x18001b731  lfence
0x18001b734  lea     rcx, [rsp+3F8h+var_348]
0x18001b73c  call    DiagHubCommon__ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e______ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___
0x18001b741  nop
0x18001b742  cmp     [rsp+3F8h+var_2D8], esi
0x18001b749  jge     short loc_18001B77C
0x18001b74b  lea     rbx, [rsp+3F8h+var_2B8]
0x18001b753  lea     rax, [rsp+3F8h+var_2B8]
0x18001b75b  sub     r15, rax
0x18001b75e  mov     esi, r13d
0x18001b761  lea     rcx, [r15+0B28h]
0x18001b768  add     rcx, rbx
0x18001b76b  mov     rdx, rbx
0x18001b76e  call    ??4EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAAEAU01234@$$QEAU01234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &&)
0x18001b773  add     rbx, r12
0x18001b776  sub     rsi, 1
0x18001b77a  jnz     short loc_18001B761
0x18001b77c  mov     rcx, rdi; lpCriticalSection
0x18001b77f  call    cs:__imp_LeaveCriticalSection
0x18001b785  nop
0x18001b786  lea     r9, ??1EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001b78d  mov     r8, r13; unsigned __int64
0x18001b790  mov     rdx, r12; unsigned __int64
0x18001b793  lea     rcx, [rsp+3F8h+var_2B8]; void *
0x18001b79b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001b7a0  nop
0x18001b7a1  jmp     loc_18001C15E
0x18001b7a6  cmp     [rsp+3F8h+var_3C0], rsi
0x18001b7ab  jz      loc_18001B858
0x18001b7b1  lea     rdx, [rsp+3F8h+var_3C0]
0x18001b7b6  lea     rcx, [rsp+3F8h+var_3B0]
0x18001b7bb  call    ?push_back@?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAXAEBQEBG@Z; std::vector<ushort const *>::push_back(ushort const * const &)
0x18001b7c0  jmp     loc_18001B858
0x18001b7c5  lea     rcx, [rsp+3F8h+var_348]
0x18001b7cd  call    DiagHubCommon__ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e______ScopeGuard__lambda_2c0640d58f277805430ee90fdadbc73e___
0x18001b7d2  nop
0x18001b7d3  xor     esi, esi
0x18001b7d5  lea     r13d, [rsi+5]
0x18001b7d9  lea     r12d, [r13+7Bh]
0x18001b7dd  cmp     [rsp+3F8h+var_2D8], esi
0x18001b7e4  jge     short loc_18001B81C
0x18001b7e6  lea     rbx, [rsp+3F8h+var_2B8]
0x18001b7ee  lea     rax, [rsp+3F8h+var_2B8]
0x18001b7f6  mov     rdi, [rsp+3F8h+lpFileName]
0x18001b7fb  sub     rdi, rax
0x18001b7fe  mov     esi, r13d
0x18001b801  lea     rcx, [rdi+0B28h]
0x18001b808  add     rcx, rbx
0x18001b80b  mov     rdx, rbx
0x18001b80e  call    ??4EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAAEAU01234@$$QEAU01234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation::operator=(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &&)
0x18001b813  add     rbx, r12
0x18001b816  sub     rsi, 1
0x18001b81a  jnz     short loc_18001B801
0x18001b81c  mov     rcx, [rsp+3F8h+lpCriticalSection]; lpCriticalSection
0x18001b821  call    cs:__imp_LeaveCriticalSection
0x18001b827  nop
0x18001b828  lea     r9, ??1EtwSessionInformation@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ; void (*)(void *)
0x18001b82f  mov     r8, r13; unsigned __int64
0x18001b832  mov     rdx, r12; unsigned __int64
0x18001b835  lea     rcx, [rsp+3F8h+var_2B8]; void *
0x18001b83d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001b842  nop
0x18001b843  lea     rcx, [rsp+3F8h+var_3B0]
0x18001b848  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x18001b84d  mov     r14d, 8007000Eh
0x18001b853  jmp     loc_18001C169
0x18001b858  mov     [rsp+3F8h+var_2D4], sil
0x18001b860  lea     rax, [rsp+3F8h+var_2D8]
0x18001b868  mov     [rsp+3F8h+var_308], rax
0x18001b870  lea     rax, [rsp+3F8h+var_2D4]
0x18001b878  mov     [rsp+3F8h+var_300], rax
0x18001b880  lea     rax, [rsp+3F8h+var_2B8]
0x18001b888  mov     [rsp+3F8h+var_2F8], rax
0x18001b890  mov     [rsp+3F8h+var_2F0], r15
0x18001b898  cmp     [r15+0F60h], sil
0x18001b89f  jz      loc_18001BA23
0x18001b8a5  mov     rax, [rsp+3F8h+var_238]
0x18001b8ad  test    rax, rax
0x18001b8b0  jz      loc_18001BA23
  ... truncated ...
```
