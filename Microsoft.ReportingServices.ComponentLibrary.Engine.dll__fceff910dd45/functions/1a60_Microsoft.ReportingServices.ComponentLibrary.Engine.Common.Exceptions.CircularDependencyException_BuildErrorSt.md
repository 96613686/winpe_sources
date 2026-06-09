# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::BuildErrorString

- ea: `0x1a60`
- end: `0x1b20`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::BuildErrorString`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a20`

## callees

- `0xc10`
- `0xd10`
- `0xd30`
- `0xd40`
- `0x1a60`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldarg.0
0x1a61  brfalse  loc_1B1A
0x1a66  ldarg.0
0x1a67  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::get_Count()
0x1a6c  ldc.i4.1
0x1a6d  ble      loc_1B1A
0x1a72  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1a77  stloc.0
0x1a78  ldarg.0
0x1a79  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::GetEnumerator()
0x1a7e  stloc.1
0x1a7f  br.s     loc_1A94
0x1a81  ldloc.1
0x1a82  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::get_Current()
0x1a87  stloc.2
0x1a88  ldloc.0
0x1a89  ldloc.2
0x1a8a  callvirt instance string Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Name()
0x1a8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a94  ldloc.1
0x1a95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a9a  brtrue.s loc_1A81
0x1a9c  leave.s  loc_1AA8
0x1a9e  ldloc.1
0x1a9f  brfalse.s loc_1AA7
0x1aa1  ldloc.1
0x1aa2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1aa7  endfinally
0x1aa8  ldloc.0
0x1aa9  ldc.i4.0
0x1aaa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1aaf  ldloc.0
0x1ab0  ldloc.0
0x1ab1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1ab6  ldc.i4.1
0x1ab7  sub
0x1ab8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1abd  ldc.i4.4
0x1abe  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1ac3  brfalse.s loc_1AD3
0x1ac5  ldloc.0
0x1ac6  ldloc.0
0x1ac7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1acc  ldc.i4.1
0x1acd  sub
0x1ace  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::RemoveAt(int32)
0x1ad3  ldloc.0
0x1ad4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1ad9  ldc.i4.2
0x1ada  bne.un.s loc_1AF5
0x1adc  ldloc.0
0x1add  ldc.i4.0
0x1ade  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1ae3  ldloc.0
0x1ae4  ldc.i4.1
0x1ae5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1aea  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependencyConjunction(string itemA, string itemB)
0x1aef  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependency(string itemlist)
0x1af4  ret
0x1af5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1afa  ldstr    a0// "{0} "
0x1aff  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ComponentItem_CircularDependencyDelimit()
0x1b04  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1b09  ldloc.0
0x1b0a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x1b0f  call     string [mscorlib]System.String::Join(string, string[])
0x1b14  call     string Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependency(string itemlist)
0x1b19  ret
0x1b1a  ldsfld   string [mscorlib]System.String::Empty
0x1b1f  ret
```
