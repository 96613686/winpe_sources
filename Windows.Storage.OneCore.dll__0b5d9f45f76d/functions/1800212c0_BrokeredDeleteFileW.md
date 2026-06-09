# BrokeredDeleteFileW

- ea: `0x1800212c0`
- end: `0x1800213ac`
- name: `BrokeredDeleteFileW`
- size: `236`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001b89c`
- `0x18001c174`
- `0x18001c5e0`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f134`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021338`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021338`

## string_xrefs

- `0x180021363`: `BrokeredDeleteFile`
- `0x1800212f1`: `DeleteFileProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredDeleteFileW(unsigned int a1, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  _QWORD v8[42]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v9[44]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v10; // [rsp+300h] [rbp+1F8h] BYREF

  v10 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v8);
  v8[0] = &TraceProvider::DeleteFileProxyActivity::`vftable';
  TraceProvider::DeleteFileProxyActivity::StartActivity((TraceProvider::DeleteFileProxyActivity *)v8);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    v8);
  v9[0] = &TraceProvider::DeleteFileProxyActivity::`vftable';
  v9[42] = &v10;
  CurrentThreadId = GetCurrentThreadId();
  v5 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_42292127ab9113ed31bcced9dd1642b2___(
         v4,
         CurrentThreadId,
         v9);
  TraceProvider::DeleteFileProxyActivity::~DeleteFileProxyActivity((TraceProvider::DeleteFileProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v8, v5);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredDeleteFile", v5, a1);
  v6 = anonymous_namespace_::HResultToWin32IfPossible(v5, a1);
  TraceProvider::DeleteFileProxyActivity::~DeleteFileProxyActivity((TraceProvider::DeleteFileProxyActivity *)v8);
  return v6;
}

```

## disassembly

```asm
0x1800212c0  mov     rax, rsp
0x1800212c3  mov     [rax+18h], rbx
0x1800212c7  mov     [rax+20h], rdi
0x1800212cb  mov     [rax+10h], rdx
0x1800212cf  push    rbp
0x1800212d0  lea     rbp, [rax-1E8h]
0x1800212d7  sub     rsp, 2E0h
0x1800212de  mov     rax, cs:__security_cookie
0x1800212e5  xor     rax, rsp
0x1800212e8  mov     [rbp+1E0h+var_10], rax
0x1800212ef  mov     edi, ecx
0x1800212f1  lea     rdx, aDeletefileprox; "DeleteFileProxyActivity"
0x1800212f8  lea     rcx, [rsp+2E0h+var_2C0]; struct wil::details::IFailureCallback *
0x1800212fd  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021302  lea     rbx, ??_7DeleteFileProxyActivity@TraceProvider@@6B@; const TraceProvider::DeleteFileProxyActivity::`vftable'
0x180021309  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18002130e  mov     [rsp+2E0h+var_2C0], rbx
0x180021313  call    ?StartActivity@DeleteFileProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::DeleteFileProxyActivity::StartActivity(void)
0x180021318  lea     rdx, [rsp+2E0h+var_2C0]
0x18002131d  lea     rcx, [rbp+1E0h+var_170]
0x180021321  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021326  lea     rax, [rbp+1E0h+arg_8]
0x18002132d  mov     [rbp+1E0h+var_170], rbx
0x180021331  mov     [rbp+1E0h+var_20], rax
0x180021338  call    cs:__imp_GetCurrentThreadId
0x18002133e  mov     edx, eax
0x180021340  lea     r8, [rbp+1E0h+var_170]
0x180021344  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_42292127ab9113ed31bcced9dd1642b2___
0x180021349  lea     rcx, [rbp+1E0h+var_170]; this
0x18002134d  mov     ebx, eax
0x18002134f  call    ??1DeleteFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::DeleteFileProxyActivity::~DeleteFileProxyActivity(void)
0x180021354  mov     edx, ebx
0x180021356  lea     rcx, [rsp+2E0h+var_2C0]
0x18002135b  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180021360  mov     r8d, edi; int
0x180021363  lea     rcx, aBrokereddelete_0; "BrokeredDeleteFile"
0x18002136a  mov     edx, ebx; int
0x18002136c  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x180021371  mov     edx, edi
0x180021373  mov     ecx, ebx
0x180021375  call    _anonymous_namespace___HResultToWin32IfPossible
0x18002137a  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18002137f  mov     ebx, eax
0x180021381  call    ??1DeleteFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::DeleteFileProxyActivity::~DeleteFileProxyActivity(void)
0x180021386  mov     eax, ebx
0x180021388  mov     rcx, [rbp+1E0h+var_10]
0x18002138f  xor     rcx, rsp; StackCookie
0x180021392  call    __security_check_cookie
0x180021397  lea     r11, [rsp+2E0h+var_s0]
0x18002139f  mov     rbx, [r11+20h]
0x1800213a3  mov     rdi, [r11+28h]
0x1800213a7  mov     rsp, r11
0x1800213aa  pop     rbp
0x1800213ab  retn
```
