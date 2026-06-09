# Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::Initialize

- ea: `0x116530`
- end: `0x1165de`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::Initialize`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x114110`

## callees

- `0x116530`
- `0x117ce0`
- `0x13cb30`
- `0x13cc20`
- `0x13de70`
- `0x13de80`
- `0x13de90`
- `0x13dea0`
- `0x13dfc0`
- `0x14d5f0`
- `0x14d610`
- `0x14d6b0`

## string_xrefs

- `0x11653e`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x116530  ldarg.0
0x116531  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_commandText
0x116536  brfalse.s loc_11655B
0x116538  ldarg.0
0x116539  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_commandText
0x11653e  ldstr    aCommandtext// "CommandText"
0x116543  ldarg.1
0x116544  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::Initialize(string propertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context)
0x116549  ldarga.s 1
0x11654b  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0x116550  ldarg.0
0x116551  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_commandText
0x116556  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::DataSetQueryCommandText(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0x11655b  ldarg.0
0x11655c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_queryParameters
0x116561  brfalse.s loc_1165DD
0x116563  ldarga.s 1
0x116565  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ObjectType()
0x11656a  stloc.0
0x11656b  ldarga.s 1
0x11656d  call     instance string Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ObjectName()
0x116572  stloc.1
0x116573  ldarga.s 1
0x116575  ldc.i4.s 0x17
0x116577  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x11657c  ldarga.s 1
0x11657e  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0x116583  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::QueryParametersStart()
0x116588  ldc.i4.0
0x116589  stloc.2
0x11658a  br.s     loc_1165B3
0x11658c  ldarg.0
0x11658d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_queryParameters
0x116592  ldloc.2
0x116593  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue>::get_Item(!!T0)
0x116598  stloc.3
0x116599  ldarga.s 1
0x11659b  ldloc.3
0x11659c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::get_Name()
0x1165a1  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::set_ObjectName(string value)
0x1165a6  ldloc.3
0x1165a7  ldnull
0x1165a8  ldarg.1
0x1165a9  ldc.i4.1
0x1165aa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue::Initialize(string containerPropertyName, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext context, bool queryParam)
0x1165af  ldloc.2
0x1165b0  ldc.i4.1
0x1165b1  add
0x1165b2  stloc.2
0x1165b3  ldloc.2
0x1165b4  ldarg.0
0x1165b5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::m_queryParameters
0x1165ba  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue>::get_Count()
0x1165bf  blt.s    loc_11658C
0x1165c1  ldarga.s 1
0x1165c3  call     instance class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::get_ExprHostBuilder()
0x1165c8  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::QueryParametersEnd()
0x1165cd  ldarga.s 1
0x1165cf  ldloc.0
0x1165d0  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1165d5  ldarga.s 1
0x1165d7  ldloc.1
0x1165d8  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.InitializationContext::set_ObjectName(string value)
0x1165dd  ret
```
