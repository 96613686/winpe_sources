# WLIDCpGetConfigDWORDValue(ulong,ulong *)

- ea: `0x180006a78`
- end: `0x180006db6`
- name: `?WLIDCpGetConfigDWORDValue@@YAJKPEAK@Z`
- size: `830`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006a1c`

## callees

- `0x180001cb0`
- `0x1800028f0`
- `0x180003020`
- `0x180006304`
- `0x180006a78`
- `0x180007150`
- `0x18000730c`
- `0x180007334`
- `0x18000789c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c8a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006afc`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180006afc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006caf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006caf`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006ba0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180006ba0`
- `RPCRT4!RpcAsyncCancelCall` at `0x180006c4b`
- `RPCRT4!RpcAsyncCancelCall` at `0x180006c4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006b43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006b43`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006c27`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006c79`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006c27`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180006c79`

## string_xrefs

- `0x180006b68`: `RPC failed to create new event, hr = %#x`
- `0x180006cc3`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCpGetConfigDWORDValue(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  char v4; // r15
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  __int64 v11; // rdx
  __int64 v12; // r8
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-D8h]
  int Reply; // [rsp+40h] [rbp-B8h] BYREF
  char v16; // [rsp+44h] [rbp-B4h]
  int v17; // [rsp+48h] [rbp-B0h] BYREF
  RPC_BINDING_HANDLE v18; // [rsp+50h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-88h] BYREF

  v18 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v18);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v17 = 5000;
  v4 = 0;
  v16 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v8 = 362;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x36u, 0, &pAsync, v18, 3, a2);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v7 = L"RPC call failed, hr = %#x";
    v8 = 364;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      (PPTraceStatus *)2,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v8,
      v7,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x1388u, 0);
  do
  {
    if ( v5 || v10 != 258 && v10 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v10 == 258 )
      v4 = 1;
    else
      v5 = 1;
    v10 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v4 );
  if ( v10 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v8 = 364;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>((__int64)NotificationRoutine, &v17);
    bAlertable[0] = Reply;
    TracePrintW(
      (PPTraceStatus *)2,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      (PPTraceStatus *)2,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x16Cu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus((__int64)NotificationRoutine, v11, v12);
  CWLIDBinding::Unbind(&v18);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180006a78  mov     [rsp+arg_0], rsi
0x180006a7d  mov     [rsp+arg_10], r14
0x180006a82  push    r15
0x180006a84  sub     rsp, 0F0h
0x180006a8b  mov     rax, cs:__security_cookie
0x180006a92  xor     rax, rsp
0x180006a95  mov     [rsp+0F8h+var_18], rax
0x180006a9d  mov     rsi, rdx
0x180006aa0  mov     [rsp+0F8h+Reply], 0
0x180006aa8  mov     [rsp+0F8h+var_A8], 0
0x180006ab1  lea     rcx, [rsp+0F8h+var_A8]; this
0x180006ab6  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180006abb  mov     [rsp+0F8h+Reply], eax
0x180006abf  test    eax, eax
0x180006ac1  js      loc_180006D90
0x180006ac7  xor     edx, edx; Val
0x180006ac9  lea     r8d, [rdx+70h]; Size
0x180006acd  lea     rcx, [rsp+0F8h+pAsync]; void *
0x180006ad2  call    memset_0
0x180006ad7  mov     [rsp+0F8h+var_B0], 1388h
0x180006adf  xor     r15b, r15b
0x180006ae2  mov     [rsp+0F8h+var_B4], r15b
0x180006ae7  xor     r14b, r14b
0x180006aea  xorps   xmm0, xmm0
0x180006aed  movups  xmmword ptr [rsp+0F8h+Handles], xmm0
0x180006af2  mov     edx, 70h ; 'p'; Size
0x180006af7  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180006afc  call    cs:__imp_RpcAsyncInitializeHandle
0x180006b02  test    eax, eax
0x180006b04  jz      short loc_180006B22
0x180006b06  jle     short loc_180006B10
0x180006b08  movzx   eax, ax
0x180006b0b  or      eax, 80070000h
0x180006b10  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180006b17  mov     r8d, 16Ah
0x180006b1d  jmp     loc_180006CD0
0x180006b22  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x180006b2e  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x180006b39  xor     r9d, r9d; lpName
0x180006b3c  xor     r8d, r8d; bInitialState
0x180006b3f  xor     edx, edx; bManualReset
0x180006b41  xor     ecx, ecx; lpEventAttributes
0x180006b43  call    cs:__imp_CreateEventW
0x180006b49  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x180006b51  test    rax, rax
0x180006b54  jnz     short loc_180006B71
0x180006b56  call    cs:__imp_GetLastError
0x180006b5c  test    eax, eax
0x180006b5e  jle     short loc_180006B68
0x180006b60  movzx   eax, ax
0x180006b63  or      eax, 80070000h
0x180006b68  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180006b6f  jmp     short loc_180006B17
0x180006b71  mov     [rsp+0F8h+Handles], rax
0x180006b76  mov     [rsp+0F8h+var_C8], rsi
0x180006b7b  mov     [rsp+0F8h+var_D0], 3
0x180006b83  mov     rax, [rsp+0F8h+var_A8]
0x180006b88  mov     qword ptr [rsp+0F8h+bAlertable], rax
0x180006b8d  lea     r9, [rsp+0F8h+pAsync]
0x180006b92  xor     r8d, r8d; pReturnValue
0x180006b95  lea     edx, [r8+36h]; nProcNum
0x180006b99  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006ba0  call    cs:__imp_Ndr64AsyncClientCall
0x180006ba6  mov     eax, [rsp+0F8h+Reply]
0x180006baa  jmp     short loc_180006BF7
0x180006bac  test    eax, eax
0x180006bae  jle     short loc_180006BB8
0x180006bb0  movzx   eax, ax
0x180006bb3  or      eax, 80070000h
0x180006bb8  mov     [rsp+0F8h+Reply], eax
0x180006bbc  mov     [rsp+0F8h+bAlertable], eax
0x180006bc0  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180006bc7  mov     r8d, 16Ch; unsigned int
0x180006bcd  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006bd4  mov     ecx, 2; unsigned __int8
0x180006bd9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006bde  mov     eax, [rsp+0F8h+Reply]
0x180006be2  test    eax, eax
0x180006be4  js      short loc_180006BEF
0x180006be6  mov     eax, 8000FFFFh
0x180006beb  mov     [rsp+0F8h+Reply], eax
0x180006bef  mov     r15b, [rsp+0F8h+var_B4]
0x180006bf4  mov     r14b, r15b
0x180006bf7  test    eax, eax
0x180006bf9  jns     short loc_180006C0D
0x180006bfb  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180006c02  mov     r8d, 16Ch
0x180006c08  jmp     loc_180006CD4
0x180006c0d  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180006c15  mov     r9d, 1388h; dwMilliseconds
0x180006c1b  xor     r8d, r8d; bWaitAll
0x180006c1e  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180006c23  lea     ecx, [r8+1]; nCount
0x180006c27  call    cs:__imp_WaitForMultipleObjectsEx
0x180006c2d  mov     esi, eax
0x180006c2f  test    r14b, r14b
0x180006c32  jnz     short loc_180006C86
0x180006c34  cmp     esi, 102h
0x180006c3a  jz      short loc_180006C41
0x180006c3c  cmp     esi, 1
0x180006c3f  jnz     short loc_180006C86
0x180006c41  mov     edx, 1; fAbort
0x180006c46  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180006c4b  call    cs:__imp_RpcAsyncCancelCall
0x180006c51  cmp     esi, 102h
0x180006c57  jnz     short loc_180006C5E
0x180006c59  mov     r15b, 1
0x180006c5c  jmp     short loc_180006C61
0x180006c5e  mov     r14b, 1
0x180006c61  mov     [rsp+0F8h+bAlertable], 0; bAlertable
0x180006c69  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180006c6d  xor     r8d, r8d; bWaitAll
0x180006c70  lea     rdx, [rsp+0F8h+Handles]; lpHandles
0x180006c75  lea     ecx, [r8+1]; nCount
0x180006c79  call    cs:__imp_WaitForMultipleObjectsEx
0x180006c7f  mov     esi, eax
0x180006c81  test    r15b, r15b
0x180006c84  jz      short loc_180006C2F
0x180006c86  test    esi, esi
0x180006c88  jz      short loc_180006CA5
0x180006c8a  call    cs:__imp_GetLastError
0x180006c90  test    eax, eax
0x180006c92  jle     short loc_180006C9C
0x180006c94  movzx   eax, ax
0x180006c97  or      eax, 80070000h
0x180006c9c  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180006ca3  jmp     short loc_180006CCA
0x180006ca5  lea     rdx, [rsp+0F8h+Reply]; Reply
0x180006caa  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x180006caf  call    cs:__imp_RpcAsyncCompleteCall
0x180006cb5  test    eax, eax
0x180006cb7  jz      short loc_180006CE9
0x180006cb9  jle     short loc_180006CC3
0x180006cbb  movzx   eax, ax
0x180006cbe  or      eax, 80070000h
0x180006cc3  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180006cca  mov     r8d, 16Ch; unsigned int
0x180006cd0  mov     [rsp+0F8h+Reply], eax
0x180006cd4  mov     [rsp+0F8h+bAlertable], eax
0x180006cd8  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006cdf  mov     ecx, 2; unsigned __int8
0x180006ce4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006ce9  mov     rcx, qword ptr [rsp+0F8h+pAsync.u]; hObject
0x180006cf1  test    rcx, rcx
0x180006cf4  jz      short loc_180006CFC
0x180006cf6  call    cs:__imp_CloseHandle
0x180006cfc  test    r15b, r15b
0x180006cff  jz      short loc_180006D39
0x180006d01  mov     [rsp+0F8h+Reply], 800705B4h
0x180006d09  lea     rdx, [rsp+0F8h+var_B0]
0x180006d0e  call    ??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)
0x180006d13  mov     eax, [rsp+0F8h+Reply]
0x180006d17  mov     [rsp+0F8h+bAlertable], eax
0x180006d1b  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180006d22  mov     r8d, 16Ch; unsigned int
0x180006d28  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006d2f  mov     ecx, 2; unsigned __int8
0x180006d34  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006d39  test    r14b, r14b
0x180006d3c  jz      short loc_180006D69
0x180006d3e  mov     eax, 800704C7h
0x180006d43  mov     [rsp+0F8h+Reply], eax
0x180006d47  mov     [rsp+0F8h+bAlertable], eax
0x180006d4b  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180006d52  mov     r8d, 16Ch; unsigned int
0x180006d58  lea     rdx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180006d5f  mov     ecx, 2; unsigned __int8
0x180006d64  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180006d69  cmp     [rsp+0F8h+Reply], 800706B5h
0x180006d71  jz      short loc_180006D7D
0x180006d73  cmp     [rsp+0F8h+Reply], 800706BAh
0x180006d7b  jnz     short loc_180006D82
0x180006d7d  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180006d82  lea     rcx, [rsp+0F8h+var_A8]; this
0x180006d87  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180006d8c  mov     eax, [rsp+0F8h+Reply]
0x180006d90  mov     rcx, [rsp+0F8h+var_18]
0x180006d98  xor     rcx, rsp; StackCookie
0x180006d9b  call    __security_check_cookie
0x180006da0  lea     r11, [rsp+0F8h+var_8]
0x180006da8  mov     rsi, [r11+10h]
0x180006dac  mov     r14, [r11+20h]
0x180006db0  mov     rsp, r11
0x180006db3  pop     r15
0x180006db5  retn
0x180008d7f  push    rbp
0x180008d81  sub     rsp, 40h
0x180008d85  mov     rbp, rdx
0x180008d88  mov     rcx, [rcx]
0x180008d8b  mov     ecx, [rcx]; unsigned int
0x180008d8d  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180008d92  nop
0x180008d93  add     rsp, 40h
0x180008d97  pop     rbp
0x180008d98  retn
```
