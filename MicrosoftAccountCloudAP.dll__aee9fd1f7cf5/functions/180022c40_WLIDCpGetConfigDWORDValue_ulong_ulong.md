# WLIDCpGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180022c40`
- end: `0x180022f85`
- name: `?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `837`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019fd8`
- `0x18001ba00`
- `0x180022c40`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022def`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022e41`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022def`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022e41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022d0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ebe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ebe`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022d68`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022d68`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022e77`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022e77`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180022cc4`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180022cc4`
- `RPCRT4!RpcAsyncCancelCall` at `0x180022e13`
- `RPCRT4!RpcAsyncCancelCall` at `0x180022e13`

## string_xrefs

- `0x180022d30`: `RPC failed to create new event, hr = %#x`
- `0x180022e8b`: `RPC Async complete call failed, hr = %#x`
- `0x180022ed6`: `WLIDCpGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall WLIDCpGetConfigDWORDValue(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+40h] [rbp-B8h] BYREF
  char v13; // [rsp+44h] [rbp-B4h]
  int v14; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

  v15 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v15);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v14 = 5000;
  v4 = 0;
  v13 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v8 = 362;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v15, 3, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v7 = L"RPC call failed, hr = %#x";
    v8 = 364;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v8,
      v7,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x1388u, 0);
  do
  {
    if ( v5 || v10 != 258 && v10 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v10 == 258 )
      v4 = 1;
    else
      v5 = 1;
    v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v4 );
  if ( v10 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v8 = 364;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
      (__int64)"WLIDCpGetConfigDWORDValue",
      &v14);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v15);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180022c40  mov     [rsp+arg_0], rsi
0x180022c45  mov     [rsp+arg_10], r14
0x180022c4a  push    r15
0x180022c4c  sub     rsp, 0F0h
0x180022c53  mov     rax, cs:__security_cookie
0x180022c5a  xor     rax, rsp
0x180022c5d  mov     [rsp+0F8h+var_18], rax
0x180022c65  mov     rsi, rdx
0x180022c68  mov     [rsp+0F8h+Reply], 0
0x180022c70  mov     [rsp+0F8h+var_A8], 0
0x180022c79  lea     rcx, [rsp+0F8h+var_A8]; this
0x180022c7e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180022c83  mov     [rsp+0F8h+Reply], eax
0x180022c87  test    eax, eax
0x180022c89  js      loc_180022F5F
0x180022c8f  xor     edx, edx; Val
0x180022c91  lea     r8d, [rdx+70h]; Size
0x180022c95  lea     rcx, [rsp+0F8h+pAsync]; void *
0x180022c9a  call    memset_0
0x180022c9f  mov     [rsp+0F8h+var_B0], 1388h
0x180022ca7  xor     r15b, r15b
0x180022caa  mov     [rsp+0F8h+var_B4], r15b
0x180022caf  xor     r14b, r14b
0x180022cb2  xorps   xmm0, xmm0
0x180022cb5  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180022cba  mov     edx, 70h ; 'p'; Size
0x180022cbf  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180022cc4  call    cs:__imp_RpcAsyncInitializeHandle
0x180022cca  test    eax, eax
0x180022ccc  jz      short loc_180022CEA
0x180022cce  jle     short loc_180022CD8
0x180022cd0  movzx   eax, ax
0x180022cd3  or      eax, 80070000h
0x180022cd8  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180022cdf  mov     r8d, 16Ah
0x180022ce5  jmp     loc_180022E98
0x180022cea  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x180022cf6  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x180022d01  xor     r9d, r9d; lpName
0x180022d04  xor     r8d, r8d; bInitialState
0x180022d07  xor     edx, edx; bManualReset
0x180022d09  xor     ecx, ecx; lpEventAttributes
0x180022d0b  call    cs:__imp_CreateEventW
0x180022d11  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x180022d19  test    rax, rax
0x180022d1c  jnz     short loc_180022D39
0x180022d1e  call    cs:__imp_GetLastError
0x180022d24  test    eax, eax
0x180022d26  jle     short loc_180022D30
0x180022d28  movzx   eax, ax
0x180022d2b  or      eax, 80070000h
0x180022d30  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180022d37  jmp     short loc_180022CDF
0x180022d39  mov     [rsp+0F8h+Handles], rax
0x180022d3e  mov     [rsp+0F8h+var_C8], rsi
0x180022d43  mov     [rsp+0F8h+var_D0], 3
0x180022d4b  mov     rax, [rsp+0F8h+var_A8]
0x180022d50  mov     qword ptr [rsp+0F8h+bAlertable], rax
0x180022d55  lea     r9, [rsp+0F8h+pAsync]
0x180022d5a  xor     r8d, r8d; pReturnValue
0x180022d5d  lea     edx, [r8+36h]; nProcNum
0x180022d61  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180022d68  call    cs:__imp_Ndr64AsyncClientCall
0x180022d6e  mov     eax, [rsp+0F8h+Reply]
0x180022d72  jmp     short loc_180022DBF
0x180022d74  test    eax, eax
0x180022d76  jle     short loc_180022D80
0x180022d78  movzx   eax, ax
0x180022d7b  or      eax, 80070000h
0x180022d80  mov     [rsp+0F8h+Reply], eax
0x180022d84  mov     [rsp+0F8h+bAlertable], eax
0x180022d88  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180022d8f  mov     r8d, 16Ch; unsigned int
0x180022d95  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022d9c  mov     ecx, 2; unsigned __int8
0x180022da1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022da6  mov     eax, [rsp+0F8h+Reply]
0x180022daa  test    eax, eax
0x180022dac  js      short loc_180022DB7
0x180022dae  mov     eax, 8000FFFFh
0x180022db3  mov     [rsp+0F8h+Reply], eax
0x180022db7  mov     r15b, [rsp+0F8h+var_B4]
0x180022dbc  mov     r14b, r15b
0x180022dbf  test    eax, eax
0x180022dc1  jns     short loc_180022DD5
0x180022dc3  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180022dca  mov     r8d, 16Ch
0x180022dd0  jmp     loc_180022E9C
0x180022dd5  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180022ddd  mov     r9d, 1388h; dwMilliseconds
0x180022de3  xor     r8d, r8d; bWaitAll
0x180022de6  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180022deb  lea     ecx, [r8+1]; nCount
0x180022def  call    cs:__imp_WaitForMultipleObjectsEx
0x180022df5  mov     esi, eax
0x180022df7  test    r14b, r14b
0x180022dfa  jnz     short loc_180022E4E
0x180022dfc  cmp     esi, 102h
0x180022e02  jz      short loc_180022E09
0x180022e04  cmp     esi, 1
0x180022e07  jnz     short loc_180022E4E
0x180022e09  mov     edx, 1; fAbort
0x180022e0e  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180022e13  call    cs:__imp_RpcAsyncCancelCall
0x180022e19  cmp     esi, 102h
0x180022e1f  jnz     short loc_180022E26
0x180022e21  mov     r15b, 1
0x180022e24  jmp     short loc_180022E29
0x180022e26  mov     r14b, 1
0x180022e29  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180022e31  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180022e35  xor     r8d, r8d; bWaitAll
0x180022e38  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180022e3d  lea     ecx, [r8+1]; nCount
0x180022e41  call    cs:__imp_WaitForMultipleObjectsEx
0x180022e47  mov     esi, eax
0x180022e49  test    r15b, r15b
0x180022e4c  jz      short loc_180022DF7
0x180022e4e  test    esi, esi
0x180022e50  jz      short loc_180022E6D
0x180022e52  call    cs:__imp_GetLastError
0x180022e58  test    eax, eax
0x180022e5a  jle     short loc_180022E64
0x180022e5c  movzx   eax, ax
0x180022e5f  or      eax, 80070000h
0x180022e64  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180022e6b  jmp     short loc_180022E92
0x180022e6d  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180022e72  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180022e77  call    cs:__imp_RpcAsyncCompleteCall
0x180022e7d  test    eax, eax
0x180022e7f  jz      short loc_180022EB1
0x180022e81  jle     short loc_180022E8B
0x180022e83  movzx   eax, ax
0x180022e86  or      eax, 80070000h
0x180022e8b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180022e92  mov     r8d, 16Ch; unsigned int
0x180022e98  mov     [rsp+0F8h+Reply], eax
0x180022e9c  mov     [rsp+0F8h+bAlertable], eax
0x180022ea0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022ea7  mov     ecx, 2; unsigned __int8
0x180022eac  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022eb1  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180022eb9  test    rcx, rcx
0x180022ebc  jz      short loc_180022EC4
0x180022ebe  call    cs:__imp_CloseHandle
0x180022ec4  test    r15b, r15b
0x180022ec7  jz      short loc_180022F08
0x180022ec9  mov     [rsp+0F8h+Reply], 800705B4h
0x180022ed1  lea     rdx, [rsp+0F8h+var_B0]
0x180022ed6  lea     rcx, aWlidcpgetconfi; "WLIDCpGetConfigDWORDValue"
0x180022edd  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x180022ee2  mov     eax, [rsp+0F8h+Reply]
0x180022ee6  mov     [rsp+0F8h+bAlertable], eax
0x180022eea  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180022ef1  mov     r8d, 16Ch; unsigned int
0x180022ef7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022efe  mov     ecx, 2; unsigned __int8
0x180022f03  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022f08  test    r14b, r14b
0x180022f0b  jz      short loc_180022F38
0x180022f0d  mov     eax, 800704C7h
0x180022f12  mov     [rsp+0F8h+Reply], eax
0x180022f16  mov     [rsp+0F8h+bAlertable], eax
0x180022f1a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180022f21  mov     r8d, 16Ch; unsigned int
0x180022f27  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022f2e  mov     ecx, 2; unsigned __int8
0x180022f33  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022f38  cmp     [rsp+0F8h+Reply], 800706B5h
0x180022f40  jz      short loc_180022F4C
0x180022f42  cmp     [rsp+0F8h+Reply], 800706BAh
0x180022f4a  jnz     short loc_180022F51
0x180022f4c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180022f51  lea     rcx, [rsp+0F8h+var_A8]; this
0x180022f56  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180022f5b  mov     eax, [rsp+0F8h+Reply]
0x180022f5f  mov     rcx, [rsp+0F8h+var_18]
0x180022f67  xor     rcx, rsp; StackCookie
0x180022f6a  call    __security_check_cookie
0x180022f6f  lea     r11, [rsp+0F8h+var_8]
0x180022f77  mov     rsi, [r11+10h]
0x180022f7b  mov     r14, [r11+20h]
0x180022f7f  mov     rsp, r11
0x180022f82  pop     r15
0x180022f84  retn
0x180030a74  push    rbp
0x180030a76  sub     rsp, 40h
0x180030a7a  mov     rbp, rdx
0x180030a7d  mov     rcx, [rcx]
0x180030a80  mov     ecx, [rcx]; unsigned int
0x180030a82  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180030a87  nop
0x180030a88  add     rsp, 40h
0x180030a8c  pop     rbp
0x180030a8d  retn
```
