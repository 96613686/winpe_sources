# WLIDCAcquireTokensEx(void * const,_WLIDAcquireTokenParams * const,ulong,_WLIDRequestParams * const,_WLIDAcquireTokenResults *,_WLIDResponseParams * *)

- ea: `0x18001c0f8`
- end: `0x18001c529`
- name: `?WLIDCAcquireTokensEx@@YAJQEAXQEAU_WLIDAcquireTokenParams@@KQEAU_WLIDRequestParams@@PEAU_WLIDAcquireTokenResults@@PEAPEAU_WLIDResponseParams@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(void *const, struct _WLIDAcquireTokenParams *const, unsigned int, struct _WLIDRequestParams *const, struct _WLIDAcquireTokenResults *, struct _WLIDResponseParams **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019570`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001bb84`
- `0x18001c0f8`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c375`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c3cd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c375`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c3cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c209`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c453`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c453`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001c2d7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001c2d7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001c409`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001c409`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001c1c2`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001c1c2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001c39f`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001c39f`

## string_xrefs

- `0x18001c22e`: `RPC failed to create new event, hr = %#x`
- `0x18001c41d`: `RPC Async complete call failed, hr = %#x`
- `0x18001c471`: `WLIDCAcquireTokensEx`
- `0x18001c4fc`: `WLIDCAcquireTokensEx`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokensEx(
        void *const a1,
        struct _WLIDAcquireTokenParams *const a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        struct _WLIDAcquireTokenResults *a5,
        struct _WLIDResponseParams **a6)
{
  DWORD v7; // r12d
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  int v15; // ecx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-158h]
  int Reply; // [rsp+90h] [rbp-E8h] BYREF
  char v19; // [rsp+94h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-E0h] BYREF
  int v21; // [rsp+9Ch] [rbp-DCh]
  DWORD v22; // [rsp+A0h] [rbp-D8h] BYREF
  struct _WLIDResponseParams **v23; // [rsp+A8h] [rbp-D0h]
  struct _WLIDRequestParams *v24; // [rsp+B0h] [rbp-C8h]
  void *v25; // [rsp+B8h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+C0h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+D0h] [rbp-A8h] BYREF

  v24 = a4;
  v21 = a3;
  v25 = a1;
  v23 = a6;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v22 = dwMilliseconds;
  v8 = 0;
  v19 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v12 = 699;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xFu,
    0,
    &pAsync,
    v25,
    *(_QWORD *)a2,
    v21,
    v24,
    *((_QWORD *)a2 + 1),
    *((_QWORD *)a2 + 2),
    *((_QWORD *)a2 + 3),
    a5,
    (char *)a5 + 4,
    (char *)a5 + 8,
    (char *)a5 + 16,
    v23,
    (char *)a5 + 12);
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v7, 0);
  do
  {
    if ( v9 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v8 = 1;
    else
      v9 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v8 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
  }
  v12 = 714;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v12,
    v11,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCAcquireTokensEx",
      (int *)&v22);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2CAu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v9 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2CAu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v15 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v15 = Reply;
  }
  return TranslateRpcServiceError(v15, "WLIDCAcquireTokensEx");
}

