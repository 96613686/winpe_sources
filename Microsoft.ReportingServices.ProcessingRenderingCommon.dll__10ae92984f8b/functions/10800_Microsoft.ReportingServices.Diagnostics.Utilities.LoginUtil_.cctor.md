# Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::.cctor

- ea: `0x10800`
- end: `0x10829`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::.cctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x107e0`

## string_xrefs

- `0x10805`: `LocalService`
- `0x10819`: `NetworkService`

## pseudocode

```c

```

## disassembly

```asm
0x10800  ldstr    aNtAuthority// "NT Authority"
0x10805  ldstr    aLocalservice// "LocalService"
0x1080a  call     string Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::MakeAccount(string domain, string userName)
0x1080f  stsfld   string Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::LocalServiceAccount
0x10814  ldstr    aNtAuthority// "NT Authority"
0x10819  ldstr    aNetworkservice// "NetworkService"
0x1081e  call     string Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::MakeAccount(string domain, string userName)
0x10823  stsfld   string Microsoft.ReportingServices.Diagnostics.Utilities.LoginUtil::NetworkServiceAccount
0x10828  ret
```
