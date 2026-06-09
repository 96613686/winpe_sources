# CCbsExecutionPackage::ActuallyGatherFileWithDeltas(wchar_t const *,IDefinitionIdentity *,void *,FileContainer const *,unsigned __int64,IServicingStagerFilePathFetcherCallback *)

- ea: `0x180156478`
- end: `0x180157094`
- name: `?ActuallyGatherFileWithDeltas@CCbsExecutionPackage@@QEAAJPEB_WPEAUIDefinitionIdentity@@PEAXPEBUFileContainer@@_KPEAVIServicingStagerFilePathFetcherCallback@@@Z`
- size: `3100`
- prototype: `int(CCbsExecutionPackage *__hidden this, const wchar_t *, struct IDefinitionIdentity *, void *, const struct FileContainer *, unsigned __int64, struct IServicingStagerFilePathFetcherCallback *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180157b64`

## callees

- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x1800261e0`
- `0x180033f58`
- `0x18003404c`
- `0x180042448`
- `0x18004854c`
- `0x180048fc0`
- `0x180049bec`
- `0x180049f58`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a4b58`
- `0x1800eb500`
- `0x1800eb920`
- `0x180126dd8`
- `0x180155db4`
- `0x180155eb4`
- `0x180156478`
- `0x1801572bc`
- `0x1801582e4`
- `0x1801583b8`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180156865`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180156855`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180156855`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180156788`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180156885`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180156788`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180156885`

## string_xrefs

- `0x180156505`: `Failed to impersonate user while gather files for package: {}`
- `0x180156c96`: `Failed to retrieve package component file express sandbox path`
- `0x180156cf1`: `Failed to retrieve package component file reservicing sandbox path`
- `0x180156d62`: `Failed to impersonate user while gather files for component identity: {}`

## pseudocode

```c

```
