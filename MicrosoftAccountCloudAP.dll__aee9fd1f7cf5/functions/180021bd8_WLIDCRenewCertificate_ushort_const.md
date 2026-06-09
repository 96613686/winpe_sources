# WLIDCRenewCertificate(ushort const *)

- ea: `0x180021bd8`
- end: `0x180021f10`
- name: `?WLIDCRenewCertificate@@YAJPEBG@Z`
- size: `824`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019940`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019dac`
- `0x18001ba00`
- `0x180021bd8`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021d7a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021dcc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021d7a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021dcc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021ca0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021e49`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180021cf3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180021cf3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021e02`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021e02`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021c5c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021c5c`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021d9e`
- `RPCRT4!RpcAsyncCancelCall` at `0x180021d9e`

## string_xrefs

- `0x180021cc5`: `RPC failed to create new event, hr = %#x`
- `0x180021e16`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCRenewCertificate(const unsigned __int16 *a1)
{
  __int64 result; // rax
  char v3; // r15
  char v4; // r14
  int LastError; // eax
  const unsigned __int16 *v6; // r9
  unsigned int v7; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v9; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-C8h]
  int Reply; // [rsp+30h] [rbp-B8h] BYREF
  char v12; // [rsp+34h] [rbp-B4h]
  int v13; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-A8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-88h] BYREF

  v14 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v14);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v13 = 600000;
  v3 = 0;
  v12 = 0;
  v4 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v7 = 1217;
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
    v6 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&OnlineProviderCertInterface_ProxyInfo, 0, 0, &pAsync, v14, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v6 = L"RPC call failed, hr = %#x";
    v7 = 1219;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v7,
      v6,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0x927C0u, 0);
  do
  {
    if ( v4 || v9 != 258 && v9 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v9 == 258 )
      v3 = 1;
    else
      v4 = 1;
    v9 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v3 );
  if ( v9 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v7 = 1219;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v3 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],unsigned long &>((__int64)"WLIDCRenewCertificate", &v13);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4C3u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v4 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x4C3u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v14);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180021bd8  mov     [rsp+arg_8], rsi
