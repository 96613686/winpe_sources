# CScenarioCtrlDesktopCBS::StageOrInstallRoutine(uint,uint,wchar_t const *,int *)

- ea: `0x18009238c`
- end: `0x180092c90`
- name: `?StageOrInstallRoutine@CScenarioCtrlDesktopCBS@@QEAAJIIPEB_WPEAH@Z`
- size: `2308`
- prototype: `__int64 __usercall@<rax>(CScenarioCtrlDesktopCBS *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const wchar_t *@<r9>, int *)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180073640`
- `0x180092ca0`
- `0x180092d10`

## callees

- `0x1800059d0`
- `0x180008960`
- `0x1800096e8`
- `0x180009770`
- `0x18000a0e8`
- `0x18000a7fc`
- `0x18000c4c4`
- `0x1800125bc`
- `0x18001270c`
- `0x180028054`
- `0x180039f90`
- `0x180077664`
- `0x180078b9c`
- `0x18008b38c`
- `0x18009032c`
- `0x18009238c`
- `0x18009ad18`
- `0x18009b1cc`
- `0x18009d348`
- `0x18009eb7c`
- `0x1800a57c0`
- `0x1800acd88`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092bd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092bd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092be6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800928b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092a96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800928b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092a96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092c23`

## string_xrefs

- `0x18009277d`: `UpdateAgentLCU`
- `0x180092c7e`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x1800925f9`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlDesktopCBS.h`
- `0x180092652`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlDesktopCBS.h`
- `0x180092c3f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlDesktopCBS.h`
- `0x180092488`: `An unsupported UpdatePriority was set to UpdateAgent. Will run with Default priority`
- `0x180092837`: `ServicingProcessor succeeded in installing the SSU.`
- `0x180092856`: `ServicingProcessor succeeded in installing the SSU. Creating a new session to install the rest of the packages.`
- `0x180092882`: `ServicingProcessor succeeded in installing the SSU within the MuV6 path. Skipping non-SSU package(s) install and will resume when the stack restarts. Returning CBS_E_MUV6_STACK_SHUTDOWN_NEEDED.`
- `0x180092a65`: `ICbsServicingProcessor->Process failed to stage the non-SSU packages because a postponed reserve install was considered.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CScenarioCtrlDesktopCBS::StageOrInstallRoutine(
        CScenarioCtrlDesktopCBS *this,
        char a2,
        __int64 a3,
        const wchar_t *a4,
        int *a5)
{
  const wchar_t *v5; // r10
  char v8; // r15
  unsigned int v9; // r13d
  unsigned __int8 v10; // r14
  int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int ActionList; // eax
  __int64 v15; // rdx
  int v16; // esi
  void (__fastcall ***v17)(_QWORD); // rdi
  __int64 v18; // rcx
  int updated; // eax
  char v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  char v33; // r12
  __int64 v34; // rax
  unsigned __int64 v35; // rcx
  unsigned int v36; // r9d
  unsigned int v37; // eax
  int v38; // eax
  const char *v39; // rcx
  unsigned int v40; // edx
  unsigned int v41; // r8d
  int v42; // eax
  __int64 traits_2_0_unsigned_short; // rax
  const char *v44; // r9
  __int64 v45; // r11
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  unsigned __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rcx
  const wchar_t *v59; // r9
  LPVOID v60; // rdx
  __int64 sstring; // rax
  __int64 v62; // rbx
  HANDLE ProcessHeap; // rax
  int *v64; // [rsp+28h] [rbp-A1h]
  wchar_t v65[4]; // [rsp+38h] [rbp-91h] BYREF
  int v66[2]; // [rsp+40h] [rbp-89h] BYREF
  CScenarioCtrlDesktopCBS *v67; // [rsp+48h] [rbp-81h] BYREF
  const wchar_t **v68; // [rsp+50h] [rbp-79h]
  const wchar_t **v69; // [rsp+58h] [rbp-71h]
  int *v70; // [rsp+60h] [rbp-69h]
  int *v71; // [rsp+68h] [rbp-61h]
  int *v72; // [rsp+70h] [rbp-59h]
  LPVOID *p_pv; // [rsp+78h] [rbp-51h]
  LPVOID *v74; // [rsp+80h] [rbp-49h]
  unsigned __int64 *v75; // [rsp+88h] [rbp-41h]
  __int64 v76; // [rsp+90h] [rbp-39h]
  char v77; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v78[3]; // [rsp+99h] [rbp-30h] BYREF
  int v79; // [rsp+9Ch] [rbp-2Dh] BYREF
  int v80; // [rsp+A0h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v82; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-11h] BYREF
  int v84; // [rsp+C0h] [rbp-9h] BYREF
  int v85; // [rsp+C4h] [rbp-5h] BYREF
  _QWORD v86[2]; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+57h]
  const wchar_t *v88; // [rsp+140h] [rbp+77h] BYREF

  v88 = a4;
  v76 = -2;
  v5 = a4;
  *(_QWORD *)v66 = a5;
  v8 = 0;
  if ( !a4 || !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
      (const char *)0x80004003LL,
      (int)v64);
    return 2147500035LL;
  }
  v79 = a3;
  *((_BYTE *)this + 84) = 0;
  v78[0] = (a3 & 0x1000) != 0;
  v82 = 0;
  v9 = 100;
  v10 = 1;
  if ( (a3 & 0x1000) != 0 )
  {
    *((_DWORD *)this + 65) = 0;
  }
  else if ( (a3 & 0x400) != 0 )
  {
    *((_DWORD *)this + 65) = 1;
    v82 = 70;
  }
  else
  {
    *((_DWORD *)this + 65) = 2;
    v82 = 100;
  }
  pv = 0;
  v84 = 0;
  v85 = 0;
  v11 = *((_DWORD *)this + 6);
  switch ( v11 )
  {
    case 4:
    case 22:
      a3 = (unsigned int)a3 | 0xF;
      break;
    case 6:
      a3 = (unsigned int)a3 | 9;
      break;
    case 25:
      a3 = (unsigned int)a3 | 0xD;
      break;
    default:
      goto LABEL_16;
  }
  v79 = a3;
LABEL_16:
  v12 = *((_DWORD *)this + 64);
  if ( !v12 )
    goto LABEL_23;
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
    {
      LogAdapter::TraceError<>("An unsupported UpdatePriority was set to UpdateAgent. Will run with Default priority");
      v5 = v88;
      goto LABEL_23;
    }
    LODWORD(a3) = a3 | 0x200;
  }
  else
  {
    LODWORD(a3) = a3 | 0x100;
  }
  v79 = a3;
LABEL_23:
  v77 = 0;
  *(_QWORD *)v65 = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  ActionList = LoadActionList(0, v5, a3, v65);
  v16 = ActionList;
  v17 = *(void (__fastcall ****)(_QWORD))v65;
  if ( ActionList >= 0 )
  {
    v20 = 0;
    v21 = *(_QWORD *)(*(_QWORD *)v65 + 88LL);
    v22 = v21 + 168LL * *(unsigned int *)(*(_QWORD *)v65 + 96LL);
    while ( 1 )
    {
      if ( v21 == v22 )
      {
        v77 = v20;
        goto LABEL_49;
      }
      v23 = *(_DWORD *)(v21 + 88);
      if ( v23 == 7 )
      {
        v20 = 1;
        *((_QWORD *)this + 35) = *(_QWORD *)(v21 + 8);
        goto LABEL_46;
      }
      v24 = v23 - 2;
      if ( !v24 )
        break;
      v25 = v24 - 1;
      if ( !v25 )
        break;
      v26 = v25 - 1;
      if ( !v26 )
        break;
      v27 = v26 - 1;
      if ( !v27 )
        break;
      v28 = v27 - 1;
      if ( !v28 )
        break;
      v29 = v28 - 1;
      if ( !v29 )
        break;
      v30 = v29 - 2;
      if ( !v30 )
        break;
      v31 = v30 - 2;
      if ( v31 )
      {
        if ( v31 == 2 )
          break;
      }
      else if ( *((_DWORD *)this + 6) == 25 || *(_DWORD *)(v21 + 96) == 4 )
      {
        break;
      }
LABEL_46:
      v21 += 168;
    }
    v8 = 1;
    *((_QWORD *)this + 36) += *(_QWORD *)(v21 + 8);
    goto LABEL_46;
  }
  v80 = ActionList;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v15) = 1;
    LogAdapter::Logger::LogNumObjects<long>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v15,
      3,
      "Failed to load actionlist, hr = {}",
      &v80);
  }
  v18 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    LODWORD(v64) = 961;
    updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                *((_QWORD *)this + 4),
                4,
                L"%s(%d): Result = 0x%X",
                L"CScenarioCtrlDesktopCBS::EvaluateActionList");
    v18 = (unsigned int)updated;
    if ( updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
LABEL_49:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v16);
  if ( v17 )
    (**v17)(v17);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
      (const char *)(unsigned int)v16,
      (int)v64);
LABEL_53:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v16;
  }
  v33 = a2 & 1;
  if ( !v77 && v33 )
  {
    LogAdapter::TraceInfo<>("Only SSU operations were requested, but the actionlist does not contain an SSU.");
    **(_DWORD **)v66 = 0;
LABEL_145:
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  if ( v77 && v8 )
  {
    v34 = *((_QWORD *)this + 35);
    if ( !v34 )
    {
      if ( *((_QWORD *)this + 36) )
      {
        v34 = 0;
      }
      else
      {
        v34 = 5;
        *((_QWORD *)this + 35) = 5;
        *((_QWORD *)this + 36) = 95;
      }
    }
    v35 = *((_QWORD *)this + 33);
    v36 = *((_DWORD *)this + 77);
    if ( v82 >= v35 )
      v37 = v36 + v34 * (v82 - v35) / (v34 + *((_QWORD *)this + 36));
    else
      v37 = *((_DWORD *)this + 77);
    v38 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, v36, v37);
    if ( v38 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v38,
        (int)v64);
    v39 = "Both SSU and non-SSU package(s) are present, but only performing SSU operations.";
    if ( !v33 )
      v39 = "Both SSU and non-SSU package(s) are present. Performing any applicable operations for all.";
    LogAdapter::TraceInfo<>(v39);
  }
  else
  {
    LogAdapter::TraceInfo<>("Actionlist does not have both an SSU and non-SSU package(s).");
    v40 = *((_DWORD *)this + 77);
    if ( v82 >= *((_QWORD *)this + 34) + *((_QWORD *)this + 33) )
      v41 = v40 + v82 - *((_DWORD *)this + 66) - *((_DWORD *)this + 68);
    else
      v41 = *((_DWORD *)this + 77);
    v42 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, v40, v41);
    if ( v42 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v42,
        (int)v64);
  }
  traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                L"UpdateAgentLCU",
                                &unk_1802D0DCE,
                                0);
  if ( traits_2_0_unsigned_short == v46 || (v47 = (traits_2_0_unsigned_short - v45) >> 1, v47 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
      v44);
  v86[0] = v45;
  v86[1] = v47;
  wil::CoCreateInstance<IContextCallback,wil::err_exception_policy>(&v83);
  if ( v77 )
  {
    v67 = this;
    v68 = &v88;
    v69 = (const wchar_t **)v78;
    v70 = &v79;
    v71 = (int *)v86;
    v72 = &v84;
    p_pv = &pv;
    v74 = (LPVOID *)&v82;
    LOBYTE(v48) = *((_BYTE *)this + 128);
    v16 = ___InvokeInContext_V_lambda_1___EH___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__UpdateAgentMisc__YAJPEAUIContextCallback____QEAV_lambda_1___EH___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__N_Z(
            v83,
            &v67,
            v48);
    if ( v16 == -2145116147 )
    {
      if ( v8 )
      {
        v49 = *((_QWORD *)this + 4);
        if ( v33 )
        {
          if ( v49 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v49, 2, L"ServicingProcessor succeeded in installing the SSU.");
          goto LABEL_130;
        }
        if ( v49 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v49,
            2,
            L"ServicingProcessor succeeded in installing the SSU. Creating a new session to install the rest of the packages.");
        goto LABEL_107;
      }
LABEL_98:
      v80 = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "ICbsServicingProcessor->Process for the SSU failed");
        *(_QWORD *)v66 = &v80;
        v64 = v66;
        LOBYTE(v51) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v51,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v16,
        (int)v64);
      if ( v83 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      goto LABEL_53;
    }
    if ( v16 == -2146498506 )
    {
      if ( v8 )
      {
        v50 = *((_QWORD *)this + 4);
        if ( v50 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v50,
            2,
            L"ServicingProcessor succeeded in installing the SSU within the MuV6 path. Skipping non-SSU package(s) install"
             " and will resume when the stack restarts. Returning CBS_E_MUV6_STACK_SHUTDOWN_NEEDED.");
        if ( v83 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        if ( pv )
          CoTaskMemFree(pv);
        return 2148468790LL;
      }
      goto LABEL_98;
    }
    if ( v16 < 0 )
      goto LABEL_98;
    v52 = *((_QWORD *)this + 4);
    if ( v52 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v52,
        2,
        L"ServicingProcessor for the SSU succeeded and returned this Session ID: [%s]",
        pv);
  }
  if ( !v8 || v33 )
    goto LABEL_130;
LABEL_107:
  if ( v77 )
  {
    v53 = *((_QWORD *)this + 34);
    if ( v82 >= v53 )
    {
      if ( v82 != 100 )
        v9 = *((_DWORD *)this + 77)
           + *((_QWORD *)this + 36) * (v82 - v53) / (*((_QWORD *)this + 36) + *((_QWORD *)this + 35));
    }
    else
    {
      v9 = *((_DWORD *)this + 77);
    }
    v54 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, *((_DWORD *)this + 77), v9);
    if ( v54 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v54,
        (int)v64);
  }
  v67 = this;
  v68 = (const wchar_t **)&v77;
  v69 = &v88;
  v70 = (int *)v78;
  v71 = &v79;
  v72 = (int *)v86;
  p_pv = (LPVOID *)&v85;
  v74 = &pv;
  v75 = &v82;
  LOBYTE(v48) = *((_BYTE *)this + 128);
  v16 = ___InvokeInContext_V_lambda_2___HA___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__UpdateAgentMisc__YAJPEAUIContextCallback____QEAV_lambda_2___HA___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__N_Z(
          v83,
          &v67,
          v48);
  if ( v16 != -2146498505 )
  {
    if ( v16 < 0 )
    {
      v80 = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "ICbsServicingProcessor->Process for the non-SSU packages failed");
        *(_QWORD *)v66 = &v80;
        v64 = v66;
        LOBYTE(v56) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v56,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v16,
        (int)v64);
      if ( v83 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      goto LABEL_53;
    }
    v57 = *((_QWORD *)this + 4);
    if ( v57 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v57,
        2,
        L"ServicingProcessor for the non-SSU packages succeeded and returned this Session ID: [%s]",
        pv);
LABEL_130:
    if ( v84 != 1 && v85 != 1 )
      v10 = 0;
    v58 = *((_QWORD *)this + 4);
    if ( v58 )
    {
      v59 = L"TRUE";
      if ( !v10 )
        v59 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v58, 2, L"Reboot required: [%ls]", v59);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl) )
    {
      if ( !pv )
      {
LABEL_143:
        **(_DWORD **)v66 = v10;
        if ( v83 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
        goto LABEL_145;
      }
      v60 = pv;
    }
    else
    {
      v60 = pv;
    }
    sstring = make_sstring(v65, (unsigned __int64)v60);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      (char *)this + 72,
      sstring);
    v62 = *(_QWORD *)v65;
    if ( *(_QWORD *)v65 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v62 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    goto LABEL_143;
  }
  v55 = *((_QWORD *)this + 4);
  if ( v55 )
    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
      v55,
      2,
      L"ICbsServicingProcessor->Process failed to stage the non-SSU packages because a postponed reserve install was considered.");
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( pv )
    CoTaskMemFree(pv);
  return 2148468791LL;
}

```

