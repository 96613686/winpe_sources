# FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)

- ea: `0x180046744`
- end: `0x180046865`
- name: `?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z`
- size: `289`
- prototype: `int(FwService *__hidden this, struct _tag_FW_ADDRESSES *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180046dc0`
- `0x180046ea0`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180046744`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004680f`
- `fwbase!FwReportReturnError` at `0x180046836`
- `fwbase!FwReportReturnError` at `0x18004680f`
- `fwbase!FwReportReturnError` at `0x180046836`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800467c5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004681a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800467c5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004681a`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x1800467b4`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x1800467b4`

## string_xrefs

- `0x180046808`: `FwService::GetRemoteAddrs`
- `0x18004682f`: `FwService::GetRemoteAddrs`

## pseudocode

```c

```
