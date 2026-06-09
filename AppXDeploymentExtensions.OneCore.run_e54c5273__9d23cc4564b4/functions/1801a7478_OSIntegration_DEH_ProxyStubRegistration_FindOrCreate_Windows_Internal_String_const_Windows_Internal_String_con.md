# OSIntegration::DEH::ProxyStubRegistration::FindOrCreate(Windows::Internal::String const &,Windows::Internal::String const &,bool,OSIntegration::DEH::Collectors *,OSIntegration::DEH::ProxyStubRegistration * *)

- ea: `0x1801a7478`
- end: `0x1801a76fd`
- name: `?FindOrCreate@ProxyStubRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@0_NPEAVCollectors@23@PEAPEAU123@@Z`
- size: `645`
- prototype: `__int64 __usercall@<rax>(const struct Windows::Internal::String *@<rcx>, const struct Windows::Internal::String *@<rdx>, bool@<r8b>, struct OSIntegration::DEH::Collectors *@<r9>, struct OSIntegration::DEH::ProxyStubRegistration **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003df60`

## callees

- `0x18000b3bc`
- `0x18007f800`
- `0x18008f538`
- `0x180098ed0`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800cdcbc`
- `0x1800eb644`
- `0x18012ba10`
- `0x1801a7478`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801a7632`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801a7632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a74b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a7611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a7685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a76a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a74b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a7611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a7685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a76a9`

## string_xrefs

- `0x1801a7591`: `collectors->GetActivationCatalogCollector()->AddProxyStubRegistration( clsid, registrationImpl.Get())`
- `0x1801a74f6`: `OSIntegration::DEH::ProxyStubRegistration::FindOrCreate`
- `0x1801a7557`: `OSIntegration::DEH::ProxyStubRegistration::FindOrCreate`
- `0x1801a765f`: `OSIntegration::DEH::ProxyStubRegistration::FindOrCreate`
- `0x1801a76dd`: `OSIntegration::DEH::ProxyStubRegistration::FindOrCreate`
- `0x1801a7544`: `ProxyStubRegistration_Impl::Create(dllPath, isPackageRelativePath, &registrationImpl)`
- `0x1801a74ea`: `collectors->GetActivationCatalogCollector()->RetrieveProxyStubRegistration(clsid, &found, &registration)`

## pseudocode

```c

```
