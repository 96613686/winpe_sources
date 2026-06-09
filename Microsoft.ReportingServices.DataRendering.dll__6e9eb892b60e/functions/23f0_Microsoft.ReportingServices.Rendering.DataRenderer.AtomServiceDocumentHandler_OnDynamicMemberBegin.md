# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin

- ea: `0x23f0`
- end: `0x242b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnDynamicMemberBegin`
- size: `59`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2430`
- `0x2480`
- `0x24f0`
- `0x2540`
- `0x25b0`
- `0x2600`
- `0x2650`
- `0x2aa0`
- `0x2af0`

## callees

- `0x23f0`
- `0xb6d0`
- `0xb700`

## pseudocode

```c

```

## disassembly

```asm
0x23f0  ldarg.1
0x23f1  ldarg.2
0x23f2  ldarg.3
0x23f3  newobj   instance void DynamicElement::.ctor(string definitionPath, string dataElementName, string reportItemName)
0x23f8  stloc.0
0x23f9  ldarg.0
0x23fa  ldfld    class [System]System.Collections.Generic.Stack`1<class DynamicElement> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementScope
0x23ff  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class DynamicElement>::Peek()
0x2404  dup
0x2405  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x240a  ldloc.0
0x240b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::Add(var<u1>)
0x2410  callvirt instance bool DynamicElement::IsBranch()
0x2415  brfalse.s loc_241E
0x2417  ldarg.0
0x2418  ldc.i4.1
0x2419  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_multipleFeeds
0x241e  ldarg.0
0x241f  ldfld    class [System]System.Collections.Generic.Stack`1<class DynamicElement> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementScope
0x2424  ldloc.0
0x2425  callvirt instance void class [System]System.Collections.Generic.Stack`1<class DynamicElement>::Push(var<u1>)
0x242a  ret
```
