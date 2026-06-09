# Microsoft.VisualStudio.Setup.InstallationConfiguration::.ctor_0

- ea: `0x72e0`
- end: `0x733f`
- name: `Microsoft.VisualStudio.Setup.InstallationConfiguration::.ctor_0`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x72d0`

## callees

- `0x3380`
- `0x4e20`
- `0x72e0`
- `0x7390`

## string_xrefs

- `0x7306`: `InstallationConfigurationMissingProperty_Args1`
- `0x7313`: `components`

## pseudocode

```c

```

## disassembly

```asm
0x72e0  ldarg.0
0x72e1  call     instance void [mscorlib]System.Object::.ctor()
0x72e6  ldarg.0
0x72e7  ldarg.1
0x72e8  dup
0x72e9  brtrue.s loc_72F6
0x72eb  pop
0x72ec  ldstr    a10// "1.0"
0x72f1  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x72f6  stfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.InstallationConfiguration::<Version>k__BackingField
0x72fb  ldarg.0
0x72fc  ldarg.2
0x72fd  dup
0x72fe  brtrue.s loc_731F
0x7300  pop
0x7301  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x7306  ldstr    aInstallationco// "InstallationConfigurationMissingPropert"...
0x730b  ldc.i4.1
0x730c  newarr   [mscorlib]System.Object
0x7311  dup
0x7312  ldc.i4.0
0x7313  ldstr    aComponents// "components"
0x7318  stelem.ref
0x7319  newobj   instance void Microsoft.VisualStudio.Setup.InstallationConfigurationException::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x731e  throw
0x731f  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.InstallationConfiguration::<Components>k__BackingField
0x7324  ldarg.0
0x7325  ldarg.3
0x7326  dup
0x7327  brtrue.s loc_7339
0x7329  pop
0x732a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x732f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x7334  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionRecords::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Uris, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> MarketPlaceItemNames)
0x7339  stfld    class Microsoft.VisualStudio.Setup.ExtensionRecords Microsoft.VisualStudio.Setup.InstallationConfiguration::<Extensions>k__BackingField
0x733e  ret
```