## disassembly

```asm
0x18009238c  mov     rax, rsp
0x18009238f  mov     [rax+20h], r9
0x180092393  push    rbp
0x180092394  push    rsi
0x180092395  push    rdi
0x180092396  push    r12
0x180092398  push    r13
0x18009239a  push    r14
0x18009239c  push    r15
0x18009239e  lea     rbp, [rax-57h]
0x1800923a2  sub     rsp, 0E0h
0x1800923a9  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x1800923b1  mov     [rax+10h], rbx
0x1800923b5  mov     rax, cs:__security_cookie
0x1800923bc  xor     rax, rsp
0x1800923bf  mov     [rbp+4Fh+var_40], rax
0x1800923c3  mov     r10, r9
0x1800923c6  mov     r12d, edx
0x1800923c9  mov     rbx, rcx
0x1800923cc  mov     rax, [rbp+4Fh+arg_20]
0x1800923d0  mov     qword ptr [rsp+110h+var_D8], rax
0x1800923d5  xor     r15d, r15d
0x1800923d8  test    r9, r9
0x1800923db  jz      loc_180092C33
0x1800923e1  test    rax, rax
0x1800923e4  jz      loc_180092C33
0x1800923ea  mov     [rbp+4Fh+var_7C], r8d
0x1800923ee  mov     [rcx+54h], r15b
0x1800923f2  bt      r8d, 0Ch
0x1800923f7  setb    [rbp+4Fh+var_7F]
0x1800923fb  mov     [rbp+4Fh+var_68], r15
0x1800923ff  lea     r13d, [r15+64h]
0x180092403  lea     r14d, [r15+1]
0x180092407  bt      r8d, 0Ch
0x18009240c  jnb     short loc_180092417
0x18009240e  mov     [rcx+104h], r15d
0x180092415  jmp     short loc_18009243D
0x180092417  bt      r8d, 0Ah
0x18009241c  jnb     short loc_18009242F
0x18009241e  mov     [rcx+104h], r14d
0x180092425  mov     [rbp+4Fh+var_68], 46h ; 'F'
0x18009242d  jmp     short loc_18009243D
0x18009242f  mov     dword ptr [rcx+104h], 2
0x180092439  mov     [rbp+4Fh+var_68], r13
0x18009243d  mov     [rbp+4Fh+pv], r15
0x180092441  mov     [rbp+4Fh+var_58], r15d
0x180092445  mov     [rbp+4Fh+var_54], r15d
0x180092449  mov     eax, [rcx+18h]
0x18009244c  cmp     eax, 4
0x18009244f  jz      short loc_18009246C
0x180092451  cmp     eax, 16h
0x180092454  jz      short loc_18009246C
0x180092456  cmp     eax, 6
0x180092459  jnz     short loc_180092461
0x18009245b  or      r8d, 9
0x18009245f  jmp     short loc_180092470
0x180092461  cmp     eax, 19h
0x180092464  jnz     short loc_180092474
0x180092466  or      r8d, 0Dh
0x18009246a  jmp     short loc_180092470
0x18009246c  or      r8d, 0Fh
0x180092470  mov     [rbp+4Fh+var_7C], r8d
0x180092474  mov     ecx, [rcx+100h]
0x18009247a  test    ecx, ecx
0x18009247c  jz      short loc_1800924AA
0x18009247e  sub     ecx, 1
0x180092481  jz      short loc_1800924A1
0x180092483  cmp     ecx, 1
0x180092486  jz      short loc_18009249A
0x180092488  lea     rcx, aAnUnsupportedU; "An unsupported UpdatePriority was set t"...
0x18009248f  call    ??$TraceError@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceError<>(char const * const)
0x180092494  mov     r10, [rbp+4Fh+arg_18]
0x180092498  jmp     short loc_1800924AA
0x18009249a  bts     r8d, 9
0x18009249f  jmp     short loc_1800924A6
0x1800924a1  bts     r8d, 8
0x1800924a6  mov     [rbp+4Fh+var_7C], r8d
0x1800924aa  mov     [rbp+4Fh+var_80], r15b
0x1800924ae  mov     qword ptr [rsp+110h+var_E0], r15
0x1800924b3  mov     [rbx+118h], r15
0x1800924ba  mov     [rbx+120h], r15
0x1800924c1  lea     r9, [rsp+110h+var_E0]
0x1800924c6  mov     rdx, r10
0x1800924c9  xor     ecx, ecx
0x1800924cb  call    LoadActionList
0x1800924d0  mov     esi, eax
0x1800924d2  mov     rdi, qword ptr [rsp+110h+var_E0]
0x1800924d7  test    eax, eax
0x1800924d9  jns     short loc_18009254B
0x1800924db  mov     [rbp+4Fh+var_78], eax
0x1800924de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800924e5  test    rcx, rcx
0x1800924e8  jz      short loc_180092508
0x1800924ea  lea     rax, [rbp+4Fh+var_78]
0x1800924ee  mov     [rsp+110h+var_F0], rax
0x1800924f3  lea     r9, aFailedToLoadAc_4; "Failed to load actionlist, hr = {}"
0x1800924fa  mov     r8d, 3
0x180092500  mov     dl, r14b
0x180092503  call    ??$LogNumObjects@J@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBJ@Z; LogAdapter::Logger::LogNumObjects<long>(bool,LogAdapter::LogLevel,char const * const,long const &)
0x180092508  xor     ecx, ecx
0x18009250a  cmp     [rbx+20h], rcx
0x18009250e  jz      short loc_180092541
0x180092510  mov     dword ptr [rsp+110h+var_E8], esi
0x180092514  mov     dword ptr [rsp+110h+var_F0], 3C1h
0x18009251c  lea     r9, aCscenarioctrld; "CScenarioCtrlDesktopCBS::EvaluateAction"...
0x180092523  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18009252a  lea     edx, [rcx+4]
0x18009252d  mov     rcx, [rbx+20h]
0x180092531  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180092536  mov     ecx, eax
0x180092538  test    eax, eax
0x18009253a  jns     short loc_180092541
0x18009253c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180092541  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180092546  jmp     loc_1800925D2
0x18009254b  mov     r9b, r15b
0x18009254e  mov     rdx, [rdi+58h]
0x180092552  mov     eax, [rdi+60h]
0x180092555  imul    r8, rax, 0A8h
0x18009255c  add     r8, rdx
0x18009255f  jmp     short loc_1800925C9
0x180092561  mov     ecx, [rdx+58h]
0x180092564  cmp     ecx, 7
0x180092567  jnz     short loc_180092579
0x180092569  mov     r9b, r14b
0x18009256c  mov     rax, [rdx+8]
0x180092570  mov     [rbx+118h], rax
0x180092577  jmp     short loc_1800925C2
0x180092579  sub     ecx, 2
0x18009257c  jz      short loc_1800925B4
0x18009257e  sub     ecx, 1
0x180092581  jz      short loc_1800925B4
0x180092583  sub     ecx, 1
0x180092586  jz      short loc_1800925B4
0x180092588  sub     ecx, 1
0x18009258b  jz      short loc_1800925B4
0x18009258d  sub     ecx, 1
0x180092590  jz      short loc_1800925B4
0x180092592  sub     ecx, 1
0x180092595  jz      short loc_1800925B4
0x180092597  sub     ecx, 2
0x18009259a  jz      short loc_1800925B4
0x18009259c  sub     ecx, 2
0x18009259f  jz      short loc_1800925A8
0x1800925a1  cmp     ecx, 2
0x1800925a4  jz      short loc_1800925B4
0x1800925a6  jmp     short loc_1800925C2
0x1800925a8  cmp     dword ptr [rbx+18h], 19h
0x1800925ac  jz      short loc_1800925B4
0x1800925ae  cmp     dword ptr [rdx+60h], 4
0x1800925b2  jnz     short loc_1800925C2
0x1800925b4  mov     r15b, r14b
0x1800925b7  mov     rax, [rdx+8]
0x1800925bb  add     [rbx+120h], rax
0x1800925c2  add     rdx, 0A8h
0x1800925c9  cmp     rdx, r8
0x1800925cc  jnz     short loc_180092561
0x1800925ce  mov     [rbp+4Fh+var_80], r9b
0x1800925d2  mov     ecx, esi
0x1800925d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800925d9  nop
0x1800925da  test    rdi, rdi
0x1800925dd  jz      short loc_1800925EE
0x1800925df  mov     rax, [rdi]
0x1800925e2  mov     rcx, rdi
0x1800925e5  mov     rax, [rax]
0x1800925e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925ed  nop
0x1800925ee  test    esi, esi
0x1800925f0  jns     short loc_180092627
0x1800925f2  mov     rcx, [rbp+57h]; this
0x1800925f6  mov     r9d, esi; char *
0x1800925f9  lea     r8, aOnecoreBaseNts_22; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180092600  mov     edx, 0DCh; void *
0x180092605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009260a  nop
0x18009260b  mov     rcx, [rbp+4Fh+pv]; pv
0x18009260f  test    rcx, rcx
0x180092612  jz      short loc_180092620
0x180092614  call    cs:__imp_CoTaskMemFree
0x18009261b  nop     dword ptr [rax+rax+00h]
0x180092620  mov     eax, esi
0x180092622  jmp     loc_180092C52
0x180092627  and     r12b, r14b
0x18009262a  mov     al, [rbp+4Fh+var_80]
0x18009262d  test    al, al
0x18009262f  jnz     short loc_180092652
0x180092631  test    r12b, r12b
0x180092634  jz      short loc_180092652
0x180092636  lea     rcx, aOnlySsuOperati; "Only SSU operations were requested, but"...
0x18009263d  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180092642  mov     rcx, qword ptr [rsp+110h+var_D8]
0x180092647  mov     dword ptr [rcx], 0
0x18009264d  jmp     loc_180092C1A
0x180092652  lea     rdi, aOnecoreBaseNts_22; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180092659  test    al, al
0x18009265b  jz      loc_180092714
0x180092661  test    r15b, r15b
0x180092664  jz      loc_180092714
0x18009266a  mov     rax, [rbx+118h]
0x180092671  test    rax, rax
0x180092674  jnz     short loc_18009269A
0x180092676  cmp     [rbx+120h], rax
0x18009267d  jnz     short loc_180092698
0x18009267f  mov     eax, 5
0x180092684  mov     [rbx+118h], rax
0x18009268b  mov     qword ptr [rbx+120h], 5Fh ; '_'
0x180092696  jmp     short loc_18009269A
0x180092698  xor     eax, eax
0x18009269a  mov     rcx, [rbx+108h]
0x1800926a1  mov     r9d, [rbx+134h]
0x1800926a8  mov     r8, [rbp+4Fh+var_68]
0x1800926ac  cmp     r8, rcx
0x1800926af  jnb     short loc_1800926B6
0x1800926b1  mov     eax, r9d
0x1800926b4  jmp     short loc_1800926D2
0x1800926b6  sub     r8, rcx
0x1800926b9  imul    r8, rax
0x1800926bd  mov     rcx, [rbx+120h]
0x1800926c4  add     rcx, rax
0x1800926c7  xor     edx, edx
0x1800926c9  mov     rax, r8
0x1800926cc  div     rcx
0x1800926cf  add     eax, r9d
0x1800926d2  mov     r8d, eax; unsigned int
0x1800926d5  mov     edx, r9d; unsigned int
0x1800926d8  mov     rcx, rbx; this
0x1800926db  call    ?SetInternalProgressRange@CScenarioCtrlDesktopCBS@@QEAAJKK@Z; CScenarioCtrlDesktopCBS::SetInternalProgressRange(ulong,ulong)
0x1800926e0  mov     rcx, [rbp+57h]; this
0x1800926e4  test    eax, eax
0x1800926e6  jns     short loc_1800926F8
0x1800926e8  mov     r9d, eax; char *
0x1800926eb  mov     r8, rdi; unsigned int
0x1800926ee  mov     edx, 0FDh; void *
0x1800926f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800926f8  lea     rax, aBothSsuAndNonS; "Both SSU and non-SSU package(s) are pre"...
0x1800926ff  lea     rcx, aBothSsuAndNonS_0; "Both SSU and non-SSU package(s) are pre"...
0x180092706  test    r12b, r12b
0x180092709  cmovz   rcx, rax
0x18009270d  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180092712  jmp     short loc_180092773
0x180092714  lea     rcx, aActionlistDoes; "Actionlist does not have both an SSU an"...
0x18009271b  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180092720  mov     edx, [rbx+134h]; unsigned int
0x180092726  mov     rax, [rbx+108h]
0x18009272d  add     rax, [rbx+110h]
0x180092734  mov     r8, [rbp+4Fh+var_68]
0x180092738  cmp     r8, rax
0x18009273b  jnb     short loc_180092742
0x18009273d  mov     r8d, edx
0x180092740  jmp     short loc_180092753
0x180092742  sub     r8d, [rbx+108h]
0x180092749  sub     r8d, [rbx+110h]
0x180092750  add     r8d, edx; unsigned int
0x180092753  mov     rcx, rbx; this
0x180092756  call    ?SetInternalProgressRange@CScenarioCtrlDesktopCBS@@QEAAJKK@Z; CScenarioCtrlDesktopCBS::SetInternalProgressRange(ulong,ulong)
0x18009275b  mov     rcx, [rbp+57h]; this
0x18009275f  test    eax, eax
0x180092761  jns     short loc_180092773
0x180092763  mov     r9d, eax; char *
0x180092766  mov     r8, rdi; unsigned int
0x180092769  mov     edx, 119h; void *
0x18009276e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092773  xor     r8d, r8d
0x180092776  lea     rdx, unk_1802D0DCE
0x18009277d  lea     r11, aUpdateagentlcu; "UpdateAgentLCU"
0x180092784  mov     rcx, r11
0x180092787  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x18009278c  cmp     rax, rdx
0x18009278f  jz      loc_180092C7A
0x180092795  sub     rax, r11
0x180092798  sar     rax, 1
0x18009279b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009279f  jz      loc_180092C7A
0x1800927a5  mov     [rbp+4Fh+var_50], r11
0x1800927a9  mov     [rbp+4Fh+var_48], rax
0x1800927ad  lea     rcx, [rbp+4Fh+var_60]
0x1800927b1  call    ??$CoCreateInstance@UIContextCallback@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIContextCallback@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IContextCallback,wil::err_exception_policy>(_GUID const &,ulong)
0x1800927b6  nop
0x1800927b7  cmp     [rbp+4Fh+var_80], 0
0x1800927bb  jz      loc_180092970
0x1800927c1  mov     [rsp+110h+var_D0], rbx
0x1800927c6  lea     rax, [rbp+4Fh+arg_18]
0x1800927ca  mov     [rbp+4Fh+var_C8], rax
0x1800927ce  lea     rax, [rbp+4Fh+var_7F]
0x1800927d2  mov     [rbp+4Fh+var_C0], rax
0x1800927d6  lea     rax, [rbp+4Fh+var_7C]
0x1800927da  mov     [rbp+4Fh+var_B8], rax
0x1800927de  lea     rax, [rbp+4Fh+var_50]
0x1800927e2  mov     [rbp+4Fh+var_B0], rax
0x1800927e6  lea     rax, [rbp+4Fh+var_58]
0x1800927ea  mov     [rbp+4Fh+var_A8], rax
0x1800927ee  lea     rax, [rbp+4Fh+pv]
0x1800927f2  mov     [rbp+4Fh+var_A0], rax
0x1800927f6  lea     rax, [rbp+4Fh+var_68]
0x1800927fa  mov     [rbp+4Fh+var_98], rax
0x1800927fe  mov     r8b, [rbx+80h]
0x180092805  lea     rdx, [rsp+110h+var_D0]
0x18009280a  mov     rcx, [rbp+4Fh+var_60]
0x18009280e  call    ??$InvokeInContext@V_lambda_1_@?EH@??StageOrInstallRoutine@CScenarioCtrlDesktopCBS@@QEAAJIIPEB_WPEAH@Z@@UpdateAgentMisc@@YAJPEAUIContextCallback@@$$QEAV_lambda_1_@?EH@??StageOrInstallRoutine@CScenarioCtrlDesktopCBS@@QEAAJIIPEB_WPEAH@Z@_N@Z; UpdateAgentMisc::InvokeInContext<`CScenarioCtrlDesktopCBS::StageOrInstallRoutine(uint,uint,wchar_t const *,int *)'::`71'::_lambda_1_>(IContextCallback *,`CScenarioCtrlDesktopCBS::StageOrInstallRoutine(uint,uint,wchar_t const *,int *)'::`71'::_lambda_1_ &&,bool)
  ... truncated ...
```
