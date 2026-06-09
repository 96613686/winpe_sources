# InitializeRpcServer(bool)

- ea: `0x180044244`
- end: `0x18004481d`
- name: `?InitializeRpcServer@@YAJ_N@Z`
- size: `1497`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800381dc`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000e558`
- `0x18000f35c`
- `0x18002c61c`
- `0x18002c770`
- `0x180044028`
- `0x180044244`
- `0x180044824`
- `0x180044884`
- `0x180044c50`
- `0x180044d74`
- `0x180045278`
- `0x1800452c8`
- `0x18009bd1c`
- `0x1800cffcc`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18004463a`
- `msvcrt!free` at `0x1800446bb`
- `msvcrt!free` at `0x180044751`
- `msvcrt!free` at `0x18004475d`
- `msvcrt!free` at `0x1800447d0`
- `msvcrt!free` at `0x1800447dc`
- `msvcrt!free` at `0x1800447ec`
- `msvcrt!free` at `0x18004463a`
- `msvcrt!free` at `0x1800446bb`
- `msvcrt!free` at `0x180044751`
- `msvcrt!free` at `0x18004475d`
- `msvcrt!free` at `0x1800447d0`
- `msvcrt!free` at `0x1800447dc`
- `msvcrt!free` at `0x1800447ec`
- `msvcrt!_wtol` at `0x180044418`
- `msvcrt!_wtol` at `0x180044445`
- `msvcrt!_wtol` at `0x180044418`
- `msvcrt!_wtol` at `0x180044445`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180044614`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180044778`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180044614`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180044778`
- `RPCRT4!RpcServerInqBindings` at `0x18004456d`
- `RPCRT4!RpcServerInqBindings` at `0x18004456d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044328`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044397`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044328`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180044397`
- `DSPARSE!DsMakeSpnW` at `0x180044683`
- `DSPARSE!DsMakeSpnW` at `0x18004471e`
- `DSPARSE!DsMakeSpnW` at `0x180044683`
- `DSPARSE!DsMakeSpnW` at `0x18004471e`
- `mqsec!ComposeRPCEndPointName` at `0x18004437d`
- `mqsec!ComposeRPCEndPointName` at `0x18004437d`
- `mqsec!MQSec_IsDC` at `0x180044308`
- `mqsec!MQSec_IsDC` at `0x180044308`

## string_xrefs

