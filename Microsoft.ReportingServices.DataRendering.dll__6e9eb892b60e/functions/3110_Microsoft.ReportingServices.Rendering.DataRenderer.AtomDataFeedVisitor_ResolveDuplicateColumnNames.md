# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResolveDuplicateColumnNames

- ea: `0x3110`
- end: `0x31e2`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResolveDuplicateColumnNames`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30b0`

## callees

- `0x3110`

## pseudocode

```c

```

## disassembly

```asm
0x3110  ldarg.0
0x3111  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3116  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x311b  stloc.0
0x311c  ldc.i4.1
0x311d  stloc.1
0x311e  br       loc_31A9
0x3123  ldarg.0
0x3124  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x3129  ldloc.1
0x312a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x312f  stloc.2
0x3130  ldloc.0
0x3131  ldloc.2
0x3132  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3137  brtrue.s loc_3147
0x3139  ldarg.0
0x313a  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x313f  ldloc.2
0x3140  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3145  brfalse.s loc_3191
0x3147  ldc.i4.1
0x3148  stloc.3
0x3149  ldloc.2
0x314a  ldstr    asc_EEAC// "_"
0x314f  ldloca.s 3
0x3151  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3156  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x315b  call     string [mscorlib]System.String::Concat(string, string, string)
0x3160  stloc.s  4
0x3162  ldloc.3
0x3163  ldc.i4.1
0x3164  add
0x3165  stloc.3
0x3166  ldloc.0
0x3167  ldloc.s  4
0x3169  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x316e  brtrue.s loc_3149
0x3170  ldarg.0
0x3171  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x3176  ldloc.s  4
0x3178  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsValue(var<u1>)
0x317d  brtrue.s loc_3149
0x317f  ldarg.0
0x3180  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x3185  ldloc.s  4
0x3187  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x318c  brtrue.s loc_3149
0x318e  ldloc.s  4
0x3190  stloc.2
0x3191  ldloc.0
0x3192  ldloc.2
0x3193  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3198  ldarg.0
0x3199  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x319e  ldloc.1
0x319f  ldnull
0x31a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::set_Item(var<u1>, !!T0)
0x31a5  ldloc.1
0x31a6  ldc.i4.1
0x31a7  add
0x31a8  stloc.1
0x31a9  ldloc.1
0x31aa  ldarg.0
0x31ab  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x31b0  ble      loc_3123
0x31b5  ldc.i4.1
0x31b6  stloc.s  5
0x31b8  br.s     loc_31D7
0x31ba  ldarg.0
0x31bb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x31c0  ldloc.s  5
0x31c2  ldloc.0
0x31c3  ldloc.s  5
0x31c5  ldc.i4.1
0x31c6  sub
0x31c7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x31cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::set_Item(var<u1>, !!T0)
0x31d1  ldloc.s  5
0x31d3  ldc.i4.1
0x31d4  add
0x31d5  stloc.s  5
0x31d7  ldloc.s  5
0x31d9  ldarg.0
0x31da  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x31df  ble.s    loc_31BA
0x31e1  ret
```
