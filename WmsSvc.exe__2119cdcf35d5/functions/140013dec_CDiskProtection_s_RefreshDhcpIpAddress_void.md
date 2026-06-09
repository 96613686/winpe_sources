# CDiskProtection::s_RefreshDhcpIpAddress(void)

- ea: `0x140013dec`
- end: `0x140014182`
- name: `?s_RefreshDhcpIpAddress@CDiskProtection@@KAJXZ`
- size: `918`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000efa0`

## callees

- `0x140013dec`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140014142`
- `KERNEL32!CloseHandle` at `0x14001415c`
- `KERNEL32!CloseHandle` at `0x140014142`
- `KERNEL32!CloseHandle` at `0x14001415c`
- `KERNEL32!WaitForSingleObject` at `0x140014014`
- `KERNEL32!WaitForSingleObject` at `0x140014014`
- `KERNEL32!CreateProcessW` at `0x140013f77`
- `KERNEL32!CreateProcessW` at `0x140013f77`
- `KERNEL32!TerminateProcess` at `0x140014025`
- `KERNEL32!TerminateProcess` at `0x140014025`
- `KERNEL32!GetExitCodeProcess` at `0x140014085`
- `KERNEL32!GetExitCodeProcess` at `0x140014085`
- `KERNEL32!GetLastError` at `0x140013f85`
- `KERNEL32!GetLastError` at `0x140014093`
- `KERNEL32!GetLastError` at `0x140013f85`
- `KERNEL32!GetLastError` at `0x140014093`
- `KERNEL32!IsDebuggerPresent` at `0x140013eea`
- `KERNEL32!IsDebuggerPresent` at `0x140013fdc`
- `KERNEL32!IsDebuggerPresent` at `0x14001406c`
- `KERNEL32!IsDebuggerPresent` at `0x1400140ea`
- `KERNEL32!IsDebuggerPresent` at `0x140013eea`
- `KERNEL32!IsDebuggerPresent` at `0x140013fdc`
- `KERNEL32!IsDebuggerPresent` at `0x14001406c`
- `KERNEL32!IsDebuggerPresent` at `0x1400140ea`

## string_xrefs

- `0x140013e57`: `ipconfig.exe /renew`

## pseudocode

```c

```
