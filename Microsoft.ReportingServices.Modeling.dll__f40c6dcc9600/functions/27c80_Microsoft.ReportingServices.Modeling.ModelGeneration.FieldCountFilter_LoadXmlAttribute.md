# Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::LoadXmlAttribute

- ea: `0x27c80`
- end: `0x27d73`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::LoadXmlAttribute`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9c30`
- `0xa760`
- `0xa7b0`
- `0xa9e0`
- `0xaa40`
- `0x27c80`
- `0x27f10`
- `0x293a0`

## string_xrefs

- `0x27d25`: `Unhandled XmlFieldType `

## pseudocode

```c

```

## disassembly

```asm
0x27c80  ldarg.1
0x27c81  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x27c86  brfalse  loc_27D6A
0x27c8b  ldarg.1
0x27c8c  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x27c91  stloc.0
0x27c92  ldloc.0
0x27c93  ldstr    aCount// "count"
0x27c98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27c9d  brtrue.s loc_27CD1
0x27c9f  ldloc.0
0x27ca0  ldstr    aFieldtype// "fieldType"
0x27ca5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27caa  brtrue.s loc_27CF1
0x27cac  ldloc.0
0x27cad  ldstr    aHidden_0// "hidden"
0x27cb2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27cb7  brtrue   loc_27D44
0x27cbc  ldloc.0
0x27cbd  ldstr    aIsaggregate_0// "isAggregate"
0x27cc2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27cc7  brtrue   loc_27D57
0x27ccc  br       loc_27D6A
0x27cd1  ldarg.0
0x27cd2  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.NumericCompareExpression Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::m_compareExpr
0x27cd7  ldarg.1
0x27cd8  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0x27cdd  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.NumericCompareExpression::Parse(string expr)
0x27ce2  brtrue.s loc_27CEF
0x27ce4  ldstr    aInvalidCountEx// "Invalid count expression"
0x27ce9  newobj   instance void Microsoft.ReportingServices.Modeling.RuleConfigurationException::.ctor(string traceMessage)
0x27cee  throw
0x27cef  ldc.i4.1
0x27cf0  ret
0x27cf1  ldarg.1
0x27cf2  callvirt T0x2B0000F9
0x27cf7  stloc.1
0x27cf8  ldloc.1
0x27cf9  brfalse.s loc_27D01
0x27cfb  ldloc.1
0x27cfc  ldc.i4.1
0x27cfd  beq.s    loc_27D13
0x27cff  br.s     loc_27D25
0x27d01  ldarg.0
0x27d02  ldtoken  Microsoft.ReportingServices.Modeling.ModelAttribute
0x27d07  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27d0c  stfld    class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::m_fieldType
0x27d11  br.s     loc_27D42
0x27d13  ldarg.0
0x27d14  ldtoken  Microsoft.ReportingServices.Modeling.ModelRole
0x27d19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27d1e  stfld    class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::m_fieldType
0x27d23  br.s     loc_27D42
0x27d25  ldstr    aUnhandledXmlfi// "Unhandled XmlFieldType "
0x27d2a  ldloca.s 1
0x27d2c  constrained. XmlFieldType
0x27d32  callvirt instance string [mscorlib]System.Object::ToString()
0x27d37  call     string [mscorlib]System.String::Concat(string, string)
0x27d3c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x27d41  throw
0x27d42  ldc.i4.1
0x27d43  ret
0x27d44  ldarg.0
0x27d45  ldarg.1
0x27d46  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0x27d4b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x27d50  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::m_hidden
0x27d55  ldc.i4.1
0x27d56  ret
0x27d57  ldarg.0
0x27d58  ldarg.1
0x27d59  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0x27d5e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x27d63  stfld    valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter::m_isAggregate
0x27d68  ldc.i4.1
0x27d69  ret
0x27d6a  ldarg.0
0x27d6b  ldarg.1
0x27d6c  ldarg.2
0x27d6d  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.Filter::LoadXmlAttribute(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, class Microsoft.ReportingServices.Modeling.ModelGeneration.IXmlObjectFactory objectFactory)
0x27d72  ret
```
