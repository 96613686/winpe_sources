# Microsoft.ReportingServices.Library.StreamRequestHandler::RenderComponent

- ea: `0x6c9a0`
- end: `0x6ca11`
- name: `Microsoft.ReportingServices.Library.StreamRequestHandler::RenderComponent`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6b810`

## callees

- `0x1a4a0`
- `0x25b90`
- `0x25ba0`
- `0x6ad90`
- `0x6adc0`
- `0x6ade0`
- `0x6aeb0`
- `0x6aef0`
- `0x6af60`
- `0x6c9a0`

## string_xrefs

- `0x6c9d4`: `text/xml`
- `0x6c9a0`: `StreamRequestHandler.RenderComponent`

## pseudocode

```c

```

## disassembly

```asm
0x6c9a0  ldstr    aStreamrequesth_11// "StreamRequestHandler.RenderComponent"
0x6c9a5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x6c9aa  stloc.0
0x6c9ab  ldarg.0
0x6c9ac  callvirt instance class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x6c9b1  callvirt instance class Microsoft.ReportingServices.Library.GetComponentDefinitionAction Microsoft.ReportingServices.Library.RSService::get_GetComponentDefinitionAction()
0x6c9b6  stloc.1
0x6c9b7  ldloc.1
0x6c9b8  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.GetComponentDefinitionActionParameters>::get_ActionParameters()
0x6c9bd  ldarg.0
0x6c9be  call     instance string Microsoft.ReportingServices.Library.StreamRequestHandler::get_NormalizedItemPath()
0x6c9c3  callvirt instance void Microsoft.ReportingServices.Library.GetComponentDefinitionActionParameters::set_ItemPath(string value)
0x6c9c8  ldloc.1
0x6c9c9  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.GetComponentDefinitionActionParameters>::Execute()
0x6c9ce  ldarg.0
0x6c9cf  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c9d4  ldstr    aTextXml// "text/xml"
0x6c9d9  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::set_MimeType(string value)
0x6c9de  ldarg.0
0x6c9df  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c9e4  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x6c9e9  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding value)
0x6c9ee  ldarg.0
0x6c9ef  callvirt instance class Microsoft.ReportingServices.Library.IStreamResponse Microsoft.ReportingServices.Library.StreamRequestHandler::get_Response()
0x6c9f4  ldloc.1
0x6c9f5  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.GetComponentDefinitionActionParameters>::get_ActionParameters()
0x6c9fa  callvirt instance unsigned int8[] Microsoft.ReportingServices.Library.GetComponentDefinitionActionParameters::get_ComponentDefinition()
0x6c9ff  callvirt instance void Microsoft.ReportingServices.Library.IStreamResponse::BinaryWrite(unsigned int8[] buffer)
0x6ca04  leave.s  loc_6CA10
0x6ca06  ldloc.0
0x6ca07  brfalse.s loc_6CA0F
0x6ca09  ldloc.0
0x6ca0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ca0f  endfinally
0x6ca10  ret
```
