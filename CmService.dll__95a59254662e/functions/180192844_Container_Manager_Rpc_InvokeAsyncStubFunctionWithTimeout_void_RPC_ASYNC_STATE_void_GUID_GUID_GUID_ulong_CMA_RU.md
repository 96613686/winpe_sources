# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,ulong,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void *,_GUID * &,_GUID * &,_GUID * &,ulong &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,ulong,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void * &&,_GUID * &,_GUID * &,_GUID * &,ulong &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &)

- ea: `0x180192844`
- end: `0x180192b4d`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_GUID@@22KPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@H@ZPEAXAEAPEAU2@AEAPEAU2@AEAPEAU2@AEAKAEAPEAU3@AEAPEAU4@AEA_N@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_GUID@@22KPEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@H@Z$$QEAPEAXAEAPEAU4@77AEAKAEAPEAU5@AEAPEAU6@AEA_N@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801935bc`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x180191330`
- `0x180192844`
- `0x1801940e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019299e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192a24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019299e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180192a24`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192900`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180192900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801929c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801929c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180192af9`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801929ed`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801929ed`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192a5f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192a5f`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801928c5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801928c5`

## string_xrefs

- `0x1801928e5`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192921`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192a08`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192a3c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192a94`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192ad6`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192b14`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_GUID *,_GUID *,_GUID *,unsigned long,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,int),void *,_GUID * &,_GUID * &,_GUID * &,unsigned long &,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION * &,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &,bool &>(
        DWORD dwMilliseconds,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        __int64 *a8,
        __int64 *a9,
        unsigned __int8 *a10)
{
  unsigned int v13; // eax
  const char *v14; // r9
  __int64 v15; // rdx
  const char *v17; // r9
  DWORD LastError; // eax
  unsigned int v19; // ebx
  unsigned int v20; // eax
  const char *v21; // r9
  unsigned int v22; // edi
  int v23; // ebx
  unsigned int v24; // [rsp+20h] [rbp-108h]
  int Reply; // [rsp+50h] [rbp-D8h] BYREF
  unsigned __int8 *v26; // [rsp+58h] [rbp-D0h]
  __int64 *v27; // [rsp+60h] [rbp-C8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v27 = a9;
  v26 = a10;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v13 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v13 )
  {
    v14 = (const char *)v13;
    v15 = 132;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
  if ( !pAsync.u.APC.NotificationRoutine )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v17);
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  CmaRpcClt_NotifyCreating((unsigned int)&pAsync, *a3, *a4, *a5, *a6, *a7, *a8, *v27, *v26);
  LastError = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, dwMilliseconds);
  v19 = 0;
  if ( LastError )
  {
    if ( LastError == 128 )
    {
      v19 = 735;
    }
    else if ( LastError == 258 )
    {
      v19 = 1460;
    }
    else
    {
      if ( LastError == -1 )
        LastError = GetLastError();
      v19 = LastError;
    }
    v20 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v20 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v20,
        v24);
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        v21);
  }
  Reply = 0;
  v22 = RpcAsyncCompleteCall(&pAsync, &Reply);
  CloseHandle(pAsync.u.APC.NotificationRoutine);
  if ( v19 )
  {
    if ( v22 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
        (const char *)v22,
        v24);
    v14 = (const char *)v19;
    v15 = 208;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  if ( v22 )
  {
    v14 = (const char *)v22;
    v15 = 212;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
             v14,
             v24);
  }
  v23 = Reply;
  if ( Reply >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD5,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\RpcUtilities.h",
    (const char *)(unsigned int)Reply,
    v24);
  return v23;
}

```

## disassembly

