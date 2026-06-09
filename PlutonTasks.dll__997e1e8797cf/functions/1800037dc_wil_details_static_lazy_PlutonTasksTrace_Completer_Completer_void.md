# wil::details::static_lazy<PlutonTasksTrace>::Completer::~Completer(void)

- ea: `0x1800037dc`
- end: `0x180003811`
- name: `??1Completer@?$static_lazy@VPlutonTasksTrace@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008bd0`

## callees

- `0x1800037dc`
- `0x180006f94`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000380a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PlutonTasksTrace>::Completer::~Completer(
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
0x1800037dc  push    rbx
0x1800037de  sub     rsp, 20h
0x1800037e2  cmp     dword ptr [rcx+8], 0
0x1800037e6  mov     rbx, rcx
0x1800037e9  jnz     short loc_1800037FB
0x1800037eb  mov     rcx, [rcx]
0x1800037ee  add     rcx, 8; this
0x1800037f2  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x1800037f6  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800037fb  mov     rcx, [rbx]
0x1800037fe  mov     edx, [rbx+8]
0x180003801  lea     r8, [rcx+8]
0x180003805  add     rsp, 20h
0x180003809  pop     rbx
0x18000380a  jmp     cs:__imp_InitOnceComplete
```
