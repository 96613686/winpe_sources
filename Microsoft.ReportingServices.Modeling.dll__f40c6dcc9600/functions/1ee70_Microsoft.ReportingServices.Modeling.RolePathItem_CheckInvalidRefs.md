# Microsoft.ReportingServices.Modeling.RolePathItem::CheckInvalidRefs

- ea: `0x1ee70`
- end: `0x1eeec`
- name: `Microsoft.ReportingServices.Modeling.RolePathItem::CheckInvalidRefs`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x8500`
- `0x139d0`
- `0x13ae0`
- `0x15b40`
- `0x1eb40`
- `0x1ee70`
- `0x24510`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`

## string_xrefs

- `0x1ee95`: `RolePathItem.RoleID`

## pseudocode

```c

```

## disassembly

```asm
0x1ee70  ldarg.1
0x1ee71  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x1ee76  brtrue.s loc_1EE7D
0x1ee78  ldarg.2
0x1ee79  brtrue.s loc_1EE7D
0x1ee7b  ldc.i4.1
0x1ee7c  ret
0x1ee7d  ldarg.0
0x1ee7e  callvirt instance bool Microsoft.ReportingServices.Modeling.PathItem::HasInvalidRefs()
0x1ee83  brfalse.s loc_1EEEA
0x1ee85  ldarg.0
0x1ee86  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1ee8b  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelItem::get_IsInvalidRefTarget()
0x1ee90  brfalse.s loc_1EEC5
0x1ee92  ldarg.1
0x1ee93  ldc.i4.s 0x11
0x1ee95  ldstr    aRolepathitemRo// "RolePathItem.RoleID"
0x1ee9a  ldarg.1
0x1ee9b  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1eea0  ldarg.0
0x1eea1  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1eea6  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1eeab  stloc.0
0x1eeac  ldloca.s 0
0x1eeae  constrained. Microsoft.ReportingServices.Modeling.QName
0x1eeb4  callvirt instance string [mscorlib]System.Object::ToString()
0x1eeb9  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x1eebe  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1eec3  br.s     loc_1EEE8
0x1eec5  ldarg.1
0x1eec6  ldarg.0
0x1eec7  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1eecc  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x1eed1  ldarg.0
0x1eed2  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1eed7  ldarg.1
0x1eed8  ldarg.2
0x1eed9  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelRole::ValidateRelatedRoleReference(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool forceInvalidRefTargetCheck)
0x1eede  pop
0x1eedf  leave.s  loc_1EEE8
0x1eee1  ldarg.1
0x1eee2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x1eee7  endfinally
0x1eee8  ldc.i4.0
0x1eee9  ret
0x1eeea  ldc.i4.1
0x1eeeb  ret
```
