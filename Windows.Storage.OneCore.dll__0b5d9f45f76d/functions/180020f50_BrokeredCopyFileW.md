# BrokeredCopyFileW

- ea: `0x180020f50`
- end: `0x18002105a`
- name: `BrokeredCopyFileW`
- size: `266`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bed4`
- `0x18001c174`
- `0x18001c55c`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001ef54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020fea`

## string_xrefs

- `0x180021019`: `BrokeredCopyFile`
- `0x180020f83`: `CopyFileProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredCopyFileW(unsigned int a1, __int64 a2, __int64 a3, int a4)
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
  v11[0] = &TraceProvider::CopyFileProxyActivity::`vftable';
  TraceProvider::CopyFileProxyActivity::StartActivity((TraceProvider::CopyFileProxyActivity *)v11);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v10,
    v11);
  v10[0] = &TraceProvider::CopyFileProxyActivity::`vftable';
  v10[42] = &v12;
  v10[43] = &v13;
  v10[44] = &v14;
  CurrentThreadId = GetCurrentThreadId();
  v7 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_95afcd39453873b60d63f0d5792d158c___(
         v6,
         CurrentThreadId,
         v10);
  TraceProvider::CopyFileProxyActivity::~CopyFileProxyActivity((TraceProvider::CopyFileProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, v7);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredCopyFile", v7, a1);
  v8 = anonymous_namespace_::HResultToWin32IfPossible(v7, a1);
  TraceProvider::CopyFileProxyActivity::~CopyFileProxyActivity((TraceProvider::CopyFileProxyActivity *)v11);
  return v8;
}

```

## disassembly

```asm
0x180020f50  mov     rax, rsp
0x180020f53  mov     [rax+20h], r9d
0x180020f57  mov     [rax+18h], r8
0x180020f5b  mov     [rax+10h], rdx
0x180020f5f  push    rbp
0x180020f60  push    rbx
0x180020f61  push    rdi
0x180020f62  lea     rbp, [rax-208h]
0x180020f69  sub     rsp, 2F0h
0x180020f70  mov     rax, cs:__security_cookie
0x180020f77  xor     rax, rsp
0x180020f7a  mov     [rbp+200h+var_20], rax
0x180020f81  mov     edi, ecx
0x180020f83  lea     rdx, aCopyfileproxya; "CopyFileProxyActivity"
0x180020f8a  lea     rcx, [rbp+200h+var_170]; struct wil::details::IFailureCallback *
0x180020f91  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020f96  lea     rbx, ??_7CopyFileProxyActivity@TraceProvider@@6B@; const TraceProvider::CopyFileProxyActivity::`vftable'
0x180020f9d  lea     rcx, [rbp+200h+var_170]; this
0x180020fa4  mov     [rbp+200h+var_170], rbx
0x180020fab  call    ?StartActivity@CopyFileProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::CopyFileProxyActivity::StartActivity(void)
0x180020fb0  lea     rdx, [rbp+200h+var_170]
0x180020fb7  lea     rcx, [rsp+300h+var_2E0]
0x180020fbc  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180020fc1  lea     rax, [rbp+200h+arg_8]
0x180020fc8  mov     qword ptr [rsp+300h+var_2E0], rbx
0x180020fcd  mov     [rbp+200h+var_190], rax
0x180020fd1  lea     rax, [rbp+200h+arg_10]
0x180020fd8  mov     [rbp+200h+var_188], rax
0x180020fdc  lea     rax, [rbp+200h+arg_18]
0x180020fe3  mov     [rbp+200h+var_180], rax
0x180020fea  call    cs:__imp_GetCurrentThreadId
0x180020ff0  mov     edx, eax
0x180020ff2  lea     r8, [rsp+300h+var_2E0]
0x180020ff7  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_95afcd39453873b60d63f0d5792d158c___
0x180020ffc  lea     rcx, [rsp+300h+var_2E0]; this
0x180021001  mov     ebx, eax
0x180021003  call    ??1CopyFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CopyFileProxyActivity::~CopyFileProxyActivity(void)
0x180021008  mov     edx, ebx
0x18002100a  lea     rcx, [rbp+200h+var_170]
0x180021011  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180021016  mov     r8d, edi; int
0x180021019  lea     rcx, aBrokeredcopyfi_0; "BrokeredCopyFile"
0x180021020  mov     edx, ebx; int
0x180021022  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x180021027  mov     edx, edi
0x180021029  mov     ecx, ebx
0x18002102b  call    _anonymous_namespace___HResultToWin32IfPossible
0x180021030  lea     rcx, [rbp+200h+var_170]; this
0x180021037  mov     ebx, eax
0x180021039  call    ??1CopyFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CopyFileProxyActivity::~CopyFileProxyActivity(void)
0x18002103e  mov     eax, ebx
0x180021040  mov     rcx, [rbp+200h+var_20]
0x180021047  xor     rcx, rsp; StackCookie
0x18002104a  call    __security_check_cookie
0x18002104f  add     rsp, 2F0h
0x180021056  pop     rdi
0x180021057  pop     rbx
0x180021058  pop     rbp
0x180021059  retn
```