- `0x180044315`: `QmReplService`
- `0x18004434c`: `QmReplService`
- `0x1800445f4`: `Message Queuing - RemoteRead V1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InitializeRpcServer(char a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  char v5; // al
  char v6; // al
  unsigned int v7; // r9d
  unsigned int v8; // r9d
  DWORD v9; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // ebx
  RPC_STATUS v12; // eax
  RPC_STATUS v13; // eax
  signed int SpnW; // eax
  unsigned __int16 *pszSpn; // rbx
  signed int v16; // eax
  signed int v17; // edi
  RPC_STATUS v18; // eax
  int v19; // edi
  DWORD v20; // ecx
  DWORD pcSpnLength; // [rsp+40h] [rbp-78h] BYREF
  RPC_WSTR Endpoint[2]; // [rsp+48h] [rbp-70h] BYREF
  const bad_rpc_result *v23; // [rsp+58h] [rbp-60h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+60h] [rbp-58h] BYREF
  wchar_t Buffer[20]; // [rsp+80h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 34, &WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids);
  v2 = QMInitializeLocalRpcServer();
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 35, &WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids, v2);
    EvReportWithError(0xC000080D, v3, 0);
    LogMsgRPCStatus(v3, (wchar_t *)L"qmrpcsrv", 0xE6u);
    return v3;
  }
  if ( MQSec_IsDC() )
  {
    v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, (RPC_WSTR)L"QmReplService", 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), v5);
  }
  Endpoint[0] = 0;
  ComposeRPCEndPointName(L"QMMgmtFacility", 0, Endpoint);
  v6 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, Endpoint[0], 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), v6);
  if ( !a1 )
  {
    QMInitializeNetworkRpcServer(Buffer, 0x83Bu, 1, v7);
    v9 = QMInitializeNetworkRpcServer(&g_wszRpcIpPort, 0x837u, 1, v8);
    if ( v9
      || (dword_18013C5A4 = _wtol(&g_wszRpcIpPort),
          (v9 = QMInitializeNetworkRpcServer(&g_wszRpcIpPort2, 0x839u, 0, v10)) != 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 38, &WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids, 0);
      EvReportWithError(0x8000080B, v9, 0);
    }
    else
    {
      dword_18013C5A8 = _wtol(&g_wszRpcIpPort2);
    }
  }
  try
  {
    v11 = 16 * IsUnauthenticatedRpcAllowed() + 1;
    RegisterInterface(qword_1800F00B0, v11 | 0x90, (int (*)(void *, void *))QMCOMMSecurityCallback, 0x96u, 0x400000u);
    RegisterInterface(qword_1800F17B0, v11, (int (*)(void *, void *))QMCOMM2SecurityCallback, 0xFAu, 0x400000u);
    RegisterInterface(qword_1800E94E0, v11, QMMGMTSecurityCallback, 0x109u, 0xFFFFFFFF);
    if ( (unsigned __int8)IsOldRemoteReadAllowed() )
      RegisterInterface(qword_1800E82E0, v11 | 0x10, (int (*)(void *, void *))Qm2QmSecurityCallback, 0x10Eu, 0xFFFFFFFF);
    RegisterInterface(
      qword_1800F3440,
      v11 | 0x90,
      (int (*)(void *, void *))RemoteReadSecurityCallback,
      0x113u,
      0xFFFFFFFF);
    v12 = RpcServerInqBindings(&BindingVector);
    if ( v12 )
    {
      bad_rpc_result::bad_rpc_result((bad_rpc_result *)pExceptionObject, v12, 0x118u);
      throw (bad_rpc_result *)pExceptionObject;
    }
    RegisterEndpoint(qword_1800F00B0, (wchar_t *)L"Message Queuing - QMRT V1", 0x11Du);
    RegisterEndpoint(qword_1800F17B0, (wchar_t *)L"Message Queuing - QMRT V2", 0x122u);
    if ( (unsigned __int8)IsOldRemoteReadAllowed() )
      RegisterEndpoint(qword_1800E82E0, (wchar_t *)L"Message Queuing - QM2QM V1", 0x127u);
    RegisterEndpoint(qword_1800F3440, (wchar_t *)L"Message Queuing - RemoteRead V1", 0x12Cu);
  }
  catch ( const bad_rpc_result *v23 )
  {
    v20 = *((_DWORD *)v23 + 6);
    pcSpnLength = v20;
    if ( v20 )
      LogMsgRPCStatus(v20, (wchar_t *)L"qmrpcsrv", *((_WORD *)v23 + 14));
    free(Endpoint[0]);
    return pcSpnLength;
  }
  v13 = RpcServerRegisterAuthInfoW(0, 0xAu, 0, 0);
  v3 = v13;
  if ( v13 )
  {
    LogMsgRPCStatus(v13, (wchar_t *)L"qmrpcsrv", 0xCDu);
    free(Endpoint[0]);
    return v3;
  }
  if ( g_fPureWorkGroupMachine )
    goto LABEL_53;
  pcSpnLength = 0;
  SpnW = DsMakeSpnW(L"HOST", g_szComputerDnsName, 0, 0, 0, &pcSpnLength, 0);
  v3 = SpnW;
  if ( SpnW != 111 )
  {
    if ( SpnW > 0 )
      v3 = (unsigned __int16)SpnW | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      LogMsgHR(v3, (wchar_t *)L"qmrpcsrv", 0xC8Au);
    free(Endpoint[0]);
    return v3;
  }
  pszSpn = (unsigned __int16 *)MmAllocate(saturated_mul(++pcSpnLength, 2u));
  Endpoint[1] = pszSpn;
  v16 = DsMakeSpnW(L"HOST", g_szComputerDnsName, 0, 0, 0, &pcSpnLength, pszSpn);
  v17 = v16;
  if ( !v16 )
  {
    v18 = RpcServerRegisterAuthInfoW(pszSpn, 0x10u, 0, 0);
    v19 = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), v18);
    if ( v19 )
      LogMsgRPCStatus(v19, (wchar_t *)L"qmrpcsrv", 0x145u);
    free(pszSpn);
LABEL_53:
    free(Endpoint[0]);
    return 0;
  }
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  if ( v17 < 0 )
    LogMsgHR(v17, (wchar_t *)L"qmrpcsrv", 0x140u);
  free(pszSpn);
  free(Endpoint[0]);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180044244  mov     [rsp+arg_0], rbx
0x180044249  mov     [rsp+arg_8], rdi
0x18004424e  push    r14
0x180044250  sub     rsp, 0B0h
0x180044257  mov     rax, cs:__security_cookie
0x18004425e  xor     rax, rsp
0x180044261  mov     [rsp+0B8h+var_10], rax
0x180044269  mov     dil, cl
0x18004426c  lea     r14, WPP_GLOBAL_Control
0x180044273  mov     rcx, cs:WPP_GLOBAL_Control
0x18004427a  cmp     rcx, r14
0x18004427d  jz      short loc_1800442A0
0x18004427f  test    byte ptr [rcx+0BCh], 4
0x180044286  jz      short loc_1800442A0
0x180044288  mov     edx, 22h ; '"'
0x18004428d  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x180044294  mov     rcx, [rcx+0B0h]
0x18004429b  call    WPP_SF_
0x1800442a0  call    ?QMInitializeLocalRpcServer@@YAJXZ; QMInitializeLocalRpcServer(void)
0x1800442a5  mov     ebx, eax
0x1800442a7  test    eax, eax
0x1800442a9  jz      short loc_180044308
0x1800442ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800442b2  cmp     rcx, r14
0x1800442b5  jz      short loc_1800442DB
0x1800442b7  test    byte ptr [rcx+0BCh], 1
0x1800442be  jz      short loc_1800442DB
0x1800442c0  mov     edx, 23h ; '#'
0x1800442c5  mov     r9d, eax
0x1800442c8  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x1800442cf  mov     rcx, [rcx+0B0h]
0x1800442d6  call    WPP_SF_d
0x1800442db  xor     eax, eax
0x1800442dd  movzx   r8d, ax; unsigned __int16
0x1800442e1  mov     edx, ebx; dwMessageId
0x1800442e3  mov     ecx, 0C000080Dh; unsigned int
0x1800442e8  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x1800442ed  mov     r8d, 0E6h; unsigned __int16
0x1800442f3  lea     rdx, aQmrpcsrv; "qmrpcsrv"
0x1800442fa  mov     ecx, ebx; int
0x1800442fc  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x180044301  mov     eax, ebx
0x180044303  jmp     loc_1800447F7
0x180044308  call    cs:__imp_?MQSec_IsDC@@YA_NXZ; MQSec_IsDC(void)
0x18004430e  test    al, al
0x180044310  jz      short loc_180044366
0x180044312  xor     r9d, r9d; SecurityDescriptor
0x180044315  lea     r8, Endpoint; "QmReplService"
0x18004431c  mov     edx, 4D2h; MaxCalls
0x180044321  lea     rcx, Protseq; "ncalrpc"
0x180044328  call    cs:__imp_RpcServerUseProtseqEpW
0x18004432e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044335  cmp     rcx, r14
0x180044338  jz      short loc_180044366
0x18004433a  test    byte ptr [rcx+0BCh], 4
0x180044341  jz      short loc_180044366
0x180044343  mov     edx, 24h ; '$'
0x180044348  mov     dword ptr [rsp+0B8h+Referrer], eax; char
0x18004434c  lea     r9, Endpoint; "QmReplService"
0x180044353  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x18004435a  mov     rcx, [rcx+0B0h]; LoggerHandle
0x180044361  call    WPP_SF_Sd
0x180044366  mov     [rsp+0B8h+Endpoint], 0
0x18004436f  lea     r8, [rsp+0B8h+Endpoint]
0x180044374  xor     edx, edx
0x180044376  lea     rcx, aQmmgmtfacility; "QMMgmtFacility"
0x18004437d  call    cs:__imp_?ComposeRPCEndPointName@@YAXPEB_W0PEAPEA_W@Z; ComposeRPCEndPointName(wchar_t const *,wchar_t const *,wchar_t * *)
0x180044383  xor     r9d, r9d; SecurityDescriptor
0x180044386  mov     r8, [rsp+0B8h+Endpoint]; Endpoint
0x18004438b  mov     edx, 4D2h; MaxCalls
0x180044390  lea     rcx, Protseq; "ncalrpc"
0x180044397  call    cs:__imp_RpcServerUseProtseqEpW
0x18004439d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443a4  cmp     rcx, r14
0x1800443a7  jz      short loc_1800443D3
0x1800443a9  test    byte ptr [rcx+0BCh], 4
0x1800443b0  jz      short loc_1800443D3
0x1800443b2  mov     edx, 25h ; '%'
0x1800443b7  mov     dword ptr [rsp+0B8h+Referrer], eax; char
0x1800443bb  mov     r9, [rsp+0B8h+Endpoint]
0x1800443c0  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x1800443c7  mov     rcx, [rcx+0B0h]; LoggerHandle
0x1800443ce  call    WPP_SF_Sd
0x1800443d3  test    dil, dil
0x1800443d6  jnz     loc_180044496
0x1800443dc  mov     edx, 83Bh; unsigned int
0x1800443e1  mov     r8d, 1; int
0x1800443e7  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x1800443ef  call    ?QMInitializeNetworkRpcServer@@YAJPEA_WKHI@Z; QMInitializeNetworkRpcServer(wchar_t *,ulong,int,uint)
0x1800443f4  mov     edx, 837h; unsigned int
0x1800443f9  mov     r8d, 1; int
0x1800443ff  lea     rcx, ?g_wszRpcIpPort@@3PA_WA; Buffer
0x180044406  call    ?QMInitializeNetworkRpcServer@@YAJPEA_WKHI@Z; QMInitializeNetworkRpcServer(wchar_t *,ulong,int,uint)
0x18004440b  mov     ebx, eax
0x18004440d  test    eax, eax
0x18004440f  jnz     short loc_180044453
0x180044411  lea     rcx, ?g_wszRpcIpPort@@3PA_WA; String
0x180044418  call    cs:__imp__wtol
0x18004441e  mov     cs:dword_18013C5A4, eax
0x180044424  xor     r8d, r8d; int
0x180044427  mov     edx, 839h; unsigned int
0x18004442c  lea     rcx, ?g_wszRpcIpPort2@@3PA_WA; Buffer
0x180044433  call    ?QMInitializeNetworkRpcServer@@YAJPEA_WKHI@Z; QMInitializeNetworkRpcServer(wchar_t *,ulong,int,uint)
0x180044438  mov     ebx, eax
0x18004443a  test    eax, eax
0x18004443c  jnz     short loc_180044453
0x18004443e  lea     rcx, ?g_wszRpcIpPort2@@3PA_WA; String
0x180044445  call    cs:__imp__wtol
0x18004444b  mov     cs:dword_18013C5A8, eax
0x180044451  jmp     short loc_180044496
0x180044453  mov     rcx, cs:WPP_GLOBAL_Control
0x18004445a  cmp     rcx, r14
0x18004445d  jz      short loc_180044483
0x18004445f  test    byte ptr [rcx+0BCh], 1
0x180044466  jz      short loc_180044483
0x180044468  mov     edx, 26h ; '&'
0x18004446d  xor     r9d, r9d
0x180044470  lea     r8, WPP_4bde07fad0d03e40b51473b182e56f08_Traceguids
0x180044477  mov     rcx, [rcx+0B0h]
0x18004447e  call    WPP_SF_d
0x180044483  xor     eax, eax
0x180044485  movzx   r8d, ax; unsigned __int16
0x180044489  mov     edx, ebx; dwMessageId
0x18004448b  mov     ecx, 8000080Bh; unsigned int
0x180044490  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x180044495  nop
0x180044496  call    ?IsUnauthenticatedRpcAllowed@@YA_NXZ; IsUnauthenticatedRpcAllowed(void)
0x18004449b  movzx   ebx, al
0x18004449e  shl     ebx, 4
0x1800444a1  inc     ebx
0x1800444a3  mov     edi, ebx
0x1800444a5  or      edi, 90h
0x1800444ab  mov     r9d, 96h; unsigned __int16
0x1800444b1  mov     dword ptr [rsp+0B8h+Referrer], 400000h; unsigned int
0x1800444b9  lea     r8, ?QMCOMMSecurityCallback@@YAJPEAX0@Z; int (*)(void *, void *)
0x1800444c0  mov     edx, edi; unsigned int
0x1800444c2  lea     rcx, qword_1800F00B0; void *
0x1800444c9  call    ?RegisterInterface@@YAXPEAXIP6AJ00@ZGI@Z; RegisterInterface(void *,uint,long (*)(void *,void *),ushort,uint)
0x1800444ce  mov     r9d, 0FAh; unsigned __int16
0x1800444d4  mov     dword ptr [rsp+0B8h+Referrer], 400000h; unsigned int
0x1800444dc  lea     r8, ?QMCOMM2SecurityCallback@@YAJPEAX0@Z; int (*)(void *, void *)
0x1800444e3  mov     edx, ebx; unsigned int
0x1800444e5  lea     rcx, qword_1800F17B0; void *
0x1800444ec  call    ?RegisterInterface@@YAXPEAXIP6AJ00@ZGI@Z; RegisterInterface(void *,uint,long (*)(void *,void *),ushort,uint)
0x1800444f1  mov     r9d, 109h; unsigned __int16
0x1800444f7  mov     dword ptr [rsp+0B8h+Referrer], 0FFFFFFFFh; unsigned int
0x1800444ff  lea     r8, ?QMMGMTSecurityCallback@@YAJPEAX0@Z; int (*)(void *, void *)
0x180044506  mov     edx, ebx; unsigned int
0x180044508  lea     rcx, qword_1800E94E0; void *
0x18004450f  call    ?RegisterInterface@@YAXPEAXIP6AJ00@ZGI@Z; RegisterInterface(void *,uint,long (*)(void *,void *),ushort,uint)
0x180044514  call    IsOldRemoteReadAllowed
0x180044519  test    al, al
0x18004451b  jz      short loc_180044543
0x18004451d  mov     r9d, 10Eh; unsigned __int16
0x180044523  or      ebx, 10h
0x180044526  mov     dword ptr [rsp+0B8h+Referrer], 0FFFFFFFFh; unsigned int
0x18004452e  lea     r8, ?Qm2QmSecurityCallback@@YAJPEAX0@Z; int (*)(void *, void *)
0x180044535  mov     edx, ebx; unsigned int
0x180044537  lea     rcx, qword_1800E82E0; void *
0x18004453e  call    ?RegisterInterface@@YAXPEAXIP6AJ00@ZGI@Z; RegisterInterface(void *,uint,long (*)(void *,void *),ushort,uint)
0x180044543  mov     r9d, 113h; unsigned __int16
0x180044549  mov     dword ptr [rsp+0B8h+Referrer], 0FFFFFFFFh; unsigned int
0x180044551  lea     r8, ?RemoteReadSecurityCallback@@YAJPEAX0@Z; int (*)(void *, void *)
0x180044558  mov     edx, edi; unsigned int
0x18004455a  lea     rcx, qword_1800F3440; void *
0x180044561  call    ?RegisterInterface@@YAXPEAXIP6AJ00@ZGI@Z; RegisterInterface(void *,uint,long (*)(void *,void *),ushort,uint)
0x180044566  lea     rcx, BindingVector; BindingVector
0x18004456d  call    cs:__imp_RpcServerInqBindings
0x180044573  test    eax, eax
0x180044575  jz      short loc_18004459A
0x180044577  mov     r8d, 118h; unsigned __int16
0x18004457d  mov     edx, eax; int
0x18004457f  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x180044584  call    ??0bad_rpc_result@@QEAA@JG@Z; bad_rpc_result::bad_rpc_result(long,ushort)
0x180044589  lea     rdx, _TI3?AVbad_rpc_result@@; pThrowInfo
0x180044590  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180044595  call    _CxxThrowException_0
0x18004459a  mov     r8d, 11Dh; unsigned __int16
0x1800445a0  lea     rdx, aMessageQueuing; "Message Queuing - QMRT V1"
0x1800445a7  lea     rcx, qword_1800F00B0; void *
0x1800445ae  call    ?RegisterEndpoint@@YAXPEAXPEA_WG@Z; RegisterEndpoint(void *,wchar_t *,ushort)
0x1800445b3  mov     r8d, 122h; unsigned __int16
0x1800445b9  lea     rdx, aMessageQueuing_3; "Message Queuing - QMRT V2"
0x1800445c0  lea     rcx, qword_1800F17B0; void *
0x1800445c7  call    ?RegisterEndpoint@@YAXPEAXPEA_WG@Z; RegisterEndpoint(void *,wchar_t *,ushort)
0x1800445cc  call    IsOldRemoteReadAllowed
0x1800445d1  test    al, al
0x1800445d3  jz      short loc_1800445EE
0x1800445d5  mov     r8d, 127h; unsigned __int16
0x1800445db  lea     rdx, aMessageQueuing_0; "Message Queuing - QM2QM V1"
0x1800445e2  lea     rcx, qword_1800E82E0; void *
0x1800445e9  call    ?RegisterEndpoint@@YAXPEAXPEA_WG@Z; RegisterEndpoint(void *,wchar_t *,ushort)
0x1800445ee  mov     r8d, 12Ch; unsigned __int16
0x1800445f4  lea     rdx, aMessageQueuing_1; "Message Queuing - RemoteRead V1"
0x1800445fb  lea     rcx, qword_1800F3440; void *
0x180044602  call    ?RegisterEndpoint@@YAXPEAXPEA_WG@Z; RegisterEndpoint(void *,wchar_t *,ushort)
0x180044607  nop
0x180044608  xor     r9d, r9d; Arg
0x18004460b  xor     r8d, r8d; GetKeyFn
0x18004460e  lea     edx, [r9+0Ah]; AuthnSvc
0x180044612  xor     ecx, ecx; ServerPrincName
0x180044614  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18004461a  mov     ebx, eax
0x18004461c  test    eax, eax
0x18004461e  jz      short loc_180044646
0x180044620  mov     r8d, 0CDh; unsigned __int16
0x180044626  lea     rdx, aQmrpcsrv; "qmrpcsrv"
0x18004462d  mov     ecx, eax; int
0x18004462f  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x180044634  nop
0x180044635  mov     rcx, [rsp+0B8h+Endpoint]; Block
0x18004463a  call    cs:__imp_free
0x180044640  nop
0x180044641  jmp     loc_180044301
0x180044646  cmp     cs:?g_fPureWorkGroupMachine@@3HA, 0; int g_fPureWorkGroupMachine
0x18004464d  jnz     loc_1800447D7
0x180044653  mov     [rsp+0B8h+var_78], 0
0x18004465b  xor     r9d, r9d; InstancePort
0x18004465e  mov     [rsp+0B8h+pszSpn], r9; pszSpn
0x180044663  lea     rax, [rsp+0B8h+var_78]
0x180044668  mov     [rsp+0B8h+pcSpnLength], rax; pcSpnLength
0x18004466d  mov     [rsp+0B8h+Referrer], r9; Referrer
0x180044672  xor     r8d, r8d; InstanceName
0x180044675  mov     rdx, cs:?g_szComputerDnsName@@3V?$AP@_W@@A; ServiceName
0x18004467c  lea     rcx, ServiceClass; "HOST"
0x180044683  call    cs:__imp_DsMakeSpnW
0x180044689  mov     ebx, eax
0x18004468b  cmp     eax, 6Fh ; 'o'
0x18004468e  jz      short loc_1800446C7
0x180044690  test    eax, eax
0x180044692  jle     short loc_18004469D
0x180044694  movzx   ebx, ax
0x180044697  or      ebx, 80070000h
0x18004469d  test    ebx, ebx
0x18004469f  jns     short loc_1800446B6
0x1800446a1  mov     r8d, 0C8Ah; unsigned __int16
0x1800446a7  lea     rdx, aQmrpcsrv; "qmrpcsrv"
0x1800446ae  mov     ecx, ebx; int
0x1800446b0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800446b5  nop
0x1800446b6  mov     rcx, [rsp+0B8h+Endpoint]; Block
0x1800446bb  call    cs:__imp_free
0x1800446c1  nop
0x1800446c2  jmp     loc_180044301
0x1800446c7  mov     eax, [rsp+0B8h+var_78]
0x1800446cb  inc     eax
0x1800446cd  mov     [rsp+0B8h+var_78], eax
0x1800446d1  mov     ecx, eax
0x1800446d3  mov     eax, 2
0x1800446d8  mul     rcx
0x1800446db  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800446e2  cmovb   rax, rcx
0x1800446e6  mov     rcx, rax; unsigned __int64
0x1800446e9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800446ee  mov     rbx, rax
0x1800446f1  mov     [rsp+0B8h+var_68], rax
0x1800446f6  xor     r9d, r9d; InstancePort
0x1800446f9  mov     [rsp+0B8h+pszSpn], rax; pszSpn
0x1800446fe  lea     rax, [rsp+0B8h+var_78]
0x180044703  mov     [rsp+0B8h+pcSpnLength], rax; pcSpnLength
0x180044708  mov     [rsp+0B8h+Referrer], r9; Referrer
0x18004470d  xor     r8d, r8d; InstanceName
0x180044710  mov     rdx, cs:?g_szComputerDnsName@@3V?$AP@_W@@A; ServiceName
0x180044717  lea     rcx, ServiceClass; "HOST"
0x18004471e  call    cs:__imp_DsMakeSpnW
0x180044724  mov     edi, eax
0x180044726  test    eax, eax
0x180044728  jz      short loc_18004476B
0x18004472a  jle     short loc_180044735
0x18004472c  movzx   edi, ax
0x18004472f  or      edi, 80070000h
0x180044735  test    edi, edi
0x180044737  jns     short loc_18004474E
0x180044739  mov     r8d, 140h; unsigned __int16
0x18004473f  lea     rdx, aQmrpcsrv; "qmrpcsrv"
0x180044746  mov     ecx, edi; int
0x180044748  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004474d  nop
0x18004474e  mov     rcx, rbx; Block
0x180044751  call    cs:__imp_free
0x180044757  nop
0x180044758  mov     rcx, [rsp+0B8h+Endpoint]; Block
0x18004475d  call    cs:__imp_free
0x180044763  nop
0x180044764  mov     eax, edi
0x180044766  jmp     loc_1800447F7
0x18004476b  xor     r9d, r9d; Arg
0x18004476e  xor     r8d, r8d; GetKeyFn
0x180044771  lea     edx, [r9+10h]; AuthnSvc
0x180044775  mov     rcx, rbx; ServerPrincName
0x180044778  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18004477e  mov     edi, eax
0x180044780  mov     rcx, cs:WPP_GLOBAL_Control
0x180044787  cmp     rcx, r14
0x18004478a  jz      short loc_1800447B4
0x18004478c  test    byte ptr [rcx+0BCh], 4
0x180044793  jz      short loc_1800447B4
0x180044795  mov     edx, 27h ; '''
0x18004479a  mov     dword ptr [rsp+0B8h+Referrer], eax; char
0x18004479e  mov     r9, rbx
  ... truncated ...
```
