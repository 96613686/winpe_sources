# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x1400153d4`
- end: `0x1400153f9`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(CEventLogger *__hidden this, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000dd80`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400153e5`
- `ADVAPI32!EventWrite` at `0x1400153e5`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(CEventLogger *this, const struct _EVENT_DESCRIPTOR *a2)
{
  return EventWrite(g_Logger, a2, 0, 0) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1400153d4  sub     rsp, 28h
0x1400153d8  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x1400153df  xor     r9d, r9d; UserData
0x1400153e2  xor     r8d, r8d; UserDataCount
0x1400153e5  call    cs:__imp_EventWrite
0x1400153eb  neg     eax
0x1400153ed  sbb     eax, eax
0x1400153ef  and     eax, 80004005h
0x1400153f4  add     rsp, 28h
0x1400153f8  retn
```
