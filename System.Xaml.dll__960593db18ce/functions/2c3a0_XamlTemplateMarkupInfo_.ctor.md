# XamlTemplateMarkupInfo::.ctor

- ea: `0x2c3a0`
- end: `0x2c604`
- name: `XamlTemplateMarkupInfo::.ctor`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x29430`

## callees

- `0x20e0`
- `0x2100`
- `0x8810`
- `0xb310`
- `0xb320`
- `0xb340`
- `0xb350`
- `0xb360`
- `0xb370`
- `0x11f50`
- `0x291e0`
- `0x29fa0`
- `0x29fb0`
- `0x2b9a0`
- `0x2bdf0`
- `0x2c3a0`

## pseudocode

```c

```

## disassembly

```asm
0x2c3a0  ldarg.0
0x2c3a1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::.ctor()
0x2c3a6  stfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c3ab  ldarg.0
0x2c3ac  call     instance void ObjectMarkupInfo::.ctor()
0x2c3b1  br.s     loc_2C410
0x2c3b3  ldarg.1
0x2c3b4  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c3b9  ldc.i4.7
0x2c3ba  beq.s    loc_2C3E0
0x2c3bc  ldstr    aXamlfactoryinv// "XamlFactoryInvalidXamlNode"
0x2c3c1  ldc.i4.1
0x2c3c2  newarr   [mscorlib]System.Object
0x2c3c7  dup
0x2c3c8  ldc.i4.0
0x2c3c9  ldarg.1
0x2c3ca  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c3cf  box      System.Xaml.XamlNodeType
0x2c3d4  stelem.ref
0x2c3d5  call     string System.Xaml.SR::Get(string id, object[] args)
0x2c3da  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2c3df  throw
0x2c3e0  ldarg.2
0x2c3e1  ldarg.1
0x2c3e2  callvirt instance class System.Xaml.NamespaceDeclaration System.Xaml.XamlReader::get_Namespace()
0x2c3e7  callvirt instance bool SerializerContext::TryHoistNamespaceDeclaration(class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0x2c3ec  brtrue.s loc_2C410
0x2c3ee  ldarg.0
0x2c3ef  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c3f4  newobj   instance void ValueMarkupInfo::.ctor()
0x2c3f9  dup
0x2c3fa  ldc.i4.7
0x2c3fb  ldarg.1
0x2c3fc  callvirt instance class System.Xaml.NamespaceDeclaration System.Xaml.XamlReader::get_Namespace()
0x2c401  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c406  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c40b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c410  ldarg.1
0x2c411  callvirt instance bool System.Xaml.XamlReader::Read()
0x2c416  brfalse.s loc_2C421
0x2c418  ldarg.1
0x2c419  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c41e  ldc.i4.1
0x2c41f  bne.un.s loc_2C3B3
0x2c421  ldarg.1
0x2c422  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c427  ldc.i4.1
0x2c428  beq.s    loc_2C44E
0x2c42a  ldstr    aXamlfactoryinv// "XamlFactoryInvalidXamlNode"
0x2c42f  ldc.i4.1
0x2c430  newarr   [mscorlib]System.Object
0x2c435  dup
0x2c436  ldc.i4.0
0x2c437  ldarg.1
0x2c438  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c43d  box      System.Xaml.XamlNodeType
0x2c442  stelem.ref
0x2c443  call     string System.Xaml.SR::Get(string id, object[] args)
0x2c448  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2c44d  throw
0x2c44e  ldarg.0
0x2c44f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c454  newobj   instance void ValueMarkupInfo::.ctor()
0x2c459  dup
0x2c45a  ldc.i4.1
0x2c45b  ldarg.1
0x2c45c  callvirt instance class System.Xaml.XamlType System.Xaml.XamlReader::get_Type()
0x2c461  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c466  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c46b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c470  ldarg.0
0x2c471  ldarg.0
0x2c472  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c477  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Count()
0x2c47c  stfld    int32 XamlTemplateMarkupInfo::objectPosition
0x2c481  br       loc_2C5D0
0x2c486  ldarg.1
0x2c487  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c48c  stloc.0
0x2c48d  ldloc.0
0x2c48e  ldc.i4.1
0x2c48f  sub
0x2c490  switch   loc_2C4DD, loc_2C504, loc_2C525, loc_2C546, loc_2C56A, loc_2C588, loc_2C4B6
0x2c4b1  br       loc_2C5AC
0x2c4b6  ldarg.0
0x2c4b7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c4bc  newobj   instance void ValueMarkupInfo::.ctor()
0x2c4c1  dup
0x2c4c2  ldc.i4.7
0x2c4c3  ldarg.1
0x2c4c4  callvirt instance class System.Xaml.NamespaceDeclaration System.Xaml.XamlReader::get_Namespace()
0x2c4c9  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c4ce  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c4d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c4d8  br       loc_2C5D0
0x2c4dd  ldarg.0
0x2c4de  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c4e3  newobj   instance void ValueMarkupInfo::.ctor()
0x2c4e8  dup
0x2c4e9  ldc.i4.1
0x2c4ea  ldarg.1
0x2c4eb  callvirt instance class System.Xaml.XamlType System.Xaml.XamlReader::get_Type()
0x2c4f0  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c4f5  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c4fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c4ff  br       loc_2C5D0
0x2c504  ldarg.0
0x2c505  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c50a  newobj   instance void ValueMarkupInfo::.ctor()
0x2c50f  dup
0x2c510  ldc.i4.2
0x2c511  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2c516  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c51b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c520  br       loc_2C5D0
0x2c525  ldarg.0
0x2c526  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c52b  newobj   instance void ValueMarkupInfo::.ctor()
0x2c530  dup
0x2c531  ldc.i4.3
0x2c532  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2c537  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c53c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c541  br       loc_2C5D0
0x2c546  ldarg.0
0x2c547  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c54c  newobj   instance void ValueMarkupInfo::.ctor()
0x2c551  dup
0x2c552  ldc.i4.4
0x2c553  ldarg.1
0x2c554  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlReader::get_Member()
0x2c559  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c55e  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c563  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c568  br.s     loc_2C5D0
0x2c56a  ldarg.0
0x2c56b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c570  newobj   instance void ValueMarkupInfo::.ctor()
0x2c575  dup
0x2c576  ldc.i4.5
0x2c577  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType)
0x2c57c  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c581  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c586  br.s     loc_2C5D0
0x2c588  ldarg.0
0x2c589  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c58e  newobj   instance void ValueMarkupInfo::.ctor()
0x2c593  dup
0x2c594  ldc.i4.6
0x2c595  ldarg.1
0x2c596  callvirt instance object System.Xaml.XamlReader::get_Value()
0x2c59b  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2c5a0  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c5a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2c5aa  br.s     loc_2C5D0
0x2c5ac  ldstr    aXamlfactoryinv// "XamlFactoryInvalidXamlNode"
0x2c5b1  ldc.i4.1
0x2c5b2  newarr   [mscorlib]System.Object
0x2c5b7  dup
0x2c5b8  ldc.i4.0
0x2c5b9  ldarg.1
0x2c5ba  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0x2c5bf  box      System.Xaml.XamlNodeType
0x2c5c4  stelem.ref
0x2c5c5  call     string System.Xaml.SR::Get(string id, object[] args)
0x2c5ca  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2c5cf  throw
0x2c5d0  ldarg.1
0x2c5d1  callvirt instance bool System.Xaml.XamlReader::Read()
0x2c5d6  brtrue   loc_2C486
0x2c5db  ldarg.0
0x2c5dc  ldarg.0
0x2c5dd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c5e2  ldc.i4.0
0x2c5e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::get_Item(!!T0)
0x2c5e8  castclass ValueMarkupInfo
0x2c5ed  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2c5f2  call     instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x2c5f7  ldarg.0
0x2c5f8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> XamlTemplateMarkupInfo::nodes
0x2c5fd  ldc.i4.0
0x2c5fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::RemoveAt(int32)
0x2c603  ret
```
