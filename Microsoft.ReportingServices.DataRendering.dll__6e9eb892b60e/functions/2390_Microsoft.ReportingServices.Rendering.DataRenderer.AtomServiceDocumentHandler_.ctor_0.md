# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::.ctor_0

- ea: `0x2390`
- end: `0x23d3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::.ctor_0`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2380`
- `0x29d0`

## callees

- `0x5720`
- `0xb770`

## pseudocode

```c

```

## disassembly

```asm
0x2390  ldarg.0
0x2391  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::.ctor()
0x2396  ldarg.0
0x2397  ldarg.1
0x2398  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_visitor
0x239d  ldarg.0
0x239e  call     class DynamicElement DynamicElement::CreateRoot()
0x23a3  stfld    class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementRoot
0x23a8  ldarg.0
0x23a9  newobj   instance void class [System]System.Collections.Generic.Stack`1<class DynamicElement>::.ctor()
0x23ae  stfld    class [System]System.Collections.Generic.Stack`1<class DynamicElement> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementScope
0x23b3  ldarg.0
0x23b4  ldfld    class [System]System.Collections.Generic.Stack`1<class DynamicElement> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementScope
0x23b9  ldarg.0
0x23ba  ldfld    class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementRoot
0x23bf  callvirt instance void class [System]System.Collections.Generic.Stack`1<class DynamicElement>::Push(var<u1>)
0x23c4  ldarg.0
0x23c5  ldarg.2
0x23c6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x23cb  ldarg.0
0x23cc  ldc.i4.0
0x23cd  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_multipleFeeds
0x23d2  ret
```
