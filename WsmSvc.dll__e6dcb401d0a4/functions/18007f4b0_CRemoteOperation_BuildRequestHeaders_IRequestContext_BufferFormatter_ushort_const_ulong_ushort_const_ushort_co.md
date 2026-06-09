# CRemoteOperation::BuildRequestHeaders(IRequestContext *,BufferFormatter &,ushort const *,ulong,ushort const *,ushort const *,unsigned __int64,ulong,int)

- ea: `0x18007f4b0`
- end: `0x18008014f`
- name: `?BuildRequestHeaders@CRemoteOperation@@IEAAHPEAVIRequestContext@@AEAVBufferFormatter@@PEBGK22_KKH@Z`
- size: `3231`
- prototype: `__int64 __fastcall(CRemoteOperation *__hidden this, struct IRequestContext *, struct BufferFormatter *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007ed28`
- `0x18007eec0`
- `0x180153f18`

## callees

- `0x180005d10`
- `0x18007ec20`
- `0x18007f4b0`
- `0x180080158`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fa9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fd8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fa9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fd8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa15`
- `ntdll!EtwEventProviderEnabled` at `0x18007fa8d`
- `ntdll!EtwEventProviderEnabled` at `0x18007fa8d`

## string_xrefs

- `0x18007ff12`: `<w:OptionSet xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`
- `0x18008002e`: `" MustComply="true"`
- `0x18007f940`: `</a:MessageID><w:Locale xml:lang="`
- `0x18007f821`: `<a:ReplyTo><a:Address s:mustUnderstand="true">http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</a:Address></a:ReplyTo><a:Action s:mustUnderstand="true">`
- `0x18007f9a9`: `<p:DataLocale xml:lang="`
- `0x18007f791`: `<m:MachineID xmlns:m="http://schemas.microsoft.com/wbem/wsman/1/machineid" s:mustUnderstand="false">`

## pseudocode

```c

```
