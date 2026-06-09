# CLocationAcquireSingleShotWiFi::OnInferenceUpdate(long,ILocationInformation *)

- ea: `0x180030104`
- end: `0x180030285`
- name: `?OnInferenceUpdate@CLocationAcquireSingleShotWiFi@@AEAAXJPEAUILocationInformation@@@Z`
- size: `385`
- prototype: `void __fastcall(CLocationAcquireSingleShotWiFi *__hidden this, int, struct ILocationInformation *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800300f0`

## callees

- `0x18001be08`
- `0x180030104`
- `0x18003028c`
- `0x1800307a0`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003013e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003013e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800301bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800301bf`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180030193`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180030193`

## string_xrefs

- `0x1800301ff`: `CLocationAcquireSingleShotWiFi::OnInferenceUpdate`
- `0x180030251`: `CLocationAcquireSingleShotWiFi::OnInferenceUpdate`
- `0x1800301f3`: `LocationHelper::GetLocationProvider(LOCATION_POSITIONINGENGINE_COMPOSITE, &pCpeProvider)`

## pseudocode

```c

```
