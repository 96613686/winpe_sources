# System.Xml.Xsl.IlGen.XmlILModule::.ctor_0

- ea: `0x42430`
- end: `0x4250a`
- name: `System.Xml.Xsl.IlGen.XmlILModule::.ctor_0`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x940`

## callees

- `0x42430`
- `0x42880`

## string_xrefs

- `0x424cc`: `System.Xml.Xsl.CompiledQuery`
- `0x424eb`: `System.Xml.Xsl.CompiledQuery`
- `0x424f9`: `System.Xml.Xsl.CompiledQuery.Query`

## pseudocode

```c

```

## disassembly

```asm
0x42430  ldarg.0
0x42431  call     instance void [mscorlib]System.Object::.ctor()
0x42436  ldarg.0
0x42437  ldarg.1
0x42438  stfld    bool System.Xml.Xsl.IlGen.XmlILModule::useLRE
0x4243d  ldarg.0
0x4243e  ldarg.2
0x4243f  stfld    bool System.Xml.Xsl.IlGen.XmlILModule::emitSymbols
0x42444  ldarg.0
0x42445  ldc.i4.0
0x42446  stfld    bool System.Xml.Xsl.IlGen.XmlILModule::persistAsm
0x4244b  ldarg.0
0x4244c  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x42451  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.IlGen.XmlILModule::methods
0x42456  ldarg.1
0x42457  brtrue   loc_42509
0x4245c  call     class [mscorlib]System.Reflection.AssemblyName System.Xml.Xsl.IlGen.XmlILModule::CreateAssemblyName()
0x42461  stloc.0
0x42462  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x42467  ldloc.0
0x42468  ldarg.0
0x42469  ldfld    bool System.Xml.Xsl.IlGen.XmlILModule::persistAsm
0x4246e  brtrue.s loc_42473
0x42470  ldc.i4.1
0x42471  br.s     loc_42474
0x42473  ldc.i4.3
0x42474  callvirt instance class [mscorlib]System.Reflection.Emit.AssemblyBuilder [mscorlib]System.AppDomain::DefineDynamicAssembly(class [mscorlib]System.Reflection.AssemblyName, valuetype [mscorlib]System.Reflection.Emit.AssemblyBuilderAccess)
0x42479  stloc.1
0x4247a  ldloc.1
0x4247b  ldsfld   class [mscorlib]System.Reflection.ConstructorInfo System.Xml.Xsl.IlGen.XmlILConstructors::Transparent
0x42480  ldc.i4.0
0x42481  newarr   [mscorlib]System.Object
0x42486  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x4248b  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x42490  ldarg.2
0x42491  brfalse.s loc_424C3
0x42493  ldarg.0
0x42494  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x42499  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.IlGen.XmlILModule::urlToSymWriter
0x4249e  ldc.i4   0x103
0x424a3  stloc.3
0x424a4  ldloc.1
0x424a5  ldsfld   class [mscorlib]System.Reflection.ConstructorInfo System.Xml.Xsl.IlGen.XmlILConstructors::Debuggable
0x424aa  ldc.i4.1
0x424ab  newarr   [mscorlib]System.Object
0x424b0  dup
0x424b1  ldc.i4.0
0x424b2  ldloc.3
0x424b3  box      [mscorlib]System.Diagnostics.DebuggableAttribute/DebuggingModes
0x424b8  stelem.ref
0x424b9  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x424be  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x424c3  ldarg.0
0x424c4  ldfld    bool System.Xml.Xsl.IlGen.XmlILModule::persistAsm
0x424c9  brfalse.s loc_424EA
0x424cb  ldloc.1
0x424cc  ldstr    aSystemXmlXslCo// "System.Xml.Xsl.CompiledQuery"
0x424d1  ldarg.0
0x424d2  ldfld    string System.Xml.Xsl.IlGen.XmlILModule::modFile
0x424d7  ldstr    aDll// ".dll"
0x424dc  call     string [mscorlib]System.String::Concat(string, string)
0x424e1  ldarg.2
0x424e2  callvirt instance class [mscorlib]System.Reflection.Emit.ModuleBuilder [mscorlib]System.Reflection.Emit.AssemblyBuilder::DefineDynamicModule(string, string, bool)
0x424e7  stloc.2
0x424e8  br.s     loc_424F7
0x424ea  ldloc.1
0x424eb  ldstr    aSystemXmlXslCo// "System.Xml.Xsl.CompiledQuery"
0x424f0  ldarg.2
0x424f1  callvirt instance class [mscorlib]System.Reflection.Emit.ModuleBuilder [mscorlib]System.Reflection.Emit.AssemblyBuilder::DefineDynamicModule(string, bool)
0x424f6  stloc.2
0x424f7  ldarg.0
0x424f8  ldloc.2
0x424f9  ldstr    aSystemXmlXslCo_0// "System.Xml.Xsl.CompiledQuery.Query"
0x424fe  ldc.i4.1
0x424ff  callvirt instance class [mscorlib]System.Reflection.Emit.TypeBuilder [mscorlib]System.Reflection.Emit.ModuleBuilder::DefineType(string, valuetype [mscorlib]System.Reflection.TypeAttributes)
0x42504  stfld    class [mscorlib]System.Reflection.Emit.TypeBuilder System.Xml.Xsl.IlGen.XmlILModule::typeBldr
0x42509  ret
```
