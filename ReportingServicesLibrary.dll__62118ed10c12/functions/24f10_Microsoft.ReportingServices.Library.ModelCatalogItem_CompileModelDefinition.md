# Microsoft.ReportingServices.Library.ModelCatalogItem::CompileModelDefinition

- ea: `0x24f10`
- end: `0x24f9f`
- name: `Microsoft.ReportingServices.Library.ModelCatalogItem::CompileModelDefinition`
- size: `143`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f9e0`
- `0x2fcb0`
- `0x31970`
- `0x89440`

## callees

- `0x24f10`
- `0x765c0`

## string_xrefs

- `0x24f22`: `Compiling model "{0}".`
- `0x24f71`: `Compilation of the model "{0}" is complete.`

## pseudocode

```c

```

## disassembly

```asm
0x24f10  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x24f15  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x24f1a  brfalse.s loc_24F36
0x24f1c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x24f21  ldc.i4.4
0x24f22  ldstr    aCompilingModel// "Compiling model \"{0}\"."
0x24f27  ldc.i4.1
0x24f28  newarr   [mscorlib]System.Object
0x24f2d  dup
0x24f2e  ldc.i4.0
0x24f2f  ldarg.2
0x24f30  stelem.ref
0x24f31  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x24f36  ldarg.0
0x24f37  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x24f3c  stloc.0
0x24f3d  ldloc.0
0x24f3e  call     class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader(class [mscorlib]System.IO.Stream stream)
0x24f43  stloc.1
0x24f44  newobj   instance void [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.SemanticModel::.ctor()
0x24f49  stloc.2
0x24f4a  ldarg.3
0x24f4b  ldloc.2
0x24f4c  ldloc.1
0x24f4d  ldarg.1
0x24f4e  brtrue.s loc_24F53
0x24f50  ldc.i4.3
0x24f51  br.s     loc_24F54
0x24f53  ldc.i4.0
0x24f54  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_DefaultReportServerCulture()
0x24f59  callvirt instance class [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ValidationMessageCollection [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.SemanticModel::Compile(class [System.Xml]System.Xml.XmlReader, valuetype [Microsoft.ReportingServices.Modeling]Microsoft.ReportingServices.Modeling.ModelCompilationOptions, class [mscorlib]System.Globalization.CultureInfo)
0x24f5e  stind.ref
0x24f5f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x24f64  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x24f69  brfalse.s loc_24F85
0x24f6b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x24f70  ldc.i4.4
0x24f71  ldstr    aCompilationOfT// "Compilation of the model \"{0}\" is com"...
0x24f76  ldc.i4.1
0x24f77  newarr   [mscorlib]System.Object
0x24f7c  dup
0x24f7d  ldc.i4.0
0x24f7e  ldarg.2
0x24f7f  stelem.ref
0x24f80  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x24f85  ldloc.2
0x24f86  stloc.3
0x24f87  leave.s  loc_24F9D
0x24f89  ldloc.1
0x24f8a  brfalse.s loc_24F92
0x24f8c  ldloc.1
0x24f8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24f92  endfinally
0x24f93  ldloc.0
0x24f94  brfalse.s loc_24F9C
0x24f96  ldloc.0
0x24f97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24f9c  endfinally
0x24f9d  ldloc.3
0x24f9e  ret
```
