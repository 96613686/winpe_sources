# WLIDCGetConfigDWORDValue(ulong,ulong *)

- ea: `0x18001e4cc`
- end: `0x18001e830`
- name: `?WLIDCGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180019720`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019f4c`
- `0x18001ba00`
- `0x18001e4cc`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e696`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e6e8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e696`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e6e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e5b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e6f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e765`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e60e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001e60e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e71e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e71e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e56d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001e56d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001e6bd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001e6bd`

## string_xrefs

- `0x18001e5d9`: `RPC failed to create new event, hr = %#x`
- `0x18001e732`: `RPC Async complete call failed, hr = %#x`
- `0x18001e77d`: `WLIDCGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall WLIDCGetConfigDWORDValue(unsigned int a1, unsigned int *a2)
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
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
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
    v10 = 1091;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v18, a1, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v9 = L"RPC call failed, hr = %#x";
    v10 = 1093;
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
    v10 = 1093;
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
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>(
      (__int64)"WLIDCGetConfigDWORDValue",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x445u,
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
      0x445u,
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
0x18001e4cc  mov     [rsp+arg_10], rsi
0x18001e4d1  mov     [rsp+arg_18], r12
0x18001e4d6  push    r13
0x18001e4d8  push    r14
0x18001e4da  push    r15
0x18001e4dc  sub     rsp, 0F0h
0x18001e4e3  mov     rax, cs:__security_cookie
0x18001e4ea  xor     rax, rsp
0x18001e4ed  mov     [rsp+108h+var_28], rax
0x18001e4f5  mov     r13, rdx
0x18001e4f8  mov     r12d, ecx
0x18001e4fb  mov     [rsp+108h+dwMilliseconds], 0
0x18001e503  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001e508  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001e50d  mov     [rsp+108h+Reply], 0
0x18001e515  mov     [rsp+108h+var_B8], 0
0x18001e51e  lea     rcx, [rsp+108h+var_B8]; this
0x18001e523  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001e528  mov     [rsp+108h+Reply], eax
0x18001e52c  test    eax, eax
0x18001e52e  js      loc_18001E806
0x18001e534  xor     edx, edx; Val
0x18001e536  lea     r8d, [rdx+70h]; Size
0x18001e53a  lea     rcx, [rsp+108h+pAsync]; void *
0x18001e53f  call    memset_0
0x18001e544  mov     esi, [rsp+108h+dwMilliseconds]
0x18001e548  mov     [rsp+108h+dwMilliseconds], esi
0x18001e54c  mov     [rsp+108h+var_BC], esi
0x18001e550  xor     r15b, r15b
0x18001e553  mov     [rsp+108h+var_C4], r15b
0x18001e558  xor     r14b, r14b
0x18001e55b  xorps   xmm0, xmm0
0x18001e55e  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001e563  mov     edx, 70h ; 'p'; Size
0x18001e568  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001e56d  call    cs:__imp_RpcAsyncInitializeHandle
0x18001e573  test    eax, eax
0x18001e575  jz      short loc_18001E593
0x18001e577  jle     short loc_18001E581
0x18001e579  movzx   eax, ax
0x18001e57c  or      eax, 80070000h
0x18001e581  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001e588  mov     r8d, 443h
0x18001e58e  jmp     loc_18001E73F
0x18001e593  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001e59f  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001e5aa  xor     r9d, r9d; lpName
0x18001e5ad  xor     r8d, r8d; bInitialState
0x18001e5b0  xor     edx, edx; bManualReset
0x18001e5b2  xor     ecx, ecx; lpEventAttributes
0x18001e5b4  call    cs:__imp_CreateEventW
0x18001e5ba  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001e5c2  test    rax, rax
0x18001e5c5  jnz     short loc_18001E5E2
0x18001e5c7  call    cs:__imp_GetLastError
0x18001e5cd  test    eax, eax
0x18001e5cf  jle     short loc_18001E5D9
0x18001e5d1  movzx   eax, ax
0x18001e5d4  or      eax, 80070000h
0x18001e5d9  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001e5e0  jmp     short loc_18001E588
0x18001e5e2  mov     [rsp+108h+Handles], rax
0x18001e5e7  mov     [rsp+108h+var_D8], r13
0x18001e5ec  mov     [rsp+108h+var_E0], r12d
0x18001e5f1  mov     rax, [rsp+108h+var_B8]
0x18001e5f6  mov     qword ptr [rsp+108h+bAlertable], rax
0x18001e5fb  lea     r9, [rsp+108h+pAsync]
0x18001e600  xor     r8d, r8d; pReturnValue
0x18001e603  lea     edx, [r8+36h]; nProcNum
0x18001e607  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001e60e  call    cs:__imp_Ndr64AsyncClientCall
0x18001e614  mov     eax, [rsp+108h+Reply]
0x18001e618  jmp     short loc_18001E669
0x18001e61a  test    eax, eax
0x18001e61c  jle     short loc_18001E626
0x18001e61e  movzx   eax, ax
0x18001e621  or      eax, 80070000h
0x18001e626  mov     [rsp+108h+Reply], eax
0x18001e62a  mov     [rsp+108h+bAlertable], eax
0x18001e62e  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001e635  mov     r8d, 445h; unsigned int
0x18001e63b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e642  mov     ecx, 2; unsigned __int8
0x18001e647  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e64c  mov     eax, [rsp+108h+Reply]
0x18001e650  test    eax, eax
0x18001e652  js      short loc_18001E65D
0x18001e654  mov     eax, 8000FFFFh
0x18001e659  mov     [rsp+108h+Reply], eax
0x18001e65d  mov     esi, [rsp+108h+dwMilliseconds]
0x18001e661  mov     r15b, [rsp+108h+var_C4]
0x18001e666  mov     r14b, r15b
0x18001e669  test    eax, eax
0x18001e66b  jns     short loc_18001E67F
0x18001e66d  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001e674  mov     r8d, 445h
0x18001e67a  jmp     loc_18001E743
0x18001e67f  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001e687  mov     r9d, esi; dwMilliseconds
0x18001e68a  xor     r8d, r8d; bWaitAll
0x18001e68d  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001e692  lea     ecx, [r8+1]; nCount
0x18001e696  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e69c  mov     esi, eax
0x18001e69e  mov     r12d, 102h
0x18001e6a4  test    r14b, r14b
0x18001e6a7  jnz     short loc_18001E6F5
0x18001e6a9  cmp     esi, r12d
0x18001e6ac  jz      short loc_18001E6B3
0x18001e6ae  cmp     esi, 1
0x18001e6b1  jnz     short loc_18001E6F5
0x18001e6b3  mov     edx, 1; fAbort
0x18001e6b8  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001e6bd  call    cs:__imp_RpcAsyncCancelCall
0x18001e6c3  cmp     esi, r12d
0x18001e6c6  jnz     short loc_18001E6CD
0x18001e6c8  mov     r15b, 1
0x18001e6cb  jmp     short loc_18001E6D0
0x18001e6cd  mov     r14b, 1
0x18001e6d0  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001e6d8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001e6dc  xor     r8d, r8d; bWaitAll
0x18001e6df  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001e6e4  lea     ecx, [r8+1]; nCount
0x18001e6e8  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e6ee  mov     esi, eax
0x18001e6f0  test    r15b, r15b
0x18001e6f3  jz      short loc_18001E6A4
0x18001e6f5  test    esi, esi
0x18001e6f7  jz      short loc_18001E714
0x18001e6f9  call    cs:__imp_GetLastError
0x18001e6ff  test    eax, eax
0x18001e701  jle     short loc_18001E70B
0x18001e703  movzx   eax, ax
0x18001e706  or      eax, 80070000h
0x18001e70b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001e712  jmp     short loc_18001E739
0x18001e714  lea     rdx, [rsp+108h+Reply]; Reply
0x18001e719  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001e71e  call    cs:__imp_RpcAsyncCompleteCall
0x18001e724  test    eax, eax
0x18001e726  jz      short loc_18001E758
0x18001e728  jle     short loc_18001E732
0x18001e72a  movzx   eax, ax
0x18001e72d  or      eax, 80070000h
0x18001e732  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001e739  mov     r8d, 445h; unsigned int
0x18001e73f  mov     [rsp+108h+Reply], eax
0x18001e743  mov     [rsp+108h+bAlertable], eax
0x18001e747  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e74e  mov     ecx, 2; unsigned __int8
0x18001e753  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e758  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001e760  test    rcx, rcx
0x18001e763  jz      short loc_18001E76B
0x18001e765  call    cs:__imp_CloseHandle
0x18001e76b  test    r15b, r15b
0x18001e76e  jz      short loc_18001E7AF
0x18001e770  mov     [rsp+108h+Reply], 800705B4h
0x18001e778  lea     rdx, [rsp+108h+var_BC]
0x18001e77d  lea     rcx, aWlidcgetconfig_0; "WLIDCGetConfigDWORDValue"
0x18001e784  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x18001e789  mov     eax, [rsp+108h+Reply]
0x18001e78d  mov     [rsp+108h+bAlertable], eax
0x18001e791  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001e798  mov     r8d, 445h; unsigned int
0x18001e79e  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e7a5  mov     ecx, 2; unsigned __int8
0x18001e7aa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e7af  test    r14b, r14b
0x18001e7b2  jz      short loc_18001E7DF
0x18001e7b4  mov     eax, 800704C7h
0x18001e7b9  mov     [rsp+108h+Reply], eax
0x18001e7bd  mov     [rsp+108h+bAlertable], eax
0x18001e7c1  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001e7c8  mov     r8d, 445h; unsigned int
0x18001e7ce  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e7d5  mov     ecx, 2; unsigned __int8
0x18001e7da  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e7df  cmp     [rsp+108h+Reply], 800706B5h
0x18001e7e7  jz      short loc_18001E7F3
0x18001e7e9  cmp     [rsp+108h+Reply], 800706BAh
0x18001e7f1  jnz     short loc_18001E7F8
0x18001e7f3  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001e7f8  lea     rcx, [rsp+108h+var_B8]; this
0x18001e7fd  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001e802  mov     eax, [rsp+108h+Reply]
0x18001e806  mov     rcx, [rsp+108h+var_28]
0x18001e80e  xor     rcx, rsp; StackCookie
0x18001e811  call    __security_check_cookie
0x18001e816  lea     r11, [rsp+108h+var_18]
0x18001e81e  mov     rsi, [r11+30h]
0x18001e822  mov     r12, [r11+38h]
0x18001e826  mov     rsp, r11
0x18001e829  pop     r15
0x18001e82b  pop     r14
0x18001e82d  pop     r13
0x18001e82f  retn
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
