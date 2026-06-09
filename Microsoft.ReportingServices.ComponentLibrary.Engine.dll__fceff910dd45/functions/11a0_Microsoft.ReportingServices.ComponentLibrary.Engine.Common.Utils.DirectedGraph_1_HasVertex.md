# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::HasVertex

- ea: `0x11a0`
- end: `0x11ad`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::HasVertex`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x11a0  ldarg.0
0x11a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x11a6  ldarg.1
0x11a7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::ContainsKey(var<u1>)
0x11ac  ret
```
