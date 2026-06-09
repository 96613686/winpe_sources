# UpdateManager::WorkerThread(void)

- ea: `0x14007d4b4`
- end: `0x14007e725`
- name: `?WorkerThread@UpdateManager@@AEAA_NXZ`
- size: `4721`
- prototype: `bool __fastcall(UpdateManager *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14007ed9c`

## callees

- `0x140024de0`
- `0x14002cd1c`
- `0x140040184`
- `0x140043504`
- `0x14004519c`
- `0x140045404`
- `0x140057a20`
- `0x14007a970`
- `0x14007ab1c`
- `0x14007d4b4`
- `0x14007e798`
- `0x1400838fc`
- `0x14008b224`
- `0x1400a516c`
- `0x1400a5244`
- `0x1400a52e4`
- `0x1400a5368`
- `0x1400a985c`
- `0x1400a9974`
- `0x1400a9b68`
- `0x1400b7618`
- `0x1400b7654`
- `0x1400c6774`
- `0x1400e3390`
- `0x1400e410c`
- `0x1400e43f8`
- `0x1400eae80`
- `0x14012d7d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007d594`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007d594`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007d645`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007de20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007d645`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007de20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007d634`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007de0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007d634`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007de0f`

## string_xrefs

- `0x14007e69c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007e6e1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007e6fa`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007e713`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007d555`: `WorkerThread:  Lock acquired`
- `0x14007d4f9`: `WorkerThread:  Acquiring lock on m_workThreadMutex to call SetWorking`
- `0x14007d6ab`: `WorkerThread:  Found update {}:{} that need to be installed after reboot`
- `0x14007de85`: `WorkerThread:  Found update {}:{} that need to be installed after reboot`
- `0x14007e4da`: `WorkerThread:  Found update {}:{} that need to be installed after reboot`
- `0x14007dc9a`: `WorkerThread:  Found update {}:{} that needs to be installed after reboot, requesting asap service start`
- `0x14007e47a`: `WorkerThread:  No updates found that need to be installed after reboot`
- `0x14007e564`: `WorkerThread:  Requesting ASAP service start`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
char __fastcall UpdateManager::WorkerThread(UpdateManager *this)
{
  int v2; // edi
  mutex_extensions::shared_recursive_mutex *v4; // r13
  char IsEnabled; // al
  __int64 v6; // rcx
  bool v7; // r14
  char v8; // bl
  __int64 v9; // r14
  wchar_t *v10; // rax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // r15
  __int64 ***v16; // r12
  __int64 v17; // rdx
  signed __int32 v18; // eax
  signed __int32 v19; // ett
  __int64 v20; // rax
  volatile signed __int32 *v21; // rbx
  int v22; // edi
  __int64 v23; // rax
  wchar_t *v24; // rax
  const char *v25; // r9
  __int64 v26; // r11
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // edi
  void (*v31)(void); // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  volatile signed __int32 *v34; // r14
  volatile signed __int32 *v35; // r14
  volatile signed __int32 *v36; // r14
  volatile signed __int32 *v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  volatile signed __int32 *v41; // rbx
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  __int64 ***v46; // rdi
  __int64 **j; // rbx
  char v48; // al
  volatile signed __int32 *v49; // rsi
  __int64 v50; // rdi
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rcx
  _QWORD *v56; // rax
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  volatile signed __int32 *v59; // rbx
  bool v60; // r14
  char v61; // bl
  __int64 v62; // r14
  wchar_t *traits_2_unsigned_short; // rax
  __int64 v64; // r8
  const char *v65; // r9
  __int64 v66; // r11
  __int64 v67; // rax
  __int64 v68; // r15
  __int64 ***v69; // r12
  __int64 v70; // rdx
  signed __int32 v71; // eax
  signed __int32 v72; // ett
  __int64 v73; // rax
  volatile signed __int32 *v74; // rbx
  int v75; // edi
  __int64 v76; // rax
  wchar_t *v77; // rax
  const char *v78; // r9
  __int64 v79; // r11
  __int64 v80; // rax
  __int64 System; // rax
  __int64 v82; // rcx
  int v83; // edi
  void (*v84)(void); // rax
  __int64 v85; // rax
  __int64 v86; // rcx
  volatile signed __int32 *v87; // r14
  volatile signed __int32 *v88; // r14
  volatile signed __int32 *v89; // r14
  volatile signed __int32 *v90; // rdi
  __int64 v91; // rax
  __int64 v92; // rcx
  _QWORD *v93; // rax
  volatile signed __int32 *v94; // rbx
  __int64 v95; // rax
  __int64 v96; // rcx
  _QWORD *v97; // rax
  volatile signed __int32 *v98; // rbx
  volatile signed __int32 *v99; // rbx
  __int64 ***v100; // rdi
  __int64 **i; // rbx
  char v102; // al
  int v103; // esi
  volatile signed __int32 *v104; // rsi
  __int64 v106; // rdi
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // rdx
  volatile signed __int32 *v110; // rbx
  __int64 v111; // rax
  __int64 v112; // rcx
  _QWORD *v113; // rax
  volatile signed __int32 *v114; // rbx
  _BYTE v115[4]; // [rsp+38h] [rbp-D0h] BYREF
  int v116; // [rsp+3Ch] [rbp-CCh]
  __int128 v117; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v118; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v119; // [rsp+68h] [rbp-A0h] BYREF
  volatile signed __int32 *v120; // [rsp+70h] [rbp-98h]
  const wchar_t *v121; // [rsp+88h] [rbp-80h] BYREF
  __int64 v122; // [rsp+90h] [rbp-78h]
  _BYTE v123[8]; // [rsp+98h] [rbp-70h] BYREF
  volatile signed __int32 *v124; // [rsp+A0h] [rbp-68h]
  __int64 v125; // [rsp+A8h] [rbp-60h] BYREF
  char *v126; // [rsp+B0h] [rbp-58h]
  __int64 v127; // [rsp+B8h] [rbp-50h]
  __int64 v128; // [rsp+C0h] [rbp-48h]
  __int128 v129; // [rsp+C8h] [rbp-40h]
  __int64 v130; // [rsp+D8h] [rbp-30h]
  char v131; // [rsp+F8h] [rbp-10h]
  __int128 v132; // [rsp+100h] [rbp-8h]
  __int64 v133; // [rsp+110h] [rbp+8h]
  __int64 v134; // [rsp+118h] [rbp+10h]
  char v135; // [rsp+148h] [rbp+40h]
  char v136; // [rsp+180h] [rbp+78h]
  _BYTE v137[64]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v138[64]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v139[64]; // [rsp+208h] [rbp+100h] BYREF
  __int64 v140; // [rsp+248h] [rbp+140h] BYREF
  volatile signed __int32 *v141; // [rsp+250h] [rbp+148h]
  __int64 v142; // [rsp+258h] [rbp+150h]
  char v143; // [rsp+260h] [rbp+158h]
  __int64 v144; // [rsp+268h] [rbp+160h] BYREF
  volatile signed __int32 *v145; // [rsp+270h] [rbp+168h]
  __int64 v146; // [rsp+278h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v2 = 0;
  v116 = 0;
  *(_QWORD *)&v118 = L"WorkerThread:  Acquiring lock on m_workThreadMutex to call SetWorking";
  *((_QWORD *)&v118 + 1) = 69;
  SystemInterface::LogVerbose<>(&v118);
  v118 = (unsigned __int64)this + 1008;
  if ( (unsigned int)mtx_do_lock((char *)this + 1008, 0) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 271) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 271) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v118) = 1;
  v121 = L"WorkerThread:  Lock acquired";
  v122 = 28;
  SystemInterface::LogVerbose<>(&v121);
  UpdateManager::SetWorking(this);
  if ( (*((_DWORD *)this + 271))-- == 1 )
  {
    *((_DWORD *)this + 270) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 128);
  }
  UpdateManager::Work(this);
  v122 = 1;
  v4 = (UpdateManager *)((char *)this + 144);
  v121 = (const wchar_t *)((char *)this + 144);
  mutex_extensions::shared_recursive_mutex::lock_shared((char *)this + 144);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::GetImpl'::`2'::impl);
  v6 = *((_QWORD *)this + 42);
  if ( !IsEnabled )
  {
    if ( v6 )
      goto LABEL_102;
    v143 = 0;
    v2 = 32;
    v116 = 32;
    if ( (unsigned __int8)ScanManager::ScanInProgress(*((_QWORD *)this + 97), &v140)
      || BrokerManager::Running(*((BrokerManager **)this + 98)) )
    {
      goto LABEL_102;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
    {
      AcquireSRWLockShared((PSRWLOCK)this + 72);
      v60 = *((_QWORD *)this + 74) == 0;
      ReleaseSRWLockShared((PSRWLOCK)this + 72);
    }
    else
    {
      v60 = *((_QWORD *)this + 44) == 0;
    }
    if ( !v60 )
LABEL_102:
      v61 = 0;
    else
      v61 = 1;
    if ( (v2 & 0x20) != 0 )
    {
      v2 &= ~0x20u;
      if ( v143 )
        std::vector<std::filesystem::path>::_Tidy(&v140);
    }
    if ( !v61 )
      goto LABEL_191;
    if ( ScanManager::IsAutoRescanEnabled(*((ScanManager **)this + 97)) )
    {
      v62 = *((_QWORD *)this + 97);
      traits_2_unsigned_short = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                             L"No Work",
                                             L"WorkerThread:  Found update {}:{} that need to be installed after reboot",
                                             0);
      if ( traits_2_unsigned_short == L"WorkerThread:  Found update {}:{} that need to be installed after reboot"
        || (v67 = ((__int64)traits_2_unsigned_short - v66) >> 1, v67 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v65);
      }
      *(_QWORD *)&v117 = v66;
      *((_QWORD *)&v117 + 1) = v67;
      LOBYTE(v65) = 1;
      ScanManager::SetAutoRescanAllowed(v62, &v117, v64, v65);
    }
    v68 = *((_QWORD *)this + 4);
    v115[0] = 0;
    v125 = 0;
    v69 = (__int64 ***)((char *)this + 704);
    v126 = (char *)this + 704;
    v127 = *((_QWORD *)this + 2);
    v128 = 0;
    v117 = 0;
    v70 = *((_QWORD *)this + 1);
    if ( !v70 )
LABEL_194:
      std::_Throw_bad_weak_ptr();
    v71 = *(_DWORD *)(v70 + 8);
    do
    {
      if ( !v71 )
        goto LABEL_194;
      v72 = v71;
      v71 = _InterlockedCompareExchange((volatile signed __int32 *)(v70 + 8), v71 + 1, v71);
    }
    while ( v72 != v71 );
    v73 = *(_QWORD *)this;
    *(_QWORD *)&v117 = *(_QWORD *)this;
    v74 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_QWORD *)&v117 + 1) = v74;
    v75 = v2 | 0x800;
    v116 = v75;
    v129 = 0;
    if ( v74 )
    {
      *(_QWORD *)&v129 = v73;
      *((_QWORD *)&v129 + 1) = v74;
      _InterlockedIncrement(v74 + 3);
    }
    v130 = 0;
    v131 = 0;
    v132 = 0;
    v133 = 0;
    v76 = std::_Allocate<16,std::_Default_allocate_traits>(64);
    *(_QWORD *)v76 = v76;
    *(_QWORD *)(v76 + 8) = v76;
    *(_QWORD *)(v76 + 16) = v76;
    *(_WORD *)(v76 + 24) = 257;
    *((_QWORD *)&v132 + 1) = v76;
    v134 = 0;
    v135 = 0;
    v136 = 0;
    std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v137);
    std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v138);
    std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v139);
    v77 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"System Enable Prehibernate Wake",
                       L"No Work",
                       0);
    if ( v77 == L"No Work" || (v80 = ((__int64)v77 - v79) >> 1, v80 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v78);
    *(_QWORD *)&v118 = v79;
    *((_QWORD *)&v118 + 1) = v80;
    if ( (unsigned __int8)DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<bool>(
                            v68,
                            &v118,
                            &v125,
                            v115) )
    {
      System = SystemInterface::Providers::GetSystem(v123);
      v116 = v75 | 0x40;
      v82 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
      v83 = v75 | 0xC0;
      v84 = *(void (**)(void))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v82 + 24LL))(
                                              v82,
                                              &v144)
                             + 16LL);
    }
    else
    {
      v85 = SystemInterface::Providers::GetSystem(&v119);
      v116 = v75 | 0x100;
      v86 = *(_QWORD *)v85 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v85 + 8LL) + 4LL);
      v83 = v75 | 0x300;
      v84 = *(void (**)(void))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 24LL))(
                                              v86,
                                              &v140)
                             + 24LL);
    }
    v116 = v83;
    v84();
    if ( (v83 & 0x200) != 0 )
    {
      LOWORD(v83) = v83 & 0xFDFF;
      v87 = v141;
      if ( v141 )
      {
        if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
          if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
        }
      }
    }
    if ( (v83 & 0x100) != 0 )
    {
      v88 = v120;
      if ( v120 )
      {
        if ( _InterlockedExchangeAdd(v120 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
    }
    if ( (v83 & 0x80u) != 0 )
    {
      LOBYTE(v83) = v83 & 0x7F;
      v89 = v145;
      if ( v145 )
      {
        if ( _InterlockedExchangeAdd(v145 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
          if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
        }
      }
    }
    if ( (v83 & 0x40) != 0 )
    {
      v90 = v124;
      if ( v124 )
      {
        if ( _InterlockedExchangeAdd(v124 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
          if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
        }
      }
    }
    SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)&v125);
    if ( v74 )
    {
      if ( _InterlockedExchangeAdd(v74 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
      }
    }
    if ( *((_QWORD *)this + 89) )
    {
      if ( !ScanManager::IsAutoRescanEnabled(*((ScanManager **)this + 97)) )
      {
LABEL_162:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
          goto LABEL_176;
        v100 = (__int64 ***)*v69;
        for ( i = (__int64 **)**v69; ; i = (__int64 **)*i )
        {
          if ( i == (__int64 **)v100 )
          {
            *(_QWORD *)&v117 = L"WorkerThread:  No updates found that need to be installed after reboot";
            *((_QWORD *)&v117 + 1) = 70;
            SystemInterface::Log<>(&v117);
            goto LABEL_176;
          }
          (*(void (__fastcall **)(__int64 *, __int64 *))(*i[2] + 296))(i[2], &v140);
          v102 = v142;
          if ( (_BYTE)v142 )
          {
            v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v140 + 24LL))(v140);
            if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*i[2] + 712))(i[2]) && v103 != 3 )
            {
              v106 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*i[2] + 24))(i[2], &v144);
              v107 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*i[2] + 8))(i[2], &v119);
              *(_QWORD *)&v117 = L"WorkerThread:  Found update {}:{} that need to be installed after reboot";
              *((_QWORD *)&v117 + 1) = 72;
              SystemInterface::Log<std::wstring,std::wstring>(&v117, v107, v106);
              std::wstring::~wstring(&v119, v108);
              std::wstring::~wstring(&v144, v109);
              if ( (_BYTE)v142 )
              {
                v110 = v141;
                if ( v141 )
                {
                  if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v110)(v110);
                    if ( _InterlockedExchangeAdd(v110 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v110 + 8LL))(v110);
                  }
                }
              }
              *(_QWORD *)&v117 = L"WorkerThread:  Requesting ASAP service start";
              *((_QWORD *)&v117 + 1) = 44;
              SystemInterface::Log<>(&v117);
              v111 = SystemInterface::Providers::GetSystem(&v119);
              v112 = *(_QWORD *)v111 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v111 + 8LL) + 4LL);
              v113 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v112 + 80LL))(v112, &v140);
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v113 + 32LL))(*v113);
              v114 = v141;
              if ( v141 )
              {
                if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v114)(v114);
                  if ( _InterlockedExchangeAdd(v114 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v114 + 8LL))(v114);
                }
              }
              v59 = v120;
