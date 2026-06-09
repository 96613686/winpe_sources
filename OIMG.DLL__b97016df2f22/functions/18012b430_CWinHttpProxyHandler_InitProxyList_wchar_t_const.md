# CWinHttpProxyHandler::InitProxyList(wchar_t const *)

- ea: `0x18012b430`
- end: `0x18012b894`
- name: `?InitProxyList@CWinHttpProxyHandler@@QEAA_NPEB_W@Z`
- size: `1124`
- prototype: `bool __fastcall(CWinHttpProxyHandler *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18012ad90`

## callees

- `0x180012aa0`
- `0x180012ccc`
- `0x180016ee8`
- `0x180058fb4`
- `0x1800a17ec`
- `0x1800c6410`
- `0x18012a8b0`
- `0x18012b430`
- `0x18012bf10`
- `0x18015c2ac`
- `0x18015c6cc`
- `0x18056bd00`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x18012b6a4`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x18012b6a4`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012b4bd`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012b4d9`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012b4bd`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18012b4d9`
- `MSVCP140!_Mtx_lock` at `0x18012b4ae`
- `MSVCP140!_Mtx_lock` at `0x18012b4ae`
- `MSVCP140!_Mtx_unlock` at `0x18012b684`
- `MSVCP140!_Mtx_unlock` at `0x18012b830`
- `MSVCP140!_Mtx_unlock` at `0x18012b684`
- `MSVCP140!_Mtx_unlock` at `0x18012b830`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18012b699`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18012b699`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b56c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b5b8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b67b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b70b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b812`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b56c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b5b8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b67b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b70b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012b812`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b5b1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b674`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b80b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b5b1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b674`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012b80b`

## string_xrefs

- `0x18012b7b1`: `The proxy list was cached using the given proxy string from WinHttpGetProxyForUrl`
- `0x18012b490`: `Should not be trying to initialize the proxy list when it's already been initialized`

## pseudocode

```c

```
