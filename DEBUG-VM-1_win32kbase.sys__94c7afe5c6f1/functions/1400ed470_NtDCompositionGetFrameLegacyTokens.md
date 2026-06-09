# NtDCompositionGetFrameLegacyTokens

- ea: `0x1400ed470`
- end: `0x1400ed7b5`
- name: `NtDCompositionGetFrameLegacyTokens`
- size: `837`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400411c0`
- `0x1400ed470`
- `0x1401add1c`
- `0x1401c6588`
- `0x140238bf0`
- `0x140239180`
- `0x1402bd054`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400ed511`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ed511`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed526`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed564`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed5c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed526`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed564`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ed5c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed59e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed601`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed722`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed59e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed601`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ed722`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400ed538`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400ed538`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ed5d8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ed5d8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ed575`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ed575`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ed592`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ed5f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ed592`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ed5f5`
- `WIN32K!W32GetDCompSessionState` at `0x1400ed5af`
- `WIN32K!W32GetDCompSessionState` at `0x1400ed5af`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4fe`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4fe`

## pseudocode

```c

```
