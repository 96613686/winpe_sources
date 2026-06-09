# System.Xml.Serialization.Compiler::Compile

- ea: `0x67370`
- end: `0x67611`
- name: `System.Xml.Serialization.Compiler::Compile`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x66150`

## callees

- `0x622f0`
- `0x62370`
- `0x66b60`
- `0x66e40`
- `0x66e50`
- `0x67060`
- `0x67250`
- `0x67370`
- `0x67620`
- `0x67670`

## string_xrefs

- `0x67483`: ` /D:_DYNAMIC_XMLSERIALIZER_COMPILATION`
- `0x674da`: `XmlCompilerError`
- `0x675af`: `XmlSerializerAccessDenied`
- `0x675bf`: `XmlIdentityAccessDenied`
- `0x675dc`: `XmlSerializerCompileFailed`
- `0x675fe`: `XmlInternalError`

## pseudocode

```c

```

## disassembly

```asm
0x67370  newobj   instance void [System]Microsoft.CSharp.CSharpCodeProvider::.ctor()
0x67375  stloc.0
0x67376  ldarg.3
0x67377  callvirt instance class [System]System.CodeDom.Compiler.CompilerParameters System.Xml.Serialization.XmlSerializerCompilerParameters::get_CodeDomParameters()
0x6737c  stloc.1
0x6737d  ldloc.1
0x6737e  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x67383  ldarg.0
0x67384  call     instance string[] System.Xml.Serialization.Compiler::get_Imports()
0x67389  callvirt instance void [System]System.Collections.Specialized.StringCollection::AddRange(string[])
0x6738e  ldarg.0
0x6738f  ldfld    bool System.Xml.Serialization.Compiler::debugEnabled
0x67394  brfalse.s loc_673B0
0x67396  ldloc.1
0x67397  ldc.i4.0
0x67398  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateInMemory(bool)
0x6739d  ldloc.1
0x6739e  ldc.i4.1
0x6739f  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_IncludeDebugInformation(bool)
0x673a4  ldloc.1
0x673a5  callvirt instance class [System]System.CodeDom.Compiler.TempFileCollection [System]System.CodeDom.Compiler.CompilerParameters::get_TempFiles()
0x673aa  ldc.i4.1
0x673ab  callvirt instance void [System]System.CodeDom.Compiler.TempFileCollection::set_KeepFiles(bool)
0x673b0  ldc.i4.0
0x673b1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x673b6  stloc.2
0x673b7  ldarg.3
0x673b8  callvirt instance bool System.Xml.Serialization.XmlSerializerCompilerParameters::get_IsNeedTempDirAccess()
0x673bd  brfalse.s loc_673CB
0x673bf  ldloc.2
0x673c0  call     class [mscorlib]System.Security.Permissions.FileIOPermission System.Xml.Serialization.TempAssembly::get_FileIOPermission()
0x673c5  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x673ca  pop
0x673cb  ldloc.2
0x673cc  ldc.i4.1
0x673cd  newobj   instance void [mscorlib]System.Security.Permissions.EnvironmentPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x673d2  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x673d7  pop
0x673d8  ldloc.2
0x673d9  ldc.i4.2
0x673da  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x673df  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x673e4  pop
0x673e5  ldloc.2
0x673e6  ldc.i4.s 0x20
0x673e8  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x673ed  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x673f2  pop
0x673f3  ldloc.2
0x673f4  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x673f9  ldarg.1
0x673fa  ldnull
0x673fb  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x67400  brfalse.s loc_67444
0x67402  ldloc.1
0x67403  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_OutputAssembly()
0x67408  brfalse.s loc_67417
0x6740a  ldloc.1
0x6740b  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_OutputAssembly()
0x67410  callvirt instance int32 [mscorlib]System.String::get_Length()
0x67415  brtrue.s loc_67444
0x67417  ldloc.1
0x67418  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x6741d  call     string System.Xml.Serialization.Compiler::AssemblyNameFromOptions(string options)
0x67422  stloc.s  5
0x67424  ldloc.s  5
0x67426  brtrue.s loc_6743C
0x67428  ldloc.1
0x67429  callvirt instance class [System]System.CodeDom.Compiler.TempFileCollection [System]System.CodeDom.Compiler.CompilerParameters::get_TempFiles()
0x6742e  callvirt instance string [System]System.CodeDom.Compiler.TempFileCollection::get_TempDir()
0x67433  ldarg.1
0x67434  ldarg.2
0x67435  call     string System.Xml.Serialization.Compiler::GetTempAssemblyPath(string baseDir, class [mscorlib]System.Reflection.Assembly assembly, string defaultNamespace)
0x6743a  stloc.s  5
0x6743c  ldloc.1
0x6743d  ldloc.s  5
0x6743f  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_OutputAssembly(string)
0x67444  ldloc.1
0x67445  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x6744a  brfalse.s loc_67459
0x6744c  ldloc.1
0x6744d  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x67452  callvirt instance int32 [mscorlib]System.String::get_Length()
0x67457  brtrue.s loc_67466
0x67459  ldloc.1
0x6745a  ldstr    aNostdlib// "/nostdlib"
0x6745f  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0x67464  br.s     loc_6747C
0x67466  ldloc.1
0x67467  dup
0x67468  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x6746d  ldstr    aNostdlib_0// " /nostdlib"
0x67472  call     string [mscorlib]System.String::Concat(string, string)
0x67477  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0x6747c  ldloc.1
0x6747d  dup
0x6747e  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x67483  ldstr    aDDynamicXmlser// " /D:_DYNAMIC_XMLSERIALIZER_COMPILATION"
0x67488  call     string [mscorlib]System.String::Concat(string, string)
0x6748d  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0x67492  ldloc.1
0x67493  ldarg.s  4
0x67495  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_Evidence(class [mscorlib]System.Security.Policy.Evidence)
0x6749a  ldnull
0x6749b  stloc.3
0x6749c  ldnull
0x6749d  stloc.s  4
0x6749f  ldloc.0
0x674a0  ldloc.1
0x674a1  ldc.i4.1
0x674a2  newarr   [mscorlib]System.String
0x674a7  dup
0x674a8  ldc.i4.0
0x674a9  ldarg.0
0x674aa  ldfld    class [mscorlib]System.IO.StringWriter System.Xml.Serialization.Compiler::writer
0x674af  callvirt instance string [mscorlib]System.Object::ToString()
0x674b4  stelem.ref
0x674b5  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults [System]System.CodeDom.Compiler.CodeDomProvider::CompileAssemblyFromSource(class [System]System.CodeDom.Compiler.CompilerParameters, string[])
0x674ba  stloc.3
0x674bb  ldloc.3
0x674bc  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x674c1  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x674c6  ldc.i4.0
0x674c7  ble      loc_67590
0x674cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x674d1  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x674d6  stloc.s  6
0x674d8  ldloc.s  6
0x674da  ldstr    aXmlcompilererr// "XmlCompilerError"
0x674df  ldc.i4.1
0x674e0  newarr   [mscorlib]System.Object
0x674e5  dup
0x674e6  ldc.i4.0
0x674e7  ldloc.3
0x674e8  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerResults::get_NativeCompilerReturnValue()
0x674ed  stloc.s  8
0x674ef  ldloca.s 8
0x674f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x674f6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x674fb  stelem.ref
0x674fc  call     string System.Xml.Res::GetString(string name, object[] args)
0x67501  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x67506  ldc.i4.0
0x67507  stloc.s  7
0x67509  ldloc.3
0x6750a  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x6750f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x67514  stloc.s  9
0x67516  br.s     loc_6755F
0x67518  ldloc.s  9
0x6751a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6751f  castclass [System]System.CodeDom.Compiler.CompilerError
0x67524  stloc.s  0xA
0x67526  ldloc.s  0xA
0x67528  ldstr    asc_1284AE// ""
0x6752d  callvirt instance void [System]System.CodeDom.Compiler.CompilerError::set_FileName(string)
0x67532  ldloc.s  0xA
0x67534  callvirt instance bool [System]System.CodeDom.Compiler.CompilerError::get_IsWarning()
0x67539  brfalse.s loc_6754E
0x6753b  ldloc.s  0xA
0x6753d  callvirt instance string [System]System.CodeDom.Compiler.CompilerError::get_ErrorNumber()
0x67542  ldstr    aCs1595// "CS1595"
0x67547  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6754c  brfalse.s loc_6755F
0x6754e  ldc.i4.1
0x6754f  stloc.s  7
0x67551  ldloc.s  6
0x67553  ldloc.s  0xA
0x67555  callvirt instance string [mscorlib]System.Object::ToString()
0x6755a  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x6755f  ldloc.s  9
0x67561  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x67566  brtrue.s loc_67518
0x67568  leave.s  loc_6757F
0x6756a  ldloc.s  9
0x6756c  isinst   [mscorlib]System.IDisposable
0x67571  stloc.s  0xB
0x67573  ldloc.s  0xB
0x67575  brfalse.s loc_6757E
0x67577  ldloc.s  0xB
0x67579  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6757e  endfinally
0x6757f  ldloc.s  7
0x67581  brfalse.s loc_67590
0x67583  ldloc.s  6
0x67585  callvirt instance string [mscorlib]System.Object::ToString()
0x6758a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6758f  throw
0x67590  ldloc.3
0x67591  callvirt instance class [mscorlib]System.Reflection.Assembly [System]System.CodeDom.Compiler.CompilerResults::get_CompiledAssembly()
0x67596  stloc.s  4
0x67598  leave.s  loc_675F4
0x6759a  pop
0x6759b  call     string System.Xml.Serialization.Compiler::GetCurrentUser()
0x675a0  stloc.s  0xC
0x675a2  ldloc.s  0xC
0x675a4  brfalse.s loc_675AF
0x675a6  ldloc.s  0xC
0x675a8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x675ad  brtrue.s loc_675BF
0x675af  ldstr    aXmlserializera// "XmlSerializerAccessDenied"
0x675b4  call     string System.Xml.Res::GetString(string name)
0x675b9  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x675be  throw
0x675bf  ldstr    aXmlidentityacc// "XmlIdentityAccessDenied"
0x675c4  ldc.i4.1
0x675c5  newarr   [mscorlib]System.Object
0x675ca  dup
0x675cb  ldc.i4.0
0x675cc  ldloc.s  0xC
0x675ce  stelem.ref
0x675cf  call     string System.Xml.Res::GetString(string name, object[] args)
0x675d4  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x675d9  throw
0x675da  stloc.s  0xD
0x675dc  ldstr    aXmlserializerc_0// "XmlSerializerCompileFailed"
0x675e1  call     string System.Xml.Res::GetString(string name)
0x675e6  ldloc.s  0xD
0x675e8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x675ed  throw
0x675ee  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x675f3  endfinally
0x675f4  ldloc.s  4
0x675f6  ldnull
0x675f7  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x675fc  brfalse.s loc_6760E
0x675fe  ldstr    aXmlinternalerr// "XmlInternalError"
0x67603  call     string System.Xml.Res::GetString(string name)
0x67608  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6760d  throw
0x6760e  ldloc.s  4
0x67610  ret
```
