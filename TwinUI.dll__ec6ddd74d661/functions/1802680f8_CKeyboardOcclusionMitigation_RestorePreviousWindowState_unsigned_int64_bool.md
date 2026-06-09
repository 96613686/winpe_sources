# CKeyboardOcclusionMitigation::_RestorePreviousWindowState(unsigned __int64,bool)

- ea: `0x1802680f8`
- end: `0x180268396`
- name: `?_RestorePreviousWindowState@CKeyboardOcclusionMitigation@@AEAA_N_K_N@Z`
- size: `670`
- prototype: `bool __fastcall(CKeyboardOcclusionMitigation *__hidden this, unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1800a82f8`
- `0x180115a10`

## callees

- `0x180009dd0`
- `0x180082a48`
- `0x1800831f0`
- `0x180100230`
- `0x180100254`
- `0x180142e10`
- `0x180266e90`
- `0x180266ee0`
- `0x180266f28`
- `0x180267c24`
- `0x180267c68`
- `0x180267d78`
- `0x180267f18`
- `0x1802680f8`
- `0x1803bb010`

## import_xrefs

- `USER32!SetWindowPlacement` at `0x1802682a6`
- `USER32!SetWindowPlacement` at `0x180268385`
- `USER32!SetWindowPlacement` at `0x1802682a6`
- `USER32!SetWindowPlacement` at `0x180268385`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1802682f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1802682f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18026816b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18026816b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18026827a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18026827a`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x1802681d8`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x1802681d8`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18026821e`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18026821e`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18026819b`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18026819b`

## pseudocode

```c

```
