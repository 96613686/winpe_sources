# WLIDCCleanupIdentity(ushort const *)

- ea: `0x1800066d4`
- end: `0x180006a13`
- name: `?WLIDCCleanupIdentity@@YAJPEBG@Z`
- size: `831`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180001cb0`
- `0x1800028f0`
- `0x180002f8c`
- `0x180006304`
- `0x1800066d4`
- `0x180006a1c`
- `0x180007150`
- `0x18000730c`
- `0x180007334`
- `0x18000789c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000695a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000695a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ee`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000676a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000676a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006913`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006913`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006803`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006803`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800068b2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800068b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800067ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800067ae`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000688b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800068dd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000688b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800068dd`

## string_xrefs

- `0x1800067d3`: `RPC failed to create new event, hr = %#x`
- `0x180006927`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCCleanupIdentity(const unsigned __int16 *a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v15; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v18; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
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
LABEL_6:
    v9 = 1540;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x4Bu, 0, &pAsync, v18, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1542;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v9 = 1542;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(NotificationRoutine, &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x606u,
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
      0x606u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v18);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800066d4  push    rsi
0x1800066d6  push    r12
0x1800066d8  push    r14
0x1800066da  push    r15
0x1800066dc  sub     rsp, 0E8h
0x1800066e3  mov     rax, cs:__security_cookie
0x1800066ea  xor     rax, rsp
0x1800066ed  mov     [rsp+108h+var_38], rax
0x1800066f5  mov     r12, rcx
0x1800066f8  mov     [rsp+108h+dwMilliseconds], 0
0x180006700  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180006705  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18000670a  mov     [rsp+108h+Reply], 0
0x180006712  mov     [rsp+108h+var_C8], 0
0x18000671b  lea     rcx, [rsp+108h+var_C8]; this
0x180006720  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180006725  mov     [rsp+108h+Reply], eax
0x180006729  test    eax, eax
0x18000672b  js      loc_1800069F4
0x180006731  xor     edx, edx; Val
0x180006733  lea     r8d, [rdx+70h]; Size
0x180006737  lea     rcx, [rsp+108h+pAsync]; void *
0x18000673c  call    memset_0
0x180006741  mov     esi, [rsp+108h+dwMilliseconds]
0x180006745  mov     [rsp+108h+dwMilliseconds], esi
0x180006749  mov     [rsp+108h+var_CC], esi
0x18000674d  xor     r15b, r15b
0x180006750  mov     [rsp+108h+var_D4], r15b
0x180006755  xor     r14b, r14b
0x180006758  xorps   xmm0, xmm0
0x18000675b  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180006760  mov     edx, 70h ; 'p'; Size
0x180006765  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18000676a  call    cs:__imp_RpcAsyncInitializeHandle
0x180006770  test    eax, eax
0x180006772  jz      short loc_180006790
0x180006774  jle     short loc_18000677E
0x180006776  movzx   eax, ax
0x180006779  or      eax, 80070000h
0x18000677e  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180006785  mov     r8d, 604h
0x18000678b  jmp     loc_180006934
0x180006790  mov     [rsp+108h+pAsync.UserInfo], 0
0x180006799  mov     [rsp+108h+pAsync.NotificationType], 1
0x1800067a4  xor     r9d, r9d; lpName
0x1800067a7  xor     r8d, r8d; bInitialState
0x1800067aa  xor     edx, edx; bManualReset
0x1800067ac  xor     ecx, ecx; lpEventAttributes
0x1800067ae  call    cs:__imp_CreateEventW
0x1800067b4  mov     qword ptr [rsp+108h+pAsync.u], rax
0x1800067bc  test    rax, rax
0x1800067bf  jnz     short loc_1800067DC
0x1800067c1  call    cs:__imp_GetLastError
0x1800067c7  test    eax, eax
0x1800067c9  jle     short loc_1800067D3
0x1800067cb  movzx   eax, ax
0x1800067ce  or      eax, 80070000h
0x1800067d3  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800067da  jmp     short loc_180006785
0x1800067dc  mov     [rsp+108h+Handles], rax
0x1800067e1  mov     [rsp+108h+var_E0], r12
0x1800067e6  mov     rax, [rsp+108h+var_C8]
0x1800067eb  mov     qword ptr [rsp+108h+bAlertable], rax
0x1800067f0  lea     r9, [rsp+108h+pAsync]
0x1800067f5  xor     r8d, r8d; pReturnValue
0x1800067f8  lea     edx, [r8+4Bh]; nProcNum
0x1800067fc  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006803  call    cs:__imp_Ndr64AsyncClientCall
0x180006809  mov     eax, [rsp+108h+Reply]
0x18000680d  jmp     short loc_18000685E
0x18000680f  test    eax, eax
0x180006811  jle     short loc_18000681B
0x180006813  movzx   eax, ax
0x180006816  or      eax, 80070000h
0x18000681b  mov     [rsp+108h+Reply], eax
0x18000681f  mov     [rsp+108h+bAlertable], eax
0x180006823  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18000682a  mov     r8d, 606h; unsigned int
0x180006830  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006837  mov     ecx, 2; unsigned __int8
0x18000683c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006841  mov     eax, [rsp+108h+Reply]
0x180006845  test    eax, eax
0x180006847  js      short loc_180006852
0x180006849  mov     eax, 8000FFFFh
0x18000684e  mov     [rsp+108h+Reply], eax
0x180006852  mov     esi, [rsp+108h+dwMilliseconds]
0x180006856  mov     r15b, [rsp+108h+var_D4]
0x18000685b  mov     r14b, r15b
0x18000685e  test    eax, eax
0x180006860  jns     short loc_180006874
0x180006862  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180006869  mov     r8d, 606h
0x18000686f  jmp     loc_180006938
0x180006874  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18000687c  mov     r9d, esi; dwMilliseconds
0x18000687f  xor     r8d, r8d; bWaitAll
0x180006882  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180006887  lea     ecx, [r8+1]; nCount
0x18000688b  call    cs:__imp_WaitForMultipleObjectsEx
0x180006891  mov     esi, eax
0x180006893  mov     r12d, 102h
0x180006899  test    r14b, r14b
0x18000689c  jnz     short loc_1800068EA
0x18000689e  cmp     esi, r12d
0x1800068a1  jz      short loc_1800068A8
0x1800068a3  cmp     esi, 1
0x1800068a6  jnz     short loc_1800068EA
0x1800068a8  mov     edx, 1; fAbort
0x1800068ad  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800068b2  call    cs:__imp_RpcAsyncCancelCall
0x1800068b8  cmp     esi, r12d
0x1800068bb  jnz     short loc_1800068C2
0x1800068bd  mov     r15b, 1
0x1800068c0  jmp     short loc_1800068C5
0x1800068c2  mov     r14b, 1
0x1800068c5  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800068cd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800068d1  xor     r8d, r8d; bWaitAll
0x1800068d4  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800068d9  lea     ecx, [r8+1]; nCount
0x1800068dd  call    cs:__imp_WaitForMultipleObjectsEx
0x1800068e3  mov     esi, eax
0x1800068e5  test    r15b, r15b
0x1800068e8  jz      short loc_180006899
0x1800068ea  test    esi, esi
0x1800068ec  jz      short loc_180006909
0x1800068ee  call    cs:__imp_GetLastError
0x1800068f4  test    eax, eax
0x1800068f6  jle     short loc_180006900
0x1800068f8  movzx   eax, ax
0x1800068fb  or      eax, 80070000h
0x180006900  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180006907  jmp     short loc_18000692E
0x180006909  lea     rdx, [rsp+108h+Reply]; Reply
0x18000690e  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180006913  call    cs:__imp_RpcAsyncCompleteCall
0x180006919  test    eax, eax
0x18000691b  jz      short loc_18000694D
0x18000691d  jle     short loc_180006927
0x18000691f  movzx   eax, ax
0x180006922  or      eax, 80070000h
0x180006927  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18000692e  mov     r8d, 606h; unsigned int
0x180006934  mov     [rsp+108h+Reply], eax
0x180006938  mov     [rsp+108h+bAlertable], eax
0x18000693c  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006943  mov     ecx, 2; unsigned __int8
0x180006948  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000694d  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180006955  test    rcx, rcx
0x180006958  jz      short loc_180006960
0x18000695a  call    cs:__imp_CloseHandle
0x180006960  test    r15b, r15b
0x180006963  jz      short loc_18000699D
0x180006965  mov     [rsp+108h+Reply], 800705B4h
0x18000696d  lea     rdx, [rsp+108h+var_CC]
0x180006972  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x180006977  mov     eax, [rsp+108h+Reply]
0x18000697b  mov     [rsp+108h+bAlertable], eax
0x18000697f  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180006986  mov     r8d, 606h; unsigned int
0x18000698c  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006993  mov     ecx, 2; unsigned __int8
0x180006998  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000699d  test    r14b, r14b
0x1800069a0  jz      short loc_1800069CD
0x1800069a2  mov     eax, 800704C7h
0x1800069a7  mov     [rsp+108h+Reply], eax
0x1800069ab  mov     [rsp+108h+bAlertable], eax
0x1800069af  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800069b6  mov     r8d, 606h; unsigned int
0x1800069bc  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800069c3  mov     ecx, 2; unsigned __int8
0x1800069c8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800069cd  cmp     [rsp+108h+Reply], 800706B5h
0x1800069d5  jz      short loc_1800069E1
0x1800069d7  cmp     [rsp+108h+Reply], 800706BAh
0x1800069df  jnz     short loc_1800069E6
0x1800069e1  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800069e6  lea     rcx, [rsp+108h+var_C8]; this
0x1800069eb  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800069f0  mov     eax, [rsp+108h+Reply]
0x1800069f4  mov     rcx, [rsp+108h+var_38]
0x1800069fc  xor     rcx, rsp; StackCookie
0x1800069ff  call    __security_check_cookie
0x180006a04  add     rsp, 0E8h
0x180006a0b  pop     r15
0x180006a0d  pop     r14
0x180006a0f  pop     r12
0x180006a11  pop     rsi
0x180006a12  retn
0x180008d5e  push    rbp
0x180008d60  sub     rsp, 30h
0x180008d64  mov     rbp, rdx
0x180008d67  mov     rcx, [rcx]
0x180008d6a  mov     ecx, [rcx]; unsigned int
0x180008d6c  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180008d71  nop
0x180008d72  add     rsp, 30h
0x180008d76  pop     rbp
0x180008d77  retn
```
