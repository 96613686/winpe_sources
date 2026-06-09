# EventWriteTransfer_0

- ea: `0x180003834`
- end: `0x18000383a`
- name: `EventWriteTransfer_0`
- size: `6`
- prototype: `ULONG __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180022308`
- `0x180022b68`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003834`

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
0x180003834  jmp     cs:__imp_EventWriteTransfer
```
