# BrokeredRemoveDirectoryW

- ea: `0x180021820`
- end: `0x18002190c`
- name: `BrokeredRemoveDirectoryW`
- size: `236`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bb48`
- `0x18001c174`
- `0x18001c6bc`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f454`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021898`

## string_xrefs

- `0x1800218c3`: `BrokeredRemoveDirectory`
- `0x180021851`: `RemoveDirectoryProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredRemoveDirectoryW(unsigned int a1, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  _QWORD v8[42]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v9[44]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v10; // [rsp+300h] [rbp+1F8h] BYREF

  v10 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v8,
    (__int64)"RemoveDirectoryProxyActivity");
  v8[0] = &TraceProvider::RemoveDirectoryProxyActivity::`vftable';
  TraceProvider::RemoveDirectoryProxyActivity::StartActivity((TraceProvider::RemoveDirectoryProxyActivity *)v8);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)v8);
  v9[0] = &TraceProvider::RemoveDirectoryProxyActivity::`vftable';
  v9[42] = &v10;
  CurrentThreadId = GetCurrentThreadId();
  v5 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_62a8956ae4bc967a1b7224dcbb3e6d22___(
         v4,
         CurrentThreadId,
         v9);
  TraceProvider::RemoveDirectoryProxyActivity::~RemoveDirectoryProxyActivity((TraceProvider::RemoveDirectoryProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v8, v5);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredRemoveDirectory", v5, a1);
  v6 = anonymous_namespace_::HResultToWin32IfPossible(v5, a1);
  TraceProvider::RemoveDirectoryProxyActivity::~RemoveDirectoryProxyActivity((TraceProvider::RemoveDirectoryProxyActivity *)v8);
  return v6;
}

```

## disassembly

```asm
0x180021820  mov     rax, rsp
0x180021823  mov     [rax+18h], rbx
0x180021827  mov     [rax+20h], rdi
0x18002182b  mov     [rax+10h], rdx
0x18002182f  push    rbp
0x180021830  lea     rbp, [rax-1E8h]
0x180021837  sub     rsp, 2E0h
0x18002183e  mov     rax, cs:__security_cookie
0x180021845  xor     rax, rsp
0x180021848  mov     [rbp+1E0h+var_10], rax
0x18002184f  mov     edi, ecx
0x180021851  lea     rdx, aRemovedirector_1; "RemoveDirectoryProxyActivity"
0x180021858  lea     rcx, [rsp+2E0h+var_2C0]; struct wil::details::IFailureCallback *
0x18002185d  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021862  lea     rbx, ??_7RemoveDirectoryProxyActivity@TraceProvider@@6B@; const TraceProvider::RemoveDirectoryProxyActivity::`vftable'
0x180021869  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18002186e  mov     [rsp+2E0h+var_2C0], rbx
0x180021873  call    ?StartActivity@RemoveDirectoryProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::RemoveDirectoryProxyActivity::StartActivity(void)
0x180021878  lea     rdx, [rsp+2E0h+var_2C0]
0x18002187d  lea     rcx, [rbp+1E0h+var_170]
0x180021881  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021886  lea     rax, [rbp+1E0h+arg_8]
0x18002188d  mov     [rbp+1E0h+var_170], rbx
0x180021891  mov     [rbp+1E0h+var_20], rax
0x180021898  call    cs:__imp_GetCurrentThreadId
0x18002189e  mov     edx, eax
0x1800218a0  lea     r8, [rbp+1E0h+var_170]
0x1800218a4  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_62a8956ae4bc967a1b7224dcbb3e6d22___
0x1800218a9  lea     rcx, [rbp+1E0h+var_170]; this
0x1800218ad  mov     ebx, eax
0x1800218af  call    ??1RemoveDirectoryProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::RemoveDirectoryProxyActivity::~RemoveDirectoryProxyActivity(void)
0x1800218b4  mov     edx, ebx
0x1800218b6  lea     rcx, [rsp+2E0h+var_2C0]
0x1800218bb  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800218c0  mov     r8d, edi; int
0x1800218c3  lea     rcx, aBrokeredremove_0; "BrokeredRemoveDirectory"
0x1800218ca  mov     edx, ebx; int
0x1800218cc  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x1800218d1  mov     edx, edi
0x1800218d3  mov     ecx, ebx
0x1800218d5  call    _anonymous_namespace___HResultToWin32IfPossible
0x1800218da  lea     rcx, [rsp+2E0h+var_2C0]; this
0x1800218df  mov     ebx, eax
0x1800218e1  call    ??1RemoveDirectoryProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::RemoveDirectoryProxyActivity::~RemoveDirectoryProxyActivity(void)
0x1800218e6  mov     eax, ebx
0x1800218e8  mov     rcx, [rbp+1E0h+var_10]
0x1800218ef  xor     rcx, rsp; StackCookie
0x1800218f2  call    __security_check_cookie
0x1800218f7  lea     r11, [rsp+2E0h+var_s0]
0x1800218ff  mov     rbx, [r11+20h]
0x180021903  mov     rdi, [r11+28h]
0x180021907  mov     rsp, r11
0x18002190a  pop     rbp
0x18002190b  retn
```
