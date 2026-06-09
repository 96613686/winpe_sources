# Wns::ConnectionStateMachine::Connect(_NotificationUser,uint)

- ea: `0x18000b720`
- end: `0x18000c218`
- name: `?Connect@ConnectionStateMachine@Wns@@QEAAXU_NotificationUser@@I@Z`
- size: `2808`
- prototype: `void __fastcall(__int64, LPVOID *, DWORD)`
- caller_count: `6`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180003e60`
- `0x180004298`
- `0x1800054a0`
- `0x180006eb0`
- `0x180008780`
- `0x18000b720`

## callees

- `0x180003190`
- `0x180004f40`
- `0x1800056d0`
- `0x180007820`
- `0x180007b70`
- `0x180009250`
- `0x18000a910`
- `0x18000a980`
- `0x18000b720`
- `0x18000c220`
- `0x18000c710`
- `0x18000c760`
- `0x18000c990`
- `0x18000cd88`
- `0x18000d1f0`
- `0x18000fcf0`
- `0x1800109d4`
- `0x180012710`
- `0x180015ba8`
- `0x180021048`
- `0x180021468`
- `0x180022ce4`
- `0x180023840`
- `0x180026200`
- `0x1800265d0`
- `0x1800274c8`
- `0x1800328a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b81b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b81b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bcef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c045`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c037`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c037`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c11f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c11f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c007`

## string_xrefs

