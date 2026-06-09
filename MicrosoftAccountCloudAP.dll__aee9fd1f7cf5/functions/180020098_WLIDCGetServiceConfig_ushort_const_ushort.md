# WLIDCGetServiceConfig(ushort const *,ushort * *)

- ea: `0x180020098`
- end: `0x1800203fc`
- name: `?WLIDCGetServiceConfig@@YAJPEBGPEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019840`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019dac`
- `0x18001ba00`
- `0x180020098`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020262`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800202b4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180020262`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800202b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020180`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020193`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020331`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020331`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800201da`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800201da`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800202ea`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800202ea`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020139`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020139`
- `RPCRT4!RpcAsyncCancelCall` at `0x180020289`
- `RPCRT4!RpcAsyncCancelCall` at `0x180020289`

## string_xrefs

- `0x1800201a5`: `RPC failed to create new event, hr = %#x`
- `0x1800202fe`: `RPC Async complete call failed, hr = %#x`
- `0x180020349`: `WLIDCGetServiceConfig`

## pseudocode

```c
__int64 __fastcall WLIDCGetServiceConfig(const unsigned __int16 *a1, unsigned __int16 **a2)
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
    v10 = 648;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xEu, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 650;
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
    v10 = 650;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>(
      (__int64)"WLIDCGetServiceConfig",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x28Au,
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
      0x28Au,
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
0x180020098  mov     [rsp+arg_10], rsi
0x18002009d  mov     [rsp+arg_18], r12
0x1800200a2  push    r13
0x1800200a4  push    r14
0x1800200a6  push    r15
0x1800200a8  sub     rsp, 0F0h
0x1800200af  mov     rax, cs:__security_cookie
0x1800200b6  xor     rax, rsp
0x1800200b9  mov     [rsp+108h+var_28], rax
0x1800200c1  mov     r13, rdx
0x1800200c4  mov     r12, rcx
0x1800200c7  mov     [rsp+108h+dwMilliseconds], 0
0x1800200cf  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x1800200d4  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800200d9  mov     [rsp+108h+Reply], 0
0x1800200e1  mov     [rsp+108h+var_B8], 0
0x1800200ea  lea     rcx, [rsp+108h+var_B8]; this
0x1800200ef  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x1800200f4  mov     [rsp+108h+Reply], eax
0x1800200f8  test    eax, eax
0x1800200fa  js      loc_1800203D2
0x180020100  xor     edx, edx; Val
0x180020102  lea     r8d, [rdx+70h]; Size
0x180020106  lea     rcx, [rsp+108h+pAsync]; void *
0x18002010b  call    memset_0
0x180020110  mov     esi, [rsp+108h+dwMilliseconds]
0x180020114  mov     [rsp+108h+dwMilliseconds], esi
0x180020118  mov     [rsp+108h+var_BC], esi
0x18002011c  xor     r15b, r15b
0x18002011f  mov     [rsp+108h+var_C4], r15b
0x180020124  xor     r14b, r14b
0x180020127  xorps   xmm0, xmm0
0x18002012a  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18002012f  mov     edx, 70h ; 'p'; Size
0x180020134  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180020139  call    cs:__imp_RpcAsyncInitializeHandle
0x18002013f  test    eax, eax
0x180020141  jz      short loc_18002015F
0x180020143  jle     short loc_18002014D
0x180020145  movzx   eax, ax
0x180020148  or      eax, 80070000h
0x18002014d  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180020154  mov     r8d, 288h
0x18002015a  jmp     loc_18002030B
0x18002015f  mov     [rsp+108h+pAsync.UserInfo], 0
0x18002016b  mov     [rsp+108h+pAsync.NotificationType], 1
0x180020176  xor     r9d, r9d; lpName
0x180020179  xor     r8d, r8d; bInitialState
0x18002017c  xor     edx, edx; bManualReset
0x18002017e  xor     ecx, ecx; lpEventAttributes
0x180020180  call    cs:__imp_CreateEventW
0x180020186  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18002018e  test    rax, rax
0x180020191  jnz     short loc_1800201AE
0x180020193  call    cs:__imp_GetLastError
0x180020199  test    eax, eax
0x18002019b  jle     short loc_1800201A5
0x18002019d  movzx   eax, ax
0x1800201a0  or      eax, 80070000h
0x1800201a5  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800201ac  jmp     short loc_180020154
0x1800201ae  mov     [rsp+108h+Handles], rax
0x1800201b3  mov     [rsp+108h+var_D8], r13
0x1800201b8  mov     [rsp+108h+var_E0], r12
0x1800201bd  mov     rax, [rsp+108h+var_B8]
0x1800201c2  mov     qword ptr [rsp+108h+bAlertable], rax
0x1800201c7  lea     r9, [rsp+108h+pAsync]
0x1800201cc  xor     r8d, r8d; pReturnValue
0x1800201cf  lea     edx, [r8+0Eh]; nProcNum
0x1800201d3  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800201da  call    cs:__imp_Ndr64AsyncClientCall
0x1800201e0  mov     eax, [rsp+108h+Reply]
0x1800201e4  jmp     short loc_180020235
0x1800201e6  test    eax, eax
0x1800201e8  jle     short loc_1800201F2
0x1800201ea  movzx   eax, ax
0x1800201ed  or      eax, 80070000h
0x1800201f2  mov     [rsp+108h+Reply], eax
0x1800201f6  mov     [rsp+108h+bAlertable], eax
0x1800201fa  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180020201  mov     r8d, 28Ah; unsigned int
0x180020207  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002020e  mov     ecx, 2; unsigned __int8
0x180020213  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020218  mov     eax, [rsp+108h+Reply]
0x18002021c  test    eax, eax
0x18002021e  js      short loc_180020229
0x180020220  mov     eax, 8000FFFFh
0x180020225  mov     [rsp+108h+Reply], eax
0x180020229  mov     esi, [rsp+108h+dwMilliseconds]
0x18002022d  mov     r15b, [rsp+108h+var_C4]
0x180020232  mov     r14b, r15b
0x180020235  test    eax, eax
0x180020237  jns     short loc_18002024B
0x180020239  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180020240  mov     r8d, 28Ah
0x180020246  jmp     loc_18002030F
0x18002024b  mov     [rsp+108h+bAlertable], 0; bAlertable
0x180020253  mov     r9d, esi; dwMilliseconds
0x180020256  xor     r8d, r8d; bWaitAll
0x180020259  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18002025e  lea     ecx, [r8+1]; nCount
0x180020262  call    cs:__imp_WaitForMultipleObjectsEx
0x180020268  mov     esi, eax
0x18002026a  mov     r12d, 102h
0x180020270  test    r14b, r14b
0x180020273  jnz     short loc_1800202C1
0x180020275  cmp     esi, r12d
0x180020278  jz      short loc_18002027F
0x18002027a  cmp     esi, 1
0x18002027d  jnz     short loc_1800202C1
0x18002027f  mov     edx, 1; fAbort
0x180020284  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180020289  call    cs:__imp_RpcAsyncCancelCall
0x18002028f  cmp     esi, r12d
0x180020292  jnz     short loc_180020299
0x180020294  mov     r15b, 1
0x180020297  jmp     short loc_18002029C
0x180020299  mov     r14b, 1
0x18002029c  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800202a4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800202a8  xor     r8d, r8d; bWaitAll
0x1800202ab  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800202b0  lea     ecx, [r8+1]; nCount
0x1800202b4  call    cs:__imp_WaitForMultipleObjectsEx
0x1800202ba  mov     esi, eax
0x1800202bc  test    r15b, r15b
0x1800202bf  jz      short loc_180020270
0x1800202c1  test    esi, esi
0x1800202c3  jz      short loc_1800202E0
0x1800202c5  call    cs:__imp_GetLastError
0x1800202cb  test    eax, eax
0x1800202cd  jle     short loc_1800202D7
0x1800202cf  movzx   eax, ax
0x1800202d2  or      eax, 80070000h
0x1800202d7  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800202de  jmp     short loc_180020305
0x1800202e0  lea     rdx, [rsp+108h+Reply]; Reply
0x1800202e5  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800202ea  call    cs:__imp_RpcAsyncCompleteCall
0x1800202f0  test    eax, eax
0x1800202f2  jz      short loc_180020324
0x1800202f4  jle     short loc_1800202FE
0x1800202f6  movzx   eax, ax
0x1800202f9  or      eax, 80070000h
0x1800202fe  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180020305  mov     r8d, 28Ah; unsigned int
0x18002030b  mov     [rsp+108h+Reply], eax
0x18002030f  mov     [rsp+108h+bAlertable], eax
0x180020313  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002031a  mov     ecx, 2; unsigned __int8
0x18002031f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020324  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18002032c  test    rcx, rcx
0x18002032f  jz      short loc_180020337
0x180020331  call    cs:__imp_CloseHandle
0x180020337  test    r15b, r15b
0x18002033a  jz      short loc_18002037B
0x18002033c  mov     [rsp+108h+Reply], 800705B4h
0x180020344  lea     rdx, [rsp+108h+var_BC]
0x180020349  lea     rcx, aWlidcgetservic; "WLIDCGetServiceConfig"
0x180020350  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x180020355  mov     eax, [rsp+108h+Reply]
0x180020359  mov     [rsp+108h+bAlertable], eax
0x18002035d  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180020364  mov     r8d, 28Ah; unsigned int
0x18002036a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020371  mov     ecx, 2; unsigned __int8
0x180020376  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002037b  test    r14b, r14b
0x18002037e  jz      short loc_1800203AB
0x180020380  mov     eax, 800704C7h
0x180020385  mov     [rsp+108h+Reply], eax
0x180020389  mov     [rsp+108h+bAlertable], eax
0x18002038d  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180020394  mov     r8d, 28Ah; unsigned int
0x18002039a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800203a1  mov     ecx, 2; unsigned __int8
0x1800203a6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800203ab  cmp     [rsp+108h+Reply], 800706B5h
0x1800203b3  jz      short loc_1800203BF
0x1800203b5  cmp     [rsp+108h+Reply], 800706BAh
0x1800203bd  jnz     short loc_1800203C4
0x1800203bf  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x1800203c4  lea     rcx, [rsp+108h+var_B8]; this
0x1800203c9  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x1800203ce  mov     eax, [rsp+108h+Reply]
0x1800203d2  mov     rcx, [rsp+108h+var_28]
0x1800203da  xor     rcx, rsp; StackCookie
0x1800203dd  call    __security_check_cookie
0x1800203e2  lea     r11, [rsp+108h+var_18]
0x1800203ea  mov     rsi, [r11+30h]
0x1800203ee  mov     r12, [r11+38h]
0x1800203f2  mov     rsp, r11
0x1800203f5  pop     r15
0x1800203f7  pop     r14
0x1800203f9  pop     r13
0x1800203fb  retn
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
