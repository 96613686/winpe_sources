# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::UpdateSubscription

- ea: `0x76d0`
- end: `0x77b5`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::UpdateSubscription`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7560`
- `0x76d0`
- `0x7a90`
- `0x7af0`
- `0x7b20`
- `0x7d10`
- `0xab20`
- `0x1f830`

## pseudocode

```c

```

## disassembly

```asm
0x76d0  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x76d5  stloc.0
0x76d6  ldloc.0
0x76d7  ldarg.3
0x76d8  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass7_0::subscription
0x76dd  ldloc.0
0x76de  ldarg.0
0x76df  stfld    class Microsoft.ReportingServices.Portal.Repositories.SubscriptionService <>c__DisplayClass7_0::<>4__this
0x76e4  ldloc.0
0x76e5  ldarg.1
0x76e6  stfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x76eb  ldloc.0
0x76ec  ldarg.2
0x76ed  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x76f2  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x76f7  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x76fc  ldc.i4.s 0xC
0x76fe  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::ThrowIfFeatureNotEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x7703  ldarg.0
0x7704  ldloc.0
0x7705  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x770a  ldloc.0
0x770b  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x7710  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscription(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x7715  ldarg.0
0x7716  ldloc.0
0x7717  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x771c  ldloc.0
0x771d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x7722  call     instance string Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscriptionCulture(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x7727  stloc.1
0x7728  dup
0x7729  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsActive()
0x772e  ldloc.0
0x772f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass7_0::subscription
0x7734  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsActive()
0x7739  beq.s    loc_776E
0x773b  ldloc.0
0x773c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass7_0::subscription
0x7741  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsActive()
0x7746  brfalse.s loc_775C
0x7748  ldarg.0
0x7749  ldloc.0
0x774a  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x774f  ldloc.0
0x7750  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x7755  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::EnableSubscription(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x775a  br.s     loc_776E
0x775c  ldarg.0
0x775d  ldloc.0
0x775e  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x7763  ldloc.0
0x7764  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x7769  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::DisableSubscription(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x776e  ldloc.1
0x776f  ldloc.0
0x7770  ldftn    instance void <>c__DisplayClass7_0::<UpdateSubscription>b__0()
0x7776  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x777b  call     void Microsoft.ReportingServices.Portal.Services.Util.CultureUtil::ExecuteInCulture(string culture, class [mscorlib]System.Action action)
0x7780  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Owner()
0x7785  ldloc.0
0x7786  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass7_0::subscription
0x778b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Owner()
0x7790  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7795  brfalse.s loc_77B4
0x7797  ldarg.0
0x7798  ldloc.0
0x7799  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass7_0::userPrincipal
0x779e  ldloc.0
0x779f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::key
0x77a4  ldloc.0
0x77a5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass7_0::subscription
0x77aa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Owner()
0x77af  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::ChangeSubscriptionOwner(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key, string owner)
0x77b4  ret
```
