# LicenseProxyService::SendRequestAndWaitForResponse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ProxySettings const &,HttpRequest &)

- ea: `0x180006cec`
- end: `0x180006ff5`
- name: `?SendRequestAndWaitForResponse@LicenseProxyService@@AEAA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z`
- size: `777`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180007094`
- `0x18005abc0`
- `0x18005b840`
- `0x18005d930`
- `0x18005e044`
- `0x18005e988`

## callees

- `0x18000655c`
- `0x180006cec`
- `0x180030294`
- `0x180033c04`
- `0x1800593bc`
- `0x180075e60`
- `0x18009951c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006d3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006d3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006d69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006d69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006da5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006da5`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180006f95`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180006f95`

## string_xrefs

- `0x180006ec2`: `{"code":"BadRequest","data":[],"details":[],"innererror":{"faultcode":%d,"code":"MockFailure","data":["d02de2c9-dbec-44ac-ae7f-40dcaabe02a9"],"details":[],"message":"Forced service failure."},"message":"The client asked for a mock error from the service.","source":"LicensingFD"}`

## pseudocode

```c

```