```

## disassembly

```asm
0x18001c0f8  push    rsi
0x18001c0fa  push    r12
0x18001c0fc  push    r13
0x18001c0fe  push    r14
0x18001c100  push    r15
0x18001c102  sub     rsp, 150h
0x18001c109  mov     rax, cs:__security_cookie
0x18001c110  xor     rax, rsp
0x18001c113  mov     [rsp+178h+var_38], rax
0x18001c11b  mov     [rsp+178h+var_C8], r9
0x18001c123  mov     [rsp+178h+var_DC], r8d
0x18001c12b  mov     r13, rdx
0x18001c12e  mov     [rsp+178h+var_C0], rcx
0x18001c136  mov     rsi, [rsp+178h+arg_20]
0x18001c13e  mov     rax, [rsp+178h+arg_28]
0x18001c146  mov     [rsp+178h+var_D0], rax
0x18001c14e  mov     [rsp+178h+Reply], 0
0x18001c159  mov     [rsp+178h+dwMilliseconds], 0
0x18001c164  lea     r8, [rsp+178h+dwMilliseconds]; unsigned int *
0x18001c16c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001c171  xor     edx, edx; Val
0x18001c173  lea     r8d, [rdx+70h]; Size
0x18001c177  lea     rcx, [rsp+178h+pAsync]; void *
0x18001c17f  call    memset_0
0x18001c184  mov     r12d, [rsp+178h+dwMilliseconds]
0x18001c18c  mov     [rsp+178h+dwMilliseconds], r12d
0x18001c194  mov     [rsp+178h+var_D8], r12d
0x18001c19c  xor     r15b, r15b
0x18001c19f  mov     [rsp+178h+var_E4], r15b
0x18001c1a7  xor     r14b, r14b
0x18001c1aa  xorps   xmm0, xmm0
0x18001c1ad  movups  xmmword ptr [rsp+178h+Handles], xmm0
0x18001c1b5  mov     edx, 70h ; 'p'; Size
0x18001c1ba  lea     rcx, [rsp+178h+pAsync]; pAsync
0x18001c1c2  call    cs:__imp_RpcAsyncInitializeHandle
0x18001c1c8  test    eax, eax
0x18001c1ca  jz      short loc_18001C1E8
0x18001c1cc  jle     short loc_18001C1D6
0x18001c1ce  movzx   eax, ax
0x18001c1d1  or      eax, 80070000h
0x18001c1d6  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001c1dd  mov     r8d, 2BBh
0x18001c1e3  jmp     loc_18001C42A
0x18001c1e8  mov     [rsp+178h+pAsync.UserInfo], 0
0x18001c1f4  mov     [rsp+178h+pAsync.NotificationType], 1
0x18001c1ff  xor     r9d, r9d; lpName
0x18001c202  xor     r8d, r8d; bInitialState
0x18001c205  xor     edx, edx; bManualReset
0x18001c207  xor     ecx, ecx; lpEventAttributes
0x18001c209  call    cs:__imp_CreateEventW
0x18001c20f  mov     qword ptr [rsp+178h+pAsync.u], rax
0x18001c217  test    rax, rax
0x18001c21a  jnz     short loc_18001C237
0x18001c21c  call    cs:__imp_GetLastError
0x18001c222  test    eax, eax
0x18001c224  jle     short loc_18001C22E
0x18001c226  movzx   eax, ax
0x18001c229  or      eax, 80070000h
0x18001c22e  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001c235  jmp     short loc_18001C1DD
0x18001c237  mov     [rsp+178h+Handles], rax
0x18001c23f  lea     rax, [rsi+0Ch]
0x18001c243  lea     rcx, [rsi+10h]
0x18001c247  lea     rdx, [rsi+8]
0x18001c24b  lea     r8, [rsi+4]
0x18001c24f  mov     [rsp+178h+var_F8], rax
0x18001c257  mov     rax, [rsp+178h+var_D0]
0x18001c25f  mov     [rsp+178h+var_100], rax
0x18001c264  mov     [rsp+178h+var_108], rcx
0x18001c269  mov     [rsp+178h+var_110], rdx
0x18001c26e  mov     [rsp+178h+var_118], r8
0x18001c273  mov     [rsp+178h+var_120], rsi
0x18001c278  mov     rax, [r13+18h]
0x18001c27c  mov     [rsp+178h+var_128], rax
0x18001c281  mov     rax, [r13+10h]
0x18001c285  mov     [rsp+178h+var_130], rax
0x18001c28a  mov     rax, [r13+8]
0x18001c28e  mov     [rsp+178h+var_138], rax
0x18001c293  mov     rax, [rsp+178h+var_C8]
0x18001c29b  mov     [rsp+178h+var_140], rax
0x18001c2a0  mov     eax, [rsp+178h+var_DC]
0x18001c2a7  mov     [rsp+178h+var_148], eax
0x18001c2ab  mov     rax, [r13+0]
0x18001c2af  mov     [rsp+178h+var_150], rax
0x18001c2b4  mov     rax, [rsp+178h+var_C0]
0x18001c2bc  mov     qword ptr [rsp+178h+bAlertable], rax
0x18001c2c1  lea     r9, [rsp+178h+pAsync]
0x18001c2c9  xor     r8d, r8d; pReturnValue
0x18001c2cc  lea     edx, [r8+0Fh]; nProcNum
0x18001c2d0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001c2d7  call    cs:__imp_Ndr64AsyncClientCall
0x18001c2dd  mov     eax, [rsp+178h+Reply]
0x18001c2e4  jmp     short loc_18001C345
0x18001c2e6  test    eax, eax
0x18001c2e8  jle     short loc_18001C2F2
0x18001c2ea  movzx   eax, ax
0x18001c2ed  or      eax, 80070000h
0x18001c2f2  mov     [rsp+178h+Reply], eax
0x18001c2f9  mov     [rsp+178h+bAlertable], eax
0x18001c2fd  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001c304  mov     r8d, 2CAh; unsigned int
0x18001c30a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c311  mov     ecx, 2; unsigned __int8
0x18001c316  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c31b  mov     eax, [rsp+178h+Reply]
0x18001c322  test    eax, eax
0x18001c324  js      short loc_18001C332
0x18001c326  mov     eax, 8000FFFFh
0x18001c32b  mov     [rsp+178h+Reply], eax
0x18001c332  mov     r12d, [rsp+178h+dwMilliseconds]
0x18001c33a  mov     r15b, [rsp+178h+var_E4]
0x18001c342  mov     r14b, r15b
0x18001c345  test    eax, eax
0x18001c347  jns     short loc_18001C35B
0x18001c349  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001c350  mov     r8d, 2CAh
0x18001c356  jmp     loc_18001C431
0x18001c35b  mov     [rsp+178h+bAlertable], 0; bAlertable
0x18001c363  mov     r9d, r12d; dwMilliseconds
0x18001c366  xor     r8d, r8d; bWaitAll
0x18001c369  lea     rdx, [rsp+178h+Handles]; lpHandles
0x18001c371  lea     ecx, [r8+1]; nCount
0x18001c375  call    cs:__imp_WaitForMultipleObjectsEx
0x18001c37b  mov     esi, eax
0x18001c37d  mov     r12d, 102h
0x18001c383  test    r14b, r14b
0x18001c386  jnz     short loc_18001C3DA
0x18001c388  cmp     esi, r12d
0x18001c38b  jz      short loc_18001C392
0x18001c38d  cmp     esi, 1
0x18001c390  jnz     short loc_18001C3DA
0x18001c392  mov     edx, 1; fAbort
0x18001c397  lea     rcx, [rsp+178h+pAsync]; pAsync
0x18001c39f  call    cs:__imp_RpcAsyncCancelCall
0x18001c3a5  cmp     esi, r12d
0x18001c3a8  jnz     short loc_18001C3AF
0x18001c3aa  mov     r15b, 1
0x18001c3ad  jmp     short loc_18001C3B2
0x18001c3af  mov     r14b, 1
0x18001c3b2  mov     [rsp+178h+bAlertable], 0; bAlertable
0x18001c3ba  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001c3be  xor     r8d, r8d; bWaitAll
0x18001c3c1  lea     rdx, [rsp+178h+Handles]; lpHandles
0x18001c3c9  lea     ecx, [r8+1]; nCount
0x18001c3cd  call    cs:__imp_WaitForMultipleObjectsEx
0x18001c3d3  mov     esi, eax
0x18001c3d5  test    r15b, r15b
0x18001c3d8  jz      short loc_18001C383
0x18001c3da  test    esi, esi
0x18001c3dc  jz      short loc_18001C3F9
0x18001c3de  call    cs:__imp_GetLastError
0x18001c3e4  test    eax, eax
0x18001c3e6  jle     short loc_18001C3F0
0x18001c3e8  movzx   eax, ax
0x18001c3eb  or      eax, 80070000h
0x18001c3f0  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001c3f7  jmp     short loc_18001C424
0x18001c3f9  lea     rdx, [rsp+178h+Reply]; Reply
0x18001c401  lea     rcx, [rsp+178h+pAsync]; pAsync
0x18001c409  call    cs:__imp_RpcAsyncCompleteCall
0x18001c40f  test    eax, eax
0x18001c411  jz      short loc_18001C446
0x18001c413  jle     short loc_18001C41D
0x18001c415  movzx   eax, ax
0x18001c418  or      eax, 80070000h
0x18001c41d  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001c424  mov     r8d, 2CAh; unsigned int
0x18001c42a  mov     [rsp+178h+Reply], eax
0x18001c431  mov     [rsp+178h+bAlertable], eax
0x18001c435  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c43c  mov     ecx, 2; unsigned __int8
0x18001c441  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c446  mov     rcx, qword ptr [rsp+178h+pAsync.u]; hObject
0x18001c44e  test    rcx, rcx
0x18001c451  jz      short loc_18001C459
0x18001c453  call    cs:__imp_CloseHandle
0x18001c459  test    r15b, r15b
0x18001c45c  jz      short loc_18001C4A6
0x18001c45e  mov     [rsp+178h+Reply], 800705B4h
0x18001c469  lea     rdx, [rsp+178h+var_D8]
0x18001c471  lea     rcx, aWlidcacquireto_1; "WLIDCAcquireTokensEx"
0x18001c478  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001c47d  mov     eax, [rsp+178h+Reply]
0x18001c484  mov     [rsp+178h+bAlertable], eax
0x18001c488  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001c48f  mov     r8d, 2CAh; unsigned int
0x18001c495  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c49c  mov     ecx, 2; unsigned __int8
0x18001c4a1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c4a6  test    r14b, r14b
0x18001c4a9  jz      short loc_18001C4D9
0x18001c4ab  mov     eax, 800704C7h
0x18001c4b0  mov     [rsp+178h+Reply], eax
0x18001c4b7  mov     [rsp+178h+bAlertable], eax
0x18001c4bb  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001c4c2  mov     r8d, 2CAh; unsigned int
0x18001c4c8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c4cf  mov     ecx, 2; unsigned __int8
0x18001c4d4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c4d9  mov     ecx, [rsp+178h+Reply]
0x18001c4e0  cmp     ecx, 800706B5h
0x18001c4e6  jz      short loc_18001C4F0
0x18001c4e8  cmp     ecx, 800706BAh
0x18001c4ee  jnz     short loc_18001C4FC
0x18001c4f0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001c4f5  mov     ecx, [rsp+178h+Reply]; int
0x18001c4fc  lea     rdx, aWlidcacquireto_1; "WLIDCAcquireTokensEx"
0x18001c503  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x18001c508  mov     rcx, [rsp+178h+var_38]
0x18001c510  xor     rcx, rsp; StackCookie
0x18001c513  call    __security_check_cookie
0x18001c518  add     rsp, 150h
0x18001c51f  pop     r15
0x18001c521  pop     r14
0x18001c523  pop     r13
0x18001c525  pop     r12
0x18001c527  pop     rsi
0x18001c528  retn
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
