# SharingPlatform::SessionHost::RemoveFromPendingList(_GUID const &,unsigned __int64 *,SharingPlatform::IParticipantIdentifier * *)

- ea: `0x18005d8e4`
- end: `0x18005db1d`
- name: `?RemoveFromPendingList@SessionHost@SharingPlatform@@AEAA_NAEBU_GUID@@PEA_KPEAPEAUIParticipantIdentifier@2@@Z`
- size: `569`
- prototype: `bool __fastcall(SharingPlatform::SessionHost *__hidden this, const struct _GUID *, unsigned __int64 *, struct SharingPlatform::IParticipantIdentifier **)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18001a090`

## callees

- `0x180004928`
- `0x18000a580`
- `0x180010d04`
- `0x180018490`
- `0x18001add0`
- `0x1800225a0`
- `0x180043b48`
- `0x18004fa70`
- `0x180053320`
- `0x18005a6f8`
- `0x18005d8e4`
- `0x18005e1d8`
- `0x18005e21c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d9a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005daf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d9a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005daf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d91c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d91c`

## string_xrefs

- `0x18005d98c`: `SessionHost::RemoveFromPendingList failed to find cdpSessionId in m_pendingParticipants map; cdpSessionId = 0x%016llx`

## pseudocode

```c

```
