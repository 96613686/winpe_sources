# Catalog::ResolveConfigXml(ushort const *,XmlReader *,ulong &)

- ea: `0x180041270`
- end: `0x180041804`
- name: `?ResolveConfigXml@Catalog@@AEAAPEBGPEBGPEAVXmlReader@@AEAK@Z`
- size: `1428`
- prototype: `WCHAR *__fastcall(Catalog *this, const unsigned __int16 *, struct XmlReader *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f8c8`

## callees

- `0x180005d10`
- `0x180008920`
- `0x18003c640`
- `0x180041270`
- `0x18004a900`
- `0x18010d8c6`
- `0x180112380`
- `0x1801ba182`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18004135c`
- `msvcrt!_wcsnicmp` at `0x18004135c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004176f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800417f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004176f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800417f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800414e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800414e2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041473`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041530`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041473`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180041530`

## string_xrefs

- `0x180041321`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x18004144e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800415f9`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180041648`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180041721`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c

```
