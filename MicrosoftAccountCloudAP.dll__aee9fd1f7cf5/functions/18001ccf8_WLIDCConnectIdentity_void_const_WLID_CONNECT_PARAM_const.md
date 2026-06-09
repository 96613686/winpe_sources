# WLIDCConnectIdentity(void * const,_WLID_CONNECT_PARAM * const)

- ea: `0x18001ccf8`
- end: `0x18001d021`
- name: `?WLIDCConnectIdentity@@YAJQEAXQEAU_WLID_CONNECT_PARAM@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(void *const, struct _WLID_CONNECT_PARAM *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019620`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001ccf8`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ce93`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cee5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ce93`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cee5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cdbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf62`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001ce0b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001ce0b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cf1b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cf1b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001cd7a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001cd7a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ceba`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ceba`

## string_xrefs

- `0x18001cde0`: `RPC failed to create new event, hr = %#x`
- `0x18001cf2f`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCConnectIdentity(void *const a1, struct _WLID_CONNECT_PARAM *const a2)
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
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
    v9 = 488;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 3u, 0, &pAsync, a1, a2);
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
  v9 = 490;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCConnectIdentity",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x1EAu,
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
      0x1EAu,
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
0x18001ccf8  mov     [rsp+arg_10], rsi
0x18001ccfd  mov     [rsp+arg_18], r12
0x18001cd02  push    r13
0x18001cd04  push    r14
0x18001cd06  push    r15
0x18001cd08  sub     rsp, 0D0h
0x18001cd0f  mov     rax, cs:__security_cookie
0x18001cd16  xor     rax, rsp
0x18001cd19  mov     [rsp+0E8h+var_28], rax
0x18001cd21  mov     r13, rdx
0x18001cd24  mov     r12, rcx
0x18001cd27  mov     [rsp+0E8h+Reply], 0
0x18001cd2f  mov     [rsp+0E8h+dwMilliseconds], 0
0x18001cd37  lea     r8, [rsp+0E8h+dwMilliseconds]; unsigned int *
0x18001cd3c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001cd41  xor     edx, edx; Val
0x18001cd43  lea     r8d, [rdx+70h]; Size
0x18001cd47  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18001cd4c  call    memset_0
0x18001cd51  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18001cd55  mov     [rsp+0E8h+dwMilliseconds], esi
0x18001cd59  mov     [rsp+0E8h+var_AC], esi
0x18001cd5d  xor     r15b, r15b
0x18001cd60  mov     [rsp+0E8h+var_B4], r15b
0x18001cd65  xor     r14b, r14b
0x18001cd68  xorps   xmm0, xmm0
0x18001cd6b  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x18001cd70  mov     edx, 70h ; 'p'; Size
0x18001cd75  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18001cd7a  call    cs:__imp_RpcAsyncInitializeHandle
0x18001cd80  test    eax, eax
0x18001cd82  jz      short loc_18001CDA0
0x18001cd84  jle     short loc_18001CD8E
0x18001cd86  movzx   eax, ax
0x18001cd89  or      eax, 80070000h
0x18001cd8e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001cd95  mov     r8d, 1E8h
0x18001cd9b  jmp     loc_18001CF3C
0x18001cda0  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x18001cda9  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18001cdb1  xor     r9d, r9d; lpName
0x18001cdb4  xor     r8d, r8d; bInitialState
0x18001cdb7  xor     edx, edx; bManualReset
0x18001cdb9  xor     ecx, ecx; lpEventAttributes
0x18001cdbb  call    cs:__imp_CreateEventW
0x18001cdc1  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x18001cdc9  test    rax, rax
0x18001cdcc  jnz     short loc_18001CDE9
0x18001cdce  call    cs:__imp_GetLastError
0x18001cdd4  test    eax, eax
0x18001cdd6  jle     short loc_18001CDE0
0x18001cdd8  movzx   eax, ax
0x18001cddb  or      eax, 80070000h
0x18001cde0  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001cde7  jmp     short loc_18001CD95
0x18001cde9  mov     [rsp+0E8h+Handles], rax
0x18001cdee  mov     [rsp+0E8h+var_C0], r13
0x18001cdf3  mov     qword ptr [rsp+0E8h+bAlertable], r12
0x18001cdf8  lea     r9, [rsp+0E8h+pAsync]
0x18001cdfd  xor     r8d, r8d; pReturnValue
0x18001ce00  lea     edx, [r8+3]; nProcNum
0x18001ce04  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001ce0b  call    cs:__imp_Ndr64AsyncClientCall
0x18001ce11  mov     eax, [rsp+0E8h+Reply]
0x18001ce15  jmp     short loc_18001CE66
0x18001ce17  test    eax, eax
0x18001ce19  jle     short loc_18001CE23
0x18001ce1b  movzx   eax, ax
0x18001ce1e  or      eax, 80070000h
0x18001ce23  mov     [rsp+0E8h+Reply], eax
0x18001ce27  mov     [rsp+0E8h+bAlertable], eax
0x18001ce2b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001ce32  mov     r8d, 1EAh; unsigned int
0x18001ce38  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ce3f  mov     ecx, 2; unsigned __int8
0x18001ce44  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ce49  mov     eax, [rsp+0E8h+Reply]
0x18001ce4d  test    eax, eax
0x18001ce4f  js      short loc_18001CE5A
0x18001ce51  mov     eax, 8000FFFFh
0x18001ce56  mov     [rsp+0E8h+Reply], eax
0x18001ce5a  mov     esi, [rsp+0E8h+dwMilliseconds]
0x18001ce5e  mov     r15b, [rsp+0E8h+var_B4]
0x18001ce63  mov     r14b, r15b
0x18001ce66  test    eax, eax
0x18001ce68  jns     short loc_18001CE7C
0x18001ce6a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001ce71  mov     r8d, 1EAh
0x18001ce77  jmp     loc_18001CF40
0x18001ce7c  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18001ce84  mov     r9d, esi; dwMilliseconds
0x18001ce87  xor     r8d, r8d; bWaitAll
0x18001ce8a  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18001ce8f  lea     ecx, [r8+1]; nCount
0x18001ce93  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ce99  mov     esi, eax
0x18001ce9b  mov     r12d, 102h
0x18001cea1  test    r14b, r14b
0x18001cea4  jnz     short loc_18001CEF2
0x18001cea6  cmp     esi, r12d
0x18001cea9  jz      short loc_18001CEB0
0x18001ceab  cmp     esi, 1
0x18001ceae  jnz     short loc_18001CEF2
0x18001ceb0  mov     edx, 1; fAbort
0x18001ceb5  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18001ceba  call    cs:__imp_RpcAsyncCancelCall
0x18001cec0  cmp     esi, r12d
0x18001cec3  jnz     short loc_18001CECA
0x18001cec5  mov     r15b, 1
0x18001cec8  jmp     short loc_18001CECD
0x18001ceca  mov     r14b, 1
0x18001cecd  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x18001ced5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001ced9  xor     r8d, r8d; bWaitAll
0x18001cedc  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x18001cee1  lea     ecx, [r8+1]; nCount
0x18001cee5  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ceeb  mov     esi, eax
0x18001ceed  test    r15b, r15b
0x18001cef0  jz      short loc_18001CEA1
0x18001cef2  test    esi, esi
0x18001cef4  jz      short loc_18001CF11
0x18001cef6  call    cs:__imp_GetLastError
0x18001cefc  test    eax, eax
0x18001cefe  jle     short loc_18001CF08
0x18001cf00  movzx   eax, ax
0x18001cf03  or      eax, 80070000h
0x18001cf08  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001cf0f  jmp     short loc_18001CF36
0x18001cf11  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18001cf16  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18001cf1b  call    cs:__imp_RpcAsyncCompleteCall
0x18001cf21  test    eax, eax
0x18001cf23  jz      short loc_18001CF55
0x18001cf25  jle     short loc_18001CF2F
0x18001cf27  movzx   eax, ax
0x18001cf2a  or      eax, 80070000h
0x18001cf2f  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001cf36  mov     r8d, 1EAh; unsigned int
0x18001cf3c  mov     [rsp+0E8h+Reply], eax
0x18001cf40  mov     [rsp+0E8h+bAlertable], eax
0x18001cf44  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cf4b  mov     ecx, 2; unsigned __int8
0x18001cf50  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cf55  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x18001cf5d  test    rcx, rcx
0x18001cf60  jz      short loc_18001CF68
0x18001cf62  call    cs:__imp_CloseHandle
0x18001cf68  test    r15b, r15b
0x18001cf6b  jz      short loc_18001CFAC
0x18001cf6d  mov     [rsp+0E8h+Reply], 800705B4h
0x18001cf75  lea     rdx, [rsp+0E8h+var_AC]
0x18001cf7a  lea     rcx, aWlidcconnectid; "WLIDCConnectIdentity"
0x18001cf81  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001cf86  mov     eax, [rsp+0E8h+Reply]
0x18001cf8a  mov     [rsp+0E8h+bAlertable], eax
0x18001cf8e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001cf95  mov     r8d, 1EAh; unsigned int
0x18001cf9b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cfa2  mov     ecx, 2; unsigned __int8
0x18001cfa7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cfac  test    r14b, r14b
0x18001cfaf  jz      short loc_18001CFDC
0x18001cfb1  mov     eax, 800704C7h
0x18001cfb6  mov     [rsp+0E8h+Reply], eax
0x18001cfba  mov     [rsp+0E8h+bAlertable], eax
0x18001cfbe  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001cfc5  mov     r8d, 1EAh; unsigned int
0x18001cfcb  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cfd2  mov     ecx, 2; unsigned __int8
0x18001cfd7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cfdc  mov     eax, [rsp+0E8h+Reply]
0x18001cfe0  cmp     eax, 800706B5h
0x18001cfe5  jz      short loc_18001CFEE
0x18001cfe7  cmp     eax, 800706BAh
0x18001cfec  jnz     short loc_18001CFF7
0x18001cfee  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001cff3  mov     eax, [rsp+0E8h+Reply]
0x18001cff7  mov     rcx, [rsp+0E8h+var_28]
0x18001cfff  xor     rcx, rsp; StackCookie
0x18001d002  call    __security_check_cookie
0x18001d007  lea     r11, [rsp+0E8h+var_18]
0x18001d00f  mov     rsi, [r11+30h]
0x18001d013  mov     r12, [r11+38h]
0x18001d017  mov     rsp, r11
0x18001d01a  pop     r15
0x18001d01c  pop     r14
0x18001d01e  pop     r13
0x18001d020  retn
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
