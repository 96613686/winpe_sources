# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *),void *>(ulong,void (*)(_RPC_ASYNC_STATE *,void *),void * &&)

- ea: `0x180191e34`
- end: `0x1801920ab`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAX@ZPEAX@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAX@Z$$QEAPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180067240`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x180191330`
- `0x180191e34`
- `0x1801940b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191f07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191f8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191f07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180191f8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191ead`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180191ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191fd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192059`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180191fd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192059`
- `RPCRT4!RpcAsyncCancelCall` at `0x180191f56`
- `RPCRT4!RpcAsyncCancelCall` at `0x180191f56`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180191fc5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180191fc5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191e72`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180191e72`

## string_xrefs

- `0x180191e92`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191ecb`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191f71`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191fa2`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180191ff7`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192039`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192074`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *),void *>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 v7; // rdx
  const char *v9; // r9
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  const char *v13; // r9
  unsigned int v14; // edi
  unsigned int v15; // ebx
  unsigned int Reply[4]; // [rsp+20h] [rbp-98h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+30h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  memset_0(&pAsync, 0, sizeof(pAsync));
  v5 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v5 )
  {
    v6 = (const char *)v5;
    v7 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v9);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_InitiateShutdown(&pAsync, *a3);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v11 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v11 = 735;
    }
    else if ( LastError == 258 )
    {
      v11 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v11 = LastError;
    }
    v12 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v12 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v12,
        Reply[0]);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v13);
  }
  Reply[0] = 0;
  v14 = RpcAsyncCompleteCall(&pAsync, Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v11 )
  {
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v14,
        Reply[0]);
    v6 = (const char *)v11;
    v7 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  if ( v14 )
  {
    v6 = (const char *)v14;
    v7 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v6,
             Reply[0]);
  }
  v15 = Reply[0];
  if ( (Reply[0] & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)Reply[0],
    Reply[0]);
  return v15;
}

