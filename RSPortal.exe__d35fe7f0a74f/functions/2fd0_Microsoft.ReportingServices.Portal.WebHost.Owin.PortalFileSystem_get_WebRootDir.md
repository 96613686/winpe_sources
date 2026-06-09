# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir

- ea: `0x2fd0`
- end: `0x2fe0`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1db0`
- `0x2eb0`
- `0x2fc0`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x2fd5  ldstr    aWebrootdir// "WebRootDir"
0x2fda  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2fdf  ret
```
