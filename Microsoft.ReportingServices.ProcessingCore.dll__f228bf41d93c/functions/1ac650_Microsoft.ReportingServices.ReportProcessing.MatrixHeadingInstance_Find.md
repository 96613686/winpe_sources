# Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::Find

- ea: `0x1ac650`
- end: `0x1ac706`
- name: `Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::Find`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1900a0`

## callees

- `0x190790`
- `0x194180`
- `0x1941c0`
- `0x194bd0`
- `0x19e0f0`
- `0x1a0e20`
- `0x1a11f0`
- `0x1ac4a0`
- `0x1ac500`
- `0x1ac650`
- `0x1ac710`
- `0x1ac900`

## string_xrefs

- `0x1ac6a5`: `The instance of a computed report item cannot be null.`

## pseudocode

```c

```

## disassembly

```asm
0x1ac650  ldnull
0x1ac651  stloc.0
0x1ac652  ldarg.0
0x1ac653  call     instance bool Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::get_IsSubtotal()
0x1ac658  brfalse.s loc_1AC66D
0x1ac65a  ldarg.0
0x1ac65b  call     instance class Microsoft.ReportingServices.ReportProcessing.MatrixHeading Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::get_MatrixHeadingDef()
0x1ac660  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Subtotal Microsoft.ReportingServices.ReportProcessing.PivotHeading::get_Subtotal()
0x1ac665  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportItemCollection Microsoft.ReportingServices.ReportProcessing.Subtotal::get_ReportItems()
0x1ac66a  stloc.1
0x1ac66b  br.s     loc_1AC679
0x1ac66d  ldarg.0
0x1ac66e  call     instance class Microsoft.ReportingServices.ReportProcessing.MatrixHeading Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::get_MatrixHeadingDef()
0x1ac673  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportItemCollection Microsoft.ReportingServices.ReportProcessing.MatrixHeading::get_ReportItems()
0x1ac678  stloc.1
0x1ac679  ldloc.1
0x1ac67a  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ReportItemCollection::get_Count()
0x1ac67f  ldc.i4.0
0x1ac680  ble.s    loc_1AC6EC
0x1ac682  ldloc.1
0x1ac683  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ReportItemCollection::get_Count()
0x1ac688  ldc.i4.1
0x1ac689  bne.un.s loc_1AC68E
0x1ac68b  ldc.i4.0
0x1ac68c  starg.s  1
0x1ac68e  ldloc.1
0x1ac68f  ldarg.1
0x1ac690  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ReportItemCollection::IsReportItemComputed(int32 index)
0x1ac695  brfalse.s loc_1AC6C4
0x1ac697  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1ac69c  ldarg.0
0x1ac69d  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportItemInstance Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::m_content
0x1ac6a2  ldnull
0x1ac6a3  cgt.un
0x1ac6a5  ldstr    aTheInstanceOfA// "The instance of a computed report item "...
0x1ac6aa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1ac6af  ldarg.0
0x1ac6b0  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportItemInstance Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::m_content
0x1ac6b5  ldarg.2
0x1ac6b6  ldarg.3
0x1ac6b7  ldarg.s  4
0x1ac6b9  callvirt instance object Microsoft.ReportingServices.ReportProcessing.ISearchByUniqueName::Find(int32 targetUniqueName, class Microsoft.ReportingServices.ReportProcessing.NonComputedUniqueNames& nonCompNames, class RenderingChunkManager chunkManager)
0x1ac6be  stloc.0
0x1ac6bf  ldloc.0
0x1ac6c0  brfalse.s loc_1AC6EC
0x1ac6c2  ldloc.0
0x1ac6c3  ret
0x1ac6c4  ldarg.0
0x1ac6c5  ldarg.s  4
0x1ac6c7  call     instance class Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstanceInfo Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::GetInstanceInfo(class RenderingChunkManager chunkManager)
0x1ac6cc  callvirt instance class Microsoft.ReportingServices.ReportProcessing.NonComputedUniqueNames Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstanceInfo::get_ContentUniqueNames()
0x1ac6d1  stloc.2
0x1ac6d2  ldloc.1
0x1ac6d3  ldarg.1
0x1ac6d4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportItem Microsoft.ReportingServices.ReportProcessing.ReportItemCollection::get_Item(int32 index)
0x1ac6d9  ldarg.2
0x1ac6da  ldloca.s 2
0x1ac6dc  ldarg.s  4
0x1ac6de  callvirt instance object Microsoft.ReportingServices.ReportProcessing.ISearchByUniqueName::Find(int32 targetUniqueName, class Microsoft.ReportingServices.ReportProcessing.NonComputedUniqueNames& nonCompNames, class RenderingChunkManager chunkManager)
0x1ac6e3  stloc.0
0x1ac6e4  ldloc.0
0x1ac6e5  brfalse.s loc_1AC6EC
0x1ac6e7  ldarg.3
0x1ac6e8  ldloc.2
0x1ac6e9  stind.ref
0x1ac6ea  ldloc.0
0x1ac6eb  ret
0x1ac6ec  ldarg.0
0x1ac6ed  ldfld    class Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstanceList Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::m_subHeadingInstances
0x1ac6f2  brfalse.s loc_1AC704
0x1ac6f4  ldarg.0
0x1ac6f5  ldfld    class Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstanceList Microsoft.ReportingServices.ReportProcessing.MatrixHeadingInstance::m_subHeadingInstances
0x1ac6fa  ldarg.2
0x1ac6fb  ldarg.3
0x1ac6fc  ldarg.s  4
0x1ac6fe  callvirt instance object Microsoft.ReportingServices.ReportProcessing.ISearchByUniqueName::Find(int32 targetUniqueName, class Microsoft.ReportingServices.ReportProcessing.NonComputedUniqueNames& nonCompNames, class RenderingChunkManager chunkManager)
0x1ac703  ret
0x1ac704  ldnull
0x1ac705  ret
```
