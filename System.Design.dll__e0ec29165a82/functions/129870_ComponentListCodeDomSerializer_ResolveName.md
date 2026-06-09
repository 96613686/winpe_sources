# ComponentListCodeDomSerializer::ResolveName

- ea: `0x129870`
- end: `0x129c2b`
- name: `ComponentListCodeDomSerializer::ResolveName`
- size: `955`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x129400`
- `0x1295f0`
- `0x129870`

## callees

- `0x63480`
- `0x64130`
- `0x64ef0`
- `0x661c0`
- `0x67440`
- `0x8eec0`
- `0x129660`
- `0x129710`
- `0x129790`
- `0x129870`
- `0x129c30`
- `0x129cc0`

## string_xrefs

- `0x1299a3`: `SerializerNoSerializerForComponent`
- `0x129c0a`: `CodeDomComponentSerializationServiceDeserializationError`

## pseudocode

```c

```

## disassembly

```asm
0x129870  ldc.i4.0
0x129871  stloc.0
0x129872  ldarg.0
0x129873  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_statementsTable
0x129878  ldarg.2
0x129879  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x12987e  isinst   OrderedCodeStatementCollection
0x129883  stloc.1
0x129884  ldarg.0
0x129885  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_objectState
0x12988a  ldarg.2
0x12988b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x129890  castclass object[]
0x129895  stloc.2
0x129896  ldarg.2
0x129897  ldc.i4.s 0x2E
0x129899  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x12989e  ldc.i4.0
0x12989f  ble.s    loc_1298C9
0x1298a1  ldnull
0x1298a2  stloc.3
0x1298a3  ldarg.0
0x1298a4  ldarg.1
0x1298a5  ldarg.2
0x1298a6  ldloca.s 3
0x1298a8  call     instance class [System]System.ComponentModel.IComponent ComponentListCodeDomSerializer::ResolveNestedName(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, string& outerComponent)
0x1298ad  stloc.s  4
0x1298af  ldloc.s  4
0x1298b1  brfalse.s loc_1298C9
0x1298b3  ldloc.3
0x1298b4  brfalse.s loc_1298C9
0x1298b6  ldarg.1
0x1298b7  ldloc.s  4
0x1298b9  ldarg.2
0x1298ba  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::SetName(object, string)
0x1298bf  ldarg.0
0x1298c0  ldarg.1
0x1298c1  ldloc.3
0x1298c2  ldarg.3
0x1298c3  call     instance bool ComponentListCodeDomSerializer::ResolveName(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, bool canInvokeManager)
0x1298c8  pop
0x1298c9  ldloc.1
0x1298ca  brfalse  loc_129B01
0x1298cf  ldarg.0
0x1298d0  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_objectState
0x1298d5  ldarg.2
0x1298d6  ldnull
0x1298d7  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1298dc  ldarg.0
0x1298dd  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_statementsTable
0x1298e2  ldarg.2
0x1298e3  ldnull
0x1298e4  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1298e9  ldnull
0x1298ea  stloc.s  5
0x1298ec  ldloc.1
0x1298ed  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x1298f2  stloc.s  6
0x1298f4  br.s     loc_129920
0x1298f6  ldloc.s  6
0x1298f8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1298fd  castclass [System]System.CodeDom.CodeStatement
0x129902  stloc.s  7
0x129904  ldloc.s  7
0x129906  isinst   [System]System.CodeDom.CodeVariableDeclarationStatement
0x12990b  dup
0x12990c  stloc.s  8
0x12990e  brfalse.s loc_129920
0x129910  ldloc.s  8
0x129912  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeVariableDeclarationStatement::get_Type()
0x129917  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x12991c  stloc.s  5
0x12991e  leave.s  loc_129940
0x129920  ldloc.s  6
0x129922  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x129927  brtrue.s loc_1298F6
0x129929  leave.s  loc_129940
0x12992b  ldloc.s  6
0x12992d  isinst   [mscorlib]System.IDisposable
0x129932  stloc.s  9
0x129934  ldloc.s  9
0x129936  brfalse.s loc_12993F
0x129938  ldloc.s  9
0x12993a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12993f  endfinally
0x129940  ldloc.s  5
0x129942  brfalse  loc_1299FB
0x129947  ldarg.1
0x129948  ldloc.s  5
0x12994a  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::GetType(string)
0x12994f  stloc.s  0xA
0x129951  ldloc.s  0xA
0x129953  ldnull
0x129954  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x129959  brfalse.s loc_129981
0x12995b  ldarg.1
0x12995c  ldstr    aSerializertype// "SerializerTypeNotFound"
0x129961  ldc.i4.1
0x129962  newarr   [mscorlib]System.Object
0x129967  dup
0x129968  ldc.i4.0
0x129969  ldloc.s  5
0x12996b  stelem.ref
0x12996c  call     string System.Design.SR::GetString(string name, object[] args)
0x129971  ldarg.1
0x129972  newobj   instance void System.ComponentModel.Design.Serialization.CodeDomSerializerException::.ctor(string message, class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager)
0x129977  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x12997c  br       loc_129A3E
0x129981  ldloc.1
0x129982  brfalse  loc_129A3E
0x129987  ldloc.1
0x129988  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x12998d  ldc.i4.0
0x12998e  ble      loc_129A3E
0x129993  ldarg.0
0x129994  ldarg.1
0x129995  ldloc.s  0xA
0x129997  call     instance class System.ComponentModel.Design.Serialization.CodeDomSerializer System.ComponentModel.Design.Serialization.CodeDomSerializerBase::GetSerializer(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [mscorlib]System.Type valueType)
0x12999c  stloc.s  0xB
0x12999e  ldloc.s  0xB
0x1299a0  brtrue.s loc_1299CA
0x1299a2  ldarg.1
0x1299a3  ldstr    aSerializernose// "SerializerNoSerializerForComponent"
0x1299a8  ldc.i4.1
0x1299a9  newarr   [mscorlib]System.Object
0x1299ae  dup
0x1299af  ldc.i4.0
0x1299b0  ldloc.s  0xA
0x1299b2  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1299b7  stelem.ref
0x1299b8  call     string System.Design.SR::GetString(string name, object[] args)
0x1299bd  ldarg.1
0x1299be  newobj   instance void System.ComponentModel.Design.Serialization.CodeDomSerializerException::.ctor(string message, class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager)
0x1299c3  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x1299c8  br.s     loc_129A3E
0x1299ca  nop
0x1299cb  ldloc.s  0xB
0x1299cd  ldarg.1
0x1299ce  ldloc.1
0x1299cf  callvirt instance object System.ComponentModel.Design.Serialization.CodeDomSerializer::Deserialize(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, object codeObject)
0x1299d4  stloc.s  0xC
0x1299d6  ldloc.s  0xC
0x1299d8  ldnull
0x1299d9  cgt.un
0x1299db  stloc.0
0x1299dc  ldloc.0
0x1299dd  brfalse.s loc_1299ED
0x1299df  ldarg.0
0x1299e0  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_statementsTable
0x1299e5  ldarg.2
0x1299e6  ldloc.s  0xC
0x1299e8  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x1299ed  leave.s  loc_129A3E
0x1299ef  stloc.s  0xD
0x1299f1  ldarg.1
0x1299f2  ldloc.s  0xD
0x1299f4  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager::ReportError(object)
0x1299f9  leave.s  loc_129A3E
0x1299fb  ldloc.1
0x1299fc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x129a01  stloc.s  0xE
0x129a03  br.s     loc_129A1C
0x129a05  ldloc.s  0xE
0x129a07  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x129a0c  castclass [System]System.CodeDom.CodeStatement
0x129a11  stloc.s  0xF
0x129a13  ldarg.0
0x129a14  ldarg.1
0x129a15  ldloc.s  0xF
0x129a17  call     instance void System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeStatement(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, class [System]System.CodeDom.CodeStatement statement)
0x129a1c  ldloc.s  0xE
0x129a1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x129a23  brtrue.s loc_129A05
0x129a25  leave.s  loc_129A3C
0x129a27  ldloc.s  0xE
0x129a29  isinst   [mscorlib]System.IDisposable
0x129a2e  stloc.s  9
0x129a30  ldloc.s  9
0x129a32  brfalse.s loc_129A3B
0x129a34  ldloc.s  9
0x129a36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x129a3b  endfinally
0x129a3c  ldc.i4.1
0x129a3d  stloc.0
0x129a3e  ldloc.2
0x129a3f  brfalse.s loc_129A51
0x129a41  ldloc.2
0x129a42  ldc.i4.2
0x129a43  ldelem.ref
0x129a44  brfalse.s loc_129A51
0x129a46  ldarg.0
0x129a47  ldarg.1
0x129a48  ldarg.2
0x129a49  ldloc.2
0x129a4a  ldc.i4.2
0x129a4b  ldelem.ref
0x129a4c  call     instance void ComponentListCodeDomSerializer::DeserializeDefaultProperties(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, object state)
0x129a51  ldloc.2
0x129a52  brfalse.s loc_129A64
0x129a54  ldloc.2
0x129a55  ldc.i4.3
0x129a56  ldelem.ref
0x129a57  brfalse.s loc_129A64
0x129a59  ldarg.0
0x129a5a  ldarg.1
0x129a5b  ldarg.2
0x129a5c  ldloc.2
0x129a5d  ldc.i4.3
0x129a5e  ldelem.ref
0x129a5f  call     instance void ComponentListCodeDomSerializer::DeserializeDesignTimeProperties(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, object state)
0x129a64  ldloc.2
0x129a65  brfalse.s loc_129A77
0x129a67  ldloc.2
0x129a68  ldc.i4.4
0x129a69  ldelem.ref
0x129a6a  brfalse.s loc_129A77
0x129a6c  ldarg.0
0x129a6d  ldarg.1
0x129a6e  ldarg.2
0x129a6f  ldloc.2
0x129a70  ldc.i4.4
0x129a71  ldelem.ref
0x129a72  call     instance void ComponentListCodeDomSerializer::DeserializeEventResets(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, object state)
0x129a77  ldloc.2
0x129a78  brfalse.s loc_129A89
0x129a7a  ldloc.2
0x129a7b  ldc.i4.5
0x129a7c  ldelem.ref
0x129a7d  brfalse.s loc_129A89
0x129a7f  ldarg.1
0x129a80  ldarg.2
0x129a81  ldloc.2
0x129a82  ldc.i4.5
0x129a83  ldelem.ref
0x129a84  call     void ComponentListCodeDomSerializer::DeserializeModifier(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, object state)
0x129a89  ldarg.0
0x129a8a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> ComponentListCodeDomSerializer::_expressions
0x129a8f  ldarg.2
0x129a90  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::ContainsKey(var<u1>)
0x129a95  brfalse  loc_129C29
0x129a9a  ldarg.0
0x129a9b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> ComponentListCodeDomSerializer::_expressions
0x129aa0  ldarg.2
0x129aa1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Item(void)
0x129aa6  stloc.s  0x10
0x129aa8  ldloc.s  0x10
0x129aaa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x129aaf  stloc.s  0x11
0x129ab1  br.s     loc_129ACD
0x129ab3  ldloc.s  0x11
0x129ab5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x129aba  castclass [System]System.CodeDom.CodeExpression
0x129abf  stloc.s  0x12
0x129ac1  ldarg.0
0x129ac2  ldarg.1
0x129ac3  ldarg.2
0x129ac4  ldloc.s  0x12
0x129ac6  call     instance object System.ComponentModel.Design.Serialization.CodeDomSerializerBase::DeserializeExpression(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager manager, string name, class [System]System.CodeDom.CodeExpression expression)
0x129acb  stloc.s  0x13
0x129acd  ldloc.s  0x11
0x129acf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x129ad4  brtrue.s loc_129AB3
0x129ad6  leave.s  loc_129AED
0x129ad8  ldloc.s  0x11
0x129ada  isinst   [mscorlib]System.IDisposable
0x129adf  stloc.s  9
0x129ae1  ldloc.s  9
0x129ae3  brfalse.s loc_129AEC
0x129ae5  ldloc.s  9
0x129ae7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x129aec  endfinally
0x129aed  ldarg.0
0x129aee  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> ComponentListCodeDomSerializer::_expressions
0x129af3  ldarg.2
0x129af4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::Remove(var<u1>)
0x129af9  pop
0x129afa  ldc.i4.1
0x129afb  stloc.0
0x129afc  br       loc_129C29
0x129b01  ldarg.0
0x129b02  ldfld    class [mscorlib]System.Collections.Hashtable ComponentListCodeDomSerializer::_statementsTable
0x129b07  ldarg.2
0x129b08  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x129b0d  ldnull
0x129b0e  cgt.un
0x129b10  stloc.0
0x129b11  ldloc.0
0x129b12  brtrue   loc_129C00
0x129b17  ldarg.0
0x129b18  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> ComponentListCodeDomSerializer::_expressions
0x129b1d  ldarg.2
0x129b1e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::ContainsKey(var<u1>)
0x129b23  brfalse.s loc_129B96
0x129b25  ldarg.0
0x129b26  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList> ComponentListCodeDomSerializer::_expressions
0x129b2b  ldarg.2
0x129b2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ArrayList>::get_Item(void)
0x129b31  stloc.s  0x14
0x129b33  ldloc.s  0x14
0x129b35  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
  ... truncated ...
```
