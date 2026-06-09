# _lambda_d0de0aea0d9e121ad3b76698eff7e035_::_lambda_invoker_cdecl_(void)

- ea: `0x1800115f0`
- end: `0x1800116ec`
- name: `?_lambda_invoker_cdecl_@_lambda_d0de0aea0d9e121ad3b76698eff7e035_@@CA@XZ`
- size: `252`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800110c0`
- `0x180011560`
- `0x1800115f0`
- `0x1800116f0`
- `0x180012de0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180011688`
- `KERNEL32!SetThreadpoolTimer` at `0x180011688`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001169f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001169f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180011696`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180011696`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001161f`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001161f`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800116ce`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800116ce`

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
0x1800115f0  mov     [rsp+arg_0], rbx
0x1800115f5  push    rdi
0x1800115f6  sub     rsp, 40h
0x1800115fa  mov     rax, cs:__security_cookie
0x180011601  xor     rax, rsp
0x180011604  mov     [rsp+48h+var_18], rax
0x180011609  lea     r9, [rsp+48h+Context]; lpContext
0x18001160e  lea     r8, [rsp+48h+fPending]; fPending
0x180011613  mov     edx, 1; dwFlags
0x180011618  lea     rcx, ?wrapper@?1??Instance@TelemetryLogger@@KAPEAV2@XZ@4V?$static_lazy@VTelemetryLogger@@@details@wil@@A; lpInitOnce
0x18001161f  call    cs:__imp_InitOnceBeginInitialize
0x180011625  test    eax, eax
0x180011627  jz      loc_1800116D4
0x18001162d  cmp     [rsp+48h+fPending], 0
0x180011632  jnz     loc_1800116D4
0x180011638  mov     rbx, [rsp+48h+Context]
0x18001163d  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x180011644  mov     [rbx], rax
0x180011647  xor     edx, edx
0x180011649  lea     rcx, [rbx+40h]
0x18001164d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011652  nop
0x180011653  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180011658  mov     rcx, [rax+8]
0x18001165c  test    rcx, rcx
0x18001165f  jz      short loc_180011674
0x180011661  cmp     dword ptr [rcx], 0
0x180011664  jbe     short loc_180011674
0x180011666  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18001166b  mov     rcx, rax; this
0x18001166e  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x180011673  nop
0x180011674  mov     rdi, [rbx+40h]
0x180011678  test    rdi, rdi
0x18001167b  jz      short loc_1800116A5
0x18001167d  xor     r9d, r9d; msWindowLength
0x180011680  xor     r8d, r8d; msPeriod
0x180011683  xor     edx, edx; pftDueTime
0x180011685  mov     rcx, rdi; pti
0x180011688  call    cs:__imp_SetThreadpoolTimer
0x18001168e  mov     edx, 1; fCancelPendingCallbacks
0x180011693  mov     rcx, rdi; pti
0x180011696  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001169c  mov     rcx, rdi; pti
0x18001169f  call    cs:__imp_CloseThreadpoolTimer
0x1800116a5  lea     rcx, [rbx+20h]
0x1800116a9  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x1800116ae  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x1800116b5  mov     [rbx], rax
0x1800116b8  cmp     byte ptr [rbx+10h], 0
0x1800116bc  jz      short loc_1800116D4
0x1800116be  mov     rax, [rbx+8]
0x1800116c2  mov     rcx, [rax+20h]; RegHandle
0x1800116c6  xor     edx, edx
0x1800116c8  mov     [rax], edx
0x1800116ca  mov     [rax+20h], rdx
0x1800116ce  call    cs:__imp_EventUnregister
0x1800116d4  mov     rcx, [rsp+48h+var_18]
0x1800116d9  xor     rcx, rsp; StackCookie
0x1800116dc  call    __security_check_cookie
0x1800116e1  mov     rbx, [rsp+48h+arg_0]
0x1800116e6  add     rsp, 40h
0x1800116ea  pop     rdi
0x1800116eb  retn
```
