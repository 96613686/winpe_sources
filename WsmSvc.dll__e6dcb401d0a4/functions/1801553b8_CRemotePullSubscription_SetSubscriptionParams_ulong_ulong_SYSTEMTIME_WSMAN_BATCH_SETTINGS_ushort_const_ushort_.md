# CRemotePullSubscription::SetSubscriptionParams(ulong,ulong,_SYSTEMTIME,_WSMAN_BATCH_SETTINGS,ushort const *,ushort const *,ushort const *)

- ea: `0x1801553b8`
- end: `0x1801556c1`
- name: `?SetSubscriptionParams@CRemotePullSubscription@@QEAA_NKKU_SYSTEMTIME@@U_WSMAN_BATCH_SETTINGS@@PEBG22@Z`
- size: `777`
- prototype: `bool __high(unsigned int, unsigned int, struct _SYSTEMTIME, struct _WSMAN_BATCH_SETTINGS, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180112a40`
- `0x180141908`

## callees

- `0x180005d10`
- `0x1800224f0`
- `0x18006e6fc`
- `0x180103850`
- `0x180112380`
- `0x18011f0ec`
- `0x1801553b8`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801555bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801555bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1801555fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1801555fd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18015560b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180155620`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18015560b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180155620`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18015562e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18015562e`

## pseudocode

```c

```