```asm
0x180192844  push    rbx
0x180192846  push    rsi
0x180192847  push    rdi
0x180192848  push    r12
0x18019284a  push    r13
0x18019284c  push    r14
0x18019284e  push    r15
0x180192850  sub     rsp, 0F0h
0x180192857  mov     rax, cs:__security_cookie
0x18019285e  xor     rax, rsp
0x180192861  mov     [rsp+128h+var_48], rax
0x180192869  mov     rsi, r9
0x18019286c  mov     rdi, r8
0x18019286f  mov     ebx, ecx
0x180192871  mov     r14, [rsp+128h+arg_20]
0x180192879  mov     r15, [rsp+128h+arg_28]
0x180192881  mov     r12, [rsp+128h+arg_30]
0x180192889  mov     r13, [rsp+128h+arg_38]
0x180192891  mov     rax, [rsp+128h+arg_40]
0x180192899  mov     [rsp+128h+var_C8], rax
0x18019289e  mov     rax, [rsp+128h+arg_48]
0x1801928a6  mov     [rsp+128h+var_D0], rax
0x1801928ab  xor     edx, edx; Val
0x1801928ad  lea     r8d, [rdx+70h]; Size
0x1801928b1  lea     rcx, [rsp+128h+pAsync]; void *
0x1801928b6  call    memset_0
0x1801928bb  mov     edx, 70h ; 'p'; Size
0x1801928c0  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1801928c5  call    cs:__imp_RpcAsyncInitializeHandle
0x1801928cc  nop     dword ptr [rax+rax+00h]
0x1801928d1  test    eax, eax
0x1801928d3  jz      short loc_1801928F6
0x1801928d5  mov     r9d, eax; char *
0x1801928d8  mov     edx, 84h; void *
0x1801928dd  mov     rcx, [rsp+128h]; this
0x1801928e5  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801928ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801928f1  jmp     loc_180192B29
0x1801928f6  xor     r9d, r9d; lpName
0x1801928f9  xor     r8d, r8d; bInitialState
0x1801928fc  xor     edx, edx; bManualReset
0x1801928fe  xor     ecx, ecx; lpEventAttributes
0x180192900  call    cs:__imp_CreateEventW
0x180192907  nop     dword ptr [rax+rax+00h]
0x18019290c  mov     qword ptr [rsp+128h+pAsync.u], rax
0x180192914  test    rax, rax
0x180192917  jnz     short loc_180192937
0x180192919  mov     rcx, [rsp+128h]; this
0x180192921  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192928  mov     edx, 8Ah; void *
0x18019292d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180192932  jmp     loc_180192B29
0x180192937  mov     [rsp+128h+pAsync.UserInfo], 0
0x180192943  mov     [rsp+128h+pAsync.NotificationType], 1
0x18019294e  mov     rax, [rsp+128h+var_D0]
0x180192953  movzx   eax, byte ptr [rax]
0x180192956  mov     [rsp+128h+var_E8], eax
0x18019295a  mov     rax, [rsp+128h+var_C8]
0x18019295f  mov     rax, [rax]
0x180192962  mov     [rsp+128h+var_F0], rax
0x180192967  mov     rax, [r13+0]
0x18019296b  mov     [rsp+128h+var_F8], rax
0x180192970  mov     eax, [r12]
0x180192974  mov     [rsp+128h+var_100], eax
0x180192978  mov     rax, [r15]
0x18019297b  mov     qword ptr [rsp+128h+var_108], rax; int
0x180192980  mov     r9, [r14]
0x180192983  mov     r8, [rsi]
0x180192986  mov     rdx, [rdi]
0x180192989  lea     rcx, [rsp+128h+pAsync]
0x18019298e  call    CmaRpcClt_NotifyCreating
0x180192993  nop
0x180192994  mov     edx, ebx; dwMilliseconds
0x180192996  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hHandle
0x18019299e  call    cs:__imp_WaitForSingleObject
0x1801929a5  nop     dword ptr [rax+rax+00h]
0x1801929aa  xor     ebx, ebx
0x1801929ac  test    eax, eax
0x1801929ae  jz      loc_180192A4D
0x1801929b4  cmp     eax, 80h
0x1801929b9  jz      short loc_1801929DE
0x1801929bb  cmp     eax, 102h
0x1801929c0  jz      short loc_1801929D7
0x1801929c2  cmp     eax, 0FFFFFFFFh
0x1801929c5  jnz     short loc_1801929D3
0x1801929c7  call    cs:__imp_GetLastError
0x1801929ce  nop     dword ptr [rax+rax+00h]
0x1801929d3  mov     ebx, eax
0x1801929d5  jmp     short loc_1801929E3
0x1801929d7  mov     ebx, 5B4h
0x1801929dc  jmp     short loc_1801929E3
0x1801929de  mov     ebx, 2DFh
0x1801929e3  mov     edx, 1; fAbort
0x1801929e8  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1801929ed  call    cs:__imp_RpcAsyncCancelCall
0x1801929f4  nop     dword ptr [rax+rax+00h]
0x1801929f9  test    eax, eax
0x1801929fb  jz      short loc_180192A19
0x1801929fd  mov     rcx, [rsp+128h]; this
0x180192a05  mov     r9d, eax; char *
0x180192a08  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192a0f  mov     edx, 0BEh; void *
0x180192a14  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192a19  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192a1c  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hHandle
0x180192a24  call    cs:__imp_WaitForSingleObject
0x180192a2b  nop     dword ptr [rax+rax+00h]
0x180192a30  test    eax, eax
0x180192a32  jz      short loc_180192A4D
0x180192a34  mov     rcx, [rsp+128h]; this
0x180192a3c  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192a43  mov     edx, 0BFh; void *
0x180192a48  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180192a4d  mov     [rsp+128h+Reply], 0
0x180192a55  lea     rdx, [rsp+128h+Reply]; Reply
0x180192a5a  lea     rcx, [rsp+128h+pAsync]; pAsync
0x180192a5f  call    cs:__imp_RpcAsyncCompleteCall
0x180192a66  nop     dword ptr [rax+rax+00h]
0x180192a6b  mov     edi, eax
0x180192a6d  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180192a75  call    cs:__imp_CloseHandle
0x180192a7c  nop     dword ptr [rax+rax+00h]
0x180192a81  test    ebx, ebx
0x180192a83  jz      short loc_180192AB2
0x180192a85  test    edi, edi
0x180192a87  jz      short loc_180192AA5
0x180192a89  mov     rcx, [rsp+128h]; this
0x180192a91  mov     r9d, edi; char *
0x180192a94  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192a9b  mov     edx, 0CFh; void *
0x180192aa0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192aa5  mov     r9d, ebx
0x180192aa8  mov     edx, 0D0h
0x180192aad  jmp     loc_1801928DD
0x180192ab2  test    edi, edi
0x180192ab4  jz      short loc_180192AC3
0x180192ab6  mov     r9d, edi
0x180192ab9  mov     edx, 0D4h
0x180192abe  jmp     loc_1801928DD
0x180192ac3  mov     ebx, [rsp+128h+Reply]
0x180192ac7  test    ebx, ebx
0x180192ac9  jns     short loc_180192AEB
0x180192acb  mov     rcx, [rsp+128h]; this
0x180192ad3  mov     r9d, ebx; char *
0x180192ad6  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192add  mov     edx, 0D5h; void *
0x180192ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180192ae7  mov     eax, ebx
0x180192ae9  jmp     short loc_180192B29
0x180192aeb  xor     eax, eax
0x180192aed  jmp     short loc_180192B29
0x180192aef  mov     ebx, eax
0x180192af1  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hObject
0x180192af9  call    cs:__imp_CloseHandle
0x180192b00  nop     dword ptr [rax+rax+00h]
0x180192b05  test    ebx, ebx
0x180192b07  jz      short loc_180192B27
0x180192b09  mov     rcx, [rsp+128h]; this
0x180192b11  mov     r9d, ebx; char *
0x180192b14  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192b1b  mov     edx, 96h; void *
0x180192b20  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192b25  jmp     short loc_180192B29
0x180192b27  xor     eax, eax
0x180192b29  mov     rcx, [rsp+128h+var_48]
0x180192b31  xor     rcx, rsp; StackCookie
0x180192b34  call    __security_check_cookie
0x180192b39  add     rsp, 0F0h
0x180192b40  pop     r15
0x180192b42  pop     r14
0x180192b44  pop     r13
0x180192b46  pop     r12
0x180192b48  pop     rdi
0x180192b49  pop     rsi
0x180192b4a  pop     rbx
0x180192b4b  retn
```
