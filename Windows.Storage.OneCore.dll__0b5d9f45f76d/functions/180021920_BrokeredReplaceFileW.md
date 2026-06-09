# BrokeredReplaceFileW

- ea: `0x180021920`
- end: `0x180021a38`
- name: `BrokeredReplaceFileW`
- size: `280`
- prototype: `__int64(unsigned int, ...)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bd14`
- `0x18001c174`
- `0x18001c6e8`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f4f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800219c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800219c8`

## string_xrefs

- `0x1800219f7`: `BrokeredReplaceFile`
- `0x180021953`: `ReplaceFileProxyActivity`

## pseudocode

```c
__int64 BrokeredReplaceFileW(unsigned int a1, ...)
{
  DWORD CurrentThreadId; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  _QWORD v7[46]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v8[42]; // [rsp+198h] [rbp+90h] BYREF
  __int64 v9; // [rsp+320h] [rbp+218h] BYREF
  va_list va; // [rsp+320h] [rbp+218h]
  __int64 v11; // [rsp+328h] [rbp+220h] BYREF
  va_list va1; // [rsp+328h] [rbp+220h]
  __int64 v13; // [rsp+330h] [rbp+228h] BYREF
  va_list va2; // [rsp+330h] [rbp+228h]
  va_list va3; // [rsp+338h] [rbp+230h] BYREF

  va_start(va3, a1);
  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v8);
  v8[0] = &TraceProvider::ReplaceFileProxyActivity::`vftable';
  TraceProvider::ReplaceFileProxyActivity::StartActivity((TraceProvider::ReplaceFileProxyActivity *)v8);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v7,
    v8);
  v7[0] = &TraceProvider::ReplaceFileProxyActivity::`vftable';
  va_copy((va_list)&v7[42], va);
  va_copy((va_list)&v7[43], va1);
  va_copy((va_list)&v7[44], va2);
  va_copy((va_list)&v7[45], va3);
  CurrentThreadId = GetCurrentThreadId();
  v4 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_7ba05ad01ccac0ac0d571139ec3757e5___(
         v3,
         CurrentThreadId,
         v7);
  TraceProvider::ReplaceFileProxyActivity::~ReplaceFileProxyActivity((TraceProvider::ReplaceFileProxyActivity *)v7);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v8, v4);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredReplaceFile", v4, a1);
  v5 = anonymous_namespace_::HResultToWin32IfPossible(v4, a1);
  TraceProvider::ReplaceFileProxyActivity::~ReplaceFileProxyActivity((TraceProvider::ReplaceFileProxyActivity *)v8);
  return v5;
}

```

## disassembly

```asm
0x180021920  mov     rax, rsp
0x180021923  mov     [rax+20h], r9
0x180021927  mov     [rax+18h], r8
0x18002192b  mov     [rax+10h], rdx
0x18002192f  push    rbp
0x180021930  push    rbx
0x180021931  push    rdi
0x180021932  lea     rbp, [rax-208h]
0x180021939  sub     rsp, 2F0h
0x180021940  mov     rax, cs:__security_cookie
0x180021947  xor     rax, rsp
0x18002194a  mov     [rbp+200h+var_20], rax
0x180021951  mov     edi, ecx
0x180021953  lea     rdx, aReplacefilepro; "ReplaceFileProxyActivity"
0x18002195a  lea     rcx, [rbp+200h+var_170]; struct wil::details::IFailureCallback *
0x180021961  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021966  lea     rbx, ??_7ReplaceFileProxyActivity@TraceProvider@@6B@; const TraceProvider::ReplaceFileProxyActivity::`vftable'
0x18002196d  lea     rcx, [rbp+200h+var_170]; this
0x180021974  mov     [rbp+200h+var_170], rbx
0x18002197b  call    ?StartActivity@ReplaceFileProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::ReplaceFileProxyActivity::StartActivity(void)
0x180021980  lea     rdx, [rbp+200h+var_170]
0x180021987  lea     rcx, [rsp+300h+var_2E0]
0x18002198c  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021991  lea     rax, [rbp+200h+arg_8]
0x180021998  mov     qword ptr [rsp+300h+var_2E0], rbx
0x18002199d  mov     [rbp+200h+var_190], rax
0x1800219a1  lea     rax, [rbp+200h+arg_10]
0x1800219a8  mov     [rbp+200h+var_188], rax
0x1800219ac  lea     rax, [rbp+200h+arg_18]
0x1800219b3  mov     [rbp+200h+var_180], rax
0x1800219ba  lea     rax, [rbp+200h+arg_20]
0x1800219c1  mov     [rbp+200h+var_178], rax
0x1800219c8  call    cs:__imp_GetCurrentThreadId
0x1800219ce  mov     edx, eax
0x1800219d0  lea     r8, [rsp+300h+var_2E0]
0x1800219d5  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_7ba05ad01ccac0ac0d571139ec3757e5___
0x1800219da  lea     rcx, [rsp+300h+var_2E0]; this
0x1800219df  mov     ebx, eax
0x1800219e1  call    ??1ReplaceFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::ReplaceFileProxyActivity::~ReplaceFileProxyActivity(void)
0x1800219e6  mov     edx, ebx
0x1800219e8  lea     rcx, [rbp+200h+var_170]
0x1800219ef  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800219f4  mov     r8d, edi; int
0x1800219f7  lea     rcx, aBrokeredreplac_0; "BrokeredReplaceFile"
0x1800219fe  mov     edx, ebx; int
0x180021a00  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x180021a05  mov     edx, edi
0x180021a07  mov     ecx, ebx
0x180021a09  call    _anonymous_namespace___HResultToWin32IfPossible
0x180021a0e  lea     rcx, [rbp+200h+var_170]; this
0x180021a15  mov     ebx, eax
0x180021a17  call    ??1ReplaceFileProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::ReplaceFileProxyActivity::~ReplaceFileProxyActivity(void)
0x180021a1c  mov     eax, ebx
0x180021a1e  mov     rcx, [rbp+200h+var_20]
0x180021a25  xor     rcx, rsp; StackCookie
0x180021a28  call    __security_check_cookie
0x180021a2d  add     rsp, 2F0h
0x180021a34  pop     rdi
0x180021a35  pop     rbx
0x180021a36  pop     rbp
0x180021a37  retn
```
