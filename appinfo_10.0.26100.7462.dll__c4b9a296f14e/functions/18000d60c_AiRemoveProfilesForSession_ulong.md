# AiRemoveProfilesForSession(ulong)

- ea: `0x18000d60c`
- end: `0x18000d6fa`
- name: `?AiRemoveProfilesForSession@@YAXK@Z`
- size: `238`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d540`

## callees

- `0x18000d60c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d6c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d6c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d69a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d69a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d624`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d624`
- `ntdll!NtClose` at `0x18000d68b`
- `ntdll!NtClose` at `0x18000d68b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d6e7`
- `USERENV!UnloadUserProfile` at `0x18000d67b`
- `USERENV!UnloadUserProfile` at `0x18000d67b`

## pseudocode

```c

```
