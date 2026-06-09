# WLIDCGetUserPropertiesFromSystemStore(ushort const *,ulong *,_WLIDIdentityProperty * *)

- ea: `0x180020b18`
- end: `0x180020e75`
- name: `?WLIDCGetUserPropertiesFromSystemStore@@YAJPEBGPEAKPEAPEAU_WLIDIdentityProperty@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct _WLIDIdentityProperty **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019890`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a398`
- `0x18001ba00`
- `0x180020750`
- `0x180020b18`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020ceb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020d3d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020ceb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020d3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020bff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020dba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020dba`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020c63`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020c63`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020d73`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020d73`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020bb8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020bb8`
- `RPCRT4!RpcAsyncCancelCall` at `0x180020d12`
- `RPCRT4!RpcAsyncCancelCall` at `0x180020d12`

## string_xrefs

- `0x180020c24`: `RPC failed to create new event, hr = %#x`
- `0x180020d87`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserPropertiesFromSystemStore(
        const unsigned __int16 *a1,
        unsigned int *a2,
        struct _WLIDIdentityProperty **a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-C8h] BYREF
  struct _WLIDIdentityProperty **v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v21 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
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
LABEL_6:
    v11 = 1102;
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
    v10 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x37u, 0, &pAsync, v20, a1, a2, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1104;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v11 = 1104;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[38],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x450u,
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
      0x450u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180020b18  push    rsi
