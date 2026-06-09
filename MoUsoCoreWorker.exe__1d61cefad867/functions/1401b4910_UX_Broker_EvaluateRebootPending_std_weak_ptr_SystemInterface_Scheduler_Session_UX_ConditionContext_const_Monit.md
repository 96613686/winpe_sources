# UX::Broker::EvaluateRebootPending(std::weak_ptr<SystemInterface::Scheduler::Session>,UX::ConditionContext const &,Monitor<std::pair<bool,bool>> &,std::tuple<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bool> const &)

- ea: `0x1401b4910`
- end: `0x1401b5961`
- name: `?EvaluateRebootPending@Broker@UX@@AEAAXV?$weak_ptr@VSession@Scheduler@SystemInterface@@@std@@AEBVConditionContext@2@AEAV?$Monitor@U?$pair@_N_N@std@@@@AEBV?$tuple@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@_N@4@@Z`
- size: `4177`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14002ca74`
- `0x140040184`
- `0x140043504`
- `0x140043814`
- `0x140045404`
- `0x140045688`
- `0x14004b800`
- `0x14004d4d8`
- `0x14004f10c`
- `0x14004f25c`
- `0x1400508ac`
- `0x140053e98`
- `0x140057a20`
- `0x1400771e8`
- `0x1400772c4`
- `0x140088ed0`
- `0x140089128`
- `0x1400aae34`
- `0x1400c75e4`
- `0x1400cbdc8`
- `0x1400cd39c`
- `0x1400cd4f4`
- `0x1400eb300`
- `0x1400eeda4`
- `0x14012d7d8`
- `0x14012d864`
- `0x1401a8c3c`
- `0x1401b4834`
- `0x1401b4910`
- `0x1401cbe64`
- `0x1401cef34`
- `0x1401cf220`
- `0x1401d02d8`
- `0x1401d0e24`
- `0x1401e3918`
- `0x1401e3b4c`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4cdc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4d32`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4dee`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4fbc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b57be`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4cdc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4d32`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4dee`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b4fbc`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1401b57be`

## string_xrefs

