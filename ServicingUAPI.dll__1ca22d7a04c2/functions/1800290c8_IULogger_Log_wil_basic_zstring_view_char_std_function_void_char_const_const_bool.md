# IULogger::Log(wil::basic_zstring_view<char>,std::function<void (char const *)> const &,bool)

- ea: `0x1800290c8`
- end: `0x1800292d7`
- name: `?Log@IULogger@@AEBAXV?$basic_zstring_view@D@wil@@AEBV?$function@$$A6AXPEBD@Z@std@@_N@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028fc0`

## callees

- `0x1800031d0`
- `0x180028ce0`
- `0x180028e20`
- `0x180028e8c`
- `0x1800290c8`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlGetCriticalSectionRecursionCount` at `0x180029257`
- `ntdll!RtlGetCriticalSectionRecursionCount` at `0x180029257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800292ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029113`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029113`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002928c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002928c`

## string_xrefs

- `0x1800291f5`: `onecore\base\cbs\mobile\iucommon\iulogger.cpp`
- `0x180029268`: `Hit recursive log message during logging!\n`

## pseudocode

```c

```
