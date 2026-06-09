# CTmImpIConnectionNotify::NewConnection(IConnection *,ICliqueOwner *,ulong,ulong *)

- ea: `0x1800490e0`
- end: `0x18004a76b`
- name: `?NewConnection@CTmImpIConnectionNotify@@UEAAJPEAUIConnection@@PEAUICliqueOwner@@KPEAK@Z`
- size: `5771`
- prototype: `int(CTmImpIConnectionNotify *__hidden this, struct IConnection *, struct ICliqueOwner *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `48`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180001058`
- `0x1800063b0`
- `0x18000f720`
- `0x18000f8dc`
- `0x180013e24`
- `0x1800240b0`
- `0x180025bec`
- `0x1800267a4`
- `0x180027874`
- `0x180028288`
- `0x1800299bc`
- `0x18003336c`
- `0x1800363dc`
- `0x1800373a4`
- `0x1800392ac`
- `0x18003b020`
- `0x18003bc3c`
- `0x18003c28c`
- `0x18003c7a4`
- `0x180044ce4`
- `0x180046c60`
- `0x1800487b0`
- `0x1800490e0`
- `0x180051af8`
- `0x180052718`
- `0x18005583c`
- `0x180057bb8`
- `0x18005a380`
- `0x18005c8e4`
- `0x18005d564`
- `0x18005e84c`
- `0x180060d6c`
- `0x180062e90`
- `0x180067a58`
- `0x180067ad0`
- `0x18006e928`
- `0x180075b44`
- `0x1800785d0`
- `0x180078818`
- `0x1800788cc`
- `0x18007be84`
- `0x18007e330`
- `0x18007e3ec`
- `0x1800809e0`
- `0x180080a3c`
- `0x1800849ac`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800492c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049324`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004943f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049480`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800494d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800496a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004979b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800497f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ebf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a164`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a49a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a5bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800492c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049324`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004943f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049480`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800494d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800496a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004979b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800497f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ebf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a164`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a49a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a5bc`

## string_xrefs

- `0x180049128`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180049277`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180049175`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18004a75e`: `com\complus\dtc\dtc\tm\src\tmxactrl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTmImpIConnectionNotify::NewConnection(
        CTmImpIConnectionNotify *this,
        struct IConnection *a2,
        struct ICliqueOwner *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v8; // r14
  int v9; // eax
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int *v14; // rax
  CTxEnlistment *v15; // rax
  CTxBeginner *v16; // rdx
  void ***v17; // r10
  void (__fastcall *v18)(void ***, CTxBeginner *, struct ICliqueOwner *, struct IConnection *); // rax
  void ***v19; // rcx
  unsigned int *v20; // rax
  CTxImport *v21; // rax
  CTxImport *v22; // rdx
  unsigned int *v23; // rax
  CTxReenlist *v24; // rax
  CTxSuperiorConn_Propagate *v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rcx
  unsigned int *v28; // rax
  unsigned int *v29; // rax
  CTxVoter *v30; // rdx
  __int64 *v31; // rcx
  __int64 v32; // rax
  unsigned int *v33; // rax
  unsigned int *v34; // rax
  unsigned int *v35; // r9
  unsigned int *v36; // rax
  __int64 *v37; // rax
  unsigned int *v38; // rax
  CDtcLuSuperiorConn_Create *v39; // rax
  unsigned int *v40; // rax
  CTxBeginner *v41; // rax
  unsigned __int16 *v42; // rax
  unsigned __int16 *v43; // r9
  void ***v44; // rax
  unsigned int *v45; // rax
  CGatewayTx *v46; // rax
  unsigned int *v47; // rax
  CTxPhaseZero *v48; // rax
  unsigned int *v49; // rax
  unsigned int *v50; // rax
  unsigned int *v51; // rax
  CDtcLuRecoveryByLu *v52; // rax
  void (__fastcall *v53)(__int64, CTxSuperiorConn_Propagate *, struct IConnection *); // rax
  unsigned int *v54; // rax
  CDtcLuRecoveryByDtc *v55; // rax
  unsigned int *v56; // rax
  CDtcLuRecovery *v57; // rax
  __int64 v58; // rcx
  unsigned __int16 *v59; // rax
  unsigned int *v60; // rax
  CGatewayInstance *v61; // rax
  __int64 v62; // rcx
  unsigned int *v63; // rax
  CXaSuperiorConn_Start *v64; // rax
  __int64 v65; // rcx
  unsigned __int16 *v66; // rax
  CConnectionHelper *v67; // rcx
  CTxBeginner *v68; // rax
  CTxBeginner *v69; // r10
  void ***v70; // rax
  unsigned __int16 *v71; // rax
  unsigned int *v72; // rax
  unsigned int *v73; // rax
  __int64 v74; // rcx
  unsigned __int16 *v75; // rax
  unsigned int *v76; // rax
  unsigned int *v77; // rax
  CGatewayInstanceScan *v78; // rax
  __int64 v79; // rcx
  unsigned int *v80; // rax
  CXaSuperiorConn_Open *v81; // rax
  unsigned int *v82; // rax
  CXaMigrate *v83; // rax
  CXaMigrate *v84; // r15
  __int64 v85; // rcx
  unsigned int *v86; // rax
  CXaSuperiorConn_XaBranch_Open *v87; // rax
  __int64 v88; // rcx
  unsigned int *v89; // rax
  CXaSuperiorConn_XaBranch_Start *v90; // rax
  unsigned int *v91; // rax
  CTxExport *v92; // rax
  unsigned int *v93; // rax
  CGatewayProtocol *v94; // r15
  unsigned int *v95; // rax
  CResourceManager *v96; // rax
  unsigned __int16 *v97; // rax
  unsigned int *v98; // rax
  CSnapshotFreeze *v99; // rax
  unsigned int *v100; // rax
  CXaMigrate *v101; // rax
  CXaMigrate *v102; // r15
  int v103; // eax
  __int64 v104; // rax
  void *v105; // r9
  __int64 v106; // r8
  CTmImpIConnectionNotify *v107; // rcx
  unsigned int *v108; // rax
  CTxSuperiorConn_Propagate *v109; // rax
  CTxBeginner *v110; // rax
  int v111; // eax
  unsigned int *v112; // rax
  CTxSubordinate *v113; // rdx
  unsigned int *v114; // rax
  unsigned int *v115; // rax
  unsigned int *v116; // rax
  int v117; // [rsp+20h] [rbp-48h]
  int v118; // [rsp+20h] [rbp-48h]
  size_t Size; // [rsp+28h] [rbp-40h]
  void *Src; // [rsp+38h] [rbp-30h]
  char *v121; // [rsp+40h] [rbp-28h]
  __int64 v122; // [rsp+48h] [rbp-20h]
  int v123; // [rsp+C8h] [rbp+60h] BYREF

  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
    1597,
    L"CTmImpIConnectionNotify::NewConnection",
    0,
    L"In: %x",
    a4);
  v123 = 0;
  v8 = a5;
  *(_DWORD *)a5 = -2147024882;
  v9 = (*(__int64 (__fastcall **)(struct IConnection *, int *))(*(_QWORD *)a2 + 120LL))(a2, &v123);
  if ( v9 >= 0 )
  {
    v11 = v123;
  }
  else
  {
    DELLog(g_pCoreTmInstance, 2u, 8u, 0x80001037, v9, 1, 0, 0, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1607);
    v11 = 1;
    v123 = 1;
  }
  v12 = 0;
  if ( a4 > 0x101 )
  {
    switch ( a4 )
    {
      case 0x102u:
        if ( (g_fInboundNetworkTxEnabled || g_fOutboundNetworkTxEnabled)
          && (gDtcSecurityLevel
           || isSchannelMutualAuth
           || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 136LL))(a2)) )
        {
          v116 = (unsigned int *)operator new(0xD0u);
          a5 = (unsigned __int16 *)v116;
          if ( !v116 )
            goto LABEL_18;
          v57 = CTxSuperiorConn_RedeliverCommit::CTxSuperiorConn_RedeliverCommit((CTxSuperiorConn_RedeliverCommit *)v116);
          goto LABEL_329;
        }
        break;
      case 0x103u:
        if ( (g_fInboundNetworkTxEnabled || g_fOutboundNetworkTxEnabled)
          && (gDtcSecurityLevel
           || isSchannelMutualAuth
           || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 136LL))(a2)) )
        {
          v114 = (unsigned int *)operator new(0x90u);
          v35 = v114;
          a5 = (unsigned __int16 *)v114;
          if ( !v114 )
            goto LABEL_18;
          v115 = v114 + 12;
          *((_QWORD *)v115 + 4) = &CImpIConnectionSink_Helper::`vftable';
          *((_QWORD *)v115 + 5) = v115;
          v115[2] = 0;
          *((_QWORD *)v115 + 3) = 0;
          *((_QWORD *)v115 + 2) = 0;
          v35[24] = 0;
          *((_QWORD *)v35 + 13) = 0;
          *(_QWORD *)v35 = &CTxJoinConnHelper_Template<CTxCheckAbort_State,CTxCheckAbort>::`vftable'{for `CJoinStatusSink_TxJoinConnHelper<CTxCheckAbort_State,CTxCheckAbort>'};
          *(_QWORD *)v115 = &CTxCheckAbort::`vftable'{for `CTxJoinConnHelperConnection<CTxCheckAbort_State,CTxCheckAbort>'};
          *((_QWORD *)v35 + 16) = 0;
          v35[34] = 0;
          v35[28] = 8226;
          v37 = (__int64 *)&g_CTxCheckAbort_State_WaitForInit;
          *((_QWORD *)v35 + 15) = &g_CTxCheckAbort_State_WaitForInit;
          goto LABEL_73;
        }
        break;
      case 0x104u:
        v111 = g_fOutboundNetworkTxEnabled;
        if ( g_fOutboundNetworkTxEnabled )
        {
          if ( gDtcSecurityLevel
            || isSchannelMutualAuth
            || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 136LL))(a2) )
          {
            v112 = (unsigned int *)HeapAlloc(g_CTxSubordinate_MemAlloc, 0, 0x328u);
            a5 = (unsigned __int16 *)v112;
            if ( v112 )
              v113 = CTxSubordinate::CTxSubordinate((CTxSubordinate *)v112);
            else
              v113 = 0;
            if ( v113 )
            {
              (*(void (__fastcall **)(_QWORD, CTxSubordinate *, struct IConnection *, struct ICliqueOwner *))(**((_QWORD **)v113 + 81) + 488LL))(
                *((_QWORD *)v113 + 81),
                v113,
                a2,
                a3);
              goto LABEL_20;
            }
            goto LABEL_18;
          }
          v111 = g_fOutboundNetworkTxEnabled;
        }
        *(_DWORD *)v8 = -2147024891;
        v12 = -2147467259;
        if ( !v111 )
        {
          v104 = (*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)g_pIDtcNameObject + 24LL))(g_pIDtcNameObject);
          v106 = 2147488524LL;
          goto LABEL_290;
        }
