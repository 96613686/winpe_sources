# CMDMPushConfiguration::GetFromRegistry(ushort const *,tagVARIANT *)

- ea: `0x140025b18`
- end: `0x140025dbf`
- name: `?GetFromRegistry@CMDMPushConfiguration@@AEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `679`
- prototype: `int(CMDMPushConfiguration *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x14002478c`
- `0x1400248b4`
- `0x140025a1c`
- `0x140025dc8`
- `0x140025eb0`
- `0x140025fac`
- `0x1400260f8`
- `0x1400266b4`

## callees

- `0x1400042f0`
- `0x1400045a8`
- `0x140004660`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a0fc`
- `0x140025b18`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140025b8b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140025b8b`
- `OLEAUT32!__imp_SysAllocString` at `0x140025d35`
- `OLEAUT32!__imp_SysAllocString` at `0x140025d35`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025c12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025cb3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025c12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140025cb3`

## pseudocode

```c

```
