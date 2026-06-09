# WLIDCCreateContextEx(ushort const *,ushort const *,unsigned __int64,void * *)

- ea: `0x18001d028`
- end: `0x18001d3b6`
- name: `?WLIDCCreateContextEx@@YAJPEBG0_KPEAPEAX@Z`
- size: `910`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019640`
- `0x180019650`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019d20`
- `0x18001ba00`
- `0x18001bb84`
- `0x18001d028`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d213`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d268`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d213`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001d268`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d11a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d11a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d2e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d2e8`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d18b`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001d18b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d2a1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001d2a1`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d0d3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001d0d3`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d23d`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001d23d`

## string_xrefs

- `0x18001d13f`: `RPC failed to create new event, hr = %#x`
- `0x18001d2b5`: `RPC Async complete call failed, hr = %#x`
- `0x18001d300`: `WLIDCCreateContextEx`
- `0x18001d385`: `WLIDCCreateContextEx`

## pseudocode

```c
__int64 __fastcall WLIDCCreateContextEx(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, void **a4)
{
  __int64 result; // rax
  DWORD v7; // esi
  char v8; // r15
  char v9; // r14
  int LastError; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v14; // esi
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v17; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v19; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v20; // [rsp+60h] [rbp-D8h] BYREF
  void **v21; // [rsp+68h] [rbp-D0h]
  __int64 v22; // [rsp+70h] [rbp-C8h]
  HANDLE Handles[3]; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v21 = a4;
  v22 = a3;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, (unsigned int)a2, &dwMilliseconds);
  v20 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v20);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = dwMilliseconds;
  v19 = dwMilliseconds;
  v8 = 0;
  v17 = 0;
  v9 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v12 = 574;
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
    v11 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0xAu, 0, &pAsync, v20, a1, a2, v22, v21);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v11 = L"RPC call failed, hr = %#x";
    v12 = 576;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v12,
      v11,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v14 = WaitForMultipleObjectsEx(1u, Handles, 0, v7, 0);
  do
  {
    if ( v9 || v14 != 258 && v14 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 == 258 )
      v8 = 1;
    else
      v9 = 1;
    v14 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v8 );
  if ( v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v12 = 576;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v8 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
      (__int64)"WLIDCCreateContextEx",
      (int *)&v19);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v9 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x240u,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( Reply == -2147023179 || Reply == -2147023174 )
    TraceServiceStatus();
  CWLIDBinding::Unbind((CWLIDBinding *)&v20);
  return TranslateRpcServiceError(Reply, "WLIDCCreateContextEx");
}

```

## disassembly