LABEL_291:
        if ( !(*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 136LL))(a2) )
          CTmImpIConnectionNotify::GenerateNotAnMSDTCEvent(v107, a2);
        goto LABEL_19;
      case 0x110u:
        v110 = (CTxBeginner *)operator new(0x50u);
        v69 = v110;
        a5 = (unsigned __int16 *)v110;
        if ( !v110 )
          goto LABEL_18;
        *((_QWORD *)v110 + 4) = &CImpIConnectionSink_Helper::`vftable';
        *((_QWORD *)v110 + 5) = v110;
        *((_DWORD *)v110 + 2) = 0;
        *((_QWORD *)v110 + 3) = 0;
        *((_QWORD *)v110 + 2) = 0;
        *(_QWORD *)v110 = &CTmClusterConfig::`vftable';
        v70 = g_CTmClusterConfig_State_WaitForInit;
        *((_QWORD *)v69 + 9) = 0;
        goto LABEL_185;
      default:
        goto LABEL_17;
    }
    *(_DWORD *)v8 = -2147024891;
    v12 = -2147467259;
    goto LABEL_291;
  }
  if ( a4 == 257 )
  {
    v103 = g_fInboundNetworkTxEnabled;
    if ( g_fInboundNetworkTxEnabled )
    {
      if ( gDtcSecurityLevel
        || isSchannelMutualAuth
        || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 136LL))(a2) )
      {
        v108 = (unsigned int *)HeapAlloc(g_CTxSuperiorConn_Propagate_MemAlloc, 0, 0x100u);
        a5 = (unsigned __int16 *)v108;
        if ( !v108 )
          goto LABEL_18;
        v109 = CTxSuperiorConn_Propagate::CTxSuperiorConn_Propagate((CTxSuperiorConn_Propagate *)v108);
        v25 = v109;
        if ( !v109 )
          goto LABEL_18;
        *((_QWORD *)v109 + 31) = a3;
        v26 = *((_QWORD *)v109 + 6);
LABEL_127:
        v53 = *(void (__fastcall **)(__int64, CTxSuperiorConn_Propagate *, struct IConnection *))(*(_QWORD *)v26 + 16LL);
        goto LABEL_332;
      }
      v103 = g_fInboundNetworkTxEnabled;
    }
    *(_DWORD *)v8 = -2147024891;
    v12 = -2147467259;
    if ( !v103 )
    {
      v104 = (*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)g_pIDtcNameObject + 24LL))(g_pIDtcNameObject);
      v106 = 2147488523LL;
