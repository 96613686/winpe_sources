# TelemetryLogger::`vector deleting destructor'(uint)

- ea: `0x180014980`
- end: `0x180014a51`
- name: `??_ETelemetryLogger@@EEAAPEAXI@Z`
- size: `209`
- prototype: `TelemetryLogger *__fastcall(TelemetryLogger *this, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x1800067c0`
- `0x180014980`
- `0x180014a60`
- `0x180014f00`
- `0x180015090`
- `0x18004c090`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1800149df`
- `KERNEL32!SetThreadpoolTimer` at `0x1800149df`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800149f6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800149f6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800149ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800149ed`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180014a25`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180014a25`

## pseudocode

```c
TelemetryLogger *__fastcall TelemetryLogger::`vector deleting destructor'(TelemetryLogger *this, char a2)
{
  _DWORD *v4; // rcx
  TelemetryLogger *v5; // rax
  struct _TP_TIMER *v6; // rdi
  __int64 v7; // rax
  REGHANDLE v8; // rcx

  *(_QWORD *)this = &TelemetryLogger::`vftable';
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    0);
  v4 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
  if ( v4 && *v4 )
  {
    v5 = TelemetryLogger::Instance();
    TelemetryLogger::FireEvent_(v5);
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v6 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 8), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v6, 1);
    CloseThreadpoolTimer(v6);
  }
  std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>((char *)this + 32);
  *(_QWORD *)this = &wil::TraceLoggingProvider::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v7 = *((_QWORD *)this + 1);
    v8 = *(_QWORD *)(v7 + 32);
    *(_DWORD *)v7 = 0;
    *(_QWORD *)(v7 + 32) = 0;
    EventUnregister(v8);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180014980  mov     [rsp+arg_0], rbx
0x180014985  mov     [rsp+arg_8], rsi
0x18001498a  push    rdi
0x18001498b  sub     rsp, 20h
0x18001498f  mov     esi, edx
0x180014991  mov     rbx, rcx
0x180014994  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x18001499b  mov     [rcx], rax
0x18001499e  xor     edx, edx
0x1800149a0  add     rcx, 40h ; '@'
0x1800149a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800149a9  nop
0x1800149aa  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800149af  mov     rcx, [rax+8]
0x1800149b3  test    rcx, rcx
0x1800149b6  jz      short loc_1800149CB
0x1800149b8  cmp     dword ptr [rcx], 0
0x1800149bb  jbe     short loc_1800149CB
0x1800149bd  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800149c2  mov     rcx, rax; this
0x1800149c5  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x1800149ca  nop
0x1800149cb  mov     rdi, [rbx+40h]
0x1800149cf  test    rdi, rdi
0x1800149d2  jz      short loc_1800149FC
0x1800149d4  xor     r9d, r9d; msWindowLength
0x1800149d7  xor     r8d, r8d; msPeriod
0x1800149da  xor     edx, edx; pftDueTime
0x1800149dc  mov     rcx, rdi; pti
0x1800149df  call    cs:__imp_SetThreadpoolTimer
0x1800149e5  mov     edx, 1; fCancelPendingCallbacks
0x1800149ea  mov     rcx, rdi; pti
0x1800149ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800149f3  mov     rcx, rdi; pti
0x1800149f6  call    cs:__imp_CloseThreadpoolTimer
0x1800149fc  lea     rcx, [rbx+20h]
0x180014a00  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x180014a05  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180014a0c  mov     [rbx], rax
0x180014a0f  cmp     byte ptr [rbx+10h], 0
0x180014a13  jz      short loc_180014A2B
0x180014a15  mov     rax, [rbx+8]
0x180014a19  mov     rcx, [rax+20h]; RegHandle
0x180014a1d  xor     edx, edx
0x180014a1f  mov     [rax], edx
0x180014a21  mov     [rax+20h], rdx
0x180014a25  call    cs:__imp_EventUnregister
0x180014a2b  test    sil, 1
0x180014a2f  jz      short loc_180014A3E
0x180014a31  mov     edx, 50h ; 'P'; unsigned __int64
0x180014a36  mov     rcx, rbx; void *
0x180014a39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014a3e  mov     rax, rbx
0x180014a41  mov     rbx, [rsp+28h+arg_0]
0x180014a46  mov     rsi, [rsp+28h+arg_8]
0x180014a4b  add     rsp, 20h
0x180014a4f  pop     rdi
0x180014a50  retn
```
