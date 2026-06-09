# WLIDCCreateContextWithLogonId(ushort const *,ushort const *,ulong,long,unsigned __int64,void * *)

- ea: `0x18001d3bc`
- end: `0x18001d769`
- name: `?WLIDCCreateContextWithLogonId@@YAJPEBG0KJ_KPEAPEAX@Z`
- size: `941`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019670`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a178`
- `0x18001ba00`
- `0x18001d3bc`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d5d6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d62e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d5d6`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d62e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d4c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d6ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d6ae`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d54b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d54b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d667`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d667`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d47a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d47a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d600`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d600`

## string_xrefs

- `0x18001d4e6`: `RPC failed to create new event, hr = %#x`
- `0x18001d67b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextWithLogonId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned __int64 a5,
        void **a6)
{
  __int64 result; // rax
  DWORD v9; // esi
  char v10; // r15
  char v11; // r14
  int LastError; // eax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v16; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-128h]
  int Reply; // [rsp+60h] [rbp-E8h] BYREF
  char v20; // [rsp+64h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+68h] [rbp-E0h] BYREF
  int v22; // [rsp+6Ch] [rbp-DCh]
  int v23; // [rsp+70h] [rbp-D8h]
  DWORD v24; // [rsp+74h] [rbp-D4h] BYREF
  __int64 v25; // [rsp+78h] [rbp-D0h] BYREF
  void **v26; // [rsp+80h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+88h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-A8h] BYREF

  v22 = a4;
  v23 = a3;
  v26 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v25 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v25);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v24 = dwMilliseconds;
  v10 = 0;
  v20 = 0;
  v11 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v14 = 598;
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
    v13 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xBu,
    0,
    &pAsync,
    v25,
    a1,
    a2,
    v23,
    v22,
    a5,
    v26);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 600;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v14,
      v13,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v16 = WaitForMultipleObjectsEx(1u, Handles, 0, v9, 0);
  do
  {
    if ( v11 || v16 != 258 && v16 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v16 == 258 )
      v10 = 1;
    else
      v11 = 1;
    v16 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v10 );
  if ( v16 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v14 = 600;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v10 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v24);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x258u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v11 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x258u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v25);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18001d3bc  push    rsi
0x18001d3be  push    r12
0x18001d3c0  push    r13
0x18001d3c2  push    r14
0x18001d3c4  push    r15
0x18001d3c6  sub     rsp, 120h
0x18001d3cd  mov     rax, cs:__security_cookie
0x18001d3d4  xor     rax, rsp
0x18001d3d7  mov     [rsp+148h+var_38], rax
0x18001d3df  mov     [rsp+148h+var_DC], r9d
0x18001d3e4  mov     [rsp+148h+var_D8], r8d
0x18001d3e9  mov     r13, rdx
0x18001d3ec  mov     r12, rcx
0x18001d3ef  mov     rax, [rsp+148h+arg_28]
0x18001d3f7  mov     [rsp+148h+var_C8], rax
0x18001d3ff  mov     [rsp+148h+dwMilliseconds], 0
0x18001d407  lea     r8, [rsp+148h+dwMilliseconds]; unsigned int *
0x18001d40c  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001d411  mov     [rsp+148h+Reply], 0
0x18001d419  mov     [rsp+148h+var_D0], 0
0x18001d422  lea     rcx, [rsp+148h+var_D0]; this
0x18001d427  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001d42c  mov     [rsp+148h+Reply], eax
0x18001d430  test    eax, eax
0x18001d432  js      loc_18001D748
0x18001d438  xor     edx, edx; Val
0x18001d43a  lea     r8d, [rdx+70h]; Size
0x18001d43e  lea     rcx, [rsp+148h+pAsync]; void *
0x18001d446  call    memset_0
0x18001d44b  mov     esi, [rsp+148h+dwMilliseconds]
0x18001d44f  mov     [rsp+148h+dwMilliseconds], esi
0x18001d453  mov     [rsp+148h+var_D4], esi
0x18001d457  xor     r15b, r15b
0x18001d45a  mov     [rsp+148h+var_E4], r15b
0x18001d45f  xor     r14b, r14b
0x18001d462  xorps   xmm0, xmm0
0x18001d465  movups  xmmword ptr [rsp+148h+Handles], xmm0
0x18001d46d  mov     edx, 70h ; 'p'; Size
0x18001d472  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001d47a  call    cs:__imp_RpcAsyncInitializeHandle
0x18001d480  test    eax, eax
0x18001d482  jz      short loc_18001D4A0
0x18001d484  jle     short loc_18001D48E
0x18001d486  movzx   eax, ax
0x18001d489  or      eax, 80070000h
0x18001d48e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001d495  mov     r8d, 256h
0x18001d49b  jmp     loc_18001D688
0x18001d4a0  mov     [rsp+148h+pAsync.UserInfo], 0
0x18001d4ac  mov     [rsp+148h+pAsync.NotificationType], 1
0x18001d4b7  xor     r9d, r9d; lpName
0x18001d4ba  xor     r8d, r8d; bInitialState
0x18001d4bd  xor     edx, edx; bManualReset
0x18001d4bf  xor     ecx, ecx; lpEventAttributes
0x18001d4c1  call    cs:__imp_CreateEventW
0x18001d4c7  mov     qword ptr [rsp+148h+pAsync.u], rax
0x18001d4cf  test    rax, rax
0x18001d4d2  jnz     short loc_18001D4EF
0x18001d4d4  call    cs:__imp_GetLastError
0x18001d4da  test    eax, eax
0x18001d4dc  jle     short loc_18001D4E6
0x18001d4de  movzx   eax, ax
0x18001d4e1  or      eax, 80070000h
0x18001d4e6  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001d4ed  jmp     short loc_18001D495
0x18001d4ef  mov     [rsp+148h+Handles], rax
0x18001d4f7  mov     rax, [rsp+148h+var_C8]
0x18001d4ff  mov     [rsp+148h+var_F8], rax
0x18001d504  mov     rax, [rsp+148h+arg_20]
0x18001d50c  mov     [rsp+148h+var_100], rax
0x18001d511  mov     eax, [rsp+148h+var_DC]
0x18001d515  mov     [rsp+148h+var_108], eax
0x18001d519  mov     eax, [rsp+148h+var_D8]
0x18001d51d  mov     [rsp+148h+var_110], eax
0x18001d521  mov     [rsp+148h+var_118], r13
0x18001d526  mov     [rsp+148h+var_120], r12
0x18001d52b  mov     rax, [rsp+148h+var_D0]
0x18001d530  mov     qword ptr [rsp+148h+bAlertable], rax
0x18001d535  lea     r9, [rsp+148h+pAsync]
0x18001d53d  xor     r8d, r8d; pReturnValue
0x18001d540  lea     edx, [r8+0Bh]; nProcNum
0x18001d544  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001d54b  call    cs:__imp_Ndr64AsyncClientCall
0x18001d551  mov     eax, [rsp+148h+Reply]
0x18001d555  jmp     short loc_18001D5A6
0x18001d557  test    eax, eax
0x18001d559  jle     short loc_18001D563
0x18001d55b  movzx   eax, ax
0x18001d55e  or      eax, 80070000h
0x18001d563  mov     [rsp+148h+Reply], eax
0x18001d567  mov     [rsp+148h+bAlertable], eax
0x18001d56b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001d572  mov     r8d, 258h; unsigned int
0x18001d578  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d57f  mov     ecx, 2; unsigned __int8
0x18001d584  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d589  mov     eax, [rsp+148h+Reply]
0x18001d58d  test    eax, eax
0x18001d58f  js      short loc_18001D59A
0x18001d591  mov     eax, 8000FFFFh
0x18001d596  mov     [rsp+148h+Reply], eax
0x18001d59a  mov     esi, [rsp+148h+dwMilliseconds]
0x18001d59e  mov     r15b, [rsp+148h+var_E4]
0x18001d5a3  mov     r14b, r15b
0x18001d5a6  test    eax, eax
0x18001d5a8  jns     short loc_18001D5BC
0x18001d5aa  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001d5b1  mov     r8d, 258h
0x18001d5b7  jmp     loc_18001D68C
0x18001d5bc  mov     [rsp+148h+bAlertable], 0; bAlertable
0x18001d5c4  mov     r9d, esi; dwMilliseconds
0x18001d5c7  xor     r8d, r8d; bWaitAll
0x18001d5ca  lea     rdx, [rsp+148h+Handles]; lpHandles
0x18001d5d2  lea     ecx, [r8+1]; nCount
0x18001d5d6  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d5dc  mov     esi, eax
0x18001d5de  mov     r12d, 102h
0x18001d5e4  test    r14b, r14b
0x18001d5e7  jnz     short loc_18001D63B
0x18001d5e9  cmp     esi, r12d
0x18001d5ec  jz      short loc_18001D5F3
0x18001d5ee  cmp     esi, 1
0x18001d5f1  jnz     short loc_18001D63B
0x18001d5f3  mov     edx, 1; fAbort
0x18001d5f8  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001d600  call    cs:__imp_RpcAsyncCancelCall
0x18001d606  cmp     esi, r12d
0x18001d609  jnz     short loc_18001D610
0x18001d60b  mov     r15b, 1
0x18001d60e  jmp     short loc_18001D613
0x18001d610  mov     r14b, 1
0x18001d613  mov     [rsp+148h+bAlertable], 0; bAlertable
0x18001d61b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001d61f  xor     r8d, r8d; bWaitAll
0x18001d622  lea     rdx, [rsp+148h+Handles]; lpHandles
0x18001d62a  lea     ecx, [r8+1]; nCount
0x18001d62e  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d634  mov     esi, eax
0x18001d636  test    r15b, r15b
0x18001d639  jz      short loc_18001D5E4
0x18001d63b  test    esi, esi
0x18001d63d  jz      short loc_18001D65A
0x18001d63f  call    cs:__imp_GetLastError
0x18001d645  test    eax, eax
0x18001d647  jle     short loc_18001D651
0x18001d649  movzx   eax, ax
0x18001d64c  or      eax, 80070000h
0x18001d651  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001d658  jmp     short loc_18001D682
0x18001d65a  lea     rdx, [rsp+148h+Reply]; Reply
0x18001d65f  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001d667  call    cs:__imp_RpcAsyncCompleteCall
0x18001d66d  test    eax, eax
0x18001d66f  jz      short loc_18001D6A1
0x18001d671  jle     short loc_18001D67B
0x18001d673  movzx   eax, ax
0x18001d676  or      eax, 80070000h
0x18001d67b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001d682  mov     r8d, 258h; unsigned int
0x18001d688  mov     [rsp+148h+Reply], eax
0x18001d68c  mov     [rsp+148h+bAlertable], eax
0x18001d690  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d697  mov     ecx, 2; unsigned __int8
0x18001d69c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d6a1  mov     rcx, qword ptr [rsp+148h+pAsync.u]; hObject
0x18001d6a9  test    rcx, rcx
0x18001d6ac  jz      short loc_18001D6B4
0x18001d6ae  call    cs:__imp_CloseHandle
0x18001d6b4  test    r15b, r15b
0x18001d6b7  jz      short loc_18001D6F1
0x18001d6b9  mov     [rsp+148h+Reply], 800705B4h
0x18001d6c1  lea     rdx, [rsp+148h+var_D4]
0x18001d6c6  call    ??$RPCCallTimedOut@AEAY0BO@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BO@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[30],ulong &>(char const (&)[30],ulong &)
0x18001d6cb  mov     eax, [rsp+148h+Reply]
0x18001d6cf  mov     [rsp+148h+bAlertable], eax
0x18001d6d3  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001d6da  mov     r8d, 258h; unsigned int
0x18001d6e0  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d6e7  mov     ecx, 2; unsigned __int8
0x18001d6ec  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d6f1  test    r14b, r14b
0x18001d6f4  jz      short loc_18001D721
0x18001d6f6  mov     eax, 800704C7h
0x18001d6fb  mov     [rsp+148h+Reply], eax
0x18001d6ff  mov     [rsp+148h+bAlertable], eax
0x18001d703  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001d70a  mov     r8d, 258h; unsigned int
0x18001d710  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d717  mov     ecx, 2; unsigned __int8
0x18001d71c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d721  cmp     [rsp+148h+Reply], 800706B5h
0x18001d729  jz      short loc_18001D735
0x18001d72b  cmp     [rsp+148h+Reply], 800706BAh
0x18001d733  jnz     short loc_18001D73A
0x18001d735  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001d73a  lea     rcx, [rsp+148h+var_D0]; this
0x18001d73f  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001d744  mov     eax, [rsp+148h+Reply]
0x18001d748  mov     rcx, [rsp+148h+var_38]
0x18001d750  xor     rcx, rsp; StackCookie
0x18001d753  call    __security_check_cookie
0x18001d758  add     rsp, 120h
0x18001d75f  pop     r15
0x18001d761  pop     r14
0x18001d763  pop     r13
0x18001d765  pop     r12
0x18001d767  pop     rsi
0x18001d768  retn
0x180030ffe  push    rbp
0x180031000  sub     rsp, 60h
0x180031004  mov     rbp, rdx
0x180031007  mov     rcx, [rcx]
0x18003100a  mov     ecx, [rcx]; unsigned int
0x18003100c  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180031011  nop
0x180031012  add     rsp, 60h
0x180031016  pop     rbp
0x180031017  retn
```
