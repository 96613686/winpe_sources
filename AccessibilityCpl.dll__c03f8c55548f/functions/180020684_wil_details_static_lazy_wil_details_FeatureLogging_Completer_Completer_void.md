# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x180020684`
- end: `0x1800206ba`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021304`

## callees

- `0x180015744`
- `0x180020684`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800206ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800206ad`

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
0x180020684  push    rbx
0x180020686  sub     rsp, 20h
0x18002068a  mov     rbx, rcx
0x18002068d  cmp     dword ptr [rcx+8], 0
0x180020691  jnz     short loc_1800206A3
0x180020693  mov     rcx, [rcx]
0x180020696  add     rcx, 8; this
0x18002069a  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18002069e  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800206a3  mov     rcx, [rbx]; lpInitOnce
0x1800206a6  lea     r8, [rcx+8]; lpContext
0x1800206aa  mov     edx, [rbx+8]; dwFlags
0x1800206ad  call    cs:__imp_InitOnceComplete
0x1800206b3  nop
0x1800206b4  add     rsp, 20h
0x1800206b8  pop     rbx
0x1800206b9  retn
```
