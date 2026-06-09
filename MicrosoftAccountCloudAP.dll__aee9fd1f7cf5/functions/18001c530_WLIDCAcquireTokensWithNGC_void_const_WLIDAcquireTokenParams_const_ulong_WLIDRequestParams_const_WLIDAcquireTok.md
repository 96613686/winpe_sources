# WLIDCAcquireTokensWithNGC(void * const,_WLIDAcquireTokenParams * const,ulong,_WLIDRequestParams * const,_WLIDAcquireTokenResults *,_WLIDResponseParams * *,void *,int)

- ea: `0x18001c530`
- end: `0x18001c9a4`
- name: `?WLIDCAcquireTokensWithNGC@@YAJQEAXQEAU_WLIDAcquireTokenParams@@KQEAU_WLIDRequestParams@@PEAU_WLIDAcquireTokenResults@@PEAPEAU_WLIDResponseParams@@PEAXH@Z`
- size: `1140`
- prototype: `__int64 __fastcall(void *const, struct _WLIDAcquireTokenParams *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDAcquireTokenResults *, struct _WLIDResponseParams **, void *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800195b0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019fd8`
- `0x18001ba00`
- `0x18001c530`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c7fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c856`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c7fe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c856`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c661`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8dc`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001c75b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001c75b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001c892`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001c892`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001c61a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001c61a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001c828`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001c828`

## string_xrefs

- `0x18001c686`: `RPC failed to create new event, hr = %#x`
- `0x18001c8a6`: `RPC Async complete call failed, hr = %#x`
- `0x18001c8fa`: `WLIDCAcquireTokensWithNGC`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokensWithNGC(
        void *const a1,
        struct _WLIDAcquireTokenParams *const a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        struct _WLIDAcquireTokenResults *a5,
        struct _WLIDResponseParams **a6,
        void *a7,
        int a8)
{
  DWORD v8; // r12d
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-168h]
  unsigned int Reply; // [rsp+90h] [rbp-F8h] BYREF
  char v19; // [rsp+94h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-F0h] BYREF
  int v21; // [rsp+9Ch] [rbp-ECh]
  int v22; // [rsp+A0h] [rbp-E8h]
  DWORD v23; // [rsp+A4h] [rbp-E4h] BYREF
  HANDLE Handles[2]; // [rsp+A8h] [rbp-E0h] BYREF
  struct _WLIDResponseParams **v25; // [rsp+B8h] [rbp-D0h]
  struct _WLIDAcquireTokenParams *v26; // [rsp+C0h] [rbp-C8h]
  struct _WLIDRequestParams *v27; // [rsp+C8h] [rbp-C0h]
  void *v28; // [rsp+D0h] [rbp-B8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+E0h] [rbp-A8h] BYREF

  v27 = a4;
  v21 = a3;
  v26 = a2;
  v28 = a1;
  v25 = a6;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  if ( a8 )
    dwMilliseconds *= 3;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v23 = dwMilliseconds;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_7:
    v13 = 1499;
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
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_7;
  }
  Handles[0] = EventW;
  if ( a7 )
    Handles[1] = a7;
  v22 = (a7 != 0) + 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0x49u,
    0,
    &pAsync,
    v28,
    *(_QWORD *)v26,
    v21,
    v27,
    *((_QWORD *)v26 + 1),
    *((_QWORD *)v26 + 2),
    *((_QWORD *)v26 + 3),
    a5,
    (char *)a5 + 4,
    (char *)a5 + 8,
    (char *)a5 + 16,
    v25,
    (char *)a5 + 12);
  v15 = WaitForMultipleObjectsEx((a7 != 0) + 1, Handles, 0, v8, 0);
  do
  {
    if ( v10 || v15 != 258 && v15 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 == 258 )
      v9 = 1;
    else
      v10 = 1;
    v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v9 );
  if ( v15 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_32;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
  }
  v13 = 1514;
