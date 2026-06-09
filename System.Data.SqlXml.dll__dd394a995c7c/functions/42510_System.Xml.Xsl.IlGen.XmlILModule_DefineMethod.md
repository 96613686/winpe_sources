# System.Xml.Xsl.IlGen.XmlILModule::DefineMethod

- ea: `0x42510`
- end: `0x426a0`
- name: `System.Xml.Xsl.IlGen.XmlILModule::DefineMethod`
- size: `400`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x940`
- `0xb90`
- `0xcd0`
- `0xdb0`

## callees

- `0x42510`

## string_xrefs

- `0x425d6`: `{urn:schemas-microsoft-com:xslt-debug}runtime`
- `0x42644`: `{urn:schemas-microsoft-com:xslt-debug}runtime`

## pseudocode

```c

```

## disassembly

```asm
0x42510  ldc.i4.1
0x42511  stloc.1
0x42512  ldarg.1
0x42513  stloc.2
0x42514  ldarg.s  5
0x42516  ldc.i4.2
0x42517  and
0x42518  ldc.i4.0
0x42519  cgt.un
0x4251b  stloc.s  4
0x4251d  br.s     loc_4253C
0x4251f  ldloc.1
0x42520  ldc.i4.1
0x42521  add
0x42522  stloc.1
0x42523  ldloc.2
0x42524  ldstr    asc_5EA1C// " ("
0x42529  ldloca.s 1
0x4252b  call     instance string [mscorlib]System.Int32::ToString()
0x42530  ldstr    asc_58714// ")"
0x42535  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4253a  starg.s  1
0x4253c  ldarg.0
0x4253d  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.IlGen.XmlILModule::methods
0x42542  ldarg.1
0x42543  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x42548  brtrue.s loc_4251F
0x4254a  ldloc.s  4
0x4254c  brtrue.s loc_42575
0x4254e  ldarg.3
0x4254f  ldlen
0x42550  conv.i4
0x42551  ldc.i4.1
0x42552  add
0x42553  newarr   [mscorlib]System.Type
0x42558  stloc.3
0x42559  ldloc.3
0x4255a  ldc.i4.0
0x4255b  ldtoken  System.Xml.Xsl.Runtime.XmlQueryRuntime
0x42560  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x42565  stelem.ref
0x42566  ldarg.3
0x42567  ldc.i4.0
0x42568  ldloc.3
0x42569  ldc.i4.1
0x4256a  ldarg.3
0x4256b  ldlen
0x4256c  conv.i4
0x4256d  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x42572  ldloc.3
0x42573  starg.s  3
0x42575  ldarg.0
0x42576  ldfld    bool System.Xml.Xsl.IlGen.XmlILModule::useLRE
0x4257b  brtrue   loc_42625
0x42580  ldarg.0
0x42581  ldfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Xsl.IlGen.XmlILModule::typeBldr
0x42586  ldarg.1
0x42587  ldc.i4.s 0x11
0x42589  ldarg.2
0x4258a  ldarg.3
0x4258b  callvirt instance class [mscorlib]System.Reflection.Emit.MethodBuilder [mscorlib]System.Reflection.Emit.TypeBuilder::DefineMethod(string, valuetype [mscorlib]System.Reflection.MethodAttributes, class [mscorlib]System.Type, class [mscorlib]System.Type[])
0x42590  stloc.s  5
0x42592  ldarg.0
0x42593  ldfld    bool System.Xml.Xsl.IlGen.XmlILModule::emitSymbols
0x42598  brfalse.s loc_425CE
0x4259a  ldarg.s  5
0x4259c  ldc.i4.1
0x4259d  and
0x4259e  brfalse.s loc_425CE
0x425a0  ldloc.s  5
0x425a2  ldsfld   class [mscorlib]System.Reflection.ConstructorInfo System.Xml.Xsl.IlGen.XmlILConstructors::StepThrough
0x425a7  ldc.i4.0
0x425a8  newarr   [mscorlib]System.Object
0x425ad  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x425b2  callvirt instance void [mscorlib]System.Reflection.Emit.MethodBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x425b7  ldloc.s  5
0x425b9  ldsfld   class [mscorlib]System.Reflection.ConstructorInfo System.Xml.Xsl.IlGen.XmlILConstructors::NonUserCode
0x425be  ldc.i4.0
0x425bf  newarr   [mscorlib]System.Object
0x425c4  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x425c9  callvirt instance void [mscorlib]System.Reflection.Emit.MethodBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x425ce  ldloc.s  4
0x425d0  brtrue.s loc_425E1
0x425d2  ldloc.s  5
0x425d4  ldc.i4.1
0x425d5  ldc.i4.0
0x425d6  ldstr    aUrnSchemasMicr_1// "{urn:schemas-microsoft-com:xslt-debug}r"...
0x425db  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.MethodBuilder::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x425e0  pop
0x425e1  ldc.i4.0
0x425e2  stloc.s  6
0x425e4  br.s     loc_42618
0x425e6  ldarg.s  4
0x425e8  ldloc.s  6
0x425ea  ldelem.ref
0x425eb  brfalse.s loc_42612
0x425ed  ldarg.s  4
0x425ef  ldloc.s  6
0x425f1  ldelem.ref
0x425f2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x425f7  brfalse.s loc_42612
0x425f9  ldloc.s  5
0x425fb  ldloc.s  6
0x425fd  ldloc.s  4
0x425ff  brtrue.s loc_42604
0x42601  ldc.i4.2
0x42602  br.s     loc_42605
0x42604  ldc.i4.1
0x42605  add
0x42606  ldc.i4.0
0x42607  ldarg.s  4
0x42609  ldloc.s  6
0x4260b  ldelem.ref
0x4260c  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.MethodBuilder::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x42611  pop
0x42612  ldloc.s  6
0x42614  ldc.i4.1
0x42615  add
0x42616  stloc.s  6
0x42618  ldloc.s  6
0x4261a  ldarg.s  4
0x4261c  ldlen
0x4261d  conv.i4
0x4261e  blt.s    loc_425E6
0x42620  ldloc.s  5
0x42622  stloc.0
0x42623  br.s     loc_42691
0x42625  ldarg.1
0x42626  ldarg.2
0x42627  ldarg.3
0x42628  ldsfld   class [mscorlib]System.Reflection.Emit.ModuleBuilder System.Xml.Xsl.IlGen.XmlILModule::LREModule
0x4262d  newobj   instance void [mscorlib]System.Reflection.Emit.DynamicMethod::.ctor(string, class [mscorlib]System.Type, class [mscorlib]System.Type[], class [mscorlib]System.Reflection.Module)
0x42632  stloc.s  7
0x42634  ldloc.s  7
0x42636  ldc.i4.1
0x42637  callvirt instance void [mscorlib]System.Reflection.Emit.DynamicMethod::set_InitLocals(bool)
0x4263c  ldloc.s  4
0x4263e  brtrue.s loc_4264F
0x42640  ldloc.s  7
0x42642  ldc.i4.1
0x42643  ldc.i4.0
0x42644  ldstr    aUrnSchemasMicr_1// "{urn:schemas-microsoft-com:xslt-debug}r"...
0x42649  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x4264e  pop
0x4264f  ldc.i4.0
0x42650  stloc.s  8
0x42652  br.s     loc_42686
0x42654  ldarg.s  4
0x42656  ldloc.s  8
0x42658  ldelem.ref
0x42659  brfalse.s loc_42680
0x4265b  ldarg.s  4
0x4265d  ldloc.s  8
0x4265f  ldelem.ref
0x42660  callvirt instance int32 [mscorlib]System.String::get_Length()
0x42665  brfalse.s loc_42680
0x42667  ldloc.s  7
0x42669  ldloc.s  8
0x4266b  ldloc.s  4
0x4266d  brtrue.s loc_42672
0x4266f  ldc.i4.2
0x42670  br.s     loc_42673
0x42672  ldc.i4.1
0x42673  add
0x42674  ldc.i4.0
0x42675  ldarg.s  4
0x42677  ldloc.s  8
0x42679  ldelem.ref
0x4267a  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x4267f  pop
0x42680  ldloc.s  8
0x42682  ldc.i4.1
0x42683  add
0x42684  stloc.s  8
0x42686  ldloc.s  8
0x42688  ldarg.s  4
0x4268a  ldlen
0x4268b  conv.i4
0x4268c  blt.s    loc_42654
0x4268e  ldloc.s  7
0x42690  stloc.0
0x42691  ldarg.0
0x42692  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.IlGen.XmlILModule::methods
0x42697  ldarg.1
0x42698  ldloc.0
0x42699  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x4269e  ldloc.0
0x4269f  ret
```
