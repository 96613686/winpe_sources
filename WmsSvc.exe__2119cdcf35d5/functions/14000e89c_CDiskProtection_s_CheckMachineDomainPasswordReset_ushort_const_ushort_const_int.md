# CDiskProtection::s_CheckMachineDomainPasswordReset(ushort const *,ushort const *,int *)

- ea: `0x14000e89c`
- end: `0x14000ec25`
- name: `?s_CheckMachineDomainPasswordReset@CDiskProtection@@KAJPEBG0PEAH@Z`
- size: `905`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x140014210`

## callees

- `0x1400033e8`
- `0x14000e89c`
- `0x14000efa0`
- `0x140014384`
- `0x1400145b0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000ead9`
- `ADVAPI32!RegGetValueW` at `0x14000ead9`
- `KERNEL32!GetSystemTime` at `0x14000eb72`
- `KERNEL32!GetSystemTime` at `0x14000eb72`
- `KERNEL32!SystemTimeToFileTime` at `0x14000eb82`
- `KERNEL32!SystemTimeToFileTime` at `0x14000eb82`
- `KERNEL32!IsDebuggerPresent` at `0x14000e9ad`
- `KERNEL32!IsDebuggerPresent` at `0x14000eb37`
- `KERNEL32!IsDebuggerPresent` at `0x14000e9ad`
- `KERNEL32!IsDebuggerPresent` at `0x14000eb37`
- `ACTIVEDS!__imp_ADsGetObject` at `0x14000ea5a`
- `ACTIVEDS!__imp_ADsGetObject` at `0x14000ea5a`

## string_xrefs

- `0x14000eaa0`: `SYSTEM\CurrentControlSet\Services\NetLogon\Parameters`

## pseudocode

```c

```
