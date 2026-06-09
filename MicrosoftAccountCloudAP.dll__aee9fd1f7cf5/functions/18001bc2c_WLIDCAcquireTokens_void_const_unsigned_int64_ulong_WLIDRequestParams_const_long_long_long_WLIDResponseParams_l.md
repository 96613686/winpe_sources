# WLIDCAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,long *,void *,int)

- ea: `0x18001bc2c`
- end: `0x18001c0f1`
- name: `?WLIDCAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@3PEAXH@Z`
- size: `1221`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, struct _WLIDRequestParams *const, int *, int *, int *, struct _WLIDResponseParams **, int *, void *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019460`
- `0x1800194e0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180019c10`
- `0x18001ba00`
- `0x18001bb84`
- `0x18001bc2c`
- `0x180020750`
- `0x1800267c0`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bf44`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bf9c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bf44`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bf9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bd9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bfad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c022`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001bea1`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18001bea1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001bfd8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001bfd8`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001bd54`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18001bd54`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001bf6e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001bf6e`

## string_xrefs

- `0x18001bdc0`: `RPC failed to create new event, hr = %#x`
- `0x18001bfec`: `RPC Async complete call failed, hr = %#x`
- `0x18001c0c4`: `WLIDCAcquireTokens`

## pseudocode

```c
__int64 __fastcall WLIDCAcquireTokens(
        void *const a1,
        __int64 a2,
        int a3,
        struct _WLIDRequestParams *const a4,
        int *a5,
        int *a6,
        int *a7,
        struct _WLIDResponseParams **a8,
        int *a9,
        void *a10,
        int a11)
{
  DWORD v12; // r12d
  char v13; // r15
  char v14; // r14
  int LastError; // eax
  const unsigned __int16 *v16; // r9
  unsigned int v17; // r8d
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  DWORD v19; // esi
  PFN_RPCNOTIFICATION_ROUTINE NotificationRoutine; // rcx
  int v21; // ecx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-188h]
  int Reply; // [rsp+90h] [rbp-118h] BYREF
  char v25; // [rsp+94h] [rbp-114h]
  DWORD dwMilliseconds; // [rsp+98h] [rbp-110h] BYREF
  int v27; // [rsp+9Ch] [rbp-10Ch] BYREF
  int v28; // [rsp+A0h] [rbp-108h]
  int v29; // [rsp+A4h] [rbp-104h]
  DWORD v30; // [rsp+A8h] [rbp-100h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-F8h] BYREF
  int *v32; // [rsp+C0h] [rbp-E8h]
  struct _WLIDResponseParams **v33; // [rsp+C8h] [rbp-E0h]
  int *v34; // [rsp+D0h] [rbp-D8h]
  int *v35; // [rsp+D8h] [rbp-D0h]
  int *v36; // [rsp+E0h] [rbp-C8h]
  struct _WLIDRequestParams *v37; // [rsp+E8h] [rbp-C0h]
  __int64 v38; // [rsp+F0h] [rbp-B8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+100h] [rbp-A8h] BYREF

  v37 = a4;
  v28 = a3;
  v38 = a2;
  v36 = a5;
  v35 = a6;
  v34 = a7;
  v33 = a8;
  v32 = a9;
  v27 = 0;
  Reply = 0;
  dwMilliseconds = 0;
  WLIDCGetTimeOutValue((unsigned int)a1, a2, &dwMilliseconds);
  if ( a11 )
    dwMilliseconds *= 3;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v12 = dwMilliseconds;
  v30 = dwMilliseconds;
  v13 = 0;
  v25 = 0;
  v14 = 0;
  *(_OWORD *)Handles = 0;
  LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"RPC AsyncInitializeHandle failed, hr = %#x";
LABEL_7:
    v17 = 669;
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
    v16 = L"RPC failed to create new event, hr = %#x";
    goto LABEL_7;
  }
  Handles[0] = EventW;
  if ( a10 )
    Handles[1] = a10;
  v29 = (a10 != 0) + 1;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&liveidsvc_ProxyInfo,
    0xFu,
    0,
    &pAsync,
    a1,
    v38,
    v28,
    v37,
    &qword_18003AB48,
    0,
    &qword_18003AB48,
    v36,
    v35,
    v34,
    &v27,
    v33,
    v32);
  v19 = WaitForMultipleObjectsEx((a10 != 0) + 1, Handles, 0, v12, 0);
  do
  {
    if ( v14 || v19 != 258 && v19 != 1 )
      break;
    RpcAsyncCancelCall(&pAsync, 1);
    if ( v19 == 258 )
      v13 = 1;
    else
      v14 = 1;
    v19 = WaitForMultipleObjectsEx(1u, Handles, 0, 0xFFFFFFFF, 0);
  }
  while ( !v13 );
  if ( v19 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"Encountered error while waiting on RPC call, hr = %#x";
  }
  else
  {
    LastError = RpcAsyncCompleteCall(&pAsync, &Reply);
    if ( !LastError )
      goto LABEL_32;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = L"RPC Async complete call failed, hr = %#x";
  }
  v17 = 684;
LABEL_31:
  Reply = LastError;
  bAlertable[0] = LastError;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
    v17,
    v16,
    *(_QWORD *)bAlertable);
LABEL_32:
  NotificationRoutine = pAsync.u.APC.NotificationRoutine;
  if ( pAsync.u.APC.NotificationRoutine )
    CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v13 )
  {
    Reply = -2147023436;
    MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],unsigned long &>(
      (__int64)NotificationRoutine,
      (int *)&v30);
    bAlertable[0] = Reply;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2ACu,
      L"RPC call timed out, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  if ( v14 )
  {
    Reply = -2147023673;
    bAlertable[0] = -2147023673;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      0x2ACu,
      L"RPC call was cancelled, hr = %#x",
      *(_QWORD *)bAlertable);
  }
  v21 = Reply;
  if ( Reply == -2147023179 || Reply == -2147023174 )
  {
    TraceServiceStatus();
    v21 = Reply;
  }
  return TranslateRpcServiceError(v21, "WLIDCAcquireTokens");
}

```

