# RIMHidGetPreparsedData

- ea: `0x1400d5fc4`
- end: `0x1400d67c7`
- name: `RIMHidGetPreparsedData`
- size: `2051`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1400d3e78`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140071828`
- `0x1400718f0`
- `0x140076420`
- `0x1400d5fc4`
- `0x1400d7bfc`
- `0x1400d7df0`
- `0x1401aa4fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400d6777`
- `ntoskrnl!ZwClose` at `0x1400d6777`
- `ntoskrnl!ObfReferenceObject` at `0x1400d6044`
- `ntoskrnl!ObfReferenceObject` at `0x1400d6044`
- `ntoskrnl!KeInitializeEvent` at `0x1400d60a1`
- `ntoskrnl!KeInitializeEvent` at `0x1400d6204`
- `ntoskrnl!KeInitializeEvent` at `0x1400d60a1`
- `ntoskrnl!KeInitializeEvent` at `0x1400d6204`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d614f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d62b0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d614f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d62b0`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d60e3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d6244`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d60e3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d6244`
- `ntoskrnl!IofCallDriver` at `0x1400d6124`
- `ntoskrnl!IofCallDriver` at `0x1400d6285`
- `ntoskrnl!IofCallDriver` at `0x1400d6124`
- `ntoskrnl!IofCallDriver` at `0x1400d6285`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d675d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d67af`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d675d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d67af`
- `WIN32K!W32GetUserSessionState` at `0x1400d6328`
- `WIN32K!W32GetUserSessionState` at `0x1400d6398`
- `WIN32K!W32GetUserSessionState` at `0x1400d6450`
- `WIN32K!W32GetUserSessionState` at `0x1400d6516`
- `WIN32K!W32GetUserSessionState` at `0x1400d653e`
- `WIN32K!W32GetUserSessionState` at `0x1400d65c0`
- `WIN32K!W32GetUserSessionState` at `0x1400d6689`
- `WIN32K!W32GetUserSessionState` at `0x1400d6704`
- `WIN32K!W32GetUserSessionState` at `0x1400d6328`
- `WIN32K!W32GetUserSessionState` at `0x1400d6398`
- `WIN32K!W32GetUserSessionState` at `0x1400d6450`
- `WIN32K!W32GetUserSessionState` at `0x1400d6516`
- `WIN32K!W32GetUserSessionState` at `0x1400d653e`
- `WIN32K!W32GetUserSessionState` at `0x1400d65c0`
- `WIN32K!W32GetUserSessionState` at `0x1400d6689`
- `WIN32K!W32GetUserSessionState` at `0x1400d6704`
- `HAL!KeQueryPerformanceCounter` at `0x1400d610f`
- `HAL!KeQueryPerformanceCounter` at `0x1400d6161`
- `HAL!KeQueryPerformanceCounter` at `0x1400d6270`
- `HAL!KeQueryPerformanceCounter` at `0x1400d62c2`
- `HAL!KeQueryPerformanceCounter` at `0x1400d610f`
- `HAL!KeQueryPerformanceCounter` at `0x1400d6161`
- `HAL!KeQueryPerformanceCounter` at `0x1400d6270`
- `HAL!KeQueryPerformanceCounter` at `0x1400d62c2`

## string_xrefs

- `0x1400d617a`: `GetPreparsedData`
- `0x1400d62db`: `GetCollectionDescriptor`

## pseudocode

```c

```
