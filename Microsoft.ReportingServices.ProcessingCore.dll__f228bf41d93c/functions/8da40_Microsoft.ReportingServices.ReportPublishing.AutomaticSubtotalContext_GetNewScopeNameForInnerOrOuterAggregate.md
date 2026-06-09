# Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::GetNewScopeNameForInnerOrOuterAggregate

- ea: `0x8da40`
- end: `0x8db7d`
- name: `Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::GetNewScopeNameForInnerOrOuterAggregate`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0xef920`

## callees

- `0x8d780`
- `0x8d870`
- `0x8da40`
- `0x8db80`
- `0xbd170`
- `0xbd1c0`
- `0xbd250`
- `0xbd880`
- `0xef900`
- `0x124a70`
- `0x22efb0`

## string_xrefs

- `0x8da98`: `Unknown object type in GetNewScopeNameForNestedAggregate: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8da40  ldarg.1
0x8da41  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0x8da46  callvirt instance string PublishingValidationInfo::get_Scope()
0x8da4b  stloc.0
0x8da4c  ldarg.0
0x8da4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope> Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeNamesToClone
0x8da52  ldloc.0
0x8da53  ldloca.s 1
0x8da55  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope>::TryGetValue(var<u1>, !!T0)
0x8da5a  brfalse.s loc_8DAAE
0x8da5c  ldloc.1
0x8da5d  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion
0x8da62  stloc.s  5
0x8da64  ldloc.s  5
0x8da66  brfalse.s loc_8DA77
0x8da68  ldarg.0
0x8da69  ldloc.0
0x8da6a  ldloc.s  5
0x8da6c  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner::get_IsClone()
0x8da71  call     instance string Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::CreateUniqueReportItemName(string oldName, bool isClone)
0x8da76  ret
0x8da77  ldloc.1
0x8da78  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.ReportHierarchyNode
0x8da7d  stloc.s  6
0x8da7f  ldloc.s  6
0x8da81  brfalse.s loc_8DA92
0x8da83  ldarg.0
0x8da84  ldloc.0
0x8da85  ldloc.s  6
0x8da87  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner::get_IsClone()
0x8da8c  call     instance string Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::CreateAndRegisterUniqueGroupName(string oldName, bool isClone)
0x8da91  ret
0x8da92  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x8da97  ldc.i4.0
0x8da98  ldstr    aUnknownObjectT// "Unknown object type in GetNewScopeNameF"...
0x8da9d  ldc.i4.1
0x8da9e  newarr   [mscorlib]System.Object
0x8daa3  dup
0x8daa4  ldc.i4.0
0x8daa5  ldloc.1
0x8daa6  stelem.ref
0x8daa7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x8daac  ldloc.0
0x8daad  ret
0x8daae  ldarg.0
0x8daaf  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8dab4  ldarg.0
0x8dab5  ldfld    string Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_currentScope
0x8daba  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope Microsoft.ReportingServices.ReportPublishing.ScopeTree::GetScopeByName(string scopeName)
0x8dabf  stloc.3
0x8dac0  ldloc.3
0x8dac1  brfalse.s loc_8DAE7
0x8dac3  ldarg.0
0x8dac4  ldarg.1
0x8dac5  ldloc.3
0x8dac6  call     instance bool Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::NeedsSubtotalScopeLift(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo aggregate, class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope displayScope)
0x8dacb  brfalse.s loc_8DAE7
0x8dacd  ldarg.0
0x8dace  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8dad3  ldarg.0
0x8dad4  ldfld    string Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_currentScopeBeingCloned
0x8dad9  ldarg.0
0x8dada  ldfld    string Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_currentScope
0x8dadf  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.ScopeTree::MeasureScopeDistance(string innerScopeName, string outerScopeName)
0x8dae4  stloc.2
0x8dae5  br.s     loc_8DAE9
0x8dae7  ldc.i4.m1
0x8dae8  stloc.2
0x8dae9  ldloc.2
0x8daea  ldc.i4.0
0x8daeb  bgt.s    loc_8DAEF
0x8daed  ldloc.0
0x8daee  ret
0x8daef  ldarg.0
0x8daf0  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8daf5  ldloc.0
0x8daf6  ldloc.2
0x8daf7  callvirt instance string Microsoft.ReportingServices.ReportPublishing.ScopeTree::FindAncestorScopeName(string scopeName, int32 ancestorLevel)
0x8dafc  stloc.s  4
0x8dafe  ldloc.s  4
0x8db00  brtrue.s loc_8DB04
0x8db02  ldloc.0
0x8db03  ret
0x8db04  ldarg.0
0x8db05  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_outerAggregate
0x8db0a  brfalse.s loc_8DB7A
0x8db0c  ldarg.0
0x8db0d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_outerAggregate
0x8db12  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0x8db17  callvirt instance string PublishingValidationInfo::get_Scope()
0x8db1c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8db21  brtrue.s loc_8DB7A
0x8db23  ldarg.0
0x8db24  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8db29  ldarg.0
0x8db2a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_outerAggregate
0x8db2f  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0x8db34  callvirt instance string PublishingValidationInfo::get_Scope()
0x8db39  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope Microsoft.ReportingServices.ReportPublishing.ScopeTree::GetScopeByName(string scopeName)
0x8db3e  stloc.s  7
0x8db40  ldarg.0
0x8db41  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8db46  ldloc.s  4
0x8db48  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope Microsoft.ReportingServices.ReportPublishing.ScopeTree::GetScopeByName(string scopeName)
0x8db4d  stloc.s  8
0x8db4f  ldloc.s  7
0x8db51  brfalse.s loc_8DB7A
0x8db53  ldloc.s  8
0x8db55  brfalse.s loc_8DB7A
0x8db57  ldarg.0
0x8db58  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeTree Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_scopeTree
0x8db5d  ldloc.s  8
0x8db5f  ldloc.s  7
0x8db61  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.ScopeTree::IsParentScope(class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope outerScope, class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope innerScope)
0x8db66  brfalse.s loc_8DB7A
0x8db68  ldarg.0
0x8db69  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::m_outerAggregate
0x8db6e  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0x8db73  callvirt instance string PublishingValidationInfo::get_Scope()
0x8db78  stloc.s  4
0x8db7a  ldloc.s  4
0x8db7c  ret
```
