# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::PatchSubscription

- ea: `0x77c0`
- end: `0x7889`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::PatchSubscription`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x77c0`
- `0x7a90`
- `0x7af0`
- `0x7b20`
- `0x7d10`
- `0xab20`
- `0x1f8a0`

## pseudocode

```c

```

## disassembly

```asm
0x77c0  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x77c5  stloc.0
0x77c6  ldloc.0
0x77c7  ldarg.0
0x77c8  stfld    class Microsoft.ReportingServices.Portal.Repositories.SubscriptionService <>c__DisplayClass8_0::<>4__this
0x77cd  ldloc.0
0x77ce  ldarg.1
0x77cf  stfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass8_0::userPrincipal
0x77d4  ldloc.0
0x77d5  ldarg.2
0x77d6  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::key
0x77db  ldloc.0
0x77dc  ldarg.3
0x77dd  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass8_0::subscription
0x77e2  ldarg.s  4
0x77e4  brtrue.s loc_77E7
0x77e6  ret
0x77e7  ldarg.s  4
0x77e9  ldstr    aIsactive// "IsActive"
0x77ee  call     T0x2B000068
0x77f3  brfalse.s loc_7828
0x77f5  ldloc.0
0x77f6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass8_0::subscription
0x77fb  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsActive()
0x7800  brfalse.s loc_7816
0x7802  ldarg.0
0x7803  ldloc.0
0x7804  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass8_0::userPrincipal
0x7809  ldloc.0
0x780a  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::key
0x780f  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::EnableSubscription(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x7814  br.s     loc_7828
0x7816  ldarg.0
0x7817  ldloc.0
0x7818  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass8_0::userPrincipal
0x781d  ldloc.0
0x781e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::key
0x7823  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::DisableSubscription(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x7828  ldarg.s  4
0x782a  ldlen
0x782b  brfalse.s loc_785D
0x782d  ldloc.0
0x782e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass8_0::subscription
0x7833  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsDataDriven()
0x7838  brtrue.s loc_785D
0x783a  ldarg.0
0x783b  ldloc.0
0x783c  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass8_0::userPrincipal
0x7841  ldloc.0
0x7842  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::key
0x7847  call     instance string Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscriptionCulture(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key)
0x784c  ldloc.0
0x784d  ldftn    instance void <>c__DisplayClass8_0::<PatchSubscription>b__0()
0x7853  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7858  call     void Microsoft.ReportingServices.Portal.Services.Util.CultureUtil::ExecuteInCulture(string culture, class [mscorlib]System.Action action)
0x785d  ldarg.s  4
0x785f  ldstr    aOwner// "Owner"
0x7864  call     T0x2B000068
0x7869  brfalse.s loc_7888
0x786b  ldarg.0
0x786c  ldloc.0
0x786d  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass8_0::userPrincipal
0x7872  ldloc.0
0x7873  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::key
0x7878  ldloc.0
0x7879  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription <>c__DisplayClass8_0::subscription
0x787e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Owner()
0x7883  call     instance void Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::ChangeSubscriptionOwner(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key, string owner)
0x7888  ret
```
