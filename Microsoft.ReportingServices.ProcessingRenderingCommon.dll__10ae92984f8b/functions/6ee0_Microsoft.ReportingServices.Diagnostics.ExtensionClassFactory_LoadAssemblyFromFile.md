# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssemblyFromFile

- ea: `0x6ee0`
- end: `0x6f26`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssemblyFromFile`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6ea0`

## callees

- `0x6ee0`
- `0x6f30`

## string_xrefs

- `0x6eef`: `{0}.dll`

## pseudocode

```c

```

## disassembly

```asm
0x6ee0  ldarg.0
0x6ee1  call     instance string Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetReportServerBinDirectory()
0x6ee6  stloc.0
0x6ee7  ldarg.1
0x6ee8  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x6eed  stloc.1
0x6eee  ldloc.1
0x6eef  ldstr    a0Dll// "{0}.dll"
0x6ef4  ldloc.0
0x6ef5  ldloc.1
0x6ef6  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x6efb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6f00  call     string [mscorlib]System.String::Format(string, object)
0x6f05  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_CodeBase(string)
0x6f0a  ldloc.1
0x6f0b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(class [mscorlib]System.Reflection.AssemblyName)
0x6f10  stloc.2
0x6f11  leave.s  loc_6F24
0x6f13  ldstr    aUnableToLoadAs// "Unable to load assembly "
0x6f18  ldarg.1
0x6f19  call     string [mscorlib]System.String::Concat(string, string)
0x6f1e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x6f23  throw
0x6f24  ldloc.2
0x6f25  ret
```
