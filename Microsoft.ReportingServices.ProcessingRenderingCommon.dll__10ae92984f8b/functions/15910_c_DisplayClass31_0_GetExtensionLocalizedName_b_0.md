# <>c__DisplayClass31_0::<GetExtensionLocalizedName>b__0

- ea: `0x15910`
- end: `0x15964`
- name: `<>c__DisplayClass31_0::<GetExtensionLocalizedName>b__0`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x4fc0`
- `0x4fe0`
- `0x6ea0`
- `0xd130`
- `0x15910`

## pseudocode

```c

```

## disassembly

```asm
0x15910  ldsfld   class Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_classFactory
0x15915  ldarg.0
0x15916  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x1591b  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Assembly()
0x15920  callvirt instance class [mscorlib]System.Reflection.Assembly Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssembly(string name)
0x15925  ldarg.0
0x15926  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x1592b  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Class()
0x15930  ldc.i4.1
0x15931  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x15936  ldtoken  [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute
0x1593b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15940  ldc.i4.1
0x15941  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x15946  castclass class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute[]
0x1594b  stloc.0
0x1594c  ldloc.0
0x1594d  ldlen
0x1594e  brfalse.s loc_15963
0x15950  ldarg.0
0x15951  ldloc.0
0x15952  ldc.i4.0
0x15953  ldelem.ref
0x15954  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name()
0x15959  newobj   instance void Microsoft.ReportingServices.Diagnostics.ReturnValue::.ctor(object value)
0x1595e  stfld    class Microsoft.ReportingServices.Diagnostics.ReturnValue <>c__DisplayClass31_0::result
0x15963  ret
```
