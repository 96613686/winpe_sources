# SharingPlatform::SessionHost::RemoveFromActiveList(unsigned __int64,_GUID &)

- ea: `0x18005d7c0`
- end: `0x18005d8de`
- name: `?RemoveFromActiveList@SessionHost@SharingPlatform@@AEAA_N_KAEAU_GUID@@@Z`
- size: `286`
- prototype: `bool(SharingPlatform::SessionHost *__hidden this, unsigned __int64, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800145a0`

## callees

- `0x18000a580`
- `0x180018490`
- `0x18001add0`
- `0x180041874`
- `0x180043b48`
- `0x180053320`
- `0x18005d7c0`
- `0x18005e1d8`
- `0x18005e21c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d8c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d8c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d7e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d7e3`

## string_xrefs

- `0x18005d8ae`: `SessionHost::RemoveFromActiveList; m_participants and m_participantsGuidToCdpSessionId disagreed about presence of cdpSessionId in map; cdpSessionId = 0x%016llx`

## pseudocode

```c

```
