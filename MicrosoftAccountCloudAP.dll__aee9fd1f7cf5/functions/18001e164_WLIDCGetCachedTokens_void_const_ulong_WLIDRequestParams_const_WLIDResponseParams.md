# WLIDCGetCachedTokens(void * const,ulong,_WLIDRequestParams * const,_WLIDResponseParams * *)

- ea: `0x18001e164`
- end: `0x18001e4c3`
- name: `?WLIDCGetCachedTokens@@YAJQEAXKQEAU_WLIDRequestParams@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(void *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDResponseParams **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019700`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001e164`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e338`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e38d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e338`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e38d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e23f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e23f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e39e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e39e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e40d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e40d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e2b0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e2b0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e3c6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e3c6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e1f8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e1f8`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001e362`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001e362`

## string_xrefs

- `0x18001e264`: `RPC failed to create new event, hr = %#x`
- `0x18001e3da`: `RPC Async complete call failed, hr = %#x`
- `0x18001e425`: `WLIDCGetCachedTokens`

## pseudocode

```c
__int64 __fastcall WLIDCGetCachedTokens(
        void *const a1,
        unsigned int a2,
        struct _WLIDRequestParams *const a3,
        struct _WLIDResponseParams **a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  unsigned int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v17; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  int v19; // [rsp+5Ch] [rbp-DCh] BYREF
  DWORD v20; // [rsp+60h] [rbp-D8h] BYREF
  struct _WLIDResponseParams **v21; // [rsp+68h] [rbp-D0h]
  struct _WLIDRequestParams *v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  v19 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 725;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x12u, 0, &pAsync, a1, a2, v22, &v19, v21);
  v13 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
  do
  {
    if ( v8 || v13 != 258 && v13 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v13 == 258 )
      v7 = 1;
    else
      v8 = 1;
    v13 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v7 );
  if ( v13 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 727;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetCachedTokens",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2D7u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v8 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2D7u,
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
0x18001e164  push    rsi
0x18001e166  push    r12
0x18001e168  push    r13
0x18001e16a  push    r14
0x18001e16c  push    r15
0x18001e16e  sub     rsp, 110h
0x18001e175  mov     rax, cs:__security_cookie
0x18001e17c  xor     rax, rsp
0x18001e17f  mov     [rsp+138h+var_38], rax
0x18001e187  mov     [rsp+138h+var_D0], r9
0x18001e18c  mov     [rsp+138h+var_C8], r8
0x18001e191  mov     r13d, edx
0x18001e194  mov     r12, rcx
0x18001e197  mov     [rsp+138h+var_DC], 0
0x18001e19f  mov     [rsp+138h+Reply], 0
0x18001e1a7  mov     [rsp+138h+dwMilliseconds], 0
0x18001e1af  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18001e1b4  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001e1b9  xor     edx, edx; Val
0x18001e1bb  lea     r8d, [rdx+70h]; Size
0x18001e1bf  lea     rcx, [rsp+138h+pAsync]; void *
0x18001e1c7  call    memset_0
0x18001e1cc  mov     esi, [rsp+138h+dwMilliseconds]
0x18001e1d0  mov     [rsp+138h+dwMilliseconds], esi
0x18001e1d4  mov     [rsp+138h+var_D8], esi
0x18001e1d8  xor     r15b, r15b
0x18001e1db  mov     [rsp+138h+var_E4], r15b
0x18001e1e0  xor     r14b, r14b
0x18001e1e3  xorps   xmm0, xmm0
0x18001e1e6  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18001e1eb  mov     edx, 70h ; 'p'; Size
0x18001e1f0  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001e1f8  call    cs:__imp_RpcAsyncInitializeHandle
0x18001e1fe  test    eax, eax
0x18001e200  jz      short loc_18001E21E
0x18001e202  jle     short loc_18001E20C
0x18001e204  movzx   eax, ax
0x18001e207  or      eax, 80070000h
0x18001e20c  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001e213  mov     r8d, 2D5h
0x18001e219  jmp     loc_18001E3E7
0x18001e21e  mov     [rsp+138h+pAsync.UserInfo], 0
0x18001e22a  mov     [rsp+138h+pAsync.NotificationType], 1
0x18001e235  xor     r9d, r9d; lpName
0x18001e238  xor     r8d, r8d; bInitialState
0x18001e23b  xor     edx, edx; bManualReset
0x18001e23d  xor     ecx, ecx; lpEventAttributes
0x18001e23f  call    cs:__imp_CreateEventW
0x18001e245  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18001e24d  test    rax, rax
0x18001e250  jnz     short loc_18001E26D
0x18001e252  call    cs:__imp_GetLastError
0x18001e258  test    eax, eax
0x18001e25a  jle     short loc_18001E264
0x18001e25c  movzx   eax, ax
0x18001e25f  or      eax, 80070000h
0x18001e264  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001e26b  jmp     short loc_18001E213
0x18001e26d  mov     [rsp+138h+Handles], rax
0x18001e272  mov     rax, [rsp+138h+var_D0]
0x18001e277  mov     [rsp+138h+var_F8], rax
0x18001e27c  lea     rax, [rsp+138h+var_DC]
0x18001e281  mov     [rsp+138h+var_100], rax
0x18001e286  mov     rax, [rsp+138h+var_C8]
0x18001e28b  mov     [rsp+138h+var_108], rax
0x18001e290  mov     [rsp+138h+var_110], r13d
0x18001e295  mov     qword ptr [rsp+138h+bAlertable], r12
0x18001e29a  lea     r9, [rsp+138h+pAsync]
0x18001e2a2  xor     r8d, r8d; pReturnValue
0x18001e2a5  lea     edx, [r8+12h]; nProcNum
0x18001e2a9  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001e2b0  call    cs:__imp_Ndr64AsyncClientCall
0x18001e2b6  mov     eax, [rsp+138h+Reply]
0x18001e2ba  jmp     short loc_18001E30B
0x18001e2bc  test    eax, eax
0x18001e2be  jle     short loc_18001E2C8
0x18001e2c0  movzx   eax, ax
0x18001e2c3  or      eax, 80070000h
0x18001e2c8  mov     [rsp+138h+Reply], eax
0x18001e2cc  mov     [rsp+138h+bAlertable], eax
0x18001e2d0  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001e2d7  mov     r8d, 2D7h; unsigned int
0x18001e2dd  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e2e4  mov     ecx, 2; unsigned __int8
0x18001e2e9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e2ee  mov     eax, [rsp+138h+Reply]
0x18001e2f2  test    eax, eax
0x18001e2f4  js      short loc_18001E2FF
0x18001e2f6  mov     eax, 8000FFFFh
0x18001e2fb  mov     [rsp+138h+Reply], eax
0x18001e2ff  mov     esi, [rsp+138h+dwMilliseconds]
0x18001e303  mov     r15b, [rsp+138h+var_E4]
0x18001e308  mov     r14b, r15b
0x18001e30b  test    eax, eax
0x18001e30d  jns     short loc_18001E321
0x18001e30f  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001e316  mov     r8d, 2D7h
0x18001e31c  jmp     loc_18001E3EB
0x18001e321  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001e329  mov     r9d, esi; dwMilliseconds
0x18001e32c  xor     r8d, r8d; bWaitAll
0x18001e32f  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001e334  lea     ecx, [r8+1]; nCount
0x18001e338  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e33e  mov     esi, eax
0x18001e340  mov     r12d, 102h
0x18001e346  test    r14b, r14b
0x18001e349  jnz     short loc_18001E39A
0x18001e34b  cmp     esi, r12d
0x18001e34e  jz      short loc_18001E355
0x18001e350  cmp     esi, 1
0x18001e353  jnz     short loc_18001E39A
0x18001e355  mov     edx, 1; fAbort
0x18001e35a  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001e362  call    cs:__imp_RpcAsyncCancelCall
0x18001e368  cmp     esi, r12d
0x18001e36b  jnz     short loc_18001E372
0x18001e36d  mov     r15b, 1
0x18001e370  jmp     short loc_18001E375
0x18001e372  mov     r14b, 1
0x18001e375  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001e37d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001e381  xor     r8d, r8d; bWaitAll
0x18001e384  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001e389  lea     ecx, [r8+1]; nCount
0x18001e38d  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e393  mov     esi, eax
0x18001e395  test    r15b, r15b
0x18001e398  jz      short loc_18001E346
0x18001e39a  test    esi, esi
0x18001e39c  jz      short loc_18001E3B9
0x18001e39e  call    cs:__imp_GetLastError
0x18001e3a4  test    eax, eax
0x18001e3a6  jle     short loc_18001E3B0
0x18001e3a8  movzx   eax, ax
0x18001e3ab  or      eax, 80070000h
0x18001e3b0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001e3b7  jmp     short loc_18001E3E1
0x18001e3b9  lea     rdx, [rsp+138h+Reply]; Reply
0x18001e3be  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001e3c6  call    cs:__imp_RpcAsyncCompleteCall
0x18001e3cc  test    eax, eax
0x18001e3ce  jz      short loc_18001E400
0x18001e3d0  jle     short loc_18001E3DA
0x18001e3d2  movzx   eax, ax
0x18001e3d5  or      eax, 80070000h
0x18001e3da  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001e3e1  mov     r8d, 2D7h; unsigned int
0x18001e3e7  mov     [rsp+138h+Reply], eax
0x18001e3eb  mov     [rsp+138h+bAlertable], eax
0x18001e3ef  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e3f6  mov     ecx, 2; unsigned __int8
0x18001e3fb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e400  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18001e408  test    rcx, rcx
0x18001e40b  jz      short loc_18001E413
0x18001e40d  call    cs:__imp_CloseHandle
0x18001e413  test    r15b, r15b
0x18001e416  jz      short loc_18001E457
0x18001e418  mov     [rsp+138h+Reply], 800705B4h
0x18001e420  lea     rdx, [rsp+138h+var_D8]
0x18001e425  lea     rcx, aWlidcgetcached; "WLIDCGetCachedTokens"
0x18001e42c  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001e431  mov     eax, [rsp+138h+Reply]
0x18001e435  mov     [rsp+138h+bAlertable], eax
0x18001e439  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001e440  mov     r8d, 2D7h; unsigned int
0x18001e446  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e44d  mov     ecx, 2; unsigned __int8
0x18001e452  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e457  test    r14b, r14b
0x18001e45a  jz      short loc_18001E487
0x18001e45c  mov     eax, 800704C7h
0x18001e461  mov     [rsp+138h+Reply], eax
0x18001e465  mov     [rsp+138h+bAlertable], eax
0x18001e469  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001e470  mov     r8d, 2D7h; unsigned int
0x18001e476  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e47d  mov     ecx, 2; unsigned __int8
0x18001e482  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e487  mov     eax, [rsp+138h+Reply]
0x18001e48b  cmp     eax, 800706B5h
0x18001e490  jz      short loc_18001E499
0x18001e492  cmp     eax, 800706BAh
0x18001e497  jnz     short loc_18001E4A2
0x18001e499  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001e49e  mov     eax, [rsp+138h+Reply]
0x18001e4a2  mov     rcx, [rsp+138h+var_38]
0x18001e4aa  xor     rcx, rsp; StackCookie
0x18001e4ad  call    __security_check_cookie
0x18001e4b2  add     rsp, 110h
0x18001e4b9  pop     r15
0x18001e4bb  pop     r14
0x18001e4bd  pop     r13
0x18001e4bf  pop     r12
0x18001e4c1  pop     rsi
0x18001e4c2  retn
0x180030fdd  push    rbp
0x180030fdf  sub     rsp, 50h
0x180030fe3  mov     rbp, rdx
0x180030fe6  mov     rcx, [rcx]
0x180030fe9  mov     ecx, [rcx]; unsigned int
0x180030feb  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180030ff0  nop
0x180030ff1  add     rsp, 50h
0x180030ff5  pop     rbp
0x180030ff6  retn
```
