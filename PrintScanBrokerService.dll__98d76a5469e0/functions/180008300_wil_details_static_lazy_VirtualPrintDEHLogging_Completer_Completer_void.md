# wil::details::static_lazy<VirtualPrintDEHLogging>::Completer::~Completer(void)

- ea: `0x180008300`
- end: `0x180008335`
- name: `??1Completer@?$static_lazy@VVirtualPrintDEHLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ffe4`
- `0x18003821c`

## callees

- `0x180008300`
- `0x18000d36c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000832e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
BOOL __fastcall wil::details::static_lazy<VirtualPrintDEHLogging>::Completer::~Completer(
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
0x180008300  push    rbx
0x180008302  sub     rsp, 20h
0x180008306  cmp     dword ptr [rcx+8], 0
0x18000830a  mov     rbx, rcx
0x18000830d  jnz     short loc_18000831F
0x18000830f  mov     rcx, [rcx]
0x180008312  add     rcx, 8; this
0x180008316  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000831a  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000831f  mov     rcx, [rbx]
0x180008322  mov     edx, [rbx+8]
0x180008325  lea     r8, [rcx+8]
0x180008329  add     rsp, 20h
0x18000832d  pop     rbx
0x18000832e  jmp     cs:__imp_InitOnceComplete
```
