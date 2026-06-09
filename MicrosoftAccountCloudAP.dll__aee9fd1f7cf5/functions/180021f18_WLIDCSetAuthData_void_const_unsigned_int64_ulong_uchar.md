# WLIDCSetAuthData(void * const,unsigned __int64,ulong,uchar *)

- ea: `0x180021f18`
- end: `0x180022254`
- name: `?WLIDCSetAuthData@@YAJQEAX_KKPEAE@Z`
- size: `828`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019950`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019afc`
- `0x18001ba00`
- `0x180020750`
- `0x180021f18`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800220cf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022121`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800220cf`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022121`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021fe5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002219e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002219e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022047`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180022047`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022157`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022157`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021f9e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180021f9e`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800220f6`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800220f6`

## string_xrefs

- `0x18002200a`: `RPC failed to create new event, hr = %#x`
- `0x18002216b`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCSetAuthData(void *const a1, __int64 a2, int a3, unsigned __int8 *a4)
{
  DWORD v6; // esi
  char v7; // r15
  char v8; // r14
  int LastError; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v13; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  int v19; // [rsp+4Ch] [rbp-CCh]
  DWORD v20; // [rsp+50h] [rbp-C8h] BYREF
  unsigned __int8 *v21; // [rsp+58h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v21 = a4;
  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v6 = dwMilliseconds;
  v20 = dwMilliseconds;
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
LABEL_5:
    v11 = 610;
    goto LABEL_27;
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
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xCu, 0, &pAsync, a1, a2, v19, v21);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = L"RPC Async complete call failed, hr = %#x";
  }
  v11 = 612;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v11,
    v10,
    *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v7 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],unsigned long &>(
      (__int64)"WLIDCSetAuthData",
      (int *)&v20);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x264u,
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
      0x264u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  result = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    return Reply;
  }
  return result;
}

