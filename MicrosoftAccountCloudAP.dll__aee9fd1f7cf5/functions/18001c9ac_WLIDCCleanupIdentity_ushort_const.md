# WLIDCCleanupIdentity(ushort const *)

- ea: `0x18001c9ac`
- end: `0x18001ccf2`
- name: `?WLIDCCleanupIdentity@@YAJPEBG@Z`
- size: `838`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019610`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001c9ac`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cb63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cbb5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cb63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001cbb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cbc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc32`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001cadb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001cadb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cbeb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001cbeb`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ca42`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ca42`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001cb8a`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001cb8a`

## string_xrefs

- `0x18001caab`: `RPC failed to create new event, hr = %#x`
- `0x18001cbff`: `RPC Async complete call failed, hr = %#x`

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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x4Bu, 0, &pAsync, v17, a1);
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCCleanupIdentity",
      (int *)&v16);
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
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18001c9ac  push    rsi
0x18001c9ae  push    r12
0x18001c9b0  push    r14
0x18001c9b2  push    r15
0x18001c9b4  sub     rsp, 0E8h
0x18001c9bb  mov     rax, cs:__security_cookie
0x18001c9c2  xor     rax, rsp
0x18001c9c5  mov     [rsp+108h+var_38], rax
0x18001c9cd  mov     r12, rcx
0x18001c9d0  mov     [rsp+108h+dwMilliseconds], 0
0x18001c9d8  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001c9dd  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001c9e2  mov     [rsp+108h+Reply], 0
0x18001c9ea  mov     [rsp+108h+var_C8], 0
0x18001c9f3  lea     rcx, [rsp+108h+var_C8]; this
0x18001c9f8  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001c9fd  mov     [rsp+108h+Reply], eax
0x18001ca01  test    eax, eax
0x18001ca03  js      loc_18001CCD3
0x18001ca09  xor     edx, edx; Val
0x18001ca0b  lea     r8d, [rdx+70h]; Size
0x18001ca0f  lea     rcx, [rsp+108h+pAsync]; void *
0x18001ca14  call    memset_0
0x18001ca19  mov     esi, [rsp+108h+dwMilliseconds]
0x18001ca1d  mov     [rsp+108h+dwMilliseconds], esi
0x18001ca21  mov     [rsp+108h+var_CC], esi
0x18001ca25  xor     r15b, r15b
0x18001ca28  mov     [rsp+108h+var_D4], r15b
0x18001ca2d  xor     r14b, r14b
0x18001ca30  xorps   xmm0, xmm0
0x18001ca33  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001ca38  mov     edx, 70h ; 'p'; Size
0x18001ca3d  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ca42  call    cs:__imp_RpcAsyncInitializeHandle
0x18001ca48  test    eax, eax
0x18001ca4a  jz      short loc_18001CA68
0x18001ca4c  jle     short loc_18001CA56
0x18001ca4e  movzx   eax, ax
0x18001ca51  or      eax, 80070000h
0x18001ca56  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001ca5d  mov     r8d, 604h
0x18001ca63  jmp     loc_18001CC0C
0x18001ca68  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001ca71  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001ca7c  xor     r9d, r9d; lpName
0x18001ca7f  xor     r8d, r8d; bInitialState
0x18001ca82  xor     edx, edx; bManualReset
0x18001ca84  xor     ecx, ecx; lpEventAttributes
0x18001ca86  call    cs:__imp_CreateEventW
0x18001ca8c  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001ca94  test    rax, rax
0x18001ca97  jnz     short loc_18001CAB4
0x18001ca99  call    cs:__imp_GetLastError
0x18001ca9f  test    eax, eax
0x18001caa1  jle     short loc_18001CAAB
0x18001caa3  movzx   eax, ax
0x18001caa6  or      eax, 80070000h
0x18001caab  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001cab2  jmp     short loc_18001CA5D
0x18001cab4  mov     [rsp+108h+Handles], rax
0x18001cab9  mov     [rsp+108h+var_E0], r12
0x18001cabe  mov     rax, [rsp+108h+var_C8]
0x18001cac3  mov     qword ptr [rsp+108h+bAlertable], rax
0x18001cac8  lea     r9, [rsp+108h+pAsync]
0x18001cacd  xor     r8d, r8d; pReturnValue
0x18001cad0  lea     edx, [r8+4Bh]; nProcNum
0x18001cad4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001cadb  call    cs:__imp_Ndr64AsyncClientCall
0x18001cae1  mov     eax, [rsp+108h+Reply]
0x18001cae5  jmp     short loc_18001CB36
0x18001cae7  test    eax, eax
0x18001cae9  jle     short loc_18001CAF3
0x18001caeb  movzx   eax, ax
0x18001caee  or      eax, 80070000h
0x18001caf3  mov     [rsp+108h+Reply], eax
0x18001caf7  mov     [rsp+108h+bAlertable], eax
0x18001cafb  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001cb02  mov     r8d, 606h; unsigned int
0x18001cb08  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cb0f  mov     ecx, 2; unsigned __int8
0x18001cb14  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cb19  mov     eax, [rsp+108h+Reply]
0x18001cb1d  test    eax, eax
0x18001cb1f  js      short loc_18001CB2A
0x18001cb21  mov     eax, 8000FFFFh
0x18001cb26  mov     [rsp+108h+Reply], eax
0x18001cb2a  mov     esi, [rsp+108h+dwMilliseconds]
0x18001cb2e  mov     r15b, [rsp+108h+var_D4]
0x18001cb33  mov     r14b, r15b
0x18001cb36  test    eax, eax
0x18001cb38  jns     short loc_18001CB4C
0x18001cb3a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001cb41  mov     r8d, 606h
0x18001cb47  jmp     loc_18001CC10
0x18001cb4c  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001cb54  mov     r9d, esi; dwMilliseconds
0x18001cb57  xor     r8d, r8d; bWaitAll
0x18001cb5a  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001cb5f  lea     ecx, [r8+1]; nCount
0x18001cb63  call    cs:__imp_WaitForMultipleObjectsEx
0x18001cb69  mov     esi, eax
0x18001cb6b  mov     r12d, 102h
0x18001cb71  test    r14b, r14b
0x18001cb74  jnz     short loc_18001CBC2
0x18001cb76  cmp     esi, r12d
0x18001cb79  jz      short loc_18001CB80
0x18001cb7b  cmp     esi, 1
0x18001cb7e  jnz     short loc_18001CBC2
0x18001cb80  mov     edx, 1; fAbort
0x18001cb85  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001cb8a  call    cs:__imp_RpcAsyncCancelCall
0x18001cb90  cmp     esi, r12d
0x18001cb93  jnz     short loc_18001CB9A
0x18001cb95  mov     r15b, 1
0x18001cb98  jmp     short loc_18001CB9D
0x18001cb9a  mov     r14b, 1
0x18001cb9d  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001cba5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001cba9  xor     r8d, r8d; bWaitAll
0x18001cbac  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001cbb1  lea     ecx, [r8+1]; nCount
0x18001cbb5  call    cs:__imp_WaitForMultipleObjectsEx
0x18001cbbb  mov     esi, eax
0x18001cbbd  test    r15b, r15b
0x18001cbc0  jz      short loc_18001CB71
0x18001cbc2  test    esi, esi
0x18001cbc4  jz      short loc_18001CBE1
0x18001cbc6  call    cs:__imp_GetLastError
0x18001cbcc  test    eax, eax
0x18001cbce  jle     short loc_18001CBD8
0x18001cbd0  movzx   eax, ax
0x18001cbd3  or      eax, 80070000h
0x18001cbd8  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001cbdf  jmp     short loc_18001CC06
0x18001cbe1  lea     rdx, [rsp+108h+Reply]; Reply
0x18001cbe6  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001cbeb  call    cs:__imp_RpcAsyncCompleteCall
0x18001cbf1  test    eax, eax
0x18001cbf3  jz      short loc_18001CC25
0x18001cbf5  jle     short loc_18001CBFF
0x18001cbf7  movzx   eax, ax
0x18001cbfa  or      eax, 80070000h
0x18001cbff  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001cc06  mov     r8d, 606h; unsigned int
0x18001cc0c  mov     [rsp+108h+Reply], eax
0x18001cc10  mov     [rsp+108h+bAlertable], eax
0x18001cc14  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cc1b  mov     ecx, 2; unsigned __int8
0x18001cc20  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cc25  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001cc2d  test    rcx, rcx
0x18001cc30  jz      short loc_18001CC38
0x18001cc32  call    cs:__imp_CloseHandle
0x18001cc38  test    r15b, r15b
0x18001cc3b  jz      short loc_18001CC7C
0x18001cc3d  mov     [rsp+108h+Reply], 800705B4h
0x18001cc45  lea     rdx, [rsp+108h+var_CC]
0x18001cc4a  lea     rcx, aWlidccleanupid; "WLIDCCleanupIdentity"
0x18001cc51  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001cc56  mov     eax, [rsp+108h+Reply]
0x18001cc5a  mov     [rsp+108h+bAlertable], eax
0x18001cc5e  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001cc65  mov     r8d, 606h; unsigned int
0x18001cc6b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cc72  mov     ecx, 2; unsigned __int8
0x18001cc77  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001cc7c  test    r14b, r14b
0x18001cc7f  jz      short loc_18001CCAC
0x18001cc81  mov     eax, 800704C7h
0x18001cc86  mov     [rsp+108h+Reply], eax
0x18001cc8a  mov     [rsp+108h+bAlertable], eax
0x18001cc8e  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001cc95  mov     r8d, 606h; unsigned int
0x18001cc9b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001cca2  mov     ecx, 2; unsigned __int8
0x18001cca7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ccac  cmp     [rsp+108h+Reply], 800706B5h
0x18001ccb4  jz      short loc_18001CCC0
0x18001ccb6  cmp     [rsp+108h+Reply], 800706BAh
0x18001ccbe  jnz     short loc_18001CCC5
0x18001ccc0  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001ccc5  lea     rcx, [rsp+108h+var_C8]; this
0x18001ccca  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001cccf  mov     eax, [rsp+108h+Reply]
0x18001ccd3  mov     rcx, [rsp+108h+var_38]
0x18001ccdb  xor     rcx, rsp; StackCookie
0x18001ccde  call    __security_check_cookie
0x18001cce3  add     rsp, 0E8h
0x18001ccea  pop     r15
0x18001ccec  pop     r14
0x18001ccee  pop     r12
0x18001ccf0  pop     rsi
0x18001ccf1  retn
0x180030717  push    rbp
0x180030719  sub     rsp, 30h
0x18003071d  mov     rbp, rdx
0x180030720  mov     rcx, [rcx]
0x180030723  mov     ecx, [rcx]; unsigned int
0x180030725  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x18003072a  nop
0x18003072b  add     rsp, 30h
0x18003072f  pop     rbp
0x180030730  retn
```
