# Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::InternalCompile

- ea: `0x152db0`
- end: `0x152efd`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::InternalCompile`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x232b10`

## callees

- `0x11b330`
- `0x11b370`
- `0x11b380`
- `0x130e70`
- `0x149290`
- `0x14c7a0`
- `0x14c820`
- `0x14d030`
- `0x14d070`
- `0x152db0`
- `0x152f00`
- `0x152fd0`
- `0x152fe0`

## string_xrefs

- `0x152dcc`: `{0}{1}.dll`
- `0x152e06`: `System.dll`

## pseudocode

```c

```

## disassembly

```asm
0x152db0  ldarg.0
0x152db1  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_builder
0x152db6  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::get_HasExpressions()
0x152dbb  brfalse  loc_152EF6
0x152dc0  newobj   instance void [System]System.CodeDom.Compiler.CompilerParameters::.ctor()
0x152dc5  stloc.0
0x152dc6  ldloc.0
0x152dc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x152dcc  ldstr    a01Dll// "{0}{1}.dll"
0x152dd1  call     string [mscorlib]System.IO.Path::GetTempPath()
0x152dd6  ldarg.0
0x152dd7  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_expressionHostAssemblyHolder
0x152ddc  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_ExprHostAssemblyName()
0x152de1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x152de6  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_OutputAssembly(string)
0x152deb  ldloc.0
0x152dec  ldc.i4.0
0x152ded  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateExecutable(bool)
0x152df2  ldloc.0
0x152df3  ldc.i4.0
0x152df4  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateInMemory(bool)
0x152df9  ldloc.0
0x152dfa  ldc.i4.0
0x152dfb  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_IncludeDebugInformation(bool)
0x152e00  ldloc.0
0x152e01  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x152e06  ldstr    aSystemDll// "System.dll"
0x152e0b  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x152e10  pop
0x152e11  ldloc.0
0x152e12  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x152e17  ldtoken  [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy
0x152e1c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152e21  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x152e26  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x152e2b  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x152e30  pop
0x152e31  ldloc.0
0x152e32  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x152e37  ldtoken  [Microsoft.SqlServer.Types]Microsoft.SqlServer.Types.SqlGeography
0x152e3c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152e41  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x152e46  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x152e4b  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x152e50  pop
0x152e51  ldloc.0
0x152e52  dup
0x152e53  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x152e58  ldarg.0
0x152e59  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionParser Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_langParser
0x152e5e  callvirt instance string Microsoft.ReportingServices.RdlExpressions.ExpressionParser::GetCompilerArguments()
0x152e63  call     string [mscorlib]System.String::Concat(string, string)
0x152e68  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0x152e6d  ldarg.0
0x152e6e  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_expressionHostAssemblyHolder
0x152e73  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x152e78  brfalse.s loc_152E93
0x152e7a  ldarg.0
0x152e7b  ldarg.0
0x152e7c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_expressionHostAssemblyHolder
0x152e81  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x152e86  ldloc.0
0x152e87  ldarg.0
0x152e88  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_errorContext
0x152e8d  ldarg.1
0x152e8e  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::ResolveAssemblylocations(class [mscorlib]System.Collections.Generic.List`1<string> codeModules, class [System]System.CodeDom.Compiler.CompilerParameters options, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, class [mscorlib]System.AppDomain compilationTempAppDomain)
0x152e93  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatVersion Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatVersion::get_Current()
0x152e98  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ProcessingIntermediateFormatVersion::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatVersion version)
0x152e9d  stloc.1
0x152e9e  ldarg.0
0x152e9f  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_builder
0x152ea4  ldloc.1
0x152ea5  ldarg.2
0x152ea6  callvirt instance class [System]System.CodeDom.CodeCompileUnit Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::GetExprHost(class Microsoft.ReportingServices.ReportIntermediateFormat.ProcessingIntermediateFormatVersion version, bool refusePermissions)
0x152eab  stloc.2
0x152eac  ldarg.0
0x152ead  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_expressionHostAssemblyHolder
0x152eb2  ldarg.2
0x152eb3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::set_CompiledCodeGeneratedWithRefusedPermissions(bool value)
0x152eb8  ldarg.0
0x152eb9  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionParser Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_langParser
0x152ebe  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider Microsoft.ReportingServices.RdlExpressions.ExpressionParser::GetCodeCompiler()
0x152ec3  stloc.3
0x152ec4  call     class Microsoft.ReportingServices.RdlExpressions.ICompiler Microsoft.ReportingServices.RdlExpressions.CompilerFactory::CreateCompiler()
0x152ec9  ldloc.3
0x152eca  ldarg.0
0x152ecb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_expressionHostAssemblyHolder
0x152ed0  ldloc.0
0x152ed1  ldloc.2
0x152ed2  ldarg.0
0x152ed3  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_errorContext
0x152ed8  ldarg.0
0x152ed9  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExprCompileTimeInfoList Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_ctExprList
0x152ede  ldarg.0
0x152edf  ldfld    class Microsoft.ReportingServices.RdlExpressions.CodeModuleClassInstanceDeclCompileTimeInfoList Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_ctClassInstDeclList
0x152ee4  ldarg.0
0x152ee5  ldflda   int32 Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_customCodeNumErrors
0x152eea  ldarg.0
0x152eeb  ldflda   int32 Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::m_customCodeNumWarnings
0x152ef0  callvirt instance unsigned int8[] Microsoft.ReportingServices.RdlExpressions.ICompiler::Compile(class [System]System.CodeDom.Compiler.CodeDomProvider compiler, class Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder expressionHostAssemblyHolder, class [System]System.CodeDom.Compiler.CompilerParameters options, class [System]System.CodeDom.CodeCompileUnit compilationUnits, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, class Microsoft.ReportingServices.RdlExpressions.ExprCompileTimeInfoList ctExprList, class Microsoft.ReportingServices.RdlExpressions.CodeModuleClassInstanceDeclCompileTimeInfoList ctClassInstDeclList, int32& customCodeNumErrors, int32& customCodeNumWarnings)
0x152ef5  ret
0x152ef6  ldc.i4.0
0x152ef7  newarr   [mscorlib]System.Byte
0x152efc  ret
```