LABEL_187:
              if ( v59 )
              {
                if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
                  if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
                }
              }
              goto LABEL_176;
            }
            v102 = v142;
          }
          if ( v102 )
          {
            v104 = v141;
            if ( v141 )
            {
              if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
                if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
              }
            }
          }
        }
      }
      v95 = SystemInterface::Providers::GetSystem(&v119);
      v96 = *(_QWORD *)v95 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v95 + 8LL) + 4LL);
      v97 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v96 + 80LL))(v96, &v140);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v97 + 16LL))(*v97);
      v98 = v141;
      if ( v141 )
      {
        if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
          if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
        }
      }
    }
    else
    {
      v91 = SystemInterface::Providers::GetSystem(&v119);
      v92 = *(_QWORD *)v91 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v91 + 8LL) + 4LL);
      v93 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v92 + 80LL))(v92, &v140);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v93 + 24LL))(*v93);
      v94 = v141;
      if ( v141 )
      {
        if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
          if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
        }
      }
    }
    v99 = v120;
    if ( v120 )
    {
      if ( _InterlockedExchangeAdd(v120 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
        if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
      }
    }
    goto LABEL_162;
  }
  if ( v6 )
    goto LABEL_14;
  v143 = 0;
  v2 = 1;
  v116 = 1;
  if ( (unsigned __int8)ScanManager::ScanInProgress(*((_QWORD *)this + 97), &v140)
    || BrokerManager::Running(*((BrokerManager **)this + 98)) )
  {
    goto LABEL_14;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockShared((PSRWLOCK)this + 72);
    v7 = *((_QWORD *)this + 74) == 0;
    ReleaseSRWLockShared((PSRWLOCK)this + 72);
  }
  else
  {
    v7 = *((_QWORD *)this + 59) == 0;
  }
  if ( !v7 )
