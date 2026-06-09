# CConfigManager::RetrieveListenerIdentity(HKEY__ *,ushort *,ushort * *,LISTENER_IDENTITY *)

- ea: `0x180042970`
- end: `0x180042fab`
- name: `?RetrieveListenerIdentity@CConfigManager@@AEAAHPEAUHKEY__@@PEAGPEAPEAGPEAVLISTENER_IDENTITY@@@Z`
- size: `1595`
- prototype: `int(CConfigManager *__hidden this, HKEY, unsigned __int16 *, unsigned __int16 **, struct LISTENER_IDENTITY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180040ee0`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180026e80`
- `0x180042970`
- `0x180042fb4`
- `0x180043330`
- `0x1800436d0`
- `0x180046200`
- `0x180046d70`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x18019be40`

## import_xrefs

- `msvcrt!wcsstr` at `0x180042a32`
- `msvcrt!wcsstr` at `0x180042a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042bc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042bc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180042a03`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180042a03`

## string_xrefs

- `0x180042b88`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180042c35`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x180042d4c`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`

## pseudocode

```c

```
