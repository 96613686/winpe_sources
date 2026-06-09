# System.Xaml.XmlCompatibilityReader::.ctor

- ea: `0x105f0`
- end: `0x1074d`
- name: `System.Xaml.XmlCompatibilityReader::.ctor`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10750`

## callees

- `0x10530`
- `0x10580`
- `0x105f0`
- `0x10fe0`
- `0x117f0`
- `0x11820`
- `0x11850`
- `0x118b0`
- `0x118e0`
- `0x11910`
- `0x11940`
- `0x11970`
- `0x11a20`
- `0x11d80`
- `0x2ec70`

## pseudocode

```c

```

## disassembly

```asm
0x105f0  ldarg.0
0x105f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x105f6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XmlCompatibilityReader::_namespaceMap
0x105fb  ldarg.0
0x105fc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback>::.ctor()
0x10601  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback> System.Xaml.XmlCompatibilityReader::_elementHandler
0x10606  ldarg.0
0x10607  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::.ctor()
0x1060c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x10611  ldarg.0
0x10612  ldarg.1
0x10613  call     instance void System.Xaml.XmlWrappingReader::.ctor(class [System.Xml]System.Xml.XmlReader baseReader)
0x10618  ldarg.0
0x10619  ldnull
0x1061a  ldc.i4.m1
0x1061b  ldarg.0
0x1061c  newobj   instance void CompatibilityScope::.ctor(class CompatibilityScope previous, int32 depth, class System.Xaml.XmlCompatibilityReader reader)
0x10621  stfld    class CompatibilityScope System.Xaml.XmlCompatibilityReader::_compatibilityScope
0x10626  ldsfld   string[] System.Xaml.XmlCompatibilityReader::_predefinedNamespaces
0x1062b  stloc.0
0x1062c  ldc.i4.0
0x1062d  stloc.1
0x1062e  br.s     loc_1065E
0x10630  ldloc.0
0x10631  ldloc.1
0x10632  ldelem.ref
0x10633  stloc.2
0x10634  ldarg.0
0x10635  ldloc.2
0x10636  call     instance void System.Xaml.XmlCompatibilityReader::AddKnownNamespace(string namespaceName)
0x1063b  ldarg.0
0x1063c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Xaml.XmlCompatibilityReader::_namespaceMap
0x10641  ldloc.2
0x10642  ldloc.2
0x10643  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x10648  ldarg.0
0x10649  call     instance class [System.Xml]System.Xml.XmlReader System.Xaml.XmlWrappingReader::get_Reader()
0x1064e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x10653  ldloc.2
0x10654  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x10659  pop
0x1065a  ldloc.1
0x1065b  ldc.i4.1
0x1065c  add
0x1065d  stloc.1
0x1065e  ldloc.1
0x1065f  ldloc.0
0x10660  ldlen
0x10661  conv.i4
0x10662  blt.s    loc_10630
0x10664  ldarg.0
0x10665  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback> System.Xaml.XmlCompatibilityReader::_elementHandler
0x1066a  ldarg.0
0x1066b  call     instance string System.Xaml.XmlCompatibilityReader::get_AlternateContent()
0x10670  ldarg.0
0x10671  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleAlternateContent(int32 elementDepth, bool& more)
0x10677  newobj   instance void System.Xaml.HandleElementCallback::.ctor(object object, native int method)
0x1067c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback>::Add(var<u1>, !!T0)
0x10681  ldarg.0
0x10682  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback> System.Xaml.XmlCompatibilityReader::_elementHandler
0x10687  ldarg.0
0x10688  call     instance string System.Xaml.XmlCompatibilityReader::get_Choice()
0x1068d  ldarg.0
0x1068e  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleChoice(int32 elementDepth, bool& more)
0x10694  newobj   instance void System.Xaml.HandleElementCallback::.ctor(object object, native int method)
0x10699  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback>::Add(var<u1>, !!T0)
0x1069e  ldarg.0
0x1069f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback> System.Xaml.XmlCompatibilityReader::_elementHandler
0x106a4  ldarg.0
0x106a5  call     instance string System.Xaml.XmlCompatibilityReader::get_Fallback()
0x106aa  ldarg.0
0x106ab  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleFallback(int32 elementDepth, bool& more)
0x106b1  newobj   instance void System.Xaml.HandleElementCallback::.ctor(object object, native int method)
0x106b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleElementCallback>::Add(var<u1>, !!T0)
0x106bb  ldarg.0
0x106bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x106c1  ldarg.0
0x106c2  call     instance string System.Xaml.XmlCompatibilityReader::get_Ignorable()
0x106c7  ldarg.0
0x106c8  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleIgnorable(int32 elementDepth)
0x106ce  newobj   instance void System.Xaml.HandleAttributeCallback::.ctor(object object, native int method)
0x106d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::Add(var<u1>, !!T0)
0x106d8  ldarg.0
0x106d9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x106de  ldarg.0
0x106df  call     instance string System.Xaml.XmlCompatibilityReader::get_MustUnderstand()
0x106e4  ldarg.0
0x106e5  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleMustUnderstand(int32 elementDepth)
0x106eb  newobj   instance void System.Xaml.HandleAttributeCallback::.ctor(object object, native int method)
0x106f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::Add(var<u1>, !!T0)
0x106f5  ldarg.0
0x106f6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x106fb  ldarg.0
0x106fc  call     instance string System.Xaml.XmlCompatibilityReader::get_ProcessContent()
0x10701  ldarg.0
0x10702  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandleProcessContent(int32 elementDepth)
0x10708  newobj   instance void System.Xaml.HandleAttributeCallback::.ctor(object object, native int method)
0x1070d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::Add(var<u1>, !!T0)
0x10712  ldarg.0
0x10713  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x10718  ldarg.0
0x10719  call     instance string System.Xaml.XmlCompatibilityReader::get_PreserveElements()
0x1071e  ldarg.0
0x1071f  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandlePreserveElements(int32 elementDepth)
0x10725  newobj   instance void System.Xaml.HandleAttributeCallback::.ctor(object object, native int method)
0x1072a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::Add(var<u1>, !!T0)
0x1072f  ldarg.0
0x10730  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback> System.Xaml.XmlCompatibilityReader::_attributeHandler
0x10735  ldarg.0
0x10736  call     instance string System.Xaml.XmlCompatibilityReader::get_PreserveAttributes()
0x1073b  ldarg.0
0x1073c  ldftn    instance void System.Xaml.XmlCompatibilityReader::HandlePreserveAttributes(int32 elementDepth)
0x10742  newobj   instance void System.Xaml.HandleAttributeCallback::.ctor(object object, native int method)
0x10747  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class System.Xaml.HandleAttributeCallback>::Add(var<u1>, !!T0)
0x1074c  ret
```
