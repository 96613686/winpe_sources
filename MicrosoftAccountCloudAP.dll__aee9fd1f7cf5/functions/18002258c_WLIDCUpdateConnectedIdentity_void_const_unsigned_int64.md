# WLIDCUpdateConnectedIdentity(void * const,unsigned __int64)

- ea: `0x18002258c`
- end: `0x1800228b5`
- name: `?WLIDCUpdateConnectedIdentity@@YAJQEAX_K@Z`
- size: `809`
- prototype: `__int64 __fastcall(void *const, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180019990`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a0ec`
- `0x18001ba00`
- `0x180020750`
- `0x18002258c`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022727`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022779`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022727`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022779`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002264f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002264f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002278a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227f6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002269f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002269f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800227af`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800227af`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002260e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002260e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002274e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002274e`

## string_xrefs

- `0x180022674`: `RPC failed to create new event, hr = %#x`
- `0x1800227c3`: `RPC Async complete call failed, hr = %#x`
- `0x18002280e`: `WLIDCUpdateConnectedIdentity`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateConnectedIdentity(void *const a1, __int64 a2)
{
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  unsigned int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v15; // [rsp+34h] [rbp-B4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-B0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-ACh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-98h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v17 = dwMilliseconds;
  v5 = 0;
  v15 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v9 = 500;
    goto LABEL_27;
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
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 4u, 0, &pAsync, a1, a2);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
  }
  v9 = 502;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v9, v8, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>(
      (__int64)"WLIDCUpdateConnectedIdentity",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1F6u,
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
      0x1F6u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  result = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    return Reply;
  }
  return result;
}

