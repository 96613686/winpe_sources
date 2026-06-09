# WLIDCUpdateToken(void * const,_WLIDTokenParams const *,ushort * *)

- ea: `0x1800228bc`
- end: `0x180022c3a`
- name: `?WLIDCUpdateToken@@YAJQEAXPEBU_WLIDTokenParams@@PEAPEAG@Z`
- size: `894`
- prototype: `__int64 __fastcall(void *const, const struct _WLIDTokenParams *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800199b0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019afc`
- `0x18001ba00`
- `0x180020750`
- `0x1800228bc`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022aa3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022af8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022aa3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022af8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b78`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022a1b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022a1b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022b31`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022b31`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002296b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002296b`
- `RPCRT4!RpcAsyncCancelCall` at `0x180022acd`
- `RPCRT4!RpcAsyncCancelCall` at `0x180022acd`

## string_xrefs

- `0x1800229d7`: `RPC failed to create new event, hr = %#x`
- `0x180022b45`: `RPC Async complete call failed, hr = %#x`
- `0x180022b90`: `WLIDCUpdateToken`

## pseudocode

```c
__int64 __fastcall WLIDCUpdateToken(void *const a1, const struct _WLIDTokenParams *a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  unsigned __int16 **v13; // rax
  DWORD v14; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-108h]
  int Reply; // [rsp+40h] [rbp-E8h] BYREF
  char v17; // [rsp+44h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-E0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-DCh] BYREF
  __int64 v20; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-D0h] BYREF
  const struct _WLIDTokenParams *v22; // [rsp+60h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+68h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v22 = a2;
  v21 = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v19 = dwMilliseconds;
  v7 = 0;
  v17 = 0;
  v8 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v11 = 1322;
LABEL_32:
    Reply = LastError;
    goto LABEL_33;
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
  v13 = (unsigned __int16 **)&v21;
  if ( a3 )
    v13 = a3;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x10u, 0, &pAsync, a1, v22, v13);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v10 = L"RPC call failed, hr = %#x";
    v11 = 1328;
LABEL_33:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v11,
      v10,
      *(_QWORD *)bAlertable);
    goto LABEL_34;
  }
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v6, 0);
  do
  {
    if ( v8 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v7 = 1;
    else
      v8 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v7 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_31:
    v11 = 1328;
    goto LABEL_32;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_31;
  }
LABEL_34:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCUpdateToken",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x530u,
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
      0x530u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x1800228bc  push    rsi
0x1800228be  push    r12
0x1800228c0  push    r13
0x1800228c2  push    r14
0x1800228c4  push    r15
0x1800228c6  sub     rsp, 100h
0x1800228cd  mov     rax, cs:__security_cookie
0x1800228d4  xor     rax, rsp
0x1800228d7  mov     [rsp+128h+var_38], rax
0x1800228df  mov     r12, r8
0x1800228e2  mov     [rsp+128h+var_C8], rdx
0x1800228e7  mov     r13, rcx
0x1800228ea  mov     [rsp+128h+var_D0], 0
0x1800228f3  mov     [rsp+128h+dwMilliseconds], 0
0x1800228fb  lea     r8, [rsp+128h+dwMilliseconds]; unsigned int *
0x180022900  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180022905  mov     [rsp+128h+Reply], 0
0x18002290d  mov     [rsp+128h+var_D8], 0
0x180022916  lea     rcx, [rsp+128h+var_D8]; this
0x18002291b  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180022920  mov     [rsp+128h+Reply], eax
0x180022924  test    eax, eax
0x180022926  js      loc_180022C19
0x18002292c  xor     edx, edx; Val
0x18002292e  lea     r8d, [rdx+70h]; Size
0x180022932  lea     rcx, [rsp+128h+pAsync]; void *
0x18002293a  call    memset_0
0x18002293f  mov     esi, [rsp+128h+dwMilliseconds]
0x180022943  mov     [rsp+128h+dwMilliseconds], esi
0x180022947  mov     [rsp+128h+var_DC], esi
0x18002294b  xor     r15b, r15b
0x18002294e  mov     [rsp+128h+var_E4], r15b
0x180022953  xor     r14b, r14b
0x180022956  xorps   xmm0, xmm0
0x180022959  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18002295e  mov     edx, 70h ; 'p'; Size
0x180022963  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18002296b  call    cs:__imp_RpcAsyncInitializeHandle
0x180022971  test    eax, eax
0x180022973  jz      short loc_180022991
0x180022975  jle     short loc_18002297F
0x180022977  movzx   eax, ax
0x18002297a  or      eax, 80070000h
0x18002297f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180022986  mov     r8d, 52Ah
0x18002298c  jmp     loc_180022B52
0x180022991  mov     [rsp+128h+pAsync.UserInfo], 0
0x18002299d  mov     [rsp+128h+pAsync.NotificationType], 1
0x1800229a8  xor     r9d, r9d; lpName
0x1800229ab  xor     r8d, r8d; bInitialState
0x1800229ae  xor     edx, edx; bManualReset
0x1800229b0  xor     ecx, ecx; lpEventAttributes
0x1800229b2  call    cs:__imp_CreateEventW
0x1800229b8  mov     qword ptr [rsp+128h+pAsync.u], rax
0x1800229c0  test    rax, rax
0x1800229c3  jnz     short loc_1800229E0
0x1800229c5  call    cs:__imp_GetLastError
0x1800229cb  test    eax, eax
0x1800229cd  jle     short loc_1800229D7
0x1800229cf  movzx   eax, ax
0x1800229d2  or      eax, 80070000h
0x1800229d7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x1800229de  jmp     short loc_180022986
0x1800229e0  mov     [rsp+128h+Handles], rax
0x1800229e5  lea     rax, [rsp+128h+var_D0]
0x1800229ea  test    r12, r12
0x1800229ed  cmovnz  rax, r12
0x1800229f1  mov     [rsp+128h+var_F8], rax
0x1800229f6  mov     rax, [rsp+128h+var_C8]
0x1800229fb  mov     [rsp+128h+var_100], rax
0x180022a00  mov     qword ptr [rsp+128h+bAlertable], r13
0x180022a05  lea     r9, [rsp+128h+pAsync]
0x180022a0d  xor     r8d, r8d; pReturnValue
0x180022a10  lea     edx, [r8+10h]; nProcNum
0x180022a14  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180022a1b  call    cs:__imp_Ndr64AsyncClientCall
0x180022a21  mov     eax, [rsp+128h+Reply]
0x180022a25  jmp     short loc_180022A76
0x180022a27  test    eax, eax
0x180022a29  jle     short loc_180022A33
0x180022a2b  movzx   eax, ax
0x180022a2e  or      eax, 80070000h
0x180022a33  mov     [rsp+128h+Reply], eax
0x180022a37  mov     [rsp+128h+bAlertable], eax
0x180022a3b  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180022a42  mov     r8d, 530h; unsigned int
0x180022a48  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022a4f  mov     ecx, 2; unsigned __int8
0x180022a54  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022a59  mov     eax, [rsp+128h+Reply]
0x180022a5d  test    eax, eax
0x180022a5f  js      short loc_180022A6A
0x180022a61  mov     eax, 8000FFFFh
0x180022a66  mov     [rsp+128h+Reply], eax
0x180022a6a  mov     esi, [rsp+128h+dwMilliseconds]
0x180022a6e  mov     r15b, [rsp+128h+var_E4]
0x180022a73  mov     r14b, r15b
0x180022a76  test    eax, eax
0x180022a78  jns     short loc_180022A8C
0x180022a7a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180022a81  mov     r8d, 530h
0x180022a87  jmp     loc_180022B56
0x180022a8c  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180022a94  mov     r9d, esi; dwMilliseconds
0x180022a97  xor     r8d, r8d; bWaitAll
0x180022a9a  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180022a9f  lea     ecx, [r8+1]; nCount
0x180022aa3  call    cs:__imp_WaitForMultipleObjectsEx
0x180022aa9  mov     esi, eax
0x180022aab  mov     r12d, 102h
0x180022ab1  test    r14b, r14b
0x180022ab4  jnz     short loc_180022B05
0x180022ab6  cmp     esi, r12d
0x180022ab9  jz      short loc_180022AC0
0x180022abb  cmp     esi, 1
0x180022abe  jnz     short loc_180022B05
0x180022ac0  mov     edx, 1; fAbort
0x180022ac5  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180022acd  call    cs:__imp_RpcAsyncCancelCall
0x180022ad3  cmp     esi, r12d
0x180022ad6  jnz     short loc_180022ADD
0x180022ad8  mov     r15b, 1
0x180022adb  jmp     short loc_180022AE0
0x180022add  mov     r14b, 1
0x180022ae0  mov     [rsp+128h+bAlertable], 0; bAlertable
0x180022ae8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180022aec  xor     r8d, r8d; bWaitAll
0x180022aef  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180022af4  lea     ecx, [r8+1]; nCount
0x180022af8  call    cs:__imp_WaitForMultipleObjectsEx
0x180022afe  mov     esi, eax
0x180022b00  test    r15b, r15b
0x180022b03  jz      short loc_180022AB1
0x180022b05  test    esi, esi
0x180022b07  jz      short loc_180022B24
0x180022b09  call    cs:__imp_GetLastError
0x180022b0f  test    eax, eax
0x180022b11  jle     short loc_180022B1B
0x180022b13  movzx   eax, ax
0x180022b16  or      eax, 80070000h
0x180022b1b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180022b22  jmp     short loc_180022B4C
0x180022b24  lea     rdx, [rsp+128h+Reply]; Reply
0x180022b29  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180022b31  call    cs:__imp_RpcAsyncCompleteCall
0x180022b37  test    eax, eax
0x180022b39  jz      short loc_180022B6B
0x180022b3b  jle     short loc_180022B45
0x180022b3d  movzx   eax, ax
0x180022b40  or      eax, 80070000h
0x180022b45  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180022b4c  mov     r8d, 530h; unsigned int
0x180022b52  mov     [rsp+128h+Reply], eax
0x180022b56  mov     [rsp+128h+bAlertable], eax
0x180022b5a  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022b61  mov     ecx, 2; unsigned __int8
0x180022b66  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022b6b  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180022b73  test    rcx, rcx
0x180022b76  jz      short loc_180022B7E
0x180022b78  call    cs:__imp_CloseHandle
0x180022b7e  test    r15b, r15b
0x180022b81  jz      short loc_180022BC2
0x180022b83  mov     [rsp+128h+Reply], 800705B4h
0x180022b8b  lea     rdx, [rsp+128h+var_DC]
0x180022b90  lea     rcx, aWlidcupdatetok; "WLIDCUpdateToken"
0x180022b97  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x180022b9c  mov     eax, [rsp+128h+Reply]
0x180022ba0  mov     [rsp+128h+bAlertable], eax
0x180022ba4  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180022bab  mov     r8d, 530h; unsigned int
0x180022bb1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022bb8  mov     ecx, 2; unsigned __int8
0x180022bbd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022bc2  test    r14b, r14b
0x180022bc5  jz      short loc_180022BF2
0x180022bc7  mov     eax, 800704C7h
0x180022bcc  mov     [rsp+128h+Reply], eax
0x180022bd0  mov     [rsp+128h+bAlertable], eax
0x180022bd4  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180022bdb  mov     r8d, 530h; unsigned int
0x180022be1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022be8  mov     ecx, 2; unsigned __int8
0x180022bed  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022bf2  cmp     [rsp+128h+Reply], 800706B5h
0x180022bfa  jz      short loc_180022C06
0x180022bfc  cmp     [rsp+128h+Reply], 800706BAh
0x180022c04  jnz     short loc_180022C0B
0x180022c06  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180022c0b  lea     rcx, [rsp+128h+var_D8]; this
0x180022c10  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180022c15  mov     eax, [rsp+128h+Reply]
0x180022c19  mov     rcx, [rsp+128h+var_38]
0x180022c21  xor     rcx, rsp; StackCookie
0x180022c24  call    __security_check_cookie
0x180022c29  add     rsp, 100h
0x180022c30  pop     r15
0x180022c32  pop     r14
0x180022c34  pop     r13
0x180022c36  pop     r12
0x180022c38  pop     rsi
0x180022c39  retn
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
