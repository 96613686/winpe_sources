# Microsoft.VisualStudio.Setup.Services.PolicyService::.ctor

- ea: `0x41910`
- end: `0x419d1`
- name: `Microsoft.VisualStudio.Setup.Services.PolicyService::.ctor`
- size: `193`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3e40`
- `0x51f0`
- `0xd160`
- `0x12cb0`
- `0x14ec0`
- `0x1f120`
- `0x229d0`
- `0x2d380`
- `0x51550`
- `0x51580`
- `0x58040`

## callees

- `0x3c190`
- `0x3eaf0`
- `0x3eb70`
- `0x418b0`

## string_xrefs

- `0x41950`: `SharedInstallationPath`
- `0x41993`: `CompatibilityInstallationPath`

## pseudocode

```c

```

## disassembly

```asm
0x41910  ldarg.0
0x41911  call     instance void [mscorlib]System.Object::.ctor()
0x41916  ldarg.0
0x41917  ldarg.1
0x41918  stfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.PolicyService::services
0x4191d  ldarg.0
0x4191e  ldftn    instance void Microsoft.VisualStudio.Setup.Services.PolicyService::OnAllInvalidated(object sender, class [mscorlib]System.EventArgs args)
0x41924  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>::.ctor(object, native int)
0x41929  newobj   instance void class Microsoft.VisualStudio.Setup.WeakEventHandler`1<class [mscorlib]System.EventArgs>::.ctor(class [mscorlib]System.EventHandler`1<var<u1>>)
0x4192e  ldftn    instance void class Microsoft.VisualStudio.Setup.WeakEventHandler`1<class [mscorlib]System.EventArgs>::Handler(object, var<u1>)
0x41934  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs>::.ctor(object, native int)
0x41939  call     void Microsoft.VisualStudio.Setup.Services.PolicyService::add_AllInvalidated(class [mscorlib]System.EventHandler`1<class [mscorlib]System.EventArgs> value)
0x4193e  ldarg.0
0x4193f  ldarg.1
0x41940  newobj   instance void Microsoft.VisualStudio.Setup.Services.DefaultPolicy::.ctor(class [mscorlib]System.IServiceProvider services)
0x41945  stfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Services.PolicyService::defaults
0x4194a  ldarg.0
0x4194b  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryValueNameLookup
0x41950  ldstr    aSharedinstalla// "SharedInstallationPath"
0x41955  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x4195a  ldarg.0
0x4195b  ldftn    instance bool Microsoft.VisualStudio.Setup.Services.PolicyService::IsValueSet(string propertyName)
0x41961  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x41966  ldarg.0
0x41967  ldarg.0
0x41968  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Services.PolicyService::defaults
0x4196d  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0x41972  call     T0x2B0001E6
0x41977  ldarg.0
0x41978  ldftn    T0x2B0001E7
0x4197e  newobj   instance void class [mscorlib]System.Action`2<string, string>::.ctor(object, native int)
0x41983  newobj   instance void class Microsoft.VisualStudio.Setup.Services.SetOnce`1<string>::.ctor(string, class [mscorlib]System.Func`2<string, bool>, class [mscorlib]System.Func`2<string, var<u1>>, !!T0)
0x41988  stfld    class Microsoft.VisualStudio.Setup.Services.SetOnce`1<string> Microsoft.VisualStudio.Setup.Services.PolicyService::<SharedInstallationPath>k__BackingField
0x4198d  ldarg.0
0x4198e  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Services.PolicyService::RegistryValueNameLookup
0x41993  ldstr    aCompatibilityi// "CompatibilityInstallationPath"
0x41998  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x4199d  ldarg.0
0x4199e  ldftn    instance bool Microsoft.VisualStudio.Setup.Services.PolicyService::IsValueSet(string propertyName)
0x419a4  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x419a9  ldarg.0
0x419aa  ldarg.0
0x419ab  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Services.PolicyService::defaults
0x419b0  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CompatibilityInstallationPath()
0x419b5  call     T0x2B0001E6
0x419ba  ldarg.0
0x419bb  ldftn    T0x2B0001E7
0x419c1  newobj   instance void class [mscorlib]System.Action`2<string, string>::.ctor(object, native int)
0x419c6  newobj   instance void class Microsoft.VisualStudio.Setup.Services.SetOnce`1<string>::.ctor(string, class [mscorlib]System.Func`2<string, bool>, class [mscorlib]System.Func`2<string, var<u1>>, !!T0)
0x419cb  stfld    class Microsoft.VisualStudio.Setup.Services.SetOnce`1<string> Microsoft.VisualStudio.Setup.Services.PolicyService::<CompatibilityInstallationPath>k__BackingField
0x419d0  ret
```
