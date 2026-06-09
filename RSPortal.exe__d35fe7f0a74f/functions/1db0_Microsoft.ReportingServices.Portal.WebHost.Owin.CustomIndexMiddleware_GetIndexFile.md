# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::GetIndexFile

- ea: `0x1db0`
- end: `0x1e11`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::GetIndexFile`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ca0`

## callees

- `0x1db0`
- `0x2fd0`

## string_xrefs

- `0x1de9`: `Microsoft.ReportingServices.Portal.Web.v2.wwwroot`
- `0x1def`: `Microsoft.ReportingServices.Portal.Web`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.0
0x1db1  brtrue.s loc_1DBE
0x1db3  ldstr    aExposurecontro_0// "exposureControl"
0x1db8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1dbd  throw
0x1dbe  ldarg.0
0x1dbf  callvirt instance bool [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IExposureControl::get_DogfoodEnabled()
0x1dc4  brfalse.s loc_1DE9
0x1dc6  call     string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir()
0x1dcb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1dd0  brtrue.s loc_1DE9
0x1dd2  call     string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir()
0x1dd7  ldstr    aIndexHtml_0// "index.html"
0x1ddc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1de1  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0x1de6  stloc.0
0x1de7  br.s     loc_1E0F
0x1de9  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.Portal.Web."...
0x1dee  stloc.1
0x1def  ldstr    aMicrosoftRepor_0// "Microsoft.ReportingServices.Portal.Web"
0x1df4  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x1df9  ldloc.1
0x1dfa  ldstr    aIndexHtml_1// ".index.html"
0x1dff  call     string [mscorlib]System.String::Concat(string, string)
0x1e04  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x1e09  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x1e0e  stloc.0
0x1e0f  ldloc.0
0x1e10  ret
```
