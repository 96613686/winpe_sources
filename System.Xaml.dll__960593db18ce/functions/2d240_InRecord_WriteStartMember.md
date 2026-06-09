# InRecord::WriteStartMember

- ea: `0x2d240`
- end: `0x2d3dd`
- name: `InRecord::WriteStartMember`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config`

## callees

- `0x8860`
- `0x8b20`
- `0x8b80`
- `0x8be0`
- `0xb280`
- `0xd0f0`
- `0xd1a0`
- `0xd370`
- `0xefa0`
- `0xf950`
- `0xfd40`
- `0xfdf0`
- `0x11f20`
- `0x11f50`
- `0x2cb10`
- `0x2cb20`
- `0x2cb40`
- `0x2cb70`
- `0x2cb80`
- `0x2cca0`
- `0x2cd20`
- `0x2ce10`
- `0x2d1d0`
- `0x2d240`
- `0x2d6d0`
- `0x2dfe0`
- `0x2e4c0`
- `0x2ebe0`

## string_xrefs

- `0x2d306`: `XamlXmlWriterWriteNotSupportedInCurrentState`
- `0x2d344`: `XamlXmlWriterWriteNotSupportedInCurrentState`
- `0x2d313`: `WriteStartMember`
- `0x2d351`: `WriteStartMember`

## pseudocode

```c

```

## disassembly

```asm
0x2d240  ldarg.1
0x2d241  ldarg.2
0x2d242  callvirt instance void System.Xaml.XamlXmlWriter::CheckMemberForUniqueness(class System.Xaml.XamlMember property)
0x2d247  ldarg.1
0x2d248  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d24d  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d252  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d257  ldc.i4.4
0x2d258  beq.s    loc_2D287
0x2d25a  ldarg.1
0x2d25b  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d260  newobj   instance void Frame::.ctor()
0x2d265  dup
0x2d266  ldc.i4.4
0x2d267  callvirt instance void Frame::set_AllocatingNodeType(valuetype System.Xaml.XamlNodeType value)
0x2d26c  dup
0x2d26d  ldarg.1
0x2d26e  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d273  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d278  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d27d  callvirt instance void Frame::set_Type(class System.Xaml.XamlType value)
0x2d282  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0x2d287  ldarg.1
0x2d288  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d28d  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d292  ldarg.2
0x2d293  callvirt instance void Frame::set_Member(class System.Xaml.XamlMember value)
0x2d298  ldarg.1
0x2d299  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d29e  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d2a3  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d2a8  stloc.0
0x2d2a9  ldarg.2
0x2d2aa  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Items()
0x2d2af  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d2b4  brfalse.s loc_2D2C7
0x2d2b6  ldloc.0
0x2d2b7  ldnull
0x2d2b8  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d2bd  brfalse.s loc_2D2C7
0x2d2bf  ldloc.0
0x2d2c0  callvirt instance bool System.Xaml.XamlType::get_IsWhitespaceSignificantCollection()
0x2d2c5  brtrue.s loc_2D2D4
0x2d2c7  ldarg.2
0x2d2c8  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_UnknownContent()
0x2d2cd  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d2d2  brfalse.s loc_2D2DB
0x2d2d4  ldarg.1
0x2d2d5  ldc.i4.1
0x2d2d6  stfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d2db  ldarg.1
0x2d2dc  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d2e1  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d2e6  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2d2eb  stloc.1
0x2d2ec  ldarg.2
0x2d2ed  call     bool System.Xaml.XamlXmlWriter::IsImplicit(class System.Xaml.XamlMember xamlMember)
0x2d2f2  brfalse.s loc_2D324
0x2d2f4  ldarg.1
0x2d2f5  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d2fa  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d2ff  callvirt instance bool Frame::IsEmpty()
0x2d304  brtrue.s loc_2D37B
0x2d306  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2d30b  ldc.i4.1
0x2d30c  newarr   [mscorlib]System.Object
0x2d311  dup
0x2d312  ldc.i4.0
0x2d313  ldstr    aWritestartmemb// "WriteStartMember"
0x2d318  stelem.ref
0x2d319  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d31e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d323  throw
0x2d324  ldarg.2
0x2d325  ldloc.1
0x2d326  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::get_ContentProperty()
0x2d32b  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d330  brfalse.s loc_2D36E
0x2d332  ldarg.1
0x2d333  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d338  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d33d  callvirt instance bool Frame::IsEmpty()
0x2d342  brtrue.s loc_2D362
0x2d344  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2d349  ldc.i4.1
0x2d34a  newarr   [mscorlib]System.Object
0x2d34f  dup
0x2d350  ldc.i4.0
0x2d351  ldstr    aWritestartmemb// "WriteStartMember"
0x2d356  stelem.ref
0x2d357  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d35c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d361  throw
0x2d362  ldarg.1
0x2d363  call     class WriterState TryContentProperty::get_State()
0x2d368  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d36d  ret
0x2d36e  ldarg.1
0x2d36f  call     void WriterState::WriteMemberAsElement(class System.Xaml.XamlXmlWriter writer)
0x2d374  ldarg.1
0x2d375  ldc.i4.4
0x2d376  callvirt instance void System.Xaml.XamlXmlWriter::WriteDeferredNamespaces(valuetype System.Xaml.XamlNodeType nodeType)
0x2d37b  ldarg.2
0x2d37c  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x2d381  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x2d386  brfalse.s loc_2D3D1
0x2d388  ldarg.1
0x2d389  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d38e  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0x2d393  pop
0x2d394  ldloc.1
0x2d395  ldnull
0x2d396  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2d39b  brfalse.s loc_2D3B5
0x2d39d  ldloc.1
0x2d39e  callvirt instance bool System.Xaml.XamlType::get_ConstructionRequiresArguments()
0x2d3a3  brfalse.s loc_2D3B5
0x2d3a5  ldstr    aExpandposition// "ExpandPositionalParametersinTypeWithNoD"...
0x2d3aa  call     string System.Xaml.SR::Get(string id)
0x2d3af  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2d3b4  throw
0x2d3b5  ldarg.1
0x2d3b6  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2d3bb  call     class WriterState InRecord::get_State()
0x2d3c0  callvirt instance void PositionalParameterStateInfo::set_ReturnState(class WriterState value)
0x2d3c5  ldarg.1
0x2d3c6  call     class WriterState ExpandPositionalParameters::get_State()
0x2d3cb  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d3d0  ret
0x2d3d1  ldarg.1
0x2d3d2  call     class WriterState InMember::get_State()
0x2d3d7  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d3dc  ret
```
