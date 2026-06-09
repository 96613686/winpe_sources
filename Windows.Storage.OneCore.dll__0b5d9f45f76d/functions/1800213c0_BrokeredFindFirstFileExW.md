# BrokeredFindFirstFileExW

- ea: `0x1800213c0`
- end: `0x1800214f4`
- name: `BrokeredFindFirstFileExW`
- size: `308`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char, char, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002be0`
- `0x18000c764`
- `0x18000f224`
- `0x18001b97c`
- `0x18001c174`
- `0x18001c60c`
- `0x18001eb38`
- `0x18001ec14`
- `0x18001f1d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021484`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021484`

## string_xrefs

- `0x1800214b3`: `BrokeredFindFirstFileEx`

## pseudocode

```c
__int64 BrokeredFindFirstFileExW(unsigned int a1, __int64 a2, int a3, ...)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  _QWORD v9[48]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v10[42]; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v11; // [rsp+330h] [rbp+228h] BYREF
  int v12; // [rsp+338h] [rbp+230h] BYREF
  __int64 v13; // [rsp+340h] [rbp+238h] BYREF
  va_list va; // [rsp+340h] [rbp+238h]
  __int64 v15; // [rsp+348h] [rbp+240h] BYREF
  va_list va1; // [rsp+348h] [rbp+240h]
  __int64 v17; // [rsp+350h] [rbp+248h] BYREF
  va_list va2; // [rsp+350h] [rbp+248h]
  va_list va3; // [rsp+358h] [rbp+250h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v17 = va_arg(va3, _QWORD);
  v12 = a3;
  v11 = a2;
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (struct wil::details::IFailureCallback *)v10,
    (__int64)"FindFirstFileExProxyActivity");
  v10[0] = &TraceProvider::FindFirstFileExProxyActivity::`vftable';
  TraceProvider::FindFirstFileExProxyActivity::StartActivity((TraceProvider::FindFirstFileExProxyActivity *)v10);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)v10);
  v9[0] = &TraceProvider::FindFirstFileExProxyActivity::`vftable';
  v9[42] = &v11;
  v9[43] = &v12;
  va_copy((va_list)&v9[44], va1);
  va_copy((va_list)&v9[45], va2);
  va_copy((va_list)&v9[46], va);
  va_copy((va_list)&v9[47], va3);
  CurrentThreadId = GetCurrentThreadId();
  v6 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA__lambda_5b2cb0125494a185df564e0f90df558f___(
         v5,
         CurrentThreadId,
         v9);
  TraceProvider::FindFirstFileExProxyActivity::~FindFirstFileExProxyActivity((TraceProvider::FindFirstFileExProxyActivity *)v9);
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10, v6);
  AggregateTraceUtil::LogApiCallResult(L"BrokeredFindFirstFileEx", v6, a1);
  v7 = anonymous_namespace_::HResultToWin32IfPossible(v6, a1);
  TraceProvider::FindFirstFileExProxyActivity::~FindFirstFileExProxyActivity((TraceProvider::FindFirstFileExProxyActivity *)v10);
  return v7;
}

```

## disassembly

```asm
0x1800213c0  mov     rax, rsp
0x1800213c3  mov     [rax+20h], r9
0x1800213c7  mov     [rax+18h], r8d
0x1800213cb  mov     [rax+10h], rdx
0x1800213cf  push    rbp
0x1800213d0  push    rbx
0x1800213d1  push    rdi
0x1800213d2  lea     rbp, [rax-218h]
0x1800213d9  sub     rsp, 300h
0x1800213e0  mov     rax, cs:__security_cookie
0x1800213e7  xor     rax, rsp
0x1800213ea  mov     [rbp+210h+var_20], rax
0x1800213f1  mov     edi, ecx
0x1800213f3  lea     rdx, aFindfirstfilee_0; "FindFirstFileExProxyActivity"
0x1800213fa  lea     rcx, [rbp+210h+var_170]; struct wil::details::IFailureCallback *
0x180021401  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180021406  lea     rbx, ??_7FindFirstFileExProxyActivity@TraceProvider@@6B@; const TraceProvider::FindFirstFileExProxyActivity::`vftable'
0x18002140d  lea     rcx, [rbp+210h+var_170]; this
0x180021414  mov     [rbp+210h+var_170], rbx
0x18002141b  call    ?StartActivity@FindFirstFileExProxyActivity@TraceProvider@@QEAAXXZ; TraceProvider::FindFirstFileExProxyActivity::StartActivity(void)
0x180021420  lea     rdx, [rbp+210h+var_170]
0x180021427  lea     rcx, [rsp+310h+var_2F0]
0x18002142c  call    ??0?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x180021431  lea     rax, [rbp+210h+arg_8]
0x180021438  mov     qword ptr [rsp+310h+var_2F0], rbx
0x18002143d  mov     [rbp+210h+var_1A0], rax
0x180021441  lea     rax, [rbp+210h+arg_10]
0x180021448  mov     [rbp+210h+var_198], rax
0x18002144c  lea     rax, [rbp+210h+arg_20]
0x180021453  mov     [rbp+210h+var_190], rax
0x18002145a  lea     rax, [rbp+210h+arg_28]
0x180021461  mov     [rbp+210h+var_188], rax
0x180021468  lea     rax, [rbp+210h+arg_18]
0x18002146f  mov     [rbp+210h+var_180], rax
0x180021476  lea     rax, [rbp+210h+arg_30]
0x18002147d  mov     [rbp+210h+var_178], rax
0x180021484  call    cs:__imp_GetCurrentThreadId
0x18002148a  mov     edx, eax
0x18002148c  lea     r8, [rsp+310h+var_2F0]
0x180021491  call    Windows__Internal__ComTaskPool__RunSynchronousTaskOnMTA__lambda_5b2cb0125494a185df564e0f90df558f___
0x180021496  lea     rcx, [rsp+310h+var_2F0]; this
0x18002149b  mov     ebx, eax
0x18002149d  call    ??1FindFirstFileExProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::FindFirstFileExProxyActivity::~FindFirstFileExProxyActivity(void)
0x1800214a2  mov     edx, ebx
0x1800214a4  lea     rcx, [rbp+210h+var_170]
0x1800214ab  call    ?Stop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800214b0  mov     r8d, edi; int
0x1800214b3  lea     rcx, aBrokeredfindfi_0; "BrokeredFindFirstFileEx"
0x1800214ba  mov     edx, ebx; int
0x1800214bc  call    ?LogApiCallResult@AggregateTraceUtil@@SAXPEBGJJ@Z; AggregateTraceUtil::LogApiCallResult(ushort const *,long,long)
0x1800214c1  mov     edx, edi
0x1800214c3  mov     ecx, ebx
0x1800214c5  call    _anonymous_namespace___HResultToWin32IfPossible
0x1800214ca  lea     rcx, [rbp+210h+var_170]; this
0x1800214d1  mov     ebx, eax
0x1800214d3  call    ??1FindFirstFileExProxyActivity@TraceProvider@@QEAA@XZ; TraceProvider::FindFirstFileExProxyActivity::~FindFirstFileExProxyActivity(void)
0x1800214d8  mov     eax, ebx
0x1800214da  mov     rcx, [rbp+210h+var_20]
0x1800214e1  xor     rcx, rsp; StackCookie
0x1800214e4  call    __security_check_cookie
0x1800214e9  add     rsp, 300h
0x1800214f0  pop     rdi
0x1800214f1  pop     rbx
0x1800214f2  pop     rbp
0x1800214f3  retn
```
