# WLIDCRegisterUserIdkey(ushort const *,ushort const *,ushort const *,int,unsigned __int64)

- ea: `0x180021514`
- end: `0x1800218a1`
- name: `?WLIDCRegisterUserIdkey@@YAJPEBG00H_K@Z`
- size: `909`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800198f0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019e38`
- `0x18001ba00`
- `0x180020750`
- `0x180021514`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002170a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002175f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002170a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002175f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021606`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217df`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180021682`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180021682`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021798`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021798`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800215bf`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800215bf`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021734`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021734`

## string_xrefs

- `0x18002162b`: `RPC failed to create new event, hr = %#x`
- `0x1800217ac`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRegisterUserIdkey(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int64 a5)
{
  __int64 result; // rax
  DWORD v8; // esi
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v18; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  int v20; // [rsp+5Ch] [rbp-DCh]
  DWORD v21; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-D0h] BYREF
  const unsigned __int16 *v23; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v20 = a4;
  v23 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v21 = dwMilliseconds;
  v9 = 0;
  v18 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v13 = 1377;
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
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x42u, 0, &pAsync, v22, a1, a2, v23, v20, a5);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 1386;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v13,
      v12,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v15 = WaitForMultipleObjectsEx(1u, Handles, 0, v8, 0);
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
LABEL_29:
    v13 = 1386;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCRegisterUserIdkey",
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x56Au,
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
      0x56Au,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v22);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180021514  push    rsi
