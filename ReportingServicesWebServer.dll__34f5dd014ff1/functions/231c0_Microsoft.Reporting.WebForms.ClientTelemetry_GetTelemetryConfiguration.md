# Microsoft.Reporting.WebForms.ClientTelemetry::GetTelemetryConfiguration

- ea: `0x231c0`
- end: `0x23282`
- name: `Microsoft.Reporting.WebForms.ClientTelemetry::GetTelemetryConfiguration`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x230c0`

## callees

- `0x22ed0`
- `0x22ef0`
- `0x22f10`
- `0x22f30`
- `0x22f50`
- `0x22f70`
- `0x22f90`
- `0x23080`
- `0x231c0`
- `0x23290`

## string_xrefs

- `0x231e6`: `InstallationId`

## pseudocode

```c

```

## disassembly

```asm
0x231c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x231c5  dup
0x231c6  ldstr    aBuild// "Build"
0x231cb  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_Build()
0x231d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x231d5  dup
0x231d6  ldstr    aHost// "Host"
0x231db  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_Host()
0x231e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x231e5  dup
0x231e6  ldstr    aInstallationid// "InstallationId"
0x231eb  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_InstallationId()
0x231f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x231f5  dup
0x231f6  ldstr    aHasheduserid// "HashedUserId"
0x231fb  ldarg.0
0x231fc  call     instance string Microsoft.Reporting.WebForms.ClientTelemetry::get_HashedUserId()
0x23201  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23206  dup
0x23207  ldstr    aExternaluser// "ExternalUser"
0x2320c  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_ExternalUser()
0x23211  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23216  dup
0x23217  ldstr    aIspublicbuild// "IsPublicBuild"
0x2321c  call     bool Microsoft.Reporting.WebForms.ClientTelemetry::get_IsPublicBuild()
0x23221  stloc.0
0x23222  ldloca.s 0
0x23224  call     instance string [mscorlib]System.Boolean::ToString()
0x23229  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2322e  dup
0x2322f  ldstr    aEdition// "Edition"
0x23234  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_Edition()
0x23239  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2323e  dup
0x2323f  ldstr    aAuthentication// "AuthenticationTypes"
0x23244  call     string Microsoft.Reporting.WebForms.ClientTelemetry::get_AuthenticationTypes()
0x23249  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2324e  dup
0x2324f  ldstr    aProductsku// "ProductSku"
0x23254  ldarg.0
0x23255  call     instance bool Microsoft.Reporting.WebForms.ClientTelemetry::IsBiServer()
0x2325a  brtrue.s loc_2326D
0x2325c  ldc.i4.0
0x2325d  stloc.1
0x2325e  ldloca.s 1
0x23260  constrained. Microsoft.Reporting.WebForms.ProductSku
0x23266  callvirt instance string [mscorlib]System.Object::ToString()
0x2326b  br.s     loc_2327C
0x2326d  ldc.i4.1
0x2326e  stloc.1
0x2326f  ldloca.s 1
0x23271  constrained. Microsoft.Reporting.WebForms.ProductSku
0x23277  callvirt instance string [mscorlib]System.Object::ToString()
0x2327c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23281  ret
```
