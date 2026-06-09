# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void * &&,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &&)

- ea: `0x1801921c0`
- end: `0x180192435`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@ZPEAXPEAU2@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@@Z$$QEAPEAX$$QEAPEAU4@@Z`
- size: `629`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009d4fc`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x1801911c0`
- `0x1801921c0`
- `0x18019410c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192297`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019231a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192297`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019231a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019223a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019223a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801922c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801922c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801923e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801923e9`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801922e6`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801922e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192355`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192355`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801921ff`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801921ff`

## string_xrefs

- `0x18019221f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192258`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192301`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192332`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192387`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801923c9`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192404`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  unsigned int v7; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  const char *v11; // r9
  DWORD LastError; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  const char *v15; // r9
  unsigned int v16; // edi
  unsigned int v17; // ebx
  unsigned int Reply[4]; // [rsp+20h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+30h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  memset_0(&pAsync, 0, sizeof(pAsync));
  v7 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v7 )
  {
    v8 = (const char *)v7;
    v9 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v11);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_UpdateRuntimeFeatureConfigurations(&pAsync, *a3, *a4);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v13 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v13 = 735;
    }
    else if ( LastError == 258 )
    {
      v13 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v13 = LastError;
    }
    v14 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v14,
        Reply[0]);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v15);
  }
  Reply[0] = 0;
  v16 = RpcAsyncCompleteCall(&pAsync, Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v13 )
  {
    if ( v16 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v16,
        Reply[0]);
    v8 = (const char *)v13;
    v9 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  if ( v16 )
  {
    v8 = (const char *)v16;
    v9 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v9,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v8,
             Reply[0]);
  }
  v17 = Reply[0];
  if ( (Reply[0] & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)Reply[0],
    Reply[0]);
  return v17;
}

```

## disassembly

