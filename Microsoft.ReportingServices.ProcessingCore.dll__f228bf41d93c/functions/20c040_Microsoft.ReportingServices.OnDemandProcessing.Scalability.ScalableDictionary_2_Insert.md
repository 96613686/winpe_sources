# Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2::Insert

- ea: `0x20c040`
- end: `0x20c33f`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2::Insert`
- size: `767`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x149070`
- `0x206120`
- `0x2071a0`
- `0x2071f0`
- `0x20c040`
- `0x20c9d0`
- `0x20cc20`
- `0x20cc50`
- `0x20cc60`
- `0x20cc70`
- `0x20cc80`
- `0x20cc90`
- `0x20ce40`

## string_xrefs

- `0x20c176`: `ScalableDictionary: An element with the same key already exists within the Dictionary`

## pseudocode

```c

```

## disassembly

```asm
0x20c040  ldarg.1
0x20c041  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::PinValue()
0x20c046  stloc.0
0x20c047  ldarg.1
0x20c048  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNode Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference::Value()
0x20c04d  stloc.1
0x20c04e  ldc.i4.0
0x20c04f  stloc.2
0x20c050  ldarg.0
0x20c051  ldloc.1
0x20c052  ldarg.2
0x20c053  ldarg.s  6
0x20c055  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::HashToSlot(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNode, int32, int32)
0x20c05a  stloc.3
0x20c05b  ldloc.1
0x20c05c  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalableDictionaryEntry[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNode::Entries
0x20c061  ldloc.3
0x20c062  ldelem.ref
0x20c063  stloc.s  4
0x20c065  ldloc.s  4
0x20c067  brtrue   loc_20C0FB
0x20c06c  ldarg.0
0x20c06d  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_valuesCapacity
0x20c072  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::.ctor(int32 capacity)
0x20c077  stloc.s  5
0x20c079  ldloc.s  5
0x20c07b  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Keys()
0x20c080  ldc.i4.0
0x20c081  ldarg.3
0x20c082  box      var<u1>
0x20c087  stelem.ref
0x20c088  ldloc.s  5
0x20c08a  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Values()
0x20c08f  ldc.i4.0
0x20c090  ldarg.s  4
0x20c092  box      var<u1>
0x20c097  stelem.ref
0x20c098  ldloc.s  5
0x20c09a  dup
0x20c09b  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c0a0  stloc.s  6
0x20c0a2  ldloc.s  6
0x20c0a4  ldc.i4.1
0x20c0a5  add
0x20c0a6  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::set_Count(int32 value)
0x20c0ab  ldloc.1
0x20c0ac  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalableDictionaryEntry[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNode::Entries
0x20c0b1  ldloc.3
0x20c0b2  ldloc.s  5
0x20c0b4  stelem.ref
0x20c0b5  ldc.i4.1
0x20c0b6  stloc.2
0x20c0b7  ldarg.s  8
0x20c0b9  ldloc.0
0x20c0ba  stind.ref
0x20c0bb  ldarg.0
0x20c0bc  ldfld    bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_useFixedReferences
0x20c0c1  ldc.i4.0
0x20c0c2  ceq
0x20c0c4  ldarg.s  7
0x20c0c6  and
0x20c0c7  brfalse  loc_20C320
0x20c0cc  ldarg.3
0x20c0cd  box      var<u1>
0x20c0d2  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOfInObjectArray(object obj)
0x20c0d7  ldarg.s  4
0x20c0d9  box      var<u1>
0x20c0de  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOfInObjectArray(object obj)
0x20c0e3  add
0x20c0e4  ldloc.s  5
0x20c0e6  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_EmptySize()
0x20c0eb  add
0x20c0ec  stloc.s  7
0x20c0ee  ldarg.1
0x20c0ef  ldloc.s  7
0x20c0f1  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::UpdateSize(int32 sizeBytesDelta)
0x20c0f6  br       loc_20C320
0x20c0fb  ldloc.s  4
0x20c0fd  callvirt instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable::GetObjectType()
0x20c102  stloc.s  0xB
0x20c104  ldloc.s  0xB
0x20c106  ldc.i4.s 0x17
0x20c108  beq.s    loc_20C115
0x20c10a  ldloc.s  0xB
0x20c10c  ldc.i4.s 0x19
0x20c10e  beq.s    loc_20C13A
0x20c110  br       loc_20C30C
0x20c115  ldloc.s  4
0x20c117  isinst   Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference
0x20c11c  stloc.s  8
0x20c11e  ldarg.0
0x20c11f  ldloc.s  8
0x20c121  ldarg.2
0x20c122  ldarg.3
0x20c123  ldarg.s  4
0x20c125  ldarg.s  5
0x20c127  ldarg.s  6
0x20c129  ldc.i4.1
0x20c12a  add
0x20c12b  ldarg.s  7
0x20c12d  ldarg.s  8
0x20c12f  call     instance bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::Insert(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference, int32, var<u1>, !!T0, var<u1>, void, bool, int32)
0x20c134  stloc.2
0x20c135  br       loc_20C320
0x20c13a  ldloc.s  4
0x20c13c  isinst   Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues
0x20c141  stloc.s  9
0x20c143  ldc.i4.0
0x20c144  stloc.s  0xA
0x20c146  ldarg.s  8
0x20c148  ldnull
0x20c149  stind.ref
0x20c14a  ldc.i4.0
0x20c14b  stloc.s  0xC
0x20c14d  br.s     loc_20C1A2
0x20c14f  ldarg.0
0x20c150  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_comparer
0x20c155  ldarg.3
0x20c156  ldloc.s  9
0x20c158  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Keys()
0x20c15d  ldloc.s  0xC
0x20c15f  ldelem.ref
0x20c160  unbox.any var<u1>
0x20c165  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x20c16a  brfalse.s loc_20C19C
0x20c16c  ldarg.s  5
0x20c16e  brfalse.s loc_20C180
0x20c170  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20c175  ldc.i4.0
0x20c176  ldstr    aScalabledictio_4// "ScalableDictionary: An element with the"...
0x20c17b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20c180  ldloc.s  9
0x20c182  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Values()
0x20c187  ldloc.s  0xC
0x20c189  ldarg.s  4
0x20c18b  box      var<u1>
0x20c190  stelem.ref
0x20c191  ldc.i4.1
0x20c192  stloc.s  0xA
0x20c194  ldc.i4.0
0x20c195  stloc.2
0x20c196  ldarg.s  8
0x20c198  ldloc.0
0x20c199  stind.ref
0x20c19a  br.s     loc_20C1AD
0x20c19c  ldloc.s  0xC
0x20c19e  ldc.i4.1
0x20c19f  add
0x20c1a0  stloc.s  0xC
0x20c1a2  ldloc.s  0xC
0x20c1a4  ldloc.s  9
0x20c1a6  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c1ab  blt.s    loc_20C14F
0x20c1ad  ldloc.s  0xA
0x20c1af  brtrue   loc_20C320
0x20c1b4  ldloc.s  9
0x20c1b6  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c1bb  ldloc.s  9
0x20c1bd  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Capacity()
0x20c1c2  bge.s    loc_20C240
0x20c1c4  ldloc.s  9
0x20c1c6  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c1cb  stloc.s  0xD
0x20c1cd  ldloc.s  9
0x20c1cf  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Keys()
0x20c1d4  ldloc.s  0xD
0x20c1d6  ldarg.3
0x20c1d7  box      var<u1>
0x20c1dc  stelem.ref
0x20c1dd  ldloc.s  9
0x20c1df  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Values()
0x20c1e4  ldloc.s  0xD
0x20c1e6  ldarg.s  4
0x20c1e8  box      var<u1>
0x20c1ed  stelem.ref
0x20c1ee  ldloc.s  9
0x20c1f0  dup
0x20c1f1  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c1f6  stloc.s  6
0x20c1f8  ldloc.s  6
0x20c1fa  ldc.i4.1
0x20c1fb  add
0x20c1fc  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::set_Count(int32 value)
0x20c201  ldc.i4.1
0x20c202  stloc.2
0x20c203  ldarg.s  8
0x20c205  ldloc.0
0x20c206  stind.ref
0x20c207  ldarg.0
0x20c208  ldfld    bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_useFixedReferences
0x20c20d  ldc.i4.0
0x20c20e  ceq
0x20c210  ldarg.s  7
0x20c212  and
0x20c213  brfalse  loc_20C320
0x20c218  ldarg.1
0x20c219  ldarg.3
0x20c21a  box      var<u1>
0x20c21f  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOfInObjectArray(object obj)
0x20c224  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::UpdateSize(int32 sizeBytesDelta)
0x20c229  ldarg.1
0x20c22a  ldarg.s  4
0x20c22c  box      var<u1>
0x20c231  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOfInObjectArray(object obj)
0x20c236  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::UpdateSize(int32 sizeBytesDelta)
0x20c23b  br       loc_20C320
0x20c240  ldarg.0
0x20c241  ldarg.s  6
0x20c243  ldc.i4.1
0x20c244  add
0x20c245  ldarg.0
0x20c246  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_nodeCapacity
0x20c24b  call     instance class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::BuildNode(int32, int32)
0x20c250  stloc.s  0xE
0x20c252  ldloc.1
0x20c253  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalableDictionaryEntry[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNode::Entries
0x20c258  ldloc.3
0x20c259  ldloc.s  0xE
0x20c25b  stelem.ref
0x20c25c  ldloc.s  0xE
0x20c25e  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::PinValue()
0x20c263  stloc.s  0xF
0x20c265  ldarg.0
0x20c266  ldfld    bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::m_useFixedReferences
0x20c26b  ldc.i4.0
0x20c26c  ceq
0x20c26e  ldarg.s  7
0x20c270  and
0x20c271  brfalse.s loc_20C28F
0x20c273  ldloc.s  9
0x20c275  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOfInObjectArray(object obj)
0x20c27a  stloc.s  0x10
0x20c27c  ldarg.1
0x20c27d  ldloc.s  0x10
0x20c27f  ldc.i4.m1
0x20c280  mul
0x20c281  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::UpdateSize(int32 sizeBytesDelta)
0x20c286  ldloc.s  0xE
0x20c288  ldloc.s  0x10
0x20c28a  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::UpdateSize(int32 sizeBytesDelta)
0x20c28f  ldc.i4.0
0x20c290  stloc.s  0x11
0x20c292  br.s     loc_20C2DC
0x20c294  ldloc.s  9
0x20c296  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Keys()
0x20c29b  ldloc.s  0x11
0x20c29d  ldelem.ref
0x20c29e  unbox.any var<u1>
0x20c2a3  stloc.s  0x12
0x20c2a5  ldarg.0
0x20c2a6  ldloc.s  0xE
0x20c2a8  ldarg.0
0x20c2a9  ldloc.s  0x12
0x20c2ab  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::GetHashCode(var<u1>)
0x20c2b0  ldloc.s  0x12
0x20c2b2  ldloc.s  9
0x20c2b4  callvirt instance object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Values()
0x20c2b9  ldloc.s  0x11
0x20c2bb  ldelem.ref
0x20c2bc  unbox.any var<u1>
0x20c2c1  ldc.i4.0
0x20c2c2  ldarg.s  6
0x20c2c4  ldc.i4.1
0x20c2c5  add
0x20c2c6  ldc.i4.0
0x20c2c7  ldloca.s 0x13
0x20c2c9  call     instance bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::Insert(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference, int32, var<u1>, !!T0, var<u1>, void, bool, int32)
0x20c2ce  pop
0x20c2cf  ldloc.s  0x13
0x20c2d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20c2d6  ldloc.s  0x11
0x20c2d8  ldc.i4.1
0x20c2d9  add
0x20c2da  stloc.s  0x11
0x20c2dc  ldloc.s  0x11
0x20c2de  ldloc.s  9
0x20c2e0  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryValues::get_Count()
0x20c2e5  blt.s    loc_20C294
0x20c2e7  ldarg.0
0x20c2e8  ldloc.s  0xE
0x20c2ea  ldarg.2
0x20c2eb  ldarg.3
0x20c2ec  ldarg.s  4
0x20c2ee  ldarg.s  5
0x20c2f0  ldarg.s  6
0x20c2f2  ldc.i4.1
0x20c2f3  add
0x20c2f4  ldarg.s  7
0x20c2f6  ldarg.s  8
0x20c2f8  call     instance bool class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::Insert(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionaryNodeReference, int32, var<u1>, !!T0, var<u1>, void, bool, int32)
0x20c2fd  stloc.2
0x20c2fe  leave.s  loc_20C320
0x20c300  ldloc.s  0xF
0x20c302  brfalse.s loc_20C30B
0x20c304  ldloc.s  0xF
0x20c306  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20c30b  endfinally
0x20c30c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20c311  ldc.i4.0
0x20c312  ldstr    aUnknownObjectt_0// "Unknown ObjectType"
  ... truncated ...
```
