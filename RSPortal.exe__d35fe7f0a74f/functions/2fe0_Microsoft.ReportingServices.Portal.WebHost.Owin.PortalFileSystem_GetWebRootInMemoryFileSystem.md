# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootInMemoryFileSystem

- ea: `0x2fe0`
- end: `0x2ff7`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootInMemoryFileSystem`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2eb0`

## string_xrefs

- `0x2fe0`: `Microsoft.ReportingServices.Portal.Web.v2.wwwroot`
- `0x2fe6`: `Microsoft.ReportingServices.Portal.Web`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.Portal.Web."...
0x2fe5  stloc.0
0x2fe6  ldstr    aMicrosoftRepor_0// "Microsoft.ReportingServices.Portal.Web"
0x2feb  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2ff0  ldloc.0
0x2ff1  newobj   instance void [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.EmbeddedResourceFileSystem::.ctor(class [mscorlib]System.Reflection.Assembly, string)
0x2ff6  ret
```