- `0x18000c194`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000c13f`: `Unknown thread state encountered in state machine`

## pseudocode

```c
void __fastcall Wns::ConnectionStateMachine::Connect(__int64 a1, LPVOID *a2, DWORD a3)
{
  struct _TP_WORK *ConnectionProvider; // rbx
  void *v7; // r14
  bool v8; // si
  char *v9; // rdx
  int *v10; // rcx
  char *v11; // rax
  int *v12; // rax
  int v13; // ecx
  int v14; // esi
  DWORD v15; // eax
  const char *v16; // r9
  void *v17; // rbx
  __int64 v18; // rax
  int v19; // esi
  void *v20; // r8
  void *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  void *v26; // rsi
  HANDLE v27; // rax
  int v28; // esi
  unsigned int v29; // ebx
  _QWORD *v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  int v33; // esi
  void *v34; // rcx
  int v35; // esi
  void *v36; // rsi
  HANDLE ProcessHeap; // rax
  void *v38; // rsi
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // esi
  int v43; // [rsp+20h] [rbp-E0h]
  const char *v44; // [rsp+28h] [rbp-D8h]
  __int128 v45; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID *v47; // [rsp+50h] [rbp-B0h]
  void *v48; // [rsp+58h] [rbp-A8h] BYREF
  char v49; // [rsp+60h] [rbp-A0h]
  void **v50; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h] BYREF
  char v52; // [rsp+7Ch] [rbp-84h]
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  unsigned int v55; // [rsp+A0h] [rbp-60h] BYREF
  const char *v56; // [rsp+A8h] [rbp-58h]
  LPVOID v57; // [rsp+B0h] [rbp-50h]
  char v58; // [rsp+B8h] [rbp-48h]
  int v59; // [rsp+C0h] [rbp-40h]
  __int128 v60; // [rsp+C8h] [rbp-38h]
  __int128 v61; // [rsp+D8h] [rbp-28h]
  __int128 v62; // [rsp+E8h] [rbp-18h]
  __int128 v63; // [rsp+F8h] [rbp-8h]
  __int128 v64; // [rsp+108h] [rbp+8h]
  __int128 v65; // [rsp+118h] [rbp+18h]
  __int128 v66; // [rsp+128h] [rbp+28h]
  __int128 v67; // [rsp+138h] [rbp+38h]
  __int128 v68; // [rsp+148h] [rbp+48h]
  __int64 v69; // [rsp+158h] [rbp+58h]
  LPVOID lpMem[2]; // [rsp+160h] [rbp+60h]
  int v71; // [rsp+170h] [rbp+70h]
  __int64 v72; // [rsp+178h] [rbp+78h]
  int *v73; // [rsp+180h] [rbp+80h]
  void *v74; // [rsp+188h] [rbp+88h]
  _QWORD v75[3]; // [rsp+190h] [rbp+90h] BYREF
  int v76; // [rsp+1A8h] [rbp+A8h]
  unsigned int *v77; // [rsp+1B0h] [rbp+B0h]
  char v78; // [rsp+1B8h] [rbp+B8h]
  void **v79; // [rsp+1C0h] [rbp+C0h] BYREF
  int v80; // [rsp+1C8h] [rbp+C8h] BYREF
  char v81; // [rsp+1CCh] [rbp+CCh]
  __int128 v82; // [rsp+1D0h] [rbp+D0h]
  __int128 v83; // [rsp+1E0h] [rbp+E0h]
  unsigned int v84; // [rsp+1F0h] [rbp+F0h] BYREF
  const char *v85; // [rsp+1F8h] [rbp+F8h]
  void *v86; // [rsp+200h] [rbp+100h]
  char v87; // [rsp+208h] [rbp+108h]
  int v88; // [rsp+210h] [rbp+110h]
  __int128 v89; // [rsp+218h] [rbp+118h]
  __int128 v90; // [rsp+228h] [rbp+128h]
  __int128 v91; // [rsp+238h] [rbp+138h]
  __int128 v92; // [rsp+248h] [rbp+148h]
  __int128 v93; // [rsp+258h] [rbp+158h]
  __int128 v94; // [rsp+268h] [rbp+168h]
  __int128 v95; // [rsp+278h] [rbp+178h]
  __int128 v96; // [rsp+288h] [rbp+188h]
  __int128 v97; // [rsp+298h] [rbp+198h]
  __int64 v98; // [rsp+2A8h] [rbp+1A8h]
  __int128 v99; // [rsp+2B0h] [rbp+1B0h]
  int v100; // [rsp+2C0h] [rbp+1C0h]
  __int64 v101; // [rsp+2C8h] [rbp+1C8h]
  int *v102; // [rsp+2D0h] [rbp+1D0h]
  char *v103; // [rsp+2D8h] [rbp+1D8h]
  _QWORD v104[3]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v105; // [rsp+2F8h] [rbp+1F8h]
  unsigned int *v106; // [rsp+300h] [rbp+200h]
  char v107; // [rsp+308h] [rbp+208h]
  void **v108; // [rsp+310h] [rbp+210h] BYREF
  int v109; // [rsp+318h] [rbp+218h] BYREF
  char v110; // [rsp+31Ch] [rbp+21Ch]
  __int128 v111; // [rsp+320h] [rbp+220h]
  __int128 v112; // [rsp+330h] [rbp+230h]
  _QWORD v113[2]; // [rsp+340h] [rbp+240h] BYREF
  __int128 v114; // [rsp+350h] [rbp+250h]
  int v115; // [rsp+360h] [rbp+260h]
  __int128 v116; // [rsp+368h] [rbp+268h]
  __int128 v117; // [rsp+378h] [rbp+278h]
  __int128 v118; // [rsp+388h] [rbp+288h]
  __int128 v119; // [rsp+398h] [rbp+298h]
  __int128 v120; // [rsp+3A8h] [rbp+2A8h]
  __int128 v121; // [rsp+3B8h] [rbp+2B8h]
  __int128 v122; // [rsp+3C8h] [rbp+2C8h]
  __int128 v123; // [rsp+3D8h] [rbp+2D8h]
  __int128 v124; // [rsp+3E8h] [rbp+2E8h]
  __int64 v125; // [rsp+3F8h] [rbp+2F8h]
  LPVOID v126; // [rsp+400h] [rbp+300h]
  LPVOID v127; // [rsp+408h] [rbp+308h]
  int v128; // [rsp+410h] [rbp+310h]
  __int64 v129; // [rsp+418h] [rbp+318h]
  int *v130; // [rsp+420h] [rbp+320h]
  char *v131; // [rsp+428h] [rbp+328h]
  _QWORD v132[3]; // [rsp+430h] [rbp+330h] BYREF
  int v133; // [rsp+448h] [rbp+348h]
  _DWORD *v134; // [rsp+450h] [rbp+350h]
  char v135; // [rsp+458h] [rbp+358h]
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v51 = 0;
  v52 = 0;
  v58 = 0;
  v55 = 0;
  v56 = "ConnectActivity";
  v57 = 0;
  v59 = 0;
  *(_OWORD *)lpMem = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 1;
  v72 = 0;
  v73 = &v51;
  v74 = 0;
  v75[0] = 0;
  v75[1] = &v50;
  v75[2] = 0;
  v76 = 0;
  v77 = &v55;
  v78 = 0;
  v50 = &WnsCPLog::ConnectActivity::`vftable';
  ConnectionProvider = 0;
  *(_QWORD *)&v45 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  pv[0] = (LPVOID)a1;
  v80 = 0;
  v81 = 0;
  v87 = 0;
  v84 = 0;
  v85 = "ConnectActivity";
  v86 = 0;
  v88 = 0;
  v99 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v100 = 1;
  v101 = 0;
  v102 = &v80;
  v103 = 0;
  v104[0] = 0;
  v104[1] = &v79;
  v104[2] = 0;
  v105 = 0;
  v106 = &v84;
  v107 = 0;
  v79 = &WnsCPLog::ConnectActivity::`vftable';
  v7 = *a2;
  WnsCPLog::ConnectActivity::StartActivity(&v79, *a2, a3, *(unsigned int *)(a1 + 40));
  v8 = v76 != 0;
  v108 = &wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v109 = v51;
  v110 = v52;
  v111 = v53;
  v112 = v54;
  v51 = 0;
  v52 = 0;
  v114 = 0;
  v113[0] = v55;
  v113[1] = v56;
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)v113);
  *(_QWORD *)&v114 = v57;
  v57 = 0;
  BYTE8(v114) = v58;
  v58 = 0;
  v115 = v59;
  v116 = v60;
  v117 = v61;
  v118 = v62;
  v119 = v63;
  v120 = v64;
  v121 = v65;
  v122 = v66;
  v123 = v67;
  v124 = v68;
  v125 = v69;
  v126 = lpMem[0];
  v127 = lpMem[1];
  *(_OWORD *)lpMem = 0;
  v128 = v71;
  v129 = 0;
  v9 = (char *)v74;
  v131 = (char *)v74;
  v74 = 0;
  v132[0] = 0;
  v132[1] = &v108;
  v132[2] = 0;
  v133 = 0;
  v134 = 0;
  v135 = 0;
  if ( v8 )
  {
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v132);
    v9 = v131;
  }
  if ( v9 )
    v10 = (int *)(v9 + 8);
  else
    v10 = &v109;
  v130 = v10;
  v134 = v10 + 10;
  v73 = &v51;
  if ( v76 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v75);
  v108 = &WnsCPLog::ConnectActivity::`vftable';
  v51 = v80;
  v52 = v81;
  v53 = v82;
  v54 = v83;
  v80 = 0;
  v81 = 0;
  v55 = v84;
  v56 = v85;
  if ( v58 )
  {
    v36 = v57;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v36);
  }
  v57 = v86;
  v86 = 0;
  v58 = v87;
  v87 = 0;
  v59 = v88;
  v60 = v89;
  v61 = v90;
  v62 = v91;
  v63 = v92;
  v64 = v93;
  v65 = v94;
  v66 = v95;
  v67 = v96;
  v68 = v97;
  v69 = v98;
  if ( lpMem[0] && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem[0], 0xFFFFFFFF) == 1 )
  {
    v26 = lpMem[0];
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  *(_OWORD *)lpMem = v99;
  v99 = 0;
  v71 = v100;
  if ( v74 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v74, 0xFFFFFFFF) == 1 )
    {
      v38 = v74;
      if ( v74 )
      {
        wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>((char *)v74 + 8);
        operator delete(v38);
      }
    }
  }
  v11 = v103;
  v74 = v103;
  v103 = 0;
  if ( v74 )
    v12 = (int *)(v11 + 8);
  else
    v12 = &v51;
  v73 = v12;
  v77 = (unsigned int *)(v12 + 10);
  if ( v105 )
  {
    if ( !v76 )
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v75);
  }
  else if ( v76 )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v75);
  }
  v102 = &v80;
  if ( v105 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v104);
  WnsCPLog::ConnectActivity::~ConnectActivity((WnsCPLog::ConnectActivity *)&v108);
  WnsCPLog::ConnectActivity::~ConnectActivity((WnsCPLog::ConnectActivity *)&v79);
  v13 = *(_DWORD *)(a1 + 40);
  if ( v13 == 1 )
    goto LABEL_19;
  if ( !v13 )
  {
    ConnectionProvider = Wns::ConnectionStateMachine::LoadConnectionProvider((Wns::ConnectionStateMachine *)a1);
LABEL_19:
    *(_DWORD *)(a1 + 40) = 2;
    v14 = 1;
    goto LABEL_20;
  }
  v39 = v13 - 2;
  if ( v39 )
  {
    v40 = v39 - 1;
    if ( v40 )
    {
      v41 = v40 - 1;
      if ( v41 )
      {
        if ( v41 != 1 )
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x123,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Unknown state encountered in machine",
            v44);
        goto LABEL_19;
      }
      v14 = 4;
    }
    else
    {
      v14 = 5;
    }
  }
  else
  {
    v14 = 3;
  }
LABEL_20:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  if ( ConnectionProvider )
    SubmitThreadpoolWork(ConnectionProvider);
  if ( v14 != 5 )
  {
    v33 = v14 - 1;
    if ( v33 )
    {
      v42 = v33 - 2;
      if ( v42 )
      {
        if ( v42 != 1 )
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x13B,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Unknown thread state encountered in state machine",
            v44);
        _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
          a1 + 56,
          a3);
        v45 = *(_OWORD *)a2;
        Wns::ConnectionStateMachine::Connect(a1, &v45, a3);
      }
    }
    else
    {
      v45 = *(_OWORD *)a2;
      Wns::ConnectionStateMachine::DoConnect(a1, &v45, a3);
    }
  }
  WnsCPLog::WnsWaitForConnect<unsigned __int64 &>(a2);
  v15 = WaitForSingleObjectEx(*(HANDLE *)(a1 + 48), a3, 0);
  if ( v15 == 258 )
  {
    WnsCPLog::WnsConnectEventTimeout();
    Wns::ConnectionStateMachine::OnConnectionChanged(a1, 4, 0, 2147943860LL);
    goto LABEL_45;
  }
  if ( v15 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v16);
  if ( *(int *)(a1 + 448) >= 0 )
  {
    v17 = a2[1];
    Wns::ConnectionStateMachine::VerifyConnected((LPCRITICAL_SECTION)a1);
    Wns::ConnectionProviderLoader::Get(*(_QWORD *)(a1 + 368), &v45);
    pv[0] = 0;
    v18 = *(_QWORD *)v45;
    v47 = pv;
    v48 = 0;
    v49 = 1;
    v19 = (*(__int64 (__fastcall **)(_QWORD, void *, void **))(v18 + 80))(v45, v7, &v48);
    if ( v49 )
    {
      v20 = *v47;
      *v47 = v48;
      if ( v20 )
        CoTaskMemFree(v20);
    }
    if ( v19 == -2013002772 )
    {
      v21 = pv[0];
      pv[0] = 0;
      if ( v21 )
        CoTaskMemFree(v21);
      v22 = v45;
      if ( (_QWORD)v45 )
      {
        *(_QWORD *)&v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = a1 + 64;
LABEL_35:
      Wns::CPTransactionRequestManager::SetModeForUser(v23, v7, 1);
      Wns::ConnectionProviderLoader::Get(*(_QWORD *)(a1 + 368), &v45);
      pv[0] = v7;
      pv[1] = v17;
      v24 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)v45 + 40LL))(v45, pv);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
          (const char *)(unsigned int)v24,
          v43);
      v25 = v45;
      if ( (_QWORD)v45 )
      {
        *(_QWORD *)&v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      goto LABEL_45;
    }
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
        (const char *)(unsigned int)v19,
        v43);
    v34 = pv[0];
    v35 = *((_DWORD *)pv[0] + 3);
    pv[0] = 0;
    if ( v34 )
      CoTaskMemFree(v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    v23 = a1 + 64;
    v28 = v35 - 1;
    if ( !v28 )
    {
      Wns::CPTransactionRequestManager::SetModeForUser(v23, v7, 1);
      goto LABEL_45;
    }
    if ( v28 != 1 )
      goto LABEL_35;
    Wns::CPTransactionRequestManager::SetModeForUser(v23, v7, 0);
    v29 = *(_DWORD *)(a1 + 444);
    Wns::ClientRegistration::GetCallback(*(_QWORD *)(a1 + 360), pv);
    v30 = Wns::Callback::ScopedCallbackHandle::operator->((__int64)pv, &v45);
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(*(_QWORD *)*v30 + 24LL))(
            *v30,
            4,
            0xFFFFFFFFLL,
            v29);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x125,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionmultiplexer.cpp",
        (const char *)(unsigned int)v31);
    v32 = v45;
    if ( (_QWORD)v45 )
    {
      *(_QWORD *)&v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    if ( pv[0] )
      Wns::Callback::DecrementNumRunning((Wns::Callback *)pv[0]);
  }
LABEL_45:
  wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v50);
  WnsCPLog::ConnectActivity::~ConnectActivity((WnsCPLog::ConnectActivity *)&v50);
}

```

