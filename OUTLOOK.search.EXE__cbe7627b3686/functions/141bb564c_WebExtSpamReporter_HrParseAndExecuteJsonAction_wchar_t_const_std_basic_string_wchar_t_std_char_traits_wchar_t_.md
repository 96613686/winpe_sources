# WebExtSpamReporter::HrParseAndExecuteJsonAction(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool &)

- ea: `0x141bb564c`
- end: `0x141bb6807`
- name: `?HrParseAndExecuteJsonAction@WebExtSpamReporter@@QEAAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEA_N@Z`
- size: `4539`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x141bb34d8`

## callees

- `0x140020eb0`
- `0x140020fdc`
- `0x1400211a0`
- `0x14002ba90`
- `0x14003f6e0`
- `0x14003f764`
- `0x14003f858`
- `0x14003f988`
- `0x140046fec`
- `0x140054fb0`
- `0x14006c9e4`
- `0x14007ab68`
- `0x1400dd0ac`
- `0x1400dd620`
- `0x1400dd670`
- `0x1400dd700`
- `0x140103fac`
- `0x14010abac`
- `0x140189340`
- `0x1401b3ff4`
- `0x1401b610c`
- `0x1401b634c`
- `0x1401cc5a0`
- `0x1402c4258`
- `0x14034d304`
- `0x140388500`
- `0x140418788`
- `0x1405049f0`
- `0x1406708f0`
- `0x140694b50`
- `0x1406ea4cc`
- `0x1407e9990`
- `0x1407eafb0`
- `0x1407eceb0`
- `0x1408a4aa0`
- `0x1409c47c4`
- `0x140a1e788`
- `0x140b961e8`
- `0x140e27110`
- `0x140f0fa1c`
- `0x141bb288c`
- `0x141bb33bc`
- `0x141bb3d04`
- `0x141bb5414`
- `0x141bb564c`
- `0x141bb72f0`
- `0x141bb76e0`
- `0x141bb8084`
- `0x141bbb8d0`
- `0x141bbe238`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb5aac`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb5b7e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb62a5`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb5aac`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb5b7e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x141bb62a5`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb578e`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb57c4`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb581d`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb59d9`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5a67`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5b1e`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5be7`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5ec4`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb6013`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb578e`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb57c4`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb581d`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb59d9`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5a67`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5b1e`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5be7`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb5ec4`
- `OLMAPI32!EtwTraceErrorTag` at `0x141bb6013`
- `ole32!CoTaskMemFree` at `0x141bb5bff`
- `ole32!CoTaskMemFree` at `0x141bb5c08`
- `ole32!CoTaskMemFree` at `0x141bb5f50`
- `ole32!CoTaskMemFree` at `0x141bb5f59`
- `ole32!CoTaskMemFree` at `0x141bb5bff`
- `ole32!CoTaskMemFree` at `0x141bb5c08`
- `ole32!CoTaskMemFree` at `0x141bb5f50`
- `ole32!CoTaskMemFree` at `0x141bb5f59`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bb5758`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141bb5758`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141bb576d`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141bb576d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb5b49`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb623b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb641b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb643f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb646b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb65c5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb6675`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb671a`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb5b49`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb623b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb641b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb643f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb646b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb65c5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb6675`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141bb671a`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141bb674c`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141bb674c`

## string_xrefs

- `0x141bb6326`: `MessageReadCommandSurface`
- `0x141bb6371`: `MessageReadCommandSurface`
- `0x141bb5aa5`: `deletedItemsFolder`
- `0x141bb655d`: `SpamTaskpaneLaunch`
- `0x141bb6474`: `CommandType`
- `0x141bb64a4`: `CommandType`
- `0x141bb6424`: `HrTaskpaneLaunch`
- `0x141bb629e`: `noMove`

## pseudocode

```c

```
