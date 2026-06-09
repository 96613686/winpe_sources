# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::WriteDataRegionFeed

- ea: `0x39d0`
- end: `0x3abb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::WriteDataRegionFeed`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x39d0`
- `0x3ac0`

## pseudocode

```c

```

## disassembly

```asm
0x39d0  ldnull
0x39d1  stloc.0
0x39d2  ldarg.0
0x39d3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::.ctor()
0x39d8  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_currentTypeCodes
0x39dd  ldarg.0
0x39de  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x39e3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem> [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::get_Items()
0x39e8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem>::GetEnumerator()
0x39ed  stloc.1
0x39ee  br.s     loc_3A4E
0x39f0  ldloc.0
0x39f1  brtrue.s loc_3A01
0x39f3  ldarg.0
0x39f4  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_currentTypeCodes
0x39f9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x39fe  stloc.0
0x39ff  br.s     loc_3A4E
0x3a01  ldc.i4.0
0x3a02  stloc.2
0x3a03  br.s     loc_3A40
0x3a05  ldarg.0
0x3a06  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_currentTypeCodes
0x3a0b  ldloc.2
0x3a0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::get_Item(!!T0)
0x3a11  stloc.3
0x3a12  ldloc.3
0x3a13  brfalse.s loc_3A3C
0x3a15  ldloc.0
0x3a16  ldloc.2
0x3a17  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::get_Item(!!T0)
0x3a1c  brtrue.s loc_3A28
0x3a1e  ldloc.0
0x3a1f  ldloc.2
0x3a20  ldloc.3
0x3a21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::set_Item(int32, var<u1>)
0x3a26  br.s     loc_3A3C
0x3a28  ldloc.0
0x3a29  ldloc.2
0x3a2a  ldloc.0
0x3a2b  ldloc.2
0x3a2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::get_Item(!!T0)
0x3a31  ldloc.3
0x3a32  call     valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::ResolveTypeCode(valuetype [mscorlib]System.TypeCode typeCodeA, valuetype [mscorlib]System.TypeCode typeCodeB)
0x3a37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::set_Item(int32, var<u1>)
0x3a3c  ldloc.2
0x3a3d  ldc.i4.1
0x3a3e  add
0x3a3f  stloc.2
0x3a40  ldloc.2
0x3a41  ldarg.0
0x3a42  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_currentTypeCodes
0x3a47  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::get_Count()
0x3a4c  blt.s    loc_3A05
0x3a4e  ldloc.1
0x3a4f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3a54  brtrue.s loc_39F0
0x3a56  ldarg.0
0x3a57  ldnull
0x3a58  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_columnEdmTypes
0x3a5d  ldloc.0
0x3a5e  brfalse.s loc_3ABA
0x3a60  ldarg.0
0x3a61  ldloc.0
0x3a62  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::get_Count()
0x3a67  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x3a6c  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_columnEdmTypes
0x3a71  ldloc.0
0x3a72  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TypeCode>::GetEnumerator()
0x3a77  stloc.s  4
0x3a79  br.s     loc_3AA1
0x3a7b  ldloca.s 4
0x3a7d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.TypeCode>::get_Current()
0x3a82  stloc.s  5
0x3a84  ldarg.0
0x3a85  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x3a8a  ldloc.s  5
0x3a8c  ldloca.s 6
0x3a8e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::TryGetValue(var<u1>, !!T0)
0x3a93  pop
0x3a94  ldarg.0
0x3a95  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::m_columnEdmTypes
0x3a9a  ldloc.s  6
0x3a9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3aa1  ldloca.s 4
0x3aa3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.TypeCode>::MoveNext()
0x3aa8  brtrue.s loc_3A7B
0x3aaa  leave.s  loc_3ABA
0x3aac  ldloca.s 4
0x3aae  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.TypeCode>
0x3ab4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ab9  endfinally
0x3aba  ret
```
