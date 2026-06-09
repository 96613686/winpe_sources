# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings

- ea: `0x2f90`
- end: `0x2fb9`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2f10`

## callees

- `0x2f90`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider::get_Mappings()
0x2f96  ldarg.1
0x2f97  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x2f9c  brfalse.s loc_2FAB
0x2f9e  ldarg.0
0x2f9f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider::get_Mappings()
0x2fa4  ldarg.1
0x2fa5  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Remove(var<u1>)
0x2faa  pop
0x2fab  ldarg.0
0x2fac  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider::get_Mappings()
0x2fb1  ldarg.1
0x2fb2  ldarg.2
0x2fb3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x2fb8  ret
```
