# WLIDCEnumIdentities(unsigned __int64,ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x18001ddc0`
- end: `0x18001e15e`
- name: `?WLIDCEnumIdentities@@YAJ_KPEBG1PEAKPEAPEAPEAG@Z`
- size: `926`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800196d0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019c98`
- `0x18001ba00`
- `0x18001ddc0`
- `0x180020750`
- `0x1800231a4`
- `0x180023360`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dfcb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e023`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dfcb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e023`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dec2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ded5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ded5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0a3`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001df40`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001df40`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e05c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e05c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001de7b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001de7b`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001dff5`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001dff5`

## string_xrefs

- `0x18001dee7`: `RPC failed to create new event, hr = %#x`
- `0x18001e070`: `RPC Async complete call failed, hr = %#x`

## pseudocode

```c
__int64 __fastcall WLIDCEnumIdentities(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  __int64 result; // rax
  DWORD v8; // esi
  char v9; // r15
  char v10; // r14
  int LastError; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v15; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-118h]
  int Reply; // [rsp+50h] [rbp-E8h] BYREF
  char v19; // [rsp+54h] [rbp-E4h]
  DWORD dwMilliseconds; // [rsp+58h] [rbp-E0h] BYREF
  DWORD v21; // [rsp+5Ch] [rbp-DCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int16 ***v23; // [rsp+68h] [rbp-D0h]
  unsigned int *v24; // [rsp+70h] [rbp-C8h]
  const unsigned __int16 *v25; // [rsp+78h] [rbp-C0h]
  HANDLE Handles[2]; // [rsp+80h] [rbp-B8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  v24 = a4;
  v25 = a3;
  v23 = a5;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue(a1, (unsigned int)a2, &dwMilliseconds);
  v22 = 0;
  result = CWLIDBinding::Bind((CWLIDBinding *)&v22);
  Reply = result;
  if ( (int)result < 0 )
    return result;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = dwMilliseconds;
  v21 = dwMilliseconds;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_6:
    v13 = 812;
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
    v12 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_6;
  }
  Handles[0] = EventW;
  Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo, 0x19u, 0, &pAsync, v22, a1, a2, v25, v24, v23);
  LastError = Reply;
  if ( Reply < 0 )
  {
    v12 = L"RPC call failed, hr = %#x";
    v13 = 814;
LABEL_31:
    bAlertable[0] = LastError;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      v13,
      v12,
      *(_QWORD *)bAlertable);
    goto LABEL_32;
  }
  v15 = WaitForMultipleObjectsEx(1u, Handles, 0, v8, 0);
  do
  {
    if ( v10 || v15 != 258 && v15 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 == 258 )
      v9 = 1;
    else
      v10 = 1;
    v15 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v9 );
  if ( v15 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"Encountered error while waiting on RPC call, hr = %#x";
LABEL_29:
    v13 = 814;
    goto LABEL_30;
  }
  LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = L"RPC Async complete call failed, hr = %#x";
    goto LABEL_29;
  }
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v9 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v21);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x32Eu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v10 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x32Eu,
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
0x18001ddc0  push    rsi
0x18001ddc2  push    r12
0x18001ddc4  push    r13
0x18001ddc6  push    r14
0x18001ddc8  push    r15
0x18001ddca  sub     rsp, 110h
0x18001ddd1  mov     rax, cs:__security_cookie
0x18001ddd8  xor     rax, rsp
0x18001dddb  mov     [rsp+138h+var_38], rax
0x18001dde3  mov     [rsp+138h+var_C8], r9
0x18001dde8  mov     [rsp+138h+var_C0], r8
0x18001dded  mov     r13, rdx
0x18001ddf0  mov     r12, rcx
0x18001ddf3  mov     rax, [rsp+138h+arg_20]
0x18001ddfb  mov     [rsp+138h+var_D0], rax
0x18001de00  mov     [rsp+138h+dwMilliseconds], 0
0x18001de08  lea     r8, [rsp+138h+dwMilliseconds]; unsigned int *
0x18001de0d  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001de12  mov     [rsp+138h+Reply], 0
0x18001de1a  mov     [rsp+138h+var_D8], 0
0x18001de23  lea     rcx, [rsp+138h+var_D8]; this
0x18001de28  call    ?Bind@CWLIDBinding@@QEAAJXZ; CWLIDBinding::Bind(void)
0x18001de2d  mov     [rsp+138h+Reply], eax
0x18001de31  test    eax, eax
0x18001de33  js      loc_18001E13D
0x18001de39  xor     edx, edx; Val
0x18001de3b  lea     r8d, [rdx+70h]; Size
0x18001de3f  lea     rcx, [rsp+138h+pAsync]; void *
0x18001de47  call    memset_0
0x18001de4c  mov     esi, [rsp+138h+dwMilliseconds]
0x18001de50  mov     [rsp+138h+dwMilliseconds], esi
0x18001de54  mov     [rsp+138h+var_DC], esi
0x18001de58  xor     r15b, r15b
0x18001de5b  mov     [rsp+138h+var_E4], r15b
0x18001de60  xor     r14b, r14b
0x18001de63  xorps   xmm0, xmm0
0x18001de66  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x18001de6e  mov     edx, 70h ; 'p'; Size
0x18001de73  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001de7b  call    cs:__imp_RpcAsyncInitializeHandle
0x18001de81  test    eax, eax
0x18001de83  jz      short loc_18001DEA1
0x18001de85  jle     short loc_18001DE8F
0x18001de87  movzx   eax, ax
0x18001de8a  or      eax, 80070000h
0x18001de8f  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001de96  mov     r8d, 32Ch
0x18001de9c  jmp     loc_18001E07D
0x18001dea1  mov     [rsp+138h+pAsync.UserInfo], 0
0x18001dead  mov     [rsp+138h+pAsync.NotificationType], 1
0x18001deb8  xor     r9d, r9d; lpName
0x18001debb  xor     r8d, r8d; bInitialState
0x18001debe  xor     edx, edx; bManualReset
0x18001dec0  xor     ecx, ecx; lpEventAttributes
0x18001dec2  call    cs:__imp_CreateEventW
0x18001dec8  mov     qword ptr [rsp+138h+pAsync.u], rax
0x18001ded0  test    rax, rax
0x18001ded3  jnz     short loc_18001DEF0
0x18001ded5  call    cs:__imp_GetLastError
0x18001dedb  test    eax, eax
0x18001dedd  jle     short loc_18001DEE7
0x18001dedf  movzx   eax, ax
0x18001dee2  or      eax, 80070000h
0x18001dee7  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001deee  jmp     short loc_18001DE96
0x18001def0  mov     [rsp+138h+Handles], rax
0x18001def8  mov     rax, [rsp+138h+var_D0]
0x18001defd  mov     [rsp+138h+var_F0], rax
0x18001df02  mov     rax, [rsp+138h+var_C8]
0x18001df07  mov     [rsp+138h+var_F8], rax
0x18001df0c  mov     rax, [rsp+138h+var_C0]
0x18001df11  mov     [rsp+138h+var_100], rax
0x18001df16  mov     [rsp+138h+var_108], r13
0x18001df1b  mov     [rsp+138h+var_110], r12
0x18001df20  mov     rax, [rsp+138h+var_D8]
0x18001df25  mov     qword ptr [rsp+138h+bAlertable], rax
0x18001df2a  lea     r9, [rsp+138h+pAsync]
0x18001df32  xor     r8d, r8d; pReturnValue
0x18001df35  lea     edx, [r8+19h]; nProcNum
0x18001df39  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001df40  call    cs:__imp_Ndr64AsyncClientCall
0x18001df46  mov     eax, [rsp+138h+Reply]
0x18001df4a  jmp     short loc_18001DF9B
0x18001df4c  test    eax, eax
0x18001df4e  jle     short loc_18001DF58
0x18001df50  movzx   eax, ax
0x18001df53  or      eax, 80070000h
0x18001df58  mov     [rsp+138h+Reply], eax
0x18001df5c  mov     [rsp+138h+bAlertable], eax
0x18001df60  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001df67  mov     r8d, 32Eh; unsigned int
0x18001df6d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001df74  mov     ecx, 2; unsigned __int8
0x18001df79  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001df7e  mov     eax, [rsp+138h+Reply]
0x18001df82  test    eax, eax
0x18001df84  js      short loc_18001DF8F
0x18001df86  mov     eax, 8000FFFFh
0x18001df8b  mov     [rsp+138h+Reply], eax
0x18001df8f  mov     esi, [rsp+138h+dwMilliseconds]
0x18001df93  mov     r15b, [rsp+138h+var_E4]
0x18001df98  mov     r14b, r15b
0x18001df9b  test    eax, eax
0x18001df9d  jns     short loc_18001DFB1
0x18001df9f  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001dfa6  mov     r8d, 32Eh
0x18001dfac  jmp     loc_18001E081
0x18001dfb1  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001dfb9  mov     r9d, esi; dwMilliseconds
0x18001dfbc  xor     r8d, r8d; bWaitAll
0x18001dfbf  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001dfc7  lea     ecx, [r8+1]; nCount
0x18001dfcb  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dfd1  mov     esi, eax
0x18001dfd3  mov     r12d, 102h
0x18001dfd9  test    r14b, r14b
0x18001dfdc  jnz     short loc_18001E030
0x18001dfde  cmp     esi, r12d
0x18001dfe1  jz      short loc_18001DFE8
0x18001dfe3  cmp     esi, 1
0x18001dfe6  jnz     short loc_18001E030
0x18001dfe8  mov     edx, 1; fAbort
0x18001dfed  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001dff5  call    cs:__imp_RpcAsyncCancelCall
0x18001dffb  cmp     esi, r12d
0x18001dffe  jnz     short loc_18001E005
0x18001e000  mov     r15b, 1
0x18001e003  jmp     short loc_18001E008
0x18001e005  mov     r14b, 1
0x18001e008  mov     [rsp+138h+bAlertable], 0; bAlertable
0x18001e010  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001e014  xor     r8d, r8d; bWaitAll
0x18001e017  lea     rdx, [rsp+138h+Handles]; lpHandles
0x18001e01f  lea     ecx, [r8+1]; nCount
0x18001e023  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e029  mov     esi, eax
0x18001e02b  test    r15b, r15b
0x18001e02e  jz      short loc_18001DFD9
0x18001e030  test    esi, esi
0x18001e032  jz      short loc_18001E04F
0x18001e034  call    cs:__imp_GetLastError
0x18001e03a  test    eax, eax
0x18001e03c  jle     short loc_18001E046
0x18001e03e  movzx   eax, ax
0x18001e041  or      eax, 80070000h
0x18001e046  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001e04d  jmp     short loc_18001E077
0x18001e04f  lea     rdx, [rsp+138h+Reply]; Reply
0x18001e054  lea     rcx, [rsp+138h+pAsync]; pAsync
0x18001e05c  call    cs:__imp_RpcAsyncCompleteCall
0x18001e062  test    eax, eax
0x18001e064  jz      short loc_18001E096
0x18001e066  jle     short loc_18001E070
0x18001e068  movzx   eax, ax
0x18001e06b  or      eax, 80070000h
0x18001e070  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001e077  mov     r8d, 32Eh; unsigned int
0x18001e07d  mov     [rsp+138h+Reply], eax
0x18001e081  mov     [rsp+138h+bAlertable], eax
0x18001e085  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e08c  mov     ecx, 2; unsigned __int8
0x18001e091  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e096  mov     rcx, qword ptr [rsp+138h+pAsync.u]; hObject
0x18001e09e  test    rcx, rcx
0x18001e0a1  jz      short loc_18001E0A9
0x18001e0a3  call    cs:__imp_CloseHandle
0x18001e0a9  test    r15b, r15b
0x18001e0ac  jz      short loc_18001E0E6
0x18001e0ae  mov     [rsp+138h+Reply], 800705B4h
0x18001e0b6  lea     rdx, [rsp+138h+var_DC]
0x18001e0bb  call    ??$RPCCallTimedOut@AEAY0BE@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BE@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[20],ulong &>(char const (&)[20],ulong &)
0x18001e0c0  mov     eax, [rsp+138h+Reply]
0x18001e0c4  mov     [rsp+138h+bAlertable], eax
0x18001e0c8  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001e0cf  mov     r8d, 32Eh; unsigned int
0x18001e0d5  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e0dc  mov     ecx, 2; unsigned __int8
0x18001e0e1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e0e6  test    r14b, r14b
0x18001e0e9  jz      short loc_18001E116
0x18001e0eb  mov     eax, 800704C7h
0x18001e0f0  mov     [rsp+138h+Reply], eax
0x18001e0f4  mov     [rsp+138h+bAlertable], eax
0x18001e0f8  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001e0ff  mov     r8d, 32Eh; unsigned int
0x18001e105  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001e10c  mov     ecx, 2; unsigned __int8
0x18001e111  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001e116  cmp     [rsp+138h+Reply], 800706B5h
0x18001e11e  jz      short loc_18001E12A
0x18001e120  cmp     [rsp+138h+Reply], 800706BAh
0x18001e128  jnz     short loc_18001E12F
0x18001e12a  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001e12f  lea     rcx, [rsp+138h+var_D8]; this
0x18001e134  call    ?Unbind@CWLIDBinding@@QEAAXXZ; CWLIDBinding::Unbind(void)
0x18001e139  mov     eax, [rsp+138h+Reply]
0x18001e13d  mov     rcx, [rsp+138h+var_38]
0x18001e145  xor     rcx, rsp; StackCookie
0x18001e148  call    __security_check_cookie
0x18001e14d  add     rsp, 110h
0x18001e154  pop     r15
0x18001e156  pop     r14
0x18001e158  pop     r13
0x18001e15a  pop     r12
0x18001e15c  pop     rsi
0x18001e15d  retn
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
