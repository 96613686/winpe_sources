# MidiSrvTelemetryProvider::Instance(void)

- ea: `0x14000984c`
- end: `0x140009901`
- name: `?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct MidiSrvTelemetryProvider *(void)`
- caller_count: `137`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008b50`
- `0x14000a0cc`
- `0x14000b1f0`
- `0x14000b2b8`
- `0x14000b60c`
- `0x14000b970`
- `0x14000ba28`
- `0x14000bbbc`
- `0x14000bf9c`
- `0x14000ce08`
- `0x140010068`
- `0x1400113b8`
- `0x140014ad0`
- `0x140015020`
- `0x1400152d0`
- `0x140016484`
- `0x140017404`
- `0x140017838`
- `0x140017f94`
- `0x1400182d4`
- `0x140018770`
- `0x140018f54`
- `0x1400193c4`
- `0x140019aac`
- `0x14001a084`
- `0x14001a680`
- `0x14001b6f8`
- `0x14001ba58`
- `0x14001bc60`
- `0x14001bf60`
- `0x14001ce50`
- `0x14001d7c8`
- `0x14001fe88`
- `0x140021310`
- `0x140021470`
- `0x140023398`
- `0x140023678`
- `0x1400238a4`
- `0x140024010`
- `0x1400244a0`
- `0x140024500`
- `0x14002455c`
- `0x140025050`
- `0x140025258`
- `0x140025978`
- `0x140026018`
- `0x140029640`
- `0x14002b1a0`
- `0x14002c6b0`
- `0x14002ce1c`

## callees

- `0x140005848`
- `0x14000984c`
- `0x140009e74`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140009874`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140009874`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400098f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400098f0`

## pseudocode

```c
struct MidiSrvTelemetryProvider *MidiSrvTelemetryProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`MidiSrvTelemetryProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_1400968C8 = 0;
    v3 = &qword_1400968C0;
    qword_1400968C0 = &MidiSrvTelemetryProvider::`vftable';
    byte_1400968D0 = 0;
    dword_1400968D4 = 0;
    qword_1400968D8 = (struct _tlgProvider_t *)&`MidiSrvTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`MidiSrvTelemetryProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1400968C0, qword_1400968D8, v0);
    InitOnceComplete(&`MidiSrvTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_1400968C0);
  }
  return (struct MidiSrvTelemetryProvider *)v3;
}

```

## disassembly

```asm
0x14000984c  mov     rax, rsp
0x14000984f  push    rbx
0x140009850  sub     rsp, 20h
0x140009854  lea     r9, [rax+10h]; lpContext
0x140009858  mov     qword ptr [rax+10h], 0
0x140009860  lea     r8, [rax+8]; fPending
0x140009864  mov     dword ptr [rax+8], 0
0x14000986b  xor     edx, edx; dwFlags
0x14000986d  lea     rcx, ?wrapper@?1??Instance@MidiSrvTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiSrvTelemetryProvider@@@details@wil@@A; lpInitOnce
0x140009874  call    cs:__imp_InitOnceBeginInitialize
0x14000987a  test    eax, eax
0x14000987c  jz      short loc_1400098F6
0x14000987e  cmp     [rsp+28h+arg_0], 0
0x140009883  jz      short loc_1400098F6
0x140009885  lea     rbx, qword_1400968C0
0x14000988c  mov     cs:qword_1400968C8, 0
0x140009897  lea     rax, ??_7MidiSrvTelemetryProvider@@6B@; const MidiSrvTelemetryProvider::`vftable'
0x14000989e  mov     [rsp+28h+arg_8], rbx
0x1400098a3  mov     cs:qword_1400968C0, rax
0x1400098aa  mov     cs:byte_1400968D0, 0
0x1400098b1  mov     cs:dword_1400968D4, 0
0x1400098bb  lea     rax, ?__hInner@?1???0StaticHandle@MidiSrvTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MidiSrvTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1400098c2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@MidiSrvTelemetryProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x1400098c9  mov     cs:qword_1400968D8, rax
0x1400098d0  call    atexit
0x1400098d5  mov     rdx, cs:qword_1400968D8; struct _tlgProvider_t *
0x1400098dc  mov     rcx, rbx; this
0x1400098df  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1400098e4  mov     r8, rbx; lpContext
0x1400098e7  lea     rcx, ?wrapper@?1??Instance@MidiSrvTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VMidiSrvTelemetryProvider@@@details@wil@@A; lpInitOnce
0x1400098ee  xor     edx, edx; dwFlags
0x1400098f0  call    cs:__imp_InitOnceComplete
0x1400098f6  mov     rax, [rsp+28h+arg_8]
0x1400098fb  add     rsp, 20h
0x1400098ff  pop     rbx
0x140009900  retn
```
