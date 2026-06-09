# `TelemetryLogger::Instance(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void)

- ea: `0x180014f90`
- end: `0x18001508c`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@TelemetryLogger@@KAPEAV3@XZ@SA@XZ`
- size: `252`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800067c0`
- `0x180014a60`
- `0x180014f00`
- `0x180014f90`
- `0x180015090`
- `0x18004c070`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180015028`
- `KERNEL32!SetThreadpoolTimer` at `0x180015028`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001503f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001503f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180015036`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180015036`
- `KERNEL32!InitOnceBeginInitialize` at `0x180014fbf`
- `KERNEL32!InitOnceBeginInitialize` at `0x180014fbf`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001506e`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001506e`

## pseudocode

```c
void __fastcall `TelemetryLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_()
{
  char *v0; // rbx
  _DWORD *v1; // rcx
  TelemetryLogger *v2; // rax
  struct _TP_TIMER *v3; // rdi
  __int64 v4; // rax
  REGHANDLE v5; // rcx
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  if ( InitOnceBeginInitialize(&`TelemetryLogger::Instance'::`2'::wrapper, 1u, &fPending, &Context) && !fPending )
  {
    v0 = (char *)Context;
    *(_QWORD *)Context = &TelemetryLogger::`vftable';
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v0 + 64,
      0);
    v1 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( v1 && *v1 )
    {
      v2 = TelemetryLogger::Instance();
      TelemetryLogger::FireEvent_(v2);
    }
    v3 = (struct _TP_TIMER *)*((_QWORD *)v0 + 8);
    if ( v3 )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)v0 + 8), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v3, 1);
      CloseThreadpoolTimer(v3);
    }
    std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(v0 + 32);
    *(_QWORD *)v0 = &wil::TraceLoggingProvider::`vftable';
    if ( v0[16] )
    {
      v4 = *((_QWORD *)v0 + 1);
      v5 = *(_QWORD *)(v4 + 32);
      *(_DWORD *)v4 = 0;
      *(_QWORD *)(v4 + 32) = 0;
      EventUnregister(v5);
    }
  }
}

```

## disassembly

```asm
0x180014f90  mov     [rsp+arg_0], rbx
0x180014f95  push    rdi
0x180014f96  sub     rsp, 40h
0x180014f9a  mov     rax, cs:__security_cookie
0x180014fa1  xor     rax, rsp
0x180014fa4  mov     [rsp+48h+var_18], rax
0x180014fa9  lea     r9, [rsp+48h+Context]; lpContext
0x180014fae  lea     r8, [rsp+48h+fPending]; fPending
0x180014fb3  mov     edx, 1; dwFlags
0x180014fb8  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x180014fbf  call    cs:__imp_InitOnceBeginInitialize
0x180014fc5  test    eax, eax
0x180014fc7  jz      loc_180015074
0x180014fcd  cmp     [rsp+48h+fPending], 0
0x180014fd2  jnz     loc_180015074
0x180014fd8  mov     rbx, [rsp+48h+Context]
0x180014fdd  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x180014fe4  mov     [rbx], rax
0x180014fe7  xor     edx, edx
0x180014fe9  lea     rcx, [rbx+40h]
0x180014fed  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180014ff2  nop
0x180014ff3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180014ff8  mov     rcx, [rax+8]
0x180014ffc  test    rcx, rcx
0x180014fff  jz      short loc_180015014
0x180015001  cmp     dword ptr [rcx], 0
0x180015004  jbe     short loc_180015014
0x180015006  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18001500b  mov     rcx, rax; this
0x18001500e  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x180015013  nop
0x180015014  mov     rdi, [rbx+40h]
0x180015018  test    rdi, rdi
0x18001501b  jz      short loc_180015045
0x18001501d  xor     r9d, r9d; msWindowLength
0x180015020  xor     r8d, r8d; msPeriod
0x180015023  xor     edx, edx; pftDueTime
0x180015025  mov     rcx, rdi; pti
0x180015028  call    cs:__imp_SetThreadpoolTimer
0x18001502e  mov     edx, 1; fCancelPendingCallbacks
0x180015033  mov     rcx, rdi; pti
0x180015036  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001503c  mov     rcx, rdi; pti
0x18001503f  call    cs:__imp_CloseThreadpoolTimer
0x180015045  lea     rcx, [rbx+20h]
0x180015049  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x18001504e  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180015055  mov     [rbx], rax
0x180015058  cmp     byte ptr [rbx+10h], 0
0x18001505c  jz      short loc_180015074
0x18001505e  mov     rax, [rbx+8]
0x180015062  mov     rcx, [rax+20h]; RegHandle
0x180015066  xor     edx, edx
0x180015068  mov     [rax], edx
0x18001506a  mov     [rax+20h], rdx
0x18001506e  call    cs:__imp_EventUnregister
0x180015074  mov     rcx, [rsp+48h+var_18]
0x180015079  xor     rcx, rsp; StackCookie
0x18001507c  call    __security_check_cookie
0x180015081  mov     rbx, [rsp+48h+arg_0]
0x180015086  add     rsp, 40h
0x18001508a  pop     rdi
0x18001508b  retn
```
