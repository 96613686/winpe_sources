# wil::details::static_lazy<CredUIBrokerLogging>::Completer::~Completer(void)

- ea: `0x140009304`
- end: `0x140009339`
- name: `??1Completer@?$static_lazy@VCredUIBrokerLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140019b60`
- `0x140019c20`
- `0x140019ce0`
- `0x140019da0`

## callees

- `0x140009304`
- `0x140012950`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x140009332`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CredUIBrokerLogging>::Completer::~Completer(
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
0x140009304  push    rbx
0x140009306  sub     rsp, 20h
0x14000930a  cmp     dword ptr [rcx+8], 0
0x14000930e  mov     rbx, rcx
0x140009311  jnz     short loc_140009323
0x140009313  mov     rcx, [rcx]
0x140009316  add     rcx, 8; this
0x14000931a  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x14000931e  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140009323  mov     rcx, [rbx]
0x140009326  mov     edx, [rbx+8]
0x140009329  lea     r8, [rcx+8]
0x14000932d  add     rsp, 20h
0x140009331  pop     rbx
0x140009332  jmp     cs:__imp_InitOnceComplete
```
