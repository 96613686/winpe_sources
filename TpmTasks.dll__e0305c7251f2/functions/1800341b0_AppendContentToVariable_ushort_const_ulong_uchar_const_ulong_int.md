# AppendContentToVariable(ushort const *,ulong,uchar * const,ulong,int *)

- ea: `0x1800341b0`
- end: `0x18003430b`
- name: `?AppendContentToVariable@@YAJPEBGKQEAEKPEAH@Z`
- size: `347`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int, PVOID Value, PULONG ReturnLength, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180037338`

## callees

- `0x1800078b0`
- `0x1800341b0`
- `0x18003720c`
- `0x180039440`
- `0x180039bbc`
- `0x180039ec0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034212`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034293`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800342a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800342bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034212`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034293`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800342a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800342bb`
- `ntdll!RtlInitUnicodeString` at `0x18003425e`
- `ntdll!RtlInitUnicodeString` at `0x18003425e`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18003427a`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18003427a`

## string_xrefs

- `0x18003421c`: `KEK update, changing namespace`

## pseudocode

```c

```
