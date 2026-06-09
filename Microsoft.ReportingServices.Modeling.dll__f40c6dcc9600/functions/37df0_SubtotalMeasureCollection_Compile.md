# SubtotalMeasureCollection::Compile

- ea: `0x37df0`
- end: `0x37e8e`
- name: `SubtotalMeasureCollection::Compile`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x22990`

## callees

- `0x84f0`
- `0x8500`
- `0xafc0`
- `0xb030`
- `0xb040`
- `0x187f0`
- `0x18910`
- `0x23680`
- `0x240e0`
- `0x24630`
- `0x25a90`
- `0x25b70`
- `0x37df0`

## string_xrefs

- `0x37e09`: `SubtotalMeasures.MeasureName`
- `0x37e2a`: `SubtotalMeasures.MeasureName`

## pseudocode

```c

```

## disassembly

```asm
0x37df0  ldarg.0
0x37df1  call     instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Expression>::GetEnumerator()
0x37df6  stloc.0
0x37df7  br.s     loc_37E66
0x37df9  ldloca.s 0
0x37dfb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.Expression>::get_Current()
0x37e00  stloc.1
0x37e01  ldloca.s 2
0x37e03  ldloc.1
0x37e04  callvirt instance string Microsoft.ReportingServices.Modeling.Expression::get_Name()
0x37e09  ldstr    aSubtotalmeasur_0// "SubtotalMeasures.MeasureName"
0x37e0e  ldc.i4.1
0x37e0f  call     instance void Microsoft.ReportingServices.Modeling.ModelingReference::.ctor(string referenceByName, string propertyName, bool multipleInScope)
0x37e14  ldloc.2
0x37e15  ldarg.1
0x37e16  call     class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.SemanticQuery::TryGetMeasure(valuetype Microsoft.ReportingServices.Modeling.ModelingReference itemRef, class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x37e1b  stloc.3
0x37e1c  ldloc.3
0x37e1d  callvirt instance bool Microsoft.ReportingServices.Modeling.Expression::get_IsInvalidRefTarget()
0x37e22  brtrue.s loc_37E35
0x37e24  ldloc.3
0x37e25  ldloc.1
0x37e26  beq.s    loc_37E35
0x37e28  ldarg.1
0x37e29  ldloc.1
0x37e2a  ldstr    aSubtotalmeasur_0// "SubtotalMeasures.MeasureName"
0x37e2f  ldc.i4.1
0x37e30  call     void Microsoft.ReportingServices.Modeling.SemanticQuery::AddWrongSemanticQueryError(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.IValidationScope referencedItem, string propertyName, bool multipleInScope)
0x37e35  ldarg.1
0x37e36  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x37e3b  brfalse.s loc_37E66
0x37e3d  ldloc.1
0x37e3e  callvirt instance bool Microsoft.ReportingServices.Modeling.Expression::get_IsInvalidRefTarget()
0x37e43  brfalse.s loc_37E66
0x37e45  ldarg.1
0x37e46  ldc.i4.s 0x16
0x37e48  ldloca.s 2
0x37e4a  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x37e4f  ldarg.1
0x37e50  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x37e55  ldloca.s 2
0x37e57  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceString()
0x37e5c  call     string Microsoft.ReportingServices.Modeling.SRErrors::MeasureNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x37e61  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x37e66  ldloca.s 0
0x37e68  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.Expression>::MoveNext()
0x37e6d  brtrue.s loc_37DF9
0x37e6f  leave.s  loc_37E7F
0x37e71  ldloca.s 0
0x37e73  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.Expression>
0x37e79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37e7e  endfinally
0x37e7f  ldarg.1
0x37e80  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x37e85  brfalse.s loc_37E8D
0x37e87  ldarg.0
0x37e88  call     instance void class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Expression>::SetReadOnlyIndicator()
0x37e8d  ret
```
