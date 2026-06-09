# _lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_(void)

- ea: `0x18002f7b0`
- end: `0x18002f8ac`
- name: `?_lambda_invoker_cdecl_@_lambda_d0de0aea0d9e121ad3b76698eff7e035_@@CA@XZ`
- size: `252`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000f590`
- `0x18002f6a0`
- `0x18002f7b0`
- `0x18002fa00`
- `0x180030020`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18002f7df`
- `KERNEL32!InitOnceBeginInitialize` at `0x18002f7df`
- `KERNEL32!SetThreadpoolTimer` at `0x18002f848`
- `KERNEL32!SetThreadpoolTimer` at `0x18002f848`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002f85f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002f85f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002f856`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002f856`
- `ADVAPI32!EventUnregister` at `0x18002f88e`
- `ADVAPI32!EventUnregister` at `0x18002f88e`

## pseudocode

```c
void __fastcall _lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_()
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
0x18002f7b0  mov     [rsp+arg_0], rbx
0x18002f7b5  push    rdi
0x18002f7b6  sub     rsp, 40h
0x18002f7ba  mov     rax, cs:__security_cookie
0x18002f7c1  xor     rax, rsp
0x18002f7c4  mov     [rsp+48h+var_18], rax
0x18002f7c9  lea     r9, [rsp+48h+Context]; lpContext
0x18002f7ce  lea     r8, [rsp+48h+fPending]; fPending
0x18002f7d3  mov     edx, 1; dwFlags
0x18002f7d8  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18002f7df  call    cs:__imp_InitOnceBeginInitialize
0x18002f7e5  test    eax, eax
0x18002f7e7  jz      loc_18002F894
0x18002f7ed  cmp     [rsp+48h+fPending], 0
0x18002f7f2  jnz     loc_18002F894
0x18002f7f8  mov     rbx, [rsp+48h+Context]
0x18002f7fd  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x18002f804  mov     [rbx], rax
0x18002f807  xor     edx, edx
0x18002f809  lea     rcx, [rbx+40h]
0x18002f80d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002f812  nop
0x18002f813  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18002f818  mov     rcx, [rax+8]
0x18002f81c  test    rcx, rcx
0x18002f81f  jz      short loc_18002F834
0x18002f821  cmp     dword ptr [rcx], 0
0x18002f824  jbe     short loc_18002F834
0x18002f826  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18002f82b  mov     rcx, rax; this
0x18002f82e  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x18002f833  nop
0x18002f834  mov     rdi, [rbx+40h]
0x18002f838  test    rdi, rdi
0x18002f83b  jz      short loc_18002F865
0x18002f83d  xor     r9d, r9d; msWindowLength
0x18002f840  xor     r8d, r8d; msPeriod
0x18002f843  xor     edx, edx; pftDueTime
0x18002f845  mov     rcx, rdi; pti
0x18002f848  call    cs:__imp_SetThreadpoolTimer
0x18002f84e  mov     edx, 1; fCancelPendingCallbacks
0x18002f853  mov     rcx, rdi; pti
0x18002f856  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002f85c  mov     rcx, rdi; pti
0x18002f85f  call    cs:__imp_CloseThreadpoolTimer
0x18002f865  lea     rcx, [rbx+20h]
0x18002f869  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x18002f86e  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18002f875  mov     [rbx], rax
0x18002f878  cmp     byte ptr [rbx+10h], 0
0x18002f87c  jz      short loc_18002F894
0x18002f87e  mov     rax, [rbx+8]
0x18002f882  mov     rcx, [rax+20h]; RegHandle
0x18002f886  xor     edx, edx
0x18002f888  mov     [rax], edx
0x18002f88a  mov     [rax+20h], rdx
0x18002f88e  call    cs:__imp_EventUnregister
0x18002f894  mov     rcx, [rsp+48h+var_18]
0x18002f899  xor     rcx, rsp; StackCookie
0x18002f89c  call    __security_check_cookie
0x18002f8a1  mov     rbx, [rsp+48h+arg_0]
0x18002f8a6  add     rsp, 40h
0x18002f8aa  pop     rdi
0x18002f8ab  retn
```
