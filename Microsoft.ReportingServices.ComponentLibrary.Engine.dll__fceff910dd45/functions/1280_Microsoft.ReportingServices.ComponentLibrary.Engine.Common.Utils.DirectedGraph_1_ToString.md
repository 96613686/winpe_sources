# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::ToString

- ea: `0x1280`
- end: `0x1411`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::ToString`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1280`

## pseudocode

```c

```

## disassembly

```asm
0x1280  ldarg.0
0x1281  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1286  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x128b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1290  stloc.0
0x1291  ldloc.0
0x1292  ldstr    asc_34C8// ", "
0x1297  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x129c  pop
0x129d  ldloc.0
0x129e  ldstr    aVertexcount// "VertexCount="
0x12a3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12a8  pop
0x12a9  ldloc.0
0x12aa  ldarg.0
0x12ab  call     instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::get_VertexCount()
0x12b0  stloc.1
0x12b1  ldloca.s 1
0x12b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12b8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12c2  pop
0x12c3  ldarg.0
0x12c4  call     instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::get_Vertices()
0x12c9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<var<u1>>::GetEnumerator()
0x12ce  stloc.2
0x12cf  br       loc_13EE
0x12d4  ldloca.s 2
0x12d6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::get_Current()
0x12db  stloc.3
0x12dc  ldloc.0
0x12dd  ldstr    asc_34E8// "\n {"
0x12e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e7  pop
0x12e8  ldloc.0
0x12e9  ldarg.0
0x12ea  ldloc.3
0x12eb  callvirt instance string class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::VertexToString(var<u1>)
0x12f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12f5  pop
0x12f6  ldloc.0
0x12f7  ldstr    asc_34F0// " -> "
0x12fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1301  pop
0x1302  ldloca.s 4
0x1304  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>
0x130a  ldarg.0
0x130b  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::get_Edges()
0x1310  ldloc.3
0x1311  ldloca.s 4
0x1313  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::TryGetValue(var<u1>, !!T0)
0x1318  brfalse  loc_13D6
0x131d  ldloca.s 4
0x131f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_HasValue()
0x1324  brtrue.s loc_1337
0x1326  ldloc.0
0x1327  ldstr    aNotProbedYet// "-not probed yet-"
0x132c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1331  pop
0x1332  br       loc_13E2
0x1337  ldloca.s 4
0x1339  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x133e  stloc.s  5
0x1340  ldloca.s 5
0x1342  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x1347  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::get_Count()
0x134c  ldc.i4.0
0x134d  ble.s    loc_13C8
0x134f  ldloc.0
0x1350  ldarg.0
0x1351  ldloca.s 4
0x1353  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x1358  stloc.s  5
0x135a  ldloca.s 5
0x135c  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x1361  ldc.i4.0
0x1362  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::get_Item(!!T0)
0x1367  callvirt instance string class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::VertexToString(var<u1>)
0x136c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1371  pop
0x1372  ldc.i4.1
0x1373  stloc.s  6
0x1375  br.s     loc_13AD
0x1377  ldloc.0
0x1378  ldstr    asc_34C8// ", "
0x137d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1382  pop
0x1383  ldloc.0
0x1384  ldarg.0
0x1385  ldloca.s 4
0x1387  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x138c  stloc.s  5
0x138e  ldloca.s 5
0x1390  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x1395  ldloc.s  6
0x1397  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::get_Item(!!T0)
0x139c  callvirt instance string class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::VertexToString(var<u1>)
0x13a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13a6  pop
0x13a7  ldloc.s  6
0x13a9  ldc.i4.1
0x13aa  add
0x13ab  stloc.s  6
0x13ad  ldloc.s  6
0x13af  ldloca.s 4
0x13b1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x13b6  stloc.s  5
0x13b8  ldloca.s 5
0x13ba  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x13bf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::get_Count()
0x13c4  blt.s    loc_1377
0x13c6  br.s     loc_13E2
0x13c8  ldloc.0
0x13c9  ldstr    aNone// "-none-"
0x13ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13d3  pop
0x13d4  br.s     loc_13E2
0x13d6  ldloc.0
0x13d7  ldstr    aVertexNotFound// "-vertex not found in edge map, inconsis"...
0x13dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13e1  pop
0x13e2  ldloc.0
0x13e3  ldstr    asc_3590// "}"
0x13e8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13ed  pop
0x13ee  ldloca.s 2
0x13f0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::MoveNext()
0x13f5  brtrue   loc_12D4
0x13fa  leave.s  loc_140A
0x13fc  ldloca.s 2
0x13fe  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>
0x1404  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1409  endfinally
0x140a  ldloc.0
0x140b  callvirt instance string [mscorlib]System.Object::ToString()
0x1410  ret
```
