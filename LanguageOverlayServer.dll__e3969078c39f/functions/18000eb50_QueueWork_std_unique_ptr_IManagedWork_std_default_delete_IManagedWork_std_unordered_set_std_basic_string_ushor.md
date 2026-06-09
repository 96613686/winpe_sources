# QueueWork(std::unique_ptr<IManagedWork,std::default_delete<IManagedWork>>,std::unordered_set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,WorkPriority)

- ea: `0x18000eb50`
- end: `0x18000ed02`
- name: `?QueueWork@@YAXV?$unique_ptr@VIManagedWork@@U?$default_delete@VIManagedWork@@@std@@@std@@AEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@W4WorkPriority@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001358c`
- `0x1800179d8`
- `0x1800180d8`
- `0x180025ce0`
- `0x180025f70`
- `0x180032618`
- `0x180032c80`
- `0x1800373fc`
- `0x18003cb70`
- `0x18003f280`

## callees

- `0x180003a00`
- `0x18000eb50`
- `0x180011334`
- `0x180012ae0`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18000ec1b`
- `msvcp_win!_Mtx_unlock` at `0x18000ec1b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ebbb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ebd7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ebbb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000ebd7`
- `msvcp_win!_Mtx_lock` at `0x18000ebac`
- `msvcp_win!_Mtx_lock` at `0x18000ebac`

## string_xrefs

- `0x18000ecf0`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c

```