LABEL_14:
    v8 = 0;
  else
    v8 = 1;
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    if ( v143 )
      std::vector<std::filesystem::path>::_Tidy(&v140);
  }
  if ( !v8 )
  {
LABEL_191:
    mutex_extensions::shared_recursive_mutex::unlock_shared((UpdateManager *)((char *)this + 144));
    return 1;
  }
  if ( ScanManager::IsAutoRescanEnabled(*((ScanManager **)this + 97)) )
  {
    v9 = *((_QWORD *)this + 97);
    v10 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"No Work",
                       L"WorkerThread:  Found update {}:{} that need to be installed after reboot",
                       0);
    if ( v10 == L"WorkerThread:  Found update {}:{} that need to be installed after reboot"
      || (v14 = ((__int64)v10 - v13) >> 1, v14 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v12);
    }
    *(_QWORD *)&v118 = v13;
    *((_QWORD *)&v118 + 1) = v14;
    LOBYTE(v12) = 1;
    ScanManager::SetAutoRescanAllowed(v9, &v118, v11, v12);
  }
  v15 = *((_QWORD *)this + 4);
  v115[0] = 0;
  v125 = 0;
  v16 = (__int64 ***)((char *)this + 704);
  v126 = (char *)this + 704;
  v127 = *((_QWORD *)this + 2);
  v128 = 0;
  v118 = 0;
  v17 = *((_QWORD *)this + 1);
  if ( !v17 )
