# WLIDCSetIdentityExtendedProperty(void * const,ushort const *,ushort const *)

- ea: `0x18002225c`
- end: `0x180022584`
- name: `?WLIDCSetIdentityExtendedProperty@@YAJQEAXPEBG1@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019970`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a310`
- `0x18001ba00`
- `0x180020750`
- `0x18002225c`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022406`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022458`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022406`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022458`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022324`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800224d5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002237e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18002237e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002248e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002248e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800222dd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800222dd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002242d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002242d`

## string_xrefs

- `0x180022349`: `RPC failed to create new event, hr = %#x`
- `0x1800224a2`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetIdentityExtendedProperty(
        void *const a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
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
  const unsigned __int16 *v20; // [rsp+50h] [rbp-C8h]
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
    v10 = 775;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x17u, 0, &pAsync, a1, a2, v20);
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
  v10 = 777;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x309u,
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
      0x309u,
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
0x18002225c  push    rsi
0x18002225e  push    r12
0x180022260  push    r13
0x180022262  push    r14
0x180022264  push    r15
0x180022266  sub     rsp, 0F0h
0x18002226d  mov     rax, cs:__security_cookie
0x180022274  xor     rax, rsp
0x180022277  mov     [rsp+118h+var_38], rax
0x18002227f  mov     [rsp+118h+var_C8], r8
0x180022284  mov     r13, rdx
0x180022287  mov     r12, rcx
0x18002228a  mov     [rsp+118h+Reply], 0
0x180022292  mov     [rsp+118h+dwMilliseconds], 0
0x18002229a  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18002229f  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800222a4  xor     edx, edx; Val
0x1800222a6  lea     r8d, [rdx+70h]; Size
0x1800222aa  lea     rcx, [rsp+118h+pAsync]; void *
0x1800222af  call    memset_0
0x1800222b4  mov     esi, [rsp+118h+dwMilliseconds]
0x1800222b8  mov     [rsp+118h+dwMilliseconds], esi
0x1800222bc  mov     [rsp+118h+var_CC], esi
0x1800222c0  xor     r15b, r15b
0x1800222c3  mov     [rsp+118h+var_D4], r15b
0x1800222c8  xor     r14b, r14b
0x1800222cb  xorps   xmm0, xmm0
0x1800222ce  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x1800222d3  mov     edx, 70h ; 'p'; Size
0x1800222d8  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800222dd  call    cs:__imp_RpcAsyncInitializeHandle
0x1800222e3  test    eax, eax
0x1800222e5  jz      short loc_180022303
0x1800222e7  jle     short loc_1800222F1
0x1800222e9  movzx   eax, ax
0x1800222ec  or      eax, 80070000h
0x1800222f1  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800222f8  mov     r8d, 307h
0x1800222fe  jmp     loc_1800224AF
0x180022303  mov     [rsp+118h+pAsync.UserInfo], 0
0x18002230f  mov     [rsp+118h+pAsync.NotificationType], 1
0x18002231a  xor     r9d, r9d; lpName
0x18002231d  xor     r8d, r8d; bInitialState
0x180022320  xor     edx, edx; bManualReset
0x180022322  xor     ecx, ecx; lpEventAttributes
0x180022324  call    cs:__imp_CreateEventW
0x18002232a  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180022332  test    rax, rax
0x180022335  jnz     short loc_180022352
0x180022337  call    cs:__imp_GetLastError
0x18002233d  test    eax, eax
0x18002233f  jle     short loc_180022349
0x180022341  movzx   eax, ax
0x180022344  or      eax, 80070000h
0x180022349  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180022350  jmp     short loc_1800222F8
0x180022352  mov     [rsp+118h+Handles], rax
0x180022357  mov     rax, [rsp+118h+var_C8]
0x18002235c  mov     [rsp+118h+var_E8], rax
0x180022361  mov     [rsp+118h+var_F0], r13
0x180022366  mov     qword ptr [rsp+118h+bAlertable], r12
0x18002236b  lea     r9, [rsp+118h+pAsync]
0x180022370  xor     r8d, r8d; pReturnValue
0x180022373  lea     edx, [r8+17h]; nProcNum
0x180022377  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18002237e  call    cs:__imp_Ndr64AsyncClientCall
0x180022384  mov     eax, [rsp+118h+Reply]
0x180022388  jmp     short loc_1800223D9
0x18002238a  test    eax, eax
0x18002238c  jle     short loc_180022396
0x18002238e  movzx   eax, ax
0x180022391  or      eax, 80070000h
0x180022396  mov     [rsp+118h+Reply], eax
0x18002239a  mov     [rsp+118h+bAlertable], eax
0x18002239e  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800223a5  mov     r8d, 309h; unsigned int
0x1800223ab  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800223b2  mov     ecx, 2; unsigned __int8
0x1800223b7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800223bc  mov     eax, [rsp+118h+Reply]
0x1800223c0  test    eax, eax
0x1800223c2  js      short loc_1800223CD
0x1800223c4  mov     eax, 8000FFFFh
0x1800223c9  mov     [rsp+118h+Reply], eax
0x1800223cd  mov     esi, [rsp+118h+dwMilliseconds]
0x1800223d1  mov     r15b, [rsp+118h+var_D4]
0x1800223d6  mov     r14b, r15b
0x1800223d9  test    eax, eax
0x1800223db  jns     short loc_1800223EF
0x1800223dd  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800223e4  mov     r8d, 309h
0x1800223ea  jmp     loc_1800224B3
0x1800223ef  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800223f7  mov     r9d, esi; dwMilliseconds
0x1800223fa  xor     r8d, r8d; bWaitAll
0x1800223fd  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180022402  lea     ecx, [r8+1]; nCount
0x180022406  call    cs:__imp_WaitForMultipleObjectsEx
0x18002240c  mov     esi, eax
0x18002240e  mov     r12d, 102h
0x180022414  test    r14b, r14b
0x180022417  jnz     short loc_180022465
0x180022419  cmp     esi, r12d
0x18002241c  jz      short loc_180022423
0x18002241e  cmp     esi, 1
0x180022421  jnz     short loc_180022465
0x180022423  mov     edx, 1; fAbort
0x180022428  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18002242d  call    cs:__imp_RpcAsyncCancelCall
0x180022433  cmp     esi, r12d
0x180022436  jnz     short loc_18002243D
0x180022438  mov     r15b, 1
0x18002243b  jmp     short loc_180022440
0x18002243d  mov     r14b, 1
0x180022440  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180022448  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002244c  xor     r8d, r8d; bWaitAll
0x18002244f  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180022454  lea     ecx, [r8+1]; nCount
0x180022458  call    cs:__imp_WaitForMultipleObjectsEx
0x18002245e  mov     esi, eax
0x180022460  test    r15b, r15b
0x180022463  jz      short loc_180022414
0x180022465  test    esi, esi
0x180022467  jz      short loc_180022484
0x180022469  call    cs:__imp_GetLastError
0x18002246f  test    eax, eax
0x180022471  jle     short loc_18002247B
0x180022473  movzx   eax, ax
0x180022476  or      eax, 80070000h
0x18002247b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180022482  jmp     short loc_1800224A9
0x180022484  lea     rdx, [rsp+118h+Reply]; Reply
0x180022489  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18002248e  call    cs:__imp_RpcAsyncCompleteCall
0x180022494  test    eax, eax
0x180022496  jz      short loc_1800224C8
0x180022498  jle     short loc_1800224A2
0x18002249a  movzx   eax, ax
0x18002249d  or      eax, 80070000h
0x1800224a2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800224a9  mov     r8d, 309h; unsigned int
0x1800224af  mov     [rsp+118h+Reply], eax
0x1800224b3  mov     [rsp+118h+bAlertable], eax
0x1800224b7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800224be  mov     ecx, 2; unsigned __int8
0x1800224c3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800224c8  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x1800224d0  test    rcx, rcx
0x1800224d3  jz      short loc_1800224DB
0x1800224d5  call    cs:__imp_CloseHandle
0x1800224db  test    r15b, r15b
0x1800224de  jz      short loc_180022518
0x1800224e0  mov     [rsp+118h+Reply], 800705B4h
0x1800224e8  lea     rdx, [rsp+118h+var_CC]
0x1800224ed  call    ??$RPCCallTimedOut@AEAY0CB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[33],ulong &>(char const (&)[33],ulong &)
0x1800224f2  mov     eax, [rsp+118h+Reply]
0x1800224f6  mov     [rsp+118h+bAlertable], eax
0x1800224fa  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180022501  mov     r8d, 309h; unsigned int
0x180022507  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002250e  mov     ecx, 2; unsigned __int8
0x180022513  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022518  test    r14b, r14b
0x18002251b  jz      short loc_180022548
0x18002251d  mov     eax, 800704C7h
0x180022522  mov     [rsp+118h+Reply], eax
0x180022526  mov     [rsp+118h+bAlertable], eax
0x18002252a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180022531  mov     r8d, 309h; unsigned int
0x180022537  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002253e  mov     ecx, 2; unsigned __int8
0x180022543  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022548  mov     eax, [rsp+118h+Reply]
0x18002254c  cmp     eax, 800706B5h
0x180022551  jz      short loc_18002255A
0x180022553  cmp     eax, 800706BAh
0x180022558  jnz     short loc_180022563
0x18002255a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18002255f  mov     eax, [rsp+118h+Reply]
0x180022563  mov     rcx, [rsp+118h+var_38]
0x18002256b  xor     rcx, rsp; StackCookie
0x18002256e  call    __security_check_cookie
0x180022573  add     rsp, 0F0h
0x18002257a  pop     r15
0x18002257c  pop     r14
0x18002257e  pop     r13
0x180022580  pop     r12
0x180022582  pop     rsi
0x180022583  retn
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