```

## disassembly

```asm
0x180191e34  mov     [rsp+arg_8], rbx
0x180191e39  push    rdi
0x180191e3a  sub     rsp, 0B0h
0x180191e41  mov     rax, cs:__security_cookie
0x180191e48  xor     rax, rsp
0x180191e4b  mov     [rsp+0B8h+var_18], rax
0x180191e53  mov     rbx, r8
0x180191e56  mov     edi, ecx
0x180191e58  xor     edx, edx; Val
0x180191e5a  lea     r8d, [rdx+70h]; Size
0x180191e5e  lea     rcx, [rsp+0B8h+pAsync]; void *
0x180191e63  call    memset_0
0x180191e68  mov     edx, 70h ; 'p'; Size
0x180191e6d  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191e72  call    cs:__imp_RpcAsyncInitializeHandle
0x180191e79  nop     dword ptr [rax+rax+00h]
0x180191e7e  test    eax, eax
0x180191e80  jz      short loc_180191EA3
0x180191e82  mov     r9d, eax; char *
0x180191e85  mov     edx, 84h; void *
0x180191e8a  mov     rcx, [rsp+0B8h]; this
0x180191e92  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191e99  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180191e9e  jmp     loc_180192089
0x180191ea3  xor     r9d, r9d; lpName
0x180191ea6  xor     r8d, r8d; bInitialState
0x180191ea9  xor     edx, edx; bManualReset
0x180191eab  xor     ecx, ecx; lpEventAttributes
0x180191ead  call    cs:__imp_CreateEventW
0x180191eb4  nop     dword ptr [rax+rax+00h]
0x180191eb9  mov     qword ptr [rsp+0B8h+pAsync.u], rax
0x180191ebe  test    rax, rax
0x180191ec1  jnz     short loc_180191EE1
0x180191ec3  mov     rcx, [rsp+0B8h]; this
0x180191ecb  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191ed2  mov     edx, 8Ah; void *
0x180191ed7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180191edc  jmp     loc_180192089
0x180191ee1  mov     [rsp+0B8h+pAsync.UserInfo], 0
0x180191eea  mov     [rsp+0B8h+pAsync.NotificationType], 1
0x180191ef2  mov     rdx, [rbx]
0x180191ef5  lea     rcx, [rsp+0B8h+pAsync]
0x180191efa  call    CmaRpcClt_InitiateShutdown
0x180191eff  nop
0x180191f00  mov     edx, edi; dwMilliseconds
0x180191f02  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hHandle
0x180191f07  call    cs:__imp_WaitForSingleObject
0x180191f0e  nop     dword ptr [rax+rax+00h]
0x180191f13  xor     ebx, ebx
0x180191f15  test    eax, eax
0x180191f17  jz      loc_180191FB3
0x180191f1d  cmp     eax, 80h
0x180191f22  jz      short loc_180191F47
0x180191f24  cmp     eax, 102h
0x180191f29  jz      short loc_180191F40
0x180191f2b  cmp     eax, 0FFFFFFFFh
0x180191f2e  jnz     short loc_180191F3C
0x180191f30  call    cs:__imp_GetLastError
0x180191f37  nop     dword ptr [rax+rax+00h]
0x180191f3c  mov     ebx, eax
0x180191f3e  jmp     short loc_180191F4C
0x180191f40  mov     ebx, 5B4h
0x180191f45  jmp     short loc_180191F4C
0x180191f47  mov     ebx, 2DFh
0x180191f4c  mov     edx, 1; fAbort
0x180191f51  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191f56  call    cs:__imp_RpcAsyncCancelCall
0x180191f5d  nop     dword ptr [rax+rax+00h]
0x180191f62  test    eax, eax
0x180191f64  jz      short loc_180191F82
0x180191f66  mov     rcx, [rsp+0B8h]; this
0x180191f6e  mov     r9d, eax; char *
0x180191f71  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191f78  mov     edx, 0BEh; void *
0x180191f7d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180191f82  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180191f85  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hHandle
0x180191f8a  call    cs:__imp_WaitForSingleObject
0x180191f91  nop     dword ptr [rax+rax+00h]
0x180191f96  test    eax, eax
0x180191f98  jz      short loc_180191FB3
0x180191f9a  mov     rcx, [rsp+0B8h]; this
0x180191fa2  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191fa9  mov     edx, 0BFh; void *
0x180191fae  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180191fb3  mov     [rsp+0B8h+Reply], 0; int
0x180191fbb  lea     rdx, [rsp+0B8h+Reply]; Reply
0x180191fc0  lea     rcx, [rsp+0B8h+pAsync]; pAsync
0x180191fc5  call    cs:__imp_RpcAsyncCompleteCall
0x180191fcc  nop     dword ptr [rax+rax+00h]
0x180191fd1  mov     edi, eax
0x180191fd3  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hObject
0x180191fd8  call    cs:__imp_CloseHandle
0x180191fdf  nop     dword ptr [rax+rax+00h]
0x180191fe4  test    ebx, ebx
0x180191fe6  jz      short loc_180192015
0x180191fe8  test    edi, edi
0x180191fea  jz      short loc_180192008
0x180191fec  mov     rcx, [rsp+0B8h]; this
0x180191ff4  mov     r9d, edi; char *
0x180191ff7  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180191ffe  mov     edx, 0CFh; void *
0x180192003  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192008  mov     r9d, ebx
0x18019200b  mov     edx, 0D0h
0x180192010  jmp     loc_180191E8A
0x180192015  test    edi, edi
0x180192017  jz      short loc_180192026
0x180192019  mov     r9d, edi
0x18019201c  mov     edx, 0D4h
0x180192021  jmp     loc_180191E8A
0x180192026  mov     ebx, [rsp+0B8h+Reply]
0x18019202a  test    ebx, ebx
0x18019202c  jns     short loc_18019204E
0x18019202e  mov     rcx, [rsp+0B8h]; this
0x180192036  mov     r9d, ebx; char *
0x180192039  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192040  mov     edx, 0D5h; void *
0x180192045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019204a  mov     eax, ebx
0x18019204c  jmp     short loc_180192089
0x18019204e  xor     eax, eax
0x180192050  jmp     short loc_180192089
0x180192052  mov     ebx, eax
0x180192054  mov     rcx, qword ptr [rsp+0B8h+pAsync.u]; hObject
0x180192059  call    cs:__imp_CloseHandle
0x180192060  nop     dword ptr [rax+rax+00h]
0x180192065  test    ebx, ebx
0x180192067  jz      short loc_180192087
0x180192069  mov     rcx, [rsp+0B8h]; this
0x180192071  mov     r9d, ebx; char *
0x180192074  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019207b  mov     edx, 96h; void *
0x180192080  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192085  jmp     short loc_180192089
0x180192087  xor     eax, eax
0x180192089  mov     rcx, [rsp+0B8h+var_18]
0x180192091  xor     rcx, rsp; StackCookie
0x180192094  call    __security_check_cookie
0x180192099  mov     rbx, [rsp+0B8h+arg_8]
0x1801920a1  add     rsp, 0B0h
0x1801920a8  pop     rdi
0x1801920a9  retn
```
