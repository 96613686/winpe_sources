# WLIDCPersistCredential(void * const,ushort const *,unsigned __int64,ushort * *)

- ea: `0x1800211ac`
- end: `0x18002150e`
- name: `?WLIDCPersistCredential@@YAJQEAXPEBG_KPEAPEAG@Z`
- size: `866`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800198d0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019e38`
- `0x18001ba00`
- `0x180020750`
- `0x1800211ac`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021383`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800213d8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021383`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800213d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021288`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002129b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002129b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021458`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800212fb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800212fb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021411`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021411`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021241`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021241`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800213ad`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800213ad`

## string_xrefs

- `0x1800212ad`: `RPC failed to create new event, hr = %#x`
- `0x180021425`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCPersistCredential(
        void *const a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  unsigned __int16 **v13; // rax
  DWORD v14; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  unsigned int Reply; // [rsp+40h] [rbp-E8h] BYREF
  char v18; // [rsp+44h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-E0h] BYREF
  DWORD v20; // [rsp+4Ch] [rbp-DCh] BYREF
  __int64 v21; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-D0h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+68h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v22 = a3;
  v23 = a2;
  v21 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v11 = 840;
    goto LABEL_29;
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
  v13 = (unsigned __int16 **)&v21;
  if ( a4 )
    v13 = a4;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Bu, 0, &pAsync, a1, v23, v22, v13);
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
  do
  {
    if ( v8 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v7 = 1;
    else
      v8 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v7 );
  if ( v14 )
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
      goto LABEL_30;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 847;
LABEL_29:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_30:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCPersistCredential",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x34Fu,
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
      0x34Fu,
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
0x1800211ac  push    rsi
0x1800211ae  push    r12
0x1800211b0  push    r13
0x1800211b2  push    r14
0x1800211b4  push    r15
0x1800211b6  sub     rsp, 100h
0x1800211bd  mov     rax, cs:__security_cookie
0x1800211c4  xor     rax, rsp
0x1800211c7  mov     [rsp+128h+var_38], rax
0x1800211cf  mov     r12, r9
0x1800211d2  mov     [rsp+128h+var_D0], r8
0x1800211d7  mov     [rsp+128h+var_C8], rdx
0x1800211dc  mov     r13, rcx
0x1800211df  mov     [rsp+128h+var_D8], 0
0x1800211e8  mov     [rsp+128h+Reply], 0
0x1800211f0  mov     [rsp+128h+dwMilliseconds], 0
0x1800211f8  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x1800211fd  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180021202  xor     edx, edx; Val
0x180021204  lea     r8d, [rdx+70h]; Size
0x180021208  lea     rcx, [rsp+128h+pAsync]; void *
0x180021210  call    memset_0
0x180021215  mov     esi, [rsp+128h+dwMilliseconds]
0x180021219  mov     [rsp+128h+dwMilliseconds], esi
0x18002121d  mov     [rsp+128h+var_DC], esi
0x180021221  xor     r15b, r15b
0x180021224  mov     [rsp+128h+var_E4], r15b
0x180021229  xor     r14b, r14b
0x18002122c  xorps   xmm0, xmm0
0x18002122f  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x180021234  mov     edx, 70h ; 'p'; Size
0x180021239  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180021241  call    cs:__imp_RpcAsyncInitializeHandle
0x180021247  test    eax, eax
0x180021249  jz      short loc_180021267
0x18002124b  jle     short loc_180021255
0x18002124d  movzx   eax, ax
0x180021250  or      eax, 80070000h
0x180021255  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18002125c  mov     r8d, 348h
0x180021262  jmp     loc_180021432
0x180021267  mov     [rsp+128h+pAsync.UserInfo], 0
0x180021273  mov     [rsp+128h+pAsync.NotificationType], 1
0x18002127e  xor     r9d, r9d; lpName
0x180021281  xor     r8d, r8d; bInitialState
0x180021284  xor     edx, edx; bManualReset
0x180021286  xor     ecx, ecx; lpEventAttributes
0x180021288  call    cs:__imp_CreateEventW
0x18002128e  mov     qword ptr [rsp+128h+pAsync.u], rax
0x180021296  test    rax, rax
0x180021299  jnz     short loc_1800212B6
0x18002129b  call    cs:__imp_GetLastError
0x1800212a1  test    eax, eax
0x1800212a3  jle     short loc_1800212AD
0x1800212a5  movzx   eax, ax
0x1800212a8  or      eax, 80070000h
0x1800212ad  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800212b4  jmp     short loc_18002125C
0x1800212b6  mov     [rsp+128h+Handles], rax
0x1800212bb  lea     rax, [rsp+128h+var_D8]
0x1800212c0  test    r12, r12
0x1800212c3  cmovnz  rax, r12
0x1800212c7  mov     [rsp+128h+var_F0], rax
0x1800212cc  mov     rax, [rsp+128h+var_D0]
0x1800212d1  mov     [rsp+128h+var_F8], rax
0x1800212d6  mov     rax, [rsp+128h+var_C8]
0x1800212db  mov     [rsp+128h+var_100], rax
0x1800212e0  mov     qword ptr [rsp+128h+bAlertable], r13
0x1800212e5  lea     r9, [rsp+128h+pAsync]
0x1800212ed  xor     r8d, r8d; pReturnValue
0x1800212f0  lea     edx, [r8+1Bh]; nProcNum
0x1800212f4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800212fb  call    cs:__imp_Ndr64AsyncClientCall
0x180021301  mov     eax, [rsp+128h+Reply]
0x180021305  jmp     short loc_180021356
0x180021307  test    eax, eax
0x180021309  jle     short loc_180021313
0x18002130b  movzx   eax, ax
0x18002130e  or      eax, 80070000h
0x180021313  mov     [rsp+128h+Reply], eax
0x180021317  mov     [rsp+128h+bAlertable], eax
0x18002131b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180021322  mov     r8d, 34Fh; unsigned int
0x180021328  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002132f  mov     ecx, 2; unsigned __int8
0x180021334  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021339  mov     eax, [rsp+128h+Reply]
0x18002133d  test    eax, eax
0x18002133f  js      short loc_18002134A
0x180021341  mov     eax, 8000FFFFh
0x180021346  mov     [rsp+128h+Reply], eax
0x18002134a  mov     esi, [rsp+128h+dwMilliseconds]
0x18002134e  mov     r15b, [rsp+128h+var_E4]
0x180021353  mov     r14b, r15b
0x180021356  test    eax, eax
0x180021358  jns     short loc_18002136C
0x18002135a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180021361  mov     r8d, 34Fh
0x180021367  jmp     loc_180021436
0x18002136c  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180021374  mov     r9d, esi; dwMilliseconds
0x180021377  xor     r8d, r8d; bWaitAll
0x18002137a  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18002137f  lea     ecx, [r8+1]; nCount
0x180021383  call    cs:__imp_WaitForMultipleObjectsEx
0x180021389  mov     esi, eax
0x18002138b  mov     r12d, 102h
0x180021391  test    r14b, r14b
0x180021394  jnz     short loc_1800213E5
0x180021396  cmp     esi, r12d
0x180021399  jz      short loc_1800213A0
0x18002139b  cmp     esi, 1
0x18002139e  jnz     short loc_1800213E5
0x1800213a0  mov     edx, 1; fAbort
0x1800213a5  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1800213ad  call    cs:__imp_RpcAsyncCancelCall
0x1800213b3  cmp     esi, r12d
0x1800213b6  jnz     short loc_1800213BD
0x1800213b8  mov     r15b, 1
0x1800213bb  jmp     short loc_1800213C0
0x1800213bd  mov     r14b, 1
0x1800213c0  mov     [rsp+128h+bAlertable], 0; bAlertable
0x1800213c8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800213cc  xor     r8d, r8d; bWaitAll
0x1800213cf  lea     rdx, [rsp+128h+Handles]; lpHandles
0x1800213d4  lea     ecx, [r8+1]; nCount
0x1800213d8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800213de  mov     esi, eax
0x1800213e0  test    r15b, r15b
0x1800213e3  jz      short loc_180021391
0x1800213e5  test    esi, esi
0x1800213e7  jz      short loc_180021404
0x1800213e9  call    cs:__imp_GetLastError
0x1800213ef  test    eax, eax
0x1800213f1  jle     short loc_1800213FB
0x1800213f3  movzx   eax, ax
0x1800213f6  or      eax, 80070000h
0x1800213fb  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180021402  jmp     short loc_18002142C
0x180021404  lea     rdx, [rsp+128h+Reply]; Reply
0x180021409  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180021411  call    cs:__imp_RpcAsyncCompleteCall
0x180021417  test    eax, eax
0x180021419  jz      short loc_18002144B
0x18002141b  jle     short loc_180021425
0x18002141d  movzx   eax, ax
0x180021420  or      eax, 80070000h
0x180021425  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18002142c  mov     r8d, 34Fh; unsigned int
0x180021432  mov     [rsp+128h+Reply], eax
0x180021436  mov     [rsp+128h+bAlertable], eax
0x18002143a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021441  mov     ecx, 2; unsigned __int8
0x180021446  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002144b  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180021453  test    rcx, rcx
0x180021456  jz      short loc_18002145E
0x180021458  call    cs:__imp_CloseHandle
0x18002145e  test    r15b, r15b
0x180021461  jz      short loc_1800214A2
0x180021463  mov     [rsp+128h+Reply], 800705B4h
0x18002146b  lea     rdx, [rsp+128h+var_DC]
0x180021470  lea     rcx, aWlidcpersistcr; "WLIDCPersistCredential"
0x180021477  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x18002147c  mov     eax, [rsp+128h+Reply]
0x180021480  mov     [rsp+128h+bAlertable], eax
0x180021484  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18002148b  mov     r8d, 34Fh; unsigned int
0x180021491  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021498  mov     ecx, 2; unsigned __int8
0x18002149d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800214a2  test    r14b, r14b
0x1800214a5  jz      short loc_1800214D2
0x1800214a7  mov     eax, 800704C7h
0x1800214ac  mov     [rsp+128h+Reply], eax
0x1800214b0  mov     [rsp+128h+bAlertable], eax
0x1800214b4  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800214bb  mov     r8d, 34Fh; unsigned int
0x1800214c1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800214c8  mov     ecx, 2; unsigned __int8
0x1800214cd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800214d2  mov     eax, [rsp+128h+Reply]
0x1800214d6  cmp     eax, 800706B5h
0x1800214db  jz      short loc_1800214E4
0x1800214dd  cmp     eax, 800706BAh
0x1800214e2  jnz     short loc_1800214ED
0x1800214e4  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800214e9  mov     eax, [rsp+128h+Reply]
0x1800214ed  mov     rcx, [rsp+128h+var_38]
0x1800214f5  xor     rcx, rsp; StackCookie
0x1800214f8  call    __security_check_cookie
0x1800214fd  add     rsp, 100h
0x180021504  pop     r15
0x180021506  pop     r14
0x180021508  pop     r13
0x18002150a  pop     r12
0x18002150c  pop     rsi
0x18002150d  retn
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
