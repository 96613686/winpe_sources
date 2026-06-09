# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::WritePropertiesAsJson

- ea: `0xb8a0`
- end: `0xb929`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::WritePropertiesAsJson`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb8a0`

## pseudocode

```c

```

## disassembly

```asm
0xb8a0  ldarg.2
0xb8a1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem
0xb8a6  stloc.0
0xb8a7  ldloc.0
0xb8a8  brtrue.s loc_B8AB
0xb8aa  ret
0xb8ab  ldarg.0
0xb8ac  ldarg.1
0xb8ad  ldarg.2
0xb8ae  ldarg.3
0xb8af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb8b4  ldarg.0
0xb8b5  ldstr    aEnddate// "EndDate"
0xb8ba  ldarg.3
0xb8bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb8c0  ldarg.1
0xb8c1  ldstr    aEnddate// "EndDate"
0xb8c6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xb8cb  ldarg.3
0xb8cc  ldstr    aEnddate// "EndDate"
0xb8d1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xb8d6  ldarg.1
0xb8d7  ldloc.0
0xb8d8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_EndDate()
0xb8dd  ldarg.3
0xb8de  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb8e3  ldarg.3
0xb8e4  ldstr    aEnddate// "EndDate"
0xb8e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xb8ee  ldarg.0
0xb8ef  ldstr    aStartdate// "StartDate"
0xb8f4  ldarg.3
0xb8f5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb8fa  ldarg.1
0xb8fb  ldstr    aStartdate// "StartDate"
0xb900  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xb905  ldarg.3
0xb906  ldstr    aStartdate// "StartDate"
0xb90b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xb910  ldarg.1
0xb911  ldloc.0
0xb912  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ScheduledItem::get_StartDate()
0xb917  ldarg.3
0xb918  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb91d  ldarg.3
0xb91e  ldstr    aStartdate// "StartDate"
0xb923  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xb928  ret
```
