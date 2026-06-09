# TraceMessage

- ea: `0x180088f68`
- end: `0x180088f6e`
- name: `TraceMessage`
- size: `6`
- prototype: `ULONG(TRACEHANDLE LoggerHandle, ULONG MessageFlags, LPCGUID MessageGuid, USHORT MessageNumber, ...)`
- caller_count: `46`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a05c`
- `0x18001a17c`
- `0x18001a1cc`
- `0x18001dbd0`
- `0x18001dbf0`
- `0x180022f5c`
- `0x180022fd4`
- `0x180026858`
- `0x18002688c`
- `0x1800268d0`
- `0x180026968`
- `0x1800269a4`
- `0x180029a88`
- `0x180029ad8`
- `0x18002a988`
- `0x18002ae2c`
- `0x18002af24`
- `0x18002b024`
- `0x18002b134`
- `0x18002ba24`
- `0x1800320c0`
- `0x180032118`
- `0x18003442c`
- `0x1800358b0`
- `0x1800358fc`
- `0x180039444`
- `0x180039490`
- `0x1800394d4`
- `0x180047ad8`
- `0x18004ac48`
- `0x18004acec`
- `0x18004c54c`
- `0x18004dac4`
- `0x18004dafc`
- `0x18004db88`
- `0x180050d98`
- `0x180052328`
- `0x1800523a4`
- `0x1800523f8`
- `0x180052460`
- `0x180053a2c`
- `0x1800547cc`
- `0x18006141c`
- `0x1800655dc`
- `0x1800677c4`
- `0x180068cf4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180088f68`

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
0x180088f68  jmp     cs:__imp_TraceMessage
```
