# OSIntegration::DEH::DownloadUploadClassExtensionHandler::DoesPackageContainPPLE(OSIntegration::Package const *)

- ea: `0x180017214`
- end: `0x180017457`
- name: `?DoesPackageContainPPLE@DownloadUploadClassExtensionHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@@Z`
- size: `579`
- prototype: `__int64 __fastcall(OSIntegration::DEH::DownloadUploadClassExtensionHandler *this, const struct OSIntegration::Package *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18005f418`

## callees

- `0x18000b3bc`
- `0x180016d1c`
- `0x180017214`
- `0x18009aff4`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800172b4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800172b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001724d`
- `OLEAUT32!__imp_SysFreeString` at `0x180017302`
- `OLEAUT32!__imp_SysFreeString` at `0x1800173ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180017421`
- `OLEAUT32!__imp_SysFreeString` at `0x180017434`
- `OLEAUT32!__imp_SysFreeString` at `0x18001724d`
- `OLEAUT32!__imp_SysFreeString` at `0x180017302`
- `OLEAUT32!__imp_SysFreeString` at `0x1800173ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180017421`
- `OLEAUT32!__imp_SysFreeString` at `0x180017434`

## string_xrefs

- `0x180017263`: `/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.backgroundTasks']/*[local-name()='BackgroundTasks' and @ServerName]`
- `0x1800172ad`: `/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.backgroundTasks']/*[local-name()='BackgroundTasks' and @ServerName]`
- `0x1800172e6`: `OSIntegration::DEH::DownloadUploadClassExtensionHandler::DoesPackageContainPPLE`
- `0x18001739e`: `OSIntegration::DEH::DownloadUploadClassExtensionHandler::DoesPackageContainPPLE`
- `0x180017406`: `OSIntegration::DEH::DownloadUploadClassExtensionHandler::DoesPackageContainPPLE`
- `0x1800172da`: `xpath.CopyFromString(xpathBackgroundTasksServerName)`
- `0x180017392`: `dom->selectSingleNode(xpath, node.ReleaseAndGetAddressOf())`
- `0x1800173fa`: `OSIntegration::Tools::GetXMLDOMFromPackage(const_cast<OSIntegration::Package*>(package), dom.ReleaseAndGetAddressOf())`

## pseudocode

```c

```
