# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::EnsureDataExtensionEnabled

- ea: `0x6d70`
- end: `0x6dc4`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::EnsureDataExtensionEnabled`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6c90`

## callees

- `0x4fa0`
- `0x5020`
- `0x5040`
- `0x6d70`
- `0x72a0`
- `0x8190`

## string_xrefs

- `0x6da9`: `Extension `
- `0x6db4`: ` is not supported on this edition of Reporting Services and has been removed`

## pseudocode

```c

```

## disassembly

```asm
0x6d70  ldarg.0
0x6d71  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x6d76  ldstr    aData// "Data"
0x6d7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6d80  brfalse.s loc_6DC3
0x6d82  ldarg.2
0x6d83  ldarg.0
0x6d84  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_ClassAndAssembly()
0x6d89  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsRestrictedDataExtension(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, string configTypeAndAssembly)
0x6d8e  brfalse.s loc_6DC3
0x6d90  ldarg.0
0x6d91  ldarg.1
0x6d92  call     void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::RemoveExtensionFromConfigInfo(class Microsoft.ReportingServices.Diagnostics.Extension extension, class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration extensionsConfig)
0x6d97  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6d9c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x6da1  brfalse.s loc_6DC3
0x6da3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6da8  ldc.i4.3
0x6da9  ldstr    aExtension_0// "Extension "
0x6dae  ldarg.0
0x6daf  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6db4  ldstr    aIsNotSupported// " is not supported on this edition of Re"...
0x6db9  call     string [mscorlib]System.String::Concat(string, string, string)
0x6dbe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6dc3  ret
```
