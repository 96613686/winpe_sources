# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180007db8`
- end: `0x180007ded`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab00`
- `0x18000abc0`

## callees

- `0x180007db8`
- `0x180009d64`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007de6`

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
0x180007db8  push    rbx
0x180007dba  sub     rsp, 20h
0x180007dbe  cmp     dword ptr [rcx+8], 0
0x180007dc2  mov     rbx, rcx
0x180007dc5  jnz     short loc_180007DD7
0x180007dc7  mov     rcx, [rcx]
0x180007dca  add     rcx, 8; this
0x180007dce  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180007dd2  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180007dd7  mov     rcx, [rbx]
0x180007dda  mov     edx, [rbx+8]
0x180007ddd  lea     r8, [rcx+8]
0x180007de1  add     rsp, 20h
0x180007de5  pop     rbx
0x180007de6  jmp     cs:__imp_InitOnceComplete
```
