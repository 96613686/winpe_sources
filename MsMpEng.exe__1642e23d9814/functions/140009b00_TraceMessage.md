# TraceMessage

- ea: `0x140009b00`
- end: `0x140009b06`
- name: `TraceMessage`
- size: `6`
- prototype: `ULONG(TRACEHANDLE LoggerHandle, ULONG MessageFlags, LPCGUID MessageGuid, USHORT MessageNumber, ...)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1400020f0`
- `0x140005294`
- `0x1400052f4`
- `0x140005348`
- `0x140006794`
- `0x14000682c`
- `0x1400068fc`
- `0x140007f1c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x140009b00`

## pseudocode

```c
// attributes: thunk
ULONG TraceMessage(TRACEHANDLE LoggerHandle, ULONG MessageFlags, LPCGUID MessageGuid, USHORT MessageNumber, ...)
{
  return __imp_TraceMessage(LoggerHandle, MessageFlags, MessageGuid, MessageNumber);
}

```

## disassembly

```asm
0x140009b00  jmp     cs:__imp_TraceMessage
```
