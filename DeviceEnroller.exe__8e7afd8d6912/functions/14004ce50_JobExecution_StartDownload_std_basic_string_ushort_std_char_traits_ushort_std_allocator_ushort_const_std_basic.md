# JobExecution::StartDownload(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_Job &)

- ea: `0x14004ce50`
- end: `0x14004d457`
- name: `?StartDownload@JobExecution@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU_Job@@@Z`
- size: `1543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004a9a4`

## callees

- `0x1400042f0`
- `0x140005c81`
- `0x1400095b4`
- `0x14001e838`
- `0x14003553c`
- `0x1400429ac`
- `0x14004c794`
- `0x14004ce50`
- `0x14004e9f8`
- `0x14004f088`
- `0x14004f4d0`
- `0x14004f5e4`
- `0x140050128`
- `0x14005d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14004d399`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14004d399`
- `RPCRT4!UuidToStringW` at `0x14004d2ce`
- `RPCRT4!UuidToStringW` at `0x14004d2ce`
- `RPCRT4!RpcStringFreeW` at `0x14004d3ad`
- `RPCRT4!RpcStringFreeW` at `0x14004d3ad`

## string_xrefs

- `0x14004cece`: `JobExecution::StartDownload -  Failed to getJobConfig`
- `0x14004cef9`: `CreateBITSJob`
- `0x14004d1a0`: `Failed to setup MDM cert or AAD Token, ignore failure as job URL is not HTTPS`
- `0x14004d18f`: `Failed to setup MDM cert or AAD Token when job URL is HTTPS.`

## pseudocode

```c

```
