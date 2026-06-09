# EventWriteTransfer_0

- ea: `0x180077173`
- end: `0x180077179`
- name: `EventWriteTransfer_0`
- size: `6`
- prototype: `ULONG __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18003d800`
- `0x18003de10`
- `0x18004df00`
- `0x180050648`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180077173`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall EventWriteTransfer_0(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  return EventWriteTransfer(RegHandle, EventDescriptor, ActivityId, RelatedActivityId, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180077173  jmp     cs:__imp_EventWriteTransfer
```
