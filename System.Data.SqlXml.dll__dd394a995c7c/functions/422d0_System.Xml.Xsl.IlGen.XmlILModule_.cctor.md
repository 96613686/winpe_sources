# System.Xml.Xsl.IlGen.XmlILModule::.cctor

- ea: `0x422d0`
- end: `0x423b7`
- name: `System.Xml.Xsl.IlGen.XmlILModule::.cctor`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x422d0`
- `0x42880`

## string_xrefs

- `0x4239e`: `System.Xml.Xsl.CompiledQuery`

## pseudocode

```c

```

## disassembly

```asm
0x422d0  ldc.i4   0x462D4A3E
0x422d5  ldc.i4   0xB257
0x422da  ldc.i4   0x4AEE
0x422df  ldc.i4   0x97
0x422e4  ldc.i4   0xCD
0x422e9  ldc.i4.s 0x59
0x422eb  ldc.i4.s 0x18
0x422ed  ldc.i4   0xC7
0x422f2  ldc.i4.s 0x53
0x422f4  ldc.i4.s 0x17
0x422f6  ldc.i4.s 0x58
0x422f8  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int32, unsigned int16, unsigned int16, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8)
0x422fd  stsfld   valuetype [mscorlib]System.Guid System.Xml.Xsl.IlGen.XmlILModule::LanguageGuid
0x42302  ldc.i4   0x994B45C4
0x42307  ldc.i4   0xE6E9
0x4230c  ldc.i4   0x11D2
0x42311  ldc.i4   0x90
0x42316  ldc.i4.s 0x3F
0x42318  ldc.i4.0
0x42319  ldc.i4   0xC0
0x4231e  ldc.i4.s 0x4F
0x42320  ldc.i4   0xA3
0x42325  ldc.i4.2
0x42326  ldc.i4   0xA1
0x4232b  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int32, unsigned int16, unsigned int16, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8)
0x42330  stsfld   valuetype [mscorlib]System.Guid System.Xml.Xsl.IlGen.XmlILModule::VendorGuid
0x42335  ldc.i4.0
0x42336  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x4233b  stsfld   class [mscorlib]System.Security.PermissionSet System.Xml.Xsl.IlGen.XmlILModule::CreateModulePermissionSet
0x42340  ldsfld   class [mscorlib]System.Security.PermissionSet System.Xml.Xsl.IlGen.XmlILModule::CreateModulePermissionSet
0x42345  ldc.i4.2
0x42346  newobj   instance void [mscorlib]System.Security.Permissions.ReflectionPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.ReflectionPermissionFlag)
0x4234b  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x42350  pop
0x42351  ldsfld   class [mscorlib]System.Security.PermissionSet System.Xml.Xsl.IlGen.XmlILModule::CreateModulePermissionSet
0x42356  ldc.i4.s 0x22
0x42358  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x4235d  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x42362  pop
0x42363  ldc.i4.0
0x42364  conv.i8
0x42365  stsfld   int64 System.Xml.Xsl.IlGen.XmlILModule::AssemblyId
0x4236a  call     class [mscorlib]System.Reflection.AssemblyName System.Xml.Xsl.IlGen.XmlILModule::CreateAssemblyName()
0x4236f  stloc.0
0x42370  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x42375  ldloc.0
0x42376  ldc.i4.1
0x42377  callvirt instance class [mscorlib]System.Reflection.Emit.AssemblyBuilder [mscorlib]System.AppDomain::DefineDynamicAssembly(class [mscorlib]System.Reflection.AssemblyName, valuetype [mscorlib]System.Reflection.Emit.AssemblyBuilderAccess)
0x4237c  stloc.1
0x4237d  ldsfld   class [mscorlib]System.Security.PermissionSet System.Xml.Xsl.IlGen.XmlILModule::CreateModulePermissionSet
0x42382  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x42387  ldloc.1
0x42388  ldsfld   class [mscorlib]System.Reflection.ConstructorInfo System.Xml.Xsl.IlGen.XmlILConstructors::Transparent
0x4238d  ldc.i4.0
0x4238e  newarr   [mscorlib]System.Object
0x42393  newobj   instance void [mscorlib]System.Reflection.Emit.CustomAttributeBuilder::.ctor(class [mscorlib]System.Reflection.ConstructorInfo, object[])
0x42398  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::SetCustomAttribute(class [mscorlib]System.Reflection.Emit.CustomAttributeBuilder)
0x4239d  ldloc.1
0x4239e  ldstr    aSystemXmlXslCo// "System.Xml.Xsl.CompiledQuery"
0x423a3  ldc.i4.0
0x423a4  callvirt instance class [mscorlib]System.Reflection.Emit.ModuleBuilder [mscorlib]System.Reflection.Emit.AssemblyBuilder::DefineDynamicModule(string, bool)
0x423a9  stsfld   class [mscorlib]System.Reflection.Emit.ModuleBuilder System.Xml.Xsl.IlGen.XmlILModule::LREModule
0x423ae  leave.s  loc_423B6
0x423b0  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x423b5  endfinally
0x423b6  ret
```
