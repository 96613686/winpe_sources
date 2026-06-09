# EventWriteTransfer_0

- ea: `0x18001da24`
- end: `0x18001da2a`
- name: `EventWriteTransfer_0`
- size: `6`
- prototype: `ULONG __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800151b0`
- `0x18002210c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001da24`

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
0x18001da24  jmp     cs:__imp_EventWriteTransfer
```
