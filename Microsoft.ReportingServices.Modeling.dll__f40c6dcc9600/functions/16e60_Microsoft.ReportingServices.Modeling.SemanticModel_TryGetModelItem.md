# Microsoft.ReportingServices.Modeling.SemanticModel::TryGetModelItem

- ea: `0x16e60`
- end: `0x16fa5`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::TryGetModelItem`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9860`
- `0xaff0`
- `0xb020`
- `0xb030`
- `0xb040`
- `0xb050`
- `0x139e0`
- `0x13a70`
- `0x13ae0`
- `0x14070`
- `0x16e60`
- `0x16fb0`
- `0x24510`
- `0x24530`
- `0x24550`
- `0x24570`
- `0x25590`
- `0x25a30`
- `0x25a50`
- `0x25a90`
- `0x25b70`
- `0x25b80`
- `0x25b90`

## pseudocode

```c

```

## disassembly

```asm
0x16e60  ldarg.0
0x16e61  ldarg.1
0x16e62  ldarg.2
0x16e63  call     instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::TryResolveModelItemReference(valuetype Microsoft.ReportingServices.Modeling.ModelingReference itemRef, class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x16e68  stloc.0
0x16e69  ldloc.0
0x16e6a  brtrue   loc_16F2C
0x16e6f  call     T0x2B00007D
0x16e74  box      mvar<u1>
0x16e79  stloc.0
0x16e7a  ldarga.s 1
0x16e7c  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.QName> Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceByID()
0x16e81  stloc.2
0x16e82  ldloca.s 2
0x16e84  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.QName>::get_HasValue()
0x16e89  brfalse.s loc_16EA2
0x16e8b  ldloc.0
0x16e8c  ldarga.s 1
0x16e8e  call     instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.QName> Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceByID()
0x16e93  stloc.2
0x16e94  ldloca.s 2
0x16e96  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.QName>::get_Value()
0x16e9b  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::set_ID(valuetype Microsoft.ReportingServices.Modeling.QName value)
0x16ea0  br.s     loc_16EB8
0x16ea2  ldarga.s 1
0x16ea4  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceByName()
0x16ea9  brfalse.s loc_16EB8
0x16eab  ldloc.0
0x16eac  ldarga.s 1
0x16eae  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceByName()
0x16eb3  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::set_Name(string value)
0x16eb8  ldloc.0
0x16eb9  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_IsInvalidRefTarget()
0x16ebe  brtrue.s loc_16ECB
0x16ec0  ldstr    aInvalidRefTarg// "Invalid ref target has false item.IsInv"...
0x16ec5  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x16eca  throw
0x16ecb  ldarg.2
0x16ecc  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::SetInvalidRefsFlag()
0x16ed1  ldarga.s 1
0x16ed3  call     instance bool Microsoft.ReportingServices.Modeling.ModelingReference::get_MultipleInScope()
0x16ed8  brfalse.s loc_16EF6
0x16eda  ldarga.s 1
0x16edc  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x16ee1  ldarg.2
0x16ee2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x16ee7  ldarga.s 1
0x16ee9  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceString()
0x16eee  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x16ef3  stloc.1
0x16ef4  br.s     loc_16F10
0x16ef6  ldarga.s 1
0x16ef8  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x16efd  ldarg.2
0x16efe  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x16f03  ldarga.s 1
0x16f05  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_ReferenceString()
0x16f0a  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x16f0f  stloc.1
0x16f10  ldarg.2
0x16f11  callvirt instance bool Microsoft.ReportingServices.Modeling.ValidationContext::get_ShouldCheckInvalidRefsDuringTryGet()
0x16f16  brfalse.s loc_16F23
0x16f18  ldarg.2
0x16f19  ldc.i4.s 0x11
0x16f1b  ldloc.1
0x16f1c  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x16f21  br.s     loc_16F2C
0x16f23  ldarg.2
0x16f24  ldc.i4.s 0x11
0x16f26  ldloc.1
0x16f27  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedWarning(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x16f2c  ldloc.0
0x16f2d  isinst   mvar<u1>
0x16f32  brtrue.s loc_16F9E
0x16f34  ldarga.s 1
0x16f36  call     instance bool Microsoft.ReportingServices.Modeling.ModelingReference::get_MultipleInScope()
0x16f3b  brfalse.s loc_16F67
0x16f3d  ldarga.s 1
0x16f3f  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x16f44  ldarg.2
0x16f45  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x16f4a  ldloc.0
0x16f4b  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x16f50  ldtoken  mvar<u1>
0x16f55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f5a  call     string Microsoft.ReportingServices.Modeling.ModelItem::GetConcreteElementNames(class [mscorlib]System.Type type)
0x16f5f  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidReferencedItem_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName, string expectedTypes)
0x16f64  stloc.3
0x16f65  br.s     loc_16F8F
0x16f67  ldarga.s 1
0x16f69  call     instance string Microsoft.ReportingServices.Modeling.ModelingReference::get_PropertyName()
0x16f6e  ldarg.2
0x16f6f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x16f74  ldloc.0
0x16f75  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x16f7a  ldtoken  mvar<u1>
0x16f7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f84  call     string Microsoft.ReportingServices.Modeling.ModelItem::GetConcreteElementNames(class [mscorlib]System.Type type)
0x16f89  call     string Microsoft.ReportingServices.Modeling.SRErrors::InvalidReferencedItem(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName, string expectedTypes)
0x16f8e  stloc.3
0x16f8f  ldarg.2
0x16f90  ldc.i4.s 0x12
0x16f92  ldloc.3
0x16f93  callvirt instance class Microsoft.ReportingServices.Modeling.ValidationMessage Microsoft.ReportingServices.Modeling.ValidationContext::CreateScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x16f98  newobj   instance void Microsoft.ReportingServices.Modeling.ValidationException::.ctor(class Microsoft.ReportingServices.Modeling.ValidationMessage message)
0x16f9d  throw
0x16f9e  ldloc.0
0x16f9f  unbox.any mvar<u1>
0x16fa4  ret
```
