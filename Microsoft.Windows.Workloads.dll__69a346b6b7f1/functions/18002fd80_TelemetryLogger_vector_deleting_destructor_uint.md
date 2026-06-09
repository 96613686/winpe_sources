# TelemetryLogger::`vector deleting destructor'(uint)

- ea: `0x18002fd80`
- end: `0x18002fe51`
- name: `??_ETelemetryLogger@@EEAAPEAXI@Z`
- size: `209`
- prototype: `TelemetryLogger *__fastcall(TelemetryLogger *this, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x18000f590`
- `0x18002f6a0`
- `0x18002fa00`
- `0x18002fd80`
- `0x180030020`
- `0x18003509c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18002fddf`
- `KERNEL32!SetThreadpoolTimer` at `0x18002fddf`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002fdf6`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002fdf6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002fded`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002fded`
- `ADVAPI32!EventUnregister` at `0x18002fe25`
- `ADVAPI32!EventUnregister` at `0x18002fe25`

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
0x18002fd80  mov     [rsp+arg_0], rbx
0x18002fd85  mov     [rsp+arg_8], rsi
0x18002fd8a  push    rdi
0x18002fd8b  sub     rsp, 20h
0x18002fd8f  mov     esi, edx
0x18002fd91  mov     rbx, rcx
0x18002fd94  lea     rax, ??_7TelemetryLogger@@6B@; const TelemetryLogger::`vftable'
0x18002fd9b  mov     [rcx], rax
0x18002fd9e  xor     edx, edx
0x18002fda0  add     rcx, 40h ; '@'
0x18002fda4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002fda9  nop
0x18002fdaa  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18002fdaf  mov     rcx, [rax+8]
0x18002fdb3  test    rcx, rcx
0x18002fdb6  jz      short loc_18002FDCB
0x18002fdb8  cmp     dword ptr [rcx], 0
0x18002fdbb  jbe     short loc_18002FDCB
0x18002fdbd  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18002fdc2  mov     rcx, rax; this
0x18002fdc5  call    ?FireEvent_@TelemetryLogger@@QEAAXXZ; TelemetryLogger::FireEvent_(void)
0x18002fdca  nop
0x18002fdcb  mov     rdi, [rbx+40h]
0x18002fdcf  test    rdi, rdi
0x18002fdd2  jz      short loc_18002FDFC
0x18002fdd4  xor     r9d, r9d; msWindowLength
0x18002fdd7  xor     r8d, r8d; msPeriod
0x18002fdda  xor     edx, edx; pftDueTime
0x18002fddc  mov     rcx, rdi; pti
0x18002fddf  call    cs:__imp_SetThreadpoolTimer
0x18002fde5  mov     edx, 1; fCancelPendingCallbacks
0x18002fdea  mov     rcx, rdi; pti
0x18002fded  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002fdf3  mov     rcx, rdi; pti
0x18002fdf6  call    cs:__imp_CloseThreadpoolTimer
0x18002fdfc  lea     rcx, [rbx+20h]
0x18002fe00  call    ??1?$vector@UApiData@ApiDataList@TelemetryLogger@@V?$allocator@UApiData@ApiDataList@TelemetryLogger@@@std@@@std@@QEAA@XZ; std::vector<TelemetryLogger::ApiDataList::ApiData>::~vector<TelemetryLogger::ApiDataList::ApiData>(void)
0x18002fe05  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18002fe0c  mov     [rbx], rax
0x18002fe0f  cmp     byte ptr [rbx+10h], 0
0x18002fe13  jz      short loc_18002FE2B
0x18002fe15  mov     rax, [rbx+8]
0x18002fe19  mov     rcx, [rax+20h]; RegHandle
0x18002fe1d  xor     edx, edx
0x18002fe1f  mov     [rax], edx
0x18002fe21  mov     [rax+20h], rdx
0x18002fe25  call    cs:__imp_EventUnregister
0x18002fe2b  test    sil, 1
0x18002fe2f  jz      short loc_18002FE3E
0x18002fe31  mov     edx, 50h ; 'P'; unsigned __int64
0x18002fe36  mov     rcx, rbx; void *
0x18002fe39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002fe3e  mov     rax, rbx
0x18002fe41  mov     rbx, [rsp+28h+arg_0]
0x18002fe46  mov     rsi, [rsp+28h+arg_8]
0x18002fe4b  add     rsp, 20h
0x18002fe4f  pop     rdi
0x18002fe50  retn
```
