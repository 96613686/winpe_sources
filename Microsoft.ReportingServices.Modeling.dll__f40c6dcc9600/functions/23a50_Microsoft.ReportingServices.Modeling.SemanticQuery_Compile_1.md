# Microsoft.ReportingServices.Modeling.SemanticQuery::Compile_1

- ea: `0x23a50`
- end: `0x23af3`
- name: `Microsoft.ReportingServices.Modeling.SemanticQuery::Compile_1`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x23a30`

## callees

- `0x8480`
- `0x85a0`
- `0x85b0`
- `0x96f0`
- `0x9cf0`
- `0xa5a0`
- `0x233f0`
- `0x23a50`
- `0x23da0`
- `0x25ac0`
- `0x25ae0`

## string_xrefs

- `0x23a59`: `includeSecurityFilter`

## pseudocode

```c

```

## disassembly

```asm
0x23a50  ldarg.s  7
0x23a52  brtrue.s loc_23A64
0x23a54  ldarg.2
0x23a55  ldc.i4.4
0x23a56  and
0x23a57  brfalse.s loc_23A64
0x23a59  ldstr    aIncludesecurit_0// "includeSecurityFilter"
0x23a5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x23a63  throw
0x23a64  ldarg.0
0x23a65  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.SemanticQuery::m_model
0x23a6a  brfalse.s loc_23A79
0x23a6c  ldarg.0
0x23a6d  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.SemanticQuery::m_model
0x23a72  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x23a77  brtrue.s loc_23A84
0x23a79  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_SemanticQuery_ModelMustBeCompiled()
0x23a7e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x23a83  throw
0x23a84  ldc.i4.1
0x23a85  ldarg.2
0x23a86  ldarg.s  4
0x23a88  ldarg.s  5
0x23a8a  ldarg.s  6
0x23a8c  ldarg.s  7
0x23a8e  newobj   instance void Microsoft.ReportingServices.Modeling.CompilationContext::.ctor(bool persist, valuetype Microsoft.ReportingServices.Modeling.QueryCompilationOptions queryOptions, string userID, string userCulture, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> now, class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> includeSecurityFilter)
0x23a93  stloc.0
0x23a94  ldloc.0
0x23a95  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x23a9a  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::set_ParameterValues(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> value)
0x23a9f  ldarg.3
0x23aa0  brfalse.s loc_23AD2
0x23aa2  ldarg.3
0x23aa3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::GetEnumerator()
0x23aa8  stloc.1
0x23aa9  br.s     loc_23ABE
0x23aab  ldloc.1
0x23aac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x23ab1  stloc.2
0x23ab2  ldloc.0
0x23ab3  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Modeling.CompilationContext::get_ParameterValues()
0x23ab8  ldloc.2
0x23ab9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::Add(var<u1>)
0x23abe  ldloc.1
0x23abf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23ac4  brtrue.s loc_23AAB
0x23ac6  leave.s  loc_23AD2
0x23ac8  ldloc.1
0x23ac9  brfalse.s loc_23AD1
0x23acb  ldloc.1
0x23acc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23ad1  endfinally
0x23ad2  ldarg.0
0x23ad3  ldarg.1
0x23ad4  ldloc.0
0x23ad5  call     class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::get_Strict()
0x23ada  call     instance void Microsoft.ReportingServices.Modeling.SemanticQuery::Load(class [System.Xml]System.Xml.XmlReader xr, class Microsoft.ReportingServices.Modeling.ValidationContext validationCtx, class Microsoft.ReportingServices.Modeling.SemanticModelingSchema schema)
0x23adf  ldarg.0
0x23ae0  ldloc.0
0x23ae1  call     instance void Microsoft.ReportingServices.Modeling.SemanticQuery::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x23ae6  ldloc.0
0x23ae7  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::ThrowIfErrors()
0x23aec  ldloc.0
0x23aed  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationMessageCollection Microsoft.ReportingServices.Modeling.ValidationContext::GetMessages()
0x23af2  ret
```
