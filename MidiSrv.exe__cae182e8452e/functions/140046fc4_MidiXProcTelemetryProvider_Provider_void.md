# MidiXProcTelemetryProvider::Provider(void)

- ea: `0x140046fc4`
- end: `0x14004707d`
- name: `?Provider@MidiXProcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140046c8c`
- `0x140047258`
- `0x140047c20`

## callees

- `0x140005848`
- `0x140009e74`
- `0x140046fc4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140046fec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140046fec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140047068`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140047068`

## pseudocode

```c
const struct _tlgProvider_t *MidiXProcTelemetryProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_140096DA8 = 0;
    v3 = &qword_140096DA0;
    qword_140096DA0 = &MidiSrvTelemetryProvider::`vftable';
    byte_140096DB0 = 0;
    dword_140096DB4 = 0;
    qword_140096DB8 = (struct _tlgProvider_t *)&`MidiXProcTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiXProcTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140096DA0, qword_140096DB8, v0);
    InitOnceComplete(&`MidiXProcTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_140096DA0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x140046fc4  mov     rax, rsp
0x140046fc7  push    rbx
0x140046fc8  sub     rsp, 20h
0x140046fcc  lea     r9, [rax+10h]; lpContext
0x140046fd0  mov     qword ptr [rax+10h], 0
0x140046fd8  lea     r8, [rax+8]; fPending
0x140046fdc  mov     dword ptr [rax+8], 0
0x140046fe3  xor     edx, edx; dwFlags
0x140046fe5  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x140046fec  call    cs:__imp_InitOnceBeginInitialize
0x140046ff2  test    eax, eax
0x140046ff4  jz      short loc_14004706E
0x140046ff6  cmp     [rsp+28h+arg_0], 0
0x140046ffb  jz      short loc_14004706E
0x140046ffd  lea     rbx, qword_140096DA0
0x140047004  mov     cs:qword_140096DA8, 0
0x14004700f  lea     rax, ??_7MidiSrvTelemetryProvider@@6B@; const MidiSrvTelemetryProvider::`vftable'
0x140047016  mov     [rsp+28h+arg_8], rbx
0x14004701b  mov     cs:qword_140096DA0, rax
0x140047022  mov     cs:byte_140096DB0, 0
0x140047029  mov     cs:dword_140096DB4, 0
0x140047033  lea     rax, ?__hInner@?1???0StaticHandle@MidiXProcTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiXProcTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14004703a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x140047041  mov     cs:qword_140096DB8, rax
0x140047048  call    atexit
0x14004704d  mov     rdx, cs:qword_140096DB8; struct _tlgProvider_t *
0x140047054  mov     rcx, rbx; this
0x140047057  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14004705c  mov     r8, rbx; lpContext
0x14004705f  lea     rcx, ?wrapper@?1??Instance@MidiXProcTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiXProcTelemetryProvider@@@details@wil@@A; lpInitOnce
0x140047066  xor     edx, edx; dwFlags
0x140047068  call    cs:__imp_InitOnceComplete
0x14004706e  mov     rax, [rsp+28h+arg_8]
0x140047073  mov     rax, [rax+8]
0x140047077  add     rsp, 20h
0x14004707b  pop     rbx
0x14004707c  retn
```
