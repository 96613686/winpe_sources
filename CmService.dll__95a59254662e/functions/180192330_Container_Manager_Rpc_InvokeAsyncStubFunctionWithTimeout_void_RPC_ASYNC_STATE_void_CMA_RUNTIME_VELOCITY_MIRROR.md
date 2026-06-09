# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *),void * &&,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &&)

- ea: `0x180192330`
- end: `0x1801925a5`
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
- `0x180191330`
- `0x180192330`
- `0x18019427c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192407`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019248a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192407`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019248a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801923aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801923aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801924d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801924d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192559`
- `RPCRT4!RpcAsyncCancelCall` at `0x180192456`
- `RPCRT4!RpcAsyncCancelCall` at `0x180192456`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801924c5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801924c5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18019236f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18019236f`

## string_xrefs

- `0x18019238f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801923c8`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192471`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801924a2`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801924f7`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192539`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192574`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

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
0x180192330  push    rbx
0x180192332  push    rsi
0x180192333  push    rdi
0x180192334  sub     rsp, 0B0h
0x18019233b  mov     rax, cs:__security_cookie
0x180192342  xor     rax, rsp
0x180192345  mov     [rsp+0C8h+var_28], rax
0x18019234d  mov     rdi, r9
0x180192350  mov     rbx, r8
0x180192353  mov     esi, ecx
0x180192355  xor     edx, edx; Val
0x180192357  lea     r8d, [rdx+70h]; Size
0x18019235b  lea     rcx, [rsp+0C8h+pAsync]; void *
0x180192360  call    memset_0
0x180192365  mov     edx, 70h ; 'p'; Size
0x18019236a  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x18019236f  call    cs:__imp_RpcAsyncInitializeHandle
0x180192376  nop     dword ptr [rax+rax+00h]
0x18019237b  test    eax, eax
0x18019237d  jz      short loc_1801923A0
0x18019237f  mov     r9d, eax; char *
0x180192382  mov     edx, 84h; void *
0x180192387  mov     rcx, [rsp+0C8h]; this
0x18019238f  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192396  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18019239b  jmp     loc_180192589
0x1801923a0  xor     r9d, r9d; lpName
0x1801923a3  xor     r8d, r8d; bInitialState
0x1801923a6  xor     edx, edx; bManualReset
0x1801923a8  xor     ecx, ecx; lpEventAttributes
0x1801923aa  call    cs:__imp_CreateEventW
0x1801923b1  nop     dword ptr [rax+rax+00h]
0x1801923b6  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x1801923bb  test    rax, rax
0x1801923be  jnz     short loc_1801923DE
0x1801923c0  mov     rcx, [rsp+0C8h]; this
0x1801923c8  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801923cf  mov     edx, 8Ah; void *
0x1801923d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801923d9  jmp     loc_180192589
0x1801923de  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x1801923e7  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x1801923ef  mov     r8, [rdi]
0x1801923f2  mov     rdx, [rbx]
0x1801923f5  lea     rcx, [rsp+0C8h+pAsync]
0x1801923fa  call    CmaRpcClt_UpdateRuntimeFeatureConfigurations
0x1801923ff  nop
0x180192400  mov     edx, esi; dwMilliseconds
0x180192402  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x180192407  call    cs:__imp_WaitForSingleObject
0x18019240e  nop     dword ptr [rax+rax+00h]
0x180192413  xor     ebx, ebx
0x180192415  test    eax, eax
0x180192417  jz      loc_1801924B3
0x18019241d  cmp     eax, 80h
0x180192422  jz      short loc_180192447
0x180192424  cmp     eax, 102h
0x180192429  jz      short loc_180192440
0x18019242b  cmp     eax, 0FFFFFFFFh
0x18019242e  jnz     short loc_18019243C
0x180192430  call    cs:__imp_GetLastError
0x180192437  nop     dword ptr [rax+rax+00h]
0x18019243c  mov     ebx, eax
0x18019243e  jmp     short loc_18019244C
0x180192440  mov     ebx, 5B4h
0x180192445  jmp     short loc_18019244C
0x180192447  mov     ebx, 2DFh
0x18019244c  mov     edx, 1; fAbort
0x180192451  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192456  call    cs:__imp_RpcAsyncCancelCall
0x18019245d  nop     dword ptr [rax+rax+00h]
0x180192462  test    eax, eax
0x180192464  jz      short loc_180192482
0x180192466  mov     rcx, [rsp+0C8h]; this
0x18019246e  mov     r9d, eax; char *
0x180192471  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192478  mov     edx, 0BEh; void *
0x18019247d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192482  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192485  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019248a  call    cs:__imp_WaitForSingleObject
0x180192491  nop     dword ptr [rax+rax+00h]
0x180192496  test    eax, eax
0x180192498  jz      short loc_1801924B3
0x18019249a  mov     rcx, [rsp+0C8h]; this
0x1801924a2  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801924a9  mov     edx, 0BFh; void *
0x1801924ae  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801924b3  mov     [rsp+0C8h+Reply], 0; int
0x1801924bb  lea     rdx, [rsp+0C8h+Reply]; Reply
0x1801924c0  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801924c5  call    cs:__imp_RpcAsyncCompleteCall
0x1801924cc  nop     dword ptr [rax+rax+00h]
0x1801924d1  mov     edi, eax
0x1801924d3  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801924d8  call    cs:__imp_CloseHandle
0x1801924df  nop     dword ptr [rax+rax+00h]
0x1801924e4  test    ebx, ebx
0x1801924e6  jz      short loc_180192515
0x1801924e8  test    edi, edi
0x1801924ea  jz      short loc_180192508
0x1801924ec  mov     rcx, [rsp+0C8h]; this
0x1801924f4  mov     r9d, edi; char *
0x1801924f7  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801924fe  mov     edx, 0CFh; void *
0x180192503  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192508  mov     r9d, ebx
0x18019250b  mov     edx, 0D0h
0x180192510  jmp     loc_180192387
0x180192515  test    edi, edi
0x180192517  jz      short loc_180192526
0x180192519  mov     r9d, edi
0x18019251c  mov     edx, 0D4h
0x180192521  jmp     loc_180192387
0x180192526  mov     ebx, [rsp+0C8h+Reply]
0x18019252a  test    ebx, ebx
0x18019252c  jns     short loc_18019254E
0x18019252e  mov     rcx, [rsp+0C8h]; this
0x180192536  mov     r9d, ebx; char *
0x180192539  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192540  mov     edx, 0D5h; void *
0x180192545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019254a  mov     eax, ebx
0x18019254c  jmp     short loc_180192589
0x18019254e  xor     eax, eax
0x180192550  jmp     short loc_180192589
0x180192552  mov     ebx, eax
0x180192554  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x180192559  call    cs:__imp_CloseHandle
0x180192560  nop     dword ptr [rax+rax+00h]
0x180192565  test    ebx, ebx
0x180192567  jz      short loc_180192587
0x180192569  mov     rcx, [rsp+0C8h]; this
0x180192571  mov     r9d, ebx; char *
0x180192574  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019257b  mov     edx, 96h; void *
0x180192580  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192585  jmp     short loc_180192589
0x180192587  xor     eax, eax
0x180192589  mov     rcx, [rsp+0C8h+var_28]
0x180192591  xor     rcx, rsp; StackCookie
0x180192594  call    __security_check_cookie
0x180192599  add     rsp, 0B0h
0x1801925a0  pop     rdi
0x1801925a1  pop     rsi
0x1801925a2  pop     rbx
0x1801925a3  retn
```
