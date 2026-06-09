# GetExecutionContext(_MI_Context *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180245690`
- end: `0x180245868`
- name: `?GetExecutionContext@@YA?AW4_MI_Result@@PEAU_MI_Context@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `472`
- prototype: `__int64 __fastcall(MI_Context *context, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180241bdc`

## callees

- `0x1802445d4`
- `0x1802449c8`
- `0x180245690`
- `0x180245a44`
- `0x180245eb8`
- `0x18024d160`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1802457d6`
- `msvcrt!_wcsicmp` at `0x1802457d6`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x18024573d`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x18024573d`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18024576d`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18024576d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180245792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180245792`

## pseudocode

```c

```
