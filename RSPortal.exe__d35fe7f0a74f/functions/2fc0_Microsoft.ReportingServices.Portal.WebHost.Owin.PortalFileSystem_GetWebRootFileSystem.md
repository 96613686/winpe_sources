# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootFileSystem

- ea: `0x2fc0`
- end: `0x2fcb`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootFileSystem`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2eb0`

## callees

- `0x2fd0`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  call     string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir()
0x2fc5  newobj   instance void [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.PhysicalFileSystem::.ctor(string)
0x2fca  ret
```
