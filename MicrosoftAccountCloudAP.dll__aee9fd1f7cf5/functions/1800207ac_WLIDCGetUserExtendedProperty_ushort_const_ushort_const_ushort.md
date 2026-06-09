# WLIDCGetUserExtendedProperty(ushort const *,ushort const *,ushort * *)

- ea: `0x1800207ac`
- end: `0x180020b10`
- name: `?WLIDCGetUserExtendedProperty@@YAJPEBG0PEAPEAG@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019870`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a0ec`
- `0x18001ba00`
- `0x180020750`
- `0x1800207ac`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002097f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800209d1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002097f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800209d1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020893`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a4e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800208f7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800208f7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020a07`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020a07`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002084c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002084c`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800209a6`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800209a6`

## string_xrefs

- `0x1800208b8`: `RPC failed to create new event, hr = %#x`
- `0x180020a1b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetUserExtendedProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v19; // [rsp+50h] [rbp-C8h] BYREF
  unsigned __int16 **v20; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v19 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v19);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v18 = dwMilliseconds;
  v7 = 0;
  v16 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 753;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x14u, 0, &pAsync, v19, a1, a2, v20);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 755;
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
    v11 = 755;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],unsigned long &>(
      (__int64)"WLIDCGetUserExtendedProperty",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2F3u,
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
      0x2F3u,
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
0x1800207ac  push    rsi
0x1800207ae  push    r12
0x1800207b0  push    r13
0x1800207b2  push    r14
0x1800207b4  push    r15
0x1800207b6  sub     rsp, 0F0h
0x1800207bd  mov     rax, cs:__security_cookie
0x1800207c4  xor     rax, rsp
0x1800207c7  mov     [rsp+118h+var_38], rax
0x1800207cf  mov     [rsp+118h+var_C0], r8
0x1800207d4  mov     r13, rdx
0x1800207d7  mov     r12, rcx
0x1800207da  mov     [rsp+118h+dwMilliseconds], 0
0x1800207e2  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x1800207e7  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x1800207ec  mov     [rsp+118h+Reply], 0
0x1800207f4  mov     [rsp+118h+var_C8], 0
0x1800207fd  lea     rcx, [rsp+118h+var_C8]; this
0x180020802  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180020807  mov     [rsp+118h+Reply], eax
0x18002080b  test    eax, eax
0x18002080d  js      loc_180020AEF
0x180020813  xor     edx, edx; Val
0x180020815  lea     r8d, [rdx+70h]; Size
0x180020819  lea     rcx, [rsp+118h+pAsync]; void *
0x18002081e  call    memset_0
0x180020823  mov     esi, [rsp+118h+dwMilliseconds]
0x180020827  mov     [rsp+118h+dwMilliseconds], esi
0x18002082b  mov     [rsp+118h+var_CC], esi
0x18002082f  xor     r15b, r15b
0x180020832  mov     [rsp+118h+var_D4], r15b
0x180020837  xor     r14b, r14b
0x18002083a  xorps   xmm0, xmm0
0x18002083d  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180020842  mov     edx, 70h ; 'p'; Size
0x180020847  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18002084c  call    cs:__imp_RpcAsyncInitializeHandle
0x180020852  test    eax, eax
0x180020854  jz      short loc_180020872
0x180020856  jle     short loc_180020860
0x180020858  movzx   eax, ax
0x18002085b  or      eax, 80070000h
0x180020860  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180020867  mov     r8d, 2F1h
0x18002086d  jmp     loc_180020A28
0x180020872  mov     [rsp+118h+pAsync.UserInfo], 0
0x18002087e  mov     [rsp+118h+pAsync.NotificationType], 1
0x180020889  xor     r9d, r9d; lpName
0x18002088c  xor     r8d, r8d; bInitialState
0x18002088f  xor     edx, edx; bManualReset
0x180020891  xor     ecx, ecx; lpEventAttributes
0x180020893  call    cs:__imp_CreateEventW
0x180020899  mov     qword ptr [rsp+118h+pAsync.u], rax
0x1800208a1  test    rax, rax
0x1800208a4  jnz     short loc_1800208C1
0x1800208a6  call    cs:__imp_GetLastError
0x1800208ac  test    eax, eax
0x1800208ae  jle     short loc_1800208B8
0x1800208b0  movzx   eax, ax
0x1800208b3  or      eax, 80070000h
0x1800208b8  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800208bf  jmp     short loc_180020867
0x1800208c1  mov     [rsp+118h+Handles], rax
0x1800208c6  mov     rax, [rsp+118h+var_C0]
0x1800208cb  mov     [rsp+118h+var_E0], rax
0x1800208d0  mov     [rsp+118h+var_E8], r13
0x1800208d5  mov     [rsp+118h+var_F0], r12
0x1800208da  mov     rax, [rsp+118h+var_C8]
0x1800208df  mov     qword ptr [rsp+118h+bAlertable], rax
0x1800208e4  lea     r9, [rsp+118h+pAsync]
0x1800208e9  xor     r8d, r8d; pReturnValue
0x1800208ec  lea     edx, [r8+14h]; nProcNum
0x1800208f0  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800208f7  call    cs:__imp_Ndr64AsyncClientCall
0x1800208fd  mov     eax, [rsp+118h+Reply]
0x180020901  jmp     short loc_180020952
0x180020903  test    eax, eax
0x180020905  jle     short loc_18002090F
0x180020907  movzx   eax, ax
0x18002090a  or      eax, 80070000h
0x18002090f  mov     [rsp+118h+Reply], eax
0x180020913  mov     [rsp+118h+bAlertable], eax
0x180020917  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18002091e  mov     r8d, 2F3h; unsigned int
0x180020924  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002092b  mov     ecx, 2; unsigned __int8
0x180020930  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020935  mov     eax, [rsp+118h+Reply]
0x180020939  test    eax, eax
0x18002093b  js      short loc_180020946
0x18002093d  mov     eax, 8000FFFFh
0x180020942  mov     [rsp+118h+Reply], eax
0x180020946  mov     esi, [rsp+118h+dwMilliseconds]
0x18002094a  mov     r15b, [rsp+118h+var_D4]
0x18002094f  mov     r14b, r15b
0x180020952  test    eax, eax
0x180020954  jns     short loc_180020968
0x180020956  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18002095d  mov     r8d, 2F3h
0x180020963  jmp     loc_180020A2C
0x180020968  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180020970  mov     r9d, esi; dwMilliseconds
0x180020973  xor     r8d, r8d; bWaitAll
0x180020976  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18002097b  lea     ecx, [r8+1]; nCount
0x18002097f  call    cs:__imp_WaitForMultipleObjectsEx
0x180020985  mov     esi, eax
0x180020987  mov     r12d, 102h
0x18002098d  test    r14b, r14b
0x180020990  jnz     short loc_1800209DE
0x180020992  cmp     esi, r12d
0x180020995  jz      short loc_18002099C
0x180020997  cmp     esi, 1
0x18002099a  jnz     short loc_1800209DE
0x18002099c  mov     edx, 1; fAbort
0x1800209a1  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800209a6  call    cs:__imp_RpcAsyncCancelCall
0x1800209ac  cmp     esi, r12d
0x1800209af  jnz     short loc_1800209B6
0x1800209b1  mov     r15b, 1
0x1800209b4  jmp     short loc_1800209B9
0x1800209b6  mov     r14b, 1
0x1800209b9  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800209c1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800209c5  xor     r8d, r8d; bWaitAll
0x1800209c8  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800209cd  lea     ecx, [r8+1]; nCount
0x1800209d1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800209d7  mov     esi, eax
0x1800209d9  test    r15b, r15b
0x1800209dc  jz      short loc_18002098D
0x1800209de  test    esi, esi
0x1800209e0  jz      short loc_1800209FD
0x1800209e2  call    cs:__imp_GetLastError
0x1800209e8  test    eax, eax
0x1800209ea  jle     short loc_1800209F4
0x1800209ec  movzx   eax, ax
0x1800209ef  or      eax, 80070000h
0x1800209f4  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800209fb  jmp     short loc_180020A22
0x1800209fd  lea     rdx, [rsp+118h+Reply]; Reply
0x180020a02  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180020a07  call    cs:__imp_RpcAsyncCompleteCall
0x180020a0d  test    eax, eax
0x180020a0f  jz      short loc_180020A41
0x180020a11  jle     short loc_180020A1B
0x180020a13  movzx   eax, ax
0x180020a16  or      eax, 80070000h
0x180020a1b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180020a22  mov     r8d, 2F3h; unsigned int
0x180020a28  mov     [rsp+118h+Reply], eax
0x180020a2c  mov     [rsp+118h+bAlertable], eax
0x180020a30  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020a37  mov     ecx, 2; unsigned __int8
0x180020a3c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020a41  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180020a49  test    rcx, rcx
0x180020a4c  jz      short loc_180020A54
0x180020a4e  call    cs:__imp_CloseHandle
0x180020a54  test    r15b, r15b
0x180020a57  jz      short loc_180020A98
0x180020a59  mov     [rsp+118h+Reply], 800705B4h
0x180020a61  lea     rdx, [rsp+118h+var_CC]
0x180020a66  lea     rcx, aWlidcgetuserex; "WLIDCGetUserExtendedProperty"
0x180020a6d  call    ??$RPCCallTimedOut@AEAY0BN@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BN@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[29],ulong &>(char const (&)[29],ulong &)
0x180020a72  mov     eax, [rsp+118h+Reply]
0x180020a76  mov     [rsp+118h+bAlertable], eax
0x180020a7a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180020a81  mov     r8d, 2F3h; unsigned int
0x180020a87  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020a8e  mov     ecx, 2; unsigned __int8
0x180020a93  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020a98  test    r14b, r14b
0x180020a9b  jz      short loc_180020AC8
0x180020a9d  mov     eax, 800704C7h
0x180020aa2  mov     [rsp+118h+Reply], eax
0x180020aa6  mov     [rsp+118h+bAlertable], eax
0x180020aaa  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180020ab1  mov     r8d, 2F3h; unsigned int
0x180020ab7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020abe  mov     ecx, 2; unsigned __int8
0x180020ac3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020ac8  cmp     [rsp+118h+Reply], 800706B5h
0x180020ad0  jz      short loc_180020ADC
0x180020ad2  cmp     [rsp+118h+Reply], 800706BAh
0x180020ada  jnz     short loc_180020AE1
0x180020adc  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180020ae1  lea     rcx, [rsp+118h+var_C8]; this
0x180020ae6  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180020aeb  mov     eax, [rsp+118h+Reply]
0x180020aef  mov     rcx, [rsp+118h+var_38]
0x180020af7  xor     rcx, rsp; StackCookie
0x180020afa  call    __security_check_cookie
0x180020aff  add     rsp, 0F0h
0x180020b06  pop     r15
0x180020b08  pop     r14
0x180020b0a  pop     r13
0x180020b0c  pop     r12
0x180020b0e  pop     rsi
0x180020b0f  retn
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
