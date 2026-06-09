# RouteManager::IsInterfaceHidden(_GUID const *)

- ea: `0x180019cdc`
- end: `0x180019ea9`
- name: `?IsInterfaceHidden@RouteManager@@SA_NPEBU_GUID@@@Z`
- size: `461`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180019a88`

## callees

- `0x180010080`
- `0x180019cdc`
- `0x180019f2c`
- `0x18002706c`
- `0x180087ab8`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019d9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019d9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019d6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019d6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019d8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019d8d`

## string_xrefs

- `0x180019e74`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180019e93`: `onecoreuap\net\wcm\service\base\routemanager\routemanager.cpp`

## pseudocode

```c

```
