# Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_InputTrace

- ea: `0x43e30`
- end: `0x43fd4`
- name: `Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_InputTrace`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x43cb0`
- `0x43ce0`
- `0x43d00`
- `0x43d20`
- `0x43d40`
- `0x43d60`
- `0x43d90`
- `0x43dc0`
- `0x43e30`
- `0x705d0`
- `0x70f40`
- `0x73350`

## string_xrefs

- `0x43e55`: `Report={0}, ExtensionSettings={1}, DataRetrievalPlan={2}, Description={3}, EventType={4}, MatchData={5}, Parameters={6}`
- `0x43f27`: `Report={0}, ExtensionSettings={1}, Description={2}, EventType={3}, MatchData={4}, Parameters={5}`

## pseudocode

```c

```

## disassembly

```asm
0x43e30  ldsfld   string [mscorlib]System.String::Empty
0x43e35  stloc.0
0x43e36  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x43e3b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x43e40  brfalse  loc_43FD2
0x43e45  ldarg.0
0x43e46  call     instance bool Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_IsDataDriven()
0x43e4b  brfalse  loc_43F22
0x43e50  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43e55  ldstr    aReport0Extensi// "Report={0}, ExtensionSettings={1}, Data"...
0x43e5a  ldc.i4.7
0x43e5b  newarr   [mscorlib]System.Object
0x43e60  dup
0x43e61  ldc.i4.0
0x43e62  ldarg.0
0x43e63  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Report()
0x43e68  brtrue.s loc_43E71
0x43e6a  ldstr    aNull_0// "null"
0x43e6f  br.s     loc_43E77
0x43e71  ldarg.0
0x43e72  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Report()
0x43e77  stelem.ref
0x43e78  dup
0x43e79  ldc.i4.1
0x43e7a  ldarg.0
0x43e7b  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x43e80  brtrue.s loc_43E89
0x43e82  ldstr    aNull_0// "null"
0x43e87  br.s     loc_43E94
0x43e89  ldarg.0
0x43e8a  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x43e8f  call     string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ThisToXml(class Microsoft.ReportingServices.Library.Soap.ExtensionSettings settings)
0x43e94  stelem.ref
0x43e95  dup
0x43e96  ldc.i4.2
0x43e97  ldarg.0
0x43e98  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_DataSettings()
0x43e9d  brtrue.s loc_43EA6
0x43e9f  ldstr    aNull_0// "null"
0x43ea4  br.s     loc_43EB1
0x43ea6  ldarg.0
0x43ea7  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_DataSettings()
0x43eac  call     string Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::ThisToXml(class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan dataSettings)
0x43eb1  stelem.ref
0x43eb2  dup
0x43eb3  ldc.i4.3
0x43eb4  ldarg.0
0x43eb5  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Description()
0x43eba  brtrue.s loc_43EC3
0x43ebc  ldstr    aNull_0// "null"
0x43ec1  br.s     loc_43EC9
0x43ec3  ldarg.0
0x43ec4  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Description()
0x43ec9  stelem.ref
0x43eca  dup
0x43ecb  ldc.i4.4
0x43ecc  ldarg.0
0x43ecd  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x43ed2  brtrue.s loc_43EDB
0x43ed4  ldstr    aNull_0// "null"
0x43ed9  br.s     loc_43EE1
0x43edb  ldarg.0
0x43edc  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x43ee1  stelem.ref
0x43ee2  dup
0x43ee3  ldc.i4.5
0x43ee4  ldarg.0
0x43ee5  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_MatchData()
0x43eea  brtrue.s loc_43EF3
0x43eec  ldstr    aNull_0// "null"
0x43ef1  br.s     loc_43EF9
0x43ef3  ldarg.0
0x43ef4  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_MatchData()
0x43ef9  stelem.ref
0x43efa  dup
0x43efb  ldc.i4.6
0x43efc  ldarg.0
0x43efd  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Parameters()
0x43f02  brtrue.s loc_43F0B
0x43f04  ldstr    aNull_0// "null"
0x43f09  br.s     loc_43F16
0x43f0b  ldarg.0
0x43f0c  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Parameters()
0x43f11  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x43f16  stelem.ref
0x43f17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43f1c  stloc.0
0x43f1d  br       loc_43FD2
0x43f22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43f27  ldstr    aReport0Extensi_0// "Report={0}, ExtensionSettings={1}, Desc"...
0x43f2c  ldc.i4.6
0x43f2d  newarr   [mscorlib]System.Object
0x43f32  dup
0x43f33  ldc.i4.0
0x43f34  ldarg.0
0x43f35  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Report()
0x43f3a  brtrue.s loc_43F43
0x43f3c  ldstr    aNull_0// "null"
0x43f41  br.s     loc_43F49
0x43f43  ldarg.0
0x43f44  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Report()
0x43f49  stelem.ref
0x43f4a  dup
0x43f4b  ldc.i4.1
0x43f4c  ldarg.0
0x43f4d  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x43f52  brtrue.s loc_43F5B
0x43f54  ldstr    aNull_0// "null"
0x43f59  br.s     loc_43F66
0x43f5b  ldarg.0
0x43f5c  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x43f61  call     string Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ThisToXml(class Microsoft.ReportingServices.Library.Soap.ExtensionSettings settings)
0x43f66  stelem.ref
0x43f67  dup
0x43f68  ldc.i4.2
0x43f69  ldarg.0
0x43f6a  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Description()
0x43f6f  brtrue.s loc_43F78
0x43f71  ldstr    aNull_0// "null"
0x43f76  br.s     loc_43F7E
0x43f78  ldarg.0
0x43f79  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Description()
0x43f7e  stelem.ref
0x43f7f  dup
0x43f80  ldc.i4.3
0x43f81  ldarg.0
0x43f82  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x43f87  brtrue.s loc_43F90
0x43f89  ldstr    aNull_0// "null"
0x43f8e  br.s     loc_43F96
0x43f90  ldarg.0
0x43f91  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x43f96  stelem.ref
0x43f97  dup
0x43f98  ldc.i4.4
0x43f99  ldarg.0
0x43f9a  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_MatchData()
0x43f9f  brtrue.s loc_43FA8
0x43fa1  ldstr    aNull_0// "null"
0x43fa6  br.s     loc_43FAE
0x43fa8  ldarg.0
0x43fa9  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_MatchData()
0x43fae  stelem.ref
0x43faf  dup
0x43fb0  ldc.i4.5
0x43fb1  ldarg.0
0x43fb2  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Parameters()
0x43fb7  brtrue.s loc_43FC0
0x43fb9  ldstr    aNull_0// "null"
0x43fbe  br.s     loc_43FCB
0x43fc0  ldarg.0
0x43fc1  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Parameters()
0x43fc6  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x43fcb  stelem.ref
0x43fcc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43fd1  stloc.0
0x43fd2  ldloc.0
0x43fd3  ret
```