0x180021bdd  mov     [rsp+arg_10], r14
0x180021be2  push    r15
0x180021be4  sub     rsp, 0E0h
0x180021beb  mov     rax, cs:__security_cookie
0x180021bf2  xor     rax, rsp
0x180021bf5  mov     [rsp+0E8h+var_18], rax
0x180021bfd  mov     rsi, rcx
0x180021c00  mov     [rsp+0E8h+Reply], 0
0x180021c08  mov     [rsp+0E8h+var_A8], 0
0x180021c11  lea     rcx, [rsp+0E8h+var_A8]; this
0x180021c16  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180021c1b  mov     [rsp+0E8h+Reply], eax
0x180021c1f  test    eax, eax
0x180021c21  js      loc_180021EEA
0x180021c27  xor     edx, edx; Val
0x180021c29  lea     r8d, [rdx+70h]; Size
0x180021c2d  lea     rcx, [rsp+0E8h+pAsync]; void *
0x180021c32  call    memset_0
0x180021c37  mov     [rsp+0E8h+var_B0], 927C0h
0x180021c3f  xor     r15b, r15b
0x180021c42  mov     [rsp+0E8h+var_B4], r15b
0x180021c47  xor     r14b, r14b
0x180021c4a  xorps   xmm0, xmm0
0x180021c4d  movups  xmmword ptr [rsp+0E8h+Handles], xmm0
0x180021c52  mov     edx, 70h ; 'p'; Size
0x180021c57  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180021c5c  call    cs:__imp_RpcAsyncInitializeHandle
0x180021c62  test    eax, eax
0x180021c64  jz      short loc_180021C82
0x180021c66  jle     short loc_180021C70
0x180021c68  movzx   eax, ax
0x180021c6b  or      eax, 80070000h
0x180021c70  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180021c77  mov     r8d, 4C1h
0x180021c7d  jmp     loc_180021E23
0x180021c82  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x180021c8b  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x180021c96  xor     r9d, r9d; lpName
0x180021c99  xor     r8d, r8d; bInitialState
0x180021c9c  xor     edx, edx; bManualReset
0x180021c9e  xor     ecx, ecx; lpEventAttributes
0x180021ca0  call    cs:__imp_CreateEventW
0x180021ca6  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x180021cae  test    rax, rax
0x180021cb1  jnz     short loc_180021CCE
0x180021cb3  call    cs:__imp_GetLastError
0x180021cb9  test    eax, eax
0x180021cbb  jle     short loc_180021CC5
0x180021cbd  movzx   eax, ax
0x180021cc0  or      eax, 80070000h
0x180021cc5  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180021ccc  jmp     short loc_180021C77
0x180021cce  mov     [rsp+0E8h+Handles], rax
0x180021cd3  mov     [rsp+0E8h+var_C0], rsi
0x180021cd8  mov     rax, [rsp+0E8h+var_A8]
0x180021cdd  mov     qword ptr [rsp+0E8h+bAlertable], rax
0x180021ce2  lea     r9, [rsp+0E8h+pAsync]
0x180021ce7  xor     r8d, r8d; pReturnValue
0x180021cea  xor     edx, edx; nProcNum
0x180021cec  lea     rcx, ?OnlineProviderCertInterface_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180021cf3  call    cs:__imp_Ndr64AsyncClientCall
0x180021cf9  mov     eax, [rsp+0E8h+Reply]
0x180021cfd  jmp     short loc_180021D4A
0x180021cff  test    eax, eax
0x180021d01  jle     short loc_180021D0B
0x180021d03  movzx   eax, ax
0x180021d06  or      eax, 80070000h
0x180021d0b  mov     [rsp+0E8h+Reply], eax
0x180021d0f  mov     [rsp+0E8h+bAlertable], eax
0x180021d13  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180021d1a  mov     r8d, 4C3h; unsigned int
0x180021d20  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021d27  mov     ecx, 2; unsigned __int8
0x180021d2c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021d31  mov     eax, [rsp+0E8h+Reply]
0x180021d35  test    eax, eax
0x180021d37  js      short loc_180021D42
0x180021d39  mov     eax, 8000FFFFh
0x180021d3e  mov     [rsp+0E8h+Reply], eax
0x180021d42  mov     r15b, [rsp+0E8h+var_B4]
0x180021d47  mov     r14b, r15b
0x180021d4a  test    eax, eax
0x180021d4c  jns     short loc_180021D60
0x180021d4e  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180021d55  mov     r8d, 4C3h
0x180021d5b  jmp     loc_180021E27
0x180021d60  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180021d68  mov     r9d, 927C0h; dwMilliseconds
0x180021d6e  xor     r8d, r8d; bWaitAll
0x180021d71  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180021d76  lea     ecx, [r8+1]; nCount
0x180021d7a  call    cs:__imp_WaitForMultipleObjectsEx
0x180021d80  mov     esi, eax
0x180021d82  test    r14b, r14b
0x180021d85  jnz     short loc_180021DD9
0x180021d87  cmp     esi, 102h
0x180021d8d  jz      short loc_180021D94
0x180021d8f  cmp     esi, 1
0x180021d92  jnz     short loc_180021DD9
0x180021d94  mov     edx, 1; fAbort
0x180021d99  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180021d9e  call    cs:__imp_RpcAsyncCancelCall
0x180021da4  cmp     esi, 102h
0x180021daa  jnz     short loc_180021DB1
0x180021dac  mov     r15b, 1
0x180021daf  jmp     short loc_180021DB4
0x180021db1  mov     r14b, 1
0x180021db4  mov     [rsp+0E8h+bAlertable], 0; bAlertable
0x180021dbc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180021dc0  xor     r8d, r8d; bWaitAll
0x180021dc3  lea     rdx, [rsp+0E8h+Handles]; lpHandles
0x180021dc8  lea     ecx, [r8+1]; nCount
0x180021dcc  call    cs:__imp_WaitForMultipleObjectsEx
0x180021dd2  mov     esi, eax
0x180021dd4  test    r15b, r15b
0x180021dd7  jz      short loc_180021D82
0x180021dd9  test    esi, esi
0x180021ddb  jz      short loc_180021DF8
0x180021ddd  call    cs:__imp_GetLastError
0x180021de3  test    eax, eax
0x180021de5  jle     short loc_180021DEF
0x180021de7  movzx   eax, ax
0x180021dea  or      eax, 80070000h
0x180021def  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180021df6  jmp     short loc_180021E1D
0x180021df8  lea     rdx, [rsp+0E8h+Reply]; Reply
0x180021dfd  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180021e02  call    cs:__imp_RpcAsyncCompleteCall
0x180021e08  test    eax, eax
0x180021e0a  jz      short loc_180021E3C
0x180021e0c  jle     short loc_180021E16
0x180021e0e  movzx   eax, ax
0x180021e11  or      eax, 80070000h
0x180021e16  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180021e1d  mov     r8d, 4C3h; unsigned int
0x180021e23  mov     [rsp+0E8h+Reply], eax
0x180021e27  mov     [rsp+0E8h+bAlertable], eax
0x180021e2b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021e32  mov     ecx, 2; unsigned __int8
0x180021e37  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021e3c  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hObject
0x180021e44  test    rcx, rcx
0x180021e47  jz      short loc_180021E4F
0x180021e49  call    cs:__imp_CloseHandle
0x180021e4f  test    r15b, r15b
0x180021e52  jz      short loc_180021E93
0x180021e54  mov     [rsp+0E8h+Reply], 800705B4h
0x180021e5c  lea     rdx, [rsp+0E8h+var_B0]
0x180021e61  lea     rcx, aWlidcrenewcert; "WLIDCRenewCertificate"
0x180021e68  call    ??$RPCCallTimedOut@AEAY0BG@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BG@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[22],ulong &>(char const (&)[22],ulong &)
0x180021e6d  mov     eax, [rsp+0E8h+Reply]
0x180021e71  mov     [rsp+0E8h+bAlertable], eax
0x180021e75  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180021e7c  mov     r8d, 4C3h; unsigned int
0x180021e82  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021e89  mov     ecx, 2; unsigned __int8
0x180021e8e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021e93  test    r14b, r14b
0x180021e96  jz      short loc_180021EC3
0x180021e98  mov     eax, 800704C7h
0x180021e9d  mov     [rsp+0E8h+Reply], eax
0x180021ea1  mov     [rsp+0E8h+bAlertable], eax
0x180021ea5  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180021eac  mov     r8d, 4C3h; unsigned int
0x180021eb2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180021eb9  mov     ecx, 2; unsigned __int8
0x180021ebe  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021ec3  cmp     [rsp+0E8h+Reply], 800706B5h
0x180021ecb  jz      short loc_180021ED7
0x180021ecd  cmp     [rsp+0E8h+Reply], 800706BAh
0x180021ed5  jnz     short loc_180021EDC
0x180021ed7  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x180021edc  lea     rcx, [rsp+0E8h+var_A8]; this
0x180021ee1  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180021ee6  mov     eax, [rsp+0E8h+Reply]
0x180021eea  mov     rcx, [rsp+0E8h+var_18]
0x180021ef2  xor     rcx, rsp; StackCookie
0x180021ef5  call    __security_check_cookie
0x180021efa  lea     r11, [rsp+0E8h+var_8]
0x180021f02  mov     rsi, [r11+18h]
0x180021f06  mov     r14, [r11+20h]
0x180021f0a  mov     rsp, r11
0x180021f0d  pop     r15
0x180021f0f  retn
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
