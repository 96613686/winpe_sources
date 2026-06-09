# AiRemoveProfilesForSession(ulong)

- ea: `0x18000d17c`
- end: `0x18000d238`
- name: `?AiRemoveProfilesForSession@@YAXK@Z`
- size: `188`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d040`

## callees

- `0x18000d17c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d20e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d20e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1ec`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d194`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d194`
- `ntdll!NtClose` at `0x18000d1e3`
- `ntdll!NtClose` at `0x18000d1e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d22a`
- `USERENV!UnloadUserProfile` at `0x18000d1d9`
- `USERENV!UnloadUserProfile` at `0x18000d1d9`

## pseudocode

```c

```