```

## disassembly

```asm
0x180021f18  push    rsi
0x180021f1a  push    r12
0x180021f1c  push    r13
0x180021f1e  push    r14
0x180021f20  push    r15
0x180021f22  sub     rsp, 0F0h
0x180021f29  mov     rax, cs:__security_cookie
0x180021f30  xor     rax, rsp
0x180021f33  mov     [rsp+118h+var_38], rax
0x180021f3b  mov     [rsp+118h+var_C0], r9
0x180021f40  mov     [rsp+118h+var_CC], r8d
0x180021f45  mov     r13, rdx
0x180021f48  mov     r12, rcx
0x180021f4b  mov     [rsp+118h+Reply], 0
0x180021f53  mov     [rsp+118h+dwMilliseconds], 0
0x180021f5b  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180021f60  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180021f65  xor     edx, edx; Val
0x180021f67  lea     r8d, [rdx+70h]; Size
0x180021f6b  lea     rcx, [rsp+118h+pAsync]; void *
0x180021f70  call    memset_0
0x180021f75  mov     esi, [rsp+118h+dwMilliseconds]
0x180021f79  mov     [rsp+118h+dwMilliseconds], esi
0x180021f7d  mov     [rsp+118h+var_C8], esi
0x180021f81  xor     r15b, r15b
0x180021f84  mov     [rsp+118h+var_D4], r15b
0x180021f89  xor     r14b, r14b
0x180021f8c  xorps   xmm0, xmm0
0x180021f8f  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180021f94  mov     edx, 70h ; 'p'; Size
0x180021f99  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180021f9e  call    cs:__imp_RpcAsyncInitializeHandle
0x180021fa4  test    eax, eax
0x180021fa6  jz      short loc_180021FC4
0x180021fa8  jle     short loc_180021FB2
0x180021faa  movzx   eax, ax
0x180021fad  or      eax, 80070000h
0x180021fb2  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180021fb9  mov     r8d, 262h
0x180021fbf  jmp     loc_180022178
0x180021fc4  mov     [rsp+118h+pAsync.UserInfo], 0
0x180021fd0  mov     [rsp+118h+pAsync.NotificationType], 1
0x180021fdb  xor     r9d, r9d; lpName
0x180021fde  xor     r8d, r8d; bInitialState
0x180021fe1  xor     edx, edx; bManualReset
0x180021fe3  xor     ecx, ecx; lpEventAttributes
0x180021fe5  call    cs:__imp_CreateEventW
0x180021feb  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180021ff3  test    rax, rax
0x180021ff6  jnz     short loc_180022013
0x180021ff8  call    cs:__imp_GetLastError
0x180021ffe  test    eax, eax
0x180022000  jle     short loc_18002200A
0x180022002  movzx   eax, ax
0x180022005  or      eax, 80070000h
0x18002200a  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180022011  jmp     short loc_180021FB9
0x180022013  mov     [rsp+118h+Handles], rax
0x180022018  mov     rax, [rsp+118h+var_C0]
0x18002201d  mov     [rsp+118h+var_E0], rax
0x180022022  mov     eax, [rsp+118h+var_CC]
0x180022026  mov     [rsp+118h+var_E8], eax
0x18002202a  mov     [rsp+118h+var_F0], r13
0x18002202f  mov     qword ptr [rsp+118h+bAlertable], r12
0x180022034  lea     r9, [rsp+118h+pAsync]
0x180022039  xor     r8d, r8d; pReturnValue
0x18002203c  lea     edx, [r8+0Ch]; nProcNum
0x180022040  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180022047  call    cs:__imp_Ndr64AsyncClientCall
0x18002204d  mov     eax, [rsp+118h+Reply]
0x180022051  jmp     short loc_1800220A2
0x180022053  test    eax, eax
0x180022055  jle     short loc_18002205F
0x180022057  movzx   eax, ax
0x18002205a  or      eax, 80070000h
0x18002205f  mov     [rsp+118h+Reply], eax
0x180022063  mov     [rsp+118h+bAlertable], eax
0x180022067  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18002206e  mov     r8d, 264h; unsigned int
0x180022074  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002207b  mov     ecx, 2; unsigned __int8
0x180022080  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022085  mov     eax, [rsp+118h+Reply]
0x180022089  test    eax, eax
0x18002208b  js      short loc_180022096
0x18002208d  mov     eax, 8000FFFFh
0x180022092  mov     [rsp+118h+Reply], eax
0x180022096  mov     esi, [rsp+118h+dwMilliseconds]
0x18002209a  mov     r15b, [rsp+118h+var_D4]
0x18002209f  mov     r14b, r15b
0x1800220a2  test    eax, eax
0x1800220a4  jns     short loc_1800220B8
0x1800220a6  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x1800220ad  mov     r8d, 264h
0x1800220b3  jmp     loc_18002217C
0x1800220b8  mov     [rsp+118h+bAlertable], 0; bAlertable
0x1800220c0  mov     r9d, esi; dwMilliseconds
0x1800220c3  xor     r8d, r8d; bWaitAll
0x1800220c6  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1800220cb  lea     ecx, [r8+1]; nCount
0x1800220cf  call    cs:__imp_WaitForMultipleObjectsEx
0x1800220d5  mov     esi, eax
0x1800220d7  mov     r12d, 102h
0x1800220dd  test    r14b, r14b
0x1800220e0  jnz     short loc_18002212E
0x1800220e2  cmp     esi, r12d
0x1800220e5  jz      short loc_1800220EC
0x1800220e7  cmp     esi, 1
0x1800220ea  jnz     short loc_18002212E
0x1800220ec  mov     edx, 1; fAbort
0x1800220f1  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800220f6  call    cs:__imp_RpcAsyncCancelCall
0x1800220fc  cmp     esi, r12d
0x1800220ff  jnz     short loc_180022106
0x180022101  mov     r15b, 1
0x180022104  jmp     short loc_180022109
0x180022106  mov     r14b, 1
0x180022109  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180022111  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180022115  xor     r8d, r8d; bWaitAll
0x180022118  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18002211d  lea     ecx, [r8+1]; nCount
0x180022121  call    cs:__imp_WaitForMultipleObjectsEx
0x180022127  mov     esi, eax
0x180022129  test    r15b, r15b
0x18002212c  jz      short loc_1800220DD
0x18002212e  test    esi, esi
0x180022130  jz      short loc_18002214D
0x180022132  call    cs:__imp_GetLastError
0x180022138  test    eax, eax
0x18002213a  jle     short loc_180022144
0x18002213c  movzx   eax, ax
0x18002213f  or      eax, 80070000h
0x180022144  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18002214b  jmp     short loc_180022172
0x18002214d  lea     rdx, [rsp+118h+Reply]; Reply
0x180022152  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180022157  call    cs:__imp_RpcAsyncCompleteCall
0x18002215d  test    eax, eax
0x18002215f  jz      short loc_180022191
0x180022161  jle     short loc_18002216B
0x180022163  movzx   eax, ax
0x180022166  or      eax, 80070000h
0x18002216b  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x180022172  mov     r8d, 264h; unsigned int
0x180022178  mov     [rsp+118h+Reply], eax
0x18002217c  mov     [rsp+118h+bAlertable], eax
0x180022180  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180022187  mov     ecx, 2; unsigned __int8
0x18002218c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022191  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x180022199  test    rcx, rcx
0x18002219c  jz      short loc_1800221A4
0x18002219e  call    cs:__imp_CloseHandle
0x1800221a4  test    r15b, r15b
0x1800221a7  jz      short loc_1800221E8
0x1800221a9  mov     [rsp+118h+Reply], 800705B4h
0x1800221b1  lea     rdx, [rsp+118h+var_C8]
0x1800221b6  lea     rcx, aWlidcsetauthda; "WLIDCSetAuthData"
0x1800221bd  call    ??$RPCCallTimedOut@AEAY0BB@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BB@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[17],ulong &>(char const (&)[17],ulong &)
0x1800221c2  mov     eax, [rsp+118h+Reply]
0x1800221c6  mov     [rsp+118h+bAlertable], eax
0x1800221ca  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800221d1  mov     r8d, 264h; unsigned int
0x1800221d7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800221de  mov     ecx, 2; unsigned __int8
0x1800221e3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800221e8  test    r14b, r14b
0x1800221eb  jz      short loc_180022218
0x1800221ed  mov     eax, 800704C7h
0x1800221f2  mov     [rsp+118h+Reply], eax
0x1800221f6  mov     [rsp+118h+bAlertable], eax
0x1800221fa  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180022201  mov     r8d, 264h; unsigned int
0x180022207  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002220e  mov     ecx, 2; unsigned __int8
0x180022213  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180022218  mov     eax, [rsp+118h+Reply]
0x18002221c  cmp     eax, 800706B5h
0x180022221  jz      short loc_18002222A
0x180022223  cmp     eax, 800706BAh
0x180022228  jnz     short loc_180022233
0x18002222a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18002222f  mov     eax, [rsp+118h+Reply]
0x180022233  mov     rcx, [rsp+118h+var_38]
0x18002223b  xor     rcx, rsp; StackCookie
0x18002223e  call    __security_check_cookie
0x180022243  add     rsp, 0F0h
0x18002224a  pop     r15
0x18002224c  pop     r14
0x18002224e  pop     r13
0x180022250  pop     r12
0x180022252  pop     rsi
0x180022253  retn
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
