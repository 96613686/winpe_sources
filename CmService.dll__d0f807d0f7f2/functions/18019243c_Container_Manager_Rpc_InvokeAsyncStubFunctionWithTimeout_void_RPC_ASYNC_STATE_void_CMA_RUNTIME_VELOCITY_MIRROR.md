# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void * &&,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &)

- ea: `0x18019243c`
- end: `0x1801926cc`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@ZPEAXAEAPEAU2@AEAPEAU3@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z$$QEAPEAXAEAPEAU4@AEAPEAU5@@Z`
- size: `656`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180193630`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x1801911c0`
- `0x18019243c`
- `0x180193fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801925a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801925a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801924c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801924c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019254e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019254e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801925f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801925f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192677`
- `RPCRT4!RpcAsyncCancelCall` at `0x180192574`
- `RPCRT4!RpcAsyncCancelCall` at `0x180192574`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801925e3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1801925e3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180192489`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180192489`

## string_xrefs

- `0x1801924a9`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801924e2`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18019258f`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801925c0`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192615`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192657`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192692`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  unsigned int v8; // eax
  const char *v9; // r9
  __int64 v10; // rdx
  const char *v12; // r9
  DWORD LastError; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  const char *v16; // r9
  unsigned int v17; // edi
  unsigned int v18; // ebx
  unsigned int Reply[4]; // [rsp+20h] [rbp-A8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+30h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  memset_0(&pAsync, 0, sizeof(pAsync));
  v8 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v8 )
  {
    v9 = (const char *)v8;
    v10 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v9,
             Reply[0]);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v12);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_NotifyResuming(&pAsync, *a3, *a4, *a5);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v14 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v14 = 735;
    }
    else if ( LastError == 258 )
    {
      v14 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v14 = LastError;
    }
    v15 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v15 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v15,
        Reply[0]);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v16);
  }
  Reply[0] = 0;
  v17 = RpcAsyncCompleteCall(&pAsync, Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v14 )
  {
    if ( v17 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v17,
        Reply[0]);
    v9 = (const char *)v14;
    v10 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v9,
             Reply[0]);
  }
  if ( v17 )
  {
    v9 = (const char *)v17;
    v10 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v9,
             Reply[0]);
  }
  v18 = Reply[0];
  if ( (Reply[0] & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)Reply[0],
    Reply[0]);
  return v18;
}

```

## disassembly

