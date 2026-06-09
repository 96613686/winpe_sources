# CMouseProcessor::ProcessMouseInputData(CMouseProcessor::MouseInputDataEx *,MouseInputProcessingState *,_MousePacketPerf &,_MOUSE_INPUT_DATA const *,tagUIPI_INFO_INT const *)

- ea: `0x14006d2d0`
- end: `0x14006d864`
- name: `?ProcessMouseInputData@CMouseProcessor@@AEAAXPEAVMouseInputDataEx@1@PEAUMouseInputProcessingState@@AEAU_MousePacketPerf@@PEBU_MOUSE_INPUT_DATA@@PEBUtagUIPI_INFO_INT@@@Z`
- size: `1428`
- prototype: `void __fastcall(CMouseProcessor *__hidden this, struct CMouseProcessor::MouseInputDataEx *, struct MouseInputProcessingState *, struct _MousePacketPerf *, const struct _MOUSE_INPUT_DATA *, const struct tagUIPI_INFO_INT *)`
- caller_count: `2`
- callee_count: `21`
- tags: ``

## callers

- `0x14005b9ec`
- `0x1401c300c`

## callees

- `0x14004ed5c`
- `0x140068178`
- `0x14006c710`
- `0x14006c810`
- `0x14006ccb4`
- `0x14006d0a0`
- `0x14006d108`
- `0x14006d160`
- `0x14006d1a8`
- `0x14006d2d0`
- `0x14006d86c`
- `0x14006ed20`
- `0x14006eee4`
- `0x14006ef38`
- `0x14006f084`
- `0x14011b4f8`
- `0x14011b550`
- `0x14011ca24`
- `0x14015ba84`
- `0x1401a415c`
- `0x1401aa4fc`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d4a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006d4a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d498`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006d498`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d4d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006d4d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d4c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006d4c9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006d4ee`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006d4ee`
- `WIN32K!W32GetUserSessionState` at `0x14006d351`
- `WIN32K!W32GetUserSessionState` at `0x14006d36a`
- `WIN32K!W32GetUserSessionState` at `0x14006d3a2`
- `WIN32K!W32GetUserSessionState` at `0x14006d468`
- `WIN32K!W32GetUserSessionState` at `0x14006d5f3`
- `WIN32K!W32GetUserSessionState` at `0x14006d602`
- `WIN32K!W32GetUserSessionState` at `0x14006d632`
- `WIN32K!W32GetUserSessionState` at `0x14006d641`
- `WIN32K!W32GetUserSessionState` at `0x14006d662`
- `WIN32K!W32GetUserSessionState` at `0x14006d671`
- `WIN32K!W32GetUserSessionState` at `0x14006d698`
- `WIN32K!W32GetUserSessionState` at `0x14006d6a7`
- `WIN32K!W32GetUserSessionState` at `0x14006d6c8`
- `WIN32K!W32GetUserSessionState` at `0x14006d6e4`
- `WIN32K!W32GetUserSessionState` at `0x14006d351`
- `WIN32K!W32GetUserSessionState` at `0x14006d36a`
- `WIN32K!W32GetUserSessionState` at `0x14006d3a2`
- `WIN32K!W32GetUserSessionState` at `0x14006d468`
- `WIN32K!W32GetUserSessionState` at `0x14006d5f3`
- `WIN32K!W32GetUserSessionState` at `0x14006d602`
- `WIN32K!W32GetUserSessionState` at `0x14006d632`
- `WIN32K!W32GetUserSessionState` at `0x14006d641`
- `WIN32K!W32GetUserSessionState` at `0x14006d662`
- `WIN32K!W32GetUserSessionState` at `0x14006d671`
- `WIN32K!W32GetUserSessionState` at `0x14006d698`
- `WIN32K!W32GetUserSessionState` at `0x14006d6a7`
- `WIN32K!W32GetUserSessionState` at `0x14006d6c8`
- `WIN32K!W32GetUserSessionState` at `0x14006d6e4`
- `HAL!KeQueryPerformanceCounter` at `0x14006d30a`
- `HAL!KeQueryPerformanceCounter` at `0x14006d480`
- `HAL!KeQueryPerformanceCounter` at `0x14006d30a`
- `HAL!KeQueryPerformanceCounter` at `0x14006d480`

## pseudocode

```c

```
