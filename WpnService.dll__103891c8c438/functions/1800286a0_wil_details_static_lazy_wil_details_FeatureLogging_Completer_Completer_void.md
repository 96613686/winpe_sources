# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x1800286a0`
- end: `0x1800286d5`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d830`
- `0x18000dc40`
- `0x1800172dc`
- `0x180022fec`

## callees

- `0x180022344`
- `0x1800286a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800286ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(
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
0x1800286a0  push    rbx
0x1800286a2  sub     rsp, 20h
0x1800286a6  cmp     dword ptr [rcx+8], 0
0x1800286aa  mov     rbx, rcx
0x1800286ad  jnz     short loc_1800286BF
0x1800286af  mov     rcx, [rcx]
0x1800286b2  add     rcx, 8; this
0x1800286b6  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x1800286ba  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800286bf  mov     rcx, [rbx]
0x1800286c2  mov     edx, [rbx+8]
0x1800286c5  lea     r8, [rcx+8]
0x1800286c9  add     rsp, 20h
0x1800286cd  pop     rbx
0x1800286ce  jmp     cs:__imp_InitOnceComplete
```
