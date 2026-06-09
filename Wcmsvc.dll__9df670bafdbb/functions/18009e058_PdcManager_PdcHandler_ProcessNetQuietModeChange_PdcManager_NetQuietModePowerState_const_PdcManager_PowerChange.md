# PdcManager::PdcHandler::ProcessNetQuietModeChange(PdcManager::NetQuietModePowerState const &,PdcManager::PowerChangeSource,PdcManager::NetQuietModeRestrictedStandbyFlag,bool,std::shared_ptr<PdcManager::PdcHandler::PowerRef>)

- ea: `0x18009e058`
- end: `0x18009f4a7`
- name: `?ProcessNetQuietModeChange@PdcHandler@PdcManager@@AEAAKAEBW4NetQuietModePowerState@2@W4PowerChangeSource@2@W4NetQuietModeRestrictedStandbyFlag@2@_NV?$shared_ptr@UPowerRef@PdcHandler@PdcManager@@@std@@@Z`
- size: `5199`
- prototype: `__int64 __usercall@<rax>(PdcManager::PdcHandler *this@<rcx>, enum PdcManager::NetQuietModePowerState *@<rdx>, char, __int64)`
- caller_count: `8`
- callee_count: `41`
- tags: `loader_planting, service_task`

## callers

- `0x180011320`
- `0x180054030`
- `0x1800543d4`
- `0x18007edc4`
- `0x18009b024`
- `0x18009b580`
- `0x18009deb0`
- `0x18009f888`

## callees

- `0x180002ed4`
- `0x1800030b4`
- `0x1800032e8`
- `0x1800033dc`
- `0x180007ff8`
- `0x180008394`
- `0x18000ff58`
- `0x180010080`
- `0x180027250`
- `0x180027630`
- `0x180028980`
- `0x18002c448`
- `0x18002e200`
- `0x18002e228`
- `0x18002e560`
- `0x180032540`
- `0x180033410`
- `0x1800352a0`
- `0x18003870c`
- `0x18003a08c`
- `0x18003b6dc`
- `0x18003cb94`
- `0x180040c54`
- `0x180043344`
- `0x180043a08`
- `0x18004aaf0`
- `0x18005303c`
- `0x18005323c`
- `0x1800533b0`
- `0x180053a54`
- `0x180056f18`
- `0x180073a28`
- `0x180073a90`
- `0x180084f50`
- `0x180092970`
- `0x1800985fc`
- `0x18009ab90`
- `0x18009e058`
- `0x18009f4b0`
- `0x1800a16fc`
- `0x1800a185c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e23c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e34c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e38f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e955`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e23c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e34c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e38f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e955`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f425`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009f105`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18009f105`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18009e204`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18009e204`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ea23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ea7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ea23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ea7c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009e28c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009e28c`

## string_xrefs

- `0x18009e2ac`: `onecoreuap\net\wcm\service\base\server\pdchandler.cpp`
- `0x18009e82d`: `onecoreuap\net\wcm\service\base\server\pdchandler.cpp`

## pseudocode

```c

```