```asm
0x18001d028  push    rsi
0x18001d02a  push    r12
0x18001d02c  push    r13
0x18001d02e  push    r14
0x18001d030  push    r15
0x18001d032  sub     rsp, 110h
0x18001d039  mov     rax, cs:__security_cookie
0x18001d040  xor     rax, rsp
0x18001d043  mov     [rsp+138h+var_38], rax
0x18001d04b  mov     [rsp+138h+var_D0], r9
0x18001d050  mov     [rsp+138h+var_C8], r8
0x18001d055  mov     r13, rdx
0x18001d058  mov     r12, rcx
0x18001d05b  mov     [rsp+138h+dwMilliseconds], 0
0x18001d063  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18001d068  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001d06d  mov     [rsp+138h+Reply], 0
0x18001d075  mov     [rsp+138h+var_D8], 0
0x18001d07e  lea     rcx, [rsp+138h+var_D8]; this
0x18001d083  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001d088  mov     [rsp+138h+Reply], eax
0x18001d08c  test    eax, eax
0x18001d08e  js      loc_18001D395
0x18001d094  xor     edx, edx; Val
0x18001d096  lea     r8d, [rdx+70h]; Size
0x18001d09a  lea     rcx, [rsp+138h+pAsync]; void *
0x18001d0a2  call    memset_0
0x18001d0a7  mov     esi, [rsp+138h+dwMilliseconds]
0x18001d0ab  mov     [rsp+138h+dwMilliseconds], esi
0x18001d0af  mov     [rsp+138h+var_DC], esi
0x18001d0b3  xor     r15b, r15b
0x18001d0b6  mov     [rsp+138h+var_E4], r15b
0x18001d0bb  xor     r14b, r14b
0x18001d0be  xorps   xmm0, xmm0
0x18001d0c1  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18001d0c6  mov     edx, 70h ; 'p'; Size
0x18001d0cb  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001d0d3  call    cs:__imp_RpcAsyncInitializeHandle
0x18001d0d9  test    eax, eax
0x18001d0db  jz      short loc_18001D0F9
0x18001d0dd  jle     short loc_18001D0E7
0x18001d0df  movzx   eax, ax
0x18001d0e2  or      eax, 80070000h
0x18001d0e7  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001d0ee  mov     r8d, 23Eh
0x18001d0f4  jmp     loc_18001D2C2
0x18001d0f9  mov     [rsp+138h+pAsync.UserInfo], 0
0x18001d105  mov     [rsp+138h+pAsync.NotificationType], 1
0x18001d110  xor     r9d, r9d; lpName
0x18001d113  xor     r8d, r8d; bInitialState
0x18001d116  xor     edx, edx; bManualReset
0x18001d118  xor     ecx, ecx; lpEventAttributes
0x18001d11a  call    cs:__imp_CreateEventW
0x18001d120  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18001d128  test    rax, rax
0x18001d12b  jnz     short loc_18001D148
0x18001d12d  call    cs:__imp_GetLastError
0x18001d133  test    eax, eax
0x18001d135  jle     short loc_18001D13F
0x18001d137  movzx   eax, ax
0x18001d13a  or      eax, 80070000h
0x18001d13f  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001d146  jmp     short loc_18001D0EE
0x18001d148  mov     [rsp+138h+Handles], rax
0x18001d14d  mov     rax, [rsp+138h+var_D0]
0x18001d152  mov     [rsp+138h+var_F8], rax
0x18001d157  mov     rax, [rsp+138h+var_C8]
0x18001d15c  mov     [rsp+138h+var_100], rax
0x18001d161  mov     [rsp+138h+var_108], r13
0x18001d166  mov     [rsp+138h+var_110], r12
0x18001d16b  mov     rax, [rsp+138h+var_D8]
0x18001d170  mov     qword ptr [rsp+138h+bAlertable], rax
0x18001d175  lea     r9, [rsp+138h+pAsync]
0x18001d17d  xor     r8d, r8d; pReturnValue
0x18001d180  lea     edx, [r8+0Ah]; nProcNum
0x18001d184  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001d18b  call    cs:__imp_Ndr64AsyncClientCall
0x18001d191  mov     eax, [rsp+138h+Reply]
0x18001d195  jmp     short loc_18001D1E6
0x18001d197  test    eax, eax
0x18001d199  jle     short loc_18001D1A3
0x18001d19b  movzx   eax, ax
0x18001d19e  or      eax, 80070000h
0x18001d1a3  mov     [rsp+138h+Reply], eax
0x18001d1a7  mov     [rsp+138h+bAlertable], eax
0x18001d1ab  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001d1b2  mov     r8d, 240h; unsigned int
0x18001d1b8  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d1bf  mov     ecx, 2; unsigned __int8
0x18001d1c4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d1c9  mov     eax, [rsp+138h+Reply]
0x18001d1cd  test    eax, eax
0x18001d1cf  js      short loc_18001D1DA
0x18001d1d1  mov     eax, 8000FFFFh
0x18001d1d6  mov     [rsp+138h+Reply], eax
0x18001d1da  mov     esi, [rsp+138h+dwMilliseconds]
0x18001d1de  mov     r15b, [rsp+138h+var_E4]
0x18001d1e3  mov     r14b, r15b
0x18001d1e6  test    eax, eax
0x18001d1e8  jns     short loc_18001D1FC
0x18001d1ea  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001d1f1  mov     r8d, 240h
0x18001d1f7  jmp     loc_18001D2C6
0x18001d1fc  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001d204  mov     r9d, esi; dwMilliseconds
0x18001d207  xor     r8d, r8d; bWaitAll
0x18001d20a  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001d20f  lea     ecx, [r8+1]; nCount
0x18001d213  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d219  mov     esi, eax
0x18001d21b  mov     r12d, 102h
0x18001d221  test    r14b, r14b
0x18001d224  jnz     short loc_18001D275
0x18001d226  cmp     esi, r12d
0x18001d229  jz      short loc_18001D230
0x18001d22b  cmp     esi, 1
0x18001d22e  jnz     short loc_18001D275
0x18001d230  mov     edx, 1; fAbort
0x18001d235  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001d23d  call    cs:__imp_RpcAsyncCancelCall
0x18001d243  cmp     esi, r12d
0x18001d246  jnz     short loc_18001D24D
0x18001d248  mov     r15b, 1
0x18001d24b  jmp     short loc_18001D250
0x18001d24d  mov     r14b, 1
0x18001d250  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001d258  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001d25c  xor     r8d, r8d; bWaitAll
0x18001d25f  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001d264  lea     ecx, [r8+1]; nCount
0x18001d268  call    cs:__imp_WaitForMultipleObjectsEx
0x18001d26e  mov     esi, eax
0x18001d270  test    r15b, r15b
0x18001d273  jz      short loc_18001D221
0x18001d275  test    esi, esi
0x18001d277  jz      short loc_18001D294
0x18001d279  call    cs:__imp_GetLastError
0x18001d27f  test    eax, eax
0x18001d281  jle     short loc_18001D28B
0x18001d283  movzx   eax, ax
0x18001d286  or      eax, 80070000h
0x18001d28b  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001d292  jmp     short loc_18001D2BC
0x18001d294  lea     rdx, [rsp+138h+Reply]; Reply
0x18001d299  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001d2a1  call    cs:__imp_RpcAsyncCompleteCall
0x18001d2a7  test    eax, eax
0x18001d2a9  jz      short loc_18001D2DB
0x18001d2ab  jle     short loc_18001D2B5
0x18001d2ad  movzx   eax, ax
0x18001d2b0  or      eax, 80070000h
0x18001d2b5  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001d2bc  mov     r8d, 240h; unsigned int
0x18001d2c2  mov     [rsp+138h+Reply], eax
0x18001d2c6  mov     [rsp+138h+bAlertable], eax
0x18001d2ca  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d2d1  mov     ecx, 2; unsigned __int8
0x18001d2d6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d2db  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18001d2e3  test    rcx, rcx
0x18001d2e6  jz      short loc_18001D2EE
0x18001d2e8  call    cs:__imp_CloseHandle
0x18001d2ee  test    r15b, r15b
0x18001d2f1  jz      short loc_18001D332
0x18001d2f3  mov     [rsp+138h+Reply], 800705B4h
0x18001d2fb  lea     rdx, [rsp+138h+var_DC]
0x18001d300  lea     rcx, aWlidccreatecon_0; "WLIDCCreateContextEx"
0x18001d307  call    ??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)
0x18001d30c  mov     eax, [rsp+138h+Reply]
0x18001d310  mov     [rsp+138h+bAlertable], eax
0x18001d314  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001d31b  mov     r8d, 240h; unsigned int
0x18001d321  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d328  mov     ecx, 2; unsigned __int8
0x18001d32d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d332  test    r14b, r14b
0x18001d335  jz      short loc_18001D362
0x18001d337  mov     eax, 800704C7h
0x18001d33c  mov     [rsp+138h+Reply], eax
0x18001d340  mov     [rsp+138h+bAlertable], eax
0x18001d344  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001d34b  mov     r8d, 240h; unsigned int
0x18001d351  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001d358  mov     ecx, 2; unsigned __int8
0x18001d35d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001d362  cmp     [rsp+138h+Reply], 800706B5h
0x18001d36a  jz      short loc_18001D376
0x18001d36c  cmp     [rsp+138h+Reply], 800706BAh
0x18001d374  jnz     short loc_18001D37B
0x18001d376  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001d37b  lea     rcx, [rsp+138h+var_D8]; this
0x18001d380  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001d385  lea     rdx, aWlidccreatecon_0; "WLIDCCreateContextEx"
0x18001d38c  mov     ecx, [rsp+138h+Reply]; int
0x18001d390  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x18001d395  mov     rcx, [rsp+138h+var_38]
0x18001d39d  xor     rcx, rsp; StackCookie
0x18001d3a0  call    __security_check_cookie
0x18001d3a5  add     rsp, 110h
0x18001d3ac  pop     r15
0x18001d3ae  pop     r14
0x18001d3b0  pop     r13
0x18001d3b2  pop     r12
0x18001d3b4  pop     rsi
0x18001d3b5  retn
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
