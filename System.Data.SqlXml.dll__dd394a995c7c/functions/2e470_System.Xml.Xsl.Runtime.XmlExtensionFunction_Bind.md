# System.Xml.Xsl.Runtime.XmlExtensionFunction::Bind

- ea: `0x2e470`
- end: `0x2e619`
- name: `System.Xml.Xsl.Runtime.XmlExtensionFunction::Bind`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x2e270`

## callees

- `0x3780`
- `0x2e470`
- `0x2e620`

## string_xrefs

- `0x2e4df`: `XmlIl_AmbiguousExtensionMethod`
- `0x2e57f`: `XmlIl_NonPublicExtensionMethod`
- `0x2e5b0`: `XmlIl_NoExtensionMethod`
- `0x2e5ee`: `XmlIl_GenericExtensionMethod`

## pseudocode

```c

```

## disassembly

```asm
0x2e470  ldarg.0
0x2e471  ldfld    class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::objectType
0x2e476  ldarg.0
0x2e477  ldfld    valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Xsl.Runtime.XmlExtensionFunction::flags
0x2e47c  callvirt instance class [mscorlib]System.Reflection.MethodInfo[] [mscorlib]System.Type::GetMethods(valuetype [mscorlib]System.Reflection.BindingFlags)
0x2e481  stloc.0
0x2e482  ldnull
0x2e483  stloc.1
0x2e484  ldarg.0
0x2e485  ldfld    valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Xsl.Runtime.XmlExtensionFunction::flags
0x2e48a  ldc.i4.1
0x2e48b  and
0x2e48c  ldc.i4.0
0x2e48d  cgt.un
0x2e48f  stloc.2
0x2e490  ldloc.2
0x2e491  brtrue.s loc_2E496
0x2e493  ldc.i4.4
0x2e494  br.s     loc_2E497
0x2e496  ldc.i4.5
0x2e497  stloc.3
0x2e498  ldloc.0
0x2e499  stloc.s  4
0x2e49b  ldc.i4.0
0x2e49c  stloc.s  5
0x2e49e  br.s     loc_2E51E
0x2e4a0  ldloc.s  4
0x2e4a2  ldloc.s  5
0x2e4a4  ldelem.ref
0x2e4a5  stloc.s  6
0x2e4a7  ldloc.s  6
0x2e4a9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2e4ae  ldarg.0
0x2e4af  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e4b4  ldloc.3
0x2e4b5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e4ba  brfalse.s loc_2E518
0x2e4bc  ldarg.0
0x2e4bd  ldfld    int32 System.Xml.Xsl.Runtime.XmlExtensionFunction::numArgs
0x2e4c2  ldc.i4.m1
0x2e4c3  beq.s    loc_2E4D6
0x2e4c5  ldloc.s  6
0x2e4c7  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x2e4cc  ldlen
0x2e4cd  conv.i4
0x2e4ce  ldarg.0
0x2e4cf  ldfld    int32 System.Xml.Xsl.Runtime.XmlExtensionFunction::numArgs
0x2e4d4  bne.un.s loc_2E518
0x2e4d6  ldloc.1
0x2e4d7  ldnull
0x2e4d8  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2e4dd  brfalse.s loc_2E515
0x2e4df  ldstr    aXmlilAmbiguous// "XmlIl_AmbiguousExtensionMethod"
0x2e4e4  ldc.i4.3
0x2e4e5  newarr   [mscorlib]System.String
0x2e4ea  dup
0x2e4eb  ldc.i4.0
0x2e4ec  ldarg.0
0x2e4ed  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::namespaceUri
0x2e4f2  stelem.ref
0x2e4f3  dup
0x2e4f4  ldc.i4.1
0x2e4f5  ldarg.0
0x2e4f6  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e4fb  stelem.ref
0x2e4fc  dup
0x2e4fd  ldc.i4.2
0x2e4fe  ldarg.0
0x2e4ff  ldflda   int32 System.Xml.Xsl.Runtime.XmlExtensionFunction::numArgs
0x2e504  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e509  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2e50e  stelem.ref
0x2e50f  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2e514  throw
0x2e515  ldloc.s  6
0x2e517  stloc.1
0x2e518  ldloc.s  5
0x2e51a  ldc.i4.1
0x2e51b  add
0x2e51c  stloc.s  5
0x2e51e  ldloc.s  5
0x2e520  ldloc.s  4
0x2e522  ldlen
0x2e523  conv.i4
0x2e524  blt      loc_2E4A0
0x2e529  ldloc.1
0x2e52a  ldnull
0x2e52b  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2e530  brfalse  loc_2E5E6
0x2e535  ldarg.0
0x2e536  ldfld    class [mscorlib]System.Type System.Xml.Xsl.Runtime.XmlExtensionFunction::objectType
0x2e53b  ldarg.0
0x2e53c  ldfld    valuetype [mscorlib]System.Reflection.BindingFlags System.Xml.Xsl.Runtime.XmlExtensionFunction::flags
0x2e541  ldc.i4.s 0x20
0x2e543  or
0x2e544  callvirt instance class [mscorlib]System.Reflection.MethodInfo[] [mscorlib]System.Type::GetMethods(valuetype [mscorlib]System.Reflection.BindingFlags)
0x2e549  stloc.0
0x2e54a  ldloc.0
0x2e54b  stloc.s  7
0x2e54d  ldc.i4.0
0x2e54e  stloc.s  8
0x2e550  br.s     loc_2E5A8
0x2e552  ldloc.s  7
0x2e554  ldloc.s  8
0x2e556  ldelem.ref
0x2e557  stloc.s  9
0x2e559  ldloc.s  9
0x2e55b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2e560  ldarg.0
0x2e561  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e566  ldloc.3
0x2e567  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e56c  brfalse.s loc_2E5A2
0x2e56e  ldloc.s  9
0x2e570  callvirt instance class [mscorlib]System.Reflection.ParameterInfo[] [mscorlib]System.Reflection.MethodBase::GetParameters()
0x2e575  ldlen
0x2e576  conv.i4
0x2e577  ldarg.0
0x2e578  ldfld    int32 System.Xml.Xsl.Runtime.XmlExtensionFunction::numArgs
0x2e57d  bne.un.s loc_2E5A2
0x2e57f  ldstr    aXmlilNonpublic// "XmlIl_NonPublicExtensionMethod"
0x2e584  ldc.i4.2
0x2e585  newarr   [mscorlib]System.String
0x2e58a  dup
0x2e58b  ldc.i4.0
0x2e58c  ldarg.0
0x2e58d  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::namespaceUri
0x2e592  stelem.ref
0x2e593  dup
0x2e594  ldc.i4.1
0x2e595  ldarg.0
0x2e596  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e59b  stelem.ref
0x2e59c  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2e5a1  throw
0x2e5a2  ldloc.s  8
0x2e5a4  ldc.i4.1
0x2e5a5  add
0x2e5a6  stloc.s  8
0x2e5a8  ldloc.s  8
0x2e5aa  ldloc.s  7
0x2e5ac  ldlen
0x2e5ad  conv.i4
0x2e5ae  blt.s    loc_2E552
0x2e5b0  ldstr    aXmlilNoextensi// "XmlIl_NoExtensionMethod"
0x2e5b5  ldc.i4.3
0x2e5b6  newarr   [mscorlib]System.String
0x2e5bb  dup
0x2e5bc  ldc.i4.0
0x2e5bd  ldarg.0
0x2e5be  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::namespaceUri
0x2e5c3  stelem.ref
0x2e5c4  dup
0x2e5c5  ldc.i4.1
0x2e5c6  ldarg.0
0x2e5c7  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e5cc  stelem.ref
0x2e5cd  dup
0x2e5ce  ldc.i4.2
0x2e5cf  ldarg.0
0x2e5d0  ldflda   int32 System.Xml.Xsl.Runtime.XmlExtensionFunction::numArgs
0x2e5d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e5da  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2e5df  stelem.ref
0x2e5e0  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2e5e5  throw
0x2e5e6  ldloc.1
0x2e5e7  callvirt instance bool [mscorlib]System.Reflection.MethodBase::get_IsGenericMethodDefinition()
0x2e5ec  brfalse.s loc_2E611
0x2e5ee  ldstr    aXmlilGenericex// "XmlIl_GenericExtensionMethod"
0x2e5f3  ldc.i4.2
0x2e5f4  newarr   [mscorlib]System.String
0x2e5f9  dup
0x2e5fa  ldc.i4.0
0x2e5fb  ldarg.0
0x2e5fc  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::namespaceUri
0x2e601  stelem.ref
0x2e602  dup
0x2e603  ldc.i4.1
0x2e604  ldarg.0
0x2e605  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e60a  stelem.ref
0x2e60b  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2e610  throw
0x2e611  ldarg.0
0x2e612  ldloc.1
0x2e613  call     instance void System.Xml.Xsl.Runtime.XmlExtensionFunction::Bind(class [mscorlib]System.Reflection.MethodInfo meth)
0x2e618  ret
```
