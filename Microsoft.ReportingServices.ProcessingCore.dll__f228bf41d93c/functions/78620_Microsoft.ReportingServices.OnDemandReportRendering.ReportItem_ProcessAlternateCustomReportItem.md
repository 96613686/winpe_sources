# Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::ProcessAlternateCustomReportItem

- ea: `0x78620`
- end: `0x786f1`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::ProcessAlternateCustomReportItem`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x78380`

## callees

- `0x75120`
- `0x75130`
- `0x77a10`
- `0x78620`
- `0x10c200`
- `0x10c280`
- `0x124ca0`
- `0x1767c0`
- `0x17c2b0`
- `0x1fb030`
- `0x1fb400`
- `0x1fb640`

## string_xrefs

- `0x78691`: `The '{1}.{0}' extension is not present in the configuration file: The element '{2}' will render the AltReportItem, which is not defined. Therefore, it shows an empty space.`
- `0x786bd`: `The '{1}.{0}' extension failed to load: The element '{2}' will render the AltReportItem, which is not defined. Therefore, it shows an empty space.`

## pseudocode

```c

```

## disassembly

```asm
0x78620  ldarg.0
0x78621  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem::get_ExplicitlyDefinedAltReportItem()
0x78626  brtrue   loc_786F0
0x7862b  ldnull
0x7862c  stloc.0
0x7862d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x78632  ldarg.2
0x78633  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x78638  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IExtensionFactory Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ExtFactory()
0x7863d  ldnull
0x7863e  cgt.un
0x78640  ldstr    aExtfactoryNull// "ExtFactory != null."
0x78645  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7864a  ldarg.2
0x7864b  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x78650  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IExtensionFactory Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ExtFactory()
0x78655  ldarg.0
0x78656  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem::get_Type()
0x7865b  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IExtensionFactory::IsRegisteredCustomReportItemExtension(string)
0x78660  brtrue.s loc_78699
0x78662  ldarg.2
0x78663  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x78668  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_TopLevelContext()
0x7866d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ErrorContext()
0x78672  ldc.i4   0x19A
0x78677  ldc.i4.1
0x78678  ldc.i4.s 0x1C
0x7867a  ldarg.0
0x7867b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x78680  ldarg.0
0x78681  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem::get_Type()
0x78686  call     T0x2B000001
0x7868b  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x78690  pop
0x78691  ldstr    aThe10Extension// "The '{1}.{0}' extension is not present "...
0x78696  stloc.0
0x78697  br.s     loc_786C3
0x78699  ldarg.2
0x7869a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IErrorContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_ErrorContext()
0x7869f  ldc.i4   0x199
0x786a4  ldc.i4.1
0x786a5  ldc.i4.s 0x1C
0x786a7  ldarg.0
0x786a8  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x786ad  ldarg.0
0x786ae  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem::get_Type()
0x786b3  call     T0x2B000001
0x786b8  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x786bd  ldstr    aThe10Extension_0// "The '{1}.{0}' extension failed to load:"...
0x786c2  stloc.0
0x786c3  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x786c8  ldc.i4.4
0x786c9  ldloc.0
0x786ca  ldc.i4.3
0x786cb  newarr   [mscorlib]System.Object
0x786d0  dup
0x786d1  ldc.i4.0
0x786d2  ldarg.0
0x786d3  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x786d8  stelem.ref
0x786d9  dup
0x786da  ldc.i4.1
0x786db  ldarg.0
0x786dc  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem::get_Type()
0x786e1  stelem.ref
0x786e2  dup
0x786e3  ldc.i4.2
0x786e4  ldarg.1
0x786e5  callvirt instance string Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x786ea  stelem.ref
0x786eb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x786f0  ret
```
