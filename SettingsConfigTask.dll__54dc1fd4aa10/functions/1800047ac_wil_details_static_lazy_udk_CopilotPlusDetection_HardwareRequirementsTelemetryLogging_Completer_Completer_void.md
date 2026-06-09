# wil::details::static_lazy<udk::CopilotPlusDetection::HardwareRequirementsTelemetryLogging>::Completer::~Completer(void)

- ea: `0x1800047ac`
- end: `0x1800047e1`
- name: `??1Completer@?$static_lazy@VHardwareRequirementsTelemetryLogging@CopilotPlusDetection@udk@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b170`
- `0x18001ecfc`
- `0x18001edbc`

## callees

- `0x1800047ac`
- `0x180008d08`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800047da`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<udk::CopilotPlusDetection::HardwareRequirementsTelemetryLogging>::Completer::~Completer(
        _DWORD *a1,
        __int64 a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  if ( !a1[2] )
    wil::TraceLoggingProvider::Register(
      (wil::TraceLoggingProvider *)(*(_QWORD *)a1 + 8LL),
      *(const struct _tlgProvider_t *const *)(*(_QWORD *)a1 + 32LL),
      a3);
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1800047ac  push    rbx
0x1800047ae  sub     rsp, 20h
0x1800047b2  cmp     dword ptr [rcx+8], 0
0x1800047b6  mov     rbx, rcx
0x1800047b9  jnz     short loc_1800047CB
0x1800047bb  mov     rcx, [rcx]
0x1800047be  add     rcx, 8; this
0x1800047c2  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x1800047c6  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800047cb  mov     rcx, [rbx]
0x1800047ce  mov     edx, [rbx+8]
0x1800047d1  lea     r8, [rcx+8]
0x1800047d5  add     rsp, 20h
0x1800047d9  pop     rbx
0x1800047da  jmp     cs:__imp_InitOnceComplete
```
