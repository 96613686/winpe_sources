# TelemetryLogger::`vector deleting destructor'(uint)

- ea: `0x180010fe0`
- end: `0x1800110b1`
- name: `??_ETelemetryLogger@@EEAAPEAXI@Z`
- size: `209`
- prototype: `TelemetryLogger *__fastcall(TelemetryLogger *this, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180010fe0`
- `0x1800110c0`
- `0x180011560`
- `0x1800116f0`
- `0x180012de0`
- `0x180018238`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001103f`
- `KERNEL32!SetThreadpoolTimer` at `0x18001103f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180011056`
- `KERNEL32!CloseThreadpoolTimer` at `0x180011056`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001104d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001104d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011085`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011085`

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
0x180010fe0  mov     [rsp+arg_0], rbx
0x180010fe5  mov     [rsp+arg_8], rsi
0x180010fea  push    rdi
0x180010feb  sub     rsp, 20h
0x180010fef  mov     esi, edx
0x180010ff1  mov     rbx, rcx
0x180010ff4  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x180010ffb  mov     [rcx], rax
0x180010ffe  xor     edx, edx
0x180011000  add     rcx, 40h ; '@'
0x180011004  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011009  nop
0x18001100a  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18001100f  mov     rcx, [rax+8]
0x180011013  test    rcx, rcx
0x180011016  jz      short loc_18001102B
0x180011018  cmp     dword ptr [rcx], 0
0x18001101b  jbe     short loc_18001102B
0x18001101d  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180011022  mov     rcx, rax; this
0x180011025  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x18001102a  nop
0x18001102b  mov     rdi, [rbx+40h]
0x18001102f  test    rdi, rdi
0x180011032  jz      short loc_18001105C
0x180011034  xor     r9d, r9d; msWindowLength
0x180011037  xor     r8d, r8d; msPeriod
0x18001103a  xor     edx, edx; pftDueTime
0x18001103c  mov     rcx, rdi; pti
0x18001103f  call    cs:__imp_SetThreadpoolTimer
0x180011045  mov     edx, 1; fCancelPendingCallbacks
0x18001104a  mov     rcx, rdi; pti
0x18001104d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011053  mov     rcx, rdi; pti
0x180011056  call    cs:__imp_CloseThreadpoolTimer
0x18001105c  lea     rcx, [rbx+20h]
0x180011060  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x180011065  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18001106c  mov     [rbx], rax
0x18001106f  cmp     byte ptr [rbx+10h], 0
0x180011073  jz      short loc_18001108B
0x180011075  mov     rax, [rbx+8]
0x180011079  mov     rcx, [rax+20h]; RegHandle
0x18001107d  xor     edx, edx
0x18001107f  mov     [rax], edx
0x180011081  mov     [rax+20h], rdx
0x180011085  call    cs:__imp_EventUnregister
0x18001108b  test    sil, 1
0x18001108f  jz      short loc_18001109E
0x180011091  mov     edx, 50h ; 'P'; unsigned __int64
0x180011096  mov     rcx, rbx; void *
0x180011099  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001109e  mov     rax, rbx
0x1800110a1  mov     rbx, [rsp+28h+arg_0]
0x1800110a6  mov     rsi, [rsp+28h+arg_8]
0x1800110ab  add     rsp, 20h
0x1800110af  pop     rdi
0x1800110b0  retn
```