LABEL_193:
    std::_Throw_bad_weak_ptr();
  v18 = *(_DWORD *)(v17 + 8);
  do
  {
    if ( !v18 )
      goto LABEL_193;
    v19 = v18;
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)(v17 + 8), v18 + 1, v18);
  }
  while ( v19 != v18 );
  v20 = *(_QWORD *)this;
  *(_QWORD *)&v118 = *(_QWORD *)this;
  v21 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  *((_QWORD *)&v118 + 1) = v21;
  v22 = v2 | 0x400;
  v116 = v22;
  v129 = 0;
  if ( v21 )
  {
    *(_QWORD *)&v129 = v20;
    *((_QWORD *)&v129 + 1) = v21;
    _InterlockedIncrement(v21 + 3);
  }
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v23 = std::_Allocate<16,std::_Default_allocate_traits>(64);
  *(_QWORD *)v23 = v23;
  *(_QWORD *)(v23 + 8) = v23;
  *(_QWORD *)(v23 + 16) = v23;
  *(_WORD *)(v23 + 24) = 257;
  *((_QWORD *)&v132 + 1) = v23;
  v134 = 0;
  v135 = 0;
  v136 = 0;
  std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v137);
  std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(v138);
  std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(v139);
  v24 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"System Enable Prehibernate Wake",
                     L"No Work",
                     0);
  if ( v24 == L"No Work" || (v27 = ((__int64)v24 - v26) >> 1, v27 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v25);
  *(_QWORD *)&v117 = v26;
  *((_QWORD *)&v117 + 1) = v27;
  if ( (unsigned __int8)DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<bool>(
                          v15,
                          &v117,
                          &v125,
                          v115) )
  {
    v28 = SystemInterface::Providers::GetSystem(&v140);
    v116 = v22 | 2;
    v29 = *(_QWORD *)v28 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v28 + 8LL) + 4LL);
    v30 = v22 | 6;
    v31 = *(void (**)(void))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 24LL))(
                                            v29,
                                            &v119)
                           + 16LL);
  }
  else
  {
    v32 = SystemInterface::Providers::GetSystem(&v144);
    v116 = v22 | 8;
    v33 = *(_QWORD *)v32 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v32 + 8LL) + 4LL);
    v30 = v22 | 0x18;
    v31 = *(void (**)(void))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 24LL))(
                                            v33,
                                            v123)
                           + 24LL);
  }
  v116 = v30;
  v31();
  if ( (v30 & 0x10) != 0 )
  {
    LOBYTE(v30) = v30 & 0xEF;
    v34 = v124;
    if ( v124 )
    {
      if ( _InterlockedExchangeAdd(v124 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
  }
  if ( (v30 & 8) != 0 )
  {
    LOBYTE(v30) = v30 & 0xF7;
    v35 = v145;
    if ( v145 )
    {
      if ( _InterlockedExchangeAdd(v145 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
        if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
      }
    }
  }
  if ( (v30 & 4) != 0 )
  {
    LOBYTE(v30) = v30 & 0xFB;
    v36 = v120;
    if ( v120 )
    {
      if ( _InterlockedExchangeAdd(v120 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
  }
  if ( (v30 & 2) != 0 )
  {
    v37 = v141;
    if ( v141 )
    {
      if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
  }
  SystemInterface::Providers::ConditionContext::~ConditionContext((SystemInterface::Providers::ConditionContext *)&v125);
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  if ( *((_QWORD *)this + 89) )
  {
    if ( ScanManager::IsAutoRescanEnabled(*((ScanManager **)this + 97)) )
    {
      v43 = SystemInterface::Providers::GetSystem(&v119);
      v44 = *(_QWORD *)v43 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v43 + 8LL) + 4LL);
      v45 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, &v140);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v45 + 16LL))(*v45);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v140);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v119);
    }
  }
  else
  {
    v38 = SystemInterface::Providers::GetSystem(&v119);
    v39 = *(_QWORD *)v38 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v38 + 8LL) + 4LL);
    v40 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 80LL))(v39, &v140);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 24LL))(*v40);
    v41 = v141;
    if ( v141 )
    {
      if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    v42 = v120;
    if ( v120 )
    {
      if ( _InterlockedExchangeAdd(v120 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
  {
    v46 = (__int64 ***)*v16;
    for ( j = (__int64 **)**v16; j != (__int64 **)v46; j = (__int64 **)*j )
    {
      (*(void (__fastcall **)(__int64 *, __int64 *))(*j[2] + 296))(j[2], &v144);
      v48 = v146;
      if ( (_BYTE)v146 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*j[2] + 712))(j[2])
          && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v144 + 24LL))(v144) != 3 )
        {
          v50 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*j[2] + 24))(j[2], &v119);
          v51 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*j[2] + 8))(j[2], &v140);
          *(_QWORD *)&v117 = L"WorkerThread:  Found update {}:{} that needs to be installed after reboot, requesting asap service start";
          *((_QWORD *)&v117 + 1) = 104;
          SystemInterface::Log<std::wstring,std::wstring>(&v117, v51, v50);
          std::wstring::~wstring(&v140, v52);
          std::wstring::~wstring(&v119, v53);
          v54 = SystemInterface::Providers::GetSystem(&v119);
          v55 = *(_QWORD *)v54 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v54 + 8LL) + 4LL);
          v56 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 80LL))(v55, &v140);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 32LL))(*v56);
          v57 = v141;
          if ( v141 )
          {
            if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
              if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
            }
          }
          v58 = v120;
          if ( v120 )
          {
            if ( _InterlockedExchangeAdd(v120 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
              if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
            }
          }
          if ( (_BYTE)v146 )
          {
            v59 = v145;
            goto LABEL_187;
          }
          break;
        }
        v48 = v146;
      }
      if ( v48 )
      {
        v49 = v145;
        if ( v145 )
        {
          if ( _InterlockedExchangeAdd(v145 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
          }
        }
      }
    }
  }
