# BrokeredCreateDirectoryW

- ea: `0x180021060`
- end: `0x18002114e`
- name: `BrokeredCreateDirectoryW`
- size: `238`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001b7bc`
- `0x18001c174`
- `0x18001c588`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001eff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800210e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800210e4`

## string_xrefs

- `0x18002110f`: `BrokeredCreateDirectory`
- `0x18002108f`: `CreateDirectoryProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredCreateDirectoryW(unsigned int a1, __int64 a2, __int64 a3)
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
    (__int64)"CreateDirectoryProxyActivity");
  v9[0] = &TraceProvider::CreateDirectoryProxyActivity::`vftable';
  TraceProvider::CreateDirectoryProxyActivity::StartActivity((TraceProvider::CreateDirectoryProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v10,
    (__int64)v9);
  v10[0] = &TraceProvider::CreateDirectoryProxyActivity::`vftable';
  v10[42] = &v12;
  v10[43] = &v11;
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_2f945c1d28b042d7687b46c9f8d83655___(
         v5,
         CurrentThreadId,
         v10);
  TraceProvider::CreateDirectoryProxyActivity::~CreateDirectoryProxyActivity((TraceProvider::CreateDirectoryProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, v6);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredCreateDirectory", v6, a1);
  v7 = anonymous_namespace_::HResultToWin32IfPossible(v6, a1);
  TraceProvider::CreateDirectoryProxyActivity::~CreateDirectoryProxyActivity((TraceProvider::CreateDirectoryProxyActivity *)v9);
  return v7;
}

```

## disassembly

```asm
0x180021060  mov     [rsp-8+arg_10], r8
0x180021065  mov     [rsp-8+arg_8], rdx
0x18002106a  push    rbp
0x18002106b  push    rbx
0x18002106c  push    rdi
0x18002106d  lea     rbp, [rsp-1E0h]
0x180021075  sub     rsp, 2E0h
0x18002107c  mov     rax, cs:__security_cookie
0x180021083  xor     rax, rsp
0x180021086  mov     [rbp+1F0h+var_20], rax
0x18002108d  mov     edi, ecx
0x18002108f  lea     rdx, aCreatedirector_1; "CreateDirectoryProxyActivity"
0x180021096  lea     rcx, [rsp+2F0h+var_2D0]; struct wil::details::IFailureCallback *
0x18002109b  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800210a0  lea     rbx, ??_7CreateDirectoryProxyActivity@TraceProvider@@6B@; const TraceProvider::CreateDirectoryProxyActivity::`vftable'
0x1800210a7  lea     rcx, [rsp+2F0h+var_2D0]; this
0x1800210ac  mov     [rsp+2F0h+var_2D0], rbx
0x1800210b1  call    ?StartActivity@CreateDirectoryProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::CreateDirectoryProxyActivity::StartActivity(void)
0x1800210b6  lea     rdx, [rsp+2F0h+var_2D0]
0x1800210bb  lea     rcx, [rbp+1F0h+var_180]
0x1800210bf  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800210c4  lea     rax, [rbp+1F0h+arg_10]
0x1800210cb  mov     [rbp+1F0h+var_180], rbx
0x1800210cf  mov     [rbp+1F0h+var_30], rax
0x1800210d6  lea     rax, [rbp+1F0h+arg_8]
0x1800210dd  mov     [rbp+1F0h+var_28], rax
0x1800210e4  call    cs:__imp_GetCurrentThreadId
0x1800210ea  mov     edx, eax
0x1800210ec  lea     r8, [rbp+1F0h+var_180]
0x1800210f0  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_2f945c1d28b042d7687b46c9f8d83655___
0x1800210f5  lea     rcx, [rbp+1F0h+var_180]; this
0x1800210f9  mov     ebx, eax
0x1800210fb  call    ??1CreateDirectoryProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateDirectoryProxyActivity::~CreateDirectoryProxyActivity(void)
0x180021100  mov     edx, ebx
0x180021102  lea     rcx, [rsp+2F0h+var_2D0]
0x180021107  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002110c  mov     r8d, edi; int
0x18002110f  lea     rcx, aBrokeredcreate_1; "BrokeredCreateDirectory"
0x180021116  mov     edx, ebx; int
0x180021118  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x18002111d  mov     edx, edi
0x18002111f  mov     ecx, ebx
0x180021121  call    _anonymous_namespace___HResultToWin32IfPossible
0x180021126  lea     rcx, [rsp+2F0h+var_2D0]; this
0x18002112b  mov     ebx, eax
0x18002112d  call    ??1CreateDirectoryProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateDirectoryProxyActivity::~CreateDirectoryProxyActivity(void)
0x180021132  mov     eax, ebx
0x180021134  mov     rcx, [rbp+1F0h+var_20]
0x18002113b  xor     rcx, rsp; StackCookie
0x18002113e  call    __security_check_cookie
0x180021143  add     rsp, 2E0h
0x18002114a  pop     rdi
0x18002114b  pop     rbx
0x18002114c  pop     rbp
0x18002114d  retn
```
