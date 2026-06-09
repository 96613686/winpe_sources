# SharingPlatform::SessionHost::AddToPendingParticipantsList(unsigned __int64,SharingPlatform::IParticipantIdentifier *,_GUID)

- ea: `0x180020958`
- end: `0x180020aab`
- name: `?AddToPendingParticipantsList@SessionHost@SharingPlatform@@AEAAX_KPEAUIParticipantIdentifier@2@U_GUID@@@Z`
- size: `339`
- prototype: `void __fastcall(SharingPlatform::SessionHost *__hidden this, unsigned __int64, struct SharingPlatform::IParticipantIdentifier *, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800208ac`
- `0x18005d0ac`

## callees

- `0x18000a580`
- `0x180018490`
- `0x180020958`
- `0x180053320`
- `0x18005ab0c`
- `0x18005b650`
- `0x18005b684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020a99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002097e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002097e`

## string_xrefs

- `0x1800209bf`: `SessionHost::AddToPendingParticipantsList failed to add participant to m_pendingParticipants map; cdpSessionId = 0x%016llx`

## pseudocode

```c

```
