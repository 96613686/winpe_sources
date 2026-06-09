# BrokeredCreateFile2

- ea: `0x180021160`
- end: `0x1800212b0`
- name: `BrokeredCreateFile2`
- size: `336`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char, char, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bc28`
- `0x18001c174`
- `0x18001c5b4`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f094`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021240`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021240`

## string_xrefs

- `0x18002126f`: `BrokeredCreateFile2`
- `0x180021198`: `CreateFile2ProxyActivity`

## pseudocode

```c
__int64 __fastcall BrokeredCreateFile2(unsigned int a1, __int64 a2, int a3, int a4, char a5, char a6, _QWORD *a7)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  _QWORD *v13; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v14[48]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v15[42]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v16; // [rsp+340h] [rbp+238h] BYREF
  int v17; // [rsp+348h] [rbp+240h] BYREF
  int v18; // [rsp+350h] [rbp+248h] BYREF

  v18 = a4;
  v17 = a3;
  v16 = a2;
  v13 = a7;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v15,
    (__int64)"CreateFile2ProxyActivity");
  v15[0] = &TraceProvider::CreateFile2ProxyActivity::`vftable';
  TraceProvider::CreateFile2ProxyActivity::StartActivity((TraceProvider::CreateFile2ProxyActivity *)v15);
  *v13 = -1;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v14,
    (__int64)v15);
  v14[0] = &TraceProvider::CreateFile2ProxyActivity::`vftable';
  v14[42] = &v16;
  v14[43] = &a6;
  v14[44] = &v17;
  v14[45] = &v18;
  v14[46] = &a5;
  v14[47] = &v13;
  CurrentThreadId = GetCurrentThreadId();
  v10 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_6aece9f498c1836e6b49856eae513237___(
          v9,
          CurrentThreadId,
          v14);
  TraceProvider::CreateFile2ProxyActivity::~CreateFile2ProxyActivity((TraceProvider::CreateFile2ProxyActivity *)v14);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15, v10);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredCreateFile2", v10, a1);
  v11 = anonymous_namespace_::HResultToWin32IfPossible(v10, a1);
  TraceProvider::CreateFile2ProxyActivity::~CreateFile2ProxyActivity((TraceProvider::CreateFile2ProxyActivity *)v15);
  return v11;
}

```

## disassembly

```asm
0x180021160  mov     rax, rsp
0x180021163  mov     [rax+20h], r9d
0x180021167  mov     [rax+18h], r8d
0x18002116b  mov     [rax+10h], rdx
0x18002116f  push    rbp
0x180021170  push    rbx
0x180021171  push    rdi
0x180021172  lea     rbp, [rax-228h]
0x180021179  sub     rsp, 310h
0x180021180  mov     rax, cs:__security_cookie
0x180021187  xor     rax, rsp
0x18002118a  mov     [rbp+220h+var_20], rax
0x180021191  mov     rax, [rbp+220h+arg_30]
0x180021198  lea     rdx, aCreatefile2pro; "CreateFile2ProxyActivity"
0x18002119f  mov     edi, ecx
0x1800211a1  mov     [rsp+320h+var_300], rax
0x1800211a6  lea     rcx, [rbp+220h+var_170]; struct wil::details::IFailureCallback *
0x1800211ad  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800211b2  lea     rbx, ??_7CreateFile2ProxyActivity@TraceProvider@@6B@; const TraceProvider::CreateFile2ProxyActivity::`vftable'
0x1800211b9  lea     rcx, [rbp+220h+var_170]; this
0x1800211c0  mov     [rbp+220h+var_170], rbx
0x1800211c7  call    ?StartActivity@CreateFile2ProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::CreateFile2ProxyActivity::StartActivity(void)
0x1800211cc  mov     rax, [rsp+320h+var_300]
0x1800211d1  lea     rdx, [rbp+220h+var_170]
0x1800211d8  lea     rcx, [rsp+320h+var_2F0]
0x1800211dd  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800211e4  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800211e9  lea     rax, [rbp+220h+arg_8]
0x1800211f0  mov     qword ptr [rsp+320h+var_2F0], rbx
0x1800211f5  mov     [rbp+220h+var_1A0], rax
0x1800211fc  lea     rax, [rbp+220h+arg_28]
0x180021203  mov     [rbp+220h+var_198], rax
0x18002120a  lea     rax, [rbp+220h+arg_10]
0x180021211  mov     [rbp+220h+var_190], rax
0x180021218  lea     rax, [rbp+220h+arg_18]
0x18002121f  mov     [rbp+220h+var_188], rax
0x180021226  lea     rax, [rbp+220h+arg_20]
0x18002122d  mov     [rbp+220h+var_180], rax
0x180021234  lea     rax, [rsp+320h+var_300]
0x180021239  mov     [rbp+220h+var_178], rax
0x180021240  call    cs:__imp_GetCurrentThreadId
0x180021246  mov     edx, eax
0x180021248  lea     r8, [rsp+320h+var_2F0]
0x18002124d  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_6aece9f498c1836e6b49856eae513237___
0x180021252  lea     rcx, [rsp+320h+var_2F0]; this
0x180021257  mov     ebx, eax
0x180021259  call    ??1CreateFile2ProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateFile2ProxyActivity::~CreateFile2ProxyActivity(void)
0x18002125e  mov     edx, ebx
0x180021260  lea     rcx, [rbp+220h+var_170]
0x180021267  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002126c  mov     r8d, edi; int
0x18002126f  lea     rcx, aBrokeredcreate_2; "BrokeredCreateFile2"
0x180021276  mov     edx, ebx; int
0x180021278  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x18002127d  mov     edx, edi
0x18002127f  mov     ecx, ebx
0x180021281  call    _anonymous_namespace___HResultToWin32IfPossible
0x180021286  lea     rcx, [rbp+220h+var_170]; this
0x18002128d  mov     ebx, eax
0x18002128f  call    ??1CreateFile2ProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::CreateFile2ProxyActivity::~CreateFile2ProxyActivity(void)
0x180021294  mov     eax, ebx
0x180021296  mov     rcx, [rbp+220h+var_20]
0x18002129d  xor     rcx, rsp; StackCookie
0x1800212a0  call    __security_check_cookie
0x1800212a5  add     rsp, 310h
0x1800212ac  pop     rdi
0x1800212ad  pop     rbx
0x1800212ae  pop     rbp
0x1800212af  retn
```
