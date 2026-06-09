# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18000e3f8`
- end: `0x18000e42d`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018ae0`
- `0x18004f430`
- `0x1800551ec`

## callees

- `0x18000e3f8`
- `0x180014a24`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e426`

## pseudocode

```c
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
0x18000e3f8  push    rbx
0x18000e3fa  sub     rsp, 20h
0x18000e3fe  cmp     dword ptr [rcx+8], 0
0x18000e402  mov     rbx, rcx
0x18000e405  jnz     short loc_18000E417
0x18000e407  mov     rcx, [rcx]
0x18000e40a  add     rcx, 8; this
0x18000e40e  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000e412  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e417  mov     rcx, [rbx]
0x18000e41a  mov     edx, [rbx+8]
0x18000e41d  lea     r8, [rcx+8]
0x18000e421  add     rsp, 20h
0x18000e425  pop     rbx
0x18000e426  jmp     cs:__imp_InitOnceComplete
```
