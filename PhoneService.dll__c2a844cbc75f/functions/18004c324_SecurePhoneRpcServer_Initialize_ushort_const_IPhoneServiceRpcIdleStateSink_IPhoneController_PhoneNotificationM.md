# SecurePhoneRpcServer::Initialize(ushort const *,IPhoneServiceRpcIdleStateSink *,IPhoneController *,PhoneNotificationManager *)

- ea: `0x18004c324`
- end: `0x18004c514`
- name: `?Initialize@SecurePhoneRpcServer@@QEAAJPEBGPEAUIPhoneServiceRpcIdleStateSink@@PEAUIPhoneController@@PEAVPhoneNotificationManager@@@Z`
- size: `496`
- prototype: `int(SecurePhoneRpcServer *__hidden this, const unsigned __int16 *, struct IPhoneServiceRpcIdleStateSink *, struct IPhoneController *, struct PhoneNotificationManager *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a4c`

## callees

- `0x180006e94`
- `0x18004c13c`
- `0x18004c1f4`
- `0x18004c324`
- `0x18004c51c`
- `0x18004c528`
- `0x18004d180`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c350`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c3ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c350`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c3ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c3e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c479`

## string_xrefs

- `0x18004c39e`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18004c3b9`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18004c435`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18004c450`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18004c4d9`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`

## pseudocode

```c

```
