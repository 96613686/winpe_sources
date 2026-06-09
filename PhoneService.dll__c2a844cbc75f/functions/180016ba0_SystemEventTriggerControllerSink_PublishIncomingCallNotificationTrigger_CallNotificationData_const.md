# SystemEventTriggerControllerSink::_PublishIncomingCallNotificationTrigger(CallNotificationData const &)

- ea: `0x180016ba0`
- end: `0x18001705c`
- name: `?_PublishIncomingCallNotificationTrigger@SystemEventTriggerControllerSink@@IEAAJAEBUCallNotificationData@@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(SystemEventTriggerControllerSink *__hidden this, const struct CallNotificationData *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011fc`
- `0x1800017a4`
- `0x180006e94`
- `0x1800146cc`
- `0x180016ba0`
- `0x18001787c`
- `0x180017c84`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016fd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001701e`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x180016cf3`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x180016cf3`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x180016e46`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x180016e46`

## string_xrefs

- `0x180016c55`: `onecoreuap\net\phone\phoneservice\service\lib\systemeventtriggercontrollersink.cpp`
- `0x180016fa9`: `onecoreuap\net\phone\phoneservice\service\lib\systemeventtriggercontrollersink.cpp`
- `0x180017002`: `onecoreuap\net\phone\phoneservice\service\lib\systemeventtriggercontrollersink.cpp`
- `0x180016ea7`: `IncomingCallNotificationTrigger fired`
- `0x180016ebf`: `IncomingCallNotificationTrigger no need to fire`

## pseudocode

```c

```