```asm
0x18019243c  mov     [rsp+arg_8], rbx
0x180192441  push    rsi
0x180192442  push    rdi
0x180192443  push    r14
0x180192445  sub     rsp, 0B0h
0x18019244c  mov     rax, cs:__security_cookie
0x180192453  xor     rax, rsp
0x180192456  mov     [rsp+0C8h+var_28], rax
0x18019245e  mov     rdi, r9
0x180192461  mov     rbx, r8
0x180192464  mov     r14d, ecx
0x180192467  mov     rsi, [rsp+0C8h+arg_20]
0x18019246f  xor     edx, edx; Val
0x180192471  lea     r8d, [rdx+70h]; Size
0x180192475  lea     rcx, [rsp+0C8h+pAsync]; void *
0x18019247a  call    memset_0
0x18019247f  mov     edx, 70h ; 'p'; Size
0x180192484  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192489  call    cs:__imp_RpcAsyncInitializeHandle
0x180192490  nop     dword ptr [rax+rax+00h]
0x180192495  test    eax, eax
0x180192497  jz      short loc_1801924BA
0x180192499  mov     r9d, eax; char *
0x18019249c  mov     edx, 84h; void *
0x1801924a1  mov     rcx, [rsp+0C8h]; this
0x1801924a9  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801924b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801924b5  jmp     loc_1801926A7
0x1801924ba  xor     r9d, r9d; lpName
0x1801924bd  xor     r8d, r8d; bInitialState
0x1801924c0  xor     edx, edx; bManualReset
0x1801924c2  xor     ecx, ecx; lpEventAttributes
0x1801924c4  call    cs:__imp_CreateEventW
0x1801924cb  nop     dword ptr [rax+rax+00h]
0x1801924d0  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x1801924d5  test    rax, rax
0x1801924d8  jnz     short loc_1801924F8
0x1801924da  mov     rcx, [rsp+0C8h]; this
0x1801924e2  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801924e9  mov     edx, 8Ah; void *
0x1801924ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801924f3  jmp     loc_1801926A7
0x1801924f8  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x180192501  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x180192509  mov     r9, [rsi]
0x18019250c  mov     r8, [rdi]
0x18019250f  mov     rdx, [rbx]
0x180192512  lea     rcx, [rsp+0C8h+pAsync]
0x180192517  call    CmaRpcClt_NotifyResuming
0x18019251c  nop
0x18019251d  mov     edx, r14d; dwMilliseconds
0x180192520  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x180192525  call    cs:__imp_WaitForSingleObject
0x18019252c  nop     dword ptr [rax+rax+00h]
0x180192531  xor     ebx, ebx
0x180192533  test    eax, eax
0x180192535  jz      loc_1801925D1
0x18019253b  cmp     eax, 80h
0x180192540  jz      short loc_180192565
0x180192542  cmp     eax, 102h
0x180192547  jz      short loc_18019255E
0x180192549  cmp     eax, 0FFFFFFFFh
0x18019254c  jnz     short loc_18019255A
0x18019254e  call    cs:__imp_GetLastError
0x180192555  nop     dword ptr [rax+rax+00h]
0x18019255a  mov     ebx, eax
0x18019255c  jmp     short loc_18019256A
0x18019255e  mov     ebx, 5B4h
0x180192563  jmp     short loc_18019256A
0x180192565  mov     ebx, 2DFh
0x18019256a  mov     edx, 1; fAbort
0x18019256f  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192574  call    cs:__imp_RpcAsyncCancelCall
0x18019257b  nop     dword ptr [rax+rax+00h]
0x180192580  test    eax, eax
0x180192582  jz      short loc_1801925A0
0x180192584  mov     rcx, [rsp+0C8h]; this
0x18019258c  mov     r9d, eax; char *
0x18019258f  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192596  mov     edx, 0BEh; void *
0x18019259b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1801925a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801925a3  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x1801925a8  call    cs:__imp_WaitForSingleObject
0x1801925af  nop     dword ptr [rax+rax+00h]
0x1801925b4  test    eax, eax
0x1801925b6  jz      short loc_1801925D1
0x1801925b8  mov     rcx, [rsp+0C8h]; this
0x1801925c0  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801925c7  mov     edx, 0BFh; void *
0x1801925cc  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801925d1  mov     [rsp+0C8h+Reply], 0; int
0x1801925d9  lea     rdx, [rsp+0C8h+Reply]; Reply
0x1801925de  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801925e3  call    cs:__imp_RpcAsyncCompleteCall
0x1801925ea  nop     dword ptr [rax+rax+00h]
0x1801925ef  mov     edi, eax
0x1801925f1  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801925f6  call    cs:__imp_CloseHandle
0x1801925fd  nop     dword ptr [rax+rax+00h]
0x180192602  test    ebx, ebx
0x180192604  jz      short loc_180192633
0x180192606  test    edi, edi
0x180192608  jz      short loc_180192626
0x18019260a  mov     rcx, [rsp+0C8h]; this
0x180192612  mov     r9d, edi; char *
0x180192615  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019261c  mov     edx, 0CFh; void *
0x180192621  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192626  mov     r9d, ebx
0x180192629  mov     edx, 0D0h
0x18019262e  jmp     loc_1801924A1
0x180192633  test    edi, edi
0x180192635  jz      short loc_180192644
0x180192637  mov     r9d, edi
0x18019263a  mov     edx, 0D4h
0x18019263f  jmp     loc_1801924A1
0x180192644  mov     ebx, [rsp+0C8h+Reply]
0x180192648  test    ebx, ebx
0x18019264a  jns     short loc_18019266C
0x18019264c  mov     rcx, [rsp+0C8h]; this
0x180192654  mov     r9d, ebx; char *
0x180192657  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019265e  mov     edx, 0D5h; void *
0x180192663  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192668  mov     eax, ebx
0x18019266a  jmp     short loc_1801926A7
0x18019266c  xor     eax, eax
0x18019266e  jmp     short loc_1801926A7
0x180192670  mov     ebx, eax
0x180192672  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x180192677  call    cs:__imp_CloseHandle
0x18019267e  nop     dword ptr [rax+rax+00h]
0x180192683  test    ebx, ebx
0x180192685  jz      short loc_1801926A5
0x180192687  mov     rcx, [rsp+0C8h]; this
0x18019268f  mov     r9d, ebx; char *
0x180192692  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192699  mov     edx, 96h; void *
0x18019269e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801926a3  jmp     short loc_1801926A7
0x1801926a5  xor     eax, eax
0x1801926a7  mov     rcx, [rsp+0C8h+var_28]
0x1801926af  xor     rcx, rsp; StackCookie
0x1801926b2  call    __security_check_cookie
0x1801926b7  mov     rbx, [rsp+0C8h+arg_8]
0x1801926bf  add     rsp, 0B0h
0x1801926c6  pop     r14
0x1801926c8  pop     rdi
0x1801926c9  pop     rsi
0x1801926ca  retn
```
