# wil::details::static_lazy<SessionTraceLoggingClass>::Completer::~Completer(void)

- ea: `0x140008028`
- end: `0x14000805d`
- name: `??1Completer@?$static_lazy@VSessionTraceLoggingClass@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010fe0`
- `0x1400110a0`
- `0x140011160`
- `0x140024040`

## callees

- `0x140008028`
- `0x14000d6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140008056`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SessionTraceLoggingClass>::Completer::~Completer(
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
0x140008028  push    rbx
0x14000802a  sub     rsp, 20h
0x14000802e  cmp     dword ptr [rcx+8], 0
0x140008032  mov     rbx, rcx
0x140008035  jnz     short loc_140008047
0x140008037  mov     rcx, [rcx]
0x14000803a  add     rcx, 8; this
0x14000803e  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x140008042  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140008047  mov     rcx, [rbx]
0x14000804a  mov     edx, [rbx+8]
0x14000804d  lea     r8, [rcx+8]
0x140008051  add     rsp, 20h
0x140008055  pop     rbx
0x140008056  jmp     cs:__imp_InitOnceComplete
```
