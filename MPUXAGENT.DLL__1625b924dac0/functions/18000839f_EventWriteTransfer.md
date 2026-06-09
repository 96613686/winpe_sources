# EventWriteTransfer

- ea: `0x18000839f`
- end: `0x1800083a5`
- name: `EventWriteTransfer`
- size: `6`
- prototype: `ULONG __stdcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180067a80`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000839f`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall EventWriteTransfer(
        REGHANDLE RegHandle,
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  return __imp_EventWriteTransfer(RegHandle, EventDescriptor, ActivityId, RelatedActivityId, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000839f  jmp     cs:__imp_EventWriteTransfer
```
