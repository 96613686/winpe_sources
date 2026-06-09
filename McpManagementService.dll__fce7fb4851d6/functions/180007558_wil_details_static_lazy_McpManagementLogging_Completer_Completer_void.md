# wil::details::static_lazy<McpManagementLogging>::Completer::~Completer(void)

- ea: `0x180007558`
- end: `0x18000758d`
- name: `??1Completer@?$static_lazy@VMcpManagementLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e474`
- `0x18001dfbc`
- `0x18001e130`
- `0x18001e2a4`

## callees

- `0x180007558`
- `0x18000bd94`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007586`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<McpManagementLogging>::Completer::~Completer(
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
0x180007558  push    rbx
0x18000755a  sub     rsp, 20h
0x18000755e  cmp     dword ptr [rcx+8], 0
0x180007562  mov     rbx, rcx
0x180007565  jnz     short loc_180007577
0x180007567  mov     rcx, [rcx]
0x18000756a  add     rcx, 8; this
0x18000756e  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180007572  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180007577  mov     rcx, [rbx]
0x18000757a  mov     edx, [rbx+8]
0x18000757d  lea     r8, [rcx+8]
0x180007581  add     rsp, 20h
0x180007585  pop     rbx
0x180007586  jmp     cs:__imp_InitOnceComplete
```
