# RouteManager::IsInterfaceInGoodState(_GUID const *)

- ea: `0x18001efec`
- end: `0x18001f141`
- name: `?IsInterfaceInGoodState@RouteManager@@SA_NPEBU_GUID@@@Z`
- size: `341`
- prototype: `bool __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800188cc`

## callees

- `0x180010080`
- `0x18001dea8`
- `0x18001efec`
- `0x18001f820`
- `0x18002706c`
- `0x180087ab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f0a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f0a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f071`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f071`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f091`

## string_xrefs

- `0x18001f10f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001f12b`: `onecoreuap\net\wcm\service\base\routemanager\routemanager.cpp`

## pseudocode

```c

```
