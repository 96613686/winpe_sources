# WLIDCHasPersistedCredential(void * const,ushort const *,int *)

- ea: `0x180020e7c`
- end: `0x1800211a4`
- name: `?WLIDCHasPersistedCredential@@YAJQEAXPEBGPEAH@Z`
- size: `808`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800198b0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18001a064`
- `0x18001ba00`
- `0x180020750`
- `0x180020e7c`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021026`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021078`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021026`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180021078`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f44`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800210f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800210f5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020f9e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020f9e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800210ae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800210ae`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020efd`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180020efd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002104d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18002104d`

## string_xrefs

- `0x180020f69`: `RPC failed to create new event, hr = %#x`
- `0x1800210c2`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCHasPersistedCredential(void *const a1, const unsigned __int16 *a2, int *a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v17; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-CCh] BYREF
  int *v20; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v20 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = dwMilliseconds;
  v19 = dwMilliseconds;
  v6 = 0;
  v17 = 0;
  v7 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v10 = 823;
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
    v9 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x1Au, 0, &pAsync, a1, a2, v20);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = L"RPC Async complete call failed, hr = %#x";
  }
  v10 = 825;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x339u,
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
      0x339u,
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
0x180020e7c  push    rsi
0x180020e7e  push    r12
0x180020e80  push    r13
0x180020e82  push    r14
0x180020e84  push    r15
0x180020e86  sub     rsp, 0F0h
0x180020e8d  mov     rax, cs:__security_cookie
0x180020e94  xor     rax, rsp
0x180020e97  mov     [rsp+118h+var_38], rax
0x180020e9f  mov     [rsp+118h+var_C8], r8
0x180020ea4  mov     r13, rdx
0x180020ea7  mov     r12, rcx
0x180020eaa  mov     [rsp+118h+Reply], 0
0x180020eb2  mov     [rsp+118h+dwMilliseconds], 0
0x180020eba  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x180020ebf  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x180020ec4  xor     edx, edx; Val
0x180020ec6  lea     r8d, [rdx+70h]; Size
0x180020eca  lea     rcx, [rsp+118h+pAsync]; void *
0x180020ecf  call    memset_0
0x180020ed4  mov     esi, [rsp+118h+dwMilliseconds]
0x180020ed8  mov     [rsp+118h+dwMilliseconds], esi
0x180020edc  mov     [rsp+118h+var_CC], esi
0x180020ee0  xor     r15b, r15b
0x180020ee3  mov     [rsp+118h+var_D4], r15b
0x180020ee8  xor     r14b, r14b
0x180020eeb  xorps   xmm0, xmm0
0x180020eee  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x180020ef3  mov     edx, 70h ; 'p'; Size
0x180020ef8  lea     rcx, [rsp+118h+pAsync]; pAsync
0x180020efd  call    cs:__imp_RpcAsyncInitializeHandle
0x180020f03  test    eax, eax
0x180020f05  jz      short loc_180020F23
0x180020f07  jle     short loc_180020F11
0x180020f09  movzx   eax, ax
0x180020f0c  or      eax, 80070000h
0x180020f11  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x180020f18  mov     r8d, 337h
0x180020f1e  jmp     loc_1800210CF
0x180020f23  mov     [rsp+118h+pAsync.UserInfo], 0
0x180020f2f  mov     [rsp+118h+pAsync.NotificationType], 1
0x180020f3a  xor     r9d, r9d; lpName
0x180020f3d  xor     r8d, r8d; bInitialState
0x180020f40  xor     edx, edx; bManualReset
0x180020f42  xor     ecx, ecx; lpEventAttributes
0x180020f44  call    cs:__imp_CreateEventW
0x180020f4a  mov     qword ptr [rsp+118h+pAsync.u], rax
0x180020f52  test    rax, rax
0x180020f55  jnz     short loc_180020F72
0x180020f57  call    cs:__imp_GetLastError
0x180020f5d  test    eax, eax
0x180020f5f  jle     short loc_180020F69
0x180020f61  movzx   eax, ax
0x180020f64  or      eax, 80070000h
0x180020f69  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x180020f70  jmp     short loc_180020F18
0x180020f72  mov     [rsp+118h+Handles], rax
0x180020f77  mov     rax, [rsp+118h+var_C8]
0x180020f7c  mov     [rsp+118h+var_E8], rax
0x180020f81  mov     [rsp+118h+var_F0], r13
0x180020f86  mov     qword ptr [rsp+118h+bAlertable], r12
0x180020f8b  lea     r9, [rsp+118h+pAsync]
0x180020f90  xor     r8d, r8d; pReturnValue
0x180020f93  lea     edx, [r8+1Ah]; nProcNum
0x180020f97  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180020f9e  call    cs:__imp_Ndr64AsyncClientCall
0x180020fa4  mov     eax, [rsp+118h+Reply]
0x180020fa8  jmp     short loc_180020FF9
0x180020faa  test    eax, eax
0x180020fac  jle     short loc_180020FB6
0x180020fae  movzx   eax, ax
0x180020fb1  or      eax, 80070000h
0x180020fb6  mov     [rsp+118h+Reply], eax
0x180020fba  mov     [rsp+118h+bAlertable], eax
0x180020fbe  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x180020fc5  mov     r8d, 339h; unsigned int
0x180020fcb  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020fd2  mov     ecx, 2; unsigned __int8
0x180020fd7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020fdc  mov     eax, [rsp+118h+Reply]
0x180020fe0  test    eax, eax
0x180020fe2  js      short loc_180020FED
0x180020fe4  mov     eax, 8000FFFFh
0x180020fe9  mov     [rsp+118h+Reply], eax
0x180020fed  mov     esi, [rsp+118h+dwMilliseconds]
0x180020ff1  mov     r15b, [rsp+118h+var_D4]
0x180020ff6  mov     r14b, r15b
0x180020ff9  test    eax, eax
0x180020ffb  jns     short loc_18002100F
0x180020ffd  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180021004  mov     r8d, 339h
0x18002100a  jmp     loc_1800210D3
0x18002100f  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180021017  mov     r9d, esi; dwMilliseconds
0x18002101a  xor     r8d, r8d; bWaitAll
0x18002101d  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180021022  lea     ecx, [r8+1]; nCount
0x180021026  call    cs:__imp_WaitForMultipleObjectsEx
0x18002102c  mov     esi, eax
0x18002102e  mov     r12d, 102h
0x180021034  test    r14b, r14b
0x180021037  jnz     short loc_180021085
0x180021039  cmp     esi, r12d
0x18002103c  jz      short loc_180021043
0x18002103e  cmp     esi, 1
0x180021041  jnz     short loc_180021085
0x180021043  mov     edx, 1; fAbort
0x180021048  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18002104d  call    cs:__imp_RpcAsyncCancelCall
0x180021053  cmp     esi, r12d
0x180021056  jnz     short loc_18002105D
0x180021058  mov     r15b, 1
0x18002105b  jmp     short loc_180021060
0x18002105d  mov     r14b, 1
0x180021060  mov     [rsp+118h+bAlertable], 0; bAlertable
0x180021068  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002106c  xor     r8d, r8d; bWaitAll
0x18002106f  lea     rdx, [rsp+118h+Handles]; lpHandles
0x180021074  lea     ecx, [r8+1]; nCount
0x180021078  call    cs:__imp_WaitForMultipleObjectsEx
0x18002107e  mov     esi, eax
0x180021080  test    r15b, r15b
0x180021083  jz      short loc_180021034
0x180021085  test    esi, esi
0x180021087  jz      short loc_1800210A4
0x180021089  call    cs:__imp_GetLastError
0x18002108f  test    eax, eax
0x180021091  jle     short loc_18002109B
0x180021093  movzx   eax, ax
0x180021096  or      eax, 80070000h
0x18002109b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x1800210a2  jmp     short loc_1800210C9
0x1800210a4  lea     rdx, [rsp+118h+Reply]; Reply
0x1800210a9  lea     rcx, [rsp+118h+pAsync]; pAsync
0x1800210ae  call    cs:__imp_RpcAsyncCompleteCall
0x1800210b4  test    eax, eax
0x1800210b6  jz      short loc_1800210E8
0x1800210b8  jle     short loc_1800210C2
0x1800210ba  movzx   eax, ax
0x1800210bd  or      eax, 80070000h
0x1800210c2  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x1800210c9  mov     r8d, 339h; unsigned int
0x1800210cf  mov     [rsp+118h+Reply], eax
0x1800210d3  mov     [rsp+118h+bAlertable], eax
0x1800210d7  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800210de  mov     ecx, 2; unsigned __int8
0x1800210e3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800210e8  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x1800210f0  test    rcx, rcx
0x1800210f3  jz      short loc_1800210FB
0x1800210f5  call    cs:__imp_CloseHandle
0x1800210fb  test    r15b, r15b
0x1800210fe  jz      short loc_180021138
0x180021100  mov     [rsp+118h+Reply], 800705B4h
0x180021108  lea     rdx, [rsp+118h+var_CC]
0x18002110d  call    ??$RPCCallTimedOut@AEAY0BM@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BM@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[28],ulong &>(char const (&)[28],ulong &)
0x180021112  mov     eax, [rsp+118h+Reply]
0x180021116  mov     [rsp+118h+bAlertable], eax
0x18002111a  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x180021121  mov     r8d, 339h; unsigned int
0x180021127  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002112e  mov     ecx, 2; unsigned __int8
0x180021133  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021138  test    r14b, r14b
0x18002113b  jz      short loc_180021168
0x18002113d  mov     eax, 800704C7h
0x180021142  mov     [rsp+118h+Reply], eax
0x180021146  mov     [rsp+118h+bAlertable], eax
0x18002114a  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x180021151  mov     r8d, 339h; unsigned int
0x180021157  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002115e  mov     ecx, 2; unsigned __int8
0x180021163  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180021168  mov     eax, [rsp+118h+Reply]
0x18002116c  cmp     eax, 800706B5h
0x180021171  jz      short loc_18002117A
0x180021173  cmp     eax, 800706BAh
0x180021178  jnz     short loc_180021183
0x18002117a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18002117f  mov     eax, [rsp+118h+Reply]
0x180021183  mov     rcx, [rsp+118h+var_38]
0x18002118b  xor     rcx, rsp; StackCookie
0x18002118e  call    __security_check_cookie
0x180021193  add     rsp, 0F0h
0x18002119a  pop     r15
0x18002119c  pop     r14
0x18002119e  pop     r13
0x1800211a0  pop     r12
0x1800211a2  pop     rsi
0x1800211a3  retn
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
