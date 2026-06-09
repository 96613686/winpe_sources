# WLIDCGetDeviceDAToken(ushort * *)

- ea: `0x18001eba4`
- end: `0x18001eeea`
- name: `?WLIDCGetDeviceDAToken@@YAJPEAPEAG@Z`
- size: `838`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019750`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019dac`
- `0x18001ba00`
- `0x18001eba4`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ed5b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001edad`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ed5b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001edad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ec7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ec7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee2a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001ecd3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001ecd3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ede3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ede3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ec3a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ec3a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ed82`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ed82`

## string_xrefs

- `0x18001eca3`: `RPC failed to create new event, hr = %#x`
- `0x18001edf7`: `RPC Async complete call failed, hr = %#x`
- `0x18001ee42`: `WLIDCGetDeviceDAToken`

## pseudocode

```c
__int64 __fastcall WLIDCGetDeviceDAToken(unsigned __int16 **a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1353;
LABEL_30:
    Reply = LastError;
    goto LABEL_31;
  }
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
  pAsync.u.APC.NotificationRoutine = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x40u, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1355;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, v4, 0);
  do
  {
    if ( v6 || v11 != 258 && v11 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v11 == 258 )
      v5 = 1;
    else
      v6 = 1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v5 );
  if ( v11 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v9 = 1355;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>(
      (__int64)"WLIDCGetDeviceDAToken",
      (int *)&v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x54Bu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v6 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x54Bu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18001eba4  push    rsi
0x18001eba6  push    r12
0x18001eba8  push    r14
0x18001ebaa  push    r15
0x18001ebac  sub     rsp, 0E8h
0x18001ebb3  mov     rax, cs:__security_cookie
0x18001ebba  xor     rax, rsp
0x18001ebbd  mov     [rsp+108h+var_38], rax
0x18001ebc5  mov     r12, rcx
0x18001ebc8  mov     [rsp+108h+dwMilliseconds], 0
0x18001ebd0  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001ebd5  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001ebda  mov     [rsp+108h+Reply], 0
0x18001ebe2  mov     [rsp+108h+var_C8], 0
0x18001ebeb  lea     rcx, [rsp+108h+var_C8]; this
0x18001ebf0  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001ebf5  mov     [rsp+108h+Reply], eax
0x18001ebf9  test    eax, eax
0x18001ebfb  js      loc_18001EECB
0x18001ec01  xor     edx, edx; Val
0x18001ec03  lea     r8d, [rdx+70h]; Size
0x18001ec07  lea     rcx, [rsp+108h+pAsync]; void *
0x18001ec0c  call    memset_0
0x18001ec11  mov     esi, [rsp+108h+dwMilliseconds]
0x18001ec15  mov     [rsp+108h+dwMilliseconds], esi
0x18001ec19  mov     [rsp+108h+var_CC], esi
0x18001ec1d  xor     r15b, r15b
0x18001ec20  mov     [rsp+108h+var_D4], r15b
0x18001ec25  xor     r14b, r14b
0x18001ec28  xorps   xmm0, xmm0
0x18001ec2b  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001ec30  mov     edx, 70h ; 'p'; Size
0x18001ec35  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ec3a  call    cs:__imp_RpcAsyncInitializeHandle
0x18001ec40  test    eax, eax
0x18001ec42  jz      short loc_18001EC60
0x18001ec44  jle     short loc_18001EC4E
0x18001ec46  movzx   eax, ax
0x18001ec49  or      eax, 80070000h
0x18001ec4e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001ec55  mov     r8d, 549h
0x18001ec5b  jmp     loc_18001EE04
0x18001ec60  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001ec69  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001ec74  xor     r9d, r9d; lpName
0x18001ec77  xor     r8d, r8d; bInitialState
0x18001ec7a  xor     edx, edx; bManualReset
0x18001ec7c  xor     ecx, ecx; lpEventAttributes
0x18001ec7e  call    cs:__imp_CreateEventW
0x18001ec84  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001ec8c  test    rax, rax
0x18001ec8f  jnz     short loc_18001ECAC
0x18001ec91  call    cs:__imp_GetLastError
0x18001ec97  test    eax, eax
0x18001ec99  jle     short loc_18001ECA3
0x18001ec9b  movzx   eax, ax
0x18001ec9e  or      eax, 80070000h
0x18001eca3  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001ecaa  jmp     short loc_18001EC55
0x18001ecac  mov     [rsp+108h+Handles], rax
0x18001ecb1  mov     [rsp+108h+var_E0], r12
0x18001ecb6  mov     rax, [rsp+108h+var_C8]
0x18001ecbb  mov     qword ptr [rsp+108h+bAlertable], rax
0x18001ecc0  lea     r9, [rsp+108h+pAsync]
0x18001ecc5  xor     r8d, r8d; pReturnValue
0x18001ecc8  lea     edx, [r8+40h]; nProcNum
0x18001eccc  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001ecd3  call    cs:__imp_Ndr64AsyncClientCall
0x18001ecd9  mov     eax, [rsp+108h+Reply]
0x18001ecdd  jmp     short loc_18001ED2E
0x18001ecdf  test    eax, eax
0x18001ece1  jle     short loc_18001ECEB
0x18001ece3  movzx   eax, ax
0x18001ece6  or      eax, 80070000h
0x18001eceb  mov     [rsp+108h+Reply], eax
0x18001ecef  mov     [rsp+108h+bAlertable], eax
0x18001ecf3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001ecfa  mov     r8d, 54Bh; unsigned int
0x18001ed00  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ed07  mov     ecx, 2; unsigned __int8
0x18001ed0c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ed11  mov     eax, [rsp+108h+Reply]
0x18001ed15  test    eax, eax
0x18001ed17  js      short loc_18001ED22
0x18001ed19  mov     eax, 8000FFFFh
0x18001ed1e  mov     [rsp+108h+Reply], eax
0x18001ed22  mov     esi, [rsp+108h+dwMilliseconds]
0x18001ed26  mov     r15b, [rsp+108h+var_D4]
0x18001ed2b  mov     r14b, r15b
0x18001ed2e  test    eax, eax
0x18001ed30  jns     short loc_18001ED44
0x18001ed32  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001ed39  mov     r8d, 54Bh
0x18001ed3f  jmp     loc_18001EE08
0x18001ed44  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001ed4c  mov     r9d, esi; dwMilliseconds
0x18001ed4f  xor     r8d, r8d; bWaitAll
0x18001ed52  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001ed57  lea     ecx, [r8+1]; nCount
0x18001ed5b  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ed61  mov     esi, eax
0x18001ed63  mov     r12d, 102h
0x18001ed69  test    r14b, r14b
0x18001ed6c  jnz     short loc_18001EDBA
0x18001ed6e  cmp     esi, r12d
0x18001ed71  jz      short loc_18001ED78
0x18001ed73  cmp     esi, 1
0x18001ed76  jnz     short loc_18001EDBA
0x18001ed78  mov     edx, 1; fAbort
0x18001ed7d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ed82  call    cs:__imp_RpcAsyncCancelCall
0x18001ed88  cmp     esi, r12d
0x18001ed8b  jnz     short loc_18001ED92
0x18001ed8d  mov     r15b, 1
0x18001ed90  jmp     short loc_18001ED95
0x18001ed92  mov     r14b, 1
0x18001ed95  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001ed9d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001eda1  xor     r8d, r8d; bWaitAll
0x18001eda4  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001eda9  lea     ecx, [r8+1]; nCount
0x18001edad  call    cs:__imp_WaitForMultipleObjectsEx
0x18001edb3  mov     esi, eax
0x18001edb5  test    r15b, r15b
0x18001edb8  jz      short loc_18001ED69
0x18001edba  test    esi, esi
0x18001edbc  jz      short loc_18001EDD9
0x18001edbe  call    cs:__imp_GetLastError
0x18001edc4  test    eax, eax
0x18001edc6  jle     short loc_18001EDD0
0x18001edc8  movzx   eax, ax
0x18001edcb  or      eax, 80070000h
0x18001edd0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001edd7  jmp     short loc_18001EDFE
0x18001edd9  lea     rdx, [rsp+108h+Reply]; Reply
0x18001edde  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ede3  call    cs:__imp_RpcAsyncCompleteCall
0x18001ede9  test    eax, eax
0x18001edeb  jz      short loc_18001EE1D
0x18001eded  jle     short loc_18001EDF7
0x18001edef  movzx   eax, ax
0x18001edf2  or      eax, 80070000h
0x18001edf7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001edfe  mov     r8d, 54Bh; unsigned int
0x18001ee04  mov     [rsp+108h+Reply], eax
0x18001ee08  mov     [rsp+108h+bAlertable], eax
0x18001ee0c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ee13  mov     ecx, 2; unsigned __int8
0x18001ee18  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ee1d  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001ee25  test    rcx, rcx
0x18001ee28  jz      short loc_18001EE30
0x18001ee2a  call    cs:__imp_CloseHandle
0x18001ee30  test    r15b, r15b
0x18001ee33  jz      short loc_18001EE74
0x18001ee35  mov     [rsp+108h+Reply], 800705B4h
0x18001ee3d  lea     rdx, [rsp+108h+var_CC]
0x18001ee42  lea     rcx, aWlidcgetdevice; "WLIDCGetDeviceDAToken"
0x18001ee49  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x18001ee4e  mov     eax, [rsp+108h+Reply]
0x18001ee52  mov     [rsp+108h+bAlertable], eax
0x18001ee56  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001ee5d  mov     r8d, 54Bh; unsigned int
0x18001ee63  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ee6a  mov     ecx, 2; unsigned __int8
0x18001ee6f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ee74  test    r14b, r14b
0x18001ee77  jz      short loc_18001EEA4
0x18001ee79  mov     eax, 800704C7h
0x18001ee7e  mov     [rsp+108h+Reply], eax
0x18001ee82  mov     [rsp+108h+bAlertable], eax
0x18001ee86  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001ee8d  mov     r8d, 54Bh; unsigned int
0x18001ee93  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ee9a  mov     ecx, 2; unsigned __int8
0x18001ee9f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001eea4  cmp     [rsp+108h+Reply], 800706B5h
0x18001eeac  jz      short loc_18001EEB8
0x18001eeae  cmp     [rsp+108h+Reply], 800706BAh
0x18001eeb6  jnz     short loc_18001EEBD
0x18001eeb8  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001eebd  lea     rcx, [rsp+108h+var_C8]; this
0x18001eec2  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001eec7  mov     eax, [rsp+108h+Reply]
0x18001eecb  mov     rcx, [rsp+108h+var_38]
0x18001eed3  xor     rcx, rsp; StackCookie
0x18001eed6  call    __security_check_cookie
0x18001eedb  add     rsp, 0E8h
0x18001eee2  pop     r15
0x18001eee4  pop     r14
0x18001eee6  pop     r12
0x18001eee8  pop     rsi
0x18001eee9  retn
0x180030717  push    rbp
0x180030719  sub     rsp, 30h
0x18003071d  mov     rbp, rdx
0x180030720  mov     rcx, [rcx]
0x180030723  mov     ecx, [rcx]; unsigned int
0x180030725  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x18003072a  nop
0x18003072b  add     rsp, 30h
0x18003072f  pop     rbp
0x180030730  retn
```
