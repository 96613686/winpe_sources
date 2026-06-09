# Microsoft.ReportingServices.WebServer.ReportServerConfigFileUtil::GetViewerDeviceInfoFromConfigFile

- ea: `0x33aa0`
- end: `0x33b43`
- name: `Microsoft.ReportingServices.WebServer.ReportServerConfigFileUtil::GetViewerDeviceInfoFromConfigFile`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x343a0`

## callees

- `0x33aa0`

## string_xrefs

- `0x33b01`: `{0} value not specified in config file.`
- `0x33b29`: `{0} config file value: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x33aa0  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x33aa5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Extensions()
0x33aaa  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration/ExtensionArray [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Renderer()
0x33aaf  ldstr    aHtml5// "HTML5"
0x33ab4  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Extension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration/ExtensionArray::get_Item(string)
0x33ab9  isinst   [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RenderingExtension
0x33abe  stloc.0
0x33abf  ldnull
0x33ac0  stloc.1
0x33ac1  ldloc.0
0x33ac2  brfalse.s loc_33AE7
0x33ac4  ldloc.0
0x33ac5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x33aca  brfalse.s loc_33AE7
0x33acc  ldloc.0
0x33acd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x33ad2  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x33ad7  ldc.i4.0
0x33ad8  ble.s    loc_33AE7
0x33ada  ldloc.0
0x33adb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RenderingExtension::get_DeviceInfo()
0x33ae0  ldarg.0
0x33ae1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33ae6  stloc.1
0x33ae7  ldloc.1
0x33ae8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33aed  brfalse.s loc_33B17
0x33aef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x33af4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x33af9  brfalse.s loc_33B41
0x33afb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x33b00  ldc.i4.4
0x33b01  ldstr    a0ValueNotSpeci// "{0} value not specified in config file."
0x33b06  ldc.i4.1
0x33b07  newarr   [mscorlib]System.Object
0x33b0c  dup
0x33b0d  ldc.i4.0
0x33b0e  ldarg.0
0x33b0f  stelem.ref
0x33b10  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33b15  br.s     loc_33B41
0x33b17  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x33b1c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x33b21  brfalse.s loc_33B41
0x33b23  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_UITracer()
0x33b28  ldc.i4.4
0x33b29  ldstr    a0ConfigFileVal// "{0} config file value: {1}"
0x33b2e  ldc.i4.2
0x33b2f  newarr   [mscorlib]System.Object
0x33b34  dup
0x33b35  ldc.i4.0
0x33b36  ldarg.0
0x33b37  stelem.ref
0x33b38  dup
0x33b39  ldc.i4.1
0x33b3a  ldloc.1
0x33b3b  stelem.ref
0x33b3c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x33b41  ldloc.1
0x33b42  ret
```
