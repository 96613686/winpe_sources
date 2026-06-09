# WaasMedic::DefaultSettingsProvider::GetPluginSetting(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800223b0`
- end: `0x18002294f`
- name: `?GetPluginSetting@DefaultSettingsProvider@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@1@Z`
- size: `1439`
- prototype: `__int64 __usercall@<rax>(WaasMedic::DefaultSettingsProvider *this@<rcx>, char *@<rdx>, unsigned __int16 *@<r8>, __int64)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180022960`
- `0x180022b20`
- `0x180022d20`
- `0x180022e80`

## callees

- `0x180005ef1`
- `0x180009a54`
- `0x18000b308`
- `0x18000b6ec`
- `0x18000b9dc`
- `0x1800223b0`
- `0x180023064`
- `0x18002543c`
- `0x18002845c`
- `0x18002e294`
- `0x18002e2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002240f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002240f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800224e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022504`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022622`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002269f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022707`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002279c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800227ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002290e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002292c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800224e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022504`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022622`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002269f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800226db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022707`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002279c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800227ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002290e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002292c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022614`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022691`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002278e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800227e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002291e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022614`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022691`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800226f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002278e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800227e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022900`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002291e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002270f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002270f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227f6`
- `OLEAUT32!__imp_VariantInit` at `0x1800223ea`
- `OLEAUT32!__imp_VariantInit` at `0x18002241a`
- `OLEAUT32!__imp_VariantInit` at `0x180022450`
- `OLEAUT32!__imp_VariantInit` at `0x1800223ea`
- `OLEAUT32!__imp_VariantInit` at `0x18002241a`
- `OLEAUT32!__imp_VariantInit` at `0x180022450`
- `OLEAUT32!__imp_VariantClear` at `0x1800224a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800224c8`
- `OLEAUT32!__imp_VariantClear` at `0x180022596`
- `OLEAUT32!__imp_VariantClear` at `0x1800225c8`
- `OLEAUT32!__imp_VariantClear` at `0x180022681`
- `OLEAUT32!__imp_VariantClear` at `0x1800228d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800224a4`
- `OLEAUT32!__imp_VariantClear` at `0x1800224c8`
- `OLEAUT32!__imp_VariantClear` at `0x180022596`
- `OLEAUT32!__imp_VariantClear` at `0x1800225c8`
- `OLEAUT32!__imp_VariantClear` at `0x180022681`
- `OLEAUT32!__imp_VariantClear` at `0x1800228d2`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180022548`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180022548`

## string_xrefs

- `0x18002248e`: `Default setting for %s is not configured. Returning empty variant!`

## pseudocode

```c

```
