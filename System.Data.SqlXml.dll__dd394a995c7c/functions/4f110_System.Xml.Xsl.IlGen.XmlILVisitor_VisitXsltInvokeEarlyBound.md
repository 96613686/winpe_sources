# System.Xml.Xsl.IlGen.XmlILVisitor::VisitXsltInvokeEarlyBound

- ea: `0x4f110`
- end: `0x4f523`
- name: `System.Xml.Xsl.IlGen.XmlILVisitor::VisitXsltInvokeEarlyBound`
- size: `1043`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config`

## callees

- `0x230`
- `0x1f80`
- `0x2350`
- `0x2370`
- `0x2e2f0`
- `0x2e3a0`
- `0x2e3b0`
- `0x2e3c0`
- `0x2e3d0`
- `0x36fc0`
- `0x36fe0`
- `0x37020`
- `0x374b0`
- `0x374d0`
- `0x376c0`
- `0x37740`
- `0x37750`
- `0x3f060`
- `0x3f070`
- `0x3f150`
- `0x3f180`
- `0x3f1b0`
- `0x3f3e0`
- `0x3f500`
- `0x3f850`
- `0x3ff00`
- `0x3ff10`
- `0x3ff40`
- `0x3ff90`
- `0x3ffd0`
- `0x40020`
- `0x400f0`
- `0x405b0`
- `0x40f50`
- `0x40fa0`
- `0x4f110`
- `0x50700`
- `0x50a70`
- `0x50a80`
- `0x50a90`
- `0x50ab0`

## pseudocode

```c