LABEL_176:
  mutex_extensions::shared_recursive_mutex::unlock_shared(v4);
  return 0;
}

```

## disassembly

```asm
0x14007d4b4  mov     rax, rsp
0x14007d4b7  mov     [rax+10h], rbx
0x14007d4bb  mov     [rax+18h], rsi
0x14007d4bf  mov     [rax+20h], rdi
0x14007d4c3  push    rbp
0x14007d4c4  push    r12
0x14007d4c6  push    r13
0x14007d4c8  push    r14
0x14007d4ca  push    r15
0x14007d4cc  lea     rbp, [rax-1B8h]
0x14007d4d3  sub     rsp, 290h
0x14007d4da  mov     rax, cs:__security_cookie
0x14007d4e1  xor     rax, rsp
0x14007d4e4  mov     [rbp+1B0h+var_30], rax
0x14007d4eb  mov     rsi, rcx
0x14007d4ee  xor     r14d, r14d
0x14007d4f1  mov     edi, r14d
0x14007d4f4  mov     [rsp+2B0h+var_27C], r14d
0x14007d4f9  lea     rax, aWorkerthreadAc; "WorkerThread:  Acquiring lock on m_work"...
0x14007d500  mov     qword ptr [rsp+2B0h+var_268+8], rax
0x14007d505  mov     qword ptr [rsp+2B0h+var_258], 45h ; 'E'
0x14007d50e  lea     rcx, [rsp+2B0h+var_268+8]
0x14007d513  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007d518  xorps   xmm0, xmm0
0x14007d51b  movups  [rsp+2B0h+var_268+8], xmm0
0x14007d520  lea     rcx, [rsi+3F0h]
0x14007d527  mov     qword ptr [rsp+2B0h+var_268+8], rcx
0x14007d52c  mov     [rsp+2B0h+var_258], r14b
0x14007d531  xor     edx, edx
0x14007d533  call    mtx_do_lock
0x14007d538  test    eax, eax
0x14007d53a  jnz     loc_14007E6BA
0x14007d540  cmp     dword ptr [rsi+43Ch], 7FFFFFFFh
0x14007d54a  jz      loc_14007E6C5
0x14007d550  mov     [rsp+2B0h+var_258], 1
0x14007d555  lea     rax, aWorkerthreadLo; "WorkerThread:  Lock acquired"
0x14007d55c  mov     qword ptr [rbp+1B0h+var_230], rax
0x14007d560  mov     qword ptr [rbp+1B0h+var_230+8], 1Ch
0x14007d568  lea     rcx, [rbp+1B0h+var_230]
0x14007d56c  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007d571  mov     rcx, rsi; this
0x14007d574  call    ?SetWorking@UpdateManager@@AEAAXXZ; UpdateManager::SetWorking(void)
0x14007d579  nop
0x14007d57a  sub     dword ptr [rsi+43Ch], 1
0x14007d581  jnz     short loc_14007D59A
0x14007d583  mov     dword ptr [rsi+438h], 0FFFFFFFFh
0x14007d58d  lea     rcx, [rsi+400h]; SRWLock
0x14007d594  call    cs:__imp_ReleaseSRWLockExclusive
0x14007d59a  mov     rcx, rsi; this
0x14007d59d  call    ?Work@UpdateManager@@AEAAXXZ; UpdateManager::Work(void)
0x14007d5a2  xorps   xmm0, xmm0
0x14007d5a5  movups  [rbp+1B0h+var_230], xmm0
0x14007d5a9  lea     r13, [rsi+90h]
0x14007d5b0  mov     qword ptr [rbp+1B0h+var_230], r13
0x14007d5b4  mov     byte ptr [rbp+1B0h+var_230+8], 1
0x14007d5b8  mov     rcx, r13; this
0x14007d5bb  call    ?lock_shared@shared_recursive_mutex@mutex_extensions@@QEAAXXZ; mutex_extensions::shared_recursive_mutex::lock_shared(void)
0x14007d5c0  nop
0x14007d5c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::GetImpl(void)'::`2'::impl
0x14007d5c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_RemoveUpdateAsync_56459092>::__private_IsEnabled(void)
0x14007d5cd  mov     rcx, [rsi+150h]
0x14007d5d4  test    al, al
0x14007d5d6  jz      loc_14007DDB7
0x14007d5dc  test    rcx, rcx
0x14007d5df  jnz     loc_14007D668
0x14007d5e5  mov     [rbp+1B0h+var_58], r14b
0x14007d5ec  lea     edi, [rcx+1]
0x14007d5ef  mov     [rsp+2B0h+var_27C], edi
0x14007d5f3  lea     rdx, [rbp+1B0h+var_70]
0x14007d5fa  mov     rcx, [rsi+308h]
0x14007d601  call    ?ScanInProgress@ScanManager@@QEBA_NAEBV?$optional@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@@Z; ScanManager::ScanInProgress(std::optional<std::vector<std::wstring>> const &)
0x14007d606  test    al, al
0x14007d608  jnz     short loc_14007D668
0x14007d60a  mov     rcx, [rsi+310h]; this
0x14007d611  call    ?Running@BrokerManager@@QEAA_NXZ; BrokerManager::Running(void)
0x14007d616  test    al, al
0x14007d618  jnz     short loc_14007D668
0x14007d61a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::GetImpl(void)'::`2'::impl
0x14007d621  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Metrics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Metrics>::__private_IsEnabled(void)
0x14007d626  test    al, al
0x14007d628  jz      short loc_14007D64D
0x14007d62a  lea     rbx, [rsi+240h]
0x14007d631  mov     rcx, rbx; SRWLock
0x14007d634  call    cs:__imp_AcquireSRWLockShared
0x14007d63a  cmp     [rbx+10h], r14
0x14007d63e  setz    r14b
0x14007d642  mov     rcx, rbx; SRWLock
0x14007d645  call    cs:__imp_ReleaseSRWLockShared
0x14007d64b  jmp     short loc_14007D658
0x14007d64d  cmp     [rsi+1D8h], r14
0x14007d654  setz    r14b
0x14007d658  test    r14b, r14b
0x14007d65b  jz      short loc_14007D665
0x14007d65d  mov     bl, dil
0x14007d660  xor     r14d, r14d
0x14007d663  jmp     short loc_14007D66B
0x14007d665  xor     r14d, r14d
0x14007d668  mov     bl, r14b
0x14007d66b  test    dil, 1
0x14007d66f  jz      short loc_14007D689
0x14007d671  and     edi, 0FFFFFFFEh
0x14007d674  cmp     [rbp+1B0h+var_58], r14b
0x14007d67b  jz      short loc_14007D689
0x14007d67d  lea     rcx, [rbp+1B0h+var_70]
0x14007d684  call    ?_Tidy@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAXXZ; std::vector<std::filesystem::path>::_Tidy(void)
0x14007d689  test    bl, bl
0x14007d68b  jz      loc_14007E65A
0x14007d691  mov     rcx, [rsi+308h]; this
0x14007d698  call    ?IsAutoRescanEnabled@ScanManager@@QEBA_NXZ; ScanManager::IsAutoRescanEnabled(void)
0x14007d69d  test    al, al
0x14007d69f  jz      short loc_14007D6FA
0x14007d6a1  mov     r14, [rsi+308h]
0x14007d6a8  xor     r8d, r8d
0x14007d6ab  lea     rbx, aWorkerthreadFo; "WorkerThread:  Found update {}:{} that "...
0x14007d6b2  mov     rdx, rbx
0x14007d6b5  lea     r11, aNoWork; "No Work"
0x14007d6bc  mov     rcx, r11
0x14007d6bf  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14007d6c4  cmp     rax, rbx
0x14007d6c7  jz      loc_14007E6DA
0x14007d6cd  sub     rax, r11
0x14007d6d0  sar     rax, 1
0x14007d6d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007d6d7  jz      loc_14007E6DA
0x14007d6dd  mov     qword ptr [rsp+2B0h+var_268+8], r11
0x14007d6e2  mov     qword ptr [rsp+2B0h+var_258], rax
0x14007d6e7  mov     r9b, 1
0x14007d6ea  lea     rdx, [rsp+2B0h+var_268+8]
0x14007d6ef  mov     rcx, r14
0x14007d6f2  call    ?SetAutoRescanAllowed@ScanManager@@QEAAXV?$basic_zstring_view@_W@wil@@_N1@Z; ScanManager::SetAutoRescanAllowed(wil::basic_zstring_view<wchar_t>,bool,bool)
0x14007d6f7  xor     r14d, r14d
0x14007d6fa  mov     r15, [rsi+20h]
0x14007d6fe  mov     [rsp+2B0h+var_280], r14b
0x14007d703  mov     [rbp+1B0h+var_210], r14
0x14007d707  lea     r12, [rsi+2C0h]
0x14007d70e  mov     [rbp+1B0h+var_208], r12
0x14007d712  mov     rax, [rsi+10h]
0x14007d716  mov     [rbp+1B0h+var_200], rax
0x14007d71a  mov     [rbp+1B0h+var_1F8], r14
0x14007d71e  xorps   xmm0, xmm0
0x14007d721  movdqu  [rsp+2B0h+var_268+8], xmm0
0x14007d727  mov     rdx, [rsi+8]
0x14007d72b  test    rdx, rdx
0x14007d72e  jz      loc_14007E6AE
0x14007d734  mov     eax, [rdx+8]
0x14007d737  jmp     short loc_14007D743
0x14007d739  lea     ecx, [rax+1]
0x14007d73c  lock cmpxchg [rdx+8], ecx
0x14007d741  jz      short loc_14007D74D
0x14007d743  test    eax, eax
0x14007d745  jz      loc_14007E6AE
0x14007d74b  jmp     short loc_14007D739
0x14007d74d  mov     rax, [rsi]
0x14007d750  mov     qword ptr [rsp+2B0h+var_268+8], rax
0x14007d755  mov     rbx, [rsi+8]
0x14007d759  mov     qword ptr [rsp+2B0h+var_258], rbx
0x14007d75e  bts     edi, 0Ah
0x14007d762  mov     [rsp+2B0h+var_27C], edi
0x14007d766  xorps   xmm0, xmm0
0x14007d769  movdqu  [rbp+1B0h+var_1F0], xmm0
0x14007d76e  test    rbx, rbx
0x14007d771  jz      short loc_14007D77F
0x14007d773  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x14007d777  mov     qword ptr [rbp+1B0h+var_1F0+8], rbx
0x14007d77b  lock inc dword ptr [rbx+0Ch]
0x14007d77f  mov     [rbp+1B0h+var_1E0], r14
0x14007d783  mov     [rbp+1B0h+var_1C0], r14b
0x14007d787  movdqu  [rbp+1B0h+var_1B8], xmm0
0x14007d78c  mov     [rbp+1B0h+var_1A8], r14
0x14007d790  mov     ecx, 40h ; '@'
0x14007d795  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14007d79a  mov     [rax], rax
0x14007d79d  mov     [rax+8], rax
0x14007d7a1  mov     [rax+10h], rax
0x14007d7a5  mov     word ptr [rax+18h], 101h
0x14007d7ab  mov     qword ptr [rbp+1B0h+var_1B8+8], rax
0x14007d7af  xorps   xmm0, xmm0
0x14007d7b2  movsd   [rbp+1B0h+var_1A0], xmm0
0x14007d7b7  mov     [rbp+1B0h+var_170], r14b
0x14007d7bb  mov     [rbp+1B0h+var_138], r14b
0x14007d7bf  lea     rcx, [rbp+1B0h+var_130]
0x14007d7c6  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<std::wstring,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(void)
0x14007d7cb  nop
0x14007d7cc  lea     rcx, [rbp+1B0h+var_F0]
0x14007d7d3  call    ??0?$unordered_map@_KV?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KV?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>::unordered_map<unsigned __int64,std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>>(void)
0x14007d7d8  nop
0x14007d7d9  lea     rcx, [rbp+1B0h+var_B0]
0x14007d7e0  call    ??0?$unordered_map@_KV?$basic_zstring_view@_W@wil@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KV?$basic_zstring_view@_W@wil@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>::unordered_map<unsigned __int64,wil::basic_zstring_view<wchar_t>>(void)
0x14007d7e5  nop
0x14007d7e6  xor     r8d, r8d
0x14007d7e9  lea     r14, aNoWork; "No Work"
0x14007d7f0  mov     rdx, r14
0x14007d7f3  lea     r11, aSystemEnablePr; "System Enable Prehibernate Wake"
0x14007d7fa  mov     rcx, r11
0x14007d7fd  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14007d802  cmp     rax, r14
0x14007d805  jz      loc_14007E6F3
0x14007d80b  sub     rax, r11
0x14007d80e  sar     rax, 1
0x14007d811  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007d815  jz      loc_14007E6F3
0x14007d81b  mov     qword ptr [rsp+2B0h+var_278+8], r11
0x14007d820  mov     qword ptr [rsp+2B0h+var_268], rax
0x14007d825  lea     r9, [rsp+2B0h+var_280]
0x14007d82a  lea     r8, [rbp+1B0h+var_210]
0x14007d82e  lea     rdx, [rsp+2B0h+var_278+8]
0x14007d833  mov     rcx, r15
0x14007d836  call    ??$QueryOrDefault@_N@?$DecisionEngine@VConditionContext@Providers@SystemInterface@@@@QEBA_NV?$basic_zstring_view@_W@wil@@AEBVConditionContext@Providers@SystemInterface@@AEB_N_N@Z; DecisionEngine<SystemInterface::Providers::ConditionContext>::QueryOrDefault<bool>(wil::basic_zstring_view<wchar_t>,SystemInterface::Providers::ConditionContext const &,bool const &,bool)
0x14007d83b  test    al, al
0x14007d83d  jz      short loc_14007D886
0x14007d83f  lea     rcx, [rbp+1B0h+var_70]
0x14007d846  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14007d84b  nop
0x14007d84c  or      edi, 2
0x14007d84f  mov     [rsp+2B0h+var_27C], edi
0x14007d853  mov     rdx, [rax]
0x14007d856  mov     rax, [rdx+8]
0x14007d85a  movsxd  rcx, dword ptr [rax+4]
0x14007d85e  add     rdx, 8
0x14007d862  add     rcx, rdx
0x14007d865  mov     rax, [rcx]
0x14007d868  lea     rdx, [rsp+2B0h+var_250]
0x14007d86d  mov     rax, [rax+18h]
0x14007d871  call    _guard_dispatch_icall
0x14007d876  nop
0x14007d877  or      edi, 4
0x14007d87a  mov     rcx, [rax]
0x14007d87d  mov     rax, [rcx]
0x14007d880  mov     rax, [rax+10h]
0x14007d884  jmp     short loc_14007D8CA
0x14007d886  lea     rcx, [rbp+1B0h+var_50]
0x14007d88d  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14007d892  nop
0x14007d893  or      edi, 8
0x14007d896  mov     [rsp+2B0h+var_27C], edi
0x14007d89a  mov     rdx, [rax]
0x14007d89d  mov     rax, [rdx+8]
0x14007d8a1  movsxd  rcx, dword ptr [rax+4]
0x14007d8a5  add     rdx, 8
0x14007d8a9  add     rcx, rdx
0x14007d8ac  mov     rax, [rcx]
0x14007d8af  lea     rdx, [rbp+1B0h+var_220]
0x14007d8b3  mov     rax, [rax+18h]
0x14007d8b7  call    _guard_dispatch_icall
0x14007d8bc  nop
0x14007d8bd  or      edi, 10h
0x14007d8c0  mov     rcx, [rax]
0x14007d8c3  mov     rax, [rcx]
0x14007d8c6  mov     rax, [rax+18h]
0x14007d8ca  mov     [rsp+2B0h+var_27C], edi
0x14007d8ce  call    _guard_dispatch_icall
0x14007d8d3  nop
0x14007d8d4  or      r15, 0FFFFFFFFFFFFFFFFh
0x14007d8d8  test    dil, 10h
0x14007d8dc  jz      short loc_14007D924
0x14007d8de  and     edi, 0FFFFFFEFh
0x14007d8e1  mov     r14, [rbp+1B0h+var_218]
0x14007d8e5  test    r14, r14
0x14007d8e8  jz      short loc_14007D924
0x14007d8ea  mov     eax, r15d
0x14007d8ed  lock xadd [r14+8], eax
0x14007d8f3  add     eax, r15d
0x14007d8f6  jnz     short loc_14007D924
0x14007d8f8  mov     rax, [r14]
0x14007d8fb  mov     rcx, r14
0x14007d8fe  mov     rax, [rax]
0x14007d901  call    _guard_dispatch_icall
0x14007d906  mov     eax, r15d
0x14007d909  lock xadd [r14+0Ch], eax
0x14007d90f  add     eax, r15d
0x14007d912  jnz     short loc_14007D924
0x14007d914  mov     rax, [r14]
0x14007d917  mov     rcx, r14
0x14007d91a  mov     rax, [rax+8]
0x14007d91e  call    _guard_dispatch_icall
0x14007d923  nop
0x14007d924  test    dil, 8
0x14007d928  jz      short loc_14007D973
0x14007d92a  and     edi, 0FFFFFFF7h
0x14007d92d  mov     r14, [rbp+1B0h+var_48]
0x14007d934  test    r14, r14
0x14007d937  jz      short loc_14007D973
0x14007d939  mov     eax, r15d
0x14007d93c  lock xadd [r14+8], eax
0x14007d942  add     eax, r15d
0x14007d945  jnz     short loc_14007D973
0x14007d947  mov     rax, [r14]
0x14007d94a  mov     rcx, r14
0x14007d94d  mov     rax, [rax]
0x14007d950  call    _guard_dispatch_icall
0x14007d955  mov     eax, r15d
0x14007d958  lock xadd [r14+0Ch], eax
0x14007d95e  add     eax, r15d
0x14007d961  jnz     short loc_14007D973
0x14007d963  mov     rax, [r14]
0x14007d966  mov     rcx, r14
0x14007d969  mov     rax, [rax+8]
0x14007d96d  call    _guard_dispatch_icall
0x14007d972  nop
0x14007d973  test    dil, 4
  ... truncated ...
```
