# InMember::WriteObject

- ea: `0x2d960`
- end: `0x2da75`
- name: `InMember::WriteObject`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0xa590`
- `0xd110`
- `0xd130`
- `0xefa0`
- `0x11f20`
- `0x2cb20`
- `0x2cb30`
- `0x2cb70`
- `0x2cb80`
- `0x2cba0`
- `0x2cca0`
- `0x2cd20`
- `0x2cf60`
- `0x2d1d0`
- `0x2d490`
- `0x2d960`

## string_xrefs

- `0x2d9e4`: `XamlXmlWriterWriteObjectNotSupportedInCurrentState`
- `0x2da46`: `XamlXmlWriterIsObjectFromMemberSetForArraysOrNonCollections`

## pseudocode

```c

```

## disassembly

```asm
0x2d960  ldarg.1
0x2d961  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d966  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d96b  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d970  ldc.i4.1
0x2d971  beq.s    loc_2D9A3
0x2d973  ldarg.1
0x2d974  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d979  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d97e  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d983  ldc.i4.2
0x2d984  beq.s    loc_2D9A3
0x2d986  ldarg.1
0x2d987  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d98c  newobj   instance void Frame::.ctor()
0x2d991  dup
0x2d992  ldarg.3
0x2d993  brtrue.s loc_2D998
0x2d995  ldc.i4.1
0x2d996  br.s     loc_2D999
0x2d998  ldc.i4.2
0x2d999  callvirt instance void Frame::set_AllocatingNodeType(valuetype System.Xaml.XamlNodeType value)
0x2d99e  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0x2d9a3  ldarg.1
0x2d9a4  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d9a9  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d9ae  ldarg.2
0x2d9af  callvirt instance void Frame::set_Type(class System.Xaml.XamlType value)
0x2d9b4  ldarg.1
0x2d9b5  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d9ba  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d9bf  ldarg.3
0x2d9c0  callvirt instance void Frame::set_IsObjectFromMember(bool value)
0x2d9c5  ldarg.1
0x2d9c6  ldc.i4.0
0x2d9c7  stfld    bool System.Xaml.XamlXmlWriter::isFirstElementOfWhitespaceSignificantCollection
0x2d9cc  ldarg.3
0x2d9cd  brfalse  loc_2DA62
0x2d9d2  ldarg.1
0x2d9d3  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d9d8  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2d9dd  callvirt instance bool Frame::IsEmpty()
0x2d9e2  brtrue.s loc_2D9F4
0x2d9e4  ldstr    aXamlxmlwriterw_0// "XamlXmlWriterWriteObjectNotSupportedInC"...
0x2d9e9  call     string System.Xaml.SR::Get(string id)
0x2d9ee  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d9f3  throw
0x2d9f4  ldarg.1
0x2d9f5  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d9fa  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0x2d9ff  stloc.0
0x2da00  ldarg.1
0x2da01  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2da06  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2da0b  stloc.1
0x2da0c  ldarg.1
0x2da0d  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2da12  ldloc.0
0x2da13  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0x2da18  ldloc.1
0x2da19  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2da1e  ldc.i4.4
0x2da1f  bne.un.s loc_2DA56
0x2da21  ldloc.1
0x2da22  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2da27  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x2da2c  stloc.2
0x2da2d  ldloc.2
0x2da2e  ldnull
0x2da2f  call     bool System.Xaml.XamlType::op_Inequality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2da34  brfalse.s loc_2DA56
0x2da36  ldloc.2
0x2da37  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2da3c  brtrue.s loc_2DA56
0x2da3e  ldloc.2
0x2da3f  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x2da44  brtrue.s loc_2DA56
0x2da46  ldstr    aXamlxmlwriteri// "XamlXmlWriterIsObjectFromMemberSetForAr"...
0x2da4b  call     string System.Xaml.SR::Get(string id)
0x2da50  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2da55  throw
0x2da56  ldarg.1
0x2da57  call     class WriterState InRecord::get_State()
0x2da5c  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2da61  ret
0x2da62  ldarg.1
0x2da63  ldarg.2
0x2da64  call     void WriterState::WriteStartElementForObject(class System.Xaml.XamlXmlWriter writer, class System.Xaml.XamlType type)
0x2da69  ldarg.1
0x2da6a  call     class WriterState InRecordTryAttributes::get_State()
0x2da6f  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2da74  ret
```
