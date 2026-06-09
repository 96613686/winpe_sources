# LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(bool,LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18002a600`
- end: `0x18002a7ac`
- name: `??$LogNumObjects@V?$basic_zstring_view@_W@wil@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18002f25c`

## callees

- `0x18002a600`
- `0x1800309a4`
- `0x1800497c0`
- `0x18005060c`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002a6a3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a6e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a771`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a6a3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a6e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a771`
- `ntdll!RtlEnterCriticalSection` at `0x18002a63b`
- `ntdll!RtlEnterCriticalSection` at `0x18002a63b`
- `ntdll!RtlRaiseStatus` at `0x18002a6b5`
- `ntdll!RtlRaiseStatus` at `0x18002a6f8`
- `ntdll!RtlRaiseStatus` at `0x18002a783`
- `ntdll!RtlRaiseStatus` at `0x18002a6b5`
- `ntdll!RtlRaiseStatus` at `0x18002a6f8`
- `ntdll!RtlRaiseStatus` at `0x18002a783`

## string_xrefs

- `0x18002a745`: `Failed to rename to temp name from {0} to {1}`

## pseudocode

```c

```
