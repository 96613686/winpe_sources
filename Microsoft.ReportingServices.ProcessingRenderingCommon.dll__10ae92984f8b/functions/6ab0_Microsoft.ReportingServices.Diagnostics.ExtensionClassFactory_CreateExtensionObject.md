# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::CreateExtensionObject

- ea: `0x6ab0`
- end: `0x6b40`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::CreateExtensionObject`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x68e0`
- `0x6960`
- `0x6a30`

## callees

- `0x4fa0`
- `0x5020`
- `0x6ab0`
- `0x6dd0`
- `0xd150`
- `0xd1a0`
- `0x15870`

## string_xrefs

- `0x6af4`: `Could not create Extension of type: `

## pseudocode

```c

```

## disassembly

```asm
0x6ab0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x6ab5  stloc.0
0x6ab6  ldloc.0
0x6ab7  ldarg.0
0x6ab8  stfld    class Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory <>c__DisplayClass15_0::<>4__this
0x6abd  ldloc.0
0x6abe  ldarg.1
0x6abf  stfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x6ac4  ldloc.0
0x6ac5  ldarg.2
0x6ac6  stfld    bool <>c__DisplayClass15_0::typeOnly
0x6acb  ldloc.0
0x6acc  ldnull
0x6acd  stfld    object <>c__DisplayClass15_0::objExtension
0x6ad2  ldloc.0
0x6ad3  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x6ad8  brfalse.s loc_6B39
0x6ada  ldloc.0
0x6adb  ldftn    instance void <>c__DisplayClass15_0::<CreateExtensionObject>b__0()
0x6ae1  newobj   instance void Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object object, native int method)
0x6ae6  call     void Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class Microsoft.ReportingServices.Diagnostics.ContextBody callback)
0x6aeb  ldloc.0
0x6aec  ldfld    object <>c__DisplayClass15_0::objExtension
0x6af1  brtrue.s loc_6B1F
0x6af3  ldnull
0x6af4  ldstr    aCouldNotCreate// "Could not create Extension of type: "
0x6af9  ldloc.0
0x6afa  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x6aff  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Type()
0x6b04  ldstr    aName_1// "name: "
0x6b09  ldloc.0
0x6b0a  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x6b0f  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Name()
0x6b14  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x6b19  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x6b1e  throw
0x6b1f  leave.s  loc_6B39
0x6b21  stloc.1
0x6b22  ldarg.0
0x6b23  ldloc.1
0x6b24  ldloc.0
0x6b25  ldfld    class Microsoft.ReportingServices.Diagnostics.Extension <>c__DisplayClass15_0::extConfig
0x6b2a  ldc.i4.1
0x6b2b  call     instance void Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::ProcessExtensionLoadException(class [mscorlib]System.Exception e, class Microsoft.ReportingServices.Diagnostics.Extension extConfig, valuetype ExtensionLoadFailReason reason)
0x6b30  ldloc.0
0x6b31  ldnull
0x6b32  stfld    object <>c__DisplayClass15_0::objExtension
0x6b37  leave.s  loc_6B39
0x6b39  ldloc.0
0x6b3a  ldfld    object <>c__DisplayClass15_0::objExtension
0x6b3f  ret
```
