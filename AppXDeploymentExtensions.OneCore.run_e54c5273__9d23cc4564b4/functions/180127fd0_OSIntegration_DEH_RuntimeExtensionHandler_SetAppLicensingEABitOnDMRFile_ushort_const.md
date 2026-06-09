# OSIntegration::DEH::RuntimeExtensionHandler::SetAppLicensingEABitOnDMRFile(ushort const *)

- ea: `0x180127fd0`
- end: `0x1801281cb`
- name: `?SetAppLicensingEABitOnDMRFile@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJPEBG@Z`
- size: `507`
- prototype: `__int64 __fastcall(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18007d650`

## callees

- `0x18001c348`
- `0x18001c3c8`
- `0x180098bf4`
- `0x1800a5970`
- `0x1800f0260`
- `0x1800f10e4`
- `0x180127fd0`
- `0x180128244`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801280b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801280b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801280a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1801280a7`
- `ntdll!ZwClose` at `0x180128174`
- `ntdll!ZwClose` at `0x180128174`
- `ntdll!ZwOpenFile` at `0x180128121`
- `ntdll!ZwOpenFile` at `0x180128121`
- `ntdll!ZwSetEaFile` at `0x18012815e`
- `ntdll!ZwSetEaFile` at `0x18012815e`
- `ntdll!RtlInitUnicodeString` at `0x1801280c5`
- `ntdll!RtlInitUnicodeString` at `0x1801280c5`

## string_xrefs

- `0x18012801e`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x180128137`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x180128185`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`

## pseudocode

```c

```
