# WLIDCGetIdentityProperty(void * const,ushort const *,ushort * *)

- ea: `0x18001eef0`
- end: `0x18001f21f`
- name: `?WLIDCGetIdentityProperty@@YAJQEAXPEBGPEAPEAG@Z`
- size: `815`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019760`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019f4c`
- `0x18001ba00`
- `0x18001eef0`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f09a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f0ec`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f09a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f0ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001efb8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001efb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f169`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f012`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f012`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f122`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f122`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ef71`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001ef71`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f0c1`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f0c1`

## string_xrefs

- `0x18001efdd`: `RPC failed to create new event, hr = %#x`
- `0x18001f136`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetIdentityProperty(void *const a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  DWORD v5; // esi
  char v6; // r15
  char v7; // r14
  int LastError; // eax
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v12; // esi
  __int64 result; // rax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-F8h]
  unsigned int Reply; // [rsp+40h] [rbp-D8h] BYREF
  char v16; // [rsp+44h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+48h] [rbp-D0h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-CCh] BYREF
  unsigned __int16 **v19; // [rsp+50h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+58h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-A8h] BYREF

  v19 = a3;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
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
LABEL_5:
    v10 = 786;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x16u, 0, &pAsync, a1, a2, v19);
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
  v10 = 788;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v10, v9, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v6 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],unsigned long &>(
      (__int64)"WLIDCGetIdentityProperty",
      (int *)&v18);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x314u,
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
      0x314u,
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
0x18001eef0  push    rsi
0x18001eef2  push    r12
0x18001eef4  push    r13
0x18001eef6  push    r14
0x18001eef8  push    r15
0x18001eefa  sub     rsp, 0F0h
0x18001ef01  mov     rax, cs:__security_cookie
0x18001ef08  xor     rax, rsp
0x18001ef0b  mov     [rsp+118h+var_38], rax
0x18001ef13  mov     [rsp+118h+var_C8], r8
0x18001ef18  mov     r13, rdx
0x18001ef1b  mov     r12, rcx
0x18001ef1e  mov     [rsp+118h+Reply], 0
0x18001ef26  mov     [rsp+118h+dwMilliseconds], 0
0x18001ef2e  lea     r8, [rsp+118h+dwMilliseconds]; unsigned int *
0x18001ef33  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001ef38  xor     edx, edx; Val
0x18001ef3a  lea     r8d, [rdx+70h]; Size
0x18001ef3e  lea     rcx, [rsp+118h+pAsync]; void *
0x18001ef43  call    memset_0
0x18001ef48  mov     esi, [rsp+118h+dwMilliseconds]
0x18001ef4c  mov     [rsp+118h+dwMilliseconds], esi
0x18001ef50  mov     [rsp+118h+var_CC], esi
0x18001ef54  xor     r15b, r15b
0x18001ef57  mov     [rsp+118h+var_D4], r15b
0x18001ef5c  xor     r14b, r14b
0x18001ef5f  xorps   xmm0, xmm0
0x18001ef62  movups  xmmword ptr [rsp+118h+Handles], xmm0
0x18001ef67  mov     edx, 70h ; 'p'; Size
0x18001ef6c  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18001ef71  call    cs:__imp_RpcAsyncInitializeHandle
0x18001ef77  test    eax, eax
0x18001ef79  jz      short loc_18001EF97
0x18001ef7b  jle     short loc_18001EF85
0x18001ef7d  movzx   eax, ax
0x18001ef80  or      eax, 80070000h
0x18001ef85  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001ef8c  mov     r8d, 312h
0x18001ef92  jmp     loc_18001F143
0x18001ef97  mov     [rsp+118h+pAsync.UserInfo], 0
0x18001efa3  mov     [rsp+118h+pAsync.NotificationType], 1
0x18001efae  xor     r9d, r9d; lpName
0x18001efb1  xor     r8d, r8d; bInitialState
0x18001efb4  xor     edx, edx; bManualReset
0x18001efb6  xor     ecx, ecx; lpEventAttributes
0x18001efb8  call    cs:__imp_CreateEventW
0x18001efbe  mov     qword ptr [rsp+118h+pAsync.u], rax
0x18001efc6  test    rax, rax
0x18001efc9  jnz     short loc_18001EFE6
0x18001efcb  call    cs:__imp_GetLastError
0x18001efd1  test    eax, eax
0x18001efd3  jle     short loc_18001EFDD
0x18001efd5  movzx   eax, ax
0x18001efd8  or      eax, 80070000h
0x18001efdd  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001efe4  jmp     short loc_18001EF8C
0x18001efe6  mov     [rsp+118h+Handles], rax
0x18001efeb  mov     rax, [rsp+118h+var_C8]
0x18001eff0  mov     [rsp+118h+var_E8], rax
0x18001eff5  mov     [rsp+118h+var_F0], r13
0x18001effa  mov     qword ptr [rsp+118h+bAlertable], r12
0x18001efff  lea     r9, [rsp+118h+pAsync]
0x18001f004  xor     r8d, r8d; pReturnValue
0x18001f007  lea     edx, [r8+16h]; nProcNum
0x18001f00b  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001f012  call    cs:__imp_Ndr64AsyncClientCall
0x18001f018  mov     eax, [rsp+118h+Reply]
0x18001f01c  jmp     short loc_18001F06D
0x18001f01e  test    eax, eax
0x18001f020  jle     short loc_18001F02A
0x18001f022  movzx   eax, ax
0x18001f025  or      eax, 80070000h
0x18001f02a  mov     [rsp+118h+Reply], eax
0x18001f02e  mov     [rsp+118h+bAlertable], eax
0x18001f032  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001f039  mov     r8d, 314h; unsigned int
0x18001f03f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f046  mov     ecx, 2; unsigned __int8
0x18001f04b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f050  mov     eax, [rsp+118h+Reply]
0x18001f054  test    eax, eax
0x18001f056  js      short loc_18001F061
0x18001f058  mov     eax, 8000FFFFh
0x18001f05d  mov     [rsp+118h+Reply], eax
0x18001f061  mov     esi, [rsp+118h+dwMilliseconds]
0x18001f065  mov     r15b, [rsp+118h+var_D4]
0x18001f06a  mov     r14b, r15b
0x18001f06d  test    eax, eax
0x18001f06f  jns     short loc_18001F083
0x18001f071  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001f078  mov     r8d, 314h
0x18001f07e  jmp     loc_18001F147
0x18001f083  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18001f08b  mov     r9d, esi; dwMilliseconds
0x18001f08e  xor     r8d, r8d; bWaitAll
0x18001f091  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18001f096  lea     ecx, [r8+1]; nCount
0x18001f09a  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f0a0  mov     esi, eax
0x18001f0a2  mov     r12d, 102h
0x18001f0a8  test    r14b, r14b
0x18001f0ab  jnz     short loc_18001F0F9
0x18001f0ad  cmp     esi, r12d
0x18001f0b0  jz      short loc_18001F0B7
0x18001f0b2  cmp     esi, 1
0x18001f0b5  jnz     short loc_18001F0F9
0x18001f0b7  mov     edx, 1; fAbort
0x18001f0bc  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18001f0c1  call    cs:__imp_RpcAsyncCancelCall
0x18001f0c7  cmp     esi, r12d
0x18001f0ca  jnz     short loc_18001F0D1
0x18001f0cc  mov     r15b, 1
0x18001f0cf  jmp     short loc_18001F0D4
0x18001f0d1  mov     r14b, 1
0x18001f0d4  mov     [rsp+118h+bAlertable], 0; bAlertable
0x18001f0dc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001f0e0  xor     r8d, r8d; bWaitAll
0x18001f0e3  lea     rdx, [rsp+118h+Handles]; lpHandles
0x18001f0e8  lea     ecx, [r8+1]; nCount
0x18001f0ec  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f0f2  mov     esi, eax
0x18001f0f4  test    r15b, r15b
0x18001f0f7  jz      short loc_18001F0A8
0x18001f0f9  test    esi, esi
0x18001f0fb  jz      short loc_18001F118
0x18001f0fd  call    cs:__imp_GetLastError
0x18001f103  test    eax, eax
0x18001f105  jle     short loc_18001F10F
0x18001f107  movzx   eax, ax
0x18001f10a  or      eax, 80070000h
0x18001f10f  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001f116  jmp     short loc_18001F13D
0x18001f118  lea     rdx, [rsp+118h+Reply]; Reply
0x18001f11d  lea     rcx, [rsp+118h+pAsync]; pAsync
0x18001f122  call    cs:__imp_RpcAsyncCompleteCall
0x18001f128  test    eax, eax
0x18001f12a  jz      short loc_18001F15C
0x18001f12c  jle     short loc_18001F136
0x18001f12e  movzx   eax, ax
0x18001f131  or      eax, 80070000h
0x18001f136  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001f13d  mov     r8d, 314h; unsigned int
0x18001f143  mov     [rsp+118h+Reply], eax
0x18001f147  mov     [rsp+118h+bAlertable], eax
0x18001f14b  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f152  mov     ecx, 2; unsigned __int8
0x18001f157  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f15c  mov     rcx, qword ptr [rsp+118h+pAsync.u]; hObject
0x18001f164  test    rcx, rcx
0x18001f167  jz      short loc_18001F16F
0x18001f169  call    cs:__imp_CloseHandle
0x18001f16f  test    r15b, r15b
0x18001f172  jz      short loc_18001F1B3
0x18001f174  mov     [rsp+118h+Reply], 800705B4h
0x18001f17c  lea     rdx, [rsp+118h+var_CC]
0x18001f181  lea     rcx, aWlidcgetidenti; "WLIDCGetIdentityProperty"
0x18001f188  call    ??$RPCCallTimedOut@AEAY0BJ@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BJ@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[25],ulong &>(char const (&)[25],ulong &)
0x18001f18d  mov     eax, [rsp+118h+Reply]
0x18001f191  mov     [rsp+118h+bAlertable], eax
0x18001f195  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001f19c  mov     r8d, 314h; unsigned int
0x18001f1a2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f1a9  mov     ecx, 2; unsigned __int8
0x18001f1ae  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f1b3  test    r14b, r14b
0x18001f1b6  jz      short loc_18001F1E3
0x18001f1b8  mov     eax, 800704C7h
0x18001f1bd  mov     [rsp+118h+Reply], eax
0x18001f1c1  mov     [rsp+118h+bAlertable], eax
0x18001f1c5  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001f1cc  mov     r8d, 314h; unsigned int
0x18001f1d2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f1d9  mov     ecx, 2; unsigned __int8
0x18001f1de  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f1e3  mov     eax, [rsp+118h+Reply]
0x18001f1e7  cmp     eax, 800706B5h
0x18001f1ec  jz      short loc_18001F1F5
0x18001f1ee  cmp     eax, 800706BAh
0x18001f1f3  jnz     short loc_18001F1FE
0x18001f1f5  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001f1fa  mov     eax, [rsp+118h+Reply]
0x18001f1fe  mov     rcx, [rsp+118h+var_38]
0x18001f206  xor     rcx, rsp; StackCookie
0x18001f209  call    __security_check_cookie
0x18001f20e  add     rsp, 0F0h
0x18001f215  pop     r15
0x18001f217  pop     r14
0x18001f219  pop     r13
0x18001f21b  pop     r12
0x18001f21d  pop     rsi
0x18001f21e  retn
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
