# WLIDCGetKeyLatest(void * const,unsigned __int64,ushort const *,ushort * *,ushort * *,__int64 *)

- ea: `0x18001f228`
- end: `0x18001f5d9`
- name: `?WLIDCGetKeyLatest@@YAJQEAX_KPEBGPEAPEAG3PEA_J@Z`
- size: `945`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019780`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019b88`
- `0x18001ba00`
- `0x18001f228`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f446`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f49e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f446`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f49e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f33a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f51e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f51e`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f3bb`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f3bb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f4d7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f4d7`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001f2f3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001f2f3`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f470`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f470`

## string_xrefs

- `0x18001f35f`: `RPC failed to create new event, hr = %#x`
- `0x18001f4eb`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetKeyLatest(
        void *const a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        __int64 *a6)
{
  __int64 result; // rax
  DWORD v9; // esi
  char v10; // r15
  char v11; // r14
  int LastError; // eax
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v16; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-128h]
  int Reply; // [rsp+50h] [rbp-F8h] BYREF
  char v20; // [rsp+54h] [rbp-F4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-F0h] BYREF
  DWORD v22; // [rsp+5Ch] [rbp-ECh] BYREF
  __int64 v23; // [rsp+60h] [rbp-E8h] BYREF
  __int64 *v24; // [rsp+68h] [rbp-E0h]
  unsigned __int16 **v25; // [rsp+70h] [rbp-D8h]
  unsigned __int16 **v26; // [rsp+78h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+80h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+88h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-A8h] BYREF

  v26 = a4;
  v27 = a3;
  v25 = a5;
  v24 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v23 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v23);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v22 = dwMilliseconds;
  v10 = 0;
  v20 = 0;
  v11 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v14 = 1292;
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
    v13 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Cu, 0, &pAsync, a1, a2, v27, v26, v25, v24);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 1294;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v14,
      v13,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v16 = WaitForMultipleObjectsEx(1u, Handles, 0, v9, 0);
  do
  {
    if ( v11 || v16 != 258 && v16 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v16 == 258 )
      v10 = 1;
    else
      v11 = 1;
    v16 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v10 );
  if ( v16 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v14 = 1294;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v10 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v22);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x50Eu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v11 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x50Eu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v23);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18001f228  push    rsi
