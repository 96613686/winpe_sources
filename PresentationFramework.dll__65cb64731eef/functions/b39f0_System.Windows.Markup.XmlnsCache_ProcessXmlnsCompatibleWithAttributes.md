# System.Windows.Markup.XmlnsCache::ProcessXmlnsCompatibleWithAttributes

- ea: `0xb39f0`
- end: `0xb3ad6`
- name: `System.Windows.Markup.XmlnsCache::ProcessXmlnsCompatibleWithAttributes`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb37e0`

## callees

- `0x38c70`
- `0xb38f0`
- `0xb3920`
- `0xb39f0`

## string_xrefs

- `0xb3a42`: `XmlnsCompatibleWithAttribute`
- `0xb3a76`: `ParserCompatDuplicate`

## pseudocode

```c

```

## disassembly

```asm
0xb39f0  ldc.i4.0
0xb39f1  stloc.0
0xb39f2  br       loc_B3ACC
0xb39f7  ldarg.0
0xb39f8  ldarg.1
0xb39f9  ldloc.0
0xb39fa  ldelem.ref
0xb39fb  ldtoken  [System.Xaml]System.Windows.Markup.XmlnsCompatibleWithAttribute
0xb3a00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3a05  call     instance class [mscorlib]System.Attribute[] System.Windows.Markup.XmlnsCache::GetAttributes(class [mscorlib]System.Reflection.Assembly asm, class [mscorlib]System.Type attrType)
0xb3a0a  stloc.1
0xb3a0b  ldc.i4.0
0xb3a0c  stloc.2
0xb3a0d  br       loc_B3ABF
0xb3a12  ldnull
0xb3a13  stloc.3
0xb3a14  ldnull
0xb3a15  stloc.s  4
0xb3a17  ldarg.0
0xb3a18  ldloc.1
0xb3a19  ldloc.2
0xb3a1a  ldelem.ref
0xb3a1b  ldloca.s 3
0xb3a1d  ldloca.s 4
0xb3a1f  call     instance void System.Windows.Markup.XmlnsCache::GetNamespacesFromCompatAttr(class [mscorlib]System.Attribute attr, [out] string& oldXmlns, [out] string& newXmlns)
0xb3a24  ldloc.3
0xb3a25  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb3a2a  brtrue.s loc_B3A35
0xb3a2c  ldloc.s  4
0xb3a2e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb3a33  brfalse.s loc_B3A53
0xb3a35  ldstr    aParserattribut// "ParserAttributeArgsLow"
0xb3a3a  ldc.i4.1
0xb3a3b  newarr   [mscorlib]System.Object
0xb3a40  dup
0xb3a41  ldc.i4.0
0xb3a42  ldstr    aXmlnscompatibl// "XmlnsCompatibleWithAttribute"
0xb3a47  stelem.ref
0xb3a48  call     string System.Windows.SR::Get(string id, object[] args)
0xb3a4d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb3a52  throw
0xb3a53  ldarg.0
0xb3a54  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlnsCache::_compatTable
0xb3a59  ldloc.3
0xb3a5a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0xb3a5f  brfalse.s loc_B3A9F
0xb3a61  ldarg.0
0xb3a62  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlnsCache::_compatTable
0xb3a67  ldloc.3
0xb3a68  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xb3a6d  ldloc.s  4
0xb3a6f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb3a74  brfalse.s loc_B3A9F
0xb3a76  ldstr    aParsercompatdu// "ParserCompatDuplicate"
0xb3a7b  ldc.i4.2
0xb3a7c  newarr   [mscorlib]System.Object
0xb3a81  dup
0xb3a82  ldc.i4.0
0xb3a83  ldloc.3
0xb3a84  stelem.ref
0xb3a85  dup
0xb3a86  ldc.i4.1
0xb3a87  ldarg.0
0xb3a88  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlnsCache::_compatTable
0xb3a8d  ldloc.3
0xb3a8e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xb3a93  stelem.ref
0xb3a94  call     string System.Windows.SR::Get(string id, object[] args)
0xb3a99  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb3a9e  throw
0xb3a9f  ldarg.0
0xb3aa0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlnsCache::_compatTable
0xb3aa5  ldloc.3
0xb3aa6  ldloc.s  4
0xb3aa8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xb3aad  ldarg.0
0xb3aae  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Windows.Markup.XmlnsCache::_compatTableReverse
0xb3ab3  ldloc.s  4
0xb3ab5  ldloc.3
0xb3ab6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xb3abb  ldloc.2
0xb3abc  ldc.i4.1
0xb3abd  add
0xb3abe  stloc.2
0xb3abf  ldloc.2
0xb3ac0  ldloc.1
0xb3ac1  ldlen
0xb3ac2  conv.i4
0xb3ac3  blt      loc_B3A12
0xb3ac8  ldloc.0
0xb3ac9  ldc.i4.1
0xb3aca  add
0xb3acb  stloc.0
0xb3acc  ldloc.0
0xb3acd  ldarg.1
0xb3ace  ldlen
0xb3acf  conv.i4
0xb3ad0  blt      loc_B39F7
0xb3ad5  ret
```
