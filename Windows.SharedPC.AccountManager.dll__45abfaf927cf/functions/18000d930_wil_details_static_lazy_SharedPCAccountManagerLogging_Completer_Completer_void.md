# wil::details::static_lazy<SharedPCAccountManagerLogging>::Completer::~Completer(void)

- ea: `0x18000d930`
- end: `0x18000d965`
- name: `??1Completer@?$static_lazy@VSharedPCAccountManagerLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ec14`
- `0x180019a00`

## callees

- `0x18000d930`
- `0x18000e08c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000d95e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SharedPCAccountManagerLogging>::Completer::~Completer(
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
0x18000d930  push    rbx
0x18000d932  sub     rsp, 20h
0x18000d936  cmp     dword ptr [rcx+8], 0
0x18000d93a  mov     rbx, rcx
0x18000d93d  jnz     short loc_18000D94F
0x18000d93f  mov     rcx, [rcx]
0x18000d942  add     rcx, 8; this
0x18000d946  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000d94a  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000d94f  mov     rcx, [rbx]
0x18000d952  mov     edx, [rbx+8]
0x18000d955  lea     r8, [rcx+8]
0x18000d959  add     rsp, 20h
0x18000d95d  pop     rbx
0x18000d95e  jmp     cs:__imp_InitOnceComplete
```