LABEL_290:
      LODWORD(Size) = 0;
      a5 = *(unsigned __int16 **)(v104 + 8);
      DtcWriteToEventLoggerExW(2, 2, v106, v105, 1u, Size, &a5, 0, 1);
      goto LABEL_291;
    }
    goto LABEL_291;
  }
  if ( a4 <= 0x29 )
  {
    if ( a4 == 41 )
    {
      if ( v11 == 1 )
        goto LABEL_23;
      v60 = (unsigned int *)operator new(0x248u);
      a5 = (unsigned __int16 *)v60;
      if ( !v60 )
        goto LABEL_18;
      v61 = CGatewayInstance::CGatewayInstance((CGatewayInstance *)v60);
      v25 = v61;
      if ( !v61 )
        goto LABEL_18;
      *((_QWORD *)v61 + 62) = a3;
      v26 = *((_QWORD *)v61 + 5);
      goto LABEL_134;
    }
    if ( a4 <= 0x17 )
    {
      if ( a4 == 23 )
      {
        if ( !GetLocalDTCProfileIntExW((const unsigned __int16 *)0x101, L"SupportLuSubordinate", v10) )
          goto LABEL_17;
        if ( (v123 != 1 || g_fNetworkClientsEnabled) && g_fLuTransactionsDisabled != 1 )
        {
          v38 = (unsigned int *)operator new(0x168u);
          a5 = (unsigned __int16 *)v38;
          if ( v38 )
          {
            v39 = CDtcLuSuperiorConn_Create::CDtcLuSuperiorConn_Create((CDtcLuSuperiorConn_Create *)v38);
            if ( v39 )
            {
              CDtcLuSuperiorConn_Create::Init(v39, a2, a3);
              goto LABEL_20;
            }
          }
          goto LABEL_18;
        }
        goto LABEL_23;
      }
      if ( a4 <= 6 )
      {
        if ( a4 != 6 )
        {
          if ( a4 != 1 )
          {
            if ( a4 != 2 )
            {
              if ( a4 != 3 )
              {
                if ( a4 != 4 )
                {
                  if ( a4 != 5 )
                  {
LABEL_17:
                    *(_DWORD *)v8 = -2147024809;
LABEL_18:
                    v12 = -2147467259;
LABEL_19:
                    (*(void (__fastcall **)(struct ICliqueOwner *))(*(_QWORD *)a3 + 16LL))(a3);
LABEL_20:
                    LODWORD(v122) = *(_DWORD *)v8;
                    LODWORD(v121) = v12;
                    LODWORD(Src) = a4;
                    TraceStringInline(
                      3,
                      6,
                      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
                      2524,
                      L"CTmImpIConnectionNotify::NewConnection",
                      0,
                      L"Out: %x (%08x, %08x)",
                      Src,
                      v121,
                      v122);
                    return v12;
                  }
LABEL_264:
                  if ( v11 != 1 || g_fNetworkClientsEnabled )
                  {
                    v95 = (unsigned int *)operator new(0x130u);
                    a5 = (unsigned __int16 *)v95;
                    if ( v95 )
                    {
                      v96 = CResourceManager::CResourceManager((CResourceManager *)v95);
                      if ( v96 )
                      {
                        *((_QWORD *)v96 + 34) = a3;
                        (*(void (__fastcall **)(_QWORD, CResourceManager *, struct IConnection *, bool))(**((_QWORD **)v96 + 32) + 8LL))(
                          *((_QWORD *)v96 + 32),
                          v96,
                          a2,
                          a4 == 70);
                        goto LABEL_20;
                      }
                    }
                    goto LABEL_18;
                  }
                  goto LABEL_23;
                }
LABEL_254:
                if ( v11 != 1 || g_fNetworkClientsEnabled )
                {
                  v91 = (unsigned int *)HeapAlloc(g_CTxExport_MemAlloc, 0, 0xE8u);
                  a5 = (unsigned __int16 *)v91;
                  if ( v91 )
                  {
                    v92 = CTxExport::CTxExport((CTxExport *)v91);
                    if ( v92 )
                    {
                      CTxExport::Init(v92, a2, a3, a4 == 72);
                      goto LABEL_20;
                    }
                  }
                  goto LABEL_18;
                }
                goto LABEL_23;
              }
              if ( v11 == 1 && !g_fNetworkClientsEnabled )
                goto LABEL_23;
              v14 = (unsigned int *)HeapAlloc(g_CTxEnlistment_MemAlloc, 0, 0x150u);
              a5 = (unsigned __int16 *)v14;
              if ( !v14 )
                goto LABEL_18;
              v15 = CTxEnlistment::CTxEnlistment((CTxEnlistment *)v14);
              goto LABEL_26;
            }
            if ( v11 == 1 && !g_fNetworkClientsEnabled )
              goto LABEL_23;
            v20 = (unsigned int *)HeapAlloc(g_CTxImport_MemAlloc, 0, 0x128u);
            a5 = (unsigned __int16 *)v20;
            if ( !v20 )
              goto LABEL_18;
            v21 = CTxImport::CTxImport((CTxImport *)v20);
            v22 = v21;
            if ( !v21 )
              goto LABEL_18;
            v117 = 0;
LABEL_33:
            (*(void (__fastcall **)(_QWORD, CTxImport *, struct ICliqueOwner *, struct IConnection *, int))(**((_QWORD **)v21 + 24) + 152LL))(
              *((_QWORD *)v21 + 24),
              v22,
              a3,
              a2,
              v117);
            goto LABEL_20;
          }
LABEL_93:
          if ( v11 == 1 && !g_fNetworkClientsEnabled )
            goto LABEL_23;
          v40 = (unsigned int *)HeapAlloc(g_CTxBeginner_MemAlloc, 0, 0xC0u);
          a5 = (unsigned __int16 *)v40;
          if ( !v40 )
            goto LABEL_18;
          v41 = CTxBeginner::CTxBeginner((CTxBeginner *)v40);
          v16 = v41;
          if ( !v41 )
            goto LABEL_18;
          switch ( a4 )
          {
            case 1u:
              v118 = 0;
              break;
            case 0x28u:
              v118 = 1;
              break;
            case 0x39u:
              v19 = (void ***)*((_QWORD *)v41 + 16);
              v18 = (void (__fastcall *)(void ***, CTxBeginner *, struct ICliqueOwner *, struct IConnection *))(*v19)[4];
              goto LABEL_101;
            default:
              goto LABEL_20;
          }
          (*(void (__fastcall **)(_QWORD, CTxBeginner *, struct ICliqueOwner *, struct IConnection *, int))(**((_QWORD **)v41 + 16) + 24LL))(
            *((_QWORD *)v41 + 16),
            v41,
            a3,
            a2,
            v118);
          goto LABEL_20;
        }
        if ( v11 == 1 && !g_fNetworkClientsEnabled )
          goto LABEL_23;
        v23 = (unsigned int *)operator new(0x178u);
        a5 = (unsigned __int16 *)v23;
        if ( !v23 )
          goto LABEL_18;
        v24 = CTxReenlist::CTxReenlist((CTxReenlist *)v23);
        v25 = v24;
        if ( !v24 )
          goto LABEL_18;
        *((_QWORD *)v24 + 45) = a3;
        v26 = *((_QWORD *)v24 + 40);
        goto LABEL_331;
      }
      if ( a4 != 7 )
      {
        switch ( a4 )
        {
          case 9u:
            if ( v11 == 1 && !g_fNetworkClientsEnabled )
              goto LABEL_23;
            v33 = (unsigned int *)HeapAlloc(g_CTxVoter_MemAlloc, 0, 0xD8u);
            a5 = (unsigned __int16 *)v33;
            if ( v33 )
              v30 = CTxVoter::CTxVoter((CTxVoter *)v33);
            else
              v30 = 0;
            if ( !v30 )
              goto LABEL_18;
            *((_QWORD *)v30 + 22) = a3;
            v31 = (__int64 *)*((_QWORD *)v30 + 21);
            break;
          case 0x11u:
            if ( v11 == 1 && !g_fNetworkClientsEnabled )
              goto LABEL_23;
            v29 = (unsigned int *)HeapAlloc(g_CTxAssociate_MemAlloc, 0, 0x108u);
            a5 = (unsigned __int16 *)v29;
            if ( v29 )
              v30 = CTxAssociate::CTxAssociate((CTxAssociate *)v29);
            else
              v30 = 0;
            if ( !v30 )
              goto LABEL_18;
            *((_QWORD *)v30 + 15) = a3;
            v31 = (__int64 *)*((_QWORD *)v30 + 14);
            break;
          case 0x16u:
            if ( v11 == 1 && !g_fNetworkClientsEnabled || g_fLuTransactionsDisabled == 1 )
              goto LABEL_23;
            if ( !byte_180165D30 )
            {
              if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)tlgKeywordOn(257) )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v27,
                  (__int64)&byte_180147C6F);
              byte_180165D30 = 1;
            }
            v28 = (unsigned int *)HeapAlloc(g_CDtcLuRmEnlistment_MemAlloc, 0, 0x138u);
            a5 = (unsigned __int16 *)v28;
            if ( !v28 )
              goto LABEL_18;
            v15 = CDtcLuRmEnlistment::CDtcLuRmEnlistment((CDtcLuRmEnlistment *)v28);
LABEL_26:
            v16 = v15;
            if ( !v15 )
              goto LABEL_18;
            v17 = (void ***)*((_QWORD *)v15 + 29);
            v18 = (void (__fastcall *)(void ***, CTxBeginner *, struct ICliqueOwner *, struct IConnection *))(*v17)[55];
            v19 = v17;
LABEL_101:
            v18(v19, v16, a3, a2);
            goto LABEL_20;
          default:
            goto LABEL_17;
        }
        v32 = *v31;
