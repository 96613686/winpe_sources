# CITmInit3::Init(INameObject *,ulong,ulong,ulong)

- ea: `0x1800489a0`
- end: `0x180048ed8`
- name: `?Init@CITmInit3@@UEAAJPEAUINameObject@@KKK@Z`
- size: `1336`
- prototype: `__int64 __fastcall(CITmInit3 *__hidden this, struct INameObject *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006420`
- `0x180007ba8`
- `0x180009370`
- `0x180015230`
- `0x180018d14`
- `0x180019a90`
- `0x1800240b0`
- `0x1800489a0`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180048de7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180048de7`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x180048cb0`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x180048cb0`
- `MSDTCPRX!__imp_DllGetDTCUtilObject` at `0x180048c81`
- `MSDTCPRX!__imp_DllGetDTCUtilObject` at `0x180048c81`

## string_xrefs

- `0x180048b62`: `com\complus\dtc\dtc\tm\src\tminit.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CITmInit3::Init(
        CITmInit3 *this,
        struct INameObject *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  CTrace *v8; // rcx
  int DTCUtilObject; // ebx
  CUITrace *v10; // rcx
  unsigned int v11; // edx
  const char *v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rcx
  char *v17; // rdi
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  char v21[512]; // [rsp+50h] [rbp-B0h] BYREF

  v20[0] = 0;
  DTCUtilObject = (*(__int64 (__fastcall **)(struct INameObject *, struct ITmInstance **))(*(_QWORD *)a2 + 272LL))(
                    a2,
                    &g_pCoreTmInstance);
  if ( DTCUtilObject >= 0 )
  {
    CTrace::Init(v8);
    CUITrace::Init(v10);
    g_dwDtcMaxSessions = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                           g_pCoreTmInstance,
                           L"DtcMaxSessions",
                           32);
    g_dwTMDoNotGoIdle = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance
                                                                                                 + 344LL))(
                          g_pCoreTmInstance,
                          L"DoNotGoIdle",
                          0);
    g_bDisableTipPassThruCheck = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                                   g_pCoreTmInstance,
                                   L"DisableTipPassThruCheck",
                                   0) != 0;
    g_dwMinCheckpointInterval = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                                  g_pCoreTmInstance,
                                  L"MinCheckpointInterval",
                                  1000);
    g_dwMaxCheckpointInterval = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                                  g_pCoreTmInstance,
                                  L"MaxCheckpointInterval",
                                  50000);
    g_fWaitForAllXaBranchPrepares = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                                      g_pCoreTmInstance,
                                      L"WaitForAllXaBranchPrepares",
                                      0);
    v13 = g_dwMinCheckpointInterval;
    if ( !g_dwMinCheckpointInterval || (v14 = g_dwMaxCheckpointInterval) == 0 )
    {
      v13 = 1000;
      g_dwMinCheckpointInterval = 1000;
      v14 = 50000;
      g_dwMaxCheckpointInterval = 50000;
    }
    if ( v13 > v14 )
    {
      TracedStringCchPrintfA(
        v21,
        0x200u,
        "The specified value for MinCheckpointInterval (%d) is greater than the specified value for MaxCheckpointInterval"
        " (%d). MsDtc will be using the default values for these",
        v13,
        v14);
      g_dwMinCheckpointInterval = 1000;
      g_dwMaxCheckpointInterval = 50000;
      TraceFile(0, v21, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 0x11Eu);
    }
    g_grfNetworkDtcAccess = a3;
    g_grfXaTransactions = a4;
    g_grfOptions = a5;
    g_fNetworkAdminEnabled = 0;
    g_fNetworkClientsEnabled = 0;
    g_fInboundNetworkTxEnabled = 0;
    g_fOutboundNetworkTxEnabled = 0;
    g_fXaTransactionsEnabled = 0;
    g_fSnapshotSecurityDisabled = 0;
    if ( (a3 & 1) != 0 )
    {
      g_fNetworkAdminEnabled = (a3 & 2) != 0;
      g_fNetworkClientsEnabled = (a3 & 8) != 0;
      if ( (a3 & 4) != 0 )
      {
        g_fInboundNetworkTxEnabled = (a3 & 0x40) != 0;
        g_fOutboundNetworkTxEnabled = (a3 & 0x20) != 0;
      }
      if ( (a3 & 0x200) == 0 )
      {
        if ( (a3 & 0x100) != 0 )
        {
          gDtcSecurityLevel = 1;
        }
        else if ( (a3 & 0x80u) != 0 )
        {
          gDtcSecurityLevel = 2;
        }
      }
      isSchannelMutualAuth = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance + 344LL))(
                               g_pCoreTmInstance,
                               L"AllowOnlySchannelSecureRpcCalls",
                               0);
    }
    if ( (a4 & 1) != 0 )
      g_fXaTransactionsEnabled = 1;
    if ( (a5 & 1) != 0 )
      g_fLuTransactionsDisabled = 1;
    g_fSnapshotSecurityDisabled = GetLocalDTCSecurityProfileInt(v12, v11);
    DTCUtilObject = DllGetDTCUtilObject(&CLSID_DTCUtil, &IID_INameService3, v20);
    if ( !DTCUtilObject )
    {
      g_pINameService = (struct INameService3 *)v20[0];
      DTCUtilObject = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, v20);
      if ( !DTCUtilObject )
      {
        g_pIConnMgr = (struct IConnectionManager *)v20[0];
        DTCUtilObject = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v20[0])(
                          v20[0],
                          &IID_IConnectionManagerConfig2,
                          v20);
        if ( !DTCUtilObject )
        {
          g_pIConnMgrConfig = (struct IConnectionManagerConfig2 *)v20[0];
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v20[0] + 136LL))(v20[0], g_TmVersionInfo);
          (*(void (__fastcall **)(struct IConnectionManagerConfig2 *, _QWORD))(*(_QWORD *)g_pIConnMgrConfig + 104LL))(
            g_pIConnMgrConfig,
            g_dwDtcMaxSessions);
          v15 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance
                                                                                         + 344LL))(
                  g_pCoreTmInstance,
                  L"ServerTcpPort",
                  0);
          (*(void (__fastcall **)(struct IConnectionManagerConfig2 *, _QWORD))(*(_QWORD *)g_pIConnMgrConfig + 128LL))(
            g_pIConnMgrConfig,
            v15);
          if ( g_fNetworkAdminEnabled
            || g_fNetworkClientsEnabled
            || g_fInboundNetworkTxEnabled
            || g_fOutboundNetworkTxEnabled
            || (v19 = 0, MtxCluIsClusterPresentNonAdmin(v16, &v19), v19)
            || (DTCUtilObject = (*(__int64 (__fastcall **)(struct IConnectionManagerConfig2 *, _QWORD))(*(_QWORD *)g_pIConnMgrConfig + 120LL))(
                                  g_pIConnMgrConfig,
                                  (unsigned int)(DTCUtilObject + 32))) == 0 )
          {
            v17 = (char *)operator new(0x38u);
            v20[1] = v17;
            if ( v17 )
            {
              *(_QWORD *)v17 = &CTmImpIConnectionNotify::`vftable';
              *((_DWORD *)v17 + 2) = 0;
              InitializeCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
            }
            else
            {
              v17 = 0;
            }
            if ( v17 )
            {
              (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 8LL))(v17);
              DTCUtilObject = (*(__int64 (__fastcall **)(struct IConnectionManager *, struct INameObject *, char *, __int64))(*(_QWORD *)g_pIConnMgr + 24LL))(
                                g_pIConnMgr,
                                a2,
                                v17,
                                1);
              if ( !DTCUtilObject )
              {
                DTCUtilObject = (**(__int64 (__fastcall ***)(struct IConnectionManager *, GUID *, _QWORD *))g_pIConnMgr)(
                                  g_pIConnMgr,
                                  &IID_IConnectionDispenser,
                                  v20);
                if ( !DTCUtilObject )
                {
                  DTCUtilObject = (**(__int64 (__fastcall ***)(struct IConnectionManager *, GUID *, _QWORD *))g_pIConnMgr)(
                                    g_pIConnMgr,
                                    &IID_ICliqueDispenser,
                                    v20);
                  if ( !DTCUtilObject )
                  {
                    g_pICliqueDispenser = (struct ICliqueDispenser *)v20[0];
                    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)a2 + 8LL))(a2);
                    g_pIDtcNameObject = a2;
                  }
                }
              }
              (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
        }
      }
    }
  }
  return (unsigned int)DTCUtilObject;
}

```

## disassembly

```asm
0x1800489a0  mov     [rsp-8+arg_0], rbx
0x1800489a5  mov     [rsp-8+arg_10], rsi
0x1800489aa  push    rbp
0x1800489ab  push    rdi
0x1800489ac  push    r12
0x1800489ae  push    r14
0x1800489b0  push    r15
0x1800489b2  lea     rbp, [rsp-160h]
0x1800489ba  sub     rsp, 260h
0x1800489c1  mov     rax, cs:__security_cookie
0x1800489c8  xor     rax, rsp
0x1800489cb  mov     [rbp+180h+var_30], rax
0x1800489d2  mov     r14d, r9d
0x1800489d5  mov     edi, r8d
0x1800489d8  mov     rsi, rdx
0x1800489db  xor     r15d, r15d
0x1800489de  mov     [rsp+280h+var_248], r15
0x1800489e3  mov     rax, [rdx]
0x1800489e6  lea     rdx, ?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x1800489ed  mov     rcx, rsi
0x1800489f0  mov     rax, [rax+110h]
0x1800489f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489fc  mov     ebx, eax
0x1800489fe  test    eax, eax
0x180048a00  js      loc_180048EAB
0x180048a06  call    ?Init@CTrace@@QEAAJXZ; CTrace::Init(void)
0x180048a0b  call    ?Init@CUITrace@@QEAAJXZ; CUITrace::Init(void)
0x180048a10  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048a17  mov     rax, [rcx]
0x180048a1a  lea     r8d, [r15+20h]
0x180048a1e  lea     rdx, aDtcmaxsessions; "DtcMaxSessions"
0x180048a25  mov     rax, [rax+158h]
0x180048a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a31  mov     cs:?g_dwDtcMaxSessions@@3KA, eax; ulong g_dwDtcMaxSessions
0x180048a37  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048a3e  mov     rax, [rcx]
0x180048a41  xor     r8d, r8d
0x180048a44  lea     rdx, aDonotgoidle; "DoNotGoIdle"
0x180048a4b  mov     rax, [rax+158h]
0x180048a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a57  mov     cs:?g_dwTMDoNotGoIdle@@3KA, eax; ulong g_dwTMDoNotGoIdle
0x180048a5d  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048a64  mov     rax, [rcx]
0x180048a67  xor     r8d, r8d
0x180048a6a  lea     rdx, aDisabletippass; "DisableTipPassThruCheck"
0x180048a71  mov     rax, [rax+158h]
0x180048a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a7d  mov     ecx, r15d
0x180048a80  test    eax, eax
0x180048a82  setnz   cl
0x180048a85  mov     cs:?g_bDisableTipPassThruCheck@@3HA, ecx; int g_bDisableTipPassThruCheck
0x180048a8b  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048a92  mov     rax, [rcx]
0x180048a95  mov     ebx, 3E8h
0x180048a9a  mov     r8d, ebx
0x180048a9d  lea     rdx, aMincheckpointi; "MinCheckpointInterval"
0x180048aa4  mov     rax, [rax+158h]
0x180048aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ab0  mov     cs:?g_dwMinCheckpointInterval@@3KA, eax; ulong g_dwMinCheckpointInterval
0x180048ab6  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048abd  mov     rax, [rcx]
0x180048ac0  mov     r12d, 0C350h
0x180048ac6  mov     r8d, r12d
0x180048ac9  lea     rdx, aMaxcheckpointi; "MaxCheckpointInterval"
0x180048ad0  mov     rax, [rax+158h]
0x180048ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048adc  mov     cs:?g_dwMaxCheckpointInterval@@3KA, eax; ulong g_dwMaxCheckpointInterval
0x180048ae2  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048ae9  mov     rax, [rcx]
0x180048aec  xor     r8d, r8d
0x180048aef  lea     rdx, aWaitforallxabr; "WaitForAllXaBranchPrepares"
0x180048af6  mov     rax, [rax+158h]
0x180048afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b02  mov     cs:?g_fWaitForAllXaBranchPrepares@@3HA, eax; int g_fWaitForAllXaBranchPrepares
0x180048b08  mov     r9d, cs:?g_dwMinCheckpointInterval@@3KA; ulong g_dwMinCheckpointInterval
0x180048b0f  test    r9d, r9d
0x180048b12  jz      short loc_180048B1E
0x180048b14  mov     eax, cs:?g_dwMaxCheckpointInterval@@3KA; ulong g_dwMaxCheckpointInterval
0x180048b1a  test    eax, eax
0x180048b1c  jnz     short loc_180048B30
0x180048b1e  mov     r9d, ebx
0x180048b21  mov     cs:?g_dwMinCheckpointInterval@@3KA, ebx; ulong g_dwMinCheckpointInterval
0x180048b27  mov     eax, r12d
0x180048b2a  mov     cs:?g_dwMaxCheckpointInterval@@3KA, eax; ulong g_dwMaxCheckpointInterval
0x180048b30  cmp     r9d, eax
0x180048b33  jbe     short loc_180048B75
0x180048b35  mov     [rsp+280h+var_260], eax
0x180048b39  lea     r8, aTheSpecifiedVa; "The specified value for MinCheckpointIn"...
0x180048b40  mov     edx, 200h; unsigned __int64
0x180048b45  lea     rcx, [rsp+280h+var_230]; char *
0x180048b4a  call    ?TracedStringCchPrintfA@@YAXPEAD_KPEBDZZ; TracedStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180048b4f  mov     cs:?g_dwMinCheckpointInterval@@3KA, ebx; ulong g_dwMinCheckpointInterval
0x180048b55  mov     cs:?g_dwMaxCheckpointInterval@@3KA, r12d; ulong g_dwMaxCheckpointInterval
0x180048b5c  mov     r9d, 11Eh; unsigned int
0x180048b62  lea     r8, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x180048b69  lea     rdx, [rsp+280h+var_230]; char *
0x180048b6e  xor     ecx, ecx; int
0x180048b70  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180048b75  mov     cs:?g_grfNetworkDtcAccess@@3KA, edi; ulong g_grfNetworkDtcAccess
0x180048b7b  mov     cs:?g_grfXaTransactions@@3KA, r14d; ulong g_grfXaTransactions
0x180048b82  mov     ebx, [rbp+180h+arg_20]
0x180048b88  mov     cs:?g_grfOptions@@3KA, ebx; ulong g_grfOptions
0x180048b8e  mov     cs:?g_fNetworkAdminEnabled@@3HA, r15d; int g_fNetworkAdminEnabled
0x180048b95  mov     cs:?g_fNetworkClientsEnabled@@3HA, r15d; int g_fNetworkClientsEnabled
0x180048b9c  mov     cs:?g_fInboundNetworkTxEnabled@@3HA, r15d; int g_fInboundNetworkTxEnabled
0x180048ba3  mov     cs:?g_fOutboundNetworkTxEnabled@@3HA, r15d; int g_fOutboundNetworkTxEnabled
0x180048baa  mov     cs:?g_fXaTransactionsEnabled@@3HA, r15d; int g_fXaTransactionsEnabled
0x180048bb1  mov     cs:?g_fSnapshotSecurityDisabled@@3HA, r15d; int g_fSnapshotSecurityDisabled
0x180048bb8  mov     r12d, 1
0x180048bbe  test    r12b, dil
0x180048bc1  jz      loc_180048C4B
0x180048bc7  test    dil, 2
0x180048bcb  jz      short loc_180048BD4
0x180048bcd  mov     cs:?g_fNetworkAdminEnabled@@3HA, r12d; int g_fNetworkAdminEnabled
0x180048bd4  test    dil, 8
0x180048bd8  jz      short loc_180048BE1
0x180048bda  mov     cs:?g_fNetworkClientsEnabled@@3HA, r12d; int g_fNetworkClientsEnabled
0x180048be1  test    dil, 4
0x180048be5  jz      short loc_180048C01
0x180048be7  test    dil, 40h
0x180048beb  jz      short loc_180048BF4
0x180048bed  mov     cs:?g_fInboundNetworkTxEnabled@@3HA, r12d; int g_fInboundNetworkTxEnabled
0x180048bf4  test    dil, 20h
0x180048bf8  jz      short loc_180048C01
0x180048bfa  mov     cs:?g_fOutboundNetworkTxEnabled@@3HA, r12d; int g_fOutboundNetworkTxEnabled
0x180048c01  bt      edi, 9
0x180048c05  jb      short loc_180048C25
0x180048c07  bt      edi, 8
0x180048c0b  jnb     short loc_180048C16
0x180048c0d  mov     cs:?gDtcSecurityLevel@@3W4DTC_SECURITY_LEVEL@@A, r12d; DTC_SECURITY_LEVEL gDtcSecurityLevel
0x180048c14  jmp     short loc_180048C25
0x180048c16  test    dil, dil
0x180048c19  jns     short loc_180048C25
0x180048c1b  mov     cs:?gDtcSecurityLevel@@3W4DTC_SECURITY_LEVEL@@A, 2; DTC_SECURITY_LEVEL gDtcSecurityLevel
0x180048c25  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048c2c  mov     rax, [rcx]
0x180048c2f  xor     r8d, r8d
0x180048c32  lea     rdx, aAllowonlyschan; "AllowOnlySchannelSecureRpcCalls"
0x180048c39  mov     rax, [rax+158h]
0x180048c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c45  mov     cs:?isSchannelMutualAuth@@3HA, eax; int isSchannelMutualAuth
0x180048c4b  test    r12b, r14b
0x180048c4e  jz      short loc_180048C57
0x180048c50  mov     cs:?g_fXaTransactionsEnabled@@3HA, r12d; int g_fXaTransactionsEnabled
0x180048c57  test    r12b, bl
0x180048c5a  jz      short loc_180048C63
0x180048c5c  mov     cs:?g_fLuTransactionsDisabled@@3HA, r12d; int g_fLuTransactionsDisabled
0x180048c63  call    ?GetLocalDTCSecurityProfileInt@@YAKPEBDK@Z; GetLocalDTCSecurityProfileInt(char const *,ulong)
0x180048c68  mov     cs:?g_fSnapshotSecurityDisabled@@3HA, eax; int g_fSnapshotSecurityDisabled
0x180048c6e  lea     r8, [rsp+280h+var_248]
0x180048c73  lea     rdx, IID_INameService3
0x180048c7a  lea     rcx, CLSID_DTCUtil
0x180048c81  call    cs:__imp_DllGetDTCUtilObject
0x180048c87  mov     ebx, eax
0x180048c89  test    eax, eax
0x180048c8b  jnz     loc_180048EAB
0x180048c91  mov     rax, [rsp+280h+var_248]
0x180048c96  mov     cs:?g_pINameService@@3PEAUINameService3@@EA, rax; INameService3 * g_pINameService
0x180048c9d  lea     r8, [rsp+280h+var_248]
0x180048ca2  lea     rdx, IID_IConnectionManager
0x180048ca9  lea     rcx, CLSID_DTCCM
0x180048cb0  call    cs:__imp_DllGetDTCConnectionManager
0x180048cb6  mov     ebx, eax
0x180048cb8  test    eax, eax
0x180048cba  jnz     loc_180048EAB
0x180048cc0  mov     rcx, [rsp+280h+var_248]
0x180048cc5  mov     cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA, rcx; IConnectionManager * g_pIConnMgr
0x180048ccc  mov     rax, [rcx]
0x180048ccf  lea     r8, [rsp+280h+var_248]
0x180048cd4  lea     rdx, IID_IConnectionManagerConfig2
0x180048cdb  mov     rax, [rax]
0x180048cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ce3  mov     ebx, eax
0x180048ce5  test    eax, eax
0x180048ce7  jnz     loc_180048EAB
0x180048ced  mov     rcx, [rsp+280h+var_248]
0x180048cf2  mov     cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA, rcx; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180048cf9  mov     rax, [rcx]
0x180048cfc  mov     rdx, cs:?g_TmVersionInfo@@3U_VersionInfo@@A; _VersionInfo g_TmVersionInfo
0x180048d03  mov     rax, [rax+88h]
0x180048d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d0f  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180048d16  mov     rax, [rcx]
0x180048d19  mov     edx, cs:?g_dwDtcMaxSessions@@3KA; ulong g_dwDtcMaxSessions
0x180048d1f  mov     rax, [rax+68h]
0x180048d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d28  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180048d2f  mov     rax, [rcx]
0x180048d32  xor     r8d, r8d
0x180048d35  lea     rdx, aServertcpport; "ServerTcpPort"
0x180048d3c  mov     rax, [rax+158h]
0x180048d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d48  mov     r8d, eax
0x180048d4b  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180048d52  mov     rdx, [rcx]
0x180048d55  mov     rax, [rdx+80h]
0x180048d5c  mov     edx, r8d
0x180048d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d64  cmp     cs:?g_fNetworkAdminEnabled@@3HA, r15d; int g_fNetworkAdminEnabled
0x180048d6b  jnz     short loc_180048DBE
0x180048d6d  cmp     cs:?g_fNetworkClientsEnabled@@3HA, r15d; int g_fNetworkClientsEnabled
0x180048d74  jnz     short loc_180048DBE
0x180048d76  cmp     cs:?g_fInboundNetworkTxEnabled@@3HA, r15d; int g_fInboundNetworkTxEnabled
0x180048d7d  jnz     short loc_180048DBE
0x180048d7f  cmp     cs:?g_fOutboundNetworkTxEnabled@@3HA, r15d; int g_fOutboundNetworkTxEnabled
0x180048d86  jnz     short loc_180048DBE
0x180048d88  mov     [rsp+280h+var_250], r15b
0x180048d8d  lea     rdx, [rsp+280h+var_250]; bool *
0x180048d92  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180048d97  cmp     [rsp+280h+var_250], r15b
0x180048d9c  jnz     short loc_180048DBE
0x180048d9e  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180048da5  mov     rax, [rcx]
0x180048da8  lea     edx, [rbx+20h]
0x180048dab  mov     rax, [rax+78h]
0x180048daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048db4  mov     ebx, eax
0x180048db6  test    eax, eax
0x180048db8  jnz     loc_180048EAB
0x180048dbe  mov     ecx, 38h ; '8'; Size
0x180048dc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048dc8  mov     rdi, rax
0x180048dcb  mov     [rsp+280h+var_240], rax
0x180048dd0  test    rax, rax
0x180048dd3  jz      short loc_180048DEF
0x180048dd5  lea     rax, ??_7CTmImpIConnectionNotify@@6B@; const CTmImpIConnectionNotify::`vftable'
0x180048ddc  mov     [rdi], rax
0x180048ddf  mov     [rdi+8], r15d
0x180048de3  lea     rcx, [rdi+10h]; lpCriticalSection
0x180048de7  call    cs:__imp_InitializeCriticalSection
0x180048ded  jmp     short loc_180048DF2
0x180048def  mov     rdi, r15
0x180048df2  test    rdi, rdi
0x180048df5  jnz     short loc_180048E01
0x180048df7  mov     ebx, 8007000Eh
0x180048dfc  jmp     loc_180048EAB
0x180048e01  mov     rax, [rdi]
0x180048e04  mov     rcx, rdi
0x180048e07  mov     rax, [rax+8]
0x180048e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e10  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x180048e17  mov     rax, [rcx]
0x180048e1a  mov     r9d, r12d
0x180048e1d  mov     r8, rdi
0x180048e20  mov     rdx, rsi
0x180048e23  mov     rax, [rax+18h]
0x180048e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e2c  mov     ebx, eax
0x180048e2e  test    eax, eax
0x180048e30  jnz     short loc_180048E9C
0x180048e32  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x180048e39  mov     rax, [rcx]
0x180048e3c  lea     r8, [rsp+280h+var_248]
0x180048e41  lea     rdx, IID_IConnectionDispenser
0x180048e48  mov     rax, [rax]
0x180048e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e50  mov     ebx, eax
0x180048e52  test    eax, eax
0x180048e54  jnz     short loc_180048E9C
0x180048e56  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x180048e5d  mov     rax, [rcx]
0x180048e60  lea     r8, [rsp+280h+var_248]
0x180048e65  lea     rdx, IID_ICliqueDispenser
0x180048e6c  mov     rax, [rax]
0x180048e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e74  mov     ebx, eax
0x180048e76  test    eax, eax
0x180048e78  jnz     short loc_180048E9C
0x180048e7a  mov     rax, [rsp+280h+var_248]
0x180048e7f  mov     cs:?g_pICliqueDispenser@@3PEAUICliqueDispenser@@EA, rax; ICliqueDispenser * g_pICliqueDispenser
0x180048e86  mov     rax, [rsi]
0x180048e89  mov     rcx, rsi
0x180048e8c  mov     rax, [rax+8]
0x180048e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e95  mov     cs:?g_pIDtcNameObject@@3PEAUINameObject@@EA, rsi; INameObject * g_pIDtcNameObject
0x180048e9c  mov     rax, [rdi]
0x180048e9f  mov     rcx, rdi
0x180048ea2  mov     rax, [rax+10h]
0x180048ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048eab  mov     eax, ebx
0x180048ead  mov     rcx, [rbp+180h+var_30]
0x180048eb4  xor     rcx, rsp; StackCookie
0x180048eb7  call    __security_check_cookie
0x180048ebc  lea     r11, [rsp+280h+var_20]
0x180048ec4  mov     rbx, [r11+30h]
0x180048ec8  mov     rsi, [r11+40h]
0x180048ecc  mov     rsp, r11
0x180048ecf  pop     r15
0x180048ed1  pop     r14
0x180048ed3  pop     r12
0x180048ed5  pop     rdi
0x180048ed6  pop     rbp
0x180048ed7  retn
```
