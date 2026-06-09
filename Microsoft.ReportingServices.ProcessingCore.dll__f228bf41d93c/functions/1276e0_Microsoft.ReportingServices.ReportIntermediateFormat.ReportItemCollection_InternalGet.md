# Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::InternalGet

- ea: `0x1276e0`
- end: `0x12772d`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::InternalGet`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x127630`
- `0x127670`

## callees

- `0x1276e0`

## string_xrefs

- `0x1276ee`: `(null != m_computedReportItems)`
- `0x127706`: `(null != m_nonComputedReportItems)`

## pseudocode

```c

```

## disassembly

```asm
0x1276e0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1276e5  ldarg.0
0x1276e6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem> Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::m_computedReportItems
0x1276eb  ldnull
0x1276ec  cgt.un
0x1276ee  ldstr    aNullMComputedr// "(null != m_computedReportItems)"
0x1276f3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1276f8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1276fd  ldarg.0
0x1276fe  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem> Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::m_nonComputedReportItems
0x127703  ldnull
0x127704  cgt.un
0x127706  ldstr    aNullMNoncomput// "(null != m_nonComputedReportItems)"
0x12770b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x127710  ldarg.2
0x127711  brfalse.s loc_127720
0x127713  ldarg.0
0x127714  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem> Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::m_computedReportItems
0x127719  ldarg.1
0x12771a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem>::get_Item(!!T0)
0x12771f  ret
0x127720  ldarg.0
0x127721  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem> Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection::m_nonComputedReportItems
0x127726  ldarg.1
0x127727  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem>::get_Item(!!T0)
0x12772c  ret
```
