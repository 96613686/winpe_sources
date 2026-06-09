# Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::SetupObjectModels

- ea: `0x1fdba0`
- end: `0x1fe3e5`
- name: `Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::SetupObjectModels`
- size: `2117`
- prototype: ``
- caller_count: `3`
- callee_count: `80`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1fd940`
- `0x1fd9a0`
- `0x1fda80`

## callees

- `0xc1910`
- `0xc1930`
- `0xc1a10`
- `0xc1a30`
- `0xc1a60`
- `0xc1a70`
- `0xc1a80`
- `0xc1b00`
- `0xc1b30`
- `0xc1d20`
- `0xc1fa0`
- `0xd7450`
- `0xd7780`
- `0xd7790`
- `0xd7820`
- `0xd7830`
- `0xd7840`
- `0xd7a20`
- `0xd7f40`
- `0xd7f50`
- `0xd7f70`
- `0xd7fa0`
- `0xd7fb0`
- `0xd7fd0`
- `0xd80f0`
- `0xd8740`
- `0xd8920`
- `0xd9350`
- `0xd9390`
- `0xd9850`
- `0xd9860`
- `0xd9bd0`
- `0xd9bf0`
- `0xda0b0`
- `0xda0c0`
- `0x10df20`
- `0x10fcb0`
- `0x111830`
- `0x114be0`
- `0x114c00`
- `0x1150f0`
- `0x116890`
- `0x117860`
- `0x117930`
- `0x121df0`
- `0x122200`
- `0x122220`
- `0x124ca0`
- `0x12c140`
- `0x12c1a0`

## string_xrefs

- `0x1fddd5`: `SubReport not last in instance path.`

## pseudocode

```c