```

## disassembly

```asm
0x18002258c  mov     [rsp+arg_10], rsi
0x180022591  mov     [rsp+arg_18], r12
0x180022596  push    r13
0x180022598  push    r14
0x18002259a  push    r15
0x18002259c  sub     rsp, 0D0h
0x1800225a3  mov     rax, cs:__security_cookie
0x1800225aa  xor     rax, rsp
0x1800225ad  mov     [rsp+0E8h+var_28], rax
0x1800225b5  mov     r13, rdx
0x1800225b8  mov     r12, rcx
0x1800225bb  mov     [rsp+0E8h+Reply], 0
0x1800225c3  mov     [rsp+0E8h+dwMilliseconds], 0
0x1800225cb  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x1800225d0  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800225d5  xor     edx, edx; Val
0x1800225d7  lea     r8d, [rdx+70h]; Size
0x1800225db  lea     rcx, [rsp+0E8h+pAsync]; void *
0x1800225e0  call    memset_0
0x1800225e5  mov     esi, [rsp+0E8h+dwMilliseconds]
0x1800225e9  mov     [rsp+0E8h+dwMilliseconds], esi
0x1800225ed  mov     [rsp+0E8h+var_AC], esi
0x1800225f1  xor     r15b, r15b
0x1800225f4  mov     [rsp+0E8h+var_B4], r15b
0x1800225f9  xor     r14b, r14b
0x1800225fc  xorps   xmm0, xmm0
0x1800225ff  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x180022604  mov     edx, 70h ; 'p'; Size
0x180022609  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18002260e  call    cs:__imp_RpcAsyncInitializeHandle
0x180022614  test    eax, eax
0x180022616  jz      short loc_180022634
0x180022618  jle     short loc_180022622
0x18002261a  movzx   eax, ax
0x18002261d  or      eax, 80070000h
0x180022622  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180022629  mov     r8d, 1F4h
0x18002262f  jmp     loc_1800227D0
0x180022634  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18002263d  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x180022645  xor     r9d, r9d; lpName
0x180022648  xor     r8d, r8d; bInitialState
0x18002264b  xor     edx, edx; bManualReset
0x18002264d  xor     ecx, ecx; lpEventAttributes
0x18002264f  call    cs:__imp_CreateEventW
0x180022655  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18002265d  test    rax, rax
0x180022660  jnz     short loc_18002267D
0x180022662  call    cs:__imp_GetLastError
0x180022668  test    eax, eax
0x18002266a  jle     short loc_180022674
0x18002266c  movzx   eax, ax
0x18002266f  or      eax, 80070000h
0x180022674  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18002267b  jmp     short loc_180022629
0x18002267d  mov     [rsp+0E8h+Handles], rax
0x180022682  mov     [rsp+0E8h+var_C0], r13
0x180022687  mov     qword ptr [rsp+0E8h+bAlertable], r12
0x18002268c  lea     r9, [rsp+0E8h+pAsync]
0x180022691  xor     r8d, r8d; pReturnValue
0x180022694  lea     edx, [r8+4]; nProcNum
0x180022698  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18002269f  call    cs:__imp_Ndr64AsyncClientCall
0x1800226a5  mov     eax, [rsp+0E8h+Reply]
0x1800226a9  jmp     short loc_1800226FA
0x1800226ab  test    eax, eax
0x1800226ad  jle     short loc_1800226B7
0x1800226af  movzx   eax, ax
0x1800226b2  or      eax, 80070000h
0x1800226b7  mov     [rsp+0E8h+Reply], eax
0x1800226bb  mov     [rsp+0E8h+bAlertable], eax
0x1800226bf  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800226c6  mov     r8d, 1F6h; unsigned int
0x1800226cc  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800226d3  mov     ecx, 2; unsigned __int8
0x1800226d8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800226dd  mov     eax, [rsp+0E8h+Reply]
0x1800226e1  test    eax, eax
0x1800226e3  js      short loc_1800226EE
0x1800226e5  mov     eax, 8000FFFFh
0x1800226ea  mov     [rsp+0E8h+Reply], eax
0x1800226ee  mov     esi, [rsp+0E8h+dwMilliseconds]
0x1800226f2  mov     r15b, [rsp+0E8h+var_B4]
0x1800226f7  mov     r14b, r15b
0x1800226fa  test    eax, eax
0x1800226fc  jns     short loc_180022710
0x1800226fe  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180022705  mov     r8d, 1F6h
0x18002270b  jmp     loc_1800227D4
0x180022710  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180022718  mov     r9d, esi; dwMilliseconds
0x18002271b  xor     r8d, r8d; bWaitAll
0x18002271e  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180022723  lea     ecx, [r8+1]; nCount
0x180022727  call    cs:__imp_WaitForMultipleObjectsEx
0x18002272d  mov     esi, eax
0x18002272f  mov     r12d, 102h
0x180022735  test    r14b, r14b
0x180022738  jnz     short loc_180022786
0x18002273a  cmp     esi, r12d
0x18002273d  jz      short loc_180022744
0x18002273f  cmp     esi, 1
0x180022742  jnz     short loc_180022786
0x180022744  mov     edx, 1; fAbort
0x180022749  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18002274e  call    cs:__imp_RpcAsyncCancelCall
0x180022754  cmp     esi, r12d
0x180022757  jnz     short loc_18002275E
0x180022759  mov     r15b, 1
0x18002275c  jmp     short loc_180022761
0x18002275e  mov     r14b, 1
0x180022761  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180022769  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002276d  xor     r8d, r8d; bWaitAll
0x180022770  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180022775  lea     ecx, [r8+1]; nCount
0x180022779  call    cs:__imp_WaitForMultipleObjectsEx
0x18002277f  mov     esi, eax
0x180022781  test    r15b, r15b
0x180022784  jz      short loc_180022735
0x180022786  test    esi, esi
0x180022788  jz      short loc_1800227A5
0x18002278a  call    cs:__imp_GetLastError
0x180022790  test    eax, eax
0x180022792  jle     short loc_18002279C
0x180022794  movzx   eax, ax
0x180022797  or      eax, 80070000h
0x18002279c  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800227a3  jmp     short loc_1800227CA
0x1800227a5  lea     rdx, [rsp+0E8h+Reply]; Reply
0x1800227aa  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1800227af  call    cs:__imp_RpcAsyncCompleteCall
0x1800227b5  test    eax, eax
0x1800227b7  jz      short loc_1800227E9
0x1800227b9  jle     short loc_1800227C3
0x1800227bb  movzx   eax, ax
0x1800227be  or      eax, 80070000h
0x1800227c3  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800227ca  mov     r8d, 1F6h; unsigned int
0x1800227d0  mov     [rsp+0E8h+Reply], eax
0x1800227d4  mov     [rsp+0E8h+bAlertable], eax
0x1800227d8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800227df  mov     ecx, 2; unsigned __int8
0x1800227e4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800227e9  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x1800227f1  test    rcx, rcx
0x1800227f4  jz      short loc_1800227FC
0x1800227f6  call    cs:__imp_CloseHandle
0x1800227fc  test    r15b, r15b
0x1800227ff  jz      short loc_180022840
0x180022801  mov     [rsp+0E8h+Reply], 800705B4h
0x180022809  lea     rdx, [rsp+0E8h+var_AC]
0x18002280e  lea     rcx, aWlidcupdatecon; "WLIDCUpdateConnectedIdentity"
0x180022815  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x18002281a  mov     eax, [rsp+0E8h+Reply]
0x18002281e  mov     [rsp+0E8h+bAlertable], eax
0x180022822  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180022829  mov     r8d, 1F6h; unsigned int
0x18002282f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022836  mov     ecx, 2; unsigned __int8
0x18002283b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022840  test    r14b, r14b
0x180022843  jz      short loc_180022870
0x180022845  mov     eax, 800704C7h
0x18002284a  mov     [rsp+0E8h+Reply], eax
0x18002284e  mov     [rsp+0E8h+bAlertable], eax
0x180022852  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180022859  mov     r8d, 1F6h; unsigned int
0x18002285f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022866  mov     ecx, 2; unsigned __int8
0x18002286b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022870  mov     eax, [rsp+0E8h+Reply]
0x180022874  cmp     eax, 800706B5h
0x180022879  jz      short loc_180022882
0x18002287b  cmp     eax, 800706BAh
0x180022880  jnz     short loc_18002288B
0x180022882  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180022887  mov     eax, [rsp+0E8h+Reply]
0x18002288b  mov     rcx, [rsp+0E8h+var_28]
0x180022893  xor     rcx, rsp; StackCookie
0x180022896  call    __security_check_cookie
0x18002289b  lea     r11, [rsp+0E8h+var_18]
0x1800228a3  mov     rsi, [r11+30h]
0x1800228a7  mov     r12, [r11+38h]
0x1800228ab  mov     rsp, r11
0x1800228ae  pop     r15
0x1800228b0  pop     r14
0x1800228b2  pop     r13
0x1800228b4  retn
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
