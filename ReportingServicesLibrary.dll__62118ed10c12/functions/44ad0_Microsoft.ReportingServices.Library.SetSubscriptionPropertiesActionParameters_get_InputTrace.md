# Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_InputTrace

- ea: `0x44ad0`
- end: `0x44c74`
- name: `Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_InputTrace`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x449a0`
- `0x449d0`
- `0x449f0`
- `0x44a10`
- `0x44a30`
- `0x44a50`
- `0x44a80`
- `0x44ab0`
- `0x44ad0`
- `0x705d0`
- `0x70f40`
- `0x73350`

## string_xrefs

- `0x44af5`: `SubscriptionID={0}, ExtensionSettings={1}, DataRetrievalPlan={2}, Description={3}, EventType={4}, MatchData={5}, Parameters={6}`
- `0x44bc7`: `SubscriptionID={0}, ExtensionSettings={1}, Description={2}, EventType={3}, MatchData={4}, Parameters={5}`

## pseudocode

```c

```

## disassembly

```asm
0x44ad0  ldsfld   string [mscorlib]System.String::Empty
0x44ad5  stloc.0
0x44ad6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x44adb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x44ae0  brfalse  loc_44C72
0x44ae5  ldarg.0
0x44ae6  call     instance bool Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_IsDataDriven()
0x44aeb  brfalse  loc_44BC2
0x44af0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44af5  ldstr    aSubscriptionid_3// "SubscriptionID={0}, ExtensionSettings={"...
0x44afa  ldc.i4.7
0x44afb  newarr   [mscorlib]System.Object
0x44b00  dup
0x44b01  ldc.i4.0
0x44b02  ldarg.0
0x44b03  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_SubscriptionID()
0x44b08  brtrue.s loc_44B11
0x44b0a  ldstr    aNull_0// "null"
0x44b0f  br.s     loc_44B17
0x44b11  ldarg.0
0x44b12  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_SubscriptionID()
0x44b17  stelem.ref
0x44b18  dup
0x44b19  ldc.i4.1
0x44b1a  ldarg.0
0x44b1b  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44b20  brtrue.s loc_44B29
0x44b22  ldstr    aNull_0// "null"
0x44b27  br.s     loc_44B34
0x44b29  ldarg.0
0x44b2a  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44b2f  call     string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ThisToXml(class Microsoft.ReportingServices.Library.Soap.ExtensionSettings settings)
0x44b34  stelem.ref
0x44b35  dup
0x44b36  ldc.i4.2
0x44b37  ldarg.0
0x44b38  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_DataSettings()
0x44b3d  brtrue.s loc_44B46
0x44b3f  ldstr    aNull_0// "null"
0x44b44  br.s     loc_44B51
0x44b46  ldarg.0
0x44b47  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_DataSettings()
0x44b4c  call     string Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::ThisToXml(class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan dataSettings)
0x44b51  stelem.ref
0x44b52  dup
0x44b53  ldc.i4.3
0x44b54  ldarg.0
0x44b55  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Description()
0x44b5a  brtrue.s loc_44B63
0x44b5c  ldstr    aNull_0// "null"
0x44b61  br.s     loc_44B69
0x44b63  ldarg.0
0x44b64  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Description()
0x44b69  stelem.ref
0x44b6a  dup
0x44b6b  ldc.i4.4
0x44b6c  ldarg.0
0x44b6d  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44b72  brtrue.s loc_44B7B
0x44b74  ldstr    aNull_0// "null"
0x44b79  br.s     loc_44B81
0x44b7b  ldarg.0
0x44b7c  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44b81  stelem.ref
0x44b82  dup
0x44b83  ldc.i4.5
0x44b84  ldarg.0
0x44b85  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_MatchData()
0x44b8a  brtrue.s loc_44B93
0x44b8c  ldstr    aNull_0// "null"
0x44b91  br.s     loc_44B99
0x44b93  ldarg.0
0x44b94  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_MatchData()
0x44b99  stelem.ref
0x44b9a  dup
0x44b9b  ldc.i4.6
0x44b9c  ldarg.0
0x44b9d  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44ba2  brtrue.s loc_44BAB
0x44ba4  ldstr    aNull_0// "null"
0x44ba9  br.s     loc_44BB6
0x44bab  ldarg.0
0x44bac  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44bb1  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x44bb6  stelem.ref
0x44bb7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44bbc  stloc.0
0x44bbd  br       loc_44C72
0x44bc2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44bc7  ldstr    aSubscriptionid_4// "SubscriptionID={0}, ExtensionSettings={"...
0x44bcc  ldc.i4.6
0x44bcd  newarr   [mscorlib]System.Object
0x44bd2  dup
0x44bd3  ldc.i4.0
0x44bd4  ldarg.0
0x44bd5  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_SubscriptionID()
0x44bda  brtrue.s loc_44BE3
0x44bdc  ldstr    aNull_0// "null"
0x44be1  br.s     loc_44BE9
0x44be3  ldarg.0
0x44be4  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_SubscriptionID()
0x44be9  stelem.ref
0x44bea  dup
0x44beb  ldc.i4.1
0x44bec  ldarg.0
0x44bed  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44bf2  brtrue.s loc_44BFB
0x44bf4  ldstr    aNull_0// "null"
0x44bf9  br.s     loc_44C06
0x44bfb  ldarg.0
0x44bfc  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44c01  call     string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ThisToXml(class Microsoft.ReportingServices.Library.Soap.ExtensionSettings settings)
0x44c06  stelem.ref
0x44c07  dup
0x44c08  ldc.i4.2
0x44c09  ldarg.0
0x44c0a  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Description()
0x44c0f  brtrue.s loc_44C18
0x44c11  ldstr    aNull_0// "null"
0x44c16  br.s     loc_44C1E
0x44c18  ldarg.0
0x44c19  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Description()
0x44c1e  stelem.ref
0x44c1f  dup
0x44c20  ldc.i4.3
0x44c21  ldarg.0
0x44c22  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44c27  brtrue.s loc_44C30
0x44c29  ldstr    aNull_0// "null"
0x44c2e  br.s     loc_44C36
0x44c30  ldarg.0
0x44c31  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44c36  stelem.ref
0x44c37  dup
0x44c38  ldc.i4.4
0x44c39  ldarg.0
0x44c3a  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_MatchData()
0x44c3f  brtrue.s loc_44C48
0x44c41  ldstr    aNull_0// "null"
0x44c46  br.s     loc_44C4E
0x44c48  ldarg.0
0x44c49  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_MatchData()
0x44c4e  stelem.ref
0x44c4f  dup
0x44c50  ldc.i4.5
0x44c51  ldarg.0
0x44c52  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44c57  brtrue.s loc_44C60
0x44c59  ldstr    aNull_0// "null"
0x44c5e  br.s     loc_44C6B
0x44c60  ldarg.0
0x44c61  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44c66  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x44c6b  stelem.ref
0x44c6c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44c71  stloc.0
0x44c72  ldloc.0
0x44c73  ret
```
