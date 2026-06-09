# AppActivation::ActivateInternal(bool,Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *,CRPCTimeoutAndWaitOnAppLaunchGrace *,IPendingViewRequest *,ACTIVATION_PHASE *,IInspectable * *)

- ea: `0x18000c538`
- end: `0x18000c9d4`
- name: `?ActivateInternal@AppActivation@@AEAAJ_NPEAUIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAVCRPCTimeoutAndWaitOnAppLaunchGrace@@PEAUIPendingViewRequest@@PEAW4ACTIVATION_PHASE@@PEAPEAUIInspectable@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(AppActivation *__hidden this, bool, struct Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs *, struct CRPCTimeoutAndWaitOnAppLaunchGrace *, struct IPendingViewRequest *, enum ACTIVATION_PHASE *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x18000b5c0`
- `0x18000c538`
- `0x18000ca80`
- `0x18000dbf0`
- `0x180011328`
- `0x180024770`
- `0x180024840`
- `0x180029028`
- `0x1800300c0`
- `0x180032860`
- `0x180033350`
- `0x180038750`
- `0x18003dde4`
- `0x180042214`
- `0x18005ae90`
- `0x180084850`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c853`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c9cd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c853`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c9cd`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000c6c7`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000c6c7`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c6d3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c6d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c83a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c83a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c7aa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c8c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c7aa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c8c5`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18000c717`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18000c717`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000c754`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000c8db`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000c754`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000c8db`

## pseudocode

```c

```