```

## disassembly

```asm
0x4f110  ldarg.1
0x4f111  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilInvokeEarlyBound::get_Name()
0x4f116  stloc.0
0x4f117  ldloc.0
0x4f118  callvirt instance string System.Xml.Xsl.Qil.QilName::get_LocalName()
0x4f11d  ldloc.0
0x4f11e  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4f123  ldarg.1
0x4f124  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Qil.QilInvokeEarlyBound::get_ClrMethod()
0x4f129  newobj   instance void System.Xml.Xsl.Runtime.XmlExtensionFunction::.ctor(string name, string namespaceUri, class [mscorlib]System.Reflection.MethodInfo meth)
0x4f12e  stloc.1
0x4f12f  ldloc.1
0x4f130  callvirt instance class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::get_ClrReturnType()
0x4f135  stloc.2
0x4f136  ldarg.0
0x4f137  ldarg.1
0x4f138  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4f13d  stloc.3
0x4f13e  ldloc.2
0x4f13f  ldloc.3
0x4f140  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f145  brfalse.s loc_4F180
0x4f147  ldarg.1
0x4f148  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f14d  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsEmpty()
0x4f152  brtrue.s loc_4F180
0x4f154  ldarg.0
0x4f155  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f15a  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4f15f  ldarg.0
0x4f160  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f165  ldarg.0
0x4f166  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f16b  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4f170  ldarg.1
0x4f171  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f176  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareXmlType(class System.Xml.Xsl.XmlQueryType type)
0x4f17b  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4f180  ldloc.1
0x4f181  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XmlExtensionFunction::get_Method()
0x4f186  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsStatic()
0x4f18b  brtrue.s loc_4F1DE
0x4f18d  ldloc.0
0x4f18e  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4f193  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4f198  brtrue.s loc_4F1A7
0x4f19a  ldarg.0
0x4f19b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f1a0  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadXsltLibrary()
0x4f1a5  br.s     loc_4F1DE
0x4f1a7  ldarg.0
0x4f1a8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f1ad  ldarg.0
0x4f1ae  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f1b3  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4f1b8  ldloc.0
0x4f1b9  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4f1be  ldloc.1
0x4f1bf  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XmlExtensionFunction::get_Method()
0x4f1c4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x4f1c9  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareEarlyBound(string namespaceUri, class [mscorlib]System.Type ebType)
0x4f1ce  ldloc.1
0x4f1cf  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XmlExtensionFunction::get_Method()
0x4f1d4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x4f1d9  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallGetEarlyBoundObject(int32 idxObj, class [mscorlib]System.Type clrType)
0x4f1de  ldc.i4.0
0x4f1df  stloc.s  4
0x4f1e1  br       loc_4F3CE
0x4f1e6  ldarg.1
0x4f1e7  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilInvokeEarlyBound::get_Arguments()
0x4f1ec  ldloc.s  4
0x4f1ee  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x4f1f3  stloc.s  5
0x4f1f5  ldloc.1
0x4f1f6  ldloc.s  4
0x4f1f8  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Runtime.XmlExtensionFunction::GetXmlArgumentType(int32 index)
0x4f1fd  stloc.s  6
0x4f1ff  ldloc.1
0x4f200  ldloc.s  4
0x4f202  callvirt instance class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::GetClrArgumentType(int32 index)
0x4f207  stloc.s  8
0x4f209  ldloc.0
0x4f20a  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4f20f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4f214  brtrue   loc_4F2FD
0x4f219  ldarg.0
0x4f21a  ldloc.s  5
0x4f21c  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.Qil.QilNode nd)
0x4f221  stloc.s  9
0x4f223  ldloc.s  8
0x4f225  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x4f22a  ldloc.s  9
0x4f22c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x4f231  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::IListType
0x4f236  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f23b  brfalse.s loc_4F24D
0x4f23d  ldarg.0
0x4f23e  ldloc.s  5
0x4f240  ldloc.s  9
0x4f242  ldc.i4.1
0x4f243  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f248  br       loc_4F3C8
0x4f24d  ldloc.s  8
0x4f24f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x4f254  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4f259  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f25e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x4f263  ldfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILStorageMethods::IListType
0x4f268  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f26d  brfalse.s loc_4F287
0x4f26f  ldarg.0
0x4f270  ldloc.s  5
0x4f272  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4f277  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f27c  ldc.i4.1
0x4f27d  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f282  br       loc_4F3C8
0x4f287  ldloc.s  5
0x4f289  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f28e  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4f293  brfalse.s loc_4F2A0
0x4f295  ldloc.s  8
0x4f297  ldloc.s  9
0x4f299  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f29e  brtrue.s loc_4F2AE
0x4f2a0  ldloc.s  5
0x4f2a2  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f2a7  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x4f2ac  brtrue.s loc_4F2BE
0x4f2ae  ldarg.0
0x4f2af  ldloc.s  5
0x4f2b1  ldloc.s  8
0x4f2b3  ldc.i4.0
0x4f2b4  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f2b9  br       loc_4F3C8
0x4f2be  ldloc.s  5
0x4f2c0  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f2c5  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4f2ca  brfalse  loc_4F3C8
0x4f2cf  ldloc.s  8
0x4f2d1  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4f2d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f2db  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f2e0  brfalse  loc_4F3C8
0x4f2e5  ldarg.0
0x4f2e6  ldloc.s  5
0x4f2e8  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4f2ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f2f2  ldc.i4.0
0x4f2f3  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f2f8  br       loc_4F3C8
0x4f2fd  ldarg.0
0x4f2fe  ldloc.s  6
0x4f300  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetStorageType(class System.Xml.Xsl.XmlQueryType typ)
0x4f305  stloc.s  7
0x4f307  ldloc.s  6
0x4f309  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x4f30e  ldc.i4.1
0x4f30f  beq.s    loc_4F31F
0x4f311  ldloc.s  8
0x4f313  ldloc.s  7
0x4f315  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x4f31a  brtrue   loc_4F3AE
0x4f31f  ldarg.0
0x4f320  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f325  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4f32a  ldarg.0
0x4f32b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f330  ldarg.0
0x4f331  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f336  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x4f33b  ldloc.s  6
0x4f33d  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareXmlType(class System.Xml.Xsl.XmlQueryType type)
0x4f342  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4f347  ldarg.0
0x4f348  ldloc.s  5
0x4f34a  ldarg.0
0x4f34b  ldloc.s  6
0x4f34d  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.XmlQueryType typ)
0x4f352  ldloc.s  6
0x4f354  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4f359  ldc.i4.0
0x4f35a  ceq
0x4f35c  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f361  ldarg.0
0x4f362  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f367  ldloc.s  7
0x4f369  ldtoken  [mscorlib]System.Object
0x4f36e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f373  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TreatAs(class [mscorlib]System.Type clrTypeSrc, class [mscorlib]System.Type clrTypeDst)
0x4f378  ldarg.0
0x4f379  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f37e  ldloc.s  8
0x4f380  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadType(class [mscorlib]System.Type clrTyp)
0x4f385  ldarg.0
0x4f386  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f38b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ChangeTypeXsltArg
0x4f390  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4f395  ldarg.0
0x4f396  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f39b  ldtoken  [mscorlib]System.Object
0x4f3a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f3a5  ldloc.s  8
0x4f3a7  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TreatAs(class [mscorlib]System.Type clrTypeSrc, class [mscorlib]System.Type clrTypeDst)
0x4f3ac  br.s     loc_4F3C8
0x4f3ae  ldarg.0
0x4f3af  ldloc.s  5
0x4f3b1  ldarg.0
0x4f3b2  ldloc.s  6
0x4f3b4  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.XmlILVisitor::GetItemStorageType(class System.Xml.Xsl.XmlQueryType typ)
0x4f3b9  ldloc.s  6
0x4f3bb  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsSingleton()
0x4f3c0  ldc.i4.0
0x4f3c1  ceq
0x4f3c3  call     instance void System.Xml.Xsl.IlGen.XmlILVisitor::NestedVisitEnsureStack(class System.Xml.Xsl.Qil.QilNode nd, class [mscorlib]System.Type itemStorageType, bool isCached)
0x4f3c8  ldloc.s  4
0x4f3ca  ldc.i4.1
0x4f3cb  add
0x4f3cc  stloc.s  4
0x4f3ce  ldloc.s  4
0x4f3d0  ldarg.1
0x4f3d1  callvirt instance class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Qil.QilInvokeEarlyBound::get_Arguments()
0x4f3d6  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x4f3db  blt      loc_4F1E6
0x4f3e0  ldarg.0
0x4f3e1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f3e6  ldloc.1
0x4f3e7  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.Runtime.XmlExtensionFunction::get_Method()
0x4f3ec  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4f3f1  ldarg.1
0x4f3f2  callvirt instance class System.Xml.Xsl.XmlQueryType System.Xml.Xsl.Qil.QilNode::get_XmlType()
0x4f3f7  callvirt instance bool System.Xml.Xsl.XmlQueryType::get_IsEmpty()
0x4f3fc  brfalse.s loc_4F42C
0x4f3fe  ldarg.0
0x4f3ff  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f404  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldsfld
0x4f409  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x4f40e  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x4f413  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f418  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x4f41d  ldfld    class [mscorlib]System.Reflection.FieldInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::SeqEmpty
0x4f422  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.FieldInfo fldInfo)
0x4f427  br       loc_4F4FC
0x4f42c  ldloc.2
0x4f42d  ldloc.3
0x4f42e  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f433  brfalse.s loc_4F476
0x4f435  ldarg.0
0x4f436  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f43b  ldloc.2
0x4f43c  ldtoken  [mscorlib]System.Object
0x4f441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f446  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TreatAs(class [mscorlib]System.Type clrTypeSrc, class [mscorlib]System.Type clrTypeDst)
0x4f44b  ldarg.0
0x4f44c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f451  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ChangeTypeXsltResult
0x4f456  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4f45b  ldarg.0
0x4f45c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f461  ldtoken  [mscorlib]System.Object
0x4f466  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f46b  ldloc.3
0x4f46c  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::TreatAs(class [mscorlib]System.Type clrTypeSrc, class [mscorlib]System.Type clrTypeDst)
0x4f471  br       loc_4F4FC
0x4f476  ldloc.0
0x4f477  callvirt instance string System.Xml.Xsl.Qil.QilName::get_NamespaceUri()
0x4f47c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4f481  brfalse.s loc_4F4FC
0x4f483  ldloc.2
0x4f484  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x4f489  brtrue.s loc_4F4FC
0x4f48b  ldarg.0
0x4f48c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f491  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x4f496  stloc.s  0xA
0x4f498  ldarg.0
0x4f499  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f49e  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Dup
0x4f4a3  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x4f4a8  ldarg.0
0x4f4a9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f4ae  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Brtrue
0x4f4b3  ldloc.s  0xA
0x4f4b5  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4f4ba  ldarg.0
0x4f4bb  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f4c0  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x4f4c5  ldarg.0
0x4f4c6  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f4cb  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldstr
0x4f4d0  ldstr    aXsltItemnull// "Xslt_ItemNull"
0x4f4d5  call     string System.Xml.Utils.Res::GetString(string name)
0x4f4da  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, string strVal)
0x4f4df  ldarg.0
0x4f4e0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f4e5  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ThrowException
0x4f4ea  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4f4ef  ldarg.0
0x4f4f0  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.XmlILVisitor::helper
0x4f4f5  ldloc.s  0xA
  ... truncated ...
```
