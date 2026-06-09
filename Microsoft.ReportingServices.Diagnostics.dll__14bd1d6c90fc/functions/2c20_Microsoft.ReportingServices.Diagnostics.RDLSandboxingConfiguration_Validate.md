# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Validate

- ea: `0x2c20`
- end: `0x2e03`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::Validate`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4bd0`

## callees

- `0x17c0`
- `0x17d0`
- `0x17e0`
- `0x1980`
- `0x2c20`
- `0x30e0`

## pseudocode

```c

```

## disassembly

```asm
0x2c20  ldarg.1
0x2c21  ldc.i4.3
0x2c22  ldstr    aRdlSandboxMode// "RDL Sandbox mode enabled"
0x2c27  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2c2c  ldarg.2
0x2c2d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::GetEnumerator()
0x2c32  stloc.0
0x2c33  br       loc_2DE6
0x2c38  ldloca.s 0
0x2c3a  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Current()
0x2c3f  stloc.1
0x2c40  ldloca.s 1
0x2c42  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Key()
0x2c47  stloc.2
0x2c48  ldloca.s 1
0x2c4a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Value()
0x2c4f  stloc.3
0x2c50  ldloc.2
0x2c51  ldstr    aMaxexpressionl// "MaxExpressionLength"
0x2c56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c5b  brtrue.s loc_2C9F
0x2c5d  ldloc.2
0x2c5e  ldstr    aMaxresourcesiz// "MaxResourceSize"
0x2c63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c68  brtrue.s loc_2CE4
0x2c6a  ldloc.2
0x2c6b  ldstr    aMaxstringresul// "MaxStringResultLength"
0x2c70  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c75  brtrue   loc_2D26
0x2c7a  ldloc.2
0x2c7b  ldstr    aMaxarrayresult// "MaxArrayResultLength"
0x2c80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c85  brtrue   loc_2D68
0x2c8a  ldloc.2
0x2c8b  ldstr    aTypes// "Types"
0x2c90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c95  brtrue   loc_2DA7
0x2c9a  br       loc_2DE6
0x2c9f  ldarg.0
0x2ca0  ldarg.1
0x2ca1  ldloc.2
0x2ca2  ldloc.3
0x2ca3  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x2ca8  ldc.i4   0x3E8
0x2cad  ldstr    aCharacters// "characters"
0x2cb2  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x2cb7  stloc.s  4
0x2cb9  ldloc.s  4
0x2cbb  ldc.i4.1
0x2cbc  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x2cc1  ldloc.s  4
0x2cc3  ldc.i4   0x7FFFFFFF
0x2cc8  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x2ccd  ldloc.3
0x2cce  ldloc.s  4
0x2cd0  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x2cd5  box      [mscorlib]System.Int32
0x2cda  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2cdf  br       loc_2DE6
0x2ce4  ldarg.0
0x2ce5  ldarg.1
0x2ce6  ldloc.2
0x2ce7  ldloc.3
0x2ce8  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x2ced  ldc.i4.s 0x64
0x2cef  ldstr    aKilobytes// "kilobytes"
0x2cf4  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x2cf9  stloc.s  5
0x2cfb  ldloc.s  5
0x2cfd  ldc.i4.1
0x2cfe  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x2d03  ldloc.s  5
0x2d05  ldc.i4   0x7FFFFFFF
0x2d0a  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x2d0f  ldloc.3
0x2d10  ldloc.s  5
0x2d12  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x2d17  box      [mscorlib]System.Int32
0x2d1c  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2d21  br       loc_2DE6
0x2d26  ldarg.0
0x2d27  ldarg.1
0x2d28  ldloc.2
0x2d29  ldloc.3
0x2d2a  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x2d2f  ldc.i4   0x3E8
0x2d34  ldstr    aCharacters// "characters"
0x2d39  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x2d3e  stloc.s  6
0x2d40  ldloc.s  6
0x2d42  ldc.i4.1
0x2d43  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x2d48  ldloc.s  6
0x2d4a  ldc.i4   0x7FFFFFFF
0x2d4f  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x2d54  ldloc.3
0x2d55  ldloc.s  6
0x2d57  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x2d5c  box      [mscorlib]System.Int32
0x2d61  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2d66  br.s     loc_2DE6
0x2d68  ldarg.0
0x2d69  ldarg.1
0x2d6a  ldloc.2
0x2d6b  ldloc.3
0x2d6c  callvirt instance string Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_SpecifiedValue()
0x2d71  ldc.i4.s 0x64
0x2d73  ldstr    aItems// "items"
0x2d78  newobj   instance void Microsoft.ReportingServices.Diagnostics.IntParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource parameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, string name, string configValue, int32 defaultValue, string units)
0x2d7d  stloc.s  7
0x2d7f  ldloc.s  7
0x2d81  ldc.i4.1
0x2d82  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MinValue(var<u1>)
0x2d87  ldloc.s  7
0x2d89  ldc.i4   0x7FFFFFFF
0x2d8e  callvirt instance void class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::set_MaxValue(var<u1>)
0x2d93  ldloc.3
0x2d94  ldloc.s  7
0x2d96  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.RangedParameter`1<int32>::get_Value()
0x2d9b  box      [mscorlib]System.Int32
0x2da0  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::set_Value(object value)
0x2da5  br.s     loc_2DE6
0x2da7  ldloc.3
0x2da8  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2dad  castclass class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>
0x2db2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::GetEnumerator()
0x2db7  stloc.s  8
0x2db9  br.s     loc_2DCD
0x2dbb  ldloca.s 8
0x2dbd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::get_Current()
0x2dc2  stloc.s  9
0x2dc4  ldarg.0
0x2dc5  ldarg.1
0x2dc6  ldloc.s  9
0x2dc8  call     void Microsoft.ReportingServices.Diagnostics.RDLSandboxingTypeInfo::Validate(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource paramSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace tracer, class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag properties)
0x2dcd  ldloca.s 8
0x2dcf  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>::MoveNext()
0x2dd4  brtrue.s loc_2DBB
0x2dd6  leave.s  loc_2DE6
0x2dd8  ldloca.s 8
0x2dda  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.RDLSandboxingPropertyBag>
0x2de0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2de5  endfinally
0x2de6  ldloca.s 0
0x2de8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::MoveNext()
0x2ded  brtrue   loc_2C38
0x2df2  leave.s  loc_2E02
0x2df4  ldloca.s 0
0x2df6  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>
0x2dfc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e01  endfinally
0x2e02  ret
```
