# OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x1801bdf34`
- end: `0x1801be515`
- name: `?CreateCompatibilityEntries@ComTypeLibRegistration@DEH@OSIntegration@@AEBAJPEBUICollectorPackageInformation@23@@Z`
- size: `1505`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ComTypeLibRegistration *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801cb280`

## callees

- `0x180067050`
- `0x180077608`
- `0x18009549c`
- `0x1800b10c0`
- `0x1800b1324`
- `0x1800b1374`
- `0x1800b13a8`
- `0x1800b1a0c`
- `0x1800b1b74`
- `0x1800b2f30`
- `0x1800b302c`
- `0x1800b30e8`
- `0x1800d5520`
- `0x1800ebdf0`
- `0x1800f0260`
- `0x1800f34b0`
- `0x1801acb14`
- `0x1801adc20`
- `0x1801ba7cc`
- `0x1801bdf34`
- `0x1801c4364`
- `0x1801c5ad4`
- `0x1801d4be4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be34f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be34f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801be437`

## string_xrefs

- `0x1801be0ac`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801be1ad`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801be388`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801be4a5`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801be099`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win32Path.Value.GetRawBuffer(nullptr), absolutePath)`
- `0x1801be0a5`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x1801be1a6`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x1801be381`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x1801be49e`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x1801be492`: `registryCompatibilityCollector->AddKey( (_properties.HasMachineScope.GetValueOrDefault(false) ? Scope::Machine : Scope::User), Internal::GetTypeLibVersionKeyPath(_id, _versionNumber.GetRawBuffer(nullptr)), std::move(typeLibVersionKey))`
- `0x1801be19a`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win64Path.Value.GetRawBuffer(nullptr), absolutePath)`
- `0x1801be375`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.HelpDirectory.Value.GetRawBuffer(nullptr), absolutePath)`

## pseudocode

```c

```
