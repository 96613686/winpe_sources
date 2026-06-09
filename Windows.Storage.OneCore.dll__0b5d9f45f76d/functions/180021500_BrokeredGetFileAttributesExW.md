# BrokeredGetFileAttributesExW

- ea: `0x180021500`
- end: `0x18002160a`
- name: `BrokeredGetFileAttributesExW`
- size: `266`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001bfb4`
- `0x18001c174`
- `0x18001c638`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002159a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002159a`

## string_xrefs

- `0x1800215c9`: `BrokeredGetFileAttributesEx`

## pseudocode

```c
__int64 BrokeredGetFileAttributesExW(unsigned int a1, __int64 a2, int a3, ...)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  _QWORD v9[46]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v10[42]; // [rsp+198h] [rbp+90h] BYREF
  __int64 v11; // [rsp+320h] [rbp+218h] BYREF
  int v12; // [rsp+328h] [rbp+220h] BYREF
  va_list va; // [rsp+330h] [rbp+228h] BYREF

  va_start(va, a3);
  v12 = a3;
  v11 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v10,
    (__int64)"GetFileAttributesExProxyActivity");
  v10[0] = &TraceProvider::GetFileAttributesExProxyActivity::`vftable';
  TraceProvider::GetFileAttributesExProxyActivity::StartActivity((TraceProvider::GetFileAttributesExProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)v10);
  v9[0] = &TraceProvider::GetFileAttributesExProxyActivity::`vftable';
  v9[42] = &v11;
  v9[43] = &v12;
  va_copy((va_list)&v9[44], va);
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___(
         v5,
         CurrentThreadId,
         v9);
  TraceProvider::GetFileAttributesExProxyActivity::~GetFileAttributesExProxyActivity((TraceProvider::GetFileAttributesExProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10, v6);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredGetFileAttributesEx", v6, a1);
  v7 = anonymous_namespace_::HResultToWin32IfPossible(v6, a1);
  TraceProvider::GetFileAttributesExProxyActivity::~GetFileAttributesExProxyActivity((TraceProvider::GetFileAttributesExProxyActivity *)v10);
  return v7;
}

```

## disassembly

```asm
0x180021500  mov     rax, rsp
0x180021503  mov     [rax+20h], r9
0x180021507  mov     [rax+18h], r8d
0x18002150b  mov     [rax+10h], rdx
0x18002150f  push    rbp
0x180021510  push    rbx
0x180021511  push    rdi
0x180021512  lea     rbp, [rax-208h]
0x180021519  sub     rsp, 2F0h
0x180021520  mov     rax, cs:__security_cookie
0x180021527  xor     rax, rsp
0x18002152a  mov     [rbp+200h+var_20], rax
0x180021531  mov     edi, ecx
0x180021533  lea     rdx, aGetfileattribu_0; "GetFileAttributesExProxyActivity"
0x18002153a  lea     rcx, [rbp+200h+var_170]; struct wil::details::IFailureCallback *
0x180021541  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021546  lea     rbx, ??_7GetFileAttributesExProxyActivity@TraceProvider@@6B@; const TraceProvider::GetFileAttributesExProxyActivity::`vftable'
0x18002154d  lea     rcx, [rbp+200h+var_170]; this
0x180021554  mov     [rbp+200h+var_170], rbx
0x18002155b  call    ?StartActivity@GetFileAttributesExProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::GetFileAttributesExProxyActivity::StartActivity(void)
0x180021560  lea     rdx, [rbp+200h+var_170]
0x180021567  lea     rcx, [rsp+300h+var_2E0]
0x18002156c  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021571  lea     rax, [rbp+200h+arg_8]
0x180021578  mov     qword ptr [rsp+300h+var_2E0], rbx
0x18002157d  mov     [rbp+200h+var_190], rax
0x180021581  lea     rax, [rbp+200h+arg_10]
0x180021588  mov     [rbp+200h+var_188], rax
0x18002158c  lea     rax, [rbp+200h+arg_18]
0x180021593  mov     [rbp+200h+var_180], rax
0x18002159a  call    cs:__imp_GetCurrentThreadId
0x1800215a0  mov     edx, eax
0x1800215a2  lea     r8, [rsp+300h+var_2E0]
0x1800215a7  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_b10ee6e6ef7c5de0120f1ae782ec39fd___
0x1800215ac  lea     rcx, [rsp+300h+var_2E0]; this
0x1800215b1  mov     ebx, eax
0x1800215b3  call    ??1GetFileAttributesExProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesExProxyActivity::~GetFileAttributesExProxyActivity(void)
0x1800215b8  mov     edx, ebx
0x1800215ba  lea     rcx, [rbp+200h+var_170]
0x1800215c1  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800215c6  mov     r8d, edi; int
0x1800215c9  lea     rcx, aBrokeredgetfil_1; "BrokeredGetFileAttributesEx"
0x1800215d0  mov     edx, ebx; int
0x1800215d2  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x1800215d7  mov     edx, edi
0x1800215d9  mov     ecx, ebx
0x1800215db  call    _anonymous_namespace___HResultToWin32IfPossible
0x1800215e0  lea     rcx, [rbp+200h+var_170]; this
0x1800215e7  mov     ebx, eax
0x1800215e9  call    ??1GetFileAttributesExProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::GetFileAttributesExProxyActivity::~GetFileAttributesExProxyActivity(void)
0x1800215ee  mov     eax, ebx
0x1800215f0  mov     rcx, [rbp+200h+var_20]
0x1800215f7  xor     rcx, rsp; StackCookie
0x1800215fa  call    __security_check_cookie
0x1800215ff  add     rsp, 2F0h
0x180021606  pop     rdi
0x180021607  pop     rbx
0x180021608  pop     rbp
0x180021609  retn
```