LABEL_76:
        (*(void (__fastcall **)(__int64 *, CTxVoter *, struct IConnection *))(v32 + 8))(v31, v30, a2);
        goto LABEL_20;
      }
      if ( v11 == 1 && !g_fNetworkAdminEnabled )
        goto LABEL_23;
      v34 = (unsigned int *)operator new(0x90u);
      v35 = v34;
      a5 = (unsigned __int16 *)v34;
      if ( !v34 )
        goto LABEL_18;
      v36 = v34 + 12;
      *((_QWORD *)v36 + 4) = &CImpIConnectionSink_Helper::`vftable';
      *((_QWORD *)v36 + 5) = v36;
      v36[2] = 0;
      *((_QWORD *)v36 + 3) = 0;
      *((_QWORD *)v36 + 2) = 0;
      *(_QWORD *)v35 = &CTxResolve::`vftable'{for `CJoinStatusSink_TxJoinConnHelper<CTxResolve_State,CTxResolve>'};
      *(_QWORD *)v36 = &CTxJoinConnHelperConnection<CDtcLuSuperiorConn_Creating_State,CDtcLuSuperiorConn_Creating>::`vftable';
      v35[35] = 4213;
      v37 = (__int64 *)&g_CTxResolve_State_WaitForInit;
      goto LABEL_72;
    }
    if ( a4 == 24 )
    {
      if ( (v11 != 1 || g_fNetworkClientsEnabled) && g_fLuTransactionsDisabled != 1 )
      {
        if ( !byte_180165D30 )
        {
          if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)tlgKeywordOn(a4 - 24) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v58,
              (__int64)&byte_180147C4F);
          byte_180165D30 = 1;
        }
        v59 = (unsigned __int16 *)operator new(0x98u);
        a5 = v59;
        if ( v59 )
        {
          *((_QWORD *)v59 + 4) = &CImpIConnectionSink_Helper::`vftable';
          *((_QWORD *)v59 + 5) = v59;
          *((_DWORD *)v59 + 2) = 0;
          *((_QWORD *)v59 + 3) = 0;
          *((_QWORD *)v59 + 2) = 0;
          *(_QWORD *)v59 = &CDtcLuConfigure::`vftable'{for `CDtcLuConfigureConnection'};
          *((_QWORD *)v59 + 6) = &CJoinStatusSink_DtcLuConfigure::`vftable';
          *((_QWORD *)v59 + 12) = &CDtcLuConfigure::`vftable'{for `CImpIDtcLuToDtcLuConfigureAdd'};
          *((_QWORD *)v59 + 13) = &CDtcLuConfigure::`vftable'{for `CImpIDtcLuToDtcLuConfigureDelete'};
          *((_QWORD *)v59 + 18) = 0;
          *((_QWORD *)v59 + 15) = 0;
          *((_DWORD *)v59 + 34) = 0;
          *((_QWORD *)v59 + 16) = 0;
          *((_QWORD *)v59 + 14) = g_CDtcLuConfigure_State_WaitForInit;
          *((_QWORD *)v59 + 15) = a3;
          (*((void (__fastcall **)(void ***, unsigned __int16 *, struct IConnection *))g_CDtcLuConfigure_State_WaitForInit[0]
           + 7))(
            g_CDtcLuConfigure_State_WaitForInit,
            v59,
            a2);
          goto LABEL_20;
        }
        goto LABEL_18;
      }
      goto LABEL_23;
    }
    if ( a4 != 25 )
    {
      if ( a4 != 32 )
      {
        if ( a4 != 33 )
        {
          switch ( a4 )
          {
            case '"':
              if ( v11 == 1 && !g_fNetworkAdminEnabled )
                goto LABEL_23;
              v49 = (unsigned int *)operator new(0x88u);
              v35 = v49;
              a5 = (unsigned __int16 *)v49;
              if ( !v49 )
                goto LABEL_18;
              v50 = v49 + 12;
              *((_QWORD *)v50 + 4) = &CImpIConnectionSink_Helper::`vftable';
              *((_QWORD *)v50 + 5) = v50;
              v50[2] = 0;
              *((_QWORD *)v50 + 3) = 0;
              *((_QWORD *)v50 + 2) = 0;
              v35[24] = 0;
              *((_QWORD *)v35 + 13) = 0;
              *(_QWORD *)v35 = &CTxResolve::`vftable'{for `CJoinStatusSink_TxJoinConnHelper<CTxResolve_State,CTxResolve>'};
              *(_QWORD *)v50 = &CTxJoinConnHelperConnection<CDtcLuSuperiorConn_Creating_State,CDtcLuSuperiorConn_Creating>::`vftable';
              *((_QWORD *)v35 + 15) = 0;
              v35[32] = 0;
              v35[33] = 18179;
              v37 = (__int64 *)&g_CTxGetDetails_State_WaitForInit;
              *((_QWORD *)v35 + 14) = &g_CTxGetDetails_State_WaitForInit;
              *((_QWORD *)v35 + 15) = a3;
              goto LABEL_75;
            case '$':
              if ( v11 == 1 && !g_fNetworkClientsEnabled )
                goto LABEL_23;
              v47 = (unsigned int *)HeapAlloc(g_CTxPhaseZero_MemAlloc, 0, 0xD0u);
              a5 = (unsigned __int16 *)v47;
              if ( !v47 )
                goto LABEL_18;
              v48 = CTxPhaseZero::CTxPhaseZero((CTxPhaseZero *)v47);
              v25 = v48;
              if ( !v48 )
                goto LABEL_18;
              *((_QWORD *)v48 + 22) = a3;
              v26 = *((_QWORD *)v48 + 21);
              break;
            case '%':
              if ( v11 == 1 )
                goto LABEL_23;
              v45 = (unsigned int *)HeapAlloc(g_CGatewayTx_MemAlloc, 0, 0xE0u);
              a5 = (unsigned __int16 *)v45;
              if ( !v45 )
                goto LABEL_18;
              v46 = CGatewayTx::CGatewayTx((CGatewayTx *)v45);
              v25 = v46;
              if ( !v46 )
                goto LABEL_18;
              *((_QWORD *)v46 + 16) = a3;
              v26 = *((_QWORD *)v46 + 15);
              break;
            case '\'':
              if ( v11 == 1 )
                goto LABEL_23;
              v42 = (unsigned __int16 *)operator new(0x88u);
              v43 = v42;
              a5 = v42;
              if ( !v42 )
                goto LABEL_18;
              *((_QWORD *)v42 + 4) = &CImpIConnectionSink_Helper::`vftable';
              *((_QWORD *)v42 + 5) = v42;
              *((_DWORD *)v42 + 2) = 0;
              *((_QWORD *)v42 + 3) = 0;
              *((_QWORD *)v42 + 2) = 0;
              *(_QWORD *)v42 = &CGatewayTxCrashRecovery::`vftable';
              *((_DWORD *)v42 + 16) = 0;
              *((_QWORD *)v42 + 13) = 0;
              v44 = g_CGatewayTxCrashRecovery_State_WaitForInit;
LABEL_106:
              *((_QWORD *)v43 + 7) = 0;
              *((_QWORD *)v43 + 6) = v44;
              if ( v43 )
              {
                *((_QWORD *)v43 + 7) = a3;
                ((void (__fastcall *)(void ***, unsigned __int16 *, struct IConnection *))(*v44)[2])(v44, v43, a2);
                goto LABEL_20;
              }
              goto LABEL_18;
            case '(':
              goto LABEL_93;
            default:
              goto LABEL_17;
          }
LABEL_331:
          v53 = *(void (__fastcall **)(__int64, CTxSuperiorConn_Propagate *, struct IConnection *))(*(_QWORD *)v26 + 8LL);
          goto LABEL_332;
        }
        if ( v11 == 1 && !g_fNetworkClientsEnabled || g_fLuTransactionsDisabled == 1 )
          goto LABEL_23;
        v51 = (unsigned int *)operator new(0x180u);
        a5 = (unsigned __int16 *)v51;
        if ( !v51 )
          goto LABEL_18;
        v52 = CDtcLuRecoveryByLu::CDtcLuRecoveryByLu((CDtcLuRecoveryByLu *)v51);
        v25 = v52;
        if ( !v52 )
          goto LABEL_18;
        *((_QWORD *)v52 + 27) = a3;
        v26 = *((_QWORD *)v52 + 26);
        goto LABEL_127;
      }
      if ( v11 == 1 && !g_fNetworkClientsEnabled || g_fLuTransactionsDisabled == 1 )
        goto LABEL_23;
      v54 = (unsigned int *)operator new(0x198u);
      a5 = (unsigned __int16 *)v54;
      if ( !v54 )
        goto LABEL_18;
      v55 = CDtcLuRecoveryByDtc::CDtcLuRecoveryByDtc((CDtcLuRecoveryByDtc *)v54);
      v25 = v55;
      if ( !v55 )
        goto LABEL_18;
      *((_QWORD *)v55 + 33) = a3;
      v26 = *((_QWORD *)v55 + 32);
LABEL_134:
      v53 = *(void (__fastcall **)(__int64, CTxSuperiorConn_Propagate *, struct IConnection *))(*(_QWORD *)v26 + 40LL);
      goto LABEL_332;
    }
    if ( v11 == 1 && !g_fNetworkClientsEnabled || g_fLuTransactionsDisabled == 1 )
      goto LABEL_23;
    v56 = (unsigned int *)operator new(0xE0u);
    a5 = (unsigned __int16 *)v56;
    if ( !v56 )
      goto LABEL_18;
    v57 = CDtcLuRecovery::CDtcLuRecovery((CDtcLuRecovery *)v56);
LABEL_329:
    v25 = v57;
    if ( !v57 )
      goto LABEL_18;
    v26 = *((_QWORD *)v57 + 23);
    *((_QWORD *)v57 + 24) = a3;
    goto LABEL_331;
  }
  if ( a4 > 0x42 )
  {
    switch ( a4 )
    {
      case 'C':
        if ( !g_fXaTransactionsEnabled )
          goto LABEL_23;
        v100 = (unsigned int *)operator new(0x130u);
        a5 = (unsigned __int16 *)v100;
        if ( v100 )
        {
          v101 = CXaMigrate::CXaMigrate((CXaMigrate *)v100);
          v102 = v101;
          if ( v101 )
          {
            *((_QWORD *)v101 + 12) = a3;
            CConnectionHelper::InitSubordinate(v101, a2);
            *((_DWORD *)v102 + 32) = 0;
            goto LABEL_20;
          }
        }
        break;
      case 'D':
        if ( g_fSnapshotSecurityDisabled
          || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 144LL))(a2) )
        {
          v98 = (unsigned int *)operator new(0x108u);
          a5 = (unsigned __int16 *)v98;
          if ( v98 )
          {
            v99 = CSnapshotFreeze::CSnapshotFreeze((CSnapshotFreeze *)v98);
            if ( v99 )
            {
              CSnapshotFreeze::Init(v99, a2, a3);
              goto LABEL_20;
            }
          }
          goto LABEL_18;
        }
        goto LABEL_23;
      case 'E':
        if ( g_fSnapshotSecurityDisabled
          || (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 144LL))(a2) )
        {
          v97 = (unsigned __int16 *)operator new(0x98u);
          a5 = v97;
          if ( v97 )
          {
            *((_QWORD *)v97 + 4) = &CImpIConnectionSink_Helper::`vftable';
            *((_QWORD *)v97 + 5) = v97;
            *((_DWORD *)v97 + 2) = 0;
            *((_QWORD *)v97 + 3) = 0;
            *((_QWORD *)v97 + 2) = 0;
            *(_QWORD *)v97 = &CSnapshotThaw::`vftable'{for `CConnectionHelper'};
            *((_QWORD *)v97 + 6) = &CSnapshotThaw::`vftable'{for `ICliqueCreateSink'};
            *((_QWORD *)v97 + 7) = &CSnapshotThaw::`vftable'{for `CJoinStatusSink'};
            *((_QWORD *)v97 + 13) = 0;
            *((_QWORD *)v97 + 14) = 0;
            *((_DWORD *)v97 + 30) = 0;
            *((_QWORD *)v97 + 16) = 0;
            *((_QWORD *)v97 + 17) = 0;
            *((_QWORD *)v97 + 18) = 0;
            CSnapshotThaw::Init((CSnapshotThaw *)v97, a2, a3);
            goto LABEL_20;
          }
          goto LABEL_18;
        }
        goto LABEL_23;
      case 'F':
        goto LABEL_264;
      case 'G':
        v93 = (unsigned int *)operator new(0xA8u);
        a5 = (unsigned __int16 *)v93;
        if ( v93 )
          v94 = CGatewayProtocol::CGatewayProtocol((CGatewayProtocol *)v93);
        else
          v94 = 0;
        if ( v94 )
        {
          CGatewayProtocol::Init(v94, a3, a2);
          CGatewayProtocol::Release(v94);
          goto LABEL_20;
        }
        goto LABEL_18;
      case 'H':
        goto LABEL_254;
      case 'P':
        if ( g_fXaTransactionsEnabled )
        {
          if ( !byte_180165D31 )
          {
            if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v88,
                (__int64)&unk_180147CC0);
            byte_180165D31 = 1;
          }
          v89 = (unsigned int *)operator new(0x1D8u);
          a5 = (unsigned __int16 *)v89;
          if ( v89 )
          {
            v90 = CXaSuperiorConn_XaBranch_Start::CXaSuperiorConn_XaBranch_Start((CXaSuperiorConn_XaBranch_Start *)v89);
            if ( v90 )
            {
              CXaSuperiorConn_XaBranch_Start::Init(v90, a2, a3);
              goto LABEL_20;
            }
          }
          goto LABEL_18;
        }
        goto LABEL_23;
      case 'Q':
        if ( g_fXaTransactionsEnabled )
        {
          if ( !byte_180165D31 )
          {
            if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v85,
                (__int64)&byte_180147C8F);
            byte_180165D31 = 1;
          }
          v86 = (unsigned int *)operator new(0x1D8u);
          a5 = (unsigned __int16 *)v86;
          if ( v86 )
          {
            v87 = CXaSuperiorConn_XaBranch_Open::CXaSuperiorConn_XaBranch_Open((CXaSuperiorConn_XaBranch_Open *)v86);
            if ( v87 )
            {
              CXaSuperiorConn_XaBranch_Open::Init(v87, a2, a3);
              goto LABEL_20;
            }
          }
          goto LABEL_18;
        }
        goto LABEL_23;
      case 'R':
        if ( !g_fXaTransactionsEnabled )
        {
LABEL_23:
          *(_DWORD *)v8 = -2147024891;
          goto LABEL_18;
        }
        v82 = (unsigned int *)operator new(0x130u);
        a5 = (unsigned __int16 *)v82;
        if ( v82 )
        {
          v83 = CXaMigrate::CXaMigrate((CXaMigrate *)v82);
          v84 = v83;
          if ( v83 )
          {
            *((_QWORD *)v83 + 12) = a3;
            CConnectionHelper::InitSubordinate(v83, a2);
            *((_DWORD *)v84 + 32) = 1;
            goto LABEL_20;
          }
        }
        break;
      default:
        goto LABEL_17;
    }
    goto LABEL_282;
  }
  switch ( a4 )
  {
    case 'B':
      if ( g_fXaTransactionsEnabled )
      {
        if ( !byte_180165D31 )
        {
          if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v79,
              (__int64)byte_180147CF1);
          byte_180165D31 = 1;
        }
        v80 = (unsigned int *)operator new(0x138u);
        a5 = (unsigned __int16 *)v80;
        if ( v80 )
        {
          v81 = CXaSuperiorConn_Open::CXaSuperiorConn_Open((CXaSuperiorConn_Open *)v80);
          if ( v81 )
          {
            CXaSuperiorConn_Open::Init(v81, a2, a3);
            goto LABEL_20;
          }
        }
        goto LABEL_18;
      }
      goto LABEL_23;
    case '0':
      if ( v11 == 1 )
        goto LABEL_23;
      v77 = (unsigned int *)operator new(0xE8u);
      a5 = (unsigned __int16 *)v77;
      if ( !v77 )
        goto LABEL_18;
      v78 = CGatewayInstanceScan::CGatewayInstanceScan((CGatewayInstanceScan *)v77);
      v25 = v78;
      if ( !v78 )
        goto LABEL_18;
      *((_QWORD *)v78 + 20) = a3;
      v26 = *((_QWORD *)v78 + 5);
      goto LABEL_127;
    case '3':
      if ( v11 == 1 && !g_fNetworkClientsEnabled )
        goto LABEL_23;
      v76 = (unsigned int *)HeapAlloc(g_CTxImport_MemAlloc, 0, 0x128u);
      a5 = (unsigned __int16 *)v76;
      if ( !v76 )
        goto LABEL_18;
      v21 = CTxImport::CTxImport((CTxImport *)v76);
      v22 = v21;
      if ( !v21 )
        goto LABEL_18;
      v117 = 1;
      goto LABEL_33;
    case '5':
      if ( !byte_180165D32 )
      {
        if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v74,
            (__int64)byte_180147C31);
        byte_180165D32 = 1;
      }
      v75 = (unsigned __int16 *)operator new(0x50u);
      v43 = v75;
      a5 = v75;
      if ( !v75 )
        goto LABEL_18;
      *((_QWORD *)v75 + 4) = &CImpIConnectionSink_Helper::`vftable';
      *((_QWORD *)v75 + 5) = v75;
      *((_DWORD *)v75 + 2) = 0;
      *((_QWORD *)v75 + 3) = 0;
      *((_QWORD *)v75 + 2) = 0;
      *(_QWORD *)v75 = &CGetSecurityFlagsConnection::`vftable';
      *((_QWORD *)v75 + 8) = 0;
      *((_QWORD *)v75 + 9) = 0;
      v44 = g_CGetSecurityFlags_State_WaitForInit;
      goto LABEL_106;
    case '6':
      if ( v11 == 1 && !g_fNetworkAdminEnabled )
        goto LABEL_23;
      v72 = (unsigned int *)operator new(0x90u);
      v35 = v72;
      a5 = (unsigned __int16 *)v72;
      if ( !v72 )
        goto LABEL_18;
      v73 = v72 + 12;
      *((_QWORD *)v73 + 4) = &CImpIConnectionSink_Helper::`vftable';
      *((_QWORD *)v73 + 5) = v73;
      v73[2] = 0;
      *((_QWORD *)v73 + 3) = 0;
      *((_QWORD *)v73 + 2) = 0;
      *(_QWORD *)v35 = &CTxResolve::`vftable'{for `CJoinStatusSink_TxJoinConnHelper<CTxResolve_State,CTxResolve>'};
      *(_QWORD *)v73 = &CTxJoinConnHelperConnection<CDtcLuSuperiorConn_Creating_State,CDtcLuSuperiorConn_Creating>::`vftable';
      v35[35] = 8450;
      v37 = (__int64 *)&g_CTxDump_State_WaitForInit;
LABEL_72:
      v35[34] = 0;
      *((_QWORD *)v35 + 16) = 0;
      *((_QWORD *)v35 + 13) = 0;
      v35[24] = 0;
      *((_QWORD *)v35 + 14) = v37;
LABEL_73:
      if ( !v35 )
        goto LABEL_18;
      *((_QWORD *)v35 + 16) = a3;
LABEL_75:
      v31 = v37;
      v32 = *v37;
      v30 = (CTxVoter *)v35;
      goto LABEL_76;
  }
  if ( a4 != 56 )
  {
    if ( a4 == 57 )
      goto LABEL_93;
    if ( a4 != 61 )
    {
      if ( a4 != 64 )
      {
        if ( a4 != 65 )
          goto LABEL_17;
        if ( !g_fXaTransactionsEnabled )
          goto LABEL_23;
        if ( !byte_180165D31 )
        {
          if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v62,
              (__int64)word_180147D22);
          byte_180165D31 = 1;
        }
        v63 = (unsigned int *)operator new(0xF0u);
        a5 = (unsigned __int16 *)v63;
        if ( !v63 )
          goto LABEL_18;
        v64 = CXaSuperiorConn_Start::CXaSuperiorConn_Start((CXaSuperiorConn_Start *)v63);
        v25 = v64;
        if ( !v64 )
          goto LABEL_18;
        *((_QWORD *)v64 + 29) = a3;
        v26 = *((_QWORD *)v64 + 6);
        v53 = *(void (__fastcall **)(__int64, CTxSuperiorConn_Propagate *, struct IConnection *))(*(_QWORD *)v26 + 24LL);
LABEL_332:
        v53(v26, v25, a2);
        goto LABEL_20;
      }
      if ( !g_fXaTransactionsEnabled )
        goto LABEL_23;
      if ( !byte_180165D31 )
      {
        if ( (unsigned int)dword_180152CE0 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v65,
            (__int64)byte_180147D53);
        byte_180165D31 = 1;
      }
      v66 = (unsigned __int16 *)operator new(0xB0u);
      a5 = v66;
      if ( !v66 )
        goto LABEL_18;
      *((_QWORD *)v66 + 10) = &CImpIConnectionSink_Helper::`vftable';
      *((_QWORD *)v66 + 11) = v66 + 24;
      *((_DWORD *)v66 + 14) = 0;
      *((_QWORD *)v66 + 9) = 0;
      *((_QWORD *)v66 + 8) = 0;
      *((_QWORD *)v66 + 6) = &CXaControlConnection::`vftable';
      *((_QWORD *)v66 + 12) = v66;
      *((_DWORD *)v66 + 26) = 2;
      *((_QWORD *)v66 + 14) = &CJoinStatusSink_XaControl::`vftable';
      *((_QWORD *)v66 + 20) = v66;
      *((_QWORD *)v66 + 4) = 0;
      *((_QWORD *)v66 + 5) = 0;
      *(_DWORD *)v66 = 3;
      *((_QWORD *)v66 + 3) = 0;
      *((_QWORD *)v66 + 21) = 0;
      if ( *(_DWORD *)v66 != 3 )
        CTmTrace::InvalidValue(
          (CTmTrace *)&CJoinStatusSink_XaControl::`vftable',
          "com\\complus\\dtc\\dtc\\tm\\src\\tmxactrl.cpp",
          491,
          *(_DWORD *)v66);
      *((_QWORD *)v66 + 4) = a3;
      *(_DWORD *)v66 = 1;
      v67 = (CConnectionHelper *)(v66 + 24);
LABEL_193:
      CConnectionHelper::InitSubordinate(v67, a2);
      goto LABEL_20;
    }
    v68 = (CTxBeginner *)operator new(0x48u);
    v69 = v68;
    a5 = (unsigned __int16 *)v68;
    if ( !v68 )
      goto LABEL_18;
    *((_QWORD *)v68 + 4) = &CImpIConnectionSink_Helper::`vftable';
    *((_QWORD *)v68 + 5) = v68;
    *((_DWORD *)v68 + 2) = 0;
    *((_QWORD *)v68 + 3) = 0;
    *((_QWORD *)v68 + 2) = 0;
    *(_QWORD *)v68 = &CTmClusterConfig::`vftable';
    v70 = g_CGetExtendedWhereabouts_State_WaitForInit;
LABEL_185:
    *((_QWORD *)v69 + 8) = 0;
    *((_QWORD *)v69 + 7) = 0;
    *((_QWORD *)v69 + 6) = v70;
    if ( !v69 )
      goto LABEL_18;
    v19 = v70;
    v16 = v69;
    v18 = (void (__fastcall *)(void ***, CTxBeginner *, struct ICliqueOwner *, struct IConnection *))**v70;
    goto LABEL_101;
  }
  v71 = (unsigned __int16 *)operator new(0x38u);
  a5 = v71;
  if ( v71 )
  {
    *((_QWORD *)v71 + 4) = &CImpIConnectionSink_Helper::`vftable';
    *((_QWORD *)v71 + 5) = v71;
    *((_DWORD *)v71 + 2) = 0;
    *((_QWORD *)v71 + 3) = 0;
    *((_QWORD *)v71 + 2) = 0;
    *(_QWORD *)v71 = &CTxSetTxTimeout::`vftable';
    *((_QWORD *)v71 + 6) = 0;
    *((_QWORD *)v71 + 6) = a3;
    v67 = (CConnectionHelper *)v71;
    goto LABEL_193;
  }
LABEL_282:
  (*(void (__fastcall **)(struct ICliqueOwner *))(*(_QWORD *)a3 + 16LL))(a3);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800490e0  push    rbp
0x1800490e2  push    rbx
0x1800490e3  push    rsi
0x1800490e4  push    rdi
0x1800490e5  push    r12
0x1800490e7  push    r13
0x1800490e9  push    r14
0x1800490eb  push    r15
0x1800490ed  mov     rbp, rsp
0x1800490f0  sub     rsp, 68h
0x1800490f4  mov     r12d, r9d
0x1800490f7  mov     rsi, r8
0x1800490fa  mov     rdi, rdx
0x1800490fd  mov     dword ptr [rsp+68h+Src], r9d
0x180049102  lea     rax, aInX; "In: %x"
0x180049109  mov     [rsp+68h+var_38], rax
0x18004910e  xor     r13d, r13d
0x180049111  mov     [rsp+68h+Size], r13
0x180049116  lea     rax, aCtmimpiconnect; "CTmImpIConnectionNotify::NewConnection"
0x18004911d  mov     qword ptr [rsp+68h+var_48], rax
0x180049122  mov     r9d, 63Dh
0x180049128  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x18004912f  lea     edx, [r13+6]
0x180049133  lea     ecx, [rdx-3]
0x180049136  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004913b  mov     [rbp+arg_18], r13d
0x18004913f  mov     r14, [rbp+arg_20]
0x180049143  mov     dword ptr [r14], 8007000Eh
0x18004914a  mov     rax, [rdi]
0x18004914d  lea     rdx, [rbp+arg_18]
0x180049151  mov     rcx, rdi
0x180049154  mov     rax, [rax+78h]
0x180049158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004915d  lea     r15d, [r13+1]
0x180049161  test    eax, eax
0x180049163  jns     short loc_1800491AE
0x180049165  lea     edx, [r13+2]; unsigned __int16
0x180049169  lea     r8d, [r13+8]; unsigned __int16
0x18004916d  mov     dword ptr [rsp+68h+var_20], 647h; int
0x180049175  lea     rcx, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x18004917c  mov     [rsp+68h+var_28], rcx; char *
0x180049181  mov     [rsp+68h+Src], r13; void *
0x180049186  mov     dword ptr [rsp+68h+var_38], r13d; unsigned int
0x18004918b  mov     dword ptr [rsp+68h+Size], r15d; int
0x180049190  mov     dword ptr [rsp+68h+var_48], eax; int
0x180049194  mov     r9d, 80001037h; unsigned int
0x18004919a  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; struct ITmInstance *
0x1800491a1  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x1800491a6  mov     eax, r15d
0x1800491a9  mov     [rbp+arg_18], eax
0x1800491ac  jmp     short loc_1800491B1
0x1800491ae  mov     eax, [rbp+arg_18]
0x1800491b1  mov     ebx, r13d
0x1800491b4  mov     ecx, 101h; unsigned __int16 *
0x1800491b9  cmp     r12d, ecx
0x1800491bc  ja      loc_18004A4D1
0x1800491c2  jz      loc_18004A3C5
0x1800491c8  cmp     r12d, 29h ; ')'
0x1800491cc  ja      loc_180049B08
0x1800491d2  jz      loc_180049AC4
0x1800491d8  cmp     r12d, 17h
0x1800491dc  ja      loc_18004962D
0x1800491e2  jz      loc_1800495BE
0x1800491e8  cmp     r12d, 6
0x1800491ec  ja      loc_1800493B9
0x1800491f2  jz      loc_180049369
0x1800491f8  mov     ecx, r12d
0x1800491fb  sub     ecx, r15d
0x1800491fe  jz      loc_180049681
0x180049204  sub     ecx, r15d
0x180049207  jz      loc_180049307
0x18004920d  sub     ecx, r15d
0x180049210  jz      loc_18004929E
0x180049216  sub     ecx, r15d
0x180049219  jz      loc_18004A143
0x18004921f  cmp     ecx, r15d
0x180049222  jz      loc_18004A1ED
0x180049228  mov     dword ptr [r14], 80070057h
0x18004922f  mov     ebx, 80004005h
0x180049234  mov     rax, [rsi]
0x180049237  mov     rcx, rsi
0x18004923a  mov     rax, [rax+10h]
0x18004923e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049243  mov     r9d, [r14]
0x180049246  mov     dword ptr [rsp+68h+var_20], r9d
0x18004924b  mov     dword ptr [rsp+68h+var_28], ebx
0x18004924f  mov     dword ptr [rsp+68h+Src], r12d
0x180049254  lea     rax, aOutX08x08x; "Out: %x (%08x, %08x)"
0x18004925b  mov     [rsp+68h+var_38], rax
0x180049260  mov     [rsp+68h+Size], r13
0x180049265  lea     rax, aCtmimpiconnect; "CTmImpIConnectionNotify::NewConnection"
0x18004926c  mov     qword ptr [rsp+68h+var_48], rax
0x180049271  mov     r9d, 9DCh
0x180049277  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x18004927e  mov     edx, 6
0x180049283  lea     ecx, [rdx-3]
0x180049286  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004928b  mov     eax, ebx
0x18004928d  add     rsp, 68h
0x180049291  pop     r15
0x180049293  pop     r14
0x180049295  pop     r13
0x180049297  pop     r12
0x180049299  pop     rdi
0x18004929a  pop     rsi
0x18004929b  pop     rbx
0x18004929c  pop     rbp
0x18004929d  retn
0x18004929e  cmp     eax, r15d
0x1800492a1  jnz     short loc_1800492B8
0x1800492a3  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x1800492aa  jnz     short loc_1800492B8
0x1800492ac  mov     dword ptr [r14], 80070005h
0x1800492b3  jmp     loc_18004922F
0x1800492b8  xor     edx, edx; dwFlags
0x1800492ba  mov     r8d, 150h; dwBytes
0x1800492c0  mov     rcx, cs:?g_CTxEnlistment_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x1800492c7  call    cs:__imp_HeapAlloc
0x1800492cd  mov     [rbp+arg_20], rax
0x1800492d1  test    rax, rax
0x1800492d4  jz      loc_18004922F
0x1800492da  mov     rcx, rax; this
0x1800492dd  call    ??0CTxEnlistment@@QEAA@XZ; CTxEnlistment::CTxEnlistment(void)
0x1800492e2  mov     rdx, rax
0x1800492e5  test    rax, rax
0x1800492e8  jz      loc_18004922F
0x1800492ee  mov     r10, [rax+0E8h]
0x1800492f5  mov     rcx, [r10]
0x1800492f8  mov     rax, [rcx+1B8h]
0x1800492ff  mov     rcx, r10
0x180049302  jmp     loc_1800496F5
0x180049307  cmp     eax, r15d
0x18004930a  jnz     short loc_180049315
0x18004930c  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x180049313  jz      short loc_1800492AC
0x180049315  xor     edx, edx; dwFlags
0x180049317  mov     r8d, 128h; dwBytes
0x18004931d  mov     rcx, cs:?g_CTxImport_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x180049324  call    cs:__imp_HeapAlloc
0x18004932a  mov     [rbp+arg_20], rax
0x18004932e  test    rax, rax
0x180049331  jz      loc_18004922F
0x180049337  mov     rcx, rax; this
0x18004933a  call    ??0CTxImport@@QEAA@XZ; CTxImport::CTxImport(void)
0x18004933f  mov     rdx, rax
0x180049342  test    rax, rax
0x180049345  jz      loc_18004922F
0x18004934b  mov     dword ptr [rsp+68h+var_48], r13d
0x180049350  mov     r10, [rax+0C0h]
0x180049357  mov     rcx, [r10]
0x18004935a  mov     rax, [rcx+98h]
0x180049361  mov     rcx, r10
0x180049364  jmp     loc_180049D3A
0x180049369  cmp     eax, r15d
0x18004936c  jnz     short loc_18004937B
0x18004936e  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x180049375  jz      loc_1800492AC
0x18004937b  mov     ecx, 178h; Size
0x180049380  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049385  mov     [rbp+arg_20], rax
0x180049389  test    rax, rax
0x18004938c  jz      loc_18004922F
0x180049392  mov     rcx, rax; this
0x180049395  call    ??0CTxReenlist@@QEAA@XZ; CTxReenlist::CTxReenlist(void)
0x18004939a  mov     rdx, rax
0x18004939d  test    rax, rax
0x1800493a0  jz      loc_18004922F
0x1800493a6  mov     [rax+168h], rsi
0x1800493ad  mov     r9, [rax+140h]
0x1800493b4  jmp     loc_18004A741
0x1800493b9  cmp     r12d, 7
0x1800493bd  jz      loc_180049511
0x1800493c3  cmp     r12d, 9
0x1800493c7  jz      loc_1800494B8
0x1800493cd  cmp     r12d, 11h
0x1800493d1  jz      loc_18004945F
0x1800493d7  cmp     r12d, 16h
0x1800493db  jnz     loc_180049228
0x1800493e1  cmp     eax, r15d
0x1800493e4  jnz     short loc_1800493F3
0x1800493e6  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x1800493ed  jz      loc_1800492AC
0x1800493f3  cmp     cs:?g_fLuTransactionsDisabled@@3HA, r15d; int g_fLuTransactionsDisabled
0x1800493fa  jz      loc_1800492AC
0x180049400  cmp     cs:byte_180165D30, r13b
0x180049407  jnz     short loc_180049430
0x180049409  mov     eax, cs:dword_180152CE0
0x18004940f  cmp     eax, 5
0x180049412  jbe     short loc_180049429
0x180049414  call    _tlgKeywordOn
0x180049419  test    al, al
0x18004941b  jz      short loc_180049429
0x18004941d  lea     rdx, byte_180147C6F
0x180049424  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180049429  mov     cs:byte_180165D30, r15b
0x180049430  xor     edx, edx; dwFlags
0x180049432  mov     r8d, 138h; dwBytes
0x180049438  mov     rcx, cs:?g_CDtcLuRmEnlistment_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x18004943f  call    cs:__imp_HeapAlloc
0x180049445  mov     [rbp+arg_20], rax
0x180049449  test    rax, rax
0x18004944c  jz      loc_18004922F
0x180049452  mov     rcx, rax; this
0x180049455  call    ??0CDtcLuRmEnlistment@@QEAA@XZ; CDtcLuRmEnlistment::CDtcLuRmEnlistment(void)
0x18004945a  jmp     loc_1800492E2
0x18004945f  cmp     eax, r15d
0x180049462  jnz     short loc_180049471
0x180049464  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x18004946b  jz      loc_1800492AC
0x180049471  xor     edx, edx; dwFlags
0x180049473  mov     r8d, 108h; dwBytes
0x180049479  mov     rcx, cs:?g_CTxAssociate_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x180049480  call    cs:__imp_HeapAlloc
0x180049486  mov     [rbp+arg_20], rax
0x18004948a  test    rax, rax
0x18004948d  jz      short loc_18004949C
0x18004948f  mov     rcx, rax; this
0x180049492  call    ??0CTxAssociate@@QEAA@XZ; CTxAssociate::CTxAssociate(void)
0x180049497  mov     rdx, rax
0x18004949a  jmp     short loc_18004949F
0x18004949c  mov     rdx, r13
0x18004949f  test    rdx, rdx
0x1800494a2  jz      loc_18004922F
0x1800494a8  mov     [rdx+78h], rsi
0x1800494ac  mov     rcx, [rdx+70h]
0x1800494b0  mov     rax, [rcx]
0x1800494b3  jmp     loc_1800495B5
0x1800494b8  cmp     eax, r15d
0x1800494bb  jnz     short loc_1800494CA
0x1800494bd  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x1800494c4  jz      loc_1800492AC
0x1800494ca  xor     edx, edx; dwFlags
0x1800494cc  mov     r8d, 0D8h; dwBytes
0x1800494d2  mov     rcx, cs:?g_CTxVoter_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x1800494d9  call    cs:__imp_HeapAlloc
0x1800494df  mov     [rbp+arg_20], rax
0x1800494e3  test    rax, rax
0x1800494e6  jz      short loc_1800494F5
0x1800494e8  mov     rcx, rax; this
0x1800494eb  call    ??0CTxVoter@@QEAA@XZ; CTxVoter::CTxVoter(void)
0x1800494f0  mov     rdx, rax
0x1800494f3  jmp     short loc_1800494F8
0x1800494f5  mov     rdx, r13
0x1800494f8  test    rdx, rdx
0x1800494fb  jz      loc_18004922F
0x180049501  mov     [rdx+0B0h], rsi
0x180049508  mov     rcx, [rdx+0A8h]
0x18004950f  jmp     short loc_1800494B0
0x180049511  cmp     eax, r15d
0x180049514  jnz     short loc_180049523
0x180049516  cmp     cs:?g_fNetworkAdminEnabled@@3HA, r13d; int g_fNetworkAdminEnabled
0x18004951d  jz      loc_1800492AC
0x180049523  mov     ecx, 90h; Size
0x180049528  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004952d  mov     r9, rax
0x180049530  mov     [rbp+arg_20], rax
0x180049534  test    rax, rax
0x180049537  jz      loc_18004922F
0x18004953d  add     rax, 30h ; '0'
0x180049541  lea     rdx, ??_7CImpIConnectionSink_Helper@@6B@; const CImpIConnectionSink_Helper::`vftable'
0x180049548  mov     [rax+20h], rdx
0x18004954c  mov     [rax+28h], rax
0x180049550  mov     [rax+8], r13d
0x180049554  mov     [rax+18h], r13
0x180049558  mov     [rax+10h], r13
0x18004955c  lea     rcx, ??_7CTxResolve@@6B?$CJoinStatusSink_TxJoinConnHelper@VCTxResolve_State@@VCTxResolve@@@@@; const CTxResolve::`vftable'{for `CJoinStatusSink_TxJoinConnHelper<CTxResolve_State,CTxResolve>'}
0x180049563  mov     [r9], rcx
0x180049566  lea     rcx, ??_7?$CTxJoinConnHelperConnection@VCDtcLuSuperiorConn_Creating_State@@VCDtcLuSuperiorConn_Creating@@@@6B@; const CTxJoinConnHelperConnection<CDtcLuSuperiorConn_Creating_State,CDtcLuSuperiorConn_Creating>::`vftable'
0x18004956d  mov     [rax], rcx
0x180049570  mov     dword ptr [r9+8Ch], 1075h
0x18004957b  lea     rax, ?g_CTxResolve_State_WaitForInit@@3VCTxResolve_State_WaitForInit@@A; CTxResolve_State_WaitForInit g_CTxResolve_State_WaitForInit
0x180049582  mov     [r9+88h], r13d
0x180049589  mov     [r9+80h], r13
0x180049590  mov     [r9+68h], r13
0x180049594  mov     [r9+60h], r13d
0x180049598  mov     [r9+70h], rax
0x18004959c  test    r9, r9
0x18004959f  jz      loc_18004922F
0x1800495a5  mov     [r9+80h], rsi
0x1800495ac  mov     rcx, rax
0x1800495af  mov     rax, [rax]
0x1800495b2  mov     rdx, r9
0x1800495b5  mov     rax, [rax+8]
0x1800495b9  jmp     loc_18004A74B
0x1800495be  lea     rdx, aSupportlusubor; "SupportLuSubordinate"
0x1800495c5  call    ?GetLocalDTCProfileIntExW@@YAKPEBG0K@Z; GetLocalDTCProfileIntExW(ushort const *,ushort const *,ulong)
0x1800495ca  test    eax, eax
0x1800495cc  jz      loc_180049228
0x1800495d2  cmp     [rbp+arg_18], r15d
0x1800495d6  jnz     short loc_1800495E5
0x1800495d8  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r13d; int g_fNetworkClientsEnabled
0x1800495df  jz      loc_1800492AC
0x1800495e5  cmp     cs:?g_fLuTransactionsDisabled@@3HA, r15d; int g_fLuTransactionsDisabled
0x1800495ec  jz      loc_1800492AC
0x1800495f2  mov     ecx, 168h; Size
0x1800495f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800495fc  mov     [rbp+arg_20], rax
0x180049600  test    rax, rax
0x180049603  jz      loc_18004922F
0x180049609  mov     rcx, rax; this
  ... truncated ...
```
