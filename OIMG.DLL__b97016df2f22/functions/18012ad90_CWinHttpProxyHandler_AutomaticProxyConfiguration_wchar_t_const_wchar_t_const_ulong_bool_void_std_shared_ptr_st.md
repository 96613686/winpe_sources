# CWinHttpProxyHandler::AutomaticProxyConfiguration(wchar_t const *,wchar_t const *,ulong,bool,void * *,std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &,bool &)

- ea: `0x18012ad90`
- end: `0x18012b23f`
- name: `?AutomaticProxyConfiguration@CWinHttpProxyHandler@@AEAAKPEB_W0K_NPEAPEAXAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@AEA_N@Z`
- size: `1199`
- prototype: `__int64 __usercall@<rax>(CWinHttpProxyHandler *this@<rcx>, LPCWSTR lpcwszUrl@<rdx>, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180129614`

## callees

- `0x180012aa0`
- `0x180012ccc`
- `0x180016ee8`
- `0x1800a17ec`
- `0x18010d0f4`
- `0x180111e40`
- `0x18012a8b0`
- `0x18012ac50`
- `0x18012ad90`
- `0x18012b430`
- `0x18056bd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012b210`
- `KERNEL32!GetLastError` at `0x18012b210`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012af16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b06c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b185`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012af16`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b06c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b185`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012af0f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b065`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b17e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012af0f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b065`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b17e`
- `WINHTTP!WinHttpSetOption` at `0x18012b206`
- `WINHTTP!WinHttpSetOption` at `0x18012b206`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18012af9f`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18012af9f`

## string_xrefs

- `0x18012ae9f`: `InitSession detected proxy, and auto config URL`

## pseudocode

```c

```
