# xxxWaitForVideoPortCalloutReady(uchar,uchar,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x14015da84`
- end: `0x14015dcb1`
- name: `?xxxWaitForVideoPortCalloutReady@@YAXEEPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `557`
- prototype: `void __fastcall(unsigned __int8, unsigned __int8, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140111808`

## callees

- `0x140012c80`
- `0x140013300`
- `0x14002ce98`
- `0x14005c210`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x14015da84`
- `0x14015dcb8`
- `0x14015dd2c`
- `0x14015dd84`
- `0x140178250`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14015db62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015db62`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14015db35`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14015db35`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14015db53`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14015db53`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dab6`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dbee`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dc27`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dab6`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dbee`
- `WIN32K!W32GetUserGdiSessionState` at `0x14015dc27`
- `WIN32K!W32GetUserSessionState` at `0x14015db44`
- `WIN32K!W32GetUserSessionState` at `0x14015dc53`
- `WIN32K!W32GetUserSessionState` at `0x14015dc6d`
- `WIN32K!W32GetUserSessionState` at `0x14015db44`
- `WIN32K!W32GetUserSessionState` at `0x14015dc53`
- `WIN32K!W32GetUserSessionState` at `0x14015dc6d`

## pseudocode

```c

```
