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
  __int64 v20; // rdx
  char v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  char v34; // r12
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned int v37; // r9d
  unsigned int v38; // eax
  int v39; // eax
  const char *v40; // rcx
  unsigned int v41; // edx
  unsigned int v42; // r8d
  int v43; // eax
  __int64 traits_2_0_unsigned_short; // rax
  const char *v45; // r9
  __int64 v46; // r11
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rcx
  const wchar_t *v60; // r9
  LPVOID v61; // rdx
  __int64 sstring; // rax
  __int64 v63; // rbx
  HANDLE ProcessHeap; // rax
  int *v65; // [rsp+28h] [rbp-A1h]
  wchar_t v66[4]; // [rsp+38h] [rbp-91h] BYREF
  int v67[2]; // [rsp+40h] [rbp-89h] BYREF
  CScenarioCtrlDesktopCBS *v68; // [rsp+48h] [rbp-81h] BYREF
  const wchar_t **v69; // [rsp+50h] [rbp-79h]
  const wchar_t **v70; // [rsp+58h] [rbp-71h]
  int *v71; // [rsp+60h] [rbp-69h]
  int *v72; // [rsp+68h] [rbp-61h]
  int *v73; // [rsp+70h] [rbp-59h]
  LPVOID *p_pv; // [rsp+78h] [rbp-51h]
  LPVOID *v75; // [rsp+80h] [rbp-49h]
  unsigned __int64 *v76; // [rsp+88h] [rbp-41h]
  __int64 v77; // [rsp+90h] [rbp-39h]
  char v78; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v79[3]; // [rsp+99h] [rbp-30h] BYREF
  int v80; // [rsp+9Ch] [rbp-2Dh] BYREF
  int v81; // [rsp+A0h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v83; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-11h] BYREF
  int v85; // [rsp+C0h] [rbp-9h] BYREF
  int v86; // [rsp+C4h] [rbp-5h] BYREF
  _QWORD v87[2]; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+57h]
  const wchar_t *v89; // [rsp+140h] [rbp+77h] BYREF

  v89 = a4;
  v77 = -2;
  v5 = a4;
  *(_QWORD *)v67 = a5;
  v8 = 0;
  if ( !a4 || !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
      (const char *)0x80004003LL,
      (int)v65);
    return 2147500035LL;
  }
  v80 = a3;
  *((_BYTE *)this + 84) = 0;
  v79[0] = (a3 & 0x1000) != 0;
  v83 = 0;
  v9 = 100;
  v10 = 1;
  if ( (a3 & 0x1000) != 0 )
  {
    *((_DWORD *)this + 65) = 0;
  }
  else if ( (a3 & 0x400) != 0 )
  {
    *((_DWORD *)this + 65) = 1;
    v83 = 70;
  }
  else
  {
    *((_DWORD *)this + 65) = 2;
    v83 = 100;
  }
  pv = 0;
  v85 = 0;
  v86 = 0;
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
  v80 = a3;
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
      v5 = v89;
      goto LABEL_23;
    }
    LODWORD(a3) = a3 | 0x200;
  }
  else
  {
    LODWORD(a3) = a3 | 0x100;
  }
  v80 = a3;
LABEL_23:
  v78 = 0;
  *(_QWORD *)v66 = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  ActionList = LoadActionList(0, v5, a3, v66);
  v16 = ActionList;
  v17 = *(void (__fastcall ****)(_QWORD))v66;
  if ( ActionList >= 0 )
  {
    v21 = 0;
    v22 = *(_QWORD *)(*(_QWORD *)v66 + 88LL);
    v23 = v22 + 168LL * *(unsigned int *)(*(_QWORD *)v66 + 96LL);
    while ( 1 )
    {
      if ( v22 == v23 )
      {
        v78 = v21;
        goto LABEL_49;
      }
      v24 = *(_DWORD *)(v22 + 88);
      if ( v24 == 7 )
      {
        v21 = 1;
        *((_QWORD *)this + 35) = *(_QWORD *)(v22 + 8);
        goto LABEL_46;
      }
      v25 = v24 - 2;
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
      v30 = v29 - 1;
      if ( !v30 )
        break;
      v31 = v30 - 2;
      if ( !v31 )
        break;
      v32 = v31 - 2;
      if ( v32 )
      {
        if ( v32 == 2 )
          break;
      }
      else if ( *((_DWORD *)this + 6) == 25 || *(_DWORD *)(v22 + 96) == 4 )
      {
        break;
      }
LABEL_46:
      v22 += 168;
    }
    v8 = 1;
    *((_QWORD *)this + 36) += *(_QWORD *)(v22 + 8);
    goto LABEL_46;
  }
  v81 = ActionList;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LOBYTE(v15) = 1;
    LogAdapter::Logger::LogNumObjects<long>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v15,
      3,
      "Failed to load actionlist, hr = {}",
      &v81);
  }
  v18 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    LODWORD(v65) = 961;
    updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                *((_QWORD *)this + 4),
                4,
                L"%s(%d): Result = 0x%X",
                L"CScenarioCtrlDesktopCBS::EvaluateActionList");
    v18 = (unsigned int)updated;
    if ( updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated, v20);
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
      (int)v65);
