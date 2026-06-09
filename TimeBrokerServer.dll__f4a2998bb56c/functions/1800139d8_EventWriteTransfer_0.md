# EventWriteTransfer_0

- ea: `0x1800139d8`
- end: `0x1800139de`
- name: `EventWriteTransfer_0`
- size: `6`
- prototype: `ULONG __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000b0d0`
- `0x18000be68`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800139d8`

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
0x1800139d8  jmp     cs:__imp_EventWriteTransfer
```
