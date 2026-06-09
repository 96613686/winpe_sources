# WLIDCGetConfigString(ushort const *,ushort * *)

- ea: `0x18001e838`
- end: `0x18001eb9c`
- name: `?WLIDCGetConfigString@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019730`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001e838`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ea02`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ea54`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ea02`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ea54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e920`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ead1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ead1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e97a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e97a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ea8a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ea8a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e8d9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e8d9`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ea29`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ea29`

## string_xrefs

- `0x18001e945`: `RPC failed to create new event, hr = %#x`
- `0x18001ea9e`: `RPC Async complete call failed, hr = %#x`
- `0x18001eae9`: `WLIDCGetConfigString`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v15; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v17 = dwMilliseconds;
  v6 = 0;
  v15 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1226;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x33u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1228;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v10,
      v9,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
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
LABEL_29:
    v10 = 1228;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetConfigString",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4CCu,
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
      0x4CCu,
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
0x18001e838  mov     [rsp+arg_10], rsi
0x18001e83d  mov     [rsp+arg_18], r12
0x18001e842  push    r13
0x18001e844  push    r14
0x18001e846  push    r15
0x18001e848  sub     rsp, 0F0h
0x18001e84f  mov     rax, cs:__security_cookie
0x18001e856  xor     rax, rsp
0x18001e859  mov     [rsp+108h+var_28], rax
0x18001e861  mov     r13, rdx
0x18001e864  mov     r12, rcx
0x18001e867  mov     [rsp+108h+dwMilliseconds], 0
0x18001e86f  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001e874  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001e879  mov     [rsp+108h+Reply], 0
0x18001e881  mov     [rsp+108h+var_B8], 0
0x18001e88a  lea     rcx, [rsp+108h+var_B8]; this
0x18001e88f  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001e894  mov     [rsp+108h+Reply], eax
0x18001e898  test    eax, eax
0x18001e89a  js      loc_18001EB72
0x18001e8a0  xor     edx, edx; Val
0x18001e8a2  lea     r8d, [rdx+70h]; Size
0x18001e8a6  lea     rcx, [rsp+108h+pAsync]; void *
0x18001e8ab  call    memset_0
0x18001e8b0  mov     esi, [rsp+108h+dwMilliseconds]
0x18001e8b4  mov     [rsp+108h+dwMilliseconds], esi
0x18001e8b8  mov     [rsp+108h+var_BC], esi
0x18001e8bc  xor     r15b, r15b
0x18001e8bf  mov     [rsp+108h+var_C4], r15b
0x18001e8c4  xor     r14b, r14b
0x18001e8c7  xorps   xmm0, xmm0
0x18001e8ca  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001e8cf  mov     edx, 70h ; 'p'; Size
0x18001e8d4  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001e8d9  call    cs:__imp_RpcAsyncInitializeHandle
0x18001e8df  test    eax, eax
0x18001e8e1  jz      short loc_18001E8FF
0x18001e8e3  jle     short loc_18001E8ED
0x18001e8e5  movzx   eax, ax
0x18001e8e8  or      eax, 80070000h
0x18001e8ed  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001e8f4  mov     r8d, 4CAh
0x18001e8fa  jmp     loc_18001EAAB
0x18001e8ff  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001e90b  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001e916  xor     r9d, r9d; lpName
0x18001e919  xor     r8d, r8d; bInitialState
0x18001e91c  xor     edx, edx; bManualReset
0x18001e91e  xor     ecx, ecx; lpEventAttributes
0x18001e920  call    cs:__imp_CreateEventW
0x18001e926  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001e92e  test    rax, rax
0x18001e931  jnz     short loc_18001E94E
0x18001e933  call    cs:__imp_GetLastError
0x18001e939  test    eax, eax
0x18001e93b  jle     short loc_18001E945
0x18001e93d  movzx   eax, ax
0x18001e940  or      eax, 80070000h
0x18001e945  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001e94c  jmp     short loc_18001E8F4
0x18001e94e  mov     [rsp+108h+Handles], rax
0x18001e953  mov     [rsp+108h+var_D8], r13
0x18001e958  mov     [rsp+108h+var_E0], r12
0x18001e95d  mov     rax, [rsp+108h+var_B8]
0x18001e962  mov     qword ptr [rsp+108h+bAlertable], rax
0x18001e967  lea     r9, [rsp+108h+pAsync]
0x18001e96c  xor     r8d, r8d; pReturnValue
0x18001e96f  lea     edx, [r8+33h]; nProcNum
0x18001e973  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001e97a  call    cs:__imp_Ndr64AsyncClientCall
0x18001e980  mov     eax, [rsp+108h+Reply]
0x18001e984  jmp     short loc_18001E9D5
0x18001e986  test    eax, eax
0x18001e988  jle     short loc_18001E992
0x18001e98a  movzx   eax, ax
0x18001e98d  or      eax, 80070000h
0x18001e992  mov     [rsp+108h+Reply], eax
0x18001e996  mov     [rsp+108h+bAlertable], eax
0x18001e99a  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001e9a1  mov     r8d, 4CCh; unsigned int
0x18001e9a7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e9ae  mov     ecx, 2; unsigned __int8
0x18001e9b3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e9b8  mov     eax, [rsp+108h+Reply]
0x18001e9bc  test    eax, eax
0x18001e9be  js      short loc_18001E9C9
0x18001e9c0  mov     eax, 8000FFFFh
0x18001e9c5  mov     [rsp+108h+Reply], eax
0x18001e9c9  mov     esi, [rsp+108h+dwMilliseconds]
0x18001e9cd  mov     r15b, [rsp+108h+var_C4]
0x18001e9d2  mov     r14b, r15b
0x18001e9d5  test    eax, eax
0x18001e9d7  jns     short loc_18001E9EB
0x18001e9d9  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001e9e0  mov     r8d, 4CCh
0x18001e9e6  jmp     loc_18001EAAF
0x18001e9eb  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001e9f3  mov     r9d, esi; dwMilliseconds
0x18001e9f6  xor     r8d, r8d; bWaitAll
0x18001e9f9  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001e9fe  lea     ecx, [r8+1]; nCount
0x18001ea02  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ea08  mov     esi, eax
0x18001ea0a  mov     r12d, 102h
0x18001ea10  test    r14b, r14b
0x18001ea13  jnz     short loc_18001EA61
0x18001ea15  cmp     esi, r12d
0x18001ea18  jz      short loc_18001EA1F
0x18001ea1a  cmp     esi, 1
0x18001ea1d  jnz     short loc_18001EA61
0x18001ea1f  mov     edx, 1; fAbort
0x18001ea24  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ea29  call    cs:__imp_RpcAsyncCancelCall
0x18001ea2f  cmp     esi, r12d
0x18001ea32  jnz     short loc_18001EA39
0x18001ea34  mov     r15b, 1
0x18001ea37  jmp     short loc_18001EA3C
0x18001ea39  mov     r14b, 1
0x18001ea3c  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001ea44  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001ea48  xor     r8d, r8d; bWaitAll
0x18001ea4b  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001ea50  lea     ecx, [r8+1]; nCount
0x18001ea54  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ea5a  mov     esi, eax
0x18001ea5c  test    r15b, r15b
0x18001ea5f  jz      short loc_18001EA10
0x18001ea61  test    esi, esi
0x18001ea63  jz      short loc_18001EA80
0x18001ea65  call    cs:__imp_GetLastError
0x18001ea6b  test    eax, eax
0x18001ea6d  jle     short loc_18001EA77
0x18001ea6f  movzx   eax, ax
0x18001ea72  or      eax, 80070000h
0x18001ea77  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001ea7e  jmp     short loc_18001EAA5
0x18001ea80  lea     rdx, [rsp+108h+Reply]; Reply
0x18001ea85  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ea8a  call    cs:__imp_RpcAsyncCompleteCall
0x18001ea90  test    eax, eax
0x18001ea92  jz      short loc_18001EAC4
0x18001ea94  jle     short loc_18001EA9E
0x18001ea96  movzx   eax, ax
0x18001ea99  or      eax, 80070000h
0x18001ea9e  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001eaa5  mov     r8d, 4CCh; unsigned int
0x18001eaab  mov     [rsp+108h+Reply], eax
0x18001eaaf  mov     [rsp+108h+bAlertable], eax
0x18001eab3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001eaba  mov     ecx, 2; unsigned __int8
0x18001eabf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001eac4  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001eacc  test    rcx, rcx
0x18001eacf  jz      short loc_18001EAD7
0x18001ead1  call    cs:__imp_CloseHandle
0x18001ead7  test    r15b, r15b
0x18001eada  jz      short loc_18001EB1B
0x18001eadc  mov     [rsp+108h+Reply], 800705B4h
0x18001eae4  lea     rdx, [rsp+108h+var_BC]
0x18001eae9  lea     rcx, aWlidcgetconfig; "WLIDCGetConfigString"
0x18001eaf0  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001eaf5  mov     eax, [rsp+108h+Reply]
0x18001eaf9  mov     [rsp+108h+bAlertable], eax
0x18001eafd  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001eb04  mov     r8d, 4CCh; unsigned int
0x18001eb0a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001eb11  mov     ecx, 2; unsigned __int8
0x18001eb16  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001eb1b  test    r14b, r14b
0x18001eb1e  jz      short loc_18001EB4B
0x18001eb20  mov     eax, 800704C7h
0x18001eb25  mov     [rsp+108h+Reply], eax
0x18001eb29  mov     [rsp+108h+bAlertable], eax
0x18001eb2d  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001eb34  mov     r8d, 4CCh; unsigned int
0x18001eb3a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001eb41  mov     ecx, 2; unsigned __int8
0x18001eb46  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001eb4b  cmp     [rsp+108h+Reply], 800706B5h
0x18001eb53  jz      short loc_18001EB5F
0x18001eb55  cmp     [rsp+108h+Reply], 800706BAh
0x18001eb5d  jnz     short loc_18001EB64
0x18001eb5f  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001eb64  lea     rcx, [rsp+108h+var_B8]; this
0x18001eb69  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001eb6e  mov     eax, [rsp+108h+Reply]
0x18001eb72  mov     rcx, [rsp+108h+var_28]
0x18001eb7a  xor     rcx, rsp; StackCookie
0x18001eb7d  call    __security_check_cookie
0x18001eb82  lea     r11, [rsp+108h+var_18]
0x18001eb8a  mov     rsi, [r11+30h]
0x18001eb8e  mov     r12, [r11+38h]
0x18001eb92  mov     rsp, r11
0x18001eb95  pop     r15
0x18001eb97  pop     r14
0x18001eb99  pop     r13
0x18001eb9b  retn
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
