# Microsoft::Windows::Autopilot::Diagnostics::EtwDecoder::DecodeExportedEvtRecord(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::unique_ptr<std::vector<std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::RawEvent>,std::allocator<std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::RawEvent>>>,std::default_delete<std::vector<std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::RawEvent>,std::allocator<std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::RawEvent>>>>> &)

- ea: `0x1801bad2c`
- end: `0x1801baf45`
- name: `?DecodeExportedEvtRecord@EtwDecoder@Diagnostics@Autopilot@Windows@Microsoft@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@V?$vector@V?$shared_ptr@VRawEvent@Diagnostics@Autopilot@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VRawEvent@Diagnostics@Autopilot@Windows@Microsoft@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$shared_ptr@VRawEvent@Diagnostics@Autopilot@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VRawEvent@Diagnostics@Autopilot@Windows@Microsoft@@@std@@@2@@std@@@2@@7@@Z`
- size: `537`
- prototype: `int __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1801baf4c`

## callees

- `0x18000b820`
- `0x18000bd0c`
- `0x18000c414`
- `0x180077384`
- `0x18008019c`
- `0x1800806b0`
- `0x18019c7cc`
- `0x1801a2198`
- `0x1801ba444`
- `0x1801ba574`
- `0x1801baabc`
- `0x1801bad2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801badd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801badd9`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1801bae25`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1801bae3d`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1801bae25`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x1801bae3d`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtQuery` at `0x1801bad92`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtQuery` at `0x1801bad92`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtNext` at `0x1801badcb`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtNext` at `0x1801badcb`

## pseudocode

```c

```
