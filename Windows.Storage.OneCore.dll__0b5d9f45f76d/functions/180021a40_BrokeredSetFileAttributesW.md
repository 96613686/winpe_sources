# BrokeredSetFileAttributesW

- ea: `0x180021a40`
- end: `0x180021b2e`
- name: `BrokeredSetFileAttributesW`
- size: `238`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001ba68`
- `0x18001c174`
- `0x18001c768`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f594`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ac4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ac4`

## string_xrefs

- `0x180021aef`: `BrokeredSetFileAttributes`
- `0x180021a6f`: `SetFileAttributesProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredSetFileAttributesW(unsigned int a1, __int64 a2, int a3)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  _QWORD v9[42]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[44]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v11; // [rsp+308h] [rbp+208h] BYREF
  int v12; // [rsp+310h] [rbp+210h] BYREF

  v12 = a3;
  v11 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v9,
    (__int64)"SetFileAttributesProxyActivity");
  v9[0] = &TraceProvider::SetFileAttributesProxyActivity::`vftable';
  TraceProvider::SetFileAttributesProxyActivity::StartActivity((TraceProvider::SetFileAttributesProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v10,
    (__int64)v9);
  v10[0] = &TraceProvider::SetFileAttributesProxyActivity::`vftable';
  v10[42] = &v11;
  v10[43] = &v12;
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_60fca6eac3d28f4bb8df92bce08f5d7c___(
         v5,
         CurrentThreadId,
         v10);
  TraceProvider::SetFileAttributesProxyActivity::~SetFileAttributesProxyActivity((TraceProvider::SetFileAttributesProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, v6);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredSetFileAttributes", v6, a1);
  v7 = anonymous_namespace_::HResultToWin32IfPossible(v6, a1);
  TraceProvider::SetFileAttributesProxyActivity::~SetFileAttributesProxyActivity((TraceProvider::SetFileAttributesProxyActivity *)v9);
  return v7;
}

```

## disassembly

```asm
0x180021a40  mov     [rsp-8+arg_10], r8d
0x180021a45  mov     [rsp-8+arg_8], rdx
0x180021a4a  push    rbp
0x180021a4b  push    rbx
0x180021a4c  push    rdi
0x180021a4d  lea     rbp, [rsp-1E0h]
0x180021a55  sub     rsp, 2E0h
0x180021a5c  mov     rax, cs:__security_cookie
0x180021a63  xor     rax, rsp
0x180021a66  mov     [rbp+1F0h+var_20], rax
0x180021a6d  mov     edi, ecx
0x180021a6f  lea     rdx, aSetfileattribu_1; "SetFileAttributesProxyActivity"
0x180021a76  lea     rcx, [rsp+2F0h+var_2D0]; struct wil::details::IFailureCallback *
0x180021a7b  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021a80  lea     rbx, ??_7SetFileAttributesProxyActivity@TraceProvider@@6B@; const TraceProvider::SetFileAttributesProxyActivity::`vftable'
0x180021a87  lea     rcx, [rsp+2F0h+var_2D0]; this
0x180021a8c  mov     [rsp+2F0h+var_2D0], rbx
0x180021a91  call    ?StartActivity@SetFileAttributesProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::SetFileAttributesProxyActivity::StartActivity(void)
0x180021a96  lea     rdx, [rsp+2F0h+var_2D0]
0x180021a9b  lea     rcx, [rbp+1F0h+var_180]
0x180021a9f  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021aa4  lea     rax, [rbp+1F0h+arg_8]
0x180021aab  mov     [rbp+1F0h+var_180], rbx
0x180021aaf  mov     [rbp+1F0h+var_30], rax
0x180021ab6  lea     rax, [rbp+1F0h+arg_10]
0x180021abd  mov     [rbp+1F0h+var_28], rax
0x180021ac4  call    cs:__imp_GetCurrentThreadId
0x180021aca  mov     edx, eax
0x180021acc  lea     r8, [rbp+1F0h+var_180]
0x180021ad0  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_60fca6eac3d28f4bb8df92bce08f5d7c___
0x180021ad5  lea     rcx, [rbp+1F0h+var_180]; this
0x180021ad9  mov     ebx, eax
0x180021adb  call    ??1SetFileAttributesProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::SetFileAttributesProxyActivity::~SetFileAttributesProxyActivity(void)
0x180021ae0  mov     edx, ebx
0x180021ae2  lea     rcx, [rsp+2F0h+var_2D0]
0x180021ae7  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180021aec  mov     r8d, edi; int
0x180021aef  lea     rcx, aBrokeredsetfil_0; "BrokeredSetFileAttributes"
0x180021af6  mov     edx, ebx; int
0x180021af8  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x180021afd  mov     edx, edi
0x180021aff  mov     ecx, ebx
0x180021b01  call    _anonymous_namespace___HResultToWin32IfPossible
0x180021b06  lea     rcx, [rsp+2F0h+var_2D0]; this
0x180021b0b  mov     ebx, eax
0x180021b0d  call    ??1SetFileAttributesProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::SetFileAttributesProxyActivity::~SetFileAttributesProxyActivity(void)
0x180021b12  mov     eax, ebx
0x180021b14  mov     rcx, [rbp+1F0h+var_20]
0x180021b1b  xor     rcx, rsp; StackCookie
0x180021b1e  call    __security_check_cookie
0x180021b23  add     rsp, 2E0h
0x180021b2a  pop     rdi
0x180021b2b  pop     rbx
0x180021b2c  pop     rbp
0x180021b2d  retn
```