## disassembly

```asm
0x18000b720  mov     [rsp-8+arg_18], rbx
0x18000b725  push    rbp
0x18000b726  push    rsi
0x18000b727  push    rdi
0x18000b728  push    r12
0x18000b72a  push    r13
0x18000b72c  push    r14
0x18000b72e  push    r15
0x18000b730  lea     rbp, [rsp-370h]
0x18000b738  sub     rsp, 470h
0x18000b73f  mov     rax, cs:__security_cookie
0x18000b746  xor     rax, rsp
0x18000b749  mov     [rbp+3A0h+var_40], rax
0x18000b750  mov     r12d, r8d
0x18000b753  mov     r15, rdx
0x18000b756  mov     rdi, rcx
0x18000b759  xor     r13d, r13d
0x18000b75c  mov     [rsp+4A0h+var_428], r13d
0x18000b761  mov     [rsp+4A0h+var_424], r13b
0x18000b766  mov     [rbp+3A0h+var_3E8], r13b
0x18000b76a  mov     [rbp+3A0h+var_400], r13d
0x18000b76e  lea     rsi, aConnectactivit; "ConnectActivity"
0x18000b775  mov     [rbp+3A0h+var_3F8], rsi
0x18000b779  mov     [rbp+3A0h+var_3F0], r13
0x18000b77d  mov     [rbp+3A0h+var_3E0], r13d
0x18000b781  xorps   xmm0, xmm0
0x18000b784  movdqa  xmmword ptr [rbp+3A0h+lpMem], xmm0
0x18000b789  xorps   xmm1, xmm1
0x18000b78c  xor     eax, eax
0x18000b78e  movups  [rbp+3A0h+var_3D8], xmm1
0x18000b792  movups  [rbp+3A0h+var_3C8], xmm1
0x18000b796  movups  [rbp+3A0h+var_3B8], xmm1
0x18000b79a  movups  [rbp+3A0h+var_3A8], xmm1
0x18000b79e  movups  [rbp+3A0h+var_398], xmm1
0x18000b7a2  movups  [rbp+3A0h+var_388], xmm1
0x18000b7a6  movups  [rbp+3A0h+var_378], xmm1
0x18000b7aa  movups  [rbp+3A0h+var_368], xmm1
0x18000b7ae  movups  [rbp+3A0h+var_358], xmm1
0x18000b7b2  mov     [rbp+3A0h+var_348], rax
0x18000b7b6  mov     [rbp+3A0h+var_330], 1
0x18000b7bd  mov     [rbp+3A0h+var_328], rax
0x18000b7c1  lea     rax, [rsp+4A0h+var_428]
0x18000b7c6  mov     [rbp+3A0h+var_320], rax
0x18000b7cd  mov     [rbp+3A0h+var_318], r13
0x18000b7d4  mov     [rbp+3A0h+var_310], r13
0x18000b7db  lea     rax, [rsp+4A0h+var_430]
0x18000b7e0  mov     [rbp+3A0h+var_308], rax
0x18000b7e7  mov     [rbp+3A0h+var_300], r13
0x18000b7ee  mov     [rbp+3A0h+var_2F8], r13d
0x18000b7f5  lea     rax, [rbp+3A0h+var_400]
0x18000b7f9  mov     [rbp+3A0h+var_2F0], rax
0x18000b800  mov     [rbp+3A0h+var_2E8], r13b
0x18000b807  lea     r14, ??_7ConnectActivity@WnsCPLog@@6B@; const WnsCPLog::ConnectActivity::`vftable'
0x18000b80e  mov     [rsp+4A0h+var_430], r14
0x18000b813  mov     ebx, r13d
0x18000b816  mov     qword ptr [rsp+4A0h+var_470], rbx
0x18000b81b  call    cs:__imp_EnterCriticalSection
0x18000b821  mov     [rsp+4A0h+pv], rdi
0x18000b826  mov     [rbp+3A0h+var_2D8], r13d
0x18000b82d  mov     [rbp+3A0h+var_2D4], r13b
0x18000b834  mov     [rbp+3A0h+var_298], r13b
0x18000b83b  mov     [rbp+3A0h+var_2B0], r13d
0x18000b842  mov     [rbp+3A0h+var_2A8], rsi
0x18000b849  mov     [rbp+3A0h+var_2A0], r13
0x18000b850  mov     [rbp+3A0h+var_290], r13d
0x18000b857  xorps   xmm0, xmm0
0x18000b85a  movdqa  [rbp+3A0h+var_1F0], xmm0
0x18000b862  xorps   xmm1, xmm1
0x18000b865  xor     eax, eax
0x18000b867  movups  [rbp+3A0h+var_288], xmm1
0x18000b86e  movups  [rbp+3A0h+var_278], xmm1
0x18000b875  movups  [rbp+3A0h+var_268], xmm1
0x18000b87c  movups  [rbp+3A0h+var_258], xmm1
0x18000b883  movups  [rbp+3A0h+var_248], xmm1
0x18000b88a  movups  [rbp+3A0h+var_238], xmm1
0x18000b891  movups  [rbp+3A0h+var_228], xmm1
0x18000b898  movups  [rbp+3A0h+var_218], xmm1
0x18000b89f  movups  [rbp+3A0h+var_208], xmm1
0x18000b8a6  mov     [rbp+3A0h+var_1F8], rax
0x18000b8ad  mov     [rbp+3A0h+var_1E0], 1
0x18000b8b7  mov     [rbp+3A0h+var_1D8], rax
0x18000b8be  lea     rax, [rbp+3A0h+var_2D8]
0x18000b8c5  mov     [rbp+3A0h+var_1D0], rax
0x18000b8cc  mov     [rbp+3A0h+var_1C8], r13
0x18000b8d3  mov     [rbp+3A0h+var_1C0], r13
0x18000b8da  lea     rax, [rbp+3A0h+var_2E0]
0x18000b8e1  mov     [rbp+3A0h+var_1B8], rax
0x18000b8e8  mov     [rbp+3A0h+var_1B0], r13
0x18000b8ef  mov     [rbp+3A0h+var_1A8], r13d
0x18000b8f6  lea     rax, [rbp+3A0h+var_2B0]
0x18000b8fd  mov     [rbp+3A0h+var_1A0], rax
0x18000b904  mov     [rbp+3A0h+var_198], r13b
0x18000b90b  mov     [rbp+3A0h+var_2E0], r14
0x18000b912  mov     r14, [r15]
0x18000b915  mov     r9d, [rdi+28h]
0x18000b919  mov     r8d, r12d
0x18000b91c  mov     rdx, r14
0x18000b91f  lea     rcx, [rbp+3A0h+var_2E0]
0x18000b926  call    ?StartActivity@ConnectActivity@WnsCPLog@@QEAAX_JIW4__MIDL___MIDL_itf_wpnplatform_0000_0000_0002@@@Z; WnsCPLog::ConnectActivity::StartActivity(__int64,uint,__MIDL___MIDL_itf_wpnplatform_0000_0000_0002)
0x18000b92b  nop
0x18000b92c  cmp     [rbp+3A0h+var_2F8], r13d
0x18000b933  setnz   sil
0x18000b937  lea     rax, ??_7?$ActivityBase@VWnsCPTracelogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<WnsCPTracelogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000b93e  mov     [rbp+3A0h+var_190], rax
0x18000b945  mov     eax, [rsp+4A0h+var_428]
0x18000b949  mov     [rbp+3A0h+var_188], eax
0x18000b94f  movzx   eax, [rsp+4A0h+var_424]
0x18000b954  mov     [rbp+3A0h+var_184], al
0x18000b95a  movaps  xmm0, [rbp+3A0h+var_420]
0x18000b95e  movaps  [rbp+3A0h+var_180], xmm0
0x18000b965  movaps  xmm1, [rbp+3A0h+var_410]
0x18000b969  movaps  [rbp+3A0h+var_170], xmm1
0x18000b970  mov     [rsp+4A0h+var_428], r13d
0x18000b975  mov     [rsp+4A0h+var_424], r13b
0x18000b97a  mov     [rbp+3A0h+var_148], r13b
0x18000b981  xorps   xmm0, xmm0
0x18000b984  movups  [rbp+3A0h+var_160], xmm0
0x18000b98b  movups  xmmword ptr [rbp+250h], xmm0
0x18000b992  mov     eax, [rbp+3A0h+var_400]
0x18000b995  mov     dword ptr [rbp+3A0h+var_160], eax
0x18000b99b  mov     rax, [rbp+3A0h+var_3F8]
0x18000b99f  mov     qword ptr [rbp+3A0h+var_160+8], rax
0x18000b9a6  lea     rcx, [rbp+3A0h+var_160]; this
0x18000b9ad  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x18000b9b2  mov     rax, [rbp+3A0h+var_3F0]
0x18000b9b6  mov     [rbp+3A0h+var_150], rax
0x18000b9bd  mov     [rbp+3A0h+var_3F0], r13
0x18000b9c1  movzx   eax, [rbp+3A0h+var_3E8]
0x18000b9c5  mov     [rbp+3A0h+var_148], al
0x18000b9cb  mov     [rbp+3A0h+var_3E8], r13b
0x18000b9cf  mov     eax, [rbp+3A0h+var_3E0]
0x18000b9d2  mov     [rbp+3A0h+var_140], eax
0x18000b9d8  movups  xmm0, [rbp+3A0h+var_3D8]
0x18000b9dc  movups  [rbp+3A0h+var_138], xmm0
0x18000b9e3  movups  xmm1, [rbp+3A0h+var_3C8]
0x18000b9e7  movups  [rbp+3A0h+var_128], xmm1
0x18000b9ee  movups  xmm0, [rbp+3A0h+var_3B8]
0x18000b9f2  movups  [rbp+3A0h+var_118], xmm0
0x18000b9f9  movups  xmm1, [rbp+3A0h+var_3A8]
0x18000b9fd  movups  [rbp+3A0h+var_108], xmm1
0x18000ba04  movups  xmm0, [rbp+3A0h+var_398]
0x18000ba08  movups  [rbp+3A0h+var_F8], xmm0
0x18000ba0f  movups  xmm1, [rbp+3A0h+var_388]
0x18000ba13  movups  [rbp+3A0h+var_E8], xmm1
0x18000ba1a  movups  xmm0, [rbp+3A0h+var_378]
0x18000ba1e  movups  [rbp+3A0h+var_D8], xmm0
0x18000ba25  movups  xmm1, [rbp+3A0h+var_368]
0x18000ba29  movups  [rbp+3A0h+var_C8], xmm1
0x18000ba30  movups  xmm0, [rbp+3A0h+var_358]
0x18000ba34  movups  [rbp+3A0h+var_B8], xmm0
0x18000ba3b  movsd   xmm1, [rbp+3A0h+var_348]
0x18000ba40  movsd   [rbp+3A0h+var_A8], xmm1
0x18000ba48  mov     rax, [rbp+3A0h+lpMem]
0x18000ba4c  mov     [rbp+3A0h+var_A0], rax
0x18000ba53  mov     rax, [rbp+3A0h+lpMem+8]
0x18000ba57  mov     [rbp+3A0h+var_98], rax
0x18000ba5e  xorps   xmm0, xmm0
0x18000ba61  movdqa  xmmword ptr [rbp+3A0h+lpMem], xmm0
0x18000ba66  mov     eax, [rbp+3A0h+var_330]
0x18000ba69  mov     [rbp+3A0h+var_90], eax
0x18000ba6f  xor     eax, eax
0x18000ba71  mov     [rbp+3A0h+var_88], rax
0x18000ba78  mov     rdx, [rbp+3A0h+var_318]
0x18000ba7f  mov     [rbp+3A0h+var_78], rdx
0x18000ba86  mov     [rbp+3A0h+var_318], r13
0x18000ba8d  mov     [rbp+3A0h+var_70], r13
0x18000ba94  lea     rax, [rbp+3A0h+var_190]
0x18000ba9b  mov     [rbp+3A0h+var_68], rax
0x18000baa2  mov     [rbp+3A0h+var_60], r13
0x18000baa9  mov     [rbp+3A0h+var_58], r13d
0x18000bab0  mov     [rbp+3A0h+var_50], r13
0x18000bab7  mov     [rbp+3A0h+var_48], r13b
0x18000babe  test    sil, sil
0x18000bac1  jnz     loc_18000BFCA
0x18000bac7  test    rdx, rdx
0x18000baca  jnz     loc_18000C012
0x18000bad0  lea     rcx, [rbp+3A0h+var_188]
0x18000bad7  mov     [rbp+3A0h+var_80], rcx
0x18000bade  lea     rax, [rcx+28h]
0x18000bae2  mov     [rbp+3A0h+var_50], rax
0x18000bae9  lea     rax, [rsp+4A0h+var_428]
0x18000baee  mov     [rbp+3A0h+var_320], rax
0x18000baf5  cmp     [rbp+3A0h+var_2F8], 0
0x18000bafc  jnz     loc_18000C022
0x18000bb02  lea     rax, ??_7ConnectActivity@WnsCPLog@@6B@; const WnsCPLog::ConnectActivity::`vftable'
0x18000bb09  mov     [rbp+3A0h+var_190], rax
0x18000bb10  mov     eax, [rbp+3A0h+var_2D8]
0x18000bb16  mov     [rsp+4A0h+var_428], eax
0x18000bb1a  movzx   eax, [rbp+3A0h+var_2D4]
0x18000bb21  mov     [rsp+4A0h+var_424], al
0x18000bb25  movaps  xmm0, [rbp+3A0h+var_2D0]
0x18000bb2c  movaps  [rbp+3A0h+var_420], xmm0
0x18000bb30  movaps  xmm1, [rbp+3A0h+var_2C0]
0x18000bb37  movaps  [rbp+3A0h+var_410], xmm1
0x18000bb3b  mov     [rbp+3A0h+var_2D8], r13d
0x18000bb42  mov     [rbp+3A0h+var_2D4], 0
0x18000bb49  mov     eax, [rbp+3A0h+var_2B0]
0x18000bb4f  mov     [rbp+3A0h+var_400], eax
0x18000bb52  mov     rax, [rbp+3A0h+var_2A8]
0x18000bb59  mov     [rbp+3A0h+var_3F8], rax
0x18000bb5d  cmp     [rbp+3A0h+var_3E8], 0
0x18000bb61  jnz     loc_18000C033
0x18000bb67  mov     rax, [rbp+3A0h+var_2A0]
0x18000bb6e  mov     [rbp+3A0h+var_3F0], rax
0x18000bb72  mov     [rbp+3A0h+var_2A0], r13
0x18000bb79  movzx   eax, [rbp+3A0h+var_298]
0x18000bb80  mov     [rbp+3A0h+var_3E8], al
0x18000bb83  mov     [rbp+3A0h+var_298], 0
0x18000bb8a  mov     eax, [rbp+3A0h+var_290]
0x18000bb90  mov     [rbp+3A0h+var_3E0], eax
0x18000bb93  movups  xmm0, [rbp+3A0h+var_288]
0x18000bb9a  movups  [rbp+3A0h+var_3D8], xmm0
0x18000bb9e  movups  xmm1, [rbp+3A0h+var_278]
0x18000bba5  movups  [rbp+3A0h+var_3C8], xmm1
0x18000bba9  movups  xmm0, [rbp+3A0h+var_268]
0x18000bbb0  movups  [rbp+3A0h+var_3B8], xmm0
0x18000bbb4  movups  xmm1, [rbp+3A0h+var_258]
0x18000bbbb  movups  [rbp+3A0h+var_3A8], xmm1
0x18000bbbf  movups  xmm0, [rbp+3A0h+var_248]
0x18000bbc6  movups  [rbp+3A0h+var_398], xmm0
0x18000bbca  movups  xmm1, [rbp+3A0h+var_238]
0x18000bbd1  movups  [rbp+3A0h+var_388], xmm1
0x18000bbd5  movups  xmm0, [rbp+3A0h+var_228]
0x18000bbdc  movups  [rbp+3A0h+var_378], xmm0
0x18000bbe0  movups  xmm1, [rbp+3A0h+var_218]
0x18000bbe7  movups  [rbp+3A0h+var_368], xmm1
0x18000bbeb  movups  xmm0, [rbp+3A0h+var_208]
0x18000bbf2  movups  [rbp+3A0h+var_358], xmm0
0x18000bbf6  movsd   xmm1, [rbp+3A0h+var_1F8]
0x18000bbfe  movsd   [rbp+3A0h+var_348], xmm1
0x18000bc03  mov     rcx, [rbp+3A0h+lpMem]
0x18000bc07  test    rcx, rcx
0x18000bc0a  jnz     loc_18000BE7C
0x18000bc10  mov     rax, qword ptr [rbp+3A0h+var_1F0]
0x18000bc17  mov     [rbp+3A0h+lpMem], rax
0x18000bc1b  mov     rax, qword ptr [rbp+3A0h+var_1F0+8]
0x18000bc22  mov     [rbp+3A0h+lpMem+8], rax
0x18000bc26  xorps   xmm0, xmm0
0x18000bc29  movdqa  [rbp+3A0h+var_1F0], xmm0
0x18000bc31  mov     eax, [rbp+3A0h+var_1E0]
0x18000bc37  mov     [rbp+3A0h+var_330], eax
0x18000bc3a  mov     rcx, [rbp+3A0h+var_318]
0x18000bc41  test    rcx, rcx
0x18000bc44  jnz     loc_18000C050
0x18000bc4a  mov     rax, [rbp+3A0h+var_1C8]
0x18000bc51  mov     [rbp+3A0h+var_318], rax
0x18000bc58  mov     [rbp+3A0h+var_1C8], r13
0x18000bc5f  test    rax, rax
0x18000bc62  jnz     loc_18000C08D
0x18000bc68  lea     rax, [rsp+4A0h+var_428]
0x18000bc6d  mov     [rbp+3A0h+var_320], rax
0x18000bc74  add     rax, 28h ; '('
0x18000bc78  mov     [rbp+3A0h+var_2F0], rax
0x18000bc7f  cmp     [rbp+3A0h+var_1A8], 0
0x18000bc86  jz      loc_18000BE5E
0x18000bc8c  cmp     [rbp+3A0h+var_2F8], 0
0x18000bc93  jnz     short loc_18000BCA1
0x18000bc95  lea     rcx, [rbp+3A0h+var_310]; this
0x18000bc9c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000bca1  lea     rax, [rbp+3A0h+var_2D8]
0x18000bca8  mov     [rbp+3A0h+var_1D0], rax
0x18000bcaf  cmp     [rbp+3A0h+var_1A8], 0
0x18000bcb6  jnz     loc_18000C096
0x18000bcbc  lea     rcx, [rbp+3A0h+var_190]; this
0x18000bcc3  call    ??1ConnectActivity@WnsCPLog@@QEAA@XZ; WnsCPLog::ConnectActivity::~ConnectActivity(void)
0x18000bcc8  lea     rcx, [rbp+3A0h+var_2E0]; this
0x18000bccf  call    ??1ConnectActivity@WnsCPLog@@QEAA@XZ; WnsCPLog::ConnectActivity::~ConnectActivity(void)
0x18000bcd4  mov     ecx, [rdi+28h]
0x18000bcd7  cmp     ecx, 1
0x18000bcda  jnz     loc_18000C0A7
0x18000bce0  mov     dword ptr [rdi+28h], 2
0x18000bce7  mov     esi, 1
0x18000bcec  mov     rcx, rdi; lpCriticalSection
0x18000bcef  call    cs:__imp_LeaveCriticalSection
0x18000bcf5  nop
0x18000bcf6  test    rbx, rbx
0x18000bcf9  jnz     loc_18000C11C
0x18000bcff  cmp     esi, 5
0x18000bd02  jnz     loc_18000BFA3
0x18000bd08  mov     rcx, r15
0x18000bd0b  call    ??$WnsWaitForConnect@AEA_K@WnsCPLog@@SAXAEA_K@Z; WnsCPLog::WnsWaitForConnect<unsigned __int64 &>(unsigned __int64 &)
0x18000bd10  xor     r8d, r8d; bAlertable
0x18000bd13  mov     edx, r12d; dwMilliseconds
0x18000bd16  mov     rcx, [rdi+30h]; hHandle
0x18000bd1a  call    cs:__imp_WaitForSingleObjectEx
0x18000bd20  cmp     eax, 102h
0x18000bd25  jz      loc_18000C1F7
0x18000bd2b  test    eax, eax
0x18000bd2d  jnz     loc_18000C18D
0x18000bd33  cmp     [rdi+1C0h], eax
0x18000bd39  jl      loc_18000BECC
0x18000bd3f  mov     rbx, [r15+8]
0x18000bd43  mov     rcx, rdi; lpCriticalSection
0x18000bd46  call    ?VerifyConnected@ConnectionStateMachine@Wns@@AEAAXXZ; Wns::ConnectionStateMachine::VerifyConnected(void)
0x18000bd4b  lea     rdx, [rsp+4A0h+var_470]
0x18000bd50  mov     rcx, [rdi+170h]
0x18000bd57  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x18000bd5c  nop
0x18000bd5d  mov     [rsp+4A0h+pv], r13
0x18000bd62  mov     rcx, qword ptr [rsp+4A0h+var_470]
  ... truncated ...
```
