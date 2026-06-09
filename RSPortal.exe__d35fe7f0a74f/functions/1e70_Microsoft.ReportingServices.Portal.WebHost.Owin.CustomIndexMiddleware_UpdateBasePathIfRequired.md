# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::UpdateBasePathIfRequired

- ea: `0x1e70`
- end: `0x1f3c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::UpdateBasePathIfRequired`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1d10`

## callees

- `0x1e70`

## pseudocode

```c

```

## disassembly

```asm
0x1e70  ldarg.2
0x1e71  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1e76  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0x1e7b  stloc.0
0x1e7c  ldloca.s 0
0x1e7e  call     instance bool [Microsoft.Owin]Microsoft.Owin.PathString::get_HasValue()
0x1e83  brfalse  loc_1F3A
0x1e88  ldarg.0
0x1e89  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_serverConfiguration
0x1e8e  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1e93  callvirt instance string [mscorlib]System.String::ToLower()
0x1e98  ldarg.2
0x1e99  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1e9e  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0x1ea3  stloc.0
0x1ea4  ldloca.s 0
0x1ea6  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x1eab  callvirt instance string [mscorlib]System.String::ToLower()
0x1eb0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1eb5  brfalse  loc_1F3A
0x1eba  ldarg.0
0x1ebb  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_serverConfiguration
0x1ec0  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1ec5  ldarg.2
0x1ec6  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1ecb  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0x1ed0  stloc.0
0x1ed1  ldloca.s 0
0x1ed3  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x1ed8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1edd  brfalse.s loc_1F3A
0x1edf  ldstr    aBaseHref0// "<base href=\"/{0}/\" >"
0x1ee4  ldarg.0
0x1ee5  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_serverConfiguration
0x1eea  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x1eef  call     string [mscorlib]System.String::Format(string, object)
0x1ef4  ldstr    asc_5DD8// "//"
0x1ef9  ldstr    asc_571A// "/"
0x1efe  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1f03  stloc.1
0x1f04  ldstr    aBaseHref0// "<base href=\"/{0}/\" >"
0x1f09  ldarg.2
0x1f0a  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x1f0f  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_PathBase()
0x1f14  stloc.0
0x1f15  ldloca.s 0
0x1f17  call     instance string [Microsoft.Owin]Microsoft.Owin.PathString::get_Value()
0x1f1c  call     string [mscorlib]System.String::Format(string, object)
0x1f21  ldstr    asc_5DD8// "//"
0x1f26  ldstr    asc_571A// "/"
0x1f2b  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1f30  stloc.2
0x1f31  ldarg.1
0x1f32  ldloc.1
0x1f33  ldloc.2
0x1f34  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1f39  ret
0x1f3a  ldarg.1
0x1f3b  ret
```
