# WLIDCDisconnectIdentity(void * const)

- ea: `0x18001dab0`
- end: `0x18001ddb7`
- name: `?WLIDCDisconnectIdentity@@YAJQEAX@Z`
- size: `775`
- prototype: `__int64 __fastcall(void *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800196c0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019ec4`
- `0x18001ba00`
- `0x18001dab0`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dc3b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dc8d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dc3b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dc8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001db68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001db68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd0a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001dbb3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001dbb3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001dcc3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001dcc3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001db27`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001db27`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001dc62`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001dc62`

## string_xrefs

- `0x18001db8d`: `RPC failed to create new event, hr = %#x`
- `0x18001dcd7`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCDisconnectIdentity(void *const a1, unsigned int a2)
{
  DWORD v3; // esi
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  unsigned int Reply; // [rsp+30h] [rbp-C8h] BYREF
  char v15; // [rsp+34h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-BCh] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-A8h] BYREF

  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v3 = dwMilliseconds;
  v17 = dwMilliseconds;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v8 = 509;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 5u, 0, &pAsync, a1);
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, v3, 0);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
  }
  v8 = 511;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v8, v7, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[24],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1FFu,
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
      0x1FFu,
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
0x18001dab0  push    rsi
0x18001dab2  push    r12
0x18001dab4  push    r14
0x18001dab6  push    r15
0x18001dab8  sub     rsp, 0D8h
0x18001dabf  mov     rax, cs:__security_cookie
0x18001dac6  xor     rax, rsp
0x18001dac9  mov     [rsp+0F8h+var_38], rax
0x18001dad1  mov     r12, rcx
0x18001dad4  mov     [rsp+0F8h+Reply], 0
0x18001dadc  mov     [rsp+0F8h+dwMilliseconds], 0
0x18001dae4  lea     r8, [rsp+0F8h+dwMilliseconds]; unsigned int *
0x18001dae9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001daee  xor     edx, edx; Val
0x18001daf0  lea     r8d, [rdx+70h]; Size
0x18001daf4  lea     rcx, [rsp+0F8h+pAsync]; void *
0x18001daf9  call    memset_0
0x18001dafe  mov     esi, [rsp+0F8h+dwMilliseconds]
0x18001db02  mov     [rsp+0F8h+dwMilliseconds], esi
0x18001db06  mov     [rsp+0F8h+var_BC], esi
0x18001db0a  xor     r15b, r15b
0x18001db0d  mov     [rsp+0F8h+var_C4], r15b
0x18001db12  xor     r14b, r14b
0x18001db15  xorps   xmm0, xmm0
0x18001db18  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x18001db1d  mov     edx, 70h ; 'p'; Size
0x18001db22  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18001db27  call    cs:__imp_RpcAsyncInitializeHandle
0x18001db2d  test    eax, eax
0x18001db2f  jz      short loc_18001DB4D
0x18001db31  jle     short loc_18001DB3B
0x18001db33  movzx   eax, ax
0x18001db36  or      eax, 80070000h
0x18001db3b  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001db42  mov     r8d, 1FDh
0x18001db48  jmp     loc_18001DCE4
0x18001db4d  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x18001db56  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x18001db5e  xor     r9d, r9d; lpName
0x18001db61  xor     r8d, r8d; bInitialState
0x18001db64  xor     edx, edx; bManualReset
0x18001db66  xor     ecx, ecx; lpEventAttributes
0x18001db68  call    cs:__imp_CreateEventW
0x18001db6e  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x18001db76  test    rax, rax
0x18001db79  jnz     short loc_18001DB96
0x18001db7b  call    cs:__imp_GetLastError
0x18001db81  test    eax, eax
0x18001db83  jle     short loc_18001DB8D
0x18001db85  movzx   eax, ax
0x18001db88  or      eax, 80070000h
0x18001db8d  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001db94  jmp     short loc_18001DB42
0x18001db96  mov     [rsp+0F8h+Handles], rax
0x18001db9b  mov     qword ptr [rsp+0F8h+bAlertable], r12
0x18001dba0  lea     r9, [rsp+0F8h+pAsync]
0x18001dba5  xor     r8d, r8d; pReturnValue
0x18001dba8  lea     edx, [r8+5]; nProcNum
0x18001dbac  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001dbb3  call    cs:__imp_Ndr64AsyncClientCall
0x18001dbb9  mov     eax, [rsp+0F8h+Reply]
0x18001dbbd  jmp     short loc_18001DC0E
0x18001dbbf  test    eax, eax
0x18001dbc1  jle     short loc_18001DBCB
0x18001dbc3  movzx   eax, ax
0x18001dbc6  or      eax, 80070000h
0x18001dbcb  mov     [rsp+0F8h+Reply], eax
0x18001dbcf  mov     [rsp+0F8h+bAlertable], eax
0x18001dbd3  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001dbda  mov     r8d, 1FFh; unsigned int
0x18001dbe0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001dbe7  mov     ecx, 2; unsigned __int8
0x18001dbec  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001dbf1  mov     eax, [rsp+0F8h+Reply]
0x18001dbf5  test    eax, eax
0x18001dbf7  js      short loc_18001DC02
0x18001dbf9  mov     eax, 8000FFFFh
0x18001dbfe  mov     [rsp+0F8h+Reply], eax
0x18001dc02  mov     esi, [rsp+0F8h+dwMilliseconds]
0x18001dc06  mov     r15b, [rsp+0F8h+var_C4]
0x18001dc0b  mov     r14b, r15b
0x18001dc0e  test    eax, eax
0x18001dc10  jns     short loc_18001DC24
0x18001dc12  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001dc19  mov     r8d, 1FFh
0x18001dc1f  jmp     loc_18001DCE8
0x18001dc24  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18001dc2c  mov     r9d, esi; dwMilliseconds
0x18001dc2f  xor     r8d, r8d; bWaitAll
0x18001dc32  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18001dc37  lea     ecx, [r8+1]; nCount
0x18001dc3b  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dc41  mov     esi, eax
0x18001dc43  mov     r12d, 102h
0x18001dc49  test    r14b, r14b
0x18001dc4c  jnz     short loc_18001DC9A
0x18001dc4e  cmp     esi, r12d
0x18001dc51  jz      short loc_18001DC58
0x18001dc53  cmp     esi, 1
0x18001dc56  jnz     short loc_18001DC9A
0x18001dc58  mov     edx, 1; fAbort
0x18001dc5d  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18001dc62  call    cs:__imp_RpcAsyncCancelCall
0x18001dc68  cmp     esi, r12d
0x18001dc6b  jnz     short loc_18001DC72
0x18001dc6d  mov     r15b, 1
0x18001dc70  jmp     short loc_18001DC75
0x18001dc72  mov     r14b, 1
0x18001dc75  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x18001dc7d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001dc81  xor     r8d, r8d; bWaitAll
0x18001dc84  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x18001dc89  lea     ecx, [r8+1]; nCount
0x18001dc8d  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dc93  mov     esi, eax
0x18001dc95  test    r15b, r15b
0x18001dc98  jz      short loc_18001DC49
0x18001dc9a  test    esi, esi
0x18001dc9c  jz      short loc_18001DCB9
0x18001dc9e  call    cs:__imp_GetLastError
0x18001dca4  test    eax, eax
0x18001dca6  jle     short loc_18001DCB0
0x18001dca8  movzx   eax, ax
0x18001dcab  or      eax, 80070000h
0x18001dcb0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001dcb7  jmp     short loc_18001DCDE
0x18001dcb9  lea     rdx, [rsp+0F8h+Reply]; Reply
0x18001dcbe  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x18001dcc3  call    cs:__imp_RpcAsyncCompleteCall
0x18001dcc9  test    eax, eax
0x18001dccb  jz      short loc_18001DCFD
0x18001dccd  jle     short loc_18001DCD7
0x18001dccf  movzx   eax, ax
0x18001dcd2  or      eax, 80070000h
0x18001dcd7  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001dcde  mov     r8d, 1FFh; unsigned int
0x18001dce4  mov     [rsp+0F8h+Reply], eax
0x18001dce8  mov     [rsp+0F8h+bAlertable], eax
0x18001dcec  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001dcf3  mov     ecx, 2; unsigned __int8
0x18001dcf8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001dcfd  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x18001dd05  test    rcx, rcx
0x18001dd08  jz      short loc_18001DD10
0x18001dd0a  call    cs:__imp_CloseHandle
0x18001dd10  test    r15b, r15b
0x18001dd13  jz      short loc_18001DD4D
0x18001dd15  mov     [rsp+0F8h+Reply], 800705B4h
0x18001dd1d  lea     rdx, [rsp+0F8h+var_BC]
0x18001dd22  call    ??$RPCCallTimedOut@AEAY0BI@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BI@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[24],ulong &>(char const (&)[24],ulong &)
0x18001dd27  mov     eax, [rsp+0F8h+Reply]
0x18001dd2b  mov     [rsp+0F8h+bAlertable], eax
0x18001dd2f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001dd36  mov     r8d, 1FFh; unsigned int
0x18001dd3c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001dd43  mov     ecx, 2; unsigned __int8
0x18001dd48  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001dd4d  test    r14b, r14b
0x18001dd50  jz      short loc_18001DD7D
0x18001dd52  mov     eax, 800704C7h
0x18001dd57  mov     [rsp+0F8h+Reply], eax
0x18001dd5b  mov     [rsp+0F8h+bAlertable], eax
0x18001dd5f  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001dd66  mov     r8d, 1FFh; unsigned int
0x18001dd6c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001dd73  mov     ecx, 2; unsigned __int8
0x18001dd78  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001dd7d  mov     eax, [rsp+0F8h+Reply]
0x18001dd81  cmp     eax, 800706B5h
0x18001dd86  jz      short loc_18001DD8F
0x18001dd88  cmp     eax, 800706BAh
0x18001dd8d  jnz     short loc_18001DD98
0x18001dd8f  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001dd94  mov     eax, [rsp+0F8h+Reply]
0x18001dd98  mov     rcx, [rsp+0F8h+var_38]
0x18001dda0  xor     rcx, rsp; StackCookie
0x18001dda3  call    __security_check_cookie
0x18001dda8  add     rsp, 0D8h
0x18001ddaf  pop     r15
0x18001ddb1  pop     r14
0x18001ddb3  pop     r12
0x18001ddb5  pop     rsi
0x18001ddb6  retn
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
