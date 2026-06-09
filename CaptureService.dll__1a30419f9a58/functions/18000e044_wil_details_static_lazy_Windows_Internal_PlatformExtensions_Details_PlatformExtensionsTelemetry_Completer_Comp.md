# wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::Completer::~Completer(void)

- ea: `0x18000e044`
- end: `0x18000e079`
- name: `??1Completer@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017fb8`
- `0x180018078`

## callees

- `0x18000e044`
- `0x1800139f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e072`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
BOOL __fastcall wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::Completer::~Completer(
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
0x18000e044  push    rbx
0x18000e046  sub     rsp, 20h
0x18000e04a  cmp     dword ptr [rcx+8], 0
0x18000e04e  mov     rbx, rcx
0x18000e051  jnz     short loc_18000E063
0x18000e053  mov     rcx, [rcx]
0x18000e056  add     rcx, 8; this
0x18000e05a  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000e05e  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e063  mov     rcx, [rbx]
0x18000e066  mov     edx, [rbx+8]
0x18000e069  lea     r8, [rcx+8]
0x18000e06d  add     rsp, 20h
0x18000e071  pop     rbx
0x18000e072  jmp     cs:__imp_InitOnceComplete
```
