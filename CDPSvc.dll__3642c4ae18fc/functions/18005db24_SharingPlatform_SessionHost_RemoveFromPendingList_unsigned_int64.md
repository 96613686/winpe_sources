# SharingPlatform::SessionHost::RemoveFromPendingList(unsigned __int64)

- ea: `0x18005db24`
- end: `0x18005dbe8`
- name: `?RemoveFromPendingList@SessionHost@SharingPlatform@@AEAA_N_K@Z`
- size: `196`
- prototype: `bool __fastcall(SharingPlatform::SessionHost *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800145a0`

## callees

- `0x18000a580`
- `0x180018490`
- `0x180043b48`
- `0x180053320`
- `0x18005db24`
- `0x18005e1d8`
- `0x18005e258`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dbd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dbd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005db42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005db42`

## string_xrefs

- `0x18005dbbb`: `SessionHost::RemoveFromPendingList; m_pendingParticipants and m_pendingParticipantsGuidToCDPSessionId disagreed about presence of cdpSessionId in map; cdpSessionId = 0x%016llx`

## pseudocode

```c

```
