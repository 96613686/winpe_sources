# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::EnsureExtensionEnabled

- ea: `0x6b40`
- end: `0x6bbd`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::EnsureExtensionEnabled`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x15880`

## callees

- `0x5020`
- `0x5040`
- `0x6190`
- `0x61a0`
- `0x6b40`
- `0x8000`
- `0x10150`

## string_xrefs

- `0x6b79`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x6b40  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x6b45  callvirt instance bool Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_IsExtensibilityEnabled()
0x6b4a  brfalse.s loc_6B4D
0x6b4c  ret
0x6b4d  ldarg.0
0x6b4e  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x6b53  ldarg.0
0x6b54  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_ClassAndAssembly()
0x6b59  ldarg.1
0x6b5a  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsKnownExtension(string extensionType, string configTypeAndAssembly, string assemblyFullName)
0x6b5f  brtrue.s loc_6BBC
0x6b61  ldarg.0
0x6b62  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x6b67  ldstr    aAuthentication// "Authentication"
0x6b6c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6b71  brfalse.s loc_6B9A
0x6b73  ldarg.0
0x6b74  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x6b79  ldstr    aSecurity// "Security"
0x6b7e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6b83  brfalse.s loc_6B9A
0x6b85  ldc.i4.8
0x6b86  stloc.0
0x6b87  ldloca.s 0
0x6b89  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x6b8f  callvirt instance string [mscorlib]System.Object::ToString()
0x6b94  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.OperationNotSupportedException::.ctor(string)
0x6b99  throw
0x6b9a  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x6b9f  callvirt instance bool Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_IsCustomAuthEnabled()
0x6ba4  brtrue.s loc_6BBC
0x6ba6  ldc.i4.s 9
0x6ba8  stloc.0
0x6ba9  ldloca.s 0
0x6bab  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x6bb1  callvirt instance string [mscorlib]System.Object::ToString()
0x6bb6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.OperationNotSupportedException::.ctor(string)
0x6bbb  throw
0x6bbc  ret
```
