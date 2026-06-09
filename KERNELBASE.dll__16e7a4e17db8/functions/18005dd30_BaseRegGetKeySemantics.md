# BaseRegGetKeySemantics

- ea: `0x18005dd30`
- end: `0x18005e14a`
- name: `BaseRegGetKeySemantics`
- size: `1050`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCUNICODE_STRING Source)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180051e34`
- `0x18005a0c0`
- `0x18005bf10`
- `0x18005e150`
- `0x18005e2a0`
- `0x18005e890`
- `0x18005f0f8`
- `0x1800a6880`
- `0x1800b260c`
- `0x1801839dc`

## callees

- `0x18005dd30`
- `0x18012d038`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18005de83`
- `ntdll!RtlEqualUnicodeString` at `0x18005df01`
- `ntdll!RtlEqualUnicodeString` at `0x18005dfef`
- `ntdll!RtlEqualUnicodeString` at `0x18005de83`
- `ntdll!RtlEqualUnicodeString` at `0x18005df01`
- `ntdll!RtlEqualUnicodeString` at `0x18005dfef`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005dde5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005dde5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ddc4`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005de60`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ded3`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ddc4`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005de60`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ded3`
- `ntdll!NtQueryKey` at `0x18005df42`
- `ntdll!NtQueryKey` at `0x18005e0f2`
- `ntdll!NtQueryKey` at `0x18005df42`
- `ntdll!NtQueryKey` at `0x18005e0f2`
- `ntdll!RtlFreeHeap` at `0x18005e12a`
- `ntdll!RtlFreeHeap` at `0x18005e12a`
- `ntdll!RtlAllocateHeap` at `0x18005df89`
- `ntdll!RtlAllocateHeap` at `0x18005e0d1`
- `ntdll!RtlAllocateHeap` at `0x18005df89`
- `ntdll!RtlAllocateHeap` at `0x18005e0d1`

## string_xrefs

- `0x18005de49`: `\Registry\User`

## pseudocode

```c

```
