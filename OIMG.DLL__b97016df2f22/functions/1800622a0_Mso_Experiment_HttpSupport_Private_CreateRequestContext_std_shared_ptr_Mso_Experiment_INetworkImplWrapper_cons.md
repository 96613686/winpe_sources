# Mso::Experiment::HttpSupport::Private::CreateRequestContext(std::shared_ptr<Mso::Experiment::INetworkImplWrapper> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800622a0`
- end: `0x180062730`
- name: `?CreateRequestContext@Private@HttpSupport@Experiment@Mso@@YA?AV?$TCntPtr@VIRequestContext@Http@Mso@@@4@AEBV?$shared_ptr@VINetworkImplWrapper@Experiment@Mso@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062730`

## callees

- `0x180013080`
- `0x18001373c`
- `0x180037a58`
- `0x1800622a0`
- `0x18009bdec`
- `0x180128288`
- `0x18056bd00`
- `0x18056d1b0`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180062481`
- `KERNEL32!InitOnceBeginInitialize` at `0x180062481`
- `KERNEL32!InitOnceComplete` at `0x1800624da`
- `KERNEL32!InitOnceComplete` at `0x1800624da`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800623e3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062443`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062632`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062692`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800623e3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062443`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062632`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180062692`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006243c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006268b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006243c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006268b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18006248b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18006248b`

## string_xrefs

- `0x180062377`: `HttpSupport::CreateRequestContext > Failed to create HTTP request context.`
- `0x1800625c6`: `HttpSupport::CreateRequestContext > Failed to initialize HTTP request context.`
- `0x180062557`: `wzUserAgent`

## pseudocode

```c

```