```

## disassembly

```asm
0x1fdba0  ldnull
0x1fdba1  stloc.0
0x1fdba2  ldnull
0x1fdba3  stloc.1
0x1fdba4  ldc.i4.m1
0x1fdba5  stloc.2
0x1fdba6  ldarg.0
0x1fdba7  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdbac  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportInstance Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_CurrentReportInstance()
0x1fdbb1  stloc.3
0x1fdbb2  ldarg.0
0x1fdbb3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_lastInstancePath
0x1fdbb8  stloc.s  4
0x1fdbba  ldnull
0x1fdbbb  stloc.s  5
0x1fdbbd  ldc.i4.0
0x1fdbbe  stloc.s  6
0x1fdbc0  ldarg.0
0x1fdbc1  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdbc6  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportDefinition()
0x1fdbcb  stloc.s  7
0x1fdbcd  ldarg.0
0x1fdbce  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdbd3  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportObjectModel()
0x1fdbd8  stloc.s  8
0x1fdbda  ldc.i4.0
0x1fdbdb  stloc.s  9
0x1fdbdd  ldc.i4.0
0x1fdbde  stloc.s  0xA
0x1fdbe0  ldc.i4.0
0x1fdbe1  stloc.s  0xB
0x1fdbe3  ldarg.0
0x1fdbe4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_lastRIFObject
0x1fdbe9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath::get_InstancePath()
0x1fdbee  brfalse.s loc_1FDC06
0x1fdbf0  ldarg.0
0x1fdbf1  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_lastRIFObject
0x1fdbf6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath::get_InstancePath()
0x1fdbfb  stloc.s  5
0x1fdbfd  ldloc.s  5
0x1fdbff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem>::get_Count()
0x1fdc04  stloc.s  6
0x1fdc06  ldarg.1
0x1fdc07  ldc.i4.1
0x1fdc08  beq.s    loc_1FDC15
0x1fdc0a  ldarg.0
0x1fdc0b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdc10  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::EnsureCultureIsSetOnCurrentThread()
0x1fdc15  ldarg.1
0x1fdc16  ldc.i4.1
0x1fdc17  bne.un.s loc_1FDC3E
0x1fdc19  ldc.i4.1
0x1fdc1a  ldloc.s  7
0x1fdc1c  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_DataSetsNotOnlyUsedInParameters()
0x1fdc21  bne.un.s loc_1FDC3E
0x1fdc23  ldarg.0
0x1fdc24  ldloc.s  7
0x1fdc26  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_FirstDataSet()
0x1fdc2b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1fdc30  ldarg.s  4
0x1fdc32  call     instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::InScopeCompare(string scope1, string scope2)
0x1fdc37  brfalse.s loc_1FDC3E
0x1fdc39  leave    loc_1FE3E4
0x1fdc3e  ldc.i4.0
0x1fdc3f  stloc.s  0xC
0x1fdc41  ldarg.0
0x1fdc42  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdc47  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_InSubreport()
0x1fdc4c  brfalse.s loc_1FDC73
0x1fdc4e  ldarg.0
0x1fdc4f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_lastRIFObject
0x1fdc54  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath::get_InstancePath()
0x1fdc59  ldarg.0
0x1fdc5a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_lastRIFObject
0x1fdc5f  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath::get_InstancePathItem()
0x1fdc64  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItemType Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_Type()
0x1fdc69  ldc.i4.2
0x1fdc6a  ceq
0x1fdc6c  call     int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::GetParentReportIndex(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> instancePath, bool isSubreport)
0x1fdc71  stloc.s  0xC
0x1fdc73  ldloc.s  0xC
0x1fdc75  ldloc.s  4
0x1fdc77  ldloc.s  5
0x1fdc79  ldloc.s  8
0x1fdc7b  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_AllFieldsCleared()
0x1fdc80  ldloca.s 0xD
0x1fdc82  call     int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::GetSharedPathIndex(int32 startIndexForNewPath, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> oldPath, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem> newPath, bool returnPreviousIndex, [out] bool& identicalPaths)
0x1fdc87  stloc.s  0xE
0x1fdc89  ldarg.0
0x1fdc8a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_specialLastGroupingValues
0x1fdc8f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>>::get_Count()
0x1fdc94  stloc.s  0xF
0x1fdc96  br.s     loc_1FDCAA
0x1fdc98  ldarg.0
0x1fdc99  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_specialLastGroupingValues
0x1fdc9e  ldnull
0x1fdc9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>>::Add(var<u1>)
0x1fdca4  ldloc.s  0xF
0x1fdca6  ldc.i4.1
0x1fdca7  add
0x1fdca8  stloc.s  0xF
0x1fdcaa  ldloc.s  0xF
0x1fdcac  ldloc.s  0xC
0x1fdcae  blt.s    loc_1FDC98
0x1fdcb0  ldloc.s  0xC
0x1fdcb2  stloc.s  0x10
0x1fdcb4  br       loc_1FE2B5
0x1fdcb9  ldloc.s  5
0x1fdcbb  ldloc.s  0x10
0x1fdcbd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem>::get_Item(!!T0)
0x1fdcc2  stloc.s  0x11
0x1fdcc4  ldc.i4.0
0x1fdcc5  stloc.s  0x12
0x1fdcc7  ldarg.1
0x1fdcc8  ldc.i4.1
0x1fdcc9  beq.s    loc_1FDCD6
0x1fdccb  ldloc.s  0x10
0x1fdccd  ldloc.s  0xE
0x1fdccf  cgt
0x1fdcd1  ldc.i4.0
0x1fdcd2  ceq
0x1fdcd4  stloc.s  0x12
0x1fdcd6  ldloc.s  0x12
0x1fdcd8  brtrue.s loc_1FDD08
0x1fdcda  ldarg.1
0x1fdcdb  brtrue.s loc_1FDD08
0x1fdcdd  ldarg.0
0x1fdcde  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_specialLastGroupingValues
0x1fdce3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>>::get_Count()
0x1fdce8  ldloc.s  6
0x1fdcea  bge.s    loc_1FDCFA
0x1fdcec  ldarg.0
0x1fdced  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_specialLastGroupingValues
0x1fdcf2  ldnull
0x1fdcf3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>>::Add(var<u1>)
0x1fdcf8  br.s     loc_1FDD08
0x1fdcfa  ldarg.0
0x1fdcfb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>> Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_specialLastGroupingValues
0x1fdd00  ldloc.s  0x10
0x1fdd02  ldnull
0x1fdd03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportProcessing.PairObj`2<string, object>>::set_Item(int32, var<u1>)
0x1fdd08  ldloc.s  0x11
0x1fdd0a  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItemType Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_Type()
0x1fdd0f  stloc.s  0x14
0x1fdd11  ldloc.s  0x14
0x1fdd13  switch   loc_1FE2AF, loc_1FDDF0, loc_1FDD31, loc_1FDFB5, loc_1FDFB1
0x1fdd2c  br       loc_1FE026
0x1fdd31  ldloc.3
0x1fdd32  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_SubreportInstances()
0x1fdd37  brfalse  loc_1FE026
0x1fdd3c  ldloc.s  0x11
0x1fdd3e  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fdd43  ldloc.3
0x1fdd44  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_SubreportInstances()
0x1fdd49  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>>::get_Count()
0x1fdd4e  bge      loc_1FE026
0x1fdd53  ldloc.3
0x1fdd54  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_SubreportInstances()
0x1fdd59  ldloc.s  0x11
0x1fdd5b  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fdd60  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>>::get_Item(!!T0)
0x1fdd65  stloc.s  0x15
0x1fdd67  ldloc.s  0x15
0x1fdd69  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x1fdd6e  stloc.s  0x16
0x1fdd70  ldloc.s  0x15
0x1fdd72  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance>::Value()
0x1fdd77  stloc.s  0x17
0x1fdd79  ldloc.s  0x17
0x1fdd7b  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance::get_SubReportDef()
0x1fdd80  ldloc.s  0x15
0x1fdd82  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_CurrentSubReportInstance(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance> value)
0x1fdd87  ldarg.1
0x1fdd88  ldc.i4.1
0x1fdd89  beq.s    loc_1FDDC8
0x1fdd8b  ldloc.s  0x17
0x1fdd8d  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance::get_Initialized()
0x1fdd92  brtrue.s loc_1FDDC8
0x1fdd94  ldarg.0
0x1fdd95  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdd9a  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_IsTablixProcessingMode()
0x1fdd9f  brtrue.s loc_1FDDAE
0x1fdda1  ldarg.0
0x1fdda2  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::m_odpContext
0x1fdda7  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_IsTopLevelSubReportProcessing()
0x1fddac  brfalse.s loc_1FDDB3
0x1fddae  leave    loc_1FE3E4
0x1fddb3  ldloc.s  0x17
0x1fddb5  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInstance::get_SubReportDef()
0x1fddba  call     bool Microsoft.ReportingServices.OnDemandProcessing.SubReportInitializer::InitializeSubReport(class Microsoft.ReportingServices.ReportIntermediateFormat.SubReport subReport)
0x1fddbf  pop
0x1fddc0  ldloc.s  0x15
0x1fddc2  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x1fddc7  pop
0x1fddc8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1fddcd  ldloc.s  0x10
0x1fddcf  ldloc.s  6
0x1fddd1  ldc.i4.1
0x1fddd2  sub
0x1fddd3  ceq
0x1fddd5  ldstr    aSubreportNotLa// "SubReport not last in instance path."
0x1fddda  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1fdddf  leave    loc_1FE026
0x1fdde4  ldloc.s  0x16
0x1fdde6  brfalse.s loc_1FDDEF
0x1fdde8  ldloc.s  0x16
0x1fddea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fddef  endfinally
0x1fddf0  ldloc.3
0x1fddf1  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.ReportInstance
0x1fddf6  brfalse  loc_1FDEA6
0x1fddfb  ldloc.3
0x1fddfc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_DataRegionInstances()
0x1fde01  brfalse.s loc_1FDE44
0x1fde03  ldloc.3
0x1fde04  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_DataRegionInstances()
0x1fde09  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>>::get_Count()
0x1fde0e  ldloc.s  0x11
0x1fde10  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fde15  ble.s    loc_1FDE44
0x1fde17  ldloc.3
0x1fde18  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_DataRegionInstances()
0x1fde1d  ldloc.s  0x11
0x1fde1f  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fde24  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>>::get_Item(!!T0)
0x1fde29  brfalse.s loc_1FDE44
0x1fde2b  ldloc.3
0x1fde2c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_DataRegionInstances()
0x1fde31  ldloc.s  0x11
0x1fde33  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fde38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>>::get_Item(!!T0)
0x1fde3d  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>::Value()
0x1fde42  brtrue.s loc_1FDEA6
0x1fde44  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1fde49  ldloc.s  0x11
0x1fde4b  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fde50  ldloc.s  7
0x1fde52  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion> Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_TopLevelDataRegions()
0x1fde57  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion>::get_Count()
0x1fde5c  clt
0x1fde5e  ldstr    aNewitemIndexin// "(newItem.IndexInCollection < m_reportDe"...
0x1fde63  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1fde68  ldloc.s  7
0x1fde6a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion> Microsoft.ReportingServices.ReportIntermediateFormat.Report::get_TopLevelDataRegions()
0x1fde6f  ldloc.s  0x11
0x1fde71  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fde76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion>::get_Item(!!T0)
0x1fde7b  ldloc.s  7
0x1fde7d  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion::GetDataSet(class Microsoft.ReportingServices.ReportIntermediateFormat.Report reportDefinition)
0x1fde82  stloc.s  0x18
0x1fde84  ldarg.1
0x1fde85  ldc.i4.1
0x1fde86  bne.un.s loc_1FDE9E
0x1fde88  ldarg.0
0x1fde89  ldloc.s  0x18
0x1fde8b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1fde90  ldarg.s  4
0x1fde92  call     instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::InScopeCompare(string scope1, string scope2)
0x1fde97  brfalse.s loc_1FDE9E
0x1fde99  leave    loc_1FE3E4
0x1fde9e  ldarg.0
0x1fde9f  ldloc.s  0x18
0x1fdea1  call     instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::PerformOnDemandTablixProcessing(class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet dataSet)
0x1fdea6  ldloc.3
0x1fdea7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>> Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance::get_DataRegionInstances()
0x1fdeac  ldloc.s  0x11
0x1fdeae  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.InstancePathItem::get_IndexInCollection()
0x1fdeb3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>>::get_Item(!!T0)
0x1fdeb8  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance>::Value()
0x1fdebd  stloc.3
0x1fdebe  ldarg.0
0x1fdebf  ldc.i4.0
0x1fdec0  dup
0x1fdec1  stloc.s  9
0x1fdec3  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_inRecursiveColumnHierarchy
0x1fdec8  ldarg.0
0x1fdec9  ldc.i4.0
0x1fdeca  dup
0x1fdecb  stloc.s  0xA
0x1fdecd  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::m_inRecursiveRowHierarchy
0x1fded2  ldc.i4.m1
0x1fded3  stloc.2
0x1fded4  ldloc.3
0x1fded5  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance
0x1fdeda  stloc.0
0x1fdedb  ldloc.0
0x1fdedc  stloc.1
0x1fdedd  ldarg.1
0x1fdede  ldc.i4.1
0x1fdedf  bne.un.s loc_1FDEFB
0x1fdee1  ldarg.0
0x1fdee2  ldloc.0
0x1fdee3  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance::get_DataRegionDef()
0x1fdee8  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x1fdeed  ldarg.s  4
0x1fdeef  call     instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManagerFull::InScopeCompare(string scope1, string scope2)
0x1fdef4  brfalse.s loc_1FDEFB
0x1fdef6  leave    loc_1FE3E4
0x1fdefb  ldloc.0
0x1fdefc  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.DataRegionInstance::get_DataSetIndexInCollection()
  ... truncated ...
```
