# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats

- ea: `0x790`
- end: `0x7fa`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_RenderFormats`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x460`
- `0xa30`

## callees

- `0x670`
- `0x790`

## pseudocode

```c

```

## disassembly

```asm
0x790  ldarg.0
0x791  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_allRenderers
0x796  brtrue.s loc_7F3
0x798  ldarg.0
0x799  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x79e  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_allRenderers
0x7a3  ldarg.0
0x7a4  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ReportServerInformation()
0x7a9  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation::get_RenderingExtension()
0x7ae  stloc.0
0x7af  ldc.i4.0
0x7b0  stloc.1
0x7b1  br.s     loc_7ED
0x7b3  ldloc.0
0x7b4  ldloc.1
0x7b5  ldelem.ref
0x7b6  stloc.2
0x7b7  ldarg.0
0x7b8  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_excludedRenderFormats
0x7bd  ldloc.2
0x7be  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_Name()
0x7c3  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x7c8  brtrue.s loc_7E9
0x7ca  ldloc.2
0x7cb  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_Visible()
0x7d0  brfalse.s loc_7E9
0x7d2  ldarg.0
0x7d3  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_allRenderers
0x7d8  ldloc.2
0x7d9  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_Name()
0x7de  ldloc.2
0x7df  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Extension::get_LocalizedName()
0x7e4  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x7e9  ldloc.1
0x7ea  ldc.i4.1
0x7eb  add
0x7ec  stloc.1
0x7ed  ldloc.1
0x7ee  ldloc.0
0x7ef  ldlen
0x7f0  conv.i4
0x7f1  blt.s    loc_7B3
0x7f3  ldarg.0
0x7f4  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_allRenderers
0x7f9  ret
```
