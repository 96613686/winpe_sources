# BrokeredMoveFileExW

- ea: `0x180021710`
- end: `0x18002181a`
- name: `BrokeredMoveFileExW`
- size: `266`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bdf4`
- `0x18001c174`
- `0x18001c690`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f3b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800217aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800217aa`

## string_xrefs

- `0x1800217d9`: `BrokeredMoveFileEx`
- `0x180021743`: `MoveFileProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredMoveFileExW(unsigned int a1, __int64 a2, __int64 a3, int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  _QWORD v10[46]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v11[42]; // [rsp+198h] [rbp+90h] BYREF
  __int64 v12; // [rsp+320h] [rbp+218h] BYREF
  __int64 v13; // [rsp+328h] [rbp+220h] BYREF
  int v14; // [rsp+330h] [rbp+228h] BYREF

  v14 = a4;
  v13 = a3;
  v12 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v11);
  v11[0] = &TraceProvider::MoveFileProxyActivity::`vftable';
  TraceProvider::MoveFileProxyActivity::StartActivity((TraceProvider::MoveFileProxyActivity *)v11);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v10,
    v11);
  v10[0] = &TraceProvider::MoveFileProxyActivity::`vftable';
  v10[42] = &v12;
  v10[43] = &v13;
  v10[44] = &v14;
  CurrentThreadId = GetCurrentThreadId();
  v7 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7c7248d2766b066219d9c24e5b842382___(
         v6,
         CurrentThreadId,
         v10);
  TraceProvider::MoveFileProxyActivity::~MoveFileProxyActivity((TraceProvider::MoveFileProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, v7);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredMoveFileEx", v7, a1);
  v8 = anonymous_namespace_::HResultToWin32IfPossible(v7, a1);
  TraceProvider::MoveFileProxyActivity::~MoveFileProxyActivity((TraceProvider::MoveFileProxyActivity *)v11);
  return v8;
}

```

## disassembly

```asm
0x180021710  mov     rax, rsp
0x180021713  mov     [rax+20h], r9d
0x180021717  mov     [rax+18h], r8
0x18002171b  mov     [rax+10h], rdx
0x18002171f  push    rbp
0x180021720  push    rbx
0x180021721  push    rdi
0x180021722  lea     rbp, [rax-208h]
0x180021729  sub     rsp, 2F0h
0x180021730  mov     rax, cs:__security_cookie
0x180021737  xor     rax, rsp
0x18002173a  mov     [rbp+200h+var_20], rax
0x180021741  mov     edi, ecx
0x180021743  lea     rdx, aMovefileproxya; "MoveFileProxyActivity"
0x18002174a  lea     rcx, [rbp+200h+var_170]; struct wil::details::IFailureCallback *
0x180021751  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021756  lea     rbx, ??_7MoveFileProxyActivity@TraceProvider@@6B@; const TraceProvider::MoveFileProxyActivity::`vftable'
0x18002175d  lea     rcx, [rbp+200h+var_170]; this
0x180021764  mov     [rbp+200h+var_170], rbx
0x18002176b  call    ?StartActivity@MoveFileProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::MoveFileProxyActivity::StartActivity(void)
0x180021770  lea     rdx, [rbp+200h+var_170]
0x180021777  lea     rcx, [rsp+300h+var_2E0]
0x18002177c  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021781  lea     rax, [rbp+200h+arg_8]
0x180021788  mov     qword ptr [rsp+300h+var_2E0], rbx
0x18002178d  mov     [rbp+200h+var_190], rax
0x180021791  lea     rax, [rbp+200h+arg_10]
0x180021798  mov     [rbp+200h+var_188], rax
0x18002179c  lea     rax, [rbp+200h+arg_18]
0x1800217a3  mov     [rbp+200h+var_180], rax
0x1800217aa  call    cs:__imp_GetCurrentThreadId
0x1800217b0  mov     edx, eax
0x1800217b2  lea     r8, [rsp+300h+var_2E0]
0x1800217b7  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_7c7248d2766b066219d9c24e5b842382___
0x1800217bc  lea     rcx, [rsp+300h+var_2E0]; this
0x1800217c1  mov     ebx, eax
0x1800217c3  call    ??1MoveFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::MoveFileProxyActivity::~MoveFileProxyActivity(void)
0x1800217c8  mov     edx, ebx
0x1800217ca  lea     rcx, [rbp+200h+var_170]
0x1800217d1  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800217d6  mov     r8d, edi; int
0x1800217d9  lea     rcx, aBrokeredmovefi_0; "BrokeredMoveFileEx"
0x1800217e0  mov     edx, ebx; int
0x1800217e2  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x1800217e7  mov     edx, edi
0x1800217e9  mov     ecx, ebx
0x1800217eb  call    _anonymous_namespace___HResultToWin32IfPossible
0x1800217f0  lea     rcx, [rbp+200h+var_170]; this
0x1800217f7  mov     ebx, eax
0x1800217f9  call    ??1MoveFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::MoveFileProxyActivity::~MoveFileProxyActivity(void)
0x1800217fe  mov     eax, ebx
0x180021800  mov     rcx, [rbp+200h+var_20]
0x180021807  xor     rcx, rsp; StackCookie
0x18002180a  call    __security_check_cookie
0x18002180f  add     rsp, 2F0h
0x180021816  pop     rdi
0x180021817  pop     rbx
0x180021818  pop     rbp
0x180021819  retn
```
