# WLIDCGetSignedTokens(_WLIDSignedTokens * *)

- ea: `0x180020404`
- end: `0x18002074a`
- name: `?WLIDCGetSignedTokens@@YAJPEAPEAU_WLIDSignedTokens@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct _WLIDSignedTokens **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019860`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x180020404`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800205bb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002060d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800205bb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002060d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800204de`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800204de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002061e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002061e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002068a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002068a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020533`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180020533`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020643`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180020643`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002049a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002049a`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800205e2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800205e2`

## string_xrefs

- `0x180020503`: `RPC failed to create new event, hr = %#x`
- `0x180020657`: `RPC Async complete call failed, hr = %#x`
- `0x1800206a2`: `WLIDCGetSignedTokens`

## pseudocode

```c
__int64 __fastcall WLIDCGetSignedTokens(struct _WLIDSignedTokens **a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v4; // esi
  char v5; // r15
  char v6; // r14
  int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v11; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E8h]
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  char v14; // [rsp+34h] [rbp-D4h]
  DWORD dwMilliseconds; // [rsp+38h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v17; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-A8h] BYREF

  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v17 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v17);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = dwMilliseconds;
  v16 = dwMilliseconds;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v9 = 1345;
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
    v8 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Fu, 0, &pAsync, v17, a1);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v8 = L"RPC call failed, hr = %#x";
    v9 = 1347;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v9,
      v8,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v11 = WaitForMultipleObjectsEx(1u, Handles, 0, v4, 0);
  do
  {
    if ( v6 || v11 != 258 && v11 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v11 == 258 )
      v5 = 1;
    else
      v6 = 1;
    v11 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v5 );
  if ( v11 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v9 = 1347;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v5 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCGetSignedTokens",
      (int *)&v16);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x543u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v6 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x543u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v17);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x180020404  push    rsi
0x180020406  push    r12
0x180020408  push    r14
0x18002040a  push    r15
0x18002040c  sub     rsp, 0E8h
0x180020413  mov     rax, cs:__security_cookie
0x18002041a  xor     rax, rsp
0x18002041d  mov     [rsp+108h+var_38], rax
0x180020425  mov     r12, rcx
0x180020428  mov     [rsp+108h+dwMilliseconds], 0
0x180020430  lea     r8, [rsp+108h+dwMilliseconds]; unsigned int *
0x180020435  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18002043a  mov     [rsp+108h+Reply], 0
0x180020442  mov     [rsp+108h+var_C8], 0
0x18002044b  lea     rcx, [rsp+108h+var_C8]; this
0x180020450  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x180020455  mov     [rsp+108h+Reply], eax
0x180020459  test    eax, eax
0x18002045b  js      loc_18002072B
0x180020461  xor     edx, edx; Val
0x180020463  lea     r8d, [rdx+70h]; Size
0x180020467  lea     rcx, [rsp+108h+pAsync]; void *
0x18002046c  call    memset_0
0x180020471  mov     esi, [rsp+108h+dwMilliseconds]
0x180020475  mov     [rsp+108h+dwMilliseconds], esi
0x180020479  mov     [rsp+108h+var_CC], esi
0x18002047d  xor     r15b, r15b
0x180020480  mov     [rsp+108h+var_D4], r15b
0x180020485  xor     r14b, r14b
0x180020488  xorps   xmm0, xmm0
0x18002048b  movups  xmmword ptr [rsp+108h+Handles], xmm0
0x180020490  mov     edx, 70h ; 'p'; Size
0x180020495  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18002049a  call    cs:__imp_RpcAsyncInitializeHandle
0x1800204a0  test    eax, eax
0x1800204a2  jz      short loc_1800204C0
0x1800204a4  jle     short loc_1800204AE
0x1800204a6  movzx   eax, ax
0x1800204a9  or      eax, 80070000h
0x1800204ae  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x1800204b5  mov     r8d, 541h
0x1800204bb  jmp     loc_180020664
0x1800204c0  mov     [rsp+108h+pAsync.UserInfo], 0
0x1800204c9  mov     [rsp+108h+pAsync.NotificationType], 1
0x1800204d4  xor     r9d, r9d; lpName
0x1800204d7  xor     r8d, r8d; bInitialState
0x1800204da  xor     edx, edx; bManualReset
0x1800204dc  xor     ecx, ecx; lpEventAttributes
0x1800204de  call    cs:__imp_CreateEventW
0x1800204e4  mov     qword ptr [rsp+108h+pAsync.u], rax
0x1800204ec  test    rax, rax
0x1800204ef  jnz     short loc_18002050C
0x1800204f1  call    cs:__imp_GetLastError
0x1800204f7  test    eax, eax
0x1800204f9  jle     short loc_180020503
0x1800204fb  movzx   eax, ax
0x1800204fe  or      eax, 80070000h
0x180020503  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18002050a  jmp     short loc_1800204B5
0x18002050c  mov     [rsp+108h+Handles], rax
0x180020511  mov     [rsp+108h+var_E0], r12
0x180020516  mov     rax, [rsp+108h+var_C8]
0x18002051b  mov     qword ptr [rsp+108h+bAlertable], rax
0x180020520  lea     r9, [rsp+108h+pAsync]
0x180020525  xor     r8d, r8d; pReturnValue
0x180020528  lea     edx, [r8+3Fh]; nProcNum
0x18002052c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180020533  call    cs:__imp_Ndr64AsyncClientCall
0x180020539  mov     eax, [rsp+108h+Reply]
0x18002053d  jmp     short loc_18002058E
0x18002053f  test    eax, eax
0x180020541  jle     short loc_18002054B
0x180020543  movzx   eax, ax
0x180020546  or      eax, 80070000h
0x18002054b  mov     [rsp+108h+Reply], eax
0x18002054f  mov     [rsp+108h+bAlertable], eax
0x180020553  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18002055a  mov     r8d, 543h; unsigned int
0x180020560  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020567  mov     ecx, 2; unsigned __int8
0x18002056c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020571  mov     eax, [rsp+108h+Reply]
0x180020575  test    eax, eax
0x180020577  js      short loc_180020582
0x180020579  mov     eax, 8000FFFFh
0x18002057e  mov     [rsp+108h+Reply], eax
0x180020582  mov     esi, [rsp+108h+dwMilliseconds]
0x180020586  mov     r15b, [rsp+108h+var_D4]
0x18002058b  mov     r14b, r15b
0x18002058e  test    eax, eax
0x180020590  jns     short loc_1800205A4
0x180020592  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x180020599  mov     r8d, 543h
0x18002059f  jmp     loc_180020668
0x1800205a4  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800205ac  mov     r9d, esi; dwMilliseconds
0x1800205af  xor     r8d, r8d; bWaitAll
0x1800205b2  lea     rdx, [rsp+108h+Handles]; lpHandles
0x1800205b7  lea     ecx, [r8+1]; nCount
0x1800205bb  call    cs:__imp_WaitForMultipleObjectsEx
0x1800205c1  mov     esi, eax
0x1800205c3  mov     r12d, 102h
0x1800205c9  test    r14b, r14b
0x1800205cc  jnz     short loc_18002061A
0x1800205ce  cmp     esi, r12d
0x1800205d1  jz      short loc_1800205D8
0x1800205d3  cmp     esi, 1
0x1800205d6  jnz     short loc_18002061A
0x1800205d8  mov     edx, 1; fAbort
0x1800205dd  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800205e2  call    cs:__imp_RpcAsyncCancelCall
0x1800205e8  cmp     esi, r12d
0x1800205eb  jnz     short loc_1800205F2
0x1800205ed  mov     r15b, 1
0x1800205f0  jmp     short loc_1800205F5
0x1800205f2  mov     r14b, 1
0x1800205f5  mov     [rsp+108h+bAlertable], 0; bAlertable
0x1800205fd  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180020601  xor     r8d, r8d; bWaitAll
0x180020604  lea     rdx, [rsp+108h+Handles]; lpHandles
0x180020609  lea     ecx, [r8+1]; nCount
0x18002060d  call    cs:__imp_WaitForMultipleObjectsEx
0x180020613  mov     esi, eax
0x180020615  test    r15b, r15b
0x180020618  jz      short loc_1800205C9
0x18002061a  test    esi, esi
0x18002061c  jz      short loc_180020639
0x18002061e  call    cs:__imp_GetLastError
0x180020624  test    eax, eax
0x180020626  jle     short loc_180020630
0x180020628  movzx   eax, ax
0x18002062b  or      eax, 80070000h
0x180020630  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x180020637  jmp     short loc_18002065E
0x180020639  lea     rdx, [rsp+108h+Reply]; Reply
0x18002063e  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180020643  call    cs:__imp_RpcAsyncCompleteCall
0x180020649  test    eax, eax
0x18002064b  jz      short loc_18002067D
0x18002064d  jle     short loc_180020657
0x18002064f  movzx   eax, ax
0x180020652  or      eax, 80070000h
0x180020657  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18002065e  mov     r8d, 543h; unsigned int
0x180020664  mov     [rsp+108h+Reply], eax
0x180020668  mov     [rsp+108h+bAlertable], eax
0x18002066c  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180020673  mov     ecx, 2; unsigned __int8
0x180020678  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002067d  mov     rcx, qword ptr [rsp+108h+pAsync.u]; hObject
0x180020685  test    rcx, rcx
0x180020688  jz      short loc_180020690
0x18002068a  call    cs:__imp_CloseHandle
0x180020690  test    r15b, r15b
0x180020693  jz      short loc_1800206D4
0x180020695  mov     [rsp+108h+Reply], 800705B4h
0x18002069d  lea     rdx, [rsp+108h+var_CC]
0x1800206a2  lea     rcx, aWlidcgetsigned; "WLIDCGetSignedTokens"
0x1800206a9  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x1800206ae  mov     eax, [rsp+108h+Reply]
0x1800206b2  mov     [rsp+108h+bAlertable], eax
0x1800206b6  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x1800206bd  mov     r8d, 543h; unsigned int
0x1800206c3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800206ca  mov     ecx, 2; unsigned __int8
0x1800206cf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800206d4  test    r14b, r14b
0x1800206d7  jz      short loc_180020704
0x1800206d9  mov     eax, 800704C7h
0x1800206de  mov     [rsp+108h+Reply], eax
0x1800206e2  mov     [rsp+108h+bAlertable], eax
0x1800206e6  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x1800206ed  mov     r8d, 543h; unsigned int
0x1800206f3  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800206fa  mov     ecx, 2; unsigned __int8
0x1800206ff  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020704  cmp     [rsp+108h+Reply], 800706B5h
0x18002070c  jz      short loc_180020718
0x18002070e  cmp     [rsp+108h+Reply], 800706BAh
0x180020716  jnz     short loc_18002071D
0x180020718  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18002071d  lea     rcx, [rsp+108h+var_C8]; this
0x180020722  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x180020727  mov     eax, [rsp+108h+Reply]
0x18002072b  mov     rcx, [rsp+108h+var_38]
0x180020733  xor     rcx, rsp; StackCookie
0x180020736  call    __security_check_cookie
0x18002073b  add     rsp, 0E8h
0x180020742  pop     r15
0x180020744  pop     r14
0x180020746  pop     r12
0x180020748  pop     rsi
0x180020749  retn
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