0x180020b1a  push    r12
0x180020b1c  push    r13
0x180020b1e  push    r14
0x180020b20  push    r15
0x180020b22  sub     rsp, 0F0h
0x180020b29  mov     rax, cs:__security_cookie
0x180020b30  xor     rax, rsp
0x180020b33  mov     [rsp+118h+var_38], rax
0x180020b3b  mov     [rsp+118h+var_C0], r8
0x180020b40  mov     r13, rdx
0x180020b43  mov     r12, rcx
0x180020b46  mov     [rsp+118h+dwMilliseconds], 0
0x180020b4e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180020b53  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180020b58  mov     [rsp+118h+Reply], 0
0x180020b60  mov     [rsp+118h+var_C8], 0
0x180020b69  lea     rcx, [rsp+118h+var_C8]; this
0x180020b6e  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180020b73  mov     [rsp+118h+Reply], eax
0x180020b77  test    eax, eax
0x180020b79  js      loc_180020E54
0x180020b7f  xor     edx, edx; Val
0x180020b81  lea     r8d, [rdx+70h]; Size
0x180020b85  lea     rcx, [rsp+118h+pAsync]; void *
0x180020b8a  call    memset_0
0x180020b8f  mov     esi, [rsp+118h+dwMilliseconds]
0x180020b93  mov     [rsp+118h+dwMilliseconds], esi
0x180020b97  mov     [rsp+118h+var_CC], esi
0x180020b9b  xor     r15b, r15b
0x180020b9e  mov     [rsp+118h+var_D4], r15b
0x180020ba3  xor     r14b, r14b
0x180020ba6  xorps   xmm0, xmm0
0x180020ba9  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180020bae  mov     edx, 70h ; 'p'; Size
0x180020bb3  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180020bb8  call    cs:__imp_RpcAsyncInitializeHandle
0x180020bbe  test    eax, eax
0x180020bc0  jz      short loc_180020BDE
0x180020bc2  jle     short loc_180020BCC
0x180020bc4  movzx   eax, ax
0x180020bc7  or      eax, 80070000h
0x180020bcc  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180020bd3  mov     r8d, 44Eh
0x180020bd9  jmp     loc_180020D94
0x180020bde  mov     [rsp+118h+pAsync.UserInfo], 0
0x180020bea  mov     [rsp+118h+pAsync.NotificationType], 1
0x180020bf5  xor     r9d, r9d; lpName
0x180020bf8  xor     r8d, r8d; bInitialState
0x180020bfb  xor     edx, edx; bManualReset
0x180020bfd  xor     ecx, ecx; lpEventAttributes
0x180020bff  call    cs:__imp_CreateEventW
0x180020c05  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180020c0d  test    rax, rax
0x180020c10  jnz     short loc_180020C2D
0x180020c12  call    cs:__imp_GetLastError
0x180020c18  test    eax, eax
0x180020c1a  jle     short loc_180020C24
0x180020c1c  movzx   eax, ax
0x180020c1f  or      eax, 80070000h
0x180020c24  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180020c2b  jmp     short loc_180020BD3
0x180020c2d  mov     [rsp+118h+Handles], rax
0x180020c32  mov     rax, [rsp+118h+var_C0]
0x180020c37  mov     [rsp+118h+var_E0], rax
0x180020c3c  mov     [rsp+118h+var_E8], r13
0x180020c41  mov     [rsp+118h+var_F0], r12
0x180020c46  mov     rax, [rsp+118h+var_C8]
0x180020c4b  mov     qword ptr [rsp+118h+bAlertable], rax
0x180020c50  lea     r9, [rsp+118h+pAsync]
0x180020c55  xor     r8d, r8d; pReturnValue
0x180020c58  lea     edx, [r8+37h]; nProcNum
0x180020c5c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180020c63  call    cs:__imp_Ndr64AsyncClientCall
0x180020c69  mov     eax, [rsp+118h+Reply]
0x180020c6d  jmp     short loc_180020CBE
0x180020c6f  test    eax, eax
0x180020c71  jle     short loc_180020C7B
0x180020c73  movzx   eax, ax
0x180020c76  or      eax, 80070000h
0x180020c7b  mov     [rsp+118h+Reply], eax
0x180020c7f  mov     [rsp+118h+bAlertable], eax
0x180020c83  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180020c8a  mov     r8d, 450h; unsigned int
0x180020c90  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020c97  mov     ecx, 2; unsigned __int8
0x180020c9c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020ca1  mov     eax, [rsp+118h+Reply]
0x180020ca5  test    eax, eax
0x180020ca7  js      short loc_180020CB2
0x180020ca9  mov     eax, 8000FFFFh
0x180020cae  mov     [rsp+118h+Reply], eax
0x180020cb2  mov     esi, [rsp+118h+dwMilliseconds]
0x180020cb6  mov     r15b, [rsp+118h+var_D4]
0x180020cbb  mov     r14b, r15b
0x180020cbe  test    eax, eax
0x180020cc0  jns     short loc_180020CD4
0x180020cc2  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180020cc9  mov     r8d, 450h
0x180020ccf  jmp     loc_180020D98
0x180020cd4  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180020cdc  mov     r9d, esi; dwMilliseconds
0x180020cdf  xor     r8d, r8d; bWaitAll
0x180020ce2  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180020ce7  lea     ecx, [r8+1]; nCount
0x180020ceb  call    cs:__imp_WaitForMultipleObjectsEx
0x180020cf1  mov     esi, eax
0x180020cf3  mov     r12d, 102h
0x180020cf9  test    r14b, r14b
0x180020cfc  jnz     short loc_180020D4A
0x180020cfe  cmp     esi, r12d
0x180020d01  jz      short loc_180020D08
0x180020d03  cmp     esi, 1
0x180020d06  jnz     short loc_180020D4A
0x180020d08  mov     edx, 1; fAbort
0x180020d0d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180020d12  call    cs:__imp_RpcAsyncCancelCall
0x180020d18  cmp     esi, r12d
0x180020d1b  jnz     short loc_180020D22
0x180020d1d  mov     r15b, 1
0x180020d20  jmp     short loc_180020D25
0x180020d22  mov     r14b, 1
0x180020d25  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180020d2d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180020d31  xor     r8d, r8d; bWaitAll
0x180020d34  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180020d39  lea     ecx, [r8+1]; nCount
0x180020d3d  call    cs:__imp_WaitForMultipleObjectsEx
0x180020d43  mov     esi, eax
0x180020d45  test    r15b, r15b
0x180020d48  jz      short loc_180020CF9
0x180020d4a  test    esi, esi
0x180020d4c  jz      short loc_180020D69
0x180020d4e  call    cs:__imp_GetLastError
0x180020d54  test    eax, eax
0x180020d56  jle     short loc_180020D60
0x180020d58  movzx   eax, ax
0x180020d5b  or      eax, 80070000h
0x180020d60  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180020d67  jmp     short loc_180020D8E
0x180020d69  lea     rdx, [rsp+118h+Reply]; Reply
0x180020d6e  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180020d73  call    cs:__imp_RpcAsyncCompleteCall
0x180020d79  test    eax, eax
0x180020d7b  jz      short loc_180020DAD
0x180020d7d  jle     short loc_180020D87
0x180020d7f  movzx   eax, ax
0x180020d82  or      eax, 80070000h
0x180020d87  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180020d8e  mov     r8d, 450h; unsigned int
0x180020d94  mov     [rsp+118h+Reply], eax
0x180020d98  mov     [rsp+118h+bAlertable], eax
0x180020d9c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020da3  mov     ecx, 2; unsigned __int8
0x180020da8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020dad  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180020db5  test    rcx, rcx
0x180020db8  jz      short loc_180020DC0
0x180020dba  call    cs:__imp_CloseHandle
0x180020dc0  test    r15b, r15b
0x180020dc3  jz      short loc_180020DFD
0x180020dc5  mov     [rsp+118h+Reply], 800705B4h
0x180020dcd  lea     rdx, [rsp+118h+var_CC]
0x180020dd2  call    ??$RPCCallTimedOut@AEAY0CG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[38],ulong &>(char const (&)[38],ulong &)
0x180020dd7  mov     eax, [rsp+118h+Reply]
0x180020ddb  mov     [rsp+118h+bAlertable], eax
0x180020ddf  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180020de6  mov     r8d, 450h; unsigned int
0x180020dec  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020df3  mov     ecx, 2; unsigned __int8
0x180020df8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020dfd  test    r14b, r14b
0x180020e00  jz      short loc_180020E2D
0x180020e02  mov     eax, 800704C7h
0x180020e07  mov     [rsp+118h+Reply], eax
0x180020e0b  mov     [rsp+118h+bAlertable], eax
0x180020e0f  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180020e16  mov     r8d, 450h; unsigned int
0x180020e1c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020e23  mov     ecx, 2; unsigned __int8
0x180020e28  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020e2d  cmp     [rsp+118h+Reply], 800706B5h
0x180020e35  jz      short loc_180020E41
0x180020e37  cmp     [rsp+118h+Reply], 800706BAh
0x180020e3f  jnz     short loc_180020E46
0x180020e41  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180020e46  lea     rcx, [rsp+118h+var_C8]; this
0x180020e4b  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180020e50  mov     eax, [rsp+118h+Reply]
0x180020e54  mov     rcx, [rsp+118h+var_38]
0x180020e5c  xor     rcx, rsp; StackCookie
0x180020e5f  call    __security_check_cookie
0x180020e64  add     rsp, 0F0h
0x180020e6b  pop     r15
0x180020e6d  pop     r14
0x180020e6f  pop     r13
0x180020e71  pop     r12
0x180020e73  pop     rsi
0x180020e74  retn
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
