# WLIDCRemovePersistedCredential(void * const,ushort const *,unsigned __int64)

- ea: `0x1800218a8`
- end: `0x180021bd0`
- name: `?WLIDCRemovePersistedCredential@@YAJQEAXPEBG_K@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019920`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a200`
- `0x18001ba00`
- `0x180020750`
- `0x1800218a8`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021a52`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021aa4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021a52`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021aa4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021970`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b21`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800219ca`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800219ca`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021ada`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021ada`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021929`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021929`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021a79`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021a79`

## string_xrefs

- `0x180021995`: `RPC failed to create new event, hr = %#x`
- `0x180021aee`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRemovePersistedCredential(void *const a1, const unsigned __int16 *a2, __int64 a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v19 = dwMilliseconds;
  v6 = 0;
  v17 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 856;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Cu, 0, &pAsync, a1, a2, v20);
  v12 = WaitForMultipleObjectsEx(1u, Handles, 0, v5, 0);
  do
  {
    if ( v7 || v12 != 258 && v12 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v12 == 258 )
      v6 = 1;
    else
      v7 = 1;
    v12 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v6 );
  if ( v12 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 858;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x35Au,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v7 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x35Au,
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
0x1800218a8  push    rsi
0x1800218aa  push    r12
0x1800218ac  push    r13
0x1800218ae  push    r14
0x1800218b0  push    r15
0x1800218b2  sub     rsp, 0F0h
0x1800218b9  mov     rax, cs:__security_cookie
0x1800218c0  xor     rax, rsp
0x1800218c3  mov     [rsp+118h+var_38], rax
0x1800218cb  mov     [rsp+118h+var_C8], r8
0x1800218d0  mov     r13, rdx
0x1800218d3  mov     r12, rcx
0x1800218d6  mov     [rsp+118h+Reply], 0
0x1800218de  mov     [rsp+118h+dwMilliseconds], 0
0x1800218e6  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x1800218eb  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800218f0  xor     edx, edx; Val
0x1800218f2  lea     r8d, [rdx+70h]; Size
0x1800218f6  lea     rcx, [rsp+118h+pAsync]; void *
0x1800218fb  call    memset_0
0x180021900  mov     esi, [rsp+118h+dwMilliseconds]
0x180021904  mov     [rsp+118h+dwMilliseconds], esi
0x180021908  mov     [rsp+118h+var_CC], esi
0x18002190c  xor     r15b, r15b
0x18002190f  mov     [rsp+118h+var_D4], r15b
0x180021914  xor     r14b, r14b
0x180021917  xorps   xmm0, xmm0
0x18002191a  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18002191f  mov     edx, 70h ; 'p'; Size
0x180021924  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180021929  call    cs:__imp_RpcAsyncInitializeHandle
0x18002192f  test    eax, eax
0x180021931  jz      short loc_18002194F
0x180021933  jle     short loc_18002193D
0x180021935  movzx   eax, ax
0x180021938  or      eax, 80070000h
0x18002193d  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180021944  mov     r8d, 358h
0x18002194a  jmp     loc_180021AFB
0x18002194f  mov     [rsp+118h+pAsync.UserInfo], 0
0x18002195b  mov     [rsp+118h+pAsync.NotificationType], 1
0x180021966  xor     r9d, r9d; lpName
0x180021969  xor     r8d, r8d; bInitialState
0x18002196c  xor     edx, edx; bManualReset
0x18002196e  xor     ecx, ecx; lpEventAttributes
0x180021970  call    cs:__imp_CreateEventW
0x180021976  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18002197e  test    rax, rax
0x180021981  jnz     short loc_18002199E
0x180021983  call    cs:__imp_GetLastError
0x180021989  test    eax, eax
0x18002198b  jle     short loc_180021995
0x18002198d  movzx   eax, ax
0x180021990  or      eax, 80070000h
0x180021995  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18002199c  jmp     short loc_180021944
0x18002199e  mov     [rsp+118h+Handles], rax
0x1800219a3  mov     rax, [rsp+118h+var_C8]
0x1800219a8  mov     [rsp+118h+var_E8], rax
0x1800219ad  mov     [rsp+118h+var_F0], r13
0x1800219b2  mov     qword ptr [rsp+118h+bAlertable], r12
0x1800219b7  lea     r9, [rsp+118h+pAsync]
0x1800219bc  xor     r8d, r8d; pReturnValue
0x1800219bf  lea     edx, [r8+1Ch]; nProcNum
0x1800219c3  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800219ca  call    cs:__imp_Ndr64AsyncClientCall
0x1800219d0  mov     eax, [rsp+118h+Reply]
0x1800219d4  jmp     short loc_180021A25
0x1800219d6  test    eax, eax
0x1800219d8  jle     short loc_1800219E2
0x1800219da  movzx   eax, ax
0x1800219dd  or      eax, 80070000h
0x1800219e2  mov     [rsp+118h+Reply], eax
0x1800219e6  mov     [rsp+118h+bAlertable], eax
0x1800219ea  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800219f1  mov     r8d, 35Ah; unsigned int
0x1800219f7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800219fe  mov     ecx, 2; unsigned __int8
0x180021a03  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021a08  mov     eax, [rsp+118h+Reply]
0x180021a0c  test    eax, eax
0x180021a0e  js      short loc_180021A19
0x180021a10  mov     eax, 8000FFFFh
0x180021a15  mov     [rsp+118h+Reply], eax
0x180021a19  mov     esi, [rsp+118h+dwMilliseconds]
0x180021a1d  mov     r15b, [rsp+118h+var_D4]
0x180021a22  mov     r14b, r15b
0x180021a25  test    eax, eax
0x180021a27  jns     short loc_180021A3B
0x180021a29  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180021a30  mov     r8d, 35Ah
0x180021a36  jmp     loc_180021AFF
0x180021a3b  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180021a43  mov     r9d, esi; dwMilliseconds
0x180021a46  xor     r8d, r8d; bWaitAll
0x180021a49  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180021a4e  lea     ecx, [r8+1]; nCount
0x180021a52  call    cs:__imp_WaitForMultipleObjectsEx
0x180021a58  mov     esi, eax
0x180021a5a  mov     r12d, 102h
0x180021a60  test    r14b, r14b
0x180021a63  jnz     short loc_180021AB1
0x180021a65  cmp     esi, r12d
0x180021a68  jz      short loc_180021A6F
0x180021a6a  cmp     esi, 1
0x180021a6d  jnz     short loc_180021AB1
0x180021a6f  mov     edx, 1; fAbort
0x180021a74  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180021a79  call    cs:__imp_RpcAsyncCancelCall
0x180021a7f  cmp     esi, r12d
0x180021a82  jnz     short loc_180021A89
0x180021a84  mov     r15b, 1
0x180021a87  jmp     short loc_180021A8C
0x180021a89  mov     r14b, 1
0x180021a8c  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180021a94  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180021a98  xor     r8d, r8d; bWaitAll
0x180021a9b  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180021aa0  lea     ecx, [r8+1]; nCount
0x180021aa4  call    cs:__imp_WaitForMultipleObjectsEx
0x180021aaa  mov     esi, eax
0x180021aac  test    r15b, r15b
0x180021aaf  jz      short loc_180021A60
0x180021ab1  test    esi, esi
0x180021ab3  jz      short loc_180021AD0
0x180021ab5  call    cs:__imp_GetLastError
0x180021abb  test    eax, eax
0x180021abd  jle     short loc_180021AC7
0x180021abf  movzx   eax, ax
0x180021ac2  or      eax, 80070000h
0x180021ac7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180021ace  jmp     short loc_180021AF5
0x180021ad0  lea     rdx, [rsp+118h+Reply]; Reply
0x180021ad5  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180021ada  call    cs:__imp_RpcAsyncCompleteCall
0x180021ae0  test    eax, eax
0x180021ae2  jz      short loc_180021B14
0x180021ae4  jle     short loc_180021AEE
0x180021ae6  movzx   eax, ax
0x180021ae9  or      eax, 80070000h
0x180021aee  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180021af5  mov     r8d, 35Ah; unsigned int
0x180021afb  mov     [rsp+118h+Reply], eax
0x180021aff  mov     [rsp+118h+bAlertable], eax
0x180021b03  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021b0a  mov     ecx, 2; unsigned __int8
0x180021b0f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021b14  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180021b1c  test    rcx, rcx
0x180021b1f  jz      short loc_180021B27
0x180021b21  call    cs:__imp_CloseHandle
0x180021b27  test    r15b, r15b
0x180021b2a  jz      short loc_180021B64
0x180021b2c  mov     [rsp+118h+Reply], 800705B4h
0x180021b34  lea     rdx, [rsp+118h+var_CC]
0x180021b39  call    ??$RPCCallTimedOut@AEAY0BP@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BP@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[31],ulong &>(char const (&)[31],ulong &)
0x180021b3e  mov     eax, [rsp+118h+Reply]
0x180021b42  mov     [rsp+118h+bAlertable], eax
0x180021b46  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180021b4d  mov     r8d, 35Ah; unsigned int
0x180021b53  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021b5a  mov     ecx, 2; unsigned __int8
0x180021b5f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021b64  test    r14b, r14b
0x180021b67  jz      short loc_180021B94
0x180021b69  mov     eax, 800704C7h
0x180021b6e  mov     [rsp+118h+Reply], eax
0x180021b72  mov     [rsp+118h+bAlertable], eax
0x180021b76  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180021b7d  mov     r8d, 35Ah; unsigned int
0x180021b83  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021b8a  mov     ecx, 2; unsigned __int8
0x180021b8f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021b94  mov     eax, [rsp+118h+Reply]
0x180021b98  cmp     eax, 800706B5h
0x180021b9d  jz      short loc_180021BA6
0x180021b9f  cmp     eax, 800706BAh
0x180021ba4  jnz     short loc_180021BAF
0x180021ba6  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180021bab  mov     eax, [rsp+118h+Reply]
0x180021baf  mov     rcx, [rsp+118h+var_38]
0x180021bb7  xor     rcx, rsp; StackCookie
0x180021bba  call    __security_check_cookie
0x180021bbf  add     rsp, 0F0h
0x180021bc6  pop     r15
0x180021bc8  pop     r14
0x180021bca  pop     r13
0x180021bcc  pop     r12
0x180021bce  pop     rsi
0x180021bcf  retn
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