0x18001f22a  push    r12
0x18001f22c  push    r13
0x18001f22e  push    r14
0x18001f230  push    r15
0x18001f232  sub     rsp, 120h
0x18001f239  mov     rax, cs:__security_cookie
0x18001f240  xor     rax, rsp
0x18001f243  mov     [rsp+148h+var_38], rax
0x18001f24b  mov     [rsp+148h+var_D0], r9
0x18001f250  mov     [rsp+148h+var_C8], r8
0x18001f258  mov     r13, rdx
0x18001f25b  mov     r12, rcx
0x18001f25e  mov     rax, [rsp+148h+arg_20]
0x18001f266  mov     [rsp+148h+var_D8], rax
0x18001f26b  mov     rax, [rsp+148h+arg_28]
0x18001f273  mov     [rsp+148h+var_E0], rax
0x18001f278  mov     [rsp+148h+dwMilliseconds], 0
0x18001f280  lea     r8, [rsp+148h+dwMilliseconds]; unsigned int *
0x18001f285  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001f28a  mov     [rsp+148h+Reply], 0
0x18001f292  mov     [rsp+148h+var_E8], 0
0x18001f29b  lea     rcx, [rsp+148h+var_E8]; this
0x18001f2a0  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001f2a5  mov     [rsp+148h+Reply], eax
0x18001f2a9  test    eax, eax
0x18001f2ab  js      loc_18001F5B8
0x18001f2b1  xor     edx, edx; Val
0x18001f2b3  lea     r8d, [rdx+70h]; Size
0x18001f2b7  lea     rcx, [rsp+148h+pAsync]; void *
0x18001f2bf  call    memset_0
0x18001f2c4  mov     esi, [rsp+148h+dwMilliseconds]
0x18001f2c8  mov     [rsp+148h+dwMilliseconds], esi
0x18001f2cc  mov     [rsp+148h+var_EC], esi
0x18001f2d0  xor     r15b, r15b
0x18001f2d3  mov     [rsp+148h+var_F4], r15b
0x18001f2d8  xor     r14b, r14b
0x18001f2db  xorps   xmm0, xmm0
0x18001f2de  movups  xmmword ptr [rsp+148h+Handles], xmm0
0x18001f2e6  mov     edx, 70h ; 'p'; Size
0x18001f2eb  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001f2f3  call    cs:__imp_RpcAsyncInitializeHandle
0x18001f2f9  test    eax, eax
0x18001f2fb  jz      short loc_18001F319
0x18001f2fd  jle     short loc_18001F307
0x18001f2ff  movzx   eax, ax
0x18001f302  or      eax, 80070000h
0x18001f307  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001f30e  mov     r8d, 50Ch
0x18001f314  jmp     loc_18001F4F8
0x18001f319  mov     [rsp+148h+pAsync.UserInfo], 0
0x18001f325  mov     [rsp+148h+pAsync.NotificationType], 1
0x18001f330  xor     r9d, r9d; lpName
0x18001f333  xor     r8d, r8d; bInitialState
0x18001f336  xor     edx, edx; bManualReset
0x18001f338  xor     ecx, ecx; lpEventAttributes
0x18001f33a  call    cs:__imp_CreateEventW
0x18001f340  mov     qword ptr [rsp+148h+pAsync.u], rax
0x18001f348  test    rax, rax
0x18001f34b  jnz     short loc_18001F368
0x18001f34d  call    cs:__imp_GetLastError
0x18001f353  test    eax, eax
0x18001f355  jle     short loc_18001F35F
0x18001f357  movzx   eax, ax
0x18001f35a  or      eax, 80070000h
0x18001f35f  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001f366  jmp     short loc_18001F30E
0x18001f368  mov     [rsp+148h+Handles], rax
0x18001f370  mov     rax, [rsp+148h+var_E0]
0x18001f375  mov     [rsp+148h+var_100], rax
0x18001f37a  mov     rax, [rsp+148h+var_D8]
0x18001f37f  mov     [rsp+148h+var_108], rax
0x18001f384  mov     rax, [rsp+148h+var_D0]
0x18001f389  mov     [rsp+148h+var_110], rax
0x18001f38e  mov     rax, [rsp+148h+var_C8]
0x18001f396  mov     [rsp+148h+var_118], rax
0x18001f39b  mov     [rsp+148h+var_120], r13
0x18001f3a0  mov     qword ptr [rsp+148h+bAlertable], r12
0x18001f3a5  lea     r9, [rsp+148h+pAsync]
0x18001f3ad  xor     r8d, r8d; pReturnValue
0x18001f3b0  lea     edx, [r8+3Ch]; nProcNum
0x18001f3b4  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001f3bb  call    cs:__imp_Ndr64AsyncClientCall
0x18001f3c1  mov     eax, [rsp+148h+Reply]
0x18001f3c5  jmp     short loc_18001F416
0x18001f3c7  test    eax, eax
0x18001f3c9  jle     short loc_18001F3D3
0x18001f3cb  movzx   eax, ax
0x18001f3ce  or      eax, 80070000h
0x18001f3d3  mov     [rsp+148h+Reply], eax
0x18001f3d7  mov     [rsp+148h+bAlertable], eax
0x18001f3db  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001f3e2  mov     r8d, 50Eh; unsigned int
0x18001f3e8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f3ef  mov     ecx, 2; unsigned __int8
0x18001f3f4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f3f9  mov     eax, [rsp+148h+Reply]
0x18001f3fd  test    eax, eax
0x18001f3ff  js      short loc_18001F40A
0x18001f401  mov     eax, 8000FFFFh
0x18001f406  mov     [rsp+148h+Reply], eax
0x18001f40a  mov     esi, [rsp+148h+dwMilliseconds]
0x18001f40e  mov     r15b, [rsp+148h+var_F4]
0x18001f413  mov     r14b, r15b
0x18001f416  test    eax, eax
0x18001f418  jns     short loc_18001F42C
0x18001f41a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001f421  mov     r8d, 50Eh
0x18001f427  jmp     loc_18001F4FC
0x18001f42c  mov     [rsp+148h+bAlertable], 0; bAlertable
0x18001f434  mov     r9d, esi; dwMilliseconds
0x18001f437  xor     r8d, r8d; bWaitAll
0x18001f43a  lea     rdx, [rsp+148h+Handles]; lpHandles
0x18001f442  lea     ecx, [r8+1]; nCount
0x18001f446  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f44c  mov     esi, eax
0x18001f44e  mov     r12d, 102h
0x18001f454  test    r14b, r14b
0x18001f457  jnz     short loc_18001F4AB
0x18001f459  cmp     esi, r12d
0x18001f45c  jz      short loc_18001F463
0x18001f45e  cmp     esi, 1
0x18001f461  jnz     short loc_18001F4AB
0x18001f463  mov     edx, 1; fAbort
0x18001f468  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001f470  call    cs:__imp_RpcAsyncCancelCall
0x18001f476  cmp     esi, r12d
0x18001f479  jnz     short loc_18001F480
0x18001f47b  mov     r15b, 1
0x18001f47e  jmp     short loc_18001F483
0x18001f480  mov     r14b, 1
0x18001f483  mov     [rsp+148h+bAlertable], 0; bAlertable
0x18001f48b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001f48f  xor     r8d, r8d; bWaitAll
0x18001f492  lea     rdx, [rsp+148h+Handles]; lpHandles
0x18001f49a  lea     ecx, [r8+1]; nCount
0x18001f49e  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f4a4  mov     esi, eax
0x18001f4a6  test    r15b, r15b
0x18001f4a9  jz      short loc_18001F454
0x18001f4ab  test    esi, esi
0x18001f4ad  jz      short loc_18001F4CA
0x18001f4af  call    cs:__imp_GetLastError
0x18001f4b5  test    eax, eax
0x18001f4b7  jle     short loc_18001F4C1
0x18001f4b9  movzx   eax, ax
0x18001f4bc  or      eax, 80070000h
0x18001f4c1  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001f4c8  jmp     short loc_18001F4F2
0x18001f4ca  lea     rdx, [rsp+148h+Reply]; Reply
0x18001f4cf  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18001f4d7  call    cs:__imp_RpcAsyncCompleteCall
0x18001f4dd  test    eax, eax
0x18001f4df  jz      short loc_18001F511
0x18001f4e1  jle     short loc_18001F4EB
0x18001f4e3  movzx   eax, ax
0x18001f4e6  or      eax, 80070000h
0x18001f4eb  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001f4f2  mov     r8d, 50Eh; unsigned int
0x18001f4f8  mov     [rsp+148h+Reply], eax
0x18001f4fc  mov     [rsp+148h+bAlertable], eax
0x18001f500  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f507  mov     ecx, 2; unsigned __int8
0x18001f50c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f511  mov     rcx, qword ptr [rsp+148h+pAsync.u]; hObject
0x18001f519  test    rcx, rcx
0x18001f51c  jz      short loc_18001F524
0x18001f51e  call    cs:__imp_CloseHandle
0x18001f524  test    r15b, r15b
0x18001f527  jz      short loc_18001F561
0x18001f529  mov     [rsp+148h+Reply], 800705B4h
0x18001f531  lea     rdx, [rsp+148h+var_EC]
0x18001f536  call    ??$RPCCallTimedOut@AEAY0BC@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BC@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[18],ulong &>(char const (&)[18],ulong &)
0x18001f53b  mov     eax, [rsp+148h+Reply]
0x18001f53f  mov     [rsp+148h+bAlertable], eax
0x18001f543  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001f54a  mov     r8d, 50Eh; unsigned int
0x18001f550  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f557  mov     ecx, 2; unsigned __int8
0x18001f55c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f561  test    r14b, r14b
0x18001f564  jz      short loc_18001F591
0x18001f566  mov     eax, 800704C7h
0x18001f56b  mov     [rsp+148h+Reply], eax
0x18001f56f  mov     [rsp+148h+bAlertable], eax
0x18001f573  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001f57a  mov     r8d, 50Eh; unsigned int
0x18001f580  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f587  mov     ecx, 2; unsigned __int8
0x18001f58c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f591  cmp     [rsp+148h+Reply], 800706B5h
0x18001f599  jz      short loc_18001F5A5
0x18001f59b  cmp     [rsp+148h+Reply], 800706BAh
0x18001f5a3  jnz     short loc_18001F5AA
0x18001f5a5  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001f5aa  lea     rcx, [rsp+148h+var_E8]; this
0x18001f5af  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001f5b4  mov     eax, [rsp+148h+Reply]
0x18001f5b8  mov     rcx, [rsp+148h+var_38]
0x18001f5c0  xor     rcx, rsp; StackCookie
0x18001f5c3  call    __security_check_cookie
0x18001f5c8  add     rsp, 120h
0x18001f5cf  pop     r15
0x18001f5d1  pop     r14
0x18001f5d3  pop     r13
0x18001f5d5  pop     r12
0x18001f5d7  pop     rsi
0x18001f5d8  retn
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
