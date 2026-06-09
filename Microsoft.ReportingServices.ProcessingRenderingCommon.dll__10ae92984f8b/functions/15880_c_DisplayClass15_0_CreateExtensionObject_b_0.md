# <>c__DisplayClass15_0::<CreateExtensionObject>b__0

- ea: `0x15880`
- end: `0x158e1`
- name: `<>c__DisplayClass15_0::<CreateExtensionObject>b__0`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x4fc0`
- `0x4fe0`
- `0x6b40`
- `0x6ea0`
- `0x15880`

## pseudocode

```c

```

## disassembly

```asm
0x15880  ldarg.0
0x15881  ldfld    class Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory <>c__DisplayClass15_0::<>4__this
0x15886  ldarg.0
0x15887  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x1588c  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Assembly()
0x15891  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::LoadAssembly(string name)
0x15896  stloc.0
0x15897  ldarg.0
0x15898  ldfld    bool <>c__DisplayClass15_0::typeOnly
0x1589d  brfalse.s loc_158B8
0x1589f  ldarg.0
0x158a0  ldloc.0
0x158a1  ldarg.0
0x158a2  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x158a7  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Class()
0x158ac  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x158b1  stfld    object <>c__DisplayClass15_0::objExtension
0x158b6  br.s     loc_158CF
0x158b8  ldarg.0
0x158b9  ldloc.0
0x158ba  ldarg.0
0x158bb  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x158c0  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Class()
0x158c5  callvirt instance object [mscorlib]System.Reflection.Assembly::CreateInstance(string)
0x158ca  stfld    object <>c__DisplayClass15_0::objExtension
0x158cf  ldarg.0
0x158d0  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x158d5  ldloc.0
0x158d6  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x158db  call     void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::EnsureExtensionEnabled(class Microsoft.ReportingServices.Diagnostics.Extension extension, string assemblyFullName)
0x158e0  ret
```
