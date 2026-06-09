# DataConnectivityListener::_DataConnectivityStateNotify(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18006c8a0`
- end: `0x18006c950`
- name: `?_DataConnectivityStateNotify@DataConnectivityListener@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `176`
- prototype: `static int(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180006e94`
- `0x18006c490`
- `0x18006c49c`
- `0x18006c8a0`
- `0x18006c958`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c8dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c8dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c917`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c917`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c938`

## string_xrefs

- `0x18006c902`: `onecoreuap\net\phone\phoneservice\service\lib\dataconnectivitylistener.cpp`
- `0x18006c923`: `onecoreuap\net\phone\phoneservice\service\lib\dataconnectivitylistener.cpp`

## pseudocode

```c

```