```asm
0x1801921c0  push    rbx
0x1801921c2  push    rsi
0x1801921c3  push    rdi
0x1801921c4  sub     rsp, 0B0h
0x1801921cb  mov     rax, cs:__security_cookie
0x1801921d2  xor     rax, rsp
0x1801921d5  mov     [rsp+0C8h+var_28], rax
0x1801921dd  mov     rdi, r9
0x1801921e0  mov     rbx, r8
0x1801921e3  mov     esi, ecx
0x1801921e5  xor     edx, edx; Val
0x1801921e7  lea     r8d, [rdx+70h]; Size
0x1801921eb  lea     rcx, [rsp+0C8h+pAsync]; void *
0x1801921f0  call    memset_0
0x1801921f5  mov     edx, 70h ; 'p'; Size
0x1801921fa  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801921ff  call    cs:__imp_RpcAsyncInitializeHandle
0x180192206  nop     dword ptr [rax+rax+00h]
0x18019220b  test    eax, eax
0x18019220d  jz      short loc_180192230
0x18019220f  mov     r9d, eax; char *
0x180192212  mov     edx, 84h; void *
0x180192217  mov     rcx, [rsp+0C8h]; this
0x18019221f  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192226  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18019222b  jmp     loc_180192419
0x180192230  xor     r9d, r9d; lpName
0x180192233  xor     r8d, r8d; bInitialState
0x180192236  xor     edx, edx; bManualReset
0x180192238  xor     ecx, ecx; lpEventAttributes
0x18019223a  call    cs:__imp_CreateEventW
0x180192241  nop     dword ptr [rax+rax+00h]
0x180192246  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x18019224b  test    rax, rax
0x18019224e  jnz     short loc_18019226E
0x180192250  mov     rcx, [rsp+0C8h]; this
0x180192258  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019225f  mov     edx, 8Ah; void *
0x180192264  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180192269  jmp     loc_180192419
0x18019226e  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x180192277  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x18019227f  mov     r8, [rdi]
0x180192282  mov     rdx, [rbx]
0x180192285  lea     rcx, [rsp+0C8h+pAsync]
0x18019228a  call    CmaRpcClt_UpdateRuntimeFeatureConfigurations
0x18019228f  nop
0x180192290  mov     edx, esi; dwMilliseconds
0x180192292  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x180192297  call    cs:__imp_WaitForSingleObject
0x18019229e  nop     dword ptr [rax+rax+00h]
0x1801922a3  xor     ebx, ebx
0x1801922a5  test    eax, eax
0x1801922a7  jz      loc_180192343
0x1801922ad  cmp     eax, 80h
0x1801922b2  jz      short loc_1801922D7
0x1801922b4  cmp     eax, 102h
0x1801922b9  jz      short loc_1801922D0
0x1801922bb  cmp     eax, 0FFFFFFFFh
0x1801922be  jnz     short loc_1801922CC
0x1801922c0  call    cs:__imp_GetLastError
0x1801922c7  nop     dword ptr [rax+rax+00h]
0x1801922cc  mov     ebx, eax
0x1801922ce  jmp     short loc_1801922DC
0x1801922d0  mov     ebx, 5B4h
0x1801922d5  jmp     short loc_1801922DC
0x1801922d7  mov     ebx, 2DFh
0x1801922dc  mov     edx, 1; fAbort
0x1801922e1  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801922e6  call    cs:__imp_RpcAsyncCancelCall
0x1801922ed  nop     dword ptr [rax+rax+00h]
0x1801922f2  test    eax, eax
0x1801922f4  jz      short loc_180192312
0x1801922f6  mov     rcx, [rsp+0C8h]; this
0x1801922fe  mov     r9d, eax; char *
0x180192301  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192308  mov     edx, 0BEh; void *
0x18019230d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192312  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192315  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019231a  call    cs:__imp_WaitForSingleObject
0x180192321  nop     dword ptr [rax+rax+00h]
0x180192326  test    eax, eax
0x180192328  jz      short loc_180192343
0x18019232a  mov     rcx, [rsp+0C8h]; this
0x180192332  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192339  mov     edx, 0BFh; void *
0x18019233e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180192343  mov     [rsp+0C8h+Reply], 0; int
0x18019234b  lea     rdx, [rsp+0C8h+Reply]; Reply
0x180192350  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192355  call    cs:__imp_RpcAsyncCompleteCall
0x18019235c  nop     dword ptr [rax+rax+00h]
0x180192361  mov     edi, eax
0x180192363  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x180192368  call    cs:__imp_CloseHandle
0x18019236f  nop     dword ptr [rax+rax+00h]
0x180192374  test    ebx, ebx
0x180192376  jz      short loc_1801923A5
0x180192378  test    edi, edi
0x18019237a  jz      short loc_180192398
0x18019237c  mov     rcx, [rsp+0C8h]; this
0x180192384  mov     r9d, edi; char *
0x180192387  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019238e  mov     edx, 0CFh; void *
0x180192393  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192398  mov     r9d, ebx
0x18019239b  mov     edx, 0D0h
0x1801923a0  jmp     loc_180192217
0x1801923a5  test    edi, edi
0x1801923a7  jz      short loc_1801923B6
0x1801923a9  mov     r9d, edi
0x1801923ac  mov     edx, 0D4h
0x1801923b1  jmp     loc_180192217
0x1801923b6  mov     ebx, [rsp+0C8h+Reply]
0x1801923ba  test    ebx, ebx
0x1801923bc  jns     short loc_1801923DE
0x1801923be  mov     rcx, [rsp+0C8h]; this
0x1801923c6  mov     r9d, ebx; char *
0x1801923c9  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801923d0  mov     edx, 0D5h; void *
0x1801923d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801923da  mov     eax, ebx
0x1801923dc  jmp     short loc_180192419
0x1801923de  xor     eax, eax
0x1801923e0  jmp     short loc_180192419
0x1801923e2  mov     ebx, eax
0x1801923e4  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801923e9  call    cs:__imp_CloseHandle
0x1801923f0  nop     dword ptr [rax+rax+00h]
0x1801923f5  test    ebx, ebx
0x1801923f7  jz      short loc_180192417
0x1801923f9  mov     rcx, [rsp+0C8h]; this
0x180192401  mov     r9d, ebx; char *
0x180192404  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019240b  mov     edx, 96h; void *
0x180192410  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192415  jmp     short loc_180192419
0x180192417  xor     eax, eax
0x180192419  mov     rcx, [rsp+0C8h+var_28]
0x180192421  xor     rcx, rsp; StackCookie
0x180192424  call    __security_check_cookie
0x180192429  add     rsp, 0B0h
0x180192430  pop     rdi
0x180192431  pop     rsi
0x180192432  pop     rbx
0x180192433  retn
```
