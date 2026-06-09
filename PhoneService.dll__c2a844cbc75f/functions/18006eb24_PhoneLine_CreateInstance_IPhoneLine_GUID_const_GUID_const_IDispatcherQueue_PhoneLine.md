# PhoneLine::CreateInstance(IPhoneLine *,_GUID const &,_GUID const &,IDispatcherQueue *,PhoneLine * *)

- ea: `0x18006eb24`
- end: `0x18006edbd`
- name: `?CreateInstance@PhoneLine@@SAJPEAUIPhoneLine@@AEBU_GUID@@1PEAUIDispatcherQueue@@PEAPEAV1@@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct IPhoneLine *, const struct _GUID *, const struct _GUID *, struct IDispatcherQueue *, struct PhoneLine **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180043c58`

## callees

- `0x180005660`
- `0x180006e94`
- `0x18006cab0`
- `0x18006eb24`
- `0x180071b9c`
- `0x180071ba8`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ebe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ebe9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eca9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eca9`

## string_xrefs

- `0x18006ec3e`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18006ec59`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x18006ec7d`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18006ed82`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c

```
