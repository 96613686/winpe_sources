# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void * &&,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &)

- ea: `0x1801925ac`
- end: `0x18019283c`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@ZPEAXAEAPEAU2@AEAPEAU3@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z$$QEAPEAXAEAPEAU4@AEAPEAU5@@Z`
- size: `656`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801937a0`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x180191330`
- `0x1801925ac`
- `0x18019415c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192695`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192718`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192695`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192718`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192634`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801926be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801926be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192766`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801927e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192766`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801927e7`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801926e4`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801926e4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192753`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192753`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801925f9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801925f9`

## string_xrefs

- `0x180192619`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192652`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801926ff`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192730`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192785`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801927c7`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192802`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

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
0x1801925ac  mov     [rsp+arg_8], rbx
0x1801925b1  push    rsi
0x1801925b2  push    rdi
0x1801925b3  push    r14
0x1801925b5  sub     rsp, 0B0h
0x1801925bc  mov     rax, cs:__security_cookie
0x1801925c3  xor     rax, rsp
0x1801925c6  mov     [rsp+0C8h+var_28], rax
0x1801925ce  mov     rdi, r9
0x1801925d1  mov     rbx, r8
0x1801925d4  mov     r14d, ecx
0x1801925d7  mov     rsi, [rsp+0C8h+arg_20]
0x1801925df  xor     edx, edx; Val
0x1801925e1  lea     r8d, [rdx+70h]; Size
0x1801925e5  lea     rcx, [rsp+0C8h+pAsync]; void *
0x1801925ea  call    memset_0
0x1801925ef  mov     edx, 70h ; 'p'; Size
0x1801925f4  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801925f9  call    cs:__imp_RpcAsyncInitializeHandle
0x180192600  nop     dword ptr [rax+rax+00h]
0x180192605  test    eax, eax
0x180192607  jz      short loc_18019262A
0x180192609  mov     r9d, eax; char *
0x18019260c  mov     edx, 84h; void *
0x180192611  mov     rcx, [rsp+0C8h]; this
0x180192619  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192620  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192625  jmp     loc_180192817
0x18019262a  xor     r9d, r9d; lpName
0x18019262d  xor     r8d, r8d; bInitialState
0x180192630  xor     edx, edx; bManualReset
0x180192632  xor     ecx, ecx; lpEventAttributes
0x180192634  call    cs:__imp_CreateEventW
0x18019263b  nop     dword ptr [rax+rax+00h]
0x180192640  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x180192645  test    rax, rax
0x180192648  jnz     short loc_180192668
0x18019264a  mov     rcx, [rsp+0C8h]; this
0x180192652  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192659  mov     edx, 8Ah; void *
0x18019265e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180192663  jmp     loc_180192817
0x180192668  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x180192671  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x180192679  mov     r9, [rsi]
0x18019267c  mov     r8, [rdi]
0x18019267f  mov     rdx, [rbx]
0x180192682  lea     rcx, [rsp+0C8h+pAsync]
0x180192687  call    CmaRpcClt_NotifyResuming
0x18019268c  nop
0x18019268d  mov     edx, r14d; dwMilliseconds
0x180192690  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x180192695  call    cs:__imp_WaitForSingleObject
0x18019269c  nop     dword ptr [rax+rax+00h]
0x1801926a1  xor     ebx, ebx
0x1801926a3  test    eax, eax
0x1801926a5  jz      loc_180192741
0x1801926ab  cmp     eax, 80h
0x1801926b0  jz      short loc_1801926D5
0x1801926b2  cmp     eax, 102h
0x1801926b7  jz      short loc_1801926CE
0x1801926b9  cmp     eax, 0FFFFFFFFh
0x1801926bc  jnz     short loc_1801926CA
0x1801926be  call    cs:__imp_GetLastError
0x1801926c5  nop     dword ptr [rax+rax+00h]
0x1801926ca  mov     ebx, eax
0x1801926cc  jmp     short loc_1801926DA
0x1801926ce  mov     ebx, 5B4h
0x1801926d3  jmp     short loc_1801926DA
0x1801926d5  mov     ebx, 2DFh
0x1801926da  mov     edx, 1; fAbort
0x1801926df  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801926e4  call    cs:__imp_RpcAsyncCancelCall
0x1801926eb  nop     dword ptr [rax+rax+00h]
0x1801926f0  test    eax, eax
0x1801926f2  jz      short loc_180192710
0x1801926f4  mov     rcx, [rsp+0C8h]; this
0x1801926fc  mov     r9d, eax; char *
0x1801926ff  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192706  mov     edx, 0BEh; void *
0x18019270b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192710  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192713  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x180192718  call    cs:__imp_WaitForSingleObject
0x18019271f  nop     dword ptr [rax+rax+00h]
0x180192724  test    eax, eax
0x180192726  jz      short loc_180192741
0x180192728  mov     rcx, [rsp+0C8h]; this
0x180192730  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192737  mov     edx, 0BFh; void *
0x18019273c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180192741  mov     [rsp+0C8h+Reply], 0; int
0x180192749  lea     rdx, [rsp+0C8h+Reply]; Reply
0x18019274e  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192753  call    cs:__imp_RpcAsyncCompleteCall
0x18019275a  nop     dword ptr [rax+rax+00h]
0x18019275f  mov     edi, eax
0x180192761  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x180192766  call    cs:__imp_CloseHandle
0x18019276d  nop     dword ptr [rax+rax+00h]
0x180192772  test    ebx, ebx
0x180192774  jz      short loc_1801927A3
0x180192776  test    edi, edi
0x180192778  jz      short loc_180192796
0x18019277a  mov     rcx, [rsp+0C8h]; this
0x180192782  mov     r9d, edi; char *
0x180192785  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019278c  mov     edx, 0CFh; void *
0x180192791  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192796  mov     r9d, ebx
0x180192799  mov     edx, 0D0h
0x18019279e  jmp     loc_180192611
0x1801927a3  test    edi, edi
0x1801927a5  jz      short loc_1801927B4
0x1801927a7  mov     r9d, edi
0x1801927aa  mov     edx, 0D4h
0x1801927af  jmp     loc_180192611
0x1801927b4  mov     ebx, [rsp+0C8h+Reply]
0x1801927b8  test    ebx, ebx
0x1801927ba  jns     short loc_1801927DC
0x1801927bc  mov     rcx, [rsp+0C8h]; this
0x1801927c4  mov     r9d, ebx; char *
0x1801927c7  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801927ce  mov     edx, 0D5h; void *
0x1801927d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801927d8  mov     eax, ebx
0x1801927da  jmp     short loc_180192817
0x1801927dc  xor     eax, eax
0x1801927de  jmp     short loc_180192817
0x1801927e0  mov     ebx, eax
0x1801927e2  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801927e7  call    cs:__imp_CloseHandle
0x1801927ee  nop     dword ptr [rax+rax+00h]
0x1801927f3  test    ebx, ebx
0x1801927f5  jz      short loc_180192815
0x1801927f7  mov     rcx, [rsp+0C8h]; this
0x1801927ff  mov     r9d, ebx; char *
0x180192802  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192809  mov     edx, 96h; void *
0x18019280e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192813  jmp     short loc_180192817
0x180192815  xor     eax, eax
0x180192817  mov     rcx, [rsp+0C8h+var_28]
0x18019281f  xor     rcx, rsp; StackCookie
0x180192822  call    __security_check_cookie
0x180192827  mov     rbx, [rsp+0C8h+arg_8]
0x18019282f  add     rsp, 0B0h
0x180192836  pop     r14
0x180192838  pop     rdi
0x180192839  pop     rsi
0x18019283a  retn
```
