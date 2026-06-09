# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::CreateAndInitializeExtensionInstance

- ea: `0x6960`
- end: `0x6a29`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::CreateAndInitializeExtensionInstance`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6900`
- `0x6920`

## callees

- `0x4fa0`
- `0x5000`
- `0x5020`
- `0x6010`
- `0x6250`
- `0x6960`
- `0x6a50`
- `0x6ab0`
- `0x6dd0`
- `0x10150`

## string_xrefs

- `0x69fa`: `Report server extension {0} does not implement IExtension interface.`

## pseudocode

```c

```

## disassembly

```asm
0x6960  ldnull
0x6961  stloc.0
0x6962  ldarg.1
0x6963  brfalse  loc_6A22
0x6968  ldarg.0
0x6969  ldarg.1
0x696a  ldc.i4.0
0x696b  call     instance object Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::CreateExtensionObject(class Microsoft.ReportingServices.Diagnostics.Extension extConfig, bool typeOnly)
0x6970  stloc.0
0x6971  ldloc.0
0x6972  brfalse  loc_6A22
0x6977  ldc.i4.1
0x6978  stloc.1
0x6979  ldloc.0
0x697a  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension
0x697f  stloc.2
0x6980  ldloc.2
0x6981  brfalse.s loc_69D1
0x6983  ldloc.2
0x6984  ldarg.1
0x6985  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Configuration()
0x698a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension::SetConfiguration(string)
0x698f  leave.s  loc_6996
0x6991  pop
0x6992  ldc.i4.0
0x6993  stloc.1
0x6994  rethrow
0x6996  ldloc.0
0x6997  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ICatalogConfiguredExtension
0x699c  stloc.3
0x699d  ldloc.3
0x699e  brfalse.s loc_6A10
0x69a0  ldloc.3
0x69a1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ICatalogConfiguredExtension::EnumerateRequiredProperties()
0x69a6  stloc.s  4
0x69a8  ldloc.s  4
0x69aa  brfalse.s loc_6A10
0x69ac  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x69b1  callvirt instance class Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_OAuthConfiguration()
0x69b6  brfalse.s loc_6A10
0x69b8  ldloc.3
0x69b9  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x69be  callvirt instance class Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_OAuthConfiguration()
0x69c3  ldloc.s  4
0x69c5  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration::GetProperties(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> requestedProperties)
0x69ca  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ICatalogConfiguredExtension::SetCatalogConfiguration(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x69cf  br.s     loc_6A10
0x69d1  ldarg.1
0x69d2  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x69d7  ldstr    aData// "Data"
0x69dc  ldc.i4.4
0x69dd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x69e2  brtrue.s loc_69F4
0x69e4  ldarg.0
0x69e5  ldloc.0
0x69e6  ldarg.1
0x69e7  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x69ec  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::WrapDataExtension(object iExtension, string extensionName)
0x69f1  stloc.0
0x69f2  br.s     loc_6A10
0x69f4  ldnull
0x69f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69fa  ldstr    aReportServerEx// "Report server extension {0} does not im"...
0x69ff  ldarg.1
0x6a00  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6a05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6a0a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x6a0f  throw
0x6a10  leave.s  loc_6A22
0x6a12  stloc.s  5
0x6a14  ldarg.0
0x6a15  ldloc.s  5
0x6a17  ldarg.1
0x6a18  ldloc.1
0x6a19  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ProcessExtensionLoadException(class [mscorlib]System.Exception e, class Microsoft.ReportingServices.Diagnostics.Extension extConfig, valuetype ExtensionLoadFailReason reason)
0x6a1e  ldnull
0x6a1f  stloc.0
0x6a20  leave.s  loc_6A22
0x6a22  ldloc.0
0x6a23  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension
0x6a28  ret
```
