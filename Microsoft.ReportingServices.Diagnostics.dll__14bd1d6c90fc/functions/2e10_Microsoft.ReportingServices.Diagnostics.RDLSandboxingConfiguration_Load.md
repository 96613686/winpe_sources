# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Load

- ea: `0x2e10`
- end: `0x2f6b`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Load`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x17c0`
- `0x2e10`
- `0x3050`
- `0x31d0`

## pseudocode

```c

```

## disassembly

```asm
0x2e10  ldarg.1
0x2e11  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x2e16  stloc.0
0x2e17  br       loc_2F4E
0x2e1c  ldloca.s 0
0x2e1e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x2e23  stloc.1
0x2e24  ldloca.s 1
0x2e26  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x2e2b  stloc.2
0x2e2c  ldloca.s 1
0x2e2e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x2e33  stloc.3
0x2e34  ldloc.2
0x2e35  ldstr    aMaxexpressionl// "MaxExpressionLength"
0x2e3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e3f  brtrue.s loc_2E8A
0x2e41  ldloc.2
0x2e42  ldstr    aMaxresourcesiz// "MaxResourceSize"
0x2e47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e4c  brtrue.s loc_2EA0
0x2e4e  ldloc.2
0x2e4f  ldstr    aMaxstringresul// "MaxStringResultLength"
0x2e54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e59  brtrue.s loc_2EB6
0x2e5b  ldloc.2
0x2e5c  ldstr    aMaxarrayresult// "MaxArrayResultLength"
0x2e61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e66  brtrue.s loc_2ECC
0x2e68  ldloc.2
0x2e69  ldstr    aTypes// "Types"
0x2e6e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e73  brtrue.s loc_2EDF
0x2e75  ldloc.2
0x2e76  ldstr    aMembers// "Members"
0x2e7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e80  brtrue   loc_2F3D
0x2e85  br       loc_2F4E
0x2e8a  ldarg.0
0x2e8b  ldloc.3
0x2e8c  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2e91  unbox.any [mscorlib]System.Int32
0x2e96  stfld    int32 Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_maxExpressionLength
0x2e9b  br       loc_2F4E
0x2ea0  ldarg.0
0x2ea1  ldloc.3
0x2ea2  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2ea7  unbox.any [mscorlib]System.Int32
0x2eac  stfld    int32 Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_maxResourceSizeKB
0x2eb1  br       loc_2F4E
0x2eb6  ldarg.0
0x2eb7  ldloc.3
0x2eb8  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2ebd  unbox.any [mscorlib]System.Int32
0x2ec2  stfld    int32 Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_maxStringResultLength
0x2ec7  br       loc_2F4E
0x2ecc  ldarg.0
0x2ecd  ldloc.3
0x2ece  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2ed3  unbox.any [mscorlib]System.Int32
0x2ed8  stfld    int32 Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_maxArrayResultLength
0x2edd  br.s     loc_2F4E
0x2edf  ldarg.0
0x2ee0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRdlSandboxTypeInfo>::.ctor()
0x2ee5  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRdlSandboxTypeInfo> Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_allowedTypes
0x2eea  ldloc.3
0x2eeb  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2ef0  castclass class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>
0x2ef5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::GetEnumerator()
0x2efa  stloc.s  4
0x2efc  br.s     loc_2F24
0x2efe  ldloca.s 4
0x2f00  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::get_Current()
0x2f05  stloc.s  5
0x2f07  newobj   instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::.ctor()
0x2f0c  stloc.s  6
0x2f0e  ldloc.s  6
0x2f10  ldloc.s  5
0x2f12  callvirt instance void Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Load(class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag properties)
0x2f17  ldarg.0
0x2f18  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRdlSandboxTypeInfo> Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_allowedTypes
0x2f1d  ldloc.s  6
0x2f1f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRdlSandboxTypeInfo>::Add(var<u1>)
0x2f24  ldloca.s 4
0x2f26  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::MoveNext()
0x2f2b  brtrue.s loc_2EFE
0x2f2d  leave.s  loc_2F4E
0x2f2f  ldloca.s 4
0x2f31  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>
0x2f37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f3c  endfinally
0x2f3d  ldarg.0
0x2f3e  ldloc.3
0x2f3f  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2f44  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0x2f49  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::m_deniedMembers
0x2f4e  ldloca.s 0
0x2f50  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x2f55  brtrue   loc_2E1C
0x2f5a  leave.s  loc_2F6A
0x2f5c  ldloca.s 0
0x2f5e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x2f64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f69  endfinally
0x2f6a  ret
```
