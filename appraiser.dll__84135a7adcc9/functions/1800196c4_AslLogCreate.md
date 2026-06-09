# AslLogCreate

- ea: `0x1800196c4`
- end: `0x18001998a`
- name: `AslLogCreate`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003bd0`

## callees

- `0x180008570`
- `0x180019594`
- `0x1800196c4`
- `0x18001a154`
- `0x18001a208`
- `0x18001c6fc`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019803`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180019803`
- `ntdll!RtlInitializeCriticalSection` at `0x18001972e`
- `ntdll!RtlInitializeCriticalSection` at `0x18001972e`
- `ntdll!RtlAllocateHeap` at `0x180019707`
- `ntdll!RtlAllocateHeap` at `0x180019707`
- `ntdll!EtwEventRegister` at `0x180019790`
- `ntdll!EtwEventRegister` at `0x180019790`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180019869`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001988a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180019869`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001988a`
- `KERNEL32!GetModuleFileNameW` at `0x1800197a9`
- `KERNEL32!GetModuleFileNameW` at `0x1800197a9`
- `KERNEL32!LoadLibraryExW` at `0x18001982e`
- `KERNEL32!LoadLibraryExW` at `0x18001982e`
- `KERNEL32!FreeLibrary` at `0x1800197d0`
- `KERNEL32!FreeLibrary` at `0x1800197d0`
- `KERNEL32!GetCurrentProcessId` at `0x1800198cb`
- `KERNEL32!GetCurrentProcessId` at `0x1800198cb`
- `KERNEL32!GetProcAddress` at `0x180019846`
- `KERNEL32!GetProcAddress` at `0x180019846`
- `KERNEL32!GetLastError` at `0x1800197af`
- `KERNEL32!GetLastError` at `0x1800197af`

## string_xrefs

- `0x180019821`: `ntdll.dll`
- `0x180019862`: `%OSDataDrive%\SystemData\Temp`
- `0x180019883`: `%TEMP%`
- `0x1800198ad`: `%s\Temp`

## pseudocode

```c

```
