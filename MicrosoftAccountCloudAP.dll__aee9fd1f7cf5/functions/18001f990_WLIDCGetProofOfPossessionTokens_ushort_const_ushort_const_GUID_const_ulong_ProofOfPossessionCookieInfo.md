# WLIDCGetProofOfPossessionTokens(ushort const *,ushort const *,_GUID const *,ulong *,ProofOfPossessionCookieInfo * *)

- ea: `0x18001f990`
- end: `0x18001fd2e`
- name: `?WLIDCGetProofOfPossessionTokens@@YAJPEBG0PEBU_GUID@@PEAKPEAPEAUProofOfPossessionCookieInfo@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int *, struct ProofOfPossessionCookieInfo **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019800`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a288`
- `0x18001ba00`
- `0x18001f990`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fb9b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fbf3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fb9b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fbf3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fa92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fa92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc73`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001fb10`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001fb10`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fc2c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001fc2c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001fa4b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001fa4b`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001fbc5`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001fbc5`

## string_xrefs

- `0x18001fab7`: `RPC failed to create new event, hr = %#x`
- `0x18001fc40`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetProofOfPossessionTokens(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned int *a4,
        struct ProofOfPossessionCookieInfo **a5)
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
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v19; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-D8h] BYREF
  struct ProofOfPossessionCookieInfo **v23; // [rsp+68h] [rbp-D0h]
  unsigned int *v24; // [rsp+70h] [rbp-C8h]
  const struct _GUID *v25; // [rsp+78h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+80h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v24 = a4;
  v25 = a3;
  v23 = a5;
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
  v19 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v13 = 1365;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x41u, 0, &pAsync, v22, a1, a2, v25, v24, v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 1367;
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
    v13 = 1367;
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
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x557u,
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
      0x557u,
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
0x18001f990  push    rsi
0x18001f992  push    r12
0x18001f994  push    r13
0x18001f996  push    r14
0x18001f998  push    r15
0x18001f99a  sub     rsp, 110h
0x18001f9a1  mov     rax, cs:__security_cookie
0x18001f9a8  xor     rax, rsp
0x18001f9ab  mov     [rsp+138h+var_38], rax
0x18001f9b3  mov     [rsp+138h+var_C8], r9
0x18001f9b8  mov     [rsp+138h+var_C0], r8
0x18001f9bd  mov     r13, rdx
0x18001f9c0  mov     r12, rcx
0x18001f9c3  mov     rax, [rsp+138h+arg_20]
0x18001f9cb  mov     [rsp+138h+var_D0], rax
0x18001f9d0  mov     [rsp+138h+dwMilliseconds], 0
0x18001f9d8  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18001f9dd  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001f9e2  mov     [rsp+138h+Reply], 0
0x18001f9ea  mov     [rsp+138h+var_D8], 0
0x18001f9f3  lea     rcx, [rsp+138h+var_D8]; this
0x18001f9f8  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001f9fd  mov     [rsp+138h+Reply], eax
0x18001fa01  test    eax, eax
0x18001fa03  js      loc_18001FD0D
0x18001fa09  xor     edx, edx; Val
0x18001fa0b  lea     r8d, [rdx+70h]; Size
0x18001fa0f  lea     rcx, [rsp+138h+pAsync]; void *
0x18001fa17  call    memset_0
0x18001fa1c  mov     esi, [rsp+138h+dwMilliseconds]
0x18001fa20  mov     [rsp+138h+dwMilliseconds], esi
0x18001fa24  mov     [rsp+138h+var_DC], esi
0x18001fa28  xor     r15b, r15b
0x18001fa2b  mov     [rsp+138h+var_E4], r15b
0x18001fa30  xor     r14b, r14b
0x18001fa33  xorps   xmm0, xmm0
0x18001fa36  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18001fa3e  mov     edx, 70h ; 'p'; Size
0x18001fa43  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001fa4b  call    cs:__imp_RpcAsyncInitializeHandle
0x18001fa51  test    eax, eax
0x18001fa53  jz      short loc_18001FA71
0x18001fa55  jle     short loc_18001FA5F
0x18001fa57  movzx   eax, ax
0x18001fa5a  or      eax, 80070000h
0x18001fa5f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001fa66  mov     r8d, 555h
0x18001fa6c  jmp     loc_18001FC4D
0x18001fa71  mov     [rsp+138h+pAsync.UserInfo], 0
0x18001fa7d  mov     [rsp+138h+pAsync.NotificationType], 1
0x18001fa88  xor     r9d, r9d; lpName
0x18001fa8b  xor     r8d, r8d; bInitialState
0x18001fa8e  xor     edx, edx; bManualReset
0x18001fa90  xor     ecx, ecx; lpEventAttributes
0x18001fa92  call    cs:__imp_CreateEventW
0x18001fa98  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18001faa0  test    rax, rax
0x18001faa3  jnz     short loc_18001FAC0
0x18001faa5  call    cs:__imp_GetLastError
0x18001faab  test    eax, eax
0x18001faad  jle     short loc_18001FAB7
0x18001faaf  movzx   eax, ax
0x18001fab2  or      eax, 80070000h
0x18001fab7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001fabe  jmp     short loc_18001FA66
0x18001fac0  mov     [rsp+138h+Handles], rax
0x18001fac8  mov     rax, [rsp+138h+var_D0]
0x18001facd  mov     [rsp+138h+var_F0], rax
0x18001fad2  mov     rax, [rsp+138h+var_C8]
0x18001fad7  mov     [rsp+138h+var_F8], rax
0x18001fadc  mov     rax, [rsp+138h+var_C0]
0x18001fae1  mov     [rsp+138h+var_100], rax
0x18001fae6  mov     [rsp+138h+var_108], r13
0x18001faeb  mov     [rsp+138h+var_110], r12
0x18001faf0  mov     rax, [rsp+138h+var_D8]
0x18001faf5  mov     qword ptr [rsp+138h+bAlertable], rax
0x18001fafa  lea     r9, [rsp+138h+pAsync]
0x18001fb02  xor     r8d, r8d; pReturnValue
0x18001fb05  lea     edx, [r8+41h]; nProcNum
0x18001fb09  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001fb10  call    cs:__imp_Ndr64AsyncClientCall
0x18001fb16  mov     eax, [rsp+138h+Reply]
0x18001fb1a  jmp     short loc_18001FB6B
0x18001fb1c  test    eax, eax
0x18001fb1e  jle     short loc_18001FB28
0x18001fb20  movzx   eax, ax
0x18001fb23  or      eax, 80070000h
0x18001fb28  mov     [rsp+138h+Reply], eax
0x18001fb2c  mov     [rsp+138h+bAlertable], eax
0x18001fb30  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001fb37  mov     r8d, 557h; unsigned int
0x18001fb3d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001fb44  mov     ecx, 2; unsigned __int8
0x18001fb49  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001fb4e  mov     eax, [rsp+138h+Reply]
0x18001fb52  test    eax, eax
0x18001fb54  js      short loc_18001FB5F
0x18001fb56  mov     eax, 8000FFFFh
0x18001fb5b  mov     [rsp+138h+Reply], eax
0x18001fb5f  mov     esi, [rsp+138h+dwMilliseconds]
0x18001fb63  mov     r15b, [rsp+138h+var_E4]
0x18001fb68  mov     r14b, r15b
0x18001fb6b  test    eax, eax
0x18001fb6d  jns     short loc_18001FB81
0x18001fb6f  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001fb76  mov     r8d, 557h
0x18001fb7c  jmp     loc_18001FC51
0x18001fb81  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001fb89  mov     r9d, esi; dwMilliseconds
0x18001fb8c  xor     r8d, r8d; bWaitAll
0x18001fb8f  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001fb97  lea     ecx, [r8+1]; nCount
0x18001fb9b  call    cs:__imp_WaitForMultipleObjectsEx
0x18001fba1  mov     esi, eax
0x18001fba3  mov     r12d, 102h
0x18001fba9  test    r14b, r14b
0x18001fbac  jnz     short loc_18001FC00
0x18001fbae  cmp     esi, r12d
0x18001fbb1  jz      short loc_18001FBB8
0x18001fbb3  cmp     esi, 1
0x18001fbb6  jnz     short loc_18001FC00
0x18001fbb8  mov     edx, 1; fAbort
0x18001fbbd  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001fbc5  call    cs:__imp_RpcAsyncCancelCall
0x18001fbcb  cmp     esi, r12d
0x18001fbce  jnz     short loc_18001FBD5
0x18001fbd0  mov     r15b, 1
0x18001fbd3  jmp     short loc_18001FBD8
0x18001fbd5  mov     r14b, 1
0x18001fbd8  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001fbe0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001fbe4  xor     r8d, r8d; bWaitAll
0x18001fbe7  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001fbef  lea     ecx, [r8+1]; nCount
0x18001fbf3  call    cs:__imp_WaitForMultipleObjectsEx
0x18001fbf9  mov     esi, eax
0x18001fbfb  test    r15b, r15b
0x18001fbfe  jz      short loc_18001FBA9
0x18001fc00  test    esi, esi
0x18001fc02  jz      short loc_18001FC1F
0x18001fc04  call    cs:__imp_GetLastError
0x18001fc0a  test    eax, eax
0x18001fc0c  jle     short loc_18001FC16
0x18001fc0e  movzx   eax, ax
0x18001fc11  or      eax, 80070000h
0x18001fc16  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001fc1d  jmp     short loc_18001FC47
0x18001fc1f  lea     rdx, [rsp+138h+Reply]; Reply
0x18001fc24  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001fc2c  call    cs:__imp_RpcAsyncCompleteCall
0x18001fc32  test    eax, eax
0x18001fc34  jz      short loc_18001FC66
0x18001fc36  jle     short loc_18001FC40
0x18001fc38  movzx   eax, ax
0x18001fc3b  or      eax, 80070000h
0x18001fc40  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001fc47  mov     r8d, 557h; unsigned int
0x18001fc4d  mov     [rsp+138h+Reply], eax
0x18001fc51  mov     [rsp+138h+bAlertable], eax
0x18001fc55  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001fc5c  mov     ecx, 2; unsigned __int8
0x18001fc61  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001fc66  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18001fc6e  test    rcx, rcx
0x18001fc71  jz      short loc_18001FC79
0x18001fc73  call    cs:__imp_CloseHandle
0x18001fc79  test    r15b, r15b
0x18001fc7c  jz      short loc_18001FCB6
0x18001fc7e  mov     [rsp+138h+Reply], 800705B4h
0x18001fc86  lea     rdx, [rsp+138h+var_DC]
0x18001fc8b  call    ??$RPCCallTimedOut@AEAY0CA@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0CA@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[32],ulong &>(char const (&)[32],ulong &)
0x18001fc90  mov     eax, [rsp+138h+Reply]
0x18001fc94  mov     [rsp+138h+bAlertable], eax
0x18001fc98  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001fc9f  mov     r8d, 557h; unsigned int
0x18001fca5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001fcac  mov     ecx, 2; unsigned __int8
0x18001fcb1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001fcb6  test    r14b, r14b
0x18001fcb9  jz      short loc_18001FCE6
0x18001fcbb  mov     eax, 800704C7h
0x18001fcc0  mov     [rsp+138h+Reply], eax
0x18001fcc4  mov     [rsp+138h+bAlertable], eax
0x18001fcc8  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001fccf  mov     r8d, 557h; unsigned int
0x18001fcd5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001fcdc  mov     ecx, 2; unsigned __int8
0x18001fce1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001fce6  cmp     [rsp+138h+Reply], 800706B5h
0x18001fcee  jz      short loc_18001FCFA
0x18001fcf0  cmp     [rsp+138h+Reply], 800706BAh
0x18001fcf8  jnz     short loc_18001FCFF
0x18001fcfa  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001fcff  lea     rcx, [rsp+138h+var_D8]; this
0x18001fd04  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001fd09  mov     eax, [rsp+138h+Reply]
0x18001fd0d  mov     rcx, [rsp+138h+var_38]
0x18001fd15  xor     rcx, rsp; StackCookie
0x18001fd18  call    __security_check_cookie
0x18001fd1d  add     rsp, 110h
0x18001fd24  pop     r15
0x18001fd26  pop     r14
0x18001fd28  pop     r13
0x18001fd2a  pop     r12
0x18001fd2c  pop     rsi
0x18001fd2d  retn
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
