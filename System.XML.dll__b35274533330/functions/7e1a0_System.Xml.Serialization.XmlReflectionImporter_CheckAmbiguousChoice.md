# System.Xml.Serialization.XmlReflectionImporter::CheckAmbiguousChoice

- ea: `0x7e1a0`
- end: `0x7e39c`
- name: `System.Xml.Serialization.XmlReflectionImporter::CheckAmbiguousChoice`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x7c5e0`

## callees

- `0x622f0`
- `0x6b100`
- `0x6b120`
- `0x6b1c0`
- `0x75350`
- `0x75370`
- `0x753c0`
- `0x75470`
- `0x75b50`
- `0x75be0`
- `0x75c70`
- `0x75ca0`
- `0x79210`
- `0x79350`
- `0x7e1a0`

## string_xrefs

- `0x7e1fa`: `XmlChoiceIdentiferMissing`
- `0x7e261`: `XmlChoiceIdentiferMissing`
- `0x7e314`: `XmlArrayItemAmbiguousTypes`

## pseudocode

```c

```

## disassembly

```asm
0x7e1a0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x7e1a5  stloc.0
0x7e1a6  ldarg.1
0x7e1a7  callvirt instance class System.Xml.Serialization.XmlElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlElements()
0x7e1ac  stloc.1
0x7e1ad  ldloc.1
0x7e1ae  brfalse  loc_7E241
0x7e1b3  ldloc.1
0x7e1b4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e1b9  ldc.i4.2
0x7e1ba  blt      loc_7E241
0x7e1bf  ldarg.1
0x7e1c0  callvirt instance class System.Xml.Serialization.XmlChoiceIdentifierAttribute System.Xml.Serialization.XmlAttributes::get_XmlChoiceIdentifier()
0x7e1c5  brtrue.s loc_7E241
0x7e1c7  ldc.i4.0
0x7e1c8  stloc.3
0x7e1c9  br.s     loc_7E238
0x7e1cb  ldloc.1
0x7e1cc  ldloc.3
0x7e1cd  callvirt instance class System.Xml.Serialization.XmlElementAttribute System.Xml.Serialization.XmlElementAttributes::get_Item(int32 index)
0x7e1d2  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlElementAttribute::get_Type()
0x7e1d7  ldnull
0x7e1d8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7e1dd  brtrue.s loc_7E1ED
0x7e1df  ldloc.1
0x7e1e0  ldloc.3
0x7e1e1  callvirt instance class System.Xml.Serialization.XmlElementAttribute System.Xml.Serialization.XmlElementAttributes::get_Item(int32 index)
0x7e1e6  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlElementAttribute::get_Type()
0x7e1eb  br.s     loc_7E1EE
0x7e1ed  ldarg.2
0x7e1ee  stloc.s  4
0x7e1f0  ldloc.0
0x7e1f1  ldloc.s  4
0x7e1f3  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x7e1f8  brfalse.s loc_7E226
0x7e1fa  ldstr    aXmlchoiceident_4// "XmlChoiceIdentiferMissing"
0x7e1ff  ldc.i4.2
0x7e200  newarr   [mscorlib]System.Object
0x7e205  dup
0x7e206  ldc.i4.0
0x7e207  ldtoken  System.Xml.Serialization.XmlChoiceIdentifierAttribute
0x7e20c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e211  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7e216  stelem.ref
0x7e217  dup
0x7e218  ldc.i4.1
0x7e219  ldarg.3
0x7e21a  stelem.ref
0x7e21b  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e220  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e225  throw
0x7e226  ldloc.0
0x7e227  ldloc.s  4
0x7e229  ldc.i4.0
0x7e22a  box      [mscorlib]System.Boolean
0x7e22f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x7e234  ldloc.3
0x7e235  ldc.i4.1
0x7e236  add
0x7e237  stloc.3
0x7e238  ldloc.3
0x7e239  ldloc.1
0x7e23a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e23f  blt.s    loc_7E1CB
0x7e241  ldloc.0
0x7e242  ldtoken  System.Xml.XmlElement
0x7e247  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e24c  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x7e251  brfalse.s loc_7E28D
0x7e253  ldarg.1
0x7e254  callvirt instance class System.Xml.Serialization.XmlAnyElementAttributes System.Xml.Serialization.XmlAttributes::get_XmlAnyElements()
0x7e259  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e25e  ldc.i4.0
0x7e25f  ble.s    loc_7E28D
0x7e261  ldstr    aXmlchoiceident_4// "XmlChoiceIdentiferMissing"
0x7e266  ldc.i4.2
0x7e267  newarr   [mscorlib]System.Object
0x7e26c  dup
0x7e26d  ldc.i4.0
0x7e26e  ldtoken  System.Xml.Serialization.XmlChoiceIdentifierAttribute
0x7e273  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e278  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7e27d  stelem.ref
0x7e27e  dup
0x7e27f  ldc.i4.1
0x7e280  ldarg.3
0x7e281  stelem.ref
0x7e282  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e287  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e28c  throw
0x7e28d  ldarg.1
0x7e28e  callvirt instance class System.Xml.Serialization.XmlArrayItemAttributes System.Xml.Serialization.XmlAttributes::get_XmlArrayItems()
0x7e293  stloc.2
0x7e294  ldloc.2
0x7e295  brfalse  loc_7E39B
0x7e29a  ldloc.2
0x7e29b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e2a0  ldc.i4.2
0x7e2a1  blt      loc_7E39B
0x7e2a6  newobj   instance void System.Xml.Serialization.NameTable::.ctor()
0x7e2ab  stloc.s  5
0x7e2ad  ldc.i4.0
0x7e2ae  stloc.s  6
0x7e2b0  br       loc_7E38E
0x7e2b5  ldloc.2
0x7e2b6  ldloc.s  6
0x7e2b8  callvirt instance class System.Xml.Serialization.XmlArrayItemAttribute System.Xml.Serialization.XmlArrayItemAttributes::get_Item(int32 index)
0x7e2bd  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlArrayItemAttribute::get_Type()
0x7e2c2  ldnull
0x7e2c3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7e2c8  brtrue.s loc_7E2D9
0x7e2ca  ldloc.2
0x7e2cb  ldloc.s  6
0x7e2cd  callvirt instance class System.Xml.Serialization.XmlArrayItemAttribute System.Xml.Serialization.XmlArrayItemAttributes::get_Item(int32 index)
0x7e2d2  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlArrayItemAttribute::get_Type()
0x7e2d7  br.s     loc_7E2DA
0x7e2d9  ldarg.2
0x7e2da  stloc.s  7
0x7e2dc  ldloc.2
0x7e2dd  ldloc.s  6
0x7e2df  callvirt instance class System.Xml.Serialization.XmlArrayItemAttribute System.Xml.Serialization.XmlArrayItemAttributes::get_Item(int32 index)
0x7e2e4  callvirt instance int32 System.Xml.Serialization.XmlArrayItemAttribute::get_NestingLevel()
0x7e2e9  stloc.s  0xA
0x7e2eb  ldloca.s 0xA
0x7e2ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e2f2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7e2f7  stloc.s  8
0x7e2f9  ldloc.s  5
0x7e2fb  ldloc.s  7
0x7e2fd  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7e302  ldloc.s  8
0x7e304  callvirt instance object System.Xml.Serialization.NameTable::get_Item(string name, string ns)
0x7e309  castclass System.Xml.Serialization.XmlArrayItemAttribute
0x7e30e  stloc.s  9
0x7e310  ldloc.s  9
0x7e312  brfalse.s loc_7E370
0x7e314  ldstr    aXmlarrayitemam// "XmlArrayItemAmbiguousTypes"
0x7e319  ldc.i4.6
0x7e31a  newarr   [mscorlib]System.Object
0x7e31f  dup
0x7e320  ldc.i4.0
0x7e321  ldarg.3
0x7e322  stelem.ref
0x7e323  dup
0x7e324  ldc.i4.1
0x7e325  ldloc.s  9
0x7e327  callvirt instance string System.Xml.Serialization.XmlArrayItemAttribute::get_ElementName()
0x7e32c  stelem.ref
0x7e32d  dup
0x7e32e  ldc.i4.2
0x7e32f  ldloc.2
0x7e330  ldloc.s  6
0x7e332  callvirt instance class System.Xml.Serialization.XmlArrayItemAttribute System.Xml.Serialization.XmlArrayItemAttributes::get_Item(int32 index)
0x7e337  callvirt instance string System.Xml.Serialization.XmlArrayItemAttribute::get_ElementName()
0x7e33c  stelem.ref
0x7e33d  dup
0x7e33e  ldc.i4.3
0x7e33f  ldtoken  System.Xml.Serialization.XmlElementAttribute
0x7e344  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e349  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7e34e  stelem.ref
0x7e34f  dup
0x7e350  ldc.i4.4
0x7e351  ldtoken  System.Xml.Serialization.XmlChoiceIdentifierAttribute
0x7e356  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e35b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7e360  stelem.ref
0x7e361  dup
0x7e362  ldc.i4.5
0x7e363  ldarg.3
0x7e364  stelem.ref
0x7e365  call     string System.Xml.Res::GetString(string name, object[] args)
0x7e36a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7e36f  throw
0x7e370  ldloc.s  5
0x7e372  ldloc.s  7
0x7e374  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7e379  ldloc.s  8
0x7e37b  ldloc.2
0x7e37c  ldloc.s  6
0x7e37e  callvirt instance class System.Xml.Serialization.XmlArrayItemAttribute System.Xml.Serialization.XmlArrayItemAttributes::get_Item(int32 index)
0x7e383  callvirt instance void System.Xml.Serialization.NameTable::set_Item(string name, string ns, object value)
0x7e388  ldloc.s  6
0x7e38a  ldc.i4.1
0x7e38b  add
0x7e38c  stloc.s  6
0x7e38e  ldloc.s  6
0x7e390  ldloc.2
0x7e391  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7e396  blt      loc_7E2B5
0x7e39b  ret
```
