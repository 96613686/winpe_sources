# CommonInfo::TraceOneTimeWarning

- ea: `0x26add0`
- end: `0x26aeea`
- name: `CommonInfo::TraceOneTimeWarning`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1fcdf0`

## callees

- `0x26add0`

## string_xrefs

- `0x26ae34`: `RDL Sandboxing: Item: '{0}' attempted to use an array that violated the maximum allowed length.`
- `0x26ae53`: `RDL Sandboxing: Item: '{0}' attempted to use a String that violated the maximum allowed length.`
- `0x26ae6f`: `RDL Sandboxing: Item: '{0}' attempted to reference an external resource larger than the maximum allowed size.`
- `0x26aea7`: `A rendering extension attempted to use Report.GetOrCreateChunk or Report.CreateChunk while rendering item '{0}'. Rendering chunks are not available using the current report execution method.`

## pseudocode

```c

```

## disassembly

```asm
0x26add0  ldarg.0
0x26add1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode, bool> CommonInfo::m_hasTracedOneTimeMessage
0x26add6  brtrue.s loc_26ADD9
0x26add8  ret
0x26add9  ldarg.0
0x26adda  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode, bool> CommonInfo::m_hasTracedOneTimeMessage
0x26addf  ldarg.1
0x26ade0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode, bool>::ContainsKey(var<u1>)
0x26ade5  brtrue   loc_26AEE9
0x26adea  ldarg.2
0x26adeb  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x26adf0  stloc.0
0x26adf1  ldarg.1
0x26adf2  ldc.i4   0x1C4
0x26adf7  bgt.s    loc_26AE11
0x26adf9  ldarg.1
0x26adfa  ldc.i4   0x167
0x26adff  beq      loc_26AE85
0x26ae04  ldarg.1
0x26ae05  ldc.i4   0x1C4
0x26ae0a  beq.s    loc_26AE4D
0x26ae0c  br       loc_26AEBD
0x26ae11  ldarg.1
0x26ae12  ldc.i4   0x1C5
0x26ae17  beq.s    loc_26AE2E
0x26ae19  ldarg.1
0x26ae1a  ldc.i4   0x1CC
0x26ae1f  beq.s    loc_26AE69
0x26ae21  ldarg.1
0x26ae22  ldc.i4   0x208
0x26ae27  beq.s    loc_26AEA1
0x26ae29  br       loc_26AEBD
0x26ae2e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ae33  ldc.i4.3
0x26ae34  ldstr    aRdlSandboxingI// "RDL Sandboxing: Item: '{0}' attempted t"...
0x26ae39  ldc.i4.1
0x26ae3a  newarr   [mscorlib]System.Object
0x26ae3f  dup
0x26ae40  ldc.i4.0
0x26ae41  ldloc.0
0x26ae42  stelem.ref
0x26ae43  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26ae48  br       loc_26AEDC
0x26ae4d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ae52  ldc.i4.3
0x26ae53  ldstr    aRdlSandboxingI_0// "RDL Sandboxing: Item: '{0}' attempted t"...
0x26ae58  ldc.i4.1
0x26ae59  newarr   [mscorlib]System.Object
0x26ae5e  dup
0x26ae5f  ldc.i4.0
0x26ae60  ldloc.0
0x26ae61  stelem.ref
0x26ae62  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26ae67  br.s     loc_26AEDC
0x26ae69  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ae6e  ldc.i4.3
0x26ae6f  ldstr    aRdlSandboxingI_1// "RDL Sandboxing: Item: '{0}' attempted t"...
0x26ae74  ldc.i4.1
0x26ae75  newarr   [mscorlib]System.Object
0x26ae7a  dup
0x26ae7b  ldc.i4.0
0x26ae7c  ldloc.0
0x26ae7d  stelem.ref
0x26ae7e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26ae83  br.s     loc_26AEDC
0x26ae85  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ae8a  ldc.i4.3
0x26ae8b  ldstr    aThereWasAnErro_0// "There was an error loading the external"...
0x26ae90  ldc.i4.1
0x26ae91  newarr   [mscorlib]System.Object
0x26ae96  dup
0x26ae97  ldc.i4.0
0x26ae98  ldloc.0
0x26ae99  stelem.ref
0x26ae9a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26ae9f  br.s     loc_26AEDC
0x26aea1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26aea6  ldc.i4.3
0x26aea7  ldstr    aARenderingExte// "A rendering extension attempted to use "...
0x26aeac  ldc.i4.1
0x26aead  newarr   [mscorlib]System.Object
0x26aeb2  dup
0x26aeb3  ldc.i4.0
0x26aeb4  ldloc.0
0x26aeb5  stelem.ref
0x26aeb6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x26aebb  br.s     loc_26AEDC
0x26aebd  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26aec2  ldc.i4.0
0x26aec3  ldstr    aInvalidErrorCo// "Invalid error code: '{0}'.  Expected an"...
0x26aec8  ldc.i4.1
0x26aec9  newarr   [mscorlib]System.Object
0x26aece  dup
0x26aecf  ldc.i4.0
0x26aed0  ldarg.1
0x26aed1  box      Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode
0x26aed6  stelem.ref
0x26aed7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x26aedc  ldarg.0
0x26aedd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode, bool> CommonInfo::m_hasTracedOneTimeMessage
0x26aee2  ldarg.1
0x26aee3  ldc.i4.1
0x26aee4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode, bool>::set_Item(var<u1>, !!T0)
0x26aee9  ret
```
