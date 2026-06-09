# MidiKSAggregateTransportTelemetryProvider::Instance(void)

- ea: `0x1800117d8`
- end: `0x18001188d`
- name: `?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct MidiKSAggregateTransportTelemetryProvider *(void)`
- caller_count: `47`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800116a0`
- `0x1800124e0`
- `0x1800163a8`
- `0x1800188a8`
- `0x180018e30`
- `0x18001ab10`
- `0x18001af20`
- `0x18001b050`
- `0x18001d340`
- `0x18001dd50`
- `0x18001e500`
- `0x18001e790`
- `0x180023320`
- `0x180025070`
- `0x180025570`
- `0x180025ca0`
- `0x180027b50`
- `0x180027f90`
- `0x180028dd0`
- `0x180035960`
- `0x180035c78`
- `0x1800365e8`
- `0x180036d5c`
- `0x180037fec`
- `0x180038d30`
- `0x180039374`
- `0x18003966c`
- `0x180039928`
- `0x180039ef0`
- `0x18003b10c`
- `0x18003b408`
- `0x18003bf70`
- `0x18003c890`
- `0x18003dcf0`
- `0x18003ee80`
- `0x18003f810`
- `0x18003fc04`
- `0x18004003c`
- `0x180043c00`
- `0x180043eb4`
- `0x180044b18`
- `0x180045460`
- `0x1800456dc`
- `0x180045ce0`
- `0x180045e0c`
- `0x18005ac60`
- `0x18005ad32`

## callees

- `0x180005510`
- `0x1800117d8`
- `0x18001193c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011800`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011800`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001187c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001187c`

## pseudocode

```c
struct MidiKSAggregateTransportTelemetryProvider *MidiKSAggregateTransportTelemetryProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiKSAggregateTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180096E88 = 0;
    v3 = &qword_180096E80;
    qword_180096E80 = &MidiXProcTelemetryProvider::`vftable';
    byte_180096E90 = 0;
    dword_180096E94 = 0;
    qword_180096E98 = (struct _tlgProvider_t *)&`MidiKSAggregateTransportTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiKSAggregateTransportTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180096E80, qword_180096E98, v0);
    InitOnceComplete(&`MidiKSAggregateTransportTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180096E80);
  }
  return (struct MidiKSAggregateTransportTelemetryProvider *)v3;
}

```

## disassembly

```asm
0x1800117d8  mov     rax, rsp
0x1800117db  push    rbx
0x1800117dc  sub     rsp, 20h
0x1800117e0  lea     r9, [rax+10h]; lpContext
0x1800117e4  mov     qword ptr [rax+10h], 0
0x1800117ec  lea     r8, [rax+8]; fPending
0x1800117f0  mov     dword ptr [rax+8], 0
0x1800117f7  xor     edx, edx; dwFlags
0x1800117f9  lea     rcx, ?wrapper@?1??Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiKSAggregateTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180011800  call    cs:__imp_InitOnceBeginInitialize
0x180011806  test    eax, eax
0x180011808  jz      short loc_180011882
0x18001180a  cmp     [rsp+28h+arg_0], 0
0x18001180f  jz      short loc_180011882
0x180011811  lea     rbx, qword_180096E80
0x180011818  mov     cs:qword_180096E88, 0
0x180011823  lea     rax, ??_7MidiXProcTelemetryProvider@@6B@; const MidiXProcTelemetryProvider::`vftable'
0x18001182a  mov     [rsp+28h+arg_8], rbx
0x18001182f  mov     cs:qword_180096E80, rax
0x180011836  mov     cs:byte_180096E90, 0
0x18001183d  mov     cs:dword_180096E94, 0
0x180011847  lea     rax, ?__hInner@?1???0StaticHandle@MidiKSAggregateTransportTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiKSAggregateTransportTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001184e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180011855  mov     cs:qword_180096E98, rax
0x18001185c  call    atexit
0x180011861  mov     rdx, cs:qword_180096E98; struct _tlgProvider_t *
0x180011868  mov     rcx, rbx; this
0x18001186b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180011870  mov     r8, rbx; lpContext
0x180011873  lea     rcx, ?wrapper@?1??Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiKSAggregateTransportTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18001187a  xor     edx, edx; dwFlags
0x18001187c  call    cs:__imp_InitOnceComplete
0x180011882  mov     rax, [rsp+28h+arg_8]
0x180011887  add     rsp, 20h
0x18001188b  pop     rbx
0x18001188c  retn
```
