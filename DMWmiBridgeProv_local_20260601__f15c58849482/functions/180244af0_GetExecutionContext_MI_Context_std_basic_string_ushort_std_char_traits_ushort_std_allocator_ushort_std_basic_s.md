# GetExecutionContext(_MI_Context *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180244af0`
- end: `0x180244ce4`
- name: `?GetExecutionContext@@YA?AW4_MI_Result@@PEAU_MI_Context@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `500`
- prototype: `__int64 __fastcall(MI_Context *context)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180240f0c`

## callees

- `0x1802439ec`
- `0x180243de8`
- `0x180244af0`
- `0x180244ed8`
- `0x18024539c`
- `0x18024cd20`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180244c4b`
- `msvcrt!_wcsicmp` at `0x180244c4b`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180244b9d`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180244b9d`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180244bd3`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180244bd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244bfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180244bfe`

## pseudocode

```c

```
