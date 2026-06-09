# BrokeredGetFileAttributesW

- ea: `0x180021610`
- end: `0x1800216fe`
- name: `BrokeredGetFileAttributesW`
- size: `238`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001c094`
- `0x18001c174`
- `0x18001c664`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021694`

## string_xrefs

- `0x1800216bf`: `BrokeredGetFileAttributes`

## pseudocode

```c
__int64 __fastcall BrokeredGetFileAttributesW(unsigned int a1, __int64 a2, __int64 a3)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  _QWORD v9[42]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[44]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v11; // [rsp+308h] [rbp+208h] BYREF
  __int64 v12; // [rsp+310h] [rbp+210h] BYREF

  v12 = a3;
  v11 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v9,
    (__int64)"GetFileAttributesProxyActivity");
  v9[0] = &TraceProvider::GetFileAttributesProxyActivity::`vftable';
  TraceProvider::GetFileAttributesProxyActivity::StartActivity((TraceProvider::GetFileAttributesProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v10,
    (__int64)v9);
  v10[0] = &TraceProvider::GetFileAttributesProxyActivity::`vftable';
  v10[42] = &v11;
  v10[43] = &v12;
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_f63bbe083a301d83e9c6aa65442624a6___(
         v5,
         CurrentThreadId,
         v10);
  TraceProvider::GetFileAttributesProxyActivity::~GetFileAttributesProxyActivity((TraceProvider::GetFileAttributesProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, v6);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredGetFileAttributes", v6, a1);
  v7 = anonymous_namespace_::HResultToWin32IfPossible(v6, a1);
  TraceProvider::GetFileAttributesProxyActivity::~GetFileAttributesProxyActivity((TraceProvider::GetFileAttributesProxyActivity *)v9);
  return v7;
}

```

## disassembly

```asm
0x180021610  mov     [rsp-8+arg_10], r8
0x180021615  mov     [rsp-8+arg_8], rdx
0x18002161a  push    rbp
0x18002161b  push    rbx
0x18002161c  push    rdi
0x18002161d  lea     rbp, [rsp-1E0h]
0x180021625  sub     rsp, 2E0h
0x18002162c  mov     rax, cs:__security_cookie
0x180021633  xor     rax, rsp
0x180021636  mov     [rbp+1F0h+var_20], rax
0x18002163d  mov     edi, ecx
0x18002163f  lea     rdx, aGetfileattribu_2; "GetFileAttributesProxyActivity"
0x180021646  lea     rcx, [rsp+2F0h+var_2D0]; struct wil::details::IFailureCallback *
0x18002164b  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021650  lea     rbx, ??_7GetFileAttributesProxyActivity@TraceProvider@@6B@; const TraceProvider::GetFileAttributesProxyActivity::`vftable'
0x180021657  lea     rcx, [rsp+2F0h+var_2D0]; this
0x18002165c  mov     [rsp+2F0h+var_2D0], rbx
0x180021661  call    ?StartActivity@GetFileAttributesProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::GetFileAttributesProxyActivity::StartActivity(void)
0x180021666  lea     rdx, [rsp+2F0h+var_2D0]
0x18002166b  lea     rcx, [rbp+1F0h+var_180]
0x18002166f  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021674  lea     rax, [rbp+1F0h+arg_8]
0x18002167b  mov     [rbp+1F0h+var_180], rbx
0x18002167f  mov     [rbp+1F0h+var_30], rax
0x180021686  lea     rax, [rbp+1F0h+arg_10]
0x18002168d  mov     [rbp+1F0h+var_28], rax
0x180021694  call    cs:__imp_GetCurrentThreadId
0x18002169a  mov     edx, eax
0x18002169c  lea     r8, [rbp+1F0h+var_180]
0x1800216a0  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_f63bbe083a301d83e9c6aa65442624a6___
0x1800216a5  lea     rcx, [rbp+1F0h+var_180]; this
0x1800216a9  mov     ebx, eax
0x1800216ab  call    ??1GetFileAttributesProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesProxyActivity::~GetFileAttributesProxyActivity(void)
0x1800216b0  mov     edx, ebx
0x1800216b2  lea     rcx, [rsp+2F0h+var_2D0]
0x1800216b7  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800216bc  mov     r8d, edi; int
0x1800216bf  lea     rcx, aBrokeredgetfil_2; "BrokeredGetFileAttributes"
0x1800216c6  mov     edx, ebx; int
0x1800216c8  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x1800216cd  mov     edx, edi
0x1800216cf  mov     ecx, ebx
0x1800216d1  call    _anonymous_namespace___HResultToWin32IfPossible
0x1800216d6  lea     rcx, [rsp+2F0h+var_2D0]; this
0x1800216db  mov     ebx, eax
0x1800216dd  call    ??1GetFileAttributesProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesProxyActivity::~GetFileAttributesProxyActivity(void)
0x1800216e2  mov     eax, ebx
0x1800216e4  mov     rcx, [rbp+1F0h+var_20]
0x1800216eb  xor     rcx, rsp; StackCookie
0x1800216ee  call    __security_check_cookie
0x1800216f3  add     rsp, 2E0h
0x1800216fa  pop     rdi
0x1800216fb  pop     rbx
0x1800216fc  pop     rbp
0x1800216fd  retn
```
