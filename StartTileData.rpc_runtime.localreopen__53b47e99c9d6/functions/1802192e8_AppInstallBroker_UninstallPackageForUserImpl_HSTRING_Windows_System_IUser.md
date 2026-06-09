# AppInstallBroker::UninstallPackageForUserImpl(HSTRING__ *,Windows::System::IUser *)

- ea: `0x1802192e8`
- end: `0x1802196b3`
- name: `?UninstallPackageForUserImpl@AppInstallBroker@@AEAAJPEAUHSTRING__@@PEAUIUser@System@Windows@@@Z`
- size: `971`
- prototype: `int(AppInstallBroker *__hidden this, HSTRING, struct Windows::System::IUser *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180218e60`
- `0x180219290`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004ffc0`
- `0x180201e50`
- `0x18020f690`
- `0x1802192e8`
- `0x180219b4c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180219336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180219336`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18021938d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18021938d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18021942c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180219569`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18021942c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180219569`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802194d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802194d9`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18021934a`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18021934a`

## string_xrefs

- `0x1802193c8`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180219473`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802194ea`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021957a`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021962b`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`

## pseudocode

```c

```
