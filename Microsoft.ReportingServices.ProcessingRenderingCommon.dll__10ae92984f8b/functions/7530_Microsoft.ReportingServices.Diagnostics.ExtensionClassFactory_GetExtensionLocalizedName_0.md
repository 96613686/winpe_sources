# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetExtensionLocalizedName_0

- ea: `0x7530`
- end: `0x760b`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetExtensionLocalizedName_0`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7520`

## callees

- `0x4fa0`
- `0x5020`
- `0x6920`
- `0x6dd0`
- `0x7530`
- `0xd120`
- `0xd150`
- `0xd1a0`
- `0x15900`

## string_xrefs

- `0x75ae`: `The extension {0} does not have a LocalizedNameAttribute.`

## pseudocode

```c

```

## disassembly

```asm
0x7530  newobj   instance void <>c__DisplayClass31_0::.ctor()
0x7535  stloc.0
0x7536  ldloc.0
0x7537  ldarg.0
0x7538  stfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x753d  ldloc.0
0x753e  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x7543  brtrue.s loc_7547
0x7545  ldnull
0x7546  ret
0x7547  nop
0x7548  ldloc.0
0x7549  ldnull
0x754a  stfld    class Microsoft.ReportingServices.Diagnostics.ReturnValue <>c__DisplayClass31_0::result
0x754f  ldloc.0
0x7550  ldftn    instance void <>c__DisplayClass31_0::<GetExtensionLocalizedName>b__0()
0x7556  newobj   instance void Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object object, native int method)
0x755b  call     void Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class Microsoft.ReportingServices.Diagnostics.ContextBody callback)
0x7560  ldloc.0
0x7561  ldfld    class Microsoft.ReportingServices.Diagnostics.ReturnValue <>c__DisplayClass31_0::result
0x7566  brfalse.s loc_757E
0x7568  ldloc.0
0x7569  ldfld    class Microsoft.ReportingServices.Diagnostics.ReturnValue <>c__DisplayClass31_0::result
0x756e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ReturnValue::get_Value()
0x7573  castclass [mscorlib]System.String
0x7578  stloc.2
0x7579  leave    loc_7609
0x757e  leave.s  loc_759C
0x7580  stloc.3
0x7581  ldsfld   class Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::m_classFactory
0x7586  ldloc.3
0x7587  ldloc.0
0x7588  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x758d  ldc.i4.1
0x758e  callvirt instance void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ProcessExtensionLoadException(class [mscorlib]System.Exception e, class Microsoft.ReportingServices.Diagnostics.Extension extConfig, valuetype ExtensionLoadFailReason reason)
0x7593  ldarg.1
0x7594  brfalse.s loc_759A
0x7596  ldnull
0x7597  stloc.2
0x7598  leave.s  loc_7609
0x759a  rethrow
0x759c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ExtensionFactoryTracer()
0x75a1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x75a6  brfalse.s loc_75CC
0x75a8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ExtensionFactoryTracer()
0x75ad  ldc.i4.2
0x75ae  ldstr    aTheExtension0D// "The extension {0} does not have a Local"...
0x75b3  ldc.i4.1
0x75b4  newarr   [mscorlib]System.Object
0x75b9  dup
0x75ba  ldc.i4.0
0x75bb  ldloc.0
0x75bc  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x75c1  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x75c6  stelem.ref
0x75c7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x75cc  ldloc.0
0x75cd  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x75d2  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x75d7  ldloc.0
0x75d8  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x75dd  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x75e2  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string extensionName, string extensionType)
0x75e7  stloc.1
0x75e8  ldloc.1
0x75e9  brfalse.s loc_7607
0x75eb  ldloc.1
0x75ec  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension::get_LocalizedName()
0x75f1  stloc.s  4
0x75f3  ldloc.s  4
0x75f5  brtrue.s loc_7604
0x75f7  ldloc.0
0x75f8  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass31_0::extConfig
0x75fd  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x7602  stloc.s  4
0x7604  ldloc.s  4
0x7606  ret
0x7607  ldnull
0x7608  ret
0x7609  ldloc.2
0x760a  ret
```
