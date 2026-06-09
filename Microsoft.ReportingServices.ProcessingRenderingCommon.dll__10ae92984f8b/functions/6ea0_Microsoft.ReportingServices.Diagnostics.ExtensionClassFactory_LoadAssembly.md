# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssembly

- ea: `0x6ea0`
- end: `0x6ed9`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssembly`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x15880`
- `0x15910`

## callees

- `0x6130`
- `0x6ea0`
- `0x6ee0`
- `0x10150`

## pseudocode

```c

```

## disassembly

```asm
0x6ea0  ldnull
0x6ea1  stloc.0
0x6ea2  ldarg.1
0x6ea3  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x6ea8  stloc.0
0x6ea9  leave.s  loc_6ED7
0x6eab  stloc.1
0x6eac  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x6eb1  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x6eb6  ldc.i4.3
0x6eb7  bne.un.s loc_6EC3
0x6eb9  ldarg.0
0x6eba  ldarg.1
0x6ebb  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssemblyFromFile(string name)
0x6ec0  stloc.0
0x6ec1  br.s     loc_6ED5
0x6ec3  ldloc.1
0x6ec4  ldstr    aUnableToLoadAs// "Unable to load assembly "
0x6ec9  ldarg.1
0x6eca  call     string [mscorlib]System.String::Concat(string, string)
0x6ecf  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x6ed4  throw
0x6ed5  leave.s  loc_6ED7
0x6ed7  ldloc.0
0x6ed8  ret
```
