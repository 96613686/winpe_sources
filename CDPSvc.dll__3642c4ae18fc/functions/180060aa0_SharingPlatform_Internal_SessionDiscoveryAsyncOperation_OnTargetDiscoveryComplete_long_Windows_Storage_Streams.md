# SharingPlatform::Internal::SessionDiscoveryAsyncOperation::OnTargetDiscoveryComplete(long,Windows::Storage::Streams::IDataReader *)

- ea: `0x180060aa0`
- end: `0x180060bd8`
- name: `?OnTargetDiscoveryComplete@SessionDiscoveryAsyncOperation@Internal@SharingPlatform@@AEAAXJPEAUIDataReader@Streams@Storage@Windows@@@Z`
- size: `312`
- prototype: `void __fastcall(SharingPlatform::Internal::SessionDiscoveryAsyncOperation *__hidden this, int, struct Windows::Storage::Streams::IDataReader *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800614e0`

## callees

- `0x18000a580`
- `0x18000a988`
- `0x180018490`
- `0x1800218b4`
- `0x180053320`
- `0x18005fcc0`
- `0x180060aa0`
- `0x180061344`
- `0x1800613ac`
- `0x180061e10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060afa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060afa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060ac1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060ac1`

## string_xrefs

- `0x180060b8c`: `SessionDiscoveryAsyncOperation::OnTargetDiscoveryComplete, device=%hs`
- `0x180060b30`: `SessionDiscoveryAsyncOperation::OnTargetDiscoveryComplete FAILED, device=%hs, hr:0x%x`

## pseudocode

```c

```
