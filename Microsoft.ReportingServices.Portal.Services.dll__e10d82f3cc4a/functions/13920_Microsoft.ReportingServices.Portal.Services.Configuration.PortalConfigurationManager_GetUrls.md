# Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetUrls

- ea: `0x13920`
- end: `0x13978`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetUrls`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x13640`

## callees

- `0x13900`
- `0x13920`

## string_xrefs

- `0x13923`: `urlConfig`
- `0x13928`: `Did you forget to set your 'ReportServerPath' in the app.config?`

## pseudocode

```c

```

## disassembly

```asm
0x13920  ldarg.1
0x13921  brtrue.s loc_13933
0x13923  ldstr    aUrlconfig// "urlConfig"
0x13928  ldstr    aDidYouForgetTo// "Did you forget to set your 'ReportServe"...
0x1392d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x13932  throw
0x13933  ldarg.1
0x13934  call     bool Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::IsRSWebAppConfigured(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> urlConfig)
0x13939  brfalse.s loc_13971
0x1393b  ldarg.1
0x1393c  ldarg.0
0x1393d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::get_Item(void)
0x13942  ldfld    valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlReservation[] [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration::UrlReservations
0x13947  ldsfld   class [mscorlib]System.Func`2<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlReservation, string> <>c::<>9__14_0
0x1394c  dup
0x1394d  brtrue.s loc_13966
0x1394f  pop
0x13950  ldsfld   class <>c <>c::<>9
0x13955  ldftn    instance string <>c::<GetUrls>b__14_0(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlReservation res)
0x1395b  newobj   instance void class [mscorlib]System.Func`2<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlReservation, string>::.ctor(object, native int)
0x13960  dup
0x13961  stsfld   class [mscorlib]System.Func`2<valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlReservation, string> <>c::<>9__14_0
0x13966  call     T0x2B0000DD
0x1396b  call     T0x2B00008F
0x13970  ret
0x13971  ldc.i4.0
0x13972  newarr   [mscorlib]System.String
0x13977  ret
```
