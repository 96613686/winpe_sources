# Microsoft.ReportingServices.Diagnostics.BackgroundRequestContext::get_ReportServerVirtualDirectoryUri

- ea: `0x9950`
- end: `0x9985`
- name: `Microsoft.ReportingServices.Diagnostics.BackgroundRequestContext::get_ReportServerVirtualDirectoryUri`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x62f0`
- `0x9950`
- `0x10150`

## string_xrefs

- `0x996b`: `UrlRoot is not a valid Uri: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x9950  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x9955  callvirt instance string Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_UrlRootCalculated()
0x995a  ldc.i4.0
0x995b  ldloca.s 0
0x995d  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x9962  brfalse.s loc_9966
0x9964  ldloc.0
0x9965  ret
0x9966  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x996b  ldstr    aUrlrootIsNotAV// "UrlRoot is not a valid Uri: '{0}'"
0x9970  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x9975  callvirt instance string Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_UrlRootCalculated()
0x997a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x997f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x9984  throw
```