LABEL_31:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v13,
    v12,
    *(_QWORD *)bAlertable);
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
      (__int64)"WLIDCAcquireTokensWithNGC",
      (int *)&v23);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5EAu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v10 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5EAu,
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
0x18001c530  push    rsi
0x18001c532  push    r12
0x18001c534  push    r13
0x18001c536  push    r14
0x18001c538  push    r15
0x18001c53a  sub     rsp, 160h
0x18001c541  mov     rax, cs:__security_cookie
0x18001c548  xor     rax, rsp
0x18001c54b  mov     [rsp+188h+var_38], rax
0x18001c553  mov     [rsp+188h+var_C0], r9
0x18001c55b  mov     [rsp+188h+var_EC], r8d
0x18001c563  mov     [rsp+188h+var_C8], rdx
0x18001c56b  mov     [rsp+188h+var_B8], rcx
0x18001c573  mov     r13, [rsp+188h+arg_20]
0x18001c57b  mov     rax, [rsp+188h+arg_28]
0x18001c583  mov     [rsp+188h+var_D0], rax
0x18001c58b  mov     [rsp+188h+Reply], 0
0x18001c596  mov     [rsp+188h+dwMilliseconds], 0
0x18001c5a1  lea     r8, [rsp+188h+dwMilliseconds]; unsigned int *
0x18001c5a9  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001c5ae  cmp     [rsp+188h+arg_38], 0
0x18001c5b6  jz      short loc_18001C5C9
0x18001c5b8  mov     eax, [rsp+188h+dwMilliseconds]
0x18001c5bf  lea     eax, [rax+rax*2]
0x18001c5c2  mov     [rsp+188h+dwMilliseconds], eax
0x18001c5c9  xor     edx, edx; Val
0x18001c5cb  lea     r8d, [rdx+70h]; Size
0x18001c5cf  lea     rcx, [rsp+188h+pAsync]; void *
0x18001c5d7  call    memset_0
0x18001c5dc  mov     r12d, [rsp+188h+dwMilliseconds]
0x18001c5e4  mov     [rsp+188h+dwMilliseconds], r12d
0x18001c5ec  mov     [rsp+188h+var_E4], r12d
0x18001c5f4  xor     r15b, r15b
0x18001c5f7  mov     [rsp+188h+var_F4], r15b
0x18001c5ff  xor     r14b, r14b
0x18001c602  xorps   xmm0, xmm0
0x18001c605  movups  xmmword ptr [rsp+188h+Handles], xmm0
0x18001c60d  mov     edx, 70h ; 'p'; Size
0x18001c612  lea     rcx, [rsp+188h+pAsync]; pAsync
0x18001c61a  call    cs:__imp_RpcAsyncInitializeHandle
0x18001c620  test    eax, eax
0x18001c622  jz      short loc_18001C640
0x18001c624  jle     short loc_18001C62E
0x18001c626  movzx   eax, ax
0x18001c629  or      eax, 80070000h
0x18001c62e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001c635  mov     r8d, 5DBh
0x18001c63b  jmp     loc_18001C8B3
0x18001c640  mov     [rsp+188h+pAsync.UserInfo], 0
0x18001c64c  mov     [rsp+188h+pAsync.NotificationType], 1
0x18001c657  xor     r9d, r9d; lpName
0x18001c65a  xor     r8d, r8d; bInitialState
0x18001c65d  xor     edx, edx; bManualReset
0x18001c65f  xor     ecx, ecx; lpEventAttributes
0x18001c661  call    cs:__imp_CreateEventW
0x18001c667  mov     qword ptr [rsp+188h+pAsync.u], rax
0x18001c66f  test    rax, rax
0x18001c672  jnz     short loc_18001C68F
0x18001c674  call    cs:__imp_GetLastError
0x18001c67a  test    eax, eax
0x18001c67c  jle     short loc_18001C686
0x18001c67e  movzx   eax, ax
0x18001c681  or      eax, 80070000h
0x18001c686  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001c68d  jmp     short loc_18001C635
0x18001c68f  mov     [rsp+188h+Handles], rax
0x18001c697  mov     rax, [rsp+188h+arg_30]
0x18001c69f  test    rax, rax
0x18001c6a2  jz      short loc_18001C6AC
0x18001c6a4  mov     [rsp+188h+Handles+8], rax
0x18001c6ac  neg     rax
0x18001c6af  sbb     esi, esi
0x18001c6b1  neg     esi
0x18001c6b3  inc     esi
0x18001c6b5  mov     [rsp+188h+var_E8], esi
0x18001c6bc  lea     rax, [r13+0Ch]
0x18001c6c0  lea     rcx, [r13+10h]
0x18001c6c4  lea     rdx, [r13+8]
0x18001c6c8  lea     r8, [r13+4]
0x18001c6cc  mov     [rsp+188h+var_108], rax
0x18001c6d4  mov     rax, [rsp+188h+var_D0]
0x18001c6dc  mov     [rsp+188h+var_110], rax
0x18001c6e1  mov     [rsp+188h+var_118], rcx
0x18001c6e6  mov     [rsp+188h+var_120], rdx
0x18001c6eb  mov     [rsp+188h+var_128], r8
0x18001c6f0  mov     [rsp+188h+var_130], r13
0x18001c6f5  mov     rcx, [rsp+188h+var_C8]
0x18001c6fd  mov     rax, [rcx+18h]
0x18001c701  mov     [rsp+188h+var_138], rax
0x18001c706  mov     rax, [rcx+10h]
0x18001c70a  mov     [rsp+188h+var_140], rax
0x18001c70f  mov     rax, [rcx+8]
0x18001c713  mov     [rsp+188h+var_148], rax
0x18001c718  mov     rax, [rsp+188h+var_C0]
0x18001c720  mov     [rsp+188h+var_150], rax
0x18001c725  mov     eax, [rsp+188h+var_EC]
0x18001c72c  mov     [rsp+188h+var_158], eax
0x18001c730  mov     rax, [rcx]
0x18001c733  mov     [rsp+188h+var_160], rax
0x18001c738  mov     rax, [rsp+188h+var_B8]
0x18001c740  mov     qword ptr [rsp+188h+bAlertable], rax
0x18001c745  lea     r9, [rsp+188h+pAsync]
0x18001c74d  xor     r8d, r8d; pReturnValue
0x18001c750  lea     edx, [r8+49h]; nProcNum
0x18001c754  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001c75b  call    cs:__imp_Ndr64AsyncClientCall
0x18001c761  mov     eax, [rsp+188h+Reply]
0x18001c768  jmp     short loc_18001C7D0
0x18001c76a  test    eax, eax
0x18001c76c  jle     short loc_18001C776
0x18001c76e  movzx   eax, ax
0x18001c771  or      eax, 80070000h
0x18001c776  mov     [rsp+188h+Reply], eax
0x18001c77d  mov     [rsp+188h+bAlertable], eax
0x18001c781  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001c788  mov     r8d, 5EAh; unsigned int
0x18001c78e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c795  mov     ecx, 2; unsigned __int8
0x18001c79a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c79f  mov     eax, [rsp+188h+Reply]
0x18001c7a6  test    eax, eax
0x18001c7a8  js      short loc_18001C7B6
0x18001c7aa  mov     eax, 8000FFFFh
0x18001c7af  mov     [rsp+188h+Reply], eax
0x18001c7b6  mov     r12d, [rsp+188h+dwMilliseconds]
0x18001c7be  mov     r15b, [rsp+188h+var_F4]
0x18001c7c6  mov     r14b, r15b
0x18001c7c9  mov     esi, [rsp+188h+var_E8]
0x18001c7d0  test    eax, eax
0x18001c7d2  jns     short loc_18001C7E6
0x18001c7d4  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001c7db  mov     r8d, 5EAh
0x18001c7e1  jmp     loc_18001C8BA
0x18001c7e6  mov     [rsp+188h+bAlertable], 0; bAlertable
0x18001c7ee  mov     r9d, r12d; dwMilliseconds
0x18001c7f1  xor     r8d, r8d; bWaitAll
0x18001c7f4  lea     rdx, [rsp+188h+Handles]; lpHandles
0x18001c7fc  mov     ecx, esi; nCount
0x18001c7fe  call    cs:__imp_WaitForMultipleObjectsEx
0x18001c804  mov     esi, eax
0x18001c806  mov     r12d, 102h
0x18001c80c  test    r14b, r14b
0x18001c80f  jnz     short loc_18001C863
0x18001c811  cmp     esi, r12d
0x18001c814  jz      short loc_18001C81B
0x18001c816  cmp     esi, 1
0x18001c819  jnz     short loc_18001C863
0x18001c81b  mov     edx, 1; fAbort
0x18001c820  lea     rcx, [rsp+188h+pAsync]; pAsync
0x18001c828  call    cs:__imp_RpcAsyncCancelCall
0x18001c82e  cmp     esi, r12d
0x18001c831  jnz     short loc_18001C838
0x18001c833  mov     r15b, 1
0x18001c836  jmp     short loc_18001C83B
0x18001c838  mov     r14b, 1
0x18001c83b  mov     [rsp+188h+bAlertable], 0; bAlertable
0x18001c843  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001c847  xor     r8d, r8d; bWaitAll
0x18001c84a  lea     rdx, [rsp+188h+Handles]; lpHandles
0x18001c852  lea     ecx, [r8+1]; nCount
0x18001c856  call    cs:__imp_WaitForMultipleObjectsEx
0x18001c85c  mov     esi, eax
0x18001c85e  test    r15b, r15b
0x18001c861  jz      short loc_18001C80C
0x18001c863  test    esi, esi
0x18001c865  jz      short loc_18001C882
0x18001c867  call    cs:__imp_GetLastError
0x18001c86d  test    eax, eax
0x18001c86f  jle     short loc_18001C879
0x18001c871  movzx   eax, ax
0x18001c874  or      eax, 80070000h
0x18001c879  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001c880  jmp     short loc_18001C8AD
0x18001c882  lea     rdx, [rsp+188h+Reply]; Reply
0x18001c88a  lea     rcx, [rsp+188h+pAsync]; pAsync
0x18001c892  call    cs:__imp_RpcAsyncCompleteCall
0x18001c898  test    eax, eax
0x18001c89a  jz      short loc_18001C8CF
0x18001c89c  jle     short loc_18001C8A6
0x18001c89e  movzx   eax, ax
0x18001c8a1  or      eax, 80070000h
0x18001c8a6  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001c8ad  mov     r8d, 5EAh; unsigned int
0x18001c8b3  mov     [rsp+188h+Reply], eax
0x18001c8ba  mov     [rsp+188h+bAlertable], eax
0x18001c8be  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c8c5  mov     ecx, 2; unsigned __int8
0x18001c8ca  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c8cf  mov     rcx, qword ptr [rsp+188h+pAsync.u]; hObject
0x18001c8d7  test    rcx, rcx
0x18001c8da  jz      short loc_18001C8E2
0x18001c8dc  call    cs:__imp_CloseHandle
0x18001c8e2  test    r15b, r15b
0x18001c8e5  jz      short loc_18001C92F
0x18001c8e7  mov     [rsp+188h+Reply], 800705B4h
0x18001c8f2  lea     rdx, [rsp+188h+var_E4]
0x18001c8fa  lea     rcx, aWlidcacquireto; "WLIDCAcquireTokensWithNGC"
0x18001c901  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x18001c906  mov     eax, [rsp+188h+Reply]
0x18001c90d  mov     [rsp+188h+bAlertable], eax
0x18001c911  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001c918  mov     r8d, 5EAh; unsigned int
0x18001c91e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c925  mov     ecx, 2; unsigned __int8
0x18001c92a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c92f  test    r14b, r14b
0x18001c932  jz      short loc_18001C962
0x18001c934  mov     eax, 800704C7h
0x18001c939  mov     [rsp+188h+Reply], eax
0x18001c940  mov     [rsp+188h+bAlertable], eax
0x18001c944  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001c94b  mov     r8d, 5EAh; unsigned int
0x18001c951  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c958  mov     ecx, 2; unsigned __int8
0x18001c95d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c962  mov     eax, [rsp+188h+Reply]
0x18001c969  cmp     eax, 800706B5h
0x18001c96e  jz      short loc_18001C977
0x18001c970  cmp     eax, 800706BAh
0x18001c975  jnz     short loc_18001C983
0x18001c977  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001c97c  mov     eax, [rsp+188h+Reply]
0x18001c983  mov     rcx, [rsp+188h+var_38]
0x18001c98b  xor     rcx, rsp; StackCookie
0x18001c98e  call    __security_check_cookie
0x18001c993  add     rsp, 160h
0x18001c99a  pop     r15
0x18001c99c  pop     r14
0x18001c99e  pop     r13
0x18001c9a0  pop     r12
0x18001c9a2  pop     rsi
0x18001c9a3  retn
0x180030fb6  push    rbp
0x180030fb8  sub     rsp, 90h
0x180030fbf  mov     rbp, rdx
0x180030fc2  mov     rcx, [rcx]
0x180030fc5  mov     ecx, [rcx]; unsigned int
0x180030fc7  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180030fcc  nop
0x180030fcd  add     rsp, 90h
0x180030fd4  pop     rbp
0x180030fd5  retn
```
