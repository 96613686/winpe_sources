# WLIDCDeleteContextEx(unsigned __int64,void * *)

- ea: `0x18001d770`
- end: `0x18001daaa`
- name: `?WLIDCDeleteContextEx@@YAJ_KPEAPEAX@Z`
- size: `826`
- prototype: `int(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800196b0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001d770`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d911`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d963`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d911`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d963`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d830`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9e0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d884`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d884`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d999`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d999`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001da7c`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001da7c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d7ec`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d7ec`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d935`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d935`

## string_xrefs

- `0x18001d855`: `RPC failed to create new event, hr = %#x`
- `0x18001d9ad`: `RPC Async complete call failed, hr = %#x`
- `0x18001d9f8`: `WLIDCDeleteContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCDeleteContextEx(unsigned int a1, void **a2)
{
  DWORD v3; // esi
  char v4; // r12
  char v5; // r14
  int LastError; // eax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v10; // esi
  int v11; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v15; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v17; // [rsp+3Ch] [rbp-CCh] BYREF
  void **v18; // [rsp+40h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  v18 = a2;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  memset_0(&pAsync, 0, sizeof(pAsync));
  v3 = dwMilliseconds;
  v17 = dwMilliseconds;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_5:
    v8 = 621;
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
    v7 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_5;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xDu, 0, &pAsync, 0, a2);
  v10 = WaitForMultipleObjectsEx(1u, Handles, 0, v3, 0);
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
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_28;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = L"RPC Async complete call failed, hr = %#x";
  }
  v8 = 623;
LABEL_27:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", v8, v7, *(_QWORD *)bAlertable);
LABEL_28:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v4 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCDeleteContextEx",
      (int *)&v17);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v5 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x26Fu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v11 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v11 = Reply;
  }
  if ( v11 < 0 )
  {
    RpcSsDestroyClientContext(a2);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d770  push    rsi
0x18001d772  push    r12
0x18001d774  push    r14
0x18001d776  push    r15
0x18001d778  sub     rsp, 0E8h
0x18001d77f  mov     rax, cs:__security_cookie
0x18001d786  xor     rax, rsp
0x18001d789  mov     [rsp+108h+var_38], rax
0x18001d791  mov     r15, rdx
0x18001d794  mov     [rsp+108h+var_C8], rdx
0x18001d799  mov     [rsp+108h+Reply], 0
0x18001d7a1  mov     [rsp+108h+dwMilliseconds], 0
0x18001d7a9  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x18001d7ae  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001d7b3  xor     edx, edx; Val
0x18001d7b5  lea     r8d, [rdx+70h]; Size
0x18001d7b9  lea     rcx, [rsp+108h+pAsync]; void *
0x18001d7be  call    memset_0
0x18001d7c3  mov     esi, [rsp+108h+dwMilliseconds]
0x18001d7c7  mov     [rsp+108h+dwMilliseconds], esi
0x18001d7cb  mov     [rsp+108h+var_CC], esi
0x18001d7cf  xor     r12b, r12b
0x18001d7d2  mov     [rsp+108h+var_D4], r12b
0x18001d7d7  xor     r14b, r14b
0x18001d7da  xorps   xmm0, xmm0
0x18001d7dd  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x18001d7e2  mov     edx, 70h ; 'p'; Size
0x18001d7e7  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001d7ec  call    cs:__imp_RpcAsyncInitializeHandle
0x18001d7f2  test    eax, eax
0x18001d7f4  jz      short loc_18001D812
0x18001d7f6  jle     short loc_18001D800
0x18001d7f8  movzx   eax, ax
0x18001d7fb  or      eax, 80070000h
0x18001d800  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001d807  mov     r8d, 26Dh
0x18001d80d  jmp     loc_18001D9BA
0x18001d812  mov     [rsp+108h+pAsync.UserInfo], 0
0x18001d81b  mov     [rsp+108h+pAsync.NotificationType], 1
0x18001d826  xor     r9d, r9d; lpName
0x18001d829  xor     r8d, r8d; bInitialState
0x18001d82c  xor     edx, edx; bManualReset
0x18001d82e  xor     ecx, ecx; lpEventAttributes
0x18001d830  call    cs:__imp_CreateEventW
0x18001d836  mov     qword ptr [rsp+108h+pAsync.u], rax
0x18001d83e  test    rax, rax
0x18001d841  jnz     short loc_18001D85E
0x18001d843  call    cs:__imp_GetLastError
0x18001d849  test    eax, eax
0x18001d84b  jle     short loc_18001D855
0x18001d84d  movzx   eax, ax
0x18001d850  or      eax, 80070000h
0x18001d855  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001d85c  jmp     short loc_18001D807
0x18001d85e  mov     [rsp+108h+Handles], rax
0x18001d863  mov     [rsp+108h+var_E0], r15
0x18001d868  mov     qword ptr [rsp+108h+bAlertable], 0
0x18001d871  lea     r9, [rsp+108h+pAsync]
0x18001d876  xor     r8d, r8d; pReturnValue
0x18001d879  lea     edx, [r8+0Dh]; nProcNum
0x18001d87d  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001d884  call    cs:__imp_Ndr64AsyncClientCall
0x18001d88a  mov     eax, [rsp+108h+Reply]
0x18001d88e  jmp     short loc_18001D8E4
0x18001d890  test    eax, eax
0x18001d892  jle     short loc_18001D89C
0x18001d894  movzx   eax, ax
0x18001d897  or      eax, 80070000h
0x18001d89c  mov     [rsp+108h+Reply], eax
0x18001d8a0  mov     [rsp+108h+bAlertable], eax
0x18001d8a4  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001d8ab  mov     r8d, 26Fh; unsigned int
0x18001d8b1  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d8b8  mov     ecx, 2; unsigned __int8
0x18001d8bd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d8c2  mov     eax, [rsp+108h+Reply]
0x18001d8c6  test    eax, eax
0x18001d8c8  js      short loc_18001D8D3
0x18001d8ca  mov     eax, 8000FFFFh
0x18001d8cf  mov     [rsp+108h+Reply], eax
0x18001d8d3  mov     esi, [rsp+108h+dwMilliseconds]
0x18001d8d7  mov     r12b, [rsp+108h+var_D4]
0x18001d8dc  mov     r14b, r12b
0x18001d8df  mov     r15, [rsp+108h+var_C8]
0x18001d8e4  test    eax, eax
0x18001d8e6  jns     short loc_18001D8FA
0x18001d8e8  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001d8ef  mov     r8d, 26Fh
0x18001d8f5  jmp     loc_18001D9BE
0x18001d8fa  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001d902  mov     r9d, esi; dwMilliseconds
0x18001d905  xor     r8d, r8d; bWaitAll
0x18001d908  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001d90d  lea     ecx, [r8+1]; nCount
0x18001d911  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d917  mov     esi, eax
0x18001d919  test    r14b, r14b
0x18001d91c  jnz     short loc_18001D970
0x18001d91e  cmp     esi, 102h
0x18001d924  jz      short loc_18001D92B
0x18001d926  cmp     esi, 1
0x18001d929  jnz     short loc_18001D970
0x18001d92b  mov     edx, 1; fAbort
0x18001d930  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001d935  call    cs:__imp_RpcAsyncCancelCall
0x18001d93b  cmp     esi, 102h
0x18001d941  jnz     short loc_18001D948
0x18001d943  mov     r12b, 1
0x18001d946  jmp     short loc_18001D94B
0x18001d948  mov     r14b, 1
0x18001d94b  mov     [rsp+108h+bAlertable], 0; bAlertable
0x18001d953  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001d957  xor     r8d, r8d; bWaitAll
0x18001d95a  lea     rdx, [rsp+108h+Handles]; lpHandles
0x18001d95f  lea     ecx, [r8+1]; nCount
0x18001d963  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d969  mov     esi, eax
0x18001d96b  test    r12b, r12b
0x18001d96e  jz      short loc_18001D919
0x18001d970  test    esi, esi
0x18001d972  jz      short loc_18001D98F
0x18001d974  call    cs:__imp_GetLastError
0x18001d97a  test    eax, eax
0x18001d97c  jle     short loc_18001D986
0x18001d97e  movzx   eax, ax
0x18001d981  or      eax, 80070000h
0x18001d986  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001d98d  jmp     short loc_18001D9B4
0x18001d98f  lea     rdx, [rsp+108h+Reply]; Reply
0x18001d994  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18001d999  call    cs:__imp_RpcAsyncCompleteCall
0x18001d99f  test    eax, eax
0x18001d9a1  jz      short loc_18001D9D3
0x18001d9a3  jle     short loc_18001D9AD
0x18001d9a5  movzx   eax, ax
0x18001d9a8  or      eax, 80070000h
0x18001d9ad  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001d9b4  mov     r8d, 26Fh; unsigned int
0x18001d9ba  mov     [rsp+108h+Reply], eax
0x18001d9be  mov     [rsp+108h+bAlertable], eax
0x18001d9c2  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d9c9  mov     ecx, 2; unsigned __int8
0x18001d9ce  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d9d3  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x18001d9db  test    rcx, rcx
0x18001d9de  jz      short loc_18001D9E6
0x18001d9e0  call    cs:__imp_CloseHandle
0x18001d9e6  test    r12b, r12b
0x18001d9e9  jz      short loc_18001DA2A
0x18001d9eb  mov     [rsp+108h+Reply], 800705B4h
0x18001d9f3  lea     rdx, [rsp+108h+var_CC]
0x18001d9f8  lea     rcx, aWlidcdeletecon; "WLIDCDeleteContextEx"
0x18001d9ff  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001da04  mov     eax, [rsp+108h+Reply]
0x18001da08  mov     [rsp+108h+bAlertable], eax
0x18001da0c  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001da13  mov     r8d, 26Fh; unsigned int
0x18001da19  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001da20  mov     ecx, 2; unsigned __int8
0x18001da25  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001da2a  test    r14b, r14b
0x18001da2d  jz      short loc_18001DA5A
0x18001da2f  mov     eax, 800704C7h
0x18001da34  mov     [rsp+108h+Reply], eax
0x18001da38  mov     [rsp+108h+bAlertable], eax
0x18001da3c  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001da43  mov     r8d, 26Fh; unsigned int
0x18001da49  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001da50  mov     ecx, 2; unsigned __int8
0x18001da55  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001da5a  mov     eax, [rsp+108h+Reply]
0x18001da5e  cmp     eax, 800706B5h
0x18001da63  jz      short loc_18001DA6C
0x18001da65  cmp     eax, 800706BAh
0x18001da6a  jnz     short loc_18001DA75
0x18001da6c  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001da71  mov     eax, [rsp+108h+Reply]
0x18001da75  test    eax, eax
0x18001da77  jns     short loc_18001DA89
0x18001da79  mov     rcx, r15; ContextHandle
0x18001da7c  call    cs:__imp_RpcSsDestroyClientContext
0x18001da82  mov     qword ptr [r15], 0
0x18001da89  xor     eax, eax
0x18001da8b  mov     rcx, [rsp+108h+var_38]
0x18001da93  xor     rcx, rsp; StackCookie
0x18001da96  call    __security_check_cookie
0x18001da9b  add     rsp, 0E8h
0x18001daa2  pop     r15
0x18001daa4  pop     r14
0x18001daa6  pop     r12
0x18001daa8  pop     rsi
0x18001daa9  retn
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
