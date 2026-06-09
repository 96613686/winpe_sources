# WLIDCGetKeyWithVersion(void * const,unsigned __int64,ushort const *,ushort const *,__int64,ushort * *)

- ea: `0x18001f5e0`
- end: `0x18001f988`
- name: `?WLIDCGetKeyWithVersion@@YAJQEAX_KPEBG2_JPEAPEAG@Z`
- size: `936`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800197c0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019e38`
- `0x18001ba00`
- `0x18001f5e0`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f7ee`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f846`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f7ee`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001f846`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f6e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f6e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f857`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f8c6`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f763`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001f763`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f87f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f87f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001f69b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001f69b`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f818`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f818`

## string_xrefs

- `0x18001f707`: `RPC failed to create new event, hr = %#x`
- `0x18001f893`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCGetKeyWithVersion(
        void *const a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned __int16 **a6)
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
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v19; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int16 **v23; // [rsp+68h] [rbp-D0h]
  const unsigned __int16 *v24; // [rsp+70h] [rbp-C8h]
  const unsigned __int16 *v25; // [rsp+78h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+80h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v24 = a4;
  v25 = a3;
  v23 = a6;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v9 = dwMilliseconds;
  v21 = dwMilliseconds;
  v10 = 0;
  v19 = 0;
  v11 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v14 = 1306;
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
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x3Du, 0, &pAsync, a1, a2, v25, v24, a5, v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v13 = L"RPC call failed, hr = %#x";
    v14 = 1308;
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
    v14 = 1308;
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
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v10 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],unsigned long &>(
      (__int64)"WLIDCGetKeyWithVersion",
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x51Cu,
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
      0x51Cu,
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
0x18001f5e0  push    rsi
0x18001f5e2  push    r12
0x18001f5e4  push    r13
0x18001f5e6  push    r14
0x18001f5e8  push    r15
0x18001f5ea  sub     rsp, 110h
0x18001f5f1  mov     rax, cs:__security_cookie
0x18001f5f8  xor     rax, rsp
0x18001f5fb  mov     [rsp+138h+var_38], rax
0x18001f603  mov     [rsp+138h+var_C8], r9
0x18001f608  mov     [rsp+138h+var_C0], r8
0x18001f60d  mov     r13, rdx
0x18001f610  mov     r12, rcx
0x18001f613  mov     rax, [rsp+138h+arg_28]
0x18001f61b  mov     [rsp+138h+var_D0], rax
0x18001f620  mov     [rsp+138h+dwMilliseconds], 0
0x18001f628  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18001f62d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001f632  mov     [rsp+138h+Reply], 0
0x18001f63a  mov     [rsp+138h+var_D8], 0
0x18001f643  lea     rcx, [rsp+138h+var_D8]; this
0x18001f648  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001f64d  mov     [rsp+138h+Reply], eax
0x18001f651  test    eax, eax
0x18001f653  js      loc_18001F967
0x18001f659  xor     edx, edx; Val
0x18001f65b  lea     r8d, [rdx+70h]; Size
0x18001f65f  lea     rcx, [rsp+138h+pAsync]; void *
0x18001f667  call    memset_0
0x18001f66c  mov     esi, [rsp+138h+dwMilliseconds]
0x18001f670  mov     [rsp+138h+dwMilliseconds], esi
0x18001f674  mov     [rsp+138h+var_DC], esi
0x18001f678  xor     r15b, r15b
0x18001f67b  mov     [rsp+138h+var_E4], r15b
0x18001f680  xor     r14b, r14b
0x18001f683  xorps   xmm0, xmm0
0x18001f686  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18001f68e  mov     edx, 70h ; 'p'; Size
0x18001f693  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001f69b  call    cs:__imp_RpcAsyncInitializeHandle
0x18001f6a1  test    eax, eax
0x18001f6a3  jz      short loc_18001F6C1
0x18001f6a5  jle     short loc_18001F6AF
0x18001f6a7  movzx   eax, ax
0x18001f6aa  or      eax, 80070000h
0x18001f6af  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001f6b6  mov     r8d, 51Ah
0x18001f6bc  jmp     loc_18001F8A0
0x18001f6c1  mov     [rsp+138h+pAsync.UserInfo], 0
0x18001f6cd  mov     [rsp+138h+pAsync.NotificationType], 1
0x18001f6d8  xor     r9d, r9d; lpName
0x18001f6db  xor     r8d, r8d; bInitialState
0x18001f6de  xor     edx, edx; bManualReset
0x18001f6e0  xor     ecx, ecx; lpEventAttributes
0x18001f6e2  call    cs:__imp_CreateEventW
0x18001f6e8  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18001f6f0  test    rax, rax
0x18001f6f3  jnz     short loc_18001F710
0x18001f6f5  call    cs:__imp_GetLastError
0x18001f6fb  test    eax, eax
0x18001f6fd  jle     short loc_18001F707
0x18001f6ff  movzx   eax, ax
0x18001f702  or      eax, 80070000h
0x18001f707  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001f70e  jmp     short loc_18001F6B6
0x18001f710  mov     [rsp+138h+Handles], rax
0x18001f718  mov     rax, [rsp+138h+var_D0]
0x18001f71d  mov     [rsp+138h+var_F0], rax
0x18001f722  mov     rax, [rsp+138h+arg_20]
0x18001f72a  mov     [rsp+138h+var_F8], rax
0x18001f72f  mov     rax, [rsp+138h+var_C8]
0x18001f734  mov     [rsp+138h+var_100], rax
0x18001f739  mov     rax, [rsp+138h+var_C0]
0x18001f73e  mov     [rsp+138h+var_108], rax
0x18001f743  mov     [rsp+138h+var_110], r13
0x18001f748  mov     qword ptr [rsp+138h+bAlertable], r12
0x18001f74d  lea     r9, [rsp+138h+pAsync]
0x18001f755  xor     r8d, r8d; pReturnValue
0x18001f758  lea     edx, [r8+3Dh]; nProcNum
0x18001f75c  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001f763  call    cs:__imp_Ndr64AsyncClientCall
0x18001f769  mov     eax, [rsp+138h+Reply]
0x18001f76d  jmp     short loc_18001F7BE
0x18001f76f  test    eax, eax
0x18001f771  jle     short loc_18001F77B
0x18001f773  movzx   eax, ax
0x18001f776  or      eax, 80070000h
0x18001f77b  mov     [rsp+138h+Reply], eax
0x18001f77f  mov     [rsp+138h+bAlertable], eax
0x18001f783  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001f78a  mov     r8d, 51Ch; unsigned int
0x18001f790  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f797  mov     ecx, 2; unsigned __int8
0x18001f79c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f7a1  mov     eax, [rsp+138h+Reply]
0x18001f7a5  test    eax, eax
0x18001f7a7  js      short loc_18001F7B2
0x18001f7a9  mov     eax, 8000FFFFh
0x18001f7ae  mov     [rsp+138h+Reply], eax
0x18001f7b2  mov     esi, [rsp+138h+dwMilliseconds]
0x18001f7b6  mov     r15b, [rsp+138h+var_E4]
0x18001f7bb  mov     r14b, r15b
0x18001f7be  test    eax, eax
0x18001f7c0  jns     short loc_18001F7D4
0x18001f7c2  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001f7c9  mov     r8d, 51Ch
0x18001f7cf  jmp     loc_18001F8A4
0x18001f7d4  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001f7dc  mov     r9d, esi; dwMilliseconds
0x18001f7df  xor     r8d, r8d; bWaitAll
0x18001f7e2  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001f7ea  lea     ecx, [r8+1]; nCount
0x18001f7ee  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f7f4  mov     esi, eax
0x18001f7f6  mov     r12d, 102h
0x18001f7fc  test    r14b, r14b
0x18001f7ff  jnz     short loc_18001F853
0x18001f801  cmp     esi, r12d
0x18001f804  jz      short loc_18001F80B
0x18001f806  cmp     esi, 1
0x18001f809  jnz     short loc_18001F853
0x18001f80b  mov     edx, 1; fAbort
0x18001f810  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001f818  call    cs:__imp_RpcAsyncCancelCall
0x18001f81e  cmp     esi, r12d
0x18001f821  jnz     short loc_18001F828
0x18001f823  mov     r15b, 1
0x18001f826  jmp     short loc_18001F82B
0x18001f828  mov     r14b, 1
0x18001f82b  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001f833  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001f837  xor     r8d, r8d; bWaitAll
0x18001f83a  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001f842  lea     ecx, [r8+1]; nCount
0x18001f846  call    cs:__imp_WaitForMultipleObjectsEx
0x18001f84c  mov     esi, eax
0x18001f84e  test    r15b, r15b
0x18001f851  jz      short loc_18001F7FC
0x18001f853  test    esi, esi
0x18001f855  jz      short loc_18001F872
0x18001f857  call    cs:__imp_GetLastError
0x18001f85d  test    eax, eax
0x18001f85f  jle     short loc_18001F869
0x18001f861  movzx   eax, ax
0x18001f864  or      eax, 80070000h
0x18001f869  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001f870  jmp     short loc_18001F89A
0x18001f872  lea     rdx, [rsp+138h+Reply]; Reply
0x18001f877  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001f87f  call    cs:__imp_RpcAsyncCompleteCall
0x18001f885  test    eax, eax
0x18001f887  jz      short loc_18001F8B9
0x18001f889  jle     short loc_18001F893
0x18001f88b  movzx   eax, ax
0x18001f88e  or      eax, 80070000h
0x18001f893  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001f89a  mov     r8d, 51Ch; unsigned int
0x18001f8a0  mov     [rsp+138h+Reply], eax
0x18001f8a4  mov     [rsp+138h+bAlertable], eax
0x18001f8a8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f8af  mov     ecx, 2; unsigned __int8
0x18001f8b4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f8b9  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18001f8c1  test    rcx, rcx
0x18001f8c4  jz      short loc_18001F8CC
0x18001f8c6  call    cs:__imp_CloseHandle
0x18001f8cc  test    r15b, r15b
0x18001f8cf  jz      short loc_18001F910
0x18001f8d1  mov     [rsp+138h+Reply], 800705B4h
0x18001f8d9  lea     rdx, [rsp+138h+var_DC]
0x18001f8de  lea     rcx, aWlidcgetkeywit; "WLIDCGetKeyWithVersion"
0x18001f8e5  call    ??$RPCCallTimedOut@AEAY0BH@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BH@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[23],ulong &>(char const (&)[23],ulong &)
0x18001f8ea  mov     eax, [rsp+138h+Reply]
0x18001f8ee  mov     [rsp+138h+bAlertable], eax
0x18001f8f2  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001f8f9  mov     r8d, 51Ch; unsigned int
0x18001f8ff  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f906  mov     ecx, 2; unsigned __int8
0x18001f90b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f910  test    r14b, r14b
0x18001f913  jz      short loc_18001F940
0x18001f915  mov     eax, 800704C7h
0x18001f91a  mov     [rsp+138h+Reply], eax
0x18001f91e  mov     [rsp+138h+bAlertable], eax
0x18001f922  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001f929  mov     r8d, 51Ch; unsigned int
0x18001f92f  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001f936  mov     ecx, 2; unsigned __int8
0x18001f93b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f940  cmp     [rsp+138h+Reply], 800706B5h
0x18001f948  jz      short loc_18001F954
0x18001f94a  cmp     [rsp+138h+Reply], 800706BAh
0x18001f952  jnz     short loc_18001F959
0x18001f954  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001f959  lea     rcx, [rsp+138h+var_D8]; this
0x18001f95e  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001f963  mov     eax, [rsp+138h+Reply]
0x18001f967  mov     rcx, [rsp+138h+var_38]
0x18001f96f  xor     rcx, rsp; StackCookie
0x18001f972  call    __security_check_cookie
0x18001f977  add     rsp, 110h
0x18001f97e  pop     r15
0x18001f980  pop     r14
0x18001f982  pop     r13
0x18001f984  pop     r12
0x18001f986  pop     rsi
0x18001f987  retn
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
