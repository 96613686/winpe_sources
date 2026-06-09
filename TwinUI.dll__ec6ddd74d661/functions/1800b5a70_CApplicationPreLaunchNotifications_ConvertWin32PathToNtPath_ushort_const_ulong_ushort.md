# CApplicationPreLaunchNotifications::ConvertWin32PathToNtPath(ushort const *,ulong,ushort *)

- ea: `0x1800b5a70`
- end: `0x1800b5cb4`
- name: `?ConvertWin32PathToNtPath@CApplicationPreLaunchNotifications@@AEAAJPEBGKPEAG@Z`
- size: `580`
- prototype: `int(CApplicationPreLaunchNotifications *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800ce340`

## callees

- `0x18005a16c`
- `0x1800b5a70`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b5aa5`
- `ntdll!RtlInitUnicodeString` at `0x1800b5aa5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b5abe`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b5abe`
- `ntdll!NtCreateFile` at `0x1800b5b53`
- `ntdll!NtCreateFile` at `0x1800b5b53`
- `ntdll!NtQueryObject` at `0x1800b5b8c`
- `ntdll!NtQueryObject` at `0x1800b5b8c`
- `ntdll!RtlFreeHeap` at `0x1800b5bc0`
- `ntdll!RtlFreeHeap` at `0x1800b5c56`
- `ntdll!RtlFreeHeap` at `0x1800b5bc0`
- `ntdll!RtlFreeHeap` at `0x1800b5c56`
- `ntdll!RtlAllocateHeap` at `0x1800b5be3`
- `ntdll!RtlAllocateHeap` at `0x1800b5be3`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800b5c19`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800b5c19`
- `ntdll!NtClose` at `0x1800b5c72`
- `ntdll!NtClose` at `0x1800b5c72`
- `ntdll!RtlFreeUnicodeString` at `0x1800b5c89`
- `ntdll!RtlFreeUnicodeString` at `0x1800b5c89`

## pseudocode

```c

```