LABEL_53:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v16;
  }
  v34 = a2 & 1;
  if ( !v78 && v34 )
  {
    LogAdapter::TraceInfo<>("Only SSU operations were requested, but the actionlist does not contain an SSU.");
    **(_DWORD **)v67 = 0;
LABEL_145:
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  if ( v78 && v8 )
  {
    v35 = *((_QWORD *)this + 35);
    if ( !v35 )
    {
      if ( *((_QWORD *)this + 36) )
      {
        v35 = 0;
      }
      else
      {
        v35 = 5;
        *((_QWORD *)this + 35) = 5;
        *((_QWORD *)this + 36) = 95;
      }
    }
    v36 = *((_QWORD *)this + 33);
    v37 = *((_DWORD *)this + 77);
    if ( v83 >= v36 )
      v38 = v37 + v35 * (v83 - v36) / (v35 + *((_QWORD *)this + 36));
    else
      v38 = *((_DWORD *)this + 77);
    v39 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, v37, v38);
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v39,
        (int)v65);
    v40 = "Both SSU and non-SSU package(s) are present, but only performing SSU operations.";
    if ( !v34 )
      v40 = "Both SSU and non-SSU package(s) are present. Performing any applicable operations for all.";
    LogAdapter::TraceInfo<>(v40);
  }
  else
  {
    LogAdapter::TraceInfo<>("Actionlist does not have both an SSU and non-SSU package(s).");
    v41 = *((_DWORD *)this + 77);
    if ( v83 >= *((_QWORD *)this + 34) + *((_QWORD *)this + 33) )
      v42 = v41 + v83 - *((_DWORD *)this + 66) - *((_DWORD *)this + 68);
    else
      v42 = *((_DWORD *)this + 77);
    v43 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, v41, v42);
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v43,
        (int)v65);
  }
  traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                L"UpdateAgentLCU",
                                &unk_1802D0DCE,
                                0);
  if ( traits_2_0_unsigned_short == v47 || (v48 = (traits_2_0_unsigned_short - v46) >> 1, v48 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
      v45);
  v87[0] = v46;
  v87[1] = v48;
  wil::CoCreateInstance<IContextCallback,wil::err_exception_policy>(&v84);
  if ( v78 )
  {
    v68 = this;
    v69 = &v89;
    v70 = (const wchar_t **)v79;
    v71 = &v80;
    v72 = (int *)v87;
    v73 = &v85;
    p_pv = &pv;
    v75 = (LPVOID *)&v83;
    LOBYTE(v49) = *((_BYTE *)this + 128);
    v16 = ___InvokeInContext_V_lambda_1___EH___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__UpdateAgentMisc__YAJPEAUIContextCallback____QEAV_lambda_1___EH___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__N_Z(
            v84,
            &v68,
            v49);
    if ( v16 == -2145116147 )
    {
      if ( v8 )
      {
        v50 = *((_QWORD *)this + 4);
        if ( v34 )
        {
          if ( v50 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v50, 2, L"ServicingProcessor succeeded in installing the SSU.");
          goto LABEL_130;
        }
        if ( v50 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v50,
            2,
            L"ServicingProcessor succeeded in installing the SSU. Creating a new session to install the rest of the packages.");
        goto LABEL_107;
      }
LABEL_98:
      v81 = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "ICbsServicingProcessor->Process for the SSU failed");
        *(_QWORD *)v67 = &v81;
        v65 = v67;
        LOBYTE(v52) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v52,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v16,
        (int)v65);
      if ( v84 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
      goto LABEL_53;
    }
    if ( v16 == -2146498506 )
    {
      if ( v8 )
      {
        v51 = *((_QWORD *)this + 4);
        if ( v51 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v51,
            2,
            L"ServicingProcessor succeeded in installing the SSU within the MuV6 path. Skipping non-SSU package(s) install"
             " and will resume when the stack restarts. Returning CBS_E_MUV6_STACK_SHUTDOWN_NEEDED.");
        if ( v84 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
        if ( pv )
          CoTaskMemFree(pv);
        return 2148468790LL;
      }
      goto LABEL_98;
    }
    if ( v16 < 0 )
      goto LABEL_98;
    v53 = *((_QWORD *)this + 4);
    if ( v53 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v53,
        2,
        L"ServicingProcessor for the SSU succeeded and returned this Session ID: [%s]",
        pv);
  }
  if ( !v8 || v34 )
    goto LABEL_130;
LABEL_107:
  if ( v78 )
  {
    v54 = *((_QWORD *)this + 34);
    if ( v83 >= v54 )
    {
      if ( v83 != 100 )
        v9 = *((_DWORD *)this + 77)
           + *((_QWORD *)this + 36) * (v83 - v54) / (*((_QWORD *)this + 36) + *((_QWORD *)this + 35));
    }
    else
    {
      v9 = *((_DWORD *)this + 77);
    }
    v55 = CScenarioCtrlDesktopCBS::SetInternalProgressRange(this, *((_DWORD *)this + 77), v9);
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v55,
        (int)v65);
  }
  v68 = this;
  v69 = (const wchar_t **)&v78;
  v70 = &v89;
  v71 = (int *)v79;
  v72 = &v80;
  v73 = (int *)v87;
  p_pv = (LPVOID *)&v86;
  v75 = &pv;
  v76 = &v83;
  LOBYTE(v49) = *((_BYTE *)this + 128);
  v16 = ___InvokeInContext_V_lambda_2___HA___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__UpdateAgentMisc__YAJPEAUIContextCallback____QEAV_lambda_2___HA___StageOrInstallRoutine_CScenarioCtrlDesktopCBS__QEAAJIIPEB_WPEAH_Z__N_Z(
          v84,
          &v68,
          v49);
  if ( v16 != -2146498505 )
  {
    if ( v16 < 0 )
    {
      v81 = v16;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "ICbsServicingProcessor->Process for the non-SSU packages failed");
        *(_QWORD *)v67 = &v81;
        v65 = v67;
        LOBYTE(v57) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v57,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlDesktopCBS.h",
        (const char *)(unsigned int)v16,
        (int)v65);
      if ( v84 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
      goto LABEL_53;
    }
    v58 = *((_QWORD *)this + 4);
    if ( v58 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v58,
        2,
        L"ServicingProcessor for the non-SSU packages succeeded and returned this Session ID: [%s]",
        pv);
LABEL_130:
    if ( v85 != 1 && v86 != 1 )
      v10 = 0;
    v59 = *((_QWORD *)this + 4);
    if ( v59 )
    {
      v60 = L"TRUE";
      if ( !v10 )
        v60 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v59, 2, L"Reboot required: [%ls]", v60);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PlayB_ModelInstallation>::GetImpl'::`2'::impl) )
    {
      if ( !pv )
      {
LABEL_143:
        **(_DWORD **)v67 = v10;
        if ( v84 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
        goto LABEL_145;
      }
      v61 = pv;
    }
    else
    {
      v61 = pv;
    }
    sstring = make_sstring(v66, (unsigned __int64)v61);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      (char *)this + 72,
      sstring);
    v63 = *(_QWORD *)v66;
    if ( *(_QWORD *)v66 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v63 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    goto LABEL_143;
  }
  v56 = *((_QWORD *)this + 4);
  if ( v56 )
    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
      v56,
      2,
      L"ICbsServicingProcessor->Process failed to stage the non-SSU packages because a postponed reserve install was considered.");
  if ( v84 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
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