## disassembly

```asm
0x18001bc2c  push    rsi
0x18001bc2e  push    r12
0x18001bc30  push    r13
0x18001bc32  push    r14
0x18001bc34  push    r15
0x18001bc36  sub     rsp, 180h
0x18001bc3d  mov     rax, cs:__security_cookie
0x18001bc44  xor     rax, rsp
0x18001bc47  mov     [rsp+1A8h+var_38], rax
0x18001bc4f  mov     [rsp+1A8h+var_C0], r9
0x18001bc57  mov     [rsp+1A8h+var_108], r8d
0x18001bc5f  mov     [rsp+1A8h+var_B8], rdx
0x18001bc67  mov     r13, rcx
0x18001bc6a  mov     rax, [rsp+1A8h+arg_20]
0x18001bc72  mov     [rsp+1A8h+var_C8], rax
0x18001bc7a  mov     rax, [rsp+1A8h+arg_28]
0x18001bc82  mov     [rsp+1A8h+var_D0], rax
0x18001bc8a  mov     rax, [rsp+1A8h+arg_30]
0x18001bc92  mov     [rsp+1A8h+var_D8], rax
0x18001bc9a  mov     rax, [rsp+1A8h+arg_38]
0x18001bca2  mov     [rsp+1A8h+var_E0], rax
0x18001bcaa  mov     rax, [rsp+1A8h+arg_40]
0x18001bcb2  mov     [rsp+1A8h+var_E8], rax
0x18001bcba  mov     [rsp+1A8h+var_10C], 0
0x18001bcc5  mov     [rsp+1A8h+Reply], 0
0x18001bcd0  mov     [rsp+1A8h+dwMilliseconds], 0
0x18001bcdb  lea     r8, [rsp+1A8h+dwMilliseconds]; unsigned int *
0x18001bce3  call    ?WLIDCGetTimeOutValue@@YAJKKPEAK@Z; WLIDCGetTimeOutValue(ulong,ulong,ulong *)
0x18001bce8  cmp     [rsp+1A8h+arg_50], 0
0x18001bcf0  jz      short loc_18001BD03
0x18001bcf2  mov     eax, [rsp+1A8h+dwMilliseconds]
0x18001bcf9  lea     eax, [rax+rax*2]
0x18001bcfc  mov     [rsp+1A8h+dwMilliseconds], eax
0x18001bd03  xor     edx, edx; Val
0x18001bd05  lea     r8d, [rdx+70h]; Size
0x18001bd09  lea     rcx, [rsp+1A8h+pAsync]; void *
0x18001bd11  call    memset_0
0x18001bd16  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x18001bd1e  mov     [rsp+1A8h+dwMilliseconds], r12d
0x18001bd26  mov     [rsp+1A8h+var_100], r12d
0x18001bd2e  xor     r15b, r15b
0x18001bd31  mov     [rsp+1A8h+var_114], r15b
0x18001bd39  xor     r14b, r14b
0x18001bd3c  xorps   xmm0, xmm0
0x18001bd3f  movups  xmmword ptr [rsp+1A8h+Handles], xmm0
0x18001bd47  mov     edx, 70h ; 'p'; Size
0x18001bd4c  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18001bd54  call    cs:__imp_RpcAsyncInitializeHandle
0x18001bd5a  test    eax, eax
0x18001bd5c  jz      short loc_18001BD7A
0x18001bd5e  jle     short loc_18001BD68
0x18001bd60  movzx   eax, ax
0x18001bd63  or      eax, 80070000h
0x18001bd68  lea     r9, aRpcAsyncinitia; "RPC AsyncInitializeHandle failed, hr = "...
0x18001bd6f  mov     r8d, 29Dh
0x18001bd75  jmp     loc_18001BFF9
0x18001bd7a  mov     [rsp+1A8h+pAsync.UserInfo], 0
0x18001bd86  mov     [rsp+1A8h+pAsync.NotificationType], 1
0x18001bd91  xor     r9d, r9d; lpName
0x18001bd94  xor     r8d, r8d; bInitialState
0x18001bd97  xor     edx, edx; bManualReset
0x18001bd99  xor     ecx, ecx; lpEventAttributes
0x18001bd9b  call    cs:__imp_CreateEventW
0x18001bda1  mov     qword ptr [rsp+1A8h+pAsync.u], rax
0x18001bda9  test    rax, rax
0x18001bdac  jnz     short loc_18001BDC9
0x18001bdae  call    cs:__imp_GetLastError
0x18001bdb4  test    eax, eax
0x18001bdb6  jle     short loc_18001BDC0
0x18001bdb8  movzx   eax, ax
0x18001bdbb  or      eax, 80070000h
0x18001bdc0  lea     r9, aRpcFailedToCre; "RPC failed to create new event, hr = %#"...
0x18001bdc7  jmp     short loc_18001BD6F
0x18001bdc9  mov     [rsp+1A8h+Handles], rax
0x18001bdd1  mov     rax, [rsp+1A8h+arg_48]
0x18001bdd9  test    rax, rax
0x18001bddc  jz      short loc_18001BDE6
0x18001bdde  mov     [rsp+1A8h+Handles+8], rax
0x18001bde6  neg     rax
0x18001bde9  sbb     esi, esi
0x18001bdeb  neg     esi
0x18001bded  inc     esi
0x18001bdef  mov     [rsp+1A8h+var_104], esi
0x18001bdf6  mov     rax, [rsp+1A8h+var_E8]
0x18001bdfe  mov     [rsp+1A8h+var_128], rax
0x18001be06  mov     rax, [rsp+1A8h+var_E0]
0x18001be0e  mov     [rsp+1A8h+var_130], rax
0x18001be13  lea     rax, [rsp+1A8h+var_10C]
0x18001be1b  mov     [rsp+1A8h+var_138], rax
0x18001be20  mov     rax, [rsp+1A8h+var_D8]
0x18001be28  mov     [rsp+1A8h+var_140], rax
0x18001be2d  mov     rax, [rsp+1A8h+var_D0]
0x18001be35  mov     [rsp+1A8h+var_148], rax
0x18001be3a  mov     rax, [rsp+1A8h+var_C8]
0x18001be42  mov     [rsp+1A8h+var_150], rax
0x18001be47  lea     rax, qword_18003AB48
0x18001be4e  mov     [rsp+1A8h+var_158], rax
0x18001be53  mov     [rsp+1A8h+var_160], 0
0x18001be5c  mov     [rsp+1A8h+var_168], rax
0x18001be61  mov     rax, [rsp+1A8h+var_C0]
0x18001be69  mov     [rsp+1A8h+var_170], rax
0x18001be6e  mov     eax, [rsp+1A8h+var_108]
0x18001be75  mov     [rsp+1A8h+var_178], eax
0x18001be79  mov     rax, [rsp+1A8h+var_B8]
0x18001be81  mov     [rsp+1A8h+var_180], rax
0x18001be86  mov     qword ptr [rsp+1A8h+bAlertable], r13
0x18001be8b  lea     r9, [rsp+1A8h+pAsync]
0x18001be93  xor     r8d, r8d; pReturnValue
0x18001be96  lea     edx, [r8+0Fh]; nProcNum
0x18001be9a  lea     rcx, ?liveidsvc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001bea1  call    cs:__imp_Ndr64AsyncClientCall
0x18001bea7  mov     eax, [rsp+1A8h+Reply]
0x18001beae  jmp     short loc_18001BF16
0x18001beb0  test    eax, eax
0x18001beb2  jle     short loc_18001BEBC
0x18001beb4  movzx   eax, ax
0x18001beb7  or      eax, 80070000h
0x18001bebc  mov     [rsp+1A8h+Reply], eax
0x18001bec3  mov     [rsp+1A8h+bAlertable], eax
0x18001bec7  lea     r9, aRpcCallThrewAn; "RPC call threw an exception code, hr = "...
0x18001bece  mov     r8d, 2ACh; unsigned int
0x18001bed4  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001bedb  mov     ecx, 2; unsigned __int8
0x18001bee0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bee5  mov     eax, [rsp+1A8h+Reply]
0x18001beec  test    eax, eax
0x18001beee  js      short loc_18001BEFC
0x18001bef0  mov     eax, 8000FFFFh
0x18001bef5  mov     [rsp+1A8h+Reply], eax
0x18001befc  mov     r12d, [rsp+1A8h+dwMilliseconds]
0x18001bf04  mov     r15b, [rsp+1A8h+var_114]
0x18001bf0c  mov     r14b, r15b
0x18001bf0f  mov     esi, [rsp+1A8h+var_104]
0x18001bf16  test    eax, eax
0x18001bf18  jns     short loc_18001BF2C
0x18001bf1a  lea     r9, aRpcCallFailedH; "RPC call failed, hr = %#x"
0x18001bf21  mov     r8d, 2ACh
0x18001bf27  jmp     loc_18001C000
0x18001bf2c  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x18001bf34  mov     r9d, r12d; dwMilliseconds
0x18001bf37  xor     r8d, r8d; bWaitAll
0x18001bf3a  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x18001bf42  mov     ecx, esi; nCount
0x18001bf44  call    cs:__imp_WaitForMultipleObjectsEx
0x18001bf4a  mov     esi, eax
0x18001bf4c  mov     r12d, 102h
0x18001bf52  test    r14b, r14b
0x18001bf55  jnz     short loc_18001BFA9
0x18001bf57  cmp     esi, r12d
0x18001bf5a  jz      short loc_18001BF61
0x18001bf5c  cmp     esi, 1
0x18001bf5f  jnz     short loc_18001BFA9
0x18001bf61  mov     edx, 1; fAbort
0x18001bf66  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18001bf6e  call    cs:__imp_RpcAsyncCancelCall
0x18001bf74  cmp     esi, r12d
0x18001bf77  jnz     short loc_18001BF7E
0x18001bf79  mov     r15b, 1
0x18001bf7c  jmp     short loc_18001BF81
0x18001bf7e  mov     r14b, 1
0x18001bf81  mov     [rsp+1A8h+bAlertable], 0; bAlertable
0x18001bf89  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001bf8d  xor     r8d, r8d; bWaitAll
0x18001bf90  lea     rdx, [rsp+1A8h+Handles]; lpHandles
0x18001bf98  lea     ecx, [r8+1]; nCount
0x18001bf9c  call    cs:__imp_WaitForMultipleObjectsEx
0x18001bfa2  mov     esi, eax
0x18001bfa4  test    r15b, r15b
0x18001bfa7  jz      short loc_18001BF52
0x18001bfa9  test    esi, esi
0x18001bfab  jz      short loc_18001BFC8
0x18001bfad  call    cs:__imp_GetLastError
0x18001bfb3  test    eax, eax
0x18001bfb5  jle     short loc_18001BFBF
0x18001bfb7  movzx   eax, ax
0x18001bfba  or      eax, 80070000h
0x18001bfbf  lea     r9, aEncounteredErr; "Encountered error while waiting on RPC "...
0x18001bfc6  jmp     short loc_18001BFF3
0x18001bfc8  lea     rdx, [rsp+1A8h+Reply]; Reply
0x18001bfd0  lea     rcx, [rsp+1A8h+pAsync]; pAsync
0x18001bfd8  call    cs:__imp_RpcAsyncCompleteCall
0x18001bfde  test    eax, eax
0x18001bfe0  jz      short loc_18001C015
0x18001bfe2  jle     short loc_18001BFEC
0x18001bfe4  movzx   eax, ax
0x18001bfe7  or      eax, 80070000h
0x18001bfec  lea     r9, aRpcAsyncComple; "RPC Async complete call failed, hr = %#"...
0x18001bff3  mov     r8d, 2ACh; unsigned int
0x18001bff9  mov     [rsp+1A8h+Reply], eax
0x18001c000  mov     [rsp+1A8h+bAlertable], eax
0x18001c004  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c00b  mov     ecx, 2; unsigned __int8
0x18001c010  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c015  mov     rcx, qword ptr [rsp+1A8h+pAsync.u]; hObject
0x18001c01d  test    rcx, rcx
0x18001c020  jz      short loc_18001C028
0x18001c022  call    cs:__imp_CloseHandle
0x18001c028  test    r15b, r15b
0x18001c02b  jz      short loc_18001C06E
0x18001c02d  mov     [rsp+1A8h+Reply], 800705B4h
0x18001c038  lea     rdx, [rsp+1A8h+var_100]
0x18001c040  call    ??$RPCCallTimedOut@AEAY0BD@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BD@$$CBDAEAK@Z; MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[19],ulong &>(char const (&)[19],ulong &)
0x18001c045  mov     eax, [rsp+1A8h+Reply]
0x18001c04c  mov     [rsp+1A8h+bAlertable], eax
0x18001c050  lea     r9, aRpcCallTimedOu; "RPC call timed out, hr = %#x"
0x18001c057  mov     r8d, 2ACh; unsigned int
0x18001c05d  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c064  mov     ecx, 2; unsigned __int8
0x18001c069  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c06e  test    r14b, r14b
0x18001c071  jz      short loc_18001C0A1
0x18001c073  mov     eax, 800704C7h
0x18001c078  mov     [rsp+1A8h+Reply], eax
0x18001c07f  mov     [rsp+1A8h+bAlertable], eax
0x18001c083  lea     r9, aRpcCallWasCanc; "RPC call was cancelled, hr = %#x"
0x18001c08a  mov     r8d, 2ACh; unsigned int
0x18001c090  lea     rdx, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001c097  mov     ecx, 2; unsigned __int8
0x18001c09c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001c0a1  mov     ecx, [rsp+1A8h+Reply]
0x18001c0a8  cmp     ecx, 800706B5h
0x18001c0ae  jz      short loc_18001C0B8
0x18001c0b0  cmp     ecx, 800706BAh
0x18001c0b6  jnz     short loc_18001C0C4
0x18001c0b8  call    ?TraceServiceStatus@@YAJXZ; TraceServiceStatus(void)
0x18001c0bd  mov     ecx, [rsp+1A8h+Reply]; int
0x18001c0c4  lea     rdx, aWlidcacquireto_0; "WLIDCAcquireTokens"
0x18001c0cb  call    ?TranslateRpcServiceError@@YAJJPEBD@Z; TranslateRpcServiceError(long,char const *)
0x18001c0d0  mov     rcx, [rsp+1A8h+var_38]
0x18001c0d8  xor     rcx, rsp; StackCookie
0x18001c0db  call    __security_check_cookie
0x18001c0e0  add     rsp, 180h
0x18001c0e7  pop     r15
0x18001c0e9  pop     r14
0x18001c0eb  pop     r13
0x18001c0ed  pop     r12
0x18001c0ef  pop     rsi
0x18001c0f0  retn
0x180030fb6  push    rbp
0x180030fb8  sub     rsp, 90h
0x180030fbf  mov     rbp, rdx
0x180030fc2  mov     rcx, [rcx]
0x180030fc5  mov     ecx, [rcx]; unsigned int
0x180030fc7  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180030fcc  nop
0x180030fcd  add     rsp, 90h
0x180030fd4  pop     rbp
0x180030fd5  retn
```