- `0x1401b58ac`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401b58fb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401b594f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401b58ca`: `os updates context is missing`
- `0x1401b590d`: `os updates context is missing`
- `0x1401b5151`: `Feature update pending reboot`
- `0x1401b499f`: `UX::Broker::EvaluateRebootPending`
- `0x1401b4b37`: `Update reboot history information`
- `0x1401b4bde`: `Update reboot history information`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall UX::Broker::EvaluateRebootPending(
        UX::Broker *this,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall ***a4)())
{
  __int64 (__fastcall ***v4)(); // rsi
  __int64 v5; // rdi
  UX::Broker *v6; // r12
  __int64 v7; // rax
  _QWORD *System; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  void (__fastcall *v11)(__int64, __int128 *, unsigned __int128 *, __int64); // r14
  __int64 v12; // rax
  __int128 v13; // rax
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  int *traits_2_unsigned_short; // rax
  const char *v18; // r9
  int v19; // r11d
  __int64 v20; // rax
  const char *v21; // r9
  wchar_t *v22; // rax
  const char *v23; // r9
  int v24; // r11d
  __int64 v25; // rax
  __int64 v26; // rax
  _QWORD *v27; // rdi
  _QWORD *i; // rbx
  __int64 v29; // rsi
  _QWORD *v30; // rax
  __int64 v31; // rax
  __int64 v32; // r10
  __int64 (__fastcall *v33)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  signed __int64 v37; // rdx
  char v38; // si
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  _QWORD *v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  volatile signed __int32 *v46; // rbx
  volatile signed __int32 *v47; // rbx
  _QWORD *v48; // rax
  __int64 v49; // rbx
  int *v50; // rax
  const char *v51; // r9
  int v52; // r11d
  __int64 v53; // rax
  char v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rax
  volatile signed __int32 *v58; // rbx
  volatile signed __int32 *v59; // rbx
  _QWORD *v60; // rax
  __int64 v61; // rax
  __int64 v62; // r10
  void (__fastcall *v63)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  volatile signed __int32 *v67; // rbx
  volatile signed __int32 *v68; // rbx
  _QWORD *v69; // rax
  __int64 v70; // rax
  __int64 v71; // r10
  void (__fastcall *v72)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rdx
  volatile signed __int32 *v76; // rbx
  __int64 v77; // rdx
  __int64 v78; // rbx
  __int64 v79; // r8
  void (__fastcall ***v80)(_QWORD, __int64); // rcx
  __int64 v81; // rax
  __int64 v82; // rcx
  void (__fastcall ***v83)(_QWORD, __int64); // r8
  char IsScanning; // bl
  signed __int64 v85; // rbx
  volatile signed __int32 *v86; // rcx
  _BYTE v87[16]; // [rsp+30h] [rbp-2A8h] BYREF
  unsigned __int128 v88; // [rsp+40h] [rbp-298h] BYREF
  unsigned __int128 v89; // [rsp+50h] [rbp-288h] BYREF
  unsigned __int128 v90; // [rsp+60h] [rbp-278h] BYREF
  UX::Broker *v91; // [rsp+70h] [rbp-268h] BYREF
  volatile signed __int32 *v92; // [rsp+78h] [rbp-260h]
  unsigned __int128 v93; // [rsp+80h] [rbp-258h]
  __int128 v94; // [rsp+90h] [rbp-248h] BYREF
  unsigned __int128 v95; // [rsp+A0h] [rbp-238h] BYREF
  char v96; // [rsp+B0h] [rbp-228h]
  unsigned __int128 v97; // [rsp+C0h] [rbp-218h] BYREF
  unsigned __int128 v98; // [rsp+D0h] [rbp-208h] BYREF
  char v99; // [rsp+E8h] [rbp-1F0h]
  __int64 v100; // [rsp+F0h] [rbp-1E8h]
  __int64 (__fastcall **v101)(); // [rsp+F8h] [rbp-1E0h] BYREF
  _BYTE v102[32]; // [rsp+100h] [rbp-1D8h] BYREF
  char v103; // [rsp+120h] [rbp-1B8h]
  char v104; // [rsp+128h] [rbp-1B0h]
  __int64 (__fastcall ***v105)(); // [rsp+130h] [rbp-1A8h]
  __int64 v106; // [rsp+138h] [rbp-1A0h]
  _BYTE pExceptionObject[24]; // [rsp+140h] [rbp-198h] BYREF
  _BYTE v108[24]; // [rsp+158h] [rbp-180h] BYREF
  _BYTE v109[32]; // [rsp+170h] [rbp-168h] BYREF
  char v110; // [rsp+190h] [rbp-148h]
  char v111; // [rsp+198h] [rbp-140h]
  _QWORD v112[30]; // [rsp+1A0h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  *(_QWORD *)&v90 = a3;
  v100 = a2;
  v6 = this;
  v91 = this;
  v106 = a2;
  *(_QWORD *)&v93 = a3;
  *(_QWORD *)&v89 = a4;
  memset(v112, 0, 0xE8u);
  std::wostringstream::wostringstream(v112);
  v7 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v112, L"Evaluate Function Called: ");
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v7, "UX::Broker::EvaluateRebootPending");
  System = (_QWORD *)SystemInterface::Providers::GetSystem(&v95);
  v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*System + 56LL))(*System, &v97);
  v10 = *(_QWORD *)v9;
  v11 = *(void (__fastcall **)(__int64, __int128 *, unsigned __int128 *, __int64))(**(_QWORD **)v9 + 104LL);
  *(_QWORD *)&v94 = &v88;
  v88 = 0;
  v12 = *((_QWORD *)v6 + 1);
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v88 = *(_OWORD *)v6;
  *(_QWORD *)&v13 = std::wostringstream::str(v112, &v98);
  *((_QWORD *)&v13 + 1) = *(_QWORD *)(v13 + 16);
  if ( *(_QWORD *)(v13 + 24) > 7u )
    *(_QWORD *)&v13 = *(_QWORD *)v13;
  v94 = v13;
  v11(v10, &v94, &v88, 1);
  std::wstring::~wstring(&v98, v14);
  v15 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
  if ( *((_QWORD *)&v97 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
  if ( *((_QWORD *)&v95 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  *(_QWORD *)&v94 = (char *)v6 + 40;
  v87[0] = 0;
  traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                     L"Update reboot history information",
                                     &dword_140425924,
                                     0);
  if ( traits_2_unsigned_short == &dword_140425924
    || (v20 = ((char *)traits_2_unsigned_short - (char *)L"Update reboot history information") >> 1, v20 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v18);
  }
  *(_QWORD *)&v88 = L"Update reboot history information";
  *((_QWORD *)&v88 + 1) = v20;
  v95 = v88;
  try
  {
    if ( (unsigned __int8)DecisionEngine<UX::ConditionContext>::QueryOrDefault<bool>(
                            v19,
                            (unsigned int)&v95,
                            v5,
                            (unsigned int)v87,
                            1) )
      UX::Broker::UpdateRebootHistoryInformation(v6);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x513,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\ux\\Broker.cpp",
      v21);
    v6 = v91;
    v100 = v106;
    v5 = v93;
    *(_QWORD *)&v90 = v93;
    v4 = (__int64 (__fastcall ***)())v89;
  }
  v22 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Reboot required",
                     L"Update reboot history information",
                     0);
  if ( v22 == L"Update reboot history information" || (v25 = v22 - L"Reboot required", v25 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v23);
  *(_QWORD *)&v88 = L"Reboot required";
  *((_QWORD *)&v88 + 1) = v25;
  v95 = v88;
  DecisionEngine<UX::ConditionContext>::Query(v24, (unsigned int)v109, (unsigned int)&v95, v5, 1);
  if ( !v111 )
  {
LABEL_132:
    v99 = 0;
    IsScanning = UpdateManager::IsScanning(*((_QWORD *)v6 + 2), &v98);
    if ( v99 )
      std::vector<std::filesystem::path>::_Tidy(&v98);
    if ( !IsScanning && !UpdateManager::IsProgressing(*((UpdateManager **)v6 + 2)) )
    {
      UX::PersistedState::GetMeUpToDateSingleRebootInfo(*((_QWORD *)v6 + 3), &v88);
      if ( BYTE8(v88) )
      {
        v85 = v88 + 600000000;
        *(_QWORD *)&v90 = 0;
        GetSystemTimePreciseAsFileTime(&v90);
        v37 = (unsigned int)v90 + ((unsigned __int64)DWORD1(v90) << 32) - 116444736000000000LL;
        if ( v37 != v85 && v37 >= v85 )
          UX::PersistedState::SetGetMeUpToDateSingleReboot(*((UX::PersistedState **)v6 + 3), 0);
      }
    }
    goto LABEL_140;
  }
  if ( v110 )
  {
    if ( v110 == 1 )
    {
      if ( !UX::Broker::m_rebootRequiredWaitResult
        || byte_140507B58 && *(_BYTE *)(UX::Broker::m_rebootRequiredWaitResult + 184) )
      {
        goto LABEL_115;
      }
      *(_QWORD *)&v89 = 10;
      if ( byte_140507B58 && *(_BYTE *)(UX::Broker::m_rebootRequiredWaitResult + 184) )
        std::_Throw_future_error2(4);
      if ( !(unsigned int)std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1000>>(
                            UX::Broker::m_rebootRequiredWaitResult,
                            &v89) )
      {
LABEL_115:
        v101 = off_1403CFD60;
        v105 = &v101;
        Monitor<std::pair<bool,bool>>::send_change(v4, &v101);
        v101 = (__int64 (__fastcall **)())v6;
        std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>(
          v102,
          v109);
        v105 = v4;
        v78 = std::async__UX::Broker::EvaluateRebootPending_::_40_::_lambda_3___(&v98, v77, &v101);
        if ( &UX::Broker::m_rebootRequiredWaitResult != (__int64 *)v78 )
        {
          v79 = UX::Broker::m_rebootRequiredWaitResult;
          if ( UX::Broker::m_rebootRequiredWaitResult
            && _InterlockedExchangeAdd(
                 (volatile signed __int32 *)(UX::Broker::m_rebootRequiredWaitResult + 8),
                 0xFFFFFFFF) == 1 )
          {
            v80 = *(void (__fastcall ****)(_QWORD, __int64))(v79 + 200);
            if ( v80 )
              (**v80)(v80, v79);
            else
              (**(void (__fastcall ***)(__int64, __int64))v79)(v79, 1);
          }
          v81 = *(_QWORD *)v78;
          *(_QWORD *)v78 = 0;
          UX::Broker::m_rebootRequiredWaitResult = v81;
          byte_140507B58 = *(_BYTE *)(v78 + 8);
        }
        v82 = v98;
        if ( (_QWORD)v98 && _InterlockedExchangeAdd((volatile signed __int32 *)(v98 + 8), 0xFFFFFFFF) == 1 )
        {
          v83 = *(void (__fastcall ****)(_QWORD, __int64))(v82 + 200);
          if ( v83 )
            (**v83)(*(_QWORD *)(v82 + 200), v82);
          else
            (**(void (__fastcall ***)(__int64, __int64))v82)(v82, 1);
        }
        if ( v104 && v103 != -1 && v103 && v103 == 2 )
          std::wstring::~wstring(v102, v37);
      }
      goto LABEL_140;
    }
    goto LABEL_132;
  }
  v101 = off_1403CFD30;
  v105 = &v101;
  Monitor<std::pair<bool,bool>>::send_change(v4, &v101);
  if ( !v111 )
    std::_Throw_bad_optional_access();
  if ( v110 )
    std::_Throw_bad_variant_access();
  if ( !v109[0] )
  {
    v60 = (_QWORD *)SystemInterface::Service::GetSystem(&v90);
    v61 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v60 + 32LL))(*v60, &v94);
    v62 = *(_QWORD *)v61;
    v63 = *(void (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v61 + 80LL);
    v64 = -1;
    do
      ++v64;
    while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v64] );
    *(_QWORD *)&v88 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
    *((_QWORD *)&v88 + 1) = v64;
    v65 = -1;
    do
      ++v65;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v65] );
    *(_QWORD *)&v89 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v89 + 1) = v65;
    *(_QWORD *)&v93 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v66 = -1;
    do
      ++v66;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v66] );
    *((_QWORD *)&v93 + 1) = v66;
    v98 = v88;
    v95 = v89;
    v97 = v93;
    v63(v62, &v97, &v95, &v98);
    v67 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
    if ( *((_QWORD *)&v94 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
        if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
      }
    }
    v68 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
    if ( *((_QWORD *)&v90 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
        if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
      }
    }
    v69 = (_QWORD *)SystemInterface::Service::GetSystem(&v90);
    v70 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v69 + 32LL))(*v69, &v94);
    v71 = *(_QWORD *)v70;
    v72 = *(void (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v70 + 80LL);
    v73 = -1;
    do
      ++v73;
    while ( SystemInterface::Registry::ISCURRENTREBOOTFEATURE[v73] );
    *(_QWORD *)&v88 = SystemInterface::Registry::ISCURRENTREBOOTFEATURE;
    *((_QWORD *)&v88 + 1) = v73;
    v74 = -1;
    do
      ++v74;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v74] );
    *(_QWORD *)&v89 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v89 + 1) = v74;
    *(_QWORD *)&v93 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v75 = -1;
    do
      ++v75;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v75] );
    *((_QWORD *)&v93 + 1) = v75;
    v98 = v88;
    v95 = v89;
    v97 = v93;
    v72(v71, &v97, &v95, &v98);
    v76 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
    if ( *((_QWORD *)&v94 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
        if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
      }
    }
    v59 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
    goto LABEL_104;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::GetImpl'::`2'::impl) )
  {
    v91 = 0;
    GetSystemTimePreciseAsFileTime(&v91);
    *(_QWORD *)&v89 = ((unsigned __int64)HIDWORD(v91) << 32) - 116444736000000000LL + (unsigned int)v91;
    if ( !*(_BYTE *)(v5 + 72) )
    {
      std::logic_error::logic_error((std::logic_error *)pExceptionObject, "os updates context is missing");
      throw (std::logic_error *)pExceptionObject;
    }
    UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(v6, v5 + 56, &v89);
    v91 = 0;
    GetSystemTimePreciseAsFileTime(&v91);
    *(_QWORD *)&v89 = ((unsigned __int64)HIDWORD(v91) << 32) - 116444736000000000LL + (unsigned int)v91;
    v26 = UX::ConditionContext::AppUpdates(v5);
    UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(v6, v26, &v89);
  }
  else
  {
    if ( !*(_BYTE *)(v5 + 72) )
    {
      std::logic_error::logic_error((std::logic_error *)v108, "os updates context is missing");
      throw (std::logic_error *)v108;
    }
    v27 = *(_QWORD **)(v5 + 56);
    for ( i = (_QWORD *)*v27; i != v27; i = (_QWORD *)*i )
    {
      if ( !*(_BYTE *)(UpdateDatabase::GetUpdateRebootRecognitionTime(*((_QWORD *)v6 + 53), &v98, i[2]) + 8) )
      {
        UpdateDatabase::GetUpdateBlock(*((_QWORD *)v6 + 53), &v95, i[2]);
        if ( v96 )
        {
          if ( (_DWORD)v95 == 1 )
          {
            v29 = *((_QWORD *)v6 + 53);
            v91 = 0;
            GetSystemTimePreciseAsFileTime(&v91);
            *(_QWORD *)&v89 = ((unsigned __int64)HIDWORD(v91) << 32) - 116444736000000000LL + (unsigned int)v91;
            UpdateDatabase::SetUpdateRebootRecognitionTime(v29, i[2], &v89);
          }
        }
      }
    }
    LODWORD(v5) = v90;
  }
  v30 = (_QWORD *)SystemInterface::Service::GetSystem(&v91);
  v31 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*v30 + 32LL))(*v30, &v90);
  v32 = *(_QWORD *)v31;
  v33 = *(__int64 (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v31 + 32LL);
  v34 = -1;
  do
    ++v34;
  while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v34] );
  *(_QWORD *)&v88 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
  *((_QWORD *)&v88 + 1) = v34;
  v35 = -1;
  do
    ++v35;
  while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v35] );
  *(_QWORD *)&v89 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
  *((_QWORD *)&v89 + 1) = v35;
  *(_QWORD *)&v93 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
  v36 = -1;
  do
    ++v36;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v36] );
  *((_QWORD *)&v93 + 1) = v36;
  v95 = v88;
  v97 = v89;
  v88 = v93;
  v38 = v33(v32, &v88, &v97, &v95);
  v39 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
  if ( *((_QWORD *)&v90 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  v40 = v92;
  if ( v92 )
  {
    if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  if ( !v38 )
  {
    v41 = (_QWORD *)SystemInterface::Service::GetSystem(&v98);
    v42 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, UX::Broker **))(*(_QWORD *)*v41 + 32LL))(*v41, &v91);
    *(_QWORD *)&v90 = 0;
    GetSystemTimePreciseAsFileTime(&v90);
    *(_QWORD *)&v89 = ((unsigned __int64)DWORD1(v90) << 32) - 116444736000000000LL + (unsigned int)v90;
    v43 = -1;
    do
      ++v43;
    while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v43] );
    *(_QWORD *)&v88 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
    *((_QWORD *)&v88 + 1) = v43;
    v44 = -1;
    do
      ++v44;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v44] );
    *(_QWORD *)&v93 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v93 + 1) = v44;
    *(_QWORD *)&v90 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v45 = -1;
    do
      ++v45;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v45] );
    *((_QWORD *)&v90 + 1) = v45;
    v95 = v88;
    v97 = v93;
    v88 = v90;
    SystemInterface::Registry::SetSystemTime(
      v42,
      (unsigned int)&v88,
      (unsigned int)&v97,
      (unsigned int)&v95,
      (__int64)&v89);
    v46 = v92;
    if ( v92 )
    {
      if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    v47 = (volatile signed __int32 *)*((_QWORD *)&v98 + 1);
    if ( *((_QWORD *)&v98 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v98 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
        if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
      }
    }
    v48 = (_QWORD *)SystemInterface::Service::GetSystem(&v91);
    v49 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*v48 + 32LL))(*v48, &v90);
    v87[0] = 0;
    v50 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"Feature update pending reboot",
                   &dword_1404257DC,
                   0);
    if ( v50 == &dword_1404257DC || (v53 = ((char *)v50 - (char *)L"Feature update pending reboot") >> 1, v53 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v51);
    *(_QWORD *)&v88 = L"Feature update pending reboot";
    *((_QWORD *)&v88 + 1) = v53;
    v98 = v88;
    v54 = DecisionEngine<UX::ConditionContext>::QueryOrDefault<bool>(v52, (unsigned int)&v98, v5, (unsigned int)v87, 1);
    v55 = -1;
    do
      ++v55;
    while ( SystemInterface::Registry::ISCURRENTREBOOTFEATURE[v55] );
    v88 = __PAIR128__(v55, (unsigned __int64)SystemInterface::Registry::ISCURRENTREBOOTFEATURE);
    v56 = -1;
    do
      ++v56;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v56] );
    *(_QWORD *)&v89 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v89 + 1) = v56;
    *(_QWORD *)&v93 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v57 = -1;
    do
      ++v57;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v57] );
    *((_QWORD *)&v93 + 1) = v57;
    v98 = v88;
    v95 = v89;
    v97 = v93;
    SystemInterface::Registry::SetSystemBool(v49, (unsigned int)&v97, (unsigned int)&v95, (unsigned int)&v98, v54);
    v58 = (volatile signed __int32 *)*((_QWORD *)&v90 + 1);
    if ( *((_QWORD *)&v90 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v90 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
    v59 = v92;
LABEL_104:
    if ( v59 )
    {
      if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
    }
  }
LABEL_140:
  if ( v111 && v110 != -1 && v110 && v110 == 2 )
    std::wstring::~wstring(v109, v37);
  std::wostringstream::~wostringstream(&v112[17]);
  v112[17] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v112[17]);
  v86 = *(volatile signed __int32 **)(v100 + 8);
  if ( v86 )
  {
    if ( !_InterlockedDecrement(v86 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
  }
}

```

## disassembly

```asm
0x1401b4910  push    rbx
0x1401b4912  push    rsi
0x1401b4913  push    rdi
0x1401b4914  push    r12
0x1401b4916  push    r13
0x1401b4918  push    r14
0x1401b491a  push    r15
0x1401b491c  sub     rsp, 2A0h
0x1401b4923  mov     rax, cs:__security_cookie
0x1401b492a  xor     rax, rsp
0x1401b492d  mov     [rsp+2D8h+var_48], rax
0x1401b4935  mov     rsi, r9
0x1401b4938  mov     rdi, r8
0x1401b493b  mov     qword ptr [rsp+2D8h+var_278], r8
0x1401b4940  mov     [rsp+2D8h+var_1E8], rdx
0x1401b4948  mov     r12, rcx
0x1401b494b  mov     [rsp+2D8h+var_268], rcx
0x1401b4950  mov     [rsp+2D8h+var_1A0], rdx
0x1401b4958  mov     qword ptr [rsp+2D8h+var_258], r8
0x1401b4960  mov     qword ptr [rsp+2D8h+var_288], r9
0x1401b4965  xor     edx, edx; Val
0x1401b4967  mov     r8d, 0E8h; Size
0x1401b496d  lea     rcx, [rsp+2D8h+var_138]; void *
0x1401b4975  call    memset
0x1401b497a  lea     rcx, [rsp+2D8h+var_138]
0x1401b4982  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x1401b4987  nop
0x1401b4988  lea     rdx, aEvaluateFuncti; "Evaluate Function Called: "
0x1401b498f  lea     rcx, [rsp+2D8h+var_138]
0x1401b4997  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1401b499c  mov     rcx, rax
0x1401b499f  lea     rdx, aUxBrokerEvalua_5; "UX::Broker::EvaluateRebootPending"
0x1401b49a6  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEBD@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,char const *)
0x1401b49ab  lea     rcx, [rsp+2D8h+var_238]
0x1401b49b3  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1401b49b8  nop
0x1401b49b9  mov     rcx, [rax]
0x1401b49bc  mov     rax, [rcx]
0x1401b49bf  lea     rdx, [rsp+2D8h+var_218]
0x1401b49c7  mov     rax, [rax+38h]
0x1401b49cb  call    _guard_dispatch_icall
0x1401b49d0  nop
0x1401b49d1  mov     rbx, [rax]
0x1401b49d4  mov     rax, [rbx]
0x1401b49d7  mov     r14, [rax+68h]
0x1401b49db  lea     rax, [rsp+2D8h+var_298]
0x1401b49e0  mov     qword ptr [rsp+2D8h+var_248], rax
0x1401b49e8  xorps   xmm0, xmm0
0x1401b49eb  movdqu  [rsp+2D8h+var_298], xmm0
0x1401b49f1  mov     rax, [r12+8]
0x1401b49f6  xor     r15d, r15d
0x1401b49f9  test    rax, rax
0x1401b49fc  jz      short loc_1401B4A02
0x1401b49fe  lock inc dword ptr [rax+8]
0x1401b4a02  mov     rax, [r12]
0x1401b4a06  mov     qword ptr [rsp+2D8h+var_298], rax
0x1401b4a0b  mov     rax, [r12+8]
0x1401b4a10  mov     qword ptr [rsp+2D8h+var_298+8], rax
0x1401b4a15  lea     rdx, [rsp+2D8h+var_208]
0x1401b4a1d  lea     rcx, [rsp+2D8h+var_138]
0x1401b4a25  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x1401b4a2a  nop
0x1401b4a2b  mov     rdx, [rax+10h]
0x1401b4a2f  cmp     qword ptr [rax+18h], 7
0x1401b4a34  jbe     short loc_1401B4A39
0x1401b4a36  mov     rax, [rax]
0x1401b4a39  mov     qword ptr [rsp+2D8h+var_248], rax
0x1401b4a41  mov     qword ptr [rsp+2D8h+var_248+8], rdx
0x1401b4a49  movaps  xmm0, [rsp+2D8h+var_248]
0x1401b4a51  movdqa  [rsp+2D8h+var_248], xmm0
0x1401b4a5a  mov     r9d, 1
0x1401b4a60  lea     r8, [rsp+2D8h+var_298]
0x1401b4a65  lea     rdx, [rsp+2D8h+var_248]
0x1401b4a6d  mov     rcx, rbx
0x1401b4a70  mov     rax, r14
0x1401b4a73  call    _guard_dispatch_icall
0x1401b4a78  nop
0x1401b4a79  lea     rcx, [rsp+2D8h+var_208]
0x1401b4a81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1401b4a86  nop
0x1401b4a87  mov     rbx, qword ptr [rsp+2D8h+var_218+8]
0x1401b4a8f  or      r14, 0FFFFFFFFFFFFFFFFh
0x1401b4a93  test    rbx, rbx
0x1401b4a96  jz      short loc_1401B4AD0
0x1401b4a98  mov     eax, r14d
0x1401b4a9b  lock xadd [rbx+8], eax
0x1401b4aa0  add     eax, r14d
0x1401b4aa3  jnz     short loc_1401B4AD0
0x1401b4aa5  mov     rax, [rbx]
0x1401b4aa8  mov     rcx, rbx
0x1401b4aab  mov     rax, [rax]
0x1401b4aae  call    _guard_dispatch_icall
0x1401b4ab3  mov     eax, r14d
0x1401b4ab6  lock xadd [rbx+0Ch], eax
0x1401b4abb  add     eax, r14d
0x1401b4abe  jnz     short loc_1401B4AD0
0x1401b4ac0  mov     rax, [rbx]
0x1401b4ac3  mov     rcx, rbx
0x1401b4ac6  mov     rax, [rax+8]
0x1401b4aca  call    _guard_dispatch_icall
0x1401b4acf  nop
0x1401b4ad0  mov     rbx, qword ptr [rsp+2D8h+var_238+8]
0x1401b4ad8  test    rbx, rbx
0x1401b4adb  jz      short loc_1401B4B15
0x1401b4add  mov     eax, r14d
0x1401b4ae0  lock xadd [rbx+8], eax
0x1401b4ae5  add     eax, r14d
0x1401b4ae8  jnz     short loc_1401B4B15
0x1401b4aea  mov     rax, [rbx]
0x1401b4aed  mov     rcx, rbx
0x1401b4af0  mov     rax, [rax]
0x1401b4af3  call    _guard_dispatch_icall
0x1401b4af8  mov     eax, r14d
0x1401b4afb  lock xadd [rbx+0Ch], eax
0x1401b4b00  add     eax, r14d
0x1401b4b03  jnz     short loc_1401B4B15
0x1401b4b05  mov     rax, [rbx]
0x1401b4b08  mov     rcx, rbx
0x1401b4b0b  mov     rax, [rax+8]
0x1401b4b0f  call    _guard_dispatch_icall
0x1401b4b14  nop
0x1401b4b15  lea     rax, [r12+28h]
0x1401b4b1a  mov     qword ptr [rsp+2D8h+var_248], rax
0x1401b4b22  mov     r11, [rax]
0x1401b4b25  mov     [rsp+2D8h+var_2A8], r15b
0x1401b4b2a  xor     r8d, r8d
0x1401b4b2d  lea     rbx, dword_140425924
0x1401b4b34  mov     rdx, rbx
0x1401b4b37  lea     r13, aUpdateRebootHi; "Update reboot history information"
0x1401b4b3e  mov     rcx, r13
0x1401b4b41  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1401b4b46  cmp     rax, rbx
0x1401b4b49  jz      loc_1401B58A4
0x1401b4b4f  sub     rax, r13
0x1401b4b52  sar     rax, 1
0x1401b4b55  cmp     rax, r14
0x1401b4b58  jz      loc_1401B58A4
0x1401b4b5e  mov     qword ptr [rsp+2D8h+var_298], r13
0x1401b4b63  mov     qword ptr [rsp+2D8h+var_298+8], rax
0x1401b4b68  movaps  xmm0, [rsp+2D8h+var_298]
0x1401b4b6d  movdqa  [rsp+2D8h+var_238], xmm0
0x1401b4b76  mov     byte ptr [rsp+2D8h+var_2B8], 1
0x1401b4b7b  lea     r9, [rsp+2D8h+var_2A8]
0x1401b4b80  mov     r8, rdi
0x1401b4b83  lea     rdx, [rsp+2D8h+var_238]
0x1401b4b8b  mov     rcx, r11
0x1401b4b8e  call    ??$QueryOrDefault@_N@?$DecisionEngine@VConditionContext@UX@@@@QEBA_NV?$basic_zstring_view@_W@wil@@AEBVConditionContext@UX@@AEB_N_N@Z; DecisionEngine<UX::ConditionContext>::QueryOrDefault<bool>(wil::basic_zstring_view<wchar_t>,UX::ConditionContext const &,bool const &,bool)
0x1401b4b93  test    al, al
0x1401b4b95  jz      short loc_1401B4BA0
0x1401b4b97  mov     rcx, r12; this
0x1401b4b9a  call    ?UpdateRebootHistoryInformation@Broker@UX@@AEAAXXZ; UX::Broker::UpdateRebootHistoryInformation(void)
0x1401b4b9f  nop
0x1401b4ba0  jmp     short loc_1401B4BD0
0x1401b4ba2  xor     r15d, r15d
0x1401b4ba5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1401b4ba9  mov     r12, [rsp+2D8h+var_268]
0x1401b4bae  mov     rax, [rsp+2D8h+var_1A0]
0x1401b4bb6  mov     [rsp+2D8h+var_1E8], rax
0x1401b4bbe  mov     rdi, qword ptr [rsp+2D8h+var_258]
0x1401b4bc6  mov     qword ptr [rsp+2D8h+var_278], rdi
0x1401b4bcb  mov     rsi, qword ptr [rsp+2D8h+var_288]
0x1401b4bd0  mov     rax, qword ptr [rsp+2D8h+var_248]
0x1401b4bd8  mov     r11, [rax]
0x1401b4bdb  xor     r8d, r8d
0x1401b4bde  lea     rbx, aUpdateRebootHi; "Update reboot history information"
0x1401b4be5  mov     rdx, rbx
0x1401b4be8  lea     r13, aRebootRequired; "Reboot required"
0x1401b4bef  mov     rcx, r13
0x1401b4bf2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1401b4bf7  cmp     rax, rbx
0x1401b4bfa  jz      loc_1401B5947
0x1401b4c00  sub     rax, r13
0x1401b4c03  sar     rax, 1
0x1401b4c06  cmp     rax, r14
0x1401b4c09  jz      loc_1401B5947
0x1401b4c0f  mov     qword ptr [rsp+2D8h+var_298], r13
0x1401b4c14  mov     qword ptr [rsp+2D8h+var_298+8], rax
0x1401b4c19  movaps  xmm0, [rsp+2D8h+var_298]
0x1401b4c1e  movdqa  [rsp+2D8h+var_238], xmm0
0x1401b4c27  mov     byte ptr [rsp+2D8h+var_2B8], 1
0x1401b4c2c  mov     r9, rdi
0x1401b4c2f  lea     r8, [rsp+2D8h+var_238]
0x1401b4c37  lea     rdx, [rsp+2D8h+var_168]
0x1401b4c3f  mov     rcx, r11
0x1401b4c42  call    ?Query@?$DecisionEngine@VConditionContext@UX@@@@QEBA?AV?$optional@V?$variant@_NHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@AEBVConditionContext@UX@@_N@Z; DecisionEngine<UX::ConditionContext>::Query(wil::basic_zstring_view<wchar_t>,UX::ConditionContext const &,bool)
0x1401b4c47  nop
0x1401b4c48  cmp     [rsp+2D8h+var_140], r15b
0x1401b4c50  jz      loc_1401B574D
0x1401b4c56  mov     al, [rsp+2D8h+var_148]
0x1401b4c5d  test    al, al
0x1401b4c5f  jnz     loc_1401B5588
0x1401b4c65  lea     rax, off_1403CFD30
0x1401b4c6c  mov     [rsp+2D8h+var_1E0], rax
0x1401b4c74  lea     rax, [rsp+2D8h+var_1E0]
0x1401b4c7c  mov     [rsp+2D8h+var_1A8], rax
0x1401b4c84  lea     rdx, [rsp+2D8h+var_1E0]
0x1401b4c8c  mov     rcx, rsi
0x1401b4c8f  call    ?send_change@?$Monitor@U?$pair@_N_N@std@@@@QEAAXV?$function@$$A6A?AU?$pair@_N_N@std@@AEBU12@@Z@std@@@Z; Monitor<std::pair<bool,bool>>::send_change(std::function<std::pair<bool,bool> (std::pair<bool,bool> const &)>)
0x1401b4c94  cmp     [rsp+2D8h+var_140], r15b
0x1401b4c9c  jz      loc_1401B58BE
0x1401b4ca2  cmp     [rsp+2D8h+var_148], r15b
0x1401b4caa  jnz     loc_1401B5936
0x1401b4cb0  cmp     [rsp+2D8h+var_168], r15b
0x1401b4cb8  jz      loc_1401B52AF
0x1401b4cbe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AppNotifications@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AppNotifications@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::GetImpl(void)'::`2'::impl
0x1401b4cc5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AppNotifications@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::__private_IsEnabled(void)
0x1401b4cca  test    al, al
0x1401b4ccc  jz      loc_1401B4D6C
0x1401b4cd2  mov     [rsp+2D8h+var_268], r15
0x1401b4cd7  lea     rcx, [rsp+2D8h+var_268]
0x1401b4cdc  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1401b4ce2  mov     eax, dword ptr [rsp+2D8h+var_268+4]
0x1401b4ce6  shl     rax, 20h
0x1401b4cea  mov     ecx, dword ptr [rsp+2D8h+var_268]
0x1401b4cee  mov     r13, 0FE624E212AC18000h
0x1401b4cf8  add     rax, r13
0x1401b4cfb  add     rcx, rax
0x1401b4cfe  mov     qword ptr [rsp+2D8h+var_288], rcx
0x1401b4d03  cmp     [rdi+48h], r15b
0x1401b4d07  jz      loc_1401B58CA
0x1401b4d0d  lea     rdx, [rdi+38h]
0x1401b4d11  cmp     [rdx+10h], r15b
0x1401b4d15  jz      loc_1401B58C4
0x1401b4d1b  lea     r8, [rsp+2D8h+var_288]
0x1401b4d20  mov     rcx, r12
0x1401b4d23  call    ?SetUpdateRebootRecognitionTimeForUpdateList@Broker@UX@@AEAAXAEBV?$list@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(std::list<std::shared_ptr<Update>> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1401b4d28  mov     [rsp+2D8h+var_268], r15
0x1401b4d2d  lea     rcx, [rsp+2D8h+var_268]
0x1401b4d32  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1401b4d38  mov     eax, dword ptr [rsp+2D8h+var_268+4]
0x1401b4d3c  shl     rax, 20h
0x1401b4d40  mov     edx, dword ptr [rsp+2D8h+var_268]
0x1401b4d44  add     rax, r13
0x1401b4d47  add     rdx, rax
0x1401b4d4a  mov     qword ptr [rsp+2D8h+var_288], rdx
0x1401b4d4f  mov     rcx, rdi
0x1401b4d52  call    ?AppUpdates@ConditionContext@UX@@QEBAAEBV?$list@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@XZ; UX::ConditionContext::AppUpdates(void)
0x1401b4d57  lea     r8, [rsp+2D8h+var_288]
0x1401b4d5c  mov     rdx, rax
0x1401b4d5f  mov     rcx, r12
0x1401b4d62  call    ?SetUpdateRebootRecognitionTimeForUpdateList@Broker@UX@@AEAAXAEBV?$list@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(std::list<std::shared_ptr<Update>> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1401b4d67  jmp     loc_1401B4E29
0x1401b4d6c  cmp     [rdi+48h], r15b
0x1401b4d70  jz      loc_1401B590D
0x1401b4d76  mov     rdi, [rdi+38h]
0x1401b4d7a  mov     rbx, [rdi]
0x1401b4d7d  mov     r13, 0FE624E212AC18000h
0x1401b4d87  cmp     rbx, rdi
0x1401b4d8a  jz      loc_1401B4E24
0x1401b4d90  mov     r8, [rbx+10h]
0x1401b4d94  lea     rdx, [rsp+2D8h+var_208]
0x1401b4d9c  mov     rcx, [r12+1A8h]
0x1401b4da4  call    ?GetUpdateRebootRecognitionTime@UpdateDatabase@@QEBA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetUpdateRebootRecognitionTime(Update const &)
0x1401b4da9  cmp     [rax+8], r15b
0x1401b4dad  jnz     short loc_1401B4E1C
0x1401b4daf  mov     r8, [rbx+10h]
0x1401b4db3  lea     rdx, [rsp+2D8h+var_238]
0x1401b4dbb  mov     rcx, [r12+1A8h]
0x1401b4dc3  call    ?GetUpdateBlock@UpdateDatabase@@QEBA?AV?$optional@U?$pair@W4UpdateBlock@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@@std@@AEBVUpdate@@@Z; UpdateDatabase::GetUpdateBlock(Update const &)
0x1401b4dc8  cmp     [rsp+2D8h+var_228], r15b
0x1401b4dd0  jz      short loc_1401B4E1C
0x1401b4dd2  cmp     dword ptr [rsp+2D8h+var_238], 1
0x1401b4dda  jnz     short loc_1401B4E1C
0x1401b4ddc  mov     rsi, [r12+1A8h]
0x1401b4de4  mov     [rsp+2D8h+var_268], r15
0x1401b4de9  lea     rcx, [rsp+2D8h+var_268]
0x1401b4dee  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1401b4df4  mov     eax, dword ptr [rsp+2D8h+var_268+4]
0x1401b4df8  shl     rax, 20h
0x1401b4dfc  mov     edx, dword ptr [rsp+2D8h+var_268]
0x1401b4e00  add     rax, r13
0x1401b4e03  add     rdx, rax
0x1401b4e06  mov     qword ptr [rsp+2D8h+var_288], rdx
0x1401b4e0b  lea     r8, [rsp+2D8h+var_288]
0x1401b4e10  mov     rdx, [rbx+10h]
0x1401b4e14  mov     rcx, rsi
0x1401b4e17  call    ?SetUpdateRebootRecognitionTime@UpdateDatabase@@QEAAXAEBVUpdate@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; UpdateDatabase::SetUpdateRebootRecognitionTime(Update const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1401b4e1c  mov     rbx, [rbx]
0x1401b4e1f  jmp     loc_1401B4D87
0x1401b4e24  mov     rdi, qword ptr [rsp+2D8h+var_278]
0x1401b4e29  lea     rcx, [rsp+2D8h+var_268]
0x1401b4e2e  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1401b4e33  nop
0x1401b4e34  mov     rcx, [rax]
0x1401b4e37  mov     rax, [rcx]
0x1401b4e3a  lea     rdx, [rsp+2D8h+var_278]
0x1401b4e3f  mov     rax, [rax+20h]
0x1401b4e43  call    _guard_dispatch_icall
0x1401b4e48  nop
0x1401b4e49  mov     r10, [rax]
0x1401b4e4c  mov     rax, [r10]
0x1401b4e4f  mov     r11, [rax+20h]
0x1401b4e53  mov     rcx, cs:?CURRENTREBOOTRECOGNITIONTIME@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME
0x1401b4e5a  mov     rax, r14
0x1401b4e5d  inc     rax
0x1401b4e60  cmp     [rcx+rax*2], r15w
0x1401b4e65  jnz     short loc_1401B4E5D
0x1401b4e67  mov     qword ptr [rsp+2D8h+var_298], rcx
0x1401b4e6c  mov     qword ptr [rsp+2D8h+var_298+8], rax
0x1401b4e71  mov     rcx, cs:?UPDATE_UX_STATEVARIABLES_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT
  ... truncated ...
```
