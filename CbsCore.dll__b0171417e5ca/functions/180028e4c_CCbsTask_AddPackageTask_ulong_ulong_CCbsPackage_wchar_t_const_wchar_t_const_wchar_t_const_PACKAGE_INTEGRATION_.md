# CCbsTask::AddPackageTask(ulong,ulong,CCbsPackage *,wchar_t const *,wchar_t const *,wchar_t const *,PACKAGE_INTEGRATION_TYPE::PACKAGE_INTEGRATION,CbsState,int,wchar_t const *,UpdateSelection)

- ea: `0x180028e4c`
- end: `0x180029511`
- name: `?AddPackageTask@CCbsTask@@QEAAJKKPEAVCCbsPackage@@PEB_W11W4PACKAGE_INTEGRATION@PACKAGE_INTEGRATION_TYPE@@W4CbsState@@H1W4UpdateSelection@@@Z`
- size: `1733`
- prototype: `int __high(unsigned int, unsigned int, struct CCbsPackage *, const wchar_t *, const wchar_t *, const wchar_t *, enum PACKAGE_INTEGRATION_TYPE::PACKAGE_INTEGRATION, enum CbsState, int, const wchar_t *, enum UpdateSelection)`
- caller_count: `4`
- callee_count: `18`
- tags: `service_task, installer_update`

## callers

- `0x18015918c`
- `0x180171914`
- `0x18017ff2c`
- `0x1801d304c`

## callees

- `0x180015420`
- `0x180015640`
- `0x18001de20`
- `0x180028e4c`
- `0x18002a78c`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800b3e04`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x1800ebd20`
- `0x1800ec920`
- `0x1800fa3ec`
- `0x180125bd4`
- `0x18013e1a8`
- `0x18013e5e8`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800293f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800293f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800294db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800294db`

## string_xrefs

- `0x180028f41`: `onecore\base\cbs\core\cbstask.cpp`
- `0x180029128`: `onecore\base\cbs\core\cbstask.cpp`
- `0x180029458`: `onecore\base\cbs\core\cbstask.cpp`
- `0x1800294ba`: `onecore\base\cbs\core\cbstask.cpp`
- `0x180029392`: `Invalid update action {} specified; expected SelectionOn, SelectionOff, SelectionDefault, or SelectionCancel`
- `0x1800291a4`: `No package name defined for package task`
- `0x180028efa`: `Highest package state cannot be default or update must be provided`

## pseudocode

```c

```
