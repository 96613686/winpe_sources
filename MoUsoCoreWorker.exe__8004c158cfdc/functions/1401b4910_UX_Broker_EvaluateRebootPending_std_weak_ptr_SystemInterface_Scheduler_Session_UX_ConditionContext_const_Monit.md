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
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  int *traits_2_unsigned_short; // rax
  const char *v17; // r9
  int v18; // r11d
  __int64 v19; // rax
  const char *v20; // r9
  wchar_t *v21; // rax
  const char *v22; // r9
  int v23; // r11d
  __int64 v24; // rax
  __int64 v25; // rax
  _QWORD *v26; // rdi
  _QWORD *i; // rbx
  __int64 v28; // rsi
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // r10
  __int64 (__fastcall *v32)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  char v36; // si
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  _QWORD *v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  volatile signed __int32 *v44; // rbx
  volatile signed __int32 *v45; // rbx
  _QWORD *v46; // rax
  __int64 v47; // rbx
  int *v48; // rax
  const char *v49; // r9
  int v50; // r11d
  __int64 v51; // rax
  char v52; // r8
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  volatile signed __int32 *v56; // rbx
  volatile signed __int32 *v57; // rbx
  _QWORD *v58; // rax
  __int64 v59; // rax
  __int64 v60; // r10
  void (__fastcall *v61)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  volatile signed __int32 *v65; // rbx
  volatile signed __int32 *v66; // rbx
  _QWORD *v67; // rax
  __int64 v68; // rax
  __int64 v69; // r10
  void (__fastcall *v70)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *); // r11
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  volatile signed __int32 *v74; // rbx
  __int64 v75; // rdx
  __int64 v76; // rbx
  __int64 v77; // r8
  void (__fastcall ***v78)(_QWORD, __int64); // rcx
  __int64 v79; // rax
  __int64 v80; // rcx
  void (__fastcall ***v81)(_QWORD, __int64); // r8
  char IsScanning; // bl
  signed __int64 v83; // rbx
  signed __int64 v84; // rdx
  volatile signed __int32 *v85; // rcx
  _BYTE v86[16]; // [rsp+30h] [rbp-2A8h] BYREF
  unsigned __int128 v87; // [rsp+40h] [rbp-298h] BYREF
  unsigned __int128 v88; // [rsp+50h] [rbp-288h] BYREF
  unsigned __int128 v89; // [rsp+60h] [rbp-278h] BYREF
  UX::Broker *v90; // [rsp+70h] [rbp-268h] BYREF
  volatile signed __int32 *v91; // [rsp+78h] [rbp-260h]
  unsigned __int128 v92; // [rsp+80h] [rbp-258h]
  __int128 v93; // [rsp+90h] [rbp-248h] BYREF
  unsigned __int128 v94; // [rsp+A0h] [rbp-238h] BYREF
  char v95; // [rsp+B0h] [rbp-228h]
  unsigned __int128 v96; // [rsp+C0h] [rbp-218h] BYREF
  unsigned __int128 v97; // [rsp+D0h] [rbp-208h] BYREF
  char v98; // [rsp+E8h] [rbp-1F0h]
  __int64 v99; // [rsp+F0h] [rbp-1E8h]
  __int64 (__fastcall **v100)(); // [rsp+F8h] [rbp-1E0h] BYREF
  _BYTE v101[32]; // [rsp+100h] [rbp-1D8h] BYREF
  char v102; // [rsp+120h] [rbp-1B8h]
  char v103; // [rsp+128h] [rbp-1B0h]
  __int64 (__fastcall ***v104)(); // [rsp+130h] [rbp-1A8h]
  __int64 v105; // [rsp+138h] [rbp-1A0h]
  _BYTE pExceptionObject[24]; // [rsp+140h] [rbp-198h] BYREF
  _BYTE v107[24]; // [rsp+158h] [rbp-180h] BYREF
  _BYTE v108[32]; // [rsp+170h] [rbp-168h] BYREF
  char v109; // [rsp+190h] [rbp-148h]
  char v110; // [rsp+198h] [rbp-140h]
  _QWORD v111[30]; // [rsp+1A0h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  *(_QWORD *)&v89 = a3;
  v99 = a2;
  v6 = this;
  v90 = this;
  v105 = a2;
  *(_QWORD *)&v92 = a3;
  *(_QWORD *)&v88 = a4;
  memset(v111, 0, 0xE8u);
  std::wostringstream::wostringstream(v111);
  v7 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v111, L"Evaluate Function Called: ");
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v7, "UX::Broker::EvaluateRebootPending");
  System = (_QWORD *)SystemInterface::Providers::GetSystem(&v94);
  v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*System + 56LL))(*System, &v96);
  v10 = *(_QWORD *)v9;
  v11 = *(void (__fastcall **)(__int64, __int128 *, unsigned __int128 *, __int64))(**(_QWORD **)v9 + 104LL);
  *(_QWORD *)&v93 = &v87;
  v87 = 0;
  v12 = *((_QWORD *)v6 + 1);
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v87 = *(_OWORD *)v6;
  *(_QWORD *)&v13 = std::wostringstream::str(v111, &v97);
  *((_QWORD *)&v13 + 1) = *(_QWORD *)(v13 + 16);
  if ( *(_QWORD *)(v13 + 24) > 7u )
    *(_QWORD *)&v13 = *(_QWORD *)v13;
  v93 = v13;
  v11(v10, &v93, &v87, 1);
  std::wstring::~wstring(&v97);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v96 + 1);
  if ( *((_QWORD *)&v96 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v96 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
  if ( *((_QWORD *)&v94 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  *(_QWORD *)&v93 = (char *)v6 + 40;
  v86[0] = 0;
  traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                     L"Update reboot history information",
                                     &dword_140425924,
                                     0);
  if ( traits_2_unsigned_short == &dword_140425924
    || (v19 = ((char *)traits_2_unsigned_short - (char *)L"Update reboot history information") >> 1, v19 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v17);
  }
  *(_QWORD *)&v87 = L"Update reboot history information";
  *((_QWORD *)&v87 + 1) = v19;
  v94 = v87;
  try
  {
    if ( (unsigned __int8)DecisionEngine<UX::ConditionContext>::QueryOrDefault<bool>(
                            v18,
                            (unsigned int)&v94,
                            v5,
                            (unsigned int)v86,
                            1) )
      UX::Broker::UpdateRebootHistoryInformation(v6);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x513,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\ux\\Broker.cpp",
      v20);
    v6 = v90;
    v99 = v105;
    v5 = v92;
    *(_QWORD *)&v89 = v92;
    v4 = (__int64 (__fastcall ***)())v88;
  }
  v21 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Reboot required",
                     L"Update reboot history information",
                     0);
  if ( v21 == L"Update reboot history information" || (v24 = v21 - L"Reboot required", v24 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v22);
  *(_QWORD *)&v87 = L"Reboot required";
  *((_QWORD *)&v87 + 1) = v24;
  v94 = v87;
  DecisionEngine<UX::ConditionContext>::Query(v23, (unsigned int)v108, (unsigned int)&v94, v5, 1);
  if ( !v110 )
  {
LABEL_132:
    v98 = 0;
    IsScanning = UpdateManager::IsScanning(*((_QWORD *)v6 + 2), &v97);
    if ( v98 )
      std::vector<std::filesystem::path>::_Tidy(&v97);
    if ( !IsScanning && !UpdateManager::IsProgressing(*((UpdateManager **)v6 + 2)) )
    {
      UX::PersistedState::GetMeUpToDateSingleRebootInfo(*((_QWORD *)v6 + 3), &v87);
      if ( BYTE8(v87) )
      {
        v83 = v87 + 600000000;
        *(_QWORD *)&v89 = 0;
        GetSystemTimePreciseAsFileTime(&v89);
        v84 = (unsigned int)v89 + ((unsigned __int64)DWORD1(v89) << 32) - 116444736000000000LL;
        if ( v84 != v83 && v84 >= v83 )
          UX::PersistedState::SetGetMeUpToDateSingleReboot(*((UX::PersistedState **)v6 + 3), 0);
      }
    }
    goto LABEL_140;
  }
  if ( v109 )
  {
    if ( v109 == 1 )
    {
      if ( !UX::Broker::m_rebootRequiredWaitResult
        || byte_140507B58 && *(_BYTE *)(UX::Broker::m_rebootRequiredWaitResult + 184) )
      {
        goto LABEL_115;
      }
      *(_QWORD *)&v88 = 10;
      if ( byte_140507B58 && *(_BYTE *)(UX::Broker::m_rebootRequiredWaitResult + 184) )
        std::_Throw_future_error2(4);
      if ( !(unsigned int)std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1000>>(
                            UX::Broker::m_rebootRequiredWaitResult,
                            &v88) )
      {
LABEL_115:
        v100 = off_1403CFD60;
        v104 = &v100;
        Monitor<std::pair<bool,bool>>::send_change(v4, &v100);
        v100 = (__int64 (__fastcall **)())v6;
        std::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>::optional<std::variant<bool,int,std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>>(
          v101,
          v108);
        v104 = v4;
        v76 = std::async__UX::Broker::EvaluateRebootPending_::_40_::_lambda_3___(&v97, v75, &v100);
        if ( &UX::Broker::m_rebootRequiredWaitResult != (__int64 *)v76 )
        {
          v77 = UX::Broker::m_rebootRequiredWaitResult;
          if ( UX::Broker::m_rebootRequiredWaitResult
            && _InterlockedExchangeAdd(
                 (volatile signed __int32 *)(UX::Broker::m_rebootRequiredWaitResult + 8),
                 0xFFFFFFFF) == 1 )
          {
            v78 = *(void (__fastcall ****)(_QWORD, __int64))(v77 + 200);
            if ( v78 )
              (**v78)(v78, v77);
            else
              (**(void (__fastcall ***)(__int64, __int64))v77)(v77, 1);
          }
          v79 = *(_QWORD *)v76;
          *(_QWORD *)v76 = 0;
          UX::Broker::m_rebootRequiredWaitResult = v79;
          byte_140507B58 = *(_BYTE *)(v76 + 8);
        }
        v80 = v97;
        if ( (_QWORD)v97 && _InterlockedExchangeAdd((volatile signed __int32 *)(v97 + 8), 0xFFFFFFFF) == 1 )
        {
          v81 = *(void (__fastcall ****)(_QWORD, __int64))(v80 + 200);
          if ( v81 )
            (**v81)(*(_QWORD *)(v80 + 200), v80);
          else
            (**(void (__fastcall ***)(__int64, __int64))v80)(v80, 1);
        }
        if ( v103 && v102 != -1 && v102 && v102 == 2 )
          std::wstring::~wstring(v101);
      }
      goto LABEL_140;
    }
    goto LABEL_132;
  }
  v100 = off_1403CFD30;
  v104 = &v100;
  Monitor<std::pair<bool,bool>>::send_change(v4, &v100);
  if ( !v110 )
    std::_Throw_bad_optional_access();
  if ( v109 )
    std::_Throw_bad_variant_access();
  if ( !v108[0] )
  {
    v58 = (_QWORD *)SystemInterface::Service::GetSystem(&v89);
    v59 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v58 + 32LL))(*v58, &v93);
    v60 = *(_QWORD *)v59;
    v61 = *(void (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v59 + 80LL);
    v62 = -1;
    do
      ++v62;
    while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v62] );
    *(_QWORD *)&v87 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
    *((_QWORD *)&v87 + 1) = v62;
    v63 = -1;
    do
      ++v63;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v63] );
    *(_QWORD *)&v88 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v88 + 1) = v63;
    *(_QWORD *)&v92 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v64 = -1;
    do
      ++v64;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v64] );
    *((_QWORD *)&v92 + 1) = v64;
    v97 = v87;
    v94 = v88;
    v96 = v92;
    v61(v60, &v96, &v94, &v97);
    v65 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
    if ( *((_QWORD *)&v93 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
        if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
      }
    }
    v66 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
    if ( *((_QWORD *)&v89 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
        if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
      }
    }
    v67 = (_QWORD *)SystemInterface::Service::GetSystem(&v89);
    v68 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v67 + 32LL))(*v67, &v93);
    v69 = *(_QWORD *)v68;
    v70 = *(void (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v68 + 80LL);
    v71 = -1;
    do
      ++v71;
    while ( SystemInterface::Registry::ISCURRENTREBOOTFEATURE[v71] );
    *(_QWORD *)&v87 = SystemInterface::Registry::ISCURRENTREBOOTFEATURE;
    *((_QWORD *)&v87 + 1) = v71;
    v72 = -1;
    do
      ++v72;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v72] );
    *(_QWORD *)&v88 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v88 + 1) = v72;
    *(_QWORD *)&v92 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v73 = -1;
    do
      ++v73;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v73] );
    *((_QWORD *)&v92 + 1) = v73;
    v97 = v87;
    v94 = v88;
    v96 = v92;
    v70(v69, &v96, &v94, &v97);
    v74 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
    if ( *((_QWORD *)&v93 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
      }
    }
    v57 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
    goto LABEL_104;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AppNotifications>::GetImpl'::`2'::impl) )
  {
    v90 = 0;
    GetSystemTimePreciseAsFileTime(&v90);
    *(_QWORD *)&v88 = ((unsigned __int64)HIDWORD(v90) << 32) - 116444736000000000LL + (unsigned int)v90;
    if ( !*(_BYTE *)(v5 + 72) )
    {
      std::logic_error::logic_error((std::logic_error *)pExceptionObject, "os updates context is missing");
      throw (std::logic_error *)pExceptionObject;
    }
    UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(v6, v5 + 56, &v88);
    v90 = 0;
    GetSystemTimePreciseAsFileTime(&v90);
    *(_QWORD *)&v88 = ((unsigned __int64)HIDWORD(v90) << 32) - 116444736000000000LL + (unsigned int)v90;
    v25 = UX::ConditionContext::AppUpdates(v5);
    UX::Broker::SetUpdateRebootRecognitionTimeForUpdateList(v6, v25, &v88);
  }
  else
  {
    if ( !*(_BYTE *)(v5 + 72) )
    {
      std::logic_error::logic_error((std::logic_error *)v107, "os updates context is missing");
      throw (std::logic_error *)v107;
    }
    v26 = *(_QWORD **)(v5 + 56);
    for ( i = (_QWORD *)*v26; i != v26; i = (_QWORD *)*i )
    {
      if ( !*(_BYTE *)(UpdateDatabase::GetUpdateRebootRecognitionTime(*((_QWORD *)v6 + 53), &v97, i[2]) + 8) )
      {
        UpdateDatabase::GetUpdateBlock(*((_QWORD *)v6 + 53), &v94, i[2]);
        if ( v95 )
        {
          if ( (_DWORD)v94 == 1 )
          {
            v28 = *((_QWORD *)v6 + 53);
            v90 = 0;
            GetSystemTimePreciseAsFileTime(&v90);
            *(_QWORD *)&v88 = ((unsigned __int64)HIDWORD(v90) << 32) - 116444736000000000LL + (unsigned int)v90;
            UpdateDatabase::SetUpdateRebootRecognitionTime(v28, i[2], &v88);
          }
        }
      }
    }
    LODWORD(v5) = v89;
  }
  v29 = (_QWORD *)SystemInterface::Service::GetSystem(&v90);
  v30 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*v29 + 32LL))(*v29, &v89);
  v31 = *(_QWORD *)v30;
  v32 = *(__int64 (__fastcall **)(__int64, unsigned __int128 *, unsigned __int128 *, unsigned __int128 *))(**(_QWORD **)v30 + 32LL);
  v33 = -1;
  do
    ++v33;
  while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v33] );
  *(_QWORD *)&v87 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
  *((_QWORD *)&v87 + 1) = v33;
  v34 = -1;
  do
    ++v34;
  while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v34] );
  *(_QWORD *)&v88 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
  *((_QWORD *)&v88 + 1) = v34;
  *(_QWORD *)&v92 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
  v35 = -1;
  do
    ++v35;
  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v35] );
  *((_QWORD *)&v92 + 1) = v35;
  v94 = v87;
  v96 = v88;
  v87 = v92;
  v36 = v32(v31, &v87, &v96, &v94);
  v37 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
  if ( *((_QWORD *)&v89 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
      if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
    }
  }
  v38 = v91;
  if ( v91 )
  {
    if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
  }
  if ( !v36 )
  {
    v39 = (_QWORD *)SystemInterface::Service::GetSystem(&v97);
    v40 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, UX::Broker **))(*(_QWORD *)*v39 + 32LL))(*v39, &v90);
    *(_QWORD *)&v89 = 0;
    GetSystemTimePreciseAsFileTime(&v89);
    *(_QWORD *)&v88 = ((unsigned __int64)DWORD1(v89) << 32) - 116444736000000000LL + (unsigned int)v89;
    v41 = -1;
    do
      ++v41;
    while ( SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME[v41] );
    *(_QWORD *)&v87 = SystemInterface::Registry::CURRENTREBOOTRECOGNITIONTIME;
    *((_QWORD *)&v87 + 1) = v41;
    v42 = -1;
    do
      ++v42;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v42] );
    *(_QWORD *)&v92 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v92 + 1) = v42;
    *(_QWORD *)&v89 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v43 = -1;
    do
      ++v43;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v43] );
    *((_QWORD *)&v89 + 1) = v43;
    v94 = v87;
    v96 = v92;
    v87 = v89;
    SystemInterface::Registry::SetSystemTime(
      v40,
      (unsigned int)&v87,
      (unsigned int)&v96,
      (unsigned int)&v94,
      (__int64)&v88);
    v44 = v91;
    if ( v91 )
    {
      if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
        if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
      }
    }
    v45 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
    if ( *((_QWORD *)&v97 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    v46 = (_QWORD *)SystemInterface::Service::GetSystem(&v90);
    v47 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int128 *))(*(_QWORD *)*v46 + 32LL))(*v46, &v89);
    v86[0] = 0;
    v48 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"Feature update pending reboot",
                   &dword_1404257DC,
                   0);
    if ( v48 == &dword_1404257DC || (v51 = ((char *)v48 - (char *)L"Feature update pending reboot") >> 1, v51 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v49);
    *(_QWORD *)&v87 = L"Feature update pending reboot";
    *((_QWORD *)&v87 + 1) = v51;
    v97 = v87;
    v52 = DecisionEngine<UX::ConditionContext>::QueryOrDefault<bool>(v50, (unsigned int)&v97, v5, (unsigned int)v86, 1);
    v53 = -1;
    do
      ++v53;
    while ( SystemInterface::Registry::ISCURRENTREBOOTFEATURE[v53] );
    v87 = __PAIR128__(v53, (unsigned __int64)SystemInterface::Registry::ISCURRENTREBOOTFEATURE);
    v54 = -1;
    do
      ++v54;
    while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v54] );
    *(_QWORD *)&v88 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
    *((_QWORD *)&v88 + 1) = v54;
    *(_QWORD *)&v92 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
    v55 = -1;
    do
      ++v55;
    while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v55] );
    *((_QWORD *)&v92 + 1) = v55;
    v97 = v87;
    v94 = v88;
    v96 = v92;
    SystemInterface::Registry::SetSystemBool(v47, (unsigned int)&v96, (unsigned int)&v94, (unsigned int)&v97, v52);
    v56 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
    if ( *((_QWORD *)&v89 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    v57 = v91;
LABEL_104:
    if ( v57 )
    {
      if ( _InterlockedExchangeAdd(v57 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
        if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
      }
    }
  }
LABEL_140:
  if ( v110 && v109 != -1 && v109 && v109 == 2 )
    std::wstring::~wstring(v108);
  std::wostringstream::~wostringstream(&v111[17]);
  v111[17] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v111[17]);
  v85 = *(volatile signed __int32 **)(v99 + 8);
  if ( v85 )
  {
    if ( !_InterlockedDecrement(v85 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 8LL))(v85);
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
