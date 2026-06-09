# WLIDCGetScenarioInlineUrlWithContextData(ulong,ushort * *)

- ea: `0x18001fd34`
- end: `0x180020091`
- name: `?WLIDCGetScenarioInlineUrlWithContextData@@YAJKPEAPEAG@Z`
- size: `861`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019830`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a420`
- `0x18001ba00`
- `0x18001fd34`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fefe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ff50`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fefe`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ff50`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fe1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fe1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ffcd`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001fe76`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001fe76`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ff86`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ff86`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001fdd5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001fdd5`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ff25`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001ff25`

## string_xrefs

- `0x18001fe41`: `RPC failed to create new event, hr = %#x`
- `0x18001ff9a`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetScenarioInlineUrlWithContextData(unsigned int a1, unsigned __int16 **a2)
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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+40h] [rbp-C8h] BYREF
  char v16; // [rsp+44h] [rbp-C4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-C0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v18 = dwMilliseconds;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v10 = 1469;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x47u, 0, &pAsync, v19, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1475;
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
    v10 = 1475;
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[41],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x5C3u,
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
      0x5C3u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v19);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18001fd34  mov     [rsp+arg_10], rsi
0x18001fd39  mov     [rsp+arg_18], r12
0x18001fd3e  push    r13
0x18001fd40  push    r14
0x18001fd42  push    r15
0x18001fd44  sub     rsp, 0F0h
0x18001fd4b  mov     rax, cs:__security_cookie
0x18001fd52  xor     rax, rsp
0x18001fd55  mov     [rsp+108h+var_28], rax
0x18001fd5d  mov     r13, rdx
0x18001fd60  mov     r12d, ecx
0x18001fd63  mov     [rsp+108h+dwMilliseconds], 0
0x18001fd6b  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001fd70  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001fd75  mov     [rsp+108h+Reply], 0
0x18001fd7d  mov     [rsp+108h+var_B8], 0
0x18001fd86  lea     rcx, [rsp+108h+var_B8]; this
0x18001fd8b  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001fd90  mov     [rsp+108h+Reply], eax
0x18001fd94  test    eax, eax
0x18001fd96  js      loc_180020067
0x18001fd9c  xor     edx, edx; Val
0x18001fd9e  lea     r8d, [rdx+70h]; Size
0x18001fda2  lea     rcx, [rsp+108h+pAsync]; void *
0x18001fda7  call    memset_0
0x18001fdac  mov     esi, [rsp+108h+dwMilliseconds]
0x18001fdb0  mov     [rsp+108h+dwMilliseconds], esi
0x18001fdb4  mov     [rsp+108h+var_BC], esi
0x18001fdb8  xor     r15b, r15b
0x18001fdbb  mov     [rsp+108h+var_C4], r15b
0x18001fdc0  xor     r14b, r14b
0x18001fdc3  xorps   xmm0, xmm0
0x18001fdc6  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001fdcb  mov     edx, 70h ; 'p'; Size
0x18001fdd0  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001fdd5  call    cs:__imp_RpcAsyncInitializeHandle
0x18001fddb  test    eax, eax
0x18001fddd  jz      short loc_18001FDFB
0x18001fddf  jle     short loc_18001FDE9
0x18001fde1  movzx   eax, ax
0x18001fde4  or      eax, 80070000h
0x18001fde9  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001fdf0  mov     r8d, 5BDh
0x18001fdf6  jmp     loc_18001FFA7
0x18001fdfb  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001fe07  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001fe12  xor     r9d, r9d; lpName
0x18001fe15  xor     r8d, r8d; bInitialState
0x18001fe18  xor     edx, edx; bManualReset
0x18001fe1a  xor     ecx, ecx; lpEventAttributes
0x18001fe1c  call    cs:__imp_CreateEventW
0x18001fe22  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001fe2a  test    rax, rax
0x18001fe2d  jnz     short loc_18001FE4A
0x18001fe2f  call    cs:__imp_GetLastError
0x18001fe35  test    eax, eax
0x18001fe37  jle     short loc_18001FE41
0x18001fe39  movzx   eax, ax
0x18001fe3c  or      eax, 80070000h
0x18001fe41  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001fe48  jmp     short loc_18001FDF0
0x18001fe4a  mov     [rsp+108h+Handles], rax
0x18001fe4f  mov     [rsp+108h+var_D8], r13
0x18001fe54  mov     [rsp+108h+var_E0], r12d
0x18001fe59  mov     rax, [rsp+108h+var_B8]
0x18001fe5e  mov     qword ptr [rsp+108h+bAlertable], rax
0x18001fe63  lea     r9, [rsp+108h+pAsync]
0x18001fe68  xor     r8d, r8d; pReturnValue
0x18001fe6b  lea     edx, [r8+47h]; nProcNum
0x18001fe6f  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001fe76  call    cs:__imp_Ndr64AsyncClientCall
0x18001fe7c  mov     eax, [rsp+108h+Reply]
0x18001fe80  jmp     short loc_18001FED1
0x18001fe82  test    eax, eax
0x18001fe84  jle     short loc_18001FE8E
0x18001fe86  movzx   eax, ax
0x18001fe89  or      eax, 80070000h
0x18001fe8e  mov     [rsp+108h+Reply], eax
0x18001fe92  mov     [rsp+108h+bAlertable], eax
0x18001fe96  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001fe9d  mov     r8d, 5C3h; unsigned int
0x18001fea3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001feaa  mov     ecx, 2; unsigned __int8
0x18001feaf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001feb4  mov     eax, [rsp+108h+Reply]
0x18001feb8  test    eax, eax
0x18001feba  js      short loc_18001FEC5
0x18001febc  mov     eax, 8000FFFFh
0x18001fec1  mov     [rsp+108h+Reply], eax
0x18001fec5  mov     esi, [rsp+108h+dwMilliseconds]
0x18001fec9  mov     r15b, [rsp+108h+var_C4]
0x18001fece  mov     r14b, r15b
0x18001fed1  test    eax, eax
0x18001fed3  jns     short loc_18001FEE7
0x18001fed5  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001fedc  mov     r8d, 5C3h
0x18001fee2  jmp     loc_18001FFAB
0x18001fee7  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001feef  mov     r9d, esi; dwMilliseconds
0x18001fef2  xor     r8d, r8d; bWaitAll
0x18001fef5  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001fefa  lea     ecx, [r8+1]; nCount
0x18001fefe  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ff04  mov     esi, eax
0x18001ff06  mov     r12d, 102h
0x18001ff0c  test    r14b, r14b
0x18001ff0f  jnz     short loc_18001FF5D
0x18001ff11  cmp     esi, r12d
0x18001ff14  jz      short loc_18001FF1B
0x18001ff16  cmp     esi, 1
0x18001ff19  jnz     short loc_18001FF5D
0x18001ff1b  mov     edx, 1; fAbort
0x18001ff20  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ff25  call    cs:__imp_RpcAsyncCancelCall
0x18001ff2b  cmp     esi, r12d
0x18001ff2e  jnz     short loc_18001FF35
0x18001ff30  mov     r15b, 1
0x18001ff33  jmp     short loc_18001FF38
0x18001ff35  mov     r14b, 1
0x18001ff38  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001ff40  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001ff44  xor     r8d, r8d; bWaitAll
0x18001ff47  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001ff4c  lea     ecx, [r8+1]; nCount
0x18001ff50  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ff56  mov     esi, eax
0x18001ff58  test    r15b, r15b
0x18001ff5b  jz      short loc_18001FF0C
0x18001ff5d  test    esi, esi
0x18001ff5f  jz      short loc_18001FF7C
0x18001ff61  call    cs:__imp_GetLastError
0x18001ff67  test    eax, eax
0x18001ff69  jle     short loc_18001FF73
0x18001ff6b  movzx   eax, ax
0x18001ff6e  or      eax, 80070000h
0x18001ff73  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001ff7a  jmp     short loc_18001FFA1
0x18001ff7c  lea     rdx, [rsp+108h+Reply]; Reply
0x18001ff81  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001ff86  call    cs:__imp_RpcAsyncCompleteCall
0x18001ff8c  test    eax, eax
0x18001ff8e  jz      short loc_18001FFC0
0x18001ff90  jle     short loc_18001FF9A
0x18001ff92  movzx   eax, ax
0x18001ff95  or      eax, 80070000h
0x18001ff9a  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001ffa1  mov     r8d, 5C3h; unsigned int
0x18001ffa7  mov     [rsp+108h+Reply], eax
0x18001ffab  mov     [rsp+108h+bAlertable], eax
0x18001ffaf  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001ffb6  mov     ecx, 2; unsigned __int8
0x18001ffbb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001ffc0  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001ffc8  test    rcx, rcx
0x18001ffcb  jz      short loc_18001FFD3
0x18001ffcd  call    cs:__imp_CloseHandle
0x18001ffd3  test    r15b, r15b
0x18001ffd6  jz      short loc_180020010
0x18001ffd8  mov     [rsp+108h+Reply], 800705B4h
0x18001ffe0  lea     rdx, [rsp+108h+var_BC]
0x18001ffe5  call    ??$RPCCallTimedOut@AEAY0CJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[41],ulong &>(char const (&)[41],ulong &)
0x18001ffea  mov     eax, [rsp+108h+Reply]
0x18001ffee  mov     [rsp+108h+bAlertable], eax
0x18001fff2  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001fff9  mov     r8d, 5C3h; unsigned int
0x18001ffff  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020006  mov     ecx, 2; unsigned __int8
0x18002000b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020010  test    r14b, r14b
0x180020013  jz      short loc_180020040
0x180020015  mov     eax, 800704C7h
0x18002001a  mov     [rsp+108h+Reply], eax
0x18002001e  mov     [rsp+108h+bAlertable], eax
0x180020022  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180020029  mov     r8d, 5C3h; unsigned int
0x18002002f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020036  mov     ecx, 2; unsigned __int8
0x18002003b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020040  cmp     [rsp+108h+Reply], 800706B5h
0x180020048  jz      short loc_180020054
0x18002004a  cmp     [rsp+108h+Reply], 800706BAh
0x180020052  jnz     short loc_180020059
0x180020054  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180020059  lea     rcx, [rsp+108h+var_B8]; this
0x18002005e  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180020063  mov     eax, [rsp+108h+Reply]
0x180020067  mov     rcx, [rsp+108h+var_28]
0x18002006f  xor     rcx, rsp; StackCookie
0x180020072  call    __security_check_cookie
0x180020077  lea     r11, [rsp+108h+var_18]
0x18002007f  mov     rsi, [r11+30h]
0x180020083  mov     r12, [r11+38h]
0x180020087  mov     rsp, r11
0x18002008a  pop     r15
0x18002008c  pop     r14
0x18002008e  pop     r13
0x180020090  retn
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
