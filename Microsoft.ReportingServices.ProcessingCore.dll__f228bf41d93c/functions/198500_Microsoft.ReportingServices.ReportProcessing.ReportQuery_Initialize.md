# Microsoft.ReportingServices.ReportProcessing.ReportQuery::Initialize

- ea: `0x198500`
- end: `0x1985ad`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportQuery::Initialize`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x197c20`

## callees

- `0x18d840`
- `0x18d860`
- `0x18d900`
- `0x18ee10`
- `0x190f20`
- `0x190f30`
- `0x190f40`
- `0x190f50`
- `0x191020`
- `0x198500`
- `0x198950`
- `0x1989f0`
- `0x1a7610`

## string_xrefs

- `0x19850e`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x198500  ldarg.0
0x198501  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_commandText
0x198506  brfalse.s loc_19852B
0x198508  ldarg.0
0x198509  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_commandText
0x19850e  ldstr    aCommandtext// "CommandText"
0x198513  ldarg.1
0x198514  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context)
0x198519  ldarga.s 1
0x19851b  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x198520  ldarg.0
0x198521  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_commandText
0x198526  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::DataSetQueryCommandText(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo expression)
0x19852b  ldarg.0
0x19852c  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_queryParameters
0x198531  brfalse.s loc_1985AC
0x198533  ldarga.s 1
0x198535  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ObjectType()
0x19853a  stloc.0
0x19853b  ldarga.s 1
0x19853d  call     instance string Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ObjectName()
0x198542  stloc.1
0x198543  ldarga.s 1
0x198545  ldc.i4.s 0x17
0x198547  call     instance void Microsoft.ReportingServices.ReportProcessing.InitializationContext::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x19854c  ldarga.s 1
0x19854e  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x198553  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::QueryParametersStart()
0x198558  ldc.i4.0
0x198559  stloc.2
0x19855a  br.s     loc_198582
0x19855c  ldarg.0
0x19855d  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_queryParameters
0x198562  ldloc.2
0x198563  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterValue Microsoft.ReportingServices.ReportProcessing.ParameterValueList::get_Item(int32 index)
0x198568  stloc.3
0x198569  ldarga.s 1
0x19856b  ldloc.3
0x19856c  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ParameterValue::get_Name()
0x198571  call     instance void Microsoft.ReportingServices.ReportProcessing.InitializationContext::set_ObjectName(string value)
0x198576  ldloc.3
0x198577  ldarg.1
0x198578  ldc.i4.1
0x198579  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ParameterValue::Initialize(valuetype Microsoft.ReportingServices.ReportProcessing.InitializationContext context, bool queryParam)
0x19857e  ldloc.2
0x19857f  ldc.i4.1
0x198580  add
0x198581  stloc.2
0x198582  ldloc.2
0x198583  ldarg.0
0x198584  ldfld    class Microsoft.ReportingServices.ReportProcessing.ParameterValueList Microsoft.ReportingServices.ReportProcessing.ReportQuery::m_queryParameters
0x198589  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x19858e  blt.s    loc_19855C
0x198590  ldarga.s 1
0x198592  call     instance class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.InitializationContext::get_ExprHostBuilder()
0x198597  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::QueryParametersEnd()
0x19859c  ldarga.s 1
0x19859e  ldloc.0
0x19859f  call     instance void Microsoft.ReportingServices.ReportProcessing.InitializationContext::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1985a4  ldarga.s 1
0x1985a6  ldloc.1
0x1985a7  call     instance void Microsoft.ReportingServices.ReportProcessing.InitializationContext::set_ObjectName(string value)
0x1985ac  ret
```
