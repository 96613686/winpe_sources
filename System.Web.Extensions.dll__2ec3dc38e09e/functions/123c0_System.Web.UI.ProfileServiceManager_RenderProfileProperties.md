# System.Web.UI.ProfileServiceManager::RenderProfileProperties

- ea: `0x123c0`
- end: `0x1245c`
- name: `System.Web.UI.ProfileServiceManager::RenderProfileProperties`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x12170`

## callees

- `0x123c0`
- `0x31d00`
- `0x31f10`

## string_xrefs

- `0x123c7`: `Sys.Services.ProfileService.properties = `
- `0x12401`: `Sys.Services.ProfileService.properties.`
- `0x1241b`: ` = new Sys.Services.ProfileGroup(`

## pseudocode

```c

```

## disassembly

```asm
0x123c0  newobj   instance void System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x123c5  stloc.0
0x123c6  ldarg.0
0x123c7  ldstr    aSysServicesPro_1// "Sys.Services.ProfileService.properties "...
0x123cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x123d1  pop
0x123d2  ldarg.0
0x123d3  ldloc.0
0x123d4  ldarg.1
0x123d5  ldc.i4.1
0x123d6  callvirt instance string System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object obj, valuetype SerializationFormat serializationFormat)
0x123db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x123e0  pop
0x123e1  ldarg.0
0x123e2  ldstr    asc_40496// ";\n"
0x123e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x123ec  pop
0x123ed  ldarg.2
0x123ee  brfalse.s loc_1245B
0x123f0  ldarg.2
0x123f1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>>::GetEnumerator()
0x123f6  stloc.1
0x123f7  br.s     loc_12447
0x123f9  ldloc.1
0x123fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>>>::get_Current()
0x123ff  stloc.2
0x12400  ldarg.0
0x12401  ldstr    aSysServicesPro_2// "Sys.Services.ProfileService.properties."
0x12406  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1240b  pop
0x1240c  ldarg.0
0x1240d  ldloca.s 2
0x1240f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>>::get_Key()
0x12414  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12419  pop
0x1241a  ldarg.0
0x1241b  ldstr    aNewSysServices// " = new Sys.Services.ProfileGroup("
0x12420  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12425  pop
0x12426  ldarg.0
0x12427  ldloc.0
0x12428  ldloca.s 2
0x1242a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>>::get_Value()
0x1242f  ldc.i4.1
0x12430  callvirt instance string System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object obj, valuetype SerializationFormat serializationFormat)
0x12435  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1243a  pop
0x1243b  ldarg.0
0x1243c  ldstr    asc_40530// ");\n"
0x12441  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12446  pop
0x12447  ldloc.1
0x12448  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1244d  brtrue.s loc_123F9
0x1244f  leave.s  loc_1245B
0x12451  ldloc.1
0x12452  brfalse.s loc_1245A
0x12454  ldloc.1
0x12455  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1245a  endfinally
0x1245b  ret
```