0x180021516  push    r12
0x180021518  push    r13
0x18002151a  push    r14
0x18002151c  push    r15
0x18002151e  sub     rsp, 110h
0x180021525  mov     rax, cs:__security_cookie
0x18002152c  xor     rax, rsp
0x18002152f  mov     [rsp+138h+var_38], rax
0x180021537  mov     [rsp+138h+var_DC], r9d
0x18002153c  mov     [rsp+138h+var_C8], r8
0x180021541  mov     r13, rdx
0x180021544  mov     r12, rcx
0x180021547  mov     [rsp+138h+dwMilliseconds], 0
0x18002154f  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x180021554  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180021559  mov     [rsp+138h+Reply], 0
0x180021561  mov     [rsp+138h+var_D0], 0
0x18002156a  lea     rcx, [rsp+138h+var_D0]; this
0x18002156f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180021574  mov     [rsp+138h+Reply], eax
0x180021578  test    eax, eax
0x18002157a  js      loc_180021880
0x180021580  xor     edx, edx; Val
0x180021582  lea     r8d, [rdx+70h]; Size
0x180021586  lea     rcx, [rsp+138h+pAsync]; void *
0x18002158e  call    memset_0
0x180021593  mov     esi, [rsp+138h+dwMilliseconds]
0x180021597  mov     [rsp+138h+dwMilliseconds], esi
0x18002159b  mov     [rsp+138h+var_D8], esi
0x18002159f  xor     r15b, r15b
0x1800215a2  mov     [rsp+138h+var_E4], r15b
0x1800215a7  xor     r14b, r14b
0x1800215aa  xorps   xmm0, xmm0
0x1800215ad  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x1800215b2  mov     edx, 70h ; 'p'; Size
0x1800215b7  lea     rcx, [rsp+138h+pAsync]; pAsync
0x1800215bf  call    cs:__imp_RpcAsyncInitializeHandle
0x1800215c5  test    eax, eax
0x1800215c7  jz      short loc_1800215E5
0x1800215c9  jle     short loc_1800215D3
0x1800215cb  movzx   eax, ax
0x1800215ce  or      eax, 80070000h
0x1800215d3  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800215da  mov     r8d, 561h
0x1800215e0  jmp     loc_1800217B9
0x1800215e5  mov     [rsp+138h+pAsync.UserInfo], 0
0x1800215f1  mov     [rsp+138h+pAsync.NotificationType], 1
0x1800215fc  xor     r9d, r9d; lpName
0x1800215ff  xor     r8d, r8d; bInitialState
0x180021602  xor     edx, edx; bManualReset
0x180021604  xor     ecx, ecx; lpEventAttributes
0x180021606  call    cs:__imp_CreateEventW
0x18002160c  mov     qword ptr [rsp+138h+pAsync.u], rax
0x180021614  test    rax, rax
0x180021617  jnz     short loc_180021634
0x180021619  call    cs:__imp_GetLastError
0x18002161f  test    eax, eax
0x180021621  jle     short loc_18002162B
0x180021623  movzx   eax, ax
0x180021626  or      eax, 80070000h
0x18002162b  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180021632  jmp     short loc_1800215DA
0x180021634  mov     [rsp+138h+Handles], rax
0x180021639  mov     rax, [rsp+138h+arg_20]
0x180021641  mov     [rsp+138h+var_F0], rax
0x180021646  mov     eax, [rsp+138h+var_DC]
0x18002164a  mov     [rsp+138h+var_F8], eax
0x18002164e  mov     rax, [rsp+138h+var_C8]
0x180021653  mov     [rsp+138h+var_100], rax
0x180021658  mov     [rsp+138h+var_108], r13
0x18002165d  mov     [rsp+138h+var_110], r12
0x180021662  mov     rax, [rsp+138h+var_D0]
0x180021667  mov     qword ptr [rsp+138h+bAlertable], rax
0x18002166c  lea     r9, [rsp+138h+pAsync]
0x180021674  xor     r8d, r8d; pReturnValue
0x180021677  lea     edx, [r8+42h]; nProcNum
0x18002167b  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180021682  call    cs:__imp_Ndr64AsyncClientCall
0x180021688  mov     eax, [rsp+138h+Reply]
0x18002168c  jmp     short loc_1800216DD
0x18002168e  test    eax, eax
0x180021690  jle     short loc_18002169A
0x180021692  movzx   eax, ax
0x180021695  or      eax, 80070000h
0x18002169a  mov     [rsp+138h+Reply], eax
0x18002169e  mov     [rsp+138h+bAlertable], eax
0x1800216a2  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x1800216a9  mov     r8d, 56Ah; unsigned int
0x1800216af  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800216b6  mov     ecx, 2; unsigned __int8
0x1800216bb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800216c0  mov     eax, [rsp+138h+Reply]
0x1800216c4  test    eax, eax
0x1800216c6  js      short loc_1800216D1
0x1800216c8  mov     eax, 8000FFFFh
0x1800216cd  mov     [rsp+138h+Reply], eax
0x1800216d1  mov     esi, [rsp+138h+dwMilliseconds]
0x1800216d5  mov     r15b, [rsp+138h+var_E4]
0x1800216da  mov     r14b, r15b
0x1800216dd  test    eax, eax
0x1800216df  jns     short loc_1800216F3
0x1800216e1  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800216e8  mov     r8d, 56Ah
0x1800216ee  jmp     loc_1800217BD
0x1800216f3  mov     [rsp+138h+bAlertable], 0; bAlertable
0x1800216fb  mov     r9d, esi; dwMilliseconds
0x1800216fe  xor     r8d, r8d; bWaitAll
0x180021701  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180021706  lea     ecx, [r8+1]; nCount
0x18002170a  call    cs:__imp_WaitForMultipleObjectsEx
0x180021710  mov     esi, eax
0x180021712  mov     r12d, 102h
0x180021718  test    r14b, r14b
0x18002171b  jnz     short loc_18002176C
0x18002171d  cmp     esi, r12d
0x180021720  jz      short loc_180021727
0x180021722  cmp     esi, 1
0x180021725  jnz     short loc_18002176C
0x180021727  mov     edx, 1; fAbort
0x18002172c  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180021734  call    cs:__imp_RpcAsyncCancelCall
0x18002173a  cmp     esi, r12d
0x18002173d  jnz     short loc_180021744
0x18002173f  mov     r15b, 1
0x180021742  jmp     short loc_180021747
0x180021744  mov     r14b, 1
0x180021747  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18002174f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180021753  xor     r8d, r8d; bWaitAll
0x180021756  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18002175b  lea     ecx, [r8+1]; nCount
0x18002175f  call    cs:__imp_WaitForMultipleObjectsEx
0x180021765  mov     esi, eax
0x180021767  test    r15b, r15b
0x18002176a  jz      short loc_180021718
0x18002176c  test    esi, esi
0x18002176e  jz      short loc_18002178B
0x180021770  call    cs:__imp_GetLastError
0x180021776  test    eax, eax
0x180021778  jle     short loc_180021782
0x18002177a  movzx   eax, ax
0x18002177d  or      eax, 80070000h
0x180021782  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180021789  jmp     short loc_1800217B3
0x18002178b  lea     rdx, [rsp+138h+Reply]; Reply
0x180021790  lea     rcx, [rsp+138h+pAsync]; pAsync
0x180021798  call    cs:__imp_RpcAsyncCompleteCall
0x18002179e  test    eax, eax
0x1800217a0  jz      short loc_1800217D2
0x1800217a2  jle     short loc_1800217AC
0x1800217a4  movzx   eax, ax
0x1800217a7  or      eax, 80070000h
0x1800217ac  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800217b3  mov     r8d, 56Ah; unsigned int
0x1800217b9  mov     [rsp+138h+Reply], eax
0x1800217bd  mov     [rsp+138h+bAlertable], eax
0x1800217c1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800217c8  mov     ecx, 2; unsigned __int8
0x1800217cd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800217d2  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x1800217da  test    rcx, rcx
0x1800217dd  jz      short loc_1800217E5
0x1800217df  call    cs:__imp_CloseHandle
0x1800217e5  test    r15b, r15b
0x1800217e8  jz      short loc_180021829
0x1800217ea  mov     [rsp+138h+Reply], 800705B4h
0x1800217f2  lea     rdx, [rsp+138h+var_D8]
0x1800217f7  lea     rcx, aWlidcregisteru; "WLIDCRegisterUserIdkey"
0x1800217fe  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x180021803  mov     eax, [rsp+138h+Reply]
0x180021807  mov     [rsp+138h+bAlertable], eax
0x18002180b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180021812  mov     r8d, 56Ah; unsigned int
0x180021818  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002181f  mov     ecx, 2; unsigned __int8
0x180021824  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021829  test    r14b, r14b
0x18002182c  jz      short loc_180021859
0x18002182e  mov     eax, 800704C7h
0x180021833  mov     [rsp+138h+Reply], eax
0x180021837  mov     [rsp+138h+bAlertable], eax
0x18002183b  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180021842  mov     r8d, 56Ah; unsigned int
0x180021848  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002184f  mov     ecx, 2; unsigned __int8
0x180021854  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021859  cmp     [rsp+138h+Reply], 800706B5h
0x180021861  jz      short loc_18002186D
0x180021863  cmp     [rsp+138h+Reply], 800706BAh
0x18002186b  jnz     short loc_180021872
0x18002186d  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180021872  lea     rcx, [rsp+138h+var_D0]; this
0x180021877  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18002187c  mov     eax, [rsp+138h+Reply]
0x180021880  mov     rcx, [rsp+138h+var_38]
0x180021888  xor     rcx, rsp; StackCookie
0x18002188b  call    __security_check_cookie
0x180021890  add     rsp, 110h
0x180021897  pop     r15
0x180021899  pop     r14
0x18002189b  pop     r13
0x18002189d  pop     r12
0x18002189f  pop     rsi
0x1800218a0  retn
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
