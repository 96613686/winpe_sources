# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18001ace8`
- end: `0x18001ad1d`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002b968`
- `0x18003899c`

## callees

- `0x18001ace8`
- `0x180026b48`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001ad16`

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
0x18001ace8  push    rbx
0x18001acea  sub     rsp, 20h
0x18001acee  cmp     dword ptr [rcx+8], 0
0x18001acf2  mov     rbx, rcx
0x18001acf5  jnz     short loc_18001AD07
0x18001acf7  mov     rcx, [rcx]
0x18001acfa  add     rcx, 8; this
0x18001acfe  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18001ad02  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001ad07  mov     rcx, [rbx]
0x18001ad0a  mov     edx, [rbx+8]
0x18001ad0d  lea     r8, [rcx+8]
0x18001ad11  add     rsp, 20h
0x18001ad15  pop     rbx
0x18001ad16  jmp     cs:__imp_InitOnceComplete
```
