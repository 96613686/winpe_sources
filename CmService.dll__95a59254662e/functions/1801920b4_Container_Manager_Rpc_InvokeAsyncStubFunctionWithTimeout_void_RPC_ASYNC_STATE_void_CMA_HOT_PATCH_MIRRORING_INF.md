# Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(ulong,void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void * &&,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &)

- ea: `0x1801920b4`
- end: `0x180192329`
- name: `??$InvokeAsyncStubFunctionWithTimeout@P6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@ZPEAXAEAPEAU2@@Rpc@Manager@Container@@YAJKP6AXPEAU_RPC_ASYNC_STATE@@PEAXPEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z$$QEAPEAXAEAPEAU4@@Z`
- size: `629`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180193f30`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1800262c4`
- `0x180191330`
- `0x1801920b4`
- `0x180194244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019218b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019220e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019218b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18019220e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019212e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18019212e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801921b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801921b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019225c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801922dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019225c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801922dd`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801921da`
- `RPCRT4!RpcAsyncCancelCall` at `0x1801921da`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192249`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180192249`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801920f3`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1801920f3`

## string_xrefs

- `0x180192113`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18019214c`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801921f5`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x180192226`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x18019227b`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801922bd`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`
- `0x1801922f8`: `onecore\base\gendrv\silos\clem\rpc\common\RpcUtilities.h`

## pseudocode

```c
int __fastcall Container::Manager::Rpc::InvokeAsyncStubFunctionWithTimeout<void (*)(_RPC_ASYNC_STATE *,void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *),void *,_CMA_HOT_PATCH_MIRRORING_INFORMATION * &>(
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
  CmaRpcClt_UpdateHotPatches(&pAsync, *a3, *a4);
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
0x1801920b4  push    rbx
0x1801920b6  push    rsi
0x1801920b7  push    rdi
0x1801920b8  sub     rsp, 0B0h
0x1801920bf  mov     rax, cs:__security_cookie
0x1801920c6  xor     rax, rsp
0x1801920c9  mov     [rsp+0C8h+var_28], rax
0x1801920d1  mov     rdi, r9
0x1801920d4  mov     rbx, r8
0x1801920d7  mov     esi, ecx
0x1801920d9  xor     edx, edx; Val
0x1801920db  lea     r8d, [rdx+70h]; Size
0x1801920df  lea     rcx, [rsp+0C8h+pAsync]; void *
0x1801920e4  call    memset_0
0x1801920e9  mov     edx, 70h ; 'p'; Size
0x1801920ee  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801920f3  call    cs:__imp_RpcAsyncInitializeHandle
0x1801920fa  nop     dword ptr [rax+rax+00h]
0x1801920ff  test    eax, eax
0x180192101  jz      short loc_180192124
0x180192103  mov     r9d, eax; char *
0x180192106  mov     edx, 84h; void *
0x18019210b  mov     rcx, [rsp+0C8h]; this
0x180192113  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019211a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18019211f  jmp     loc_18019230D
0x180192124  xor     r9d, r9d; lpName
0x180192127  xor     r8d, r8d; bInitialState
0x18019212a  xor     edx, edx; bManualReset
0x18019212c  xor     ecx, ecx; lpEventAttributes
0x18019212e  call    cs:__imp_CreateEventW
0x180192135  nop     dword ptr [rax+rax+00h]
0x18019213a  mov     qword ptr [rsp+0C8h+pAsync.u], rax
0x18019213f  test    rax, rax
0x180192142  jnz     short loc_180192162
0x180192144  mov     rcx, [rsp+0C8h]; this
0x18019214c  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192153  mov     edx, 8Ah; void *
0x180192158  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18019215d  jmp     loc_18019230D
0x180192162  mov     [rsp+0C8h+pAsync.UserInfo], 0
0x18019216b  mov     [rsp+0C8h+pAsync.NotificationType], 1
0x180192173  mov     r8, [rdi]
0x180192176  mov     rdx, [rbx]
0x180192179  lea     rcx, [rsp+0C8h+pAsync]
0x18019217e  call    CmaRpcClt_UpdateHotPatches
0x180192183  nop
0x180192184  mov     edx, esi; dwMilliseconds
0x180192186  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019218b  call    cs:__imp_WaitForSingleObject
0x180192192  nop     dword ptr [rax+rax+00h]
0x180192197  xor     ebx, ebx
0x180192199  test    eax, eax
0x18019219b  jz      loc_180192237
0x1801921a1  cmp     eax, 80h
0x1801921a6  jz      short loc_1801921CB
0x1801921a8  cmp     eax, 102h
0x1801921ad  jz      short loc_1801921C4
0x1801921af  cmp     eax, 0FFFFFFFFh
0x1801921b2  jnz     short loc_1801921C0
0x1801921b4  call    cs:__imp_GetLastError
0x1801921bb  nop     dword ptr [rax+rax+00h]
0x1801921c0  mov     ebx, eax
0x1801921c2  jmp     short loc_1801921D0
0x1801921c4  mov     ebx, 5B4h
0x1801921c9  jmp     short loc_1801921D0
0x1801921cb  mov     ebx, 2DFh
0x1801921d0  mov     edx, 1; fAbort
0x1801921d5  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x1801921da  call    cs:__imp_RpcAsyncCancelCall
0x1801921e1  nop     dword ptr [rax+rax+00h]
0x1801921e6  test    eax, eax
0x1801921e8  jz      short loc_180192206
0x1801921ea  mov     rcx, [rsp+0C8h]; this
0x1801921f2  mov     r9d, eax; char *
0x1801921f5  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801921fc  mov     edx, 0BEh; void *
0x180192201  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180192206  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180192209  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hHandle
0x18019220e  call    cs:__imp_WaitForSingleObject
0x180192215  nop     dword ptr [rax+rax+00h]
0x18019221a  test    eax, eax
0x18019221c  jz      short loc_180192237
0x18019221e  mov     rcx, [rsp+0C8h]; this
0x180192226  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18019222d  mov     edx, 0BFh; void *
0x180192232  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180192237  mov     [rsp+0C8h+Reply], 0; int
0x18019223f  lea     rdx, [rsp+0C8h+Reply]; Reply
0x180192244  lea     rcx, [rsp+0C8h+pAsync]; pAsync
0x180192249  call    cs:__imp_RpcAsyncCompleteCall
0x180192250  nop     dword ptr [rax+rax+00h]
0x180192255  mov     edi, eax
0x180192257  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x18019225c  call    cs:__imp_CloseHandle
0x180192263  nop     dword ptr [rax+rax+00h]
0x180192268  test    ebx, ebx
0x18019226a  jz      short loc_180192299
0x18019226c  test    edi, edi
0x18019226e  jz      short loc_18019228C
0x180192270  mov     rcx, [rsp+0C8h]; this
0x180192278  mov     r9d, edi; char *
0x18019227b  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x180192282  mov     edx, 0CFh; void *
0x180192287  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18019228c  mov     r9d, ebx
0x18019228f  mov     edx, 0D0h
0x180192294  jmp     loc_18019210B
0x180192299  test    edi, edi
0x18019229b  jz      short loc_1801922AA
0x18019229d  mov     r9d, edi
0x1801922a0  mov     edx, 0D4h
0x1801922a5  jmp     loc_18019210B
0x1801922aa  mov     ebx, [rsp+0C8h+Reply]
0x1801922ae  test    ebx, ebx
0x1801922b0  jns     short loc_1801922D2
0x1801922b2  mov     rcx, [rsp+0C8h]; this
0x1801922ba  mov     r9d, ebx; char *
0x1801922bd  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801922c4  mov     edx, 0D5h; void *
0x1801922c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801922ce  mov     eax, ebx
0x1801922d0  jmp     short loc_18019230D
0x1801922d2  xor     eax, eax
0x1801922d4  jmp     short loc_18019230D
0x1801922d6  mov     ebx, eax
0x1801922d8  mov     rcx, qword ptr [rsp+0C8h+pAsync.u]; hObject
0x1801922dd  call    cs:__imp_CloseHandle
0x1801922e4  nop     dword ptr [rax+rax+00h]
0x1801922e9  test    ebx, ebx
0x1801922eb  jz      short loc_18019230B
0x1801922ed  mov     rcx, [rsp+0C8h]; this
0x1801922f5  mov     r9d, ebx; char *
0x1801922f8  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x1801922ff  mov     edx, 96h; void *
0x180192304  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180192309  jmp     short loc_18019230D
0x18019230b  xor     eax, eax
0x18019230d  mov     rcx, [rsp+0C8h+var_28]
0x180192315  xor     rcx, rsp; StackCookie
0x180192318  call    __security_check_cookie
0x18019231d  add     rsp, 0B0h
0x180192324  pop     rdi
0x180192325  pop     rsi
0x180192326  pop     rbx
0x180192327  retn
```
