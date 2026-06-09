# Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::InternalCompile

- ea: `0x18ce30`
- end: `0x18d03d`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::InternalCompile`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2629f0`

## callees

- `0x18c9d0`
- `0x18c9e0`
- `0x18ce30`
- `0x18d040`
- `0x18d0e0`
- `0x18d300`
- `0x18d340`
- `0x195750`
- `0x195b10`
- `0x195e20`
- `0x195e40`
- `0x196030`

## string_xrefs

- `0x18ce4c`: `{0}{1}.dll`
- `0x18ce81`: `System.dll`
- `0x18d000`: `(read == fs.Length)`

## pseudocode

```c

```

## disassembly

```asm
0x18ce30  ldarg.0
0x18ce31  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::m_builder
0x18ce36  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::get_HasExpressions()
0x18ce3b  brfalse  loc_18D033
0x18ce40  newobj   instance void [System]System.CodeDom.Compiler.CompilerParameters::.ctor()
0x18ce45  stloc.0
0x18ce46  ldloc.0
0x18ce47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ce4c  ldstr    a01Dll// "{0}{1}.dll"
0x18ce51  call     string [mscorlib]System.IO.Path::GetTempPath()
0x18ce56  ldarg.1
0x18ce57  callvirt instance string Microsoft.ReportingServices.ReportProcessing.Report::get_ExprHostAssemblyName()
0x18ce5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x18ce61  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_OutputAssembly(string)
0x18ce66  ldloc.0
0x18ce67  ldc.i4.0
0x18ce68  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateExecutable(bool)
0x18ce6d  ldloc.0
0x18ce6e  ldc.i4.0
0x18ce6f  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_GenerateInMemory(bool)
0x18ce74  ldloc.0
0x18ce75  ldc.i4.0
0x18ce76  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_IncludeDebugInformation(bool)
0x18ce7b  ldloc.0
0x18ce7c  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x18ce81  ldstr    aSystemDll// "System.dll"
0x18ce86  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x18ce8b  pop
0x18ce8c  ldloc.0
0x18ce8d  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.Compiler.CompilerParameters::get_ReferencedAssemblies()
0x18ce92  ldtoken  [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy
0x18ce97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ce9c  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x18cea1  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x18cea6  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x18ceab  pop
0x18ceac  ldloc.0
0x18cead  dup
0x18ceae  callvirt instance string [System]System.CodeDom.Compiler.CompilerParameters::get_CompilerOptions()
0x18ceb3  ldarg.0
0x18ceb4  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionParser Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::m_langParser
0x18ceb9  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ExpressionParser::GetCompilerArguments()
0x18cebe  call     string [mscorlib]System.String::Concat(string, string)
0x18cec3  callvirt instance void [System]System.CodeDom.Compiler.CompilerParameters::set_CompilerOptions(string)
0x18cec8  ldarg.1
0x18cec9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.StringList Microsoft.ReportingServices.ReportProcessing.Report::get_CodeModules()
0x18cece  brfalse.s loc_18CEE4
0x18ced0  ldarg.0
0x18ced1  ldarg.1
0x18ced2  callvirt instance class Microsoft.ReportingServices.ReportProcessing.StringList Microsoft.ReportingServices.ReportProcessing.Report::get_CodeModules()
0x18ced7  ldloc.0
0x18ced8  ldarg.0
0x18ced9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::m_errorContext
0x18cede  ldarg.2
0x18cedf  call     instance void Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::ResolveAssemblylocations(class Microsoft.ReportingServices.ReportProcessing.StringList codeModules, class [System]System.CodeDom.Compiler.CompilerParameters options, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, class [mscorlib]System.AppDomain compilationTempAppDomain)
0x18cee4  ldnull
0x18cee5  stloc.1
0x18cee6  ldarg.0
0x18cee7  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::m_builder
0x18ceec  ldarg.1
0x18ceed  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IntermediateFormatVersion Microsoft.ReportingServices.ReportProcessing.Report::get_IntermediateFormatVersion()
0x18cef2  ldarg.3
0x18cef3  callvirt instance class [System]System.CodeDom.CodeCompileUnit Microsoft.ReportingServices.ReportProcessing.ExprHostBuilder::GetExprHost(class Microsoft.ReportingServices.ReportProcessing.IntermediateFormatVersion version, bool refusePermissions)
0x18cef8  stloc.2
0x18cef9  ldarg.1
0x18cefa  ldarg.3
0x18cefb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Report::set_CompiledCodeGeneratedWithRefusedPermissions(bool value)
0x18cf00  ldarg.0
0x18cf01  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExpressionParser Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::m_langParser
0x18cf06  callvirt instance class [System]System.CodeDom.Compiler.CodeDomProvider Microsoft.ReportingServices.ReportProcessing.ExpressionParser::GetCodeCompiler()
0x18cf0b  stloc.3
0x18cf0c  ldloc.3
0x18cf0d  ldloc.0
0x18cf0e  ldc.i4.1
0x18cf0f  newarr   [System]System.CodeDom.CodeCompileUnit
0x18cf14  dup
0x18cf15  ldc.i4.0
0x18cf16  ldloc.2
0x18cf17  stelem.ref
0x18cf18  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults [System]System.CodeDom.Compiler.CodeDomProvider::CompileAssemblyFromDom(class [System]System.CodeDom.Compiler.CompilerParameters, class [System]System.CodeDom.CodeCompileUnit[])
0x18cf1d  stloc.1
0x18cf1e  ldloc.1
0x18cf1f  callvirt instance int32 [System]System.CodeDom.Compiler.CompilerResults::get_NativeCompilerReturnValue()
0x18cf24  brtrue.s loc_18CF37
0x18cf26  ldloc.1
0x18cf27  callvirt instance class [System]System.CodeDom.Compiler.CompilerErrorCollection [System]System.CodeDom.Compiler.CompilerResults::get_Errors()
0x18cf2c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x18cf31  ldc.i4.0
0x18cf32  ble      loc_18CFBF
0x18cf37  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x18cf3c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x18cf41  brfalse.s loc_18CFA8
0x18cf43  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x18cf48  stloc.s  4
0x18cf4a  ldloc.s  4
0x18cf4c  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x18cf51  ldstr    asc_29545A// "    "
0x18cf56  newobj   instance void [System]System.CodeDom.Compiler.IndentedTextWriter::.ctor(class [mscorlib]System.IO.TextWriter, string)
0x18cf5b  stloc.s  5
0x18cf5d  ldloc.3
0x18cf5e  ldloc.2
0x18cf5f  ldloc.s  5
0x18cf61  newobj   instance void [System]System.CodeDom.Compiler.CodeGeneratorOptions::.ctor()
0x18cf66  callvirt instance void [System]System.CodeDom.Compiler.CodeDomProvider::GenerateCodeFromCompileUnit(class [System]System.CodeDom.CodeCompileUnit, class [mscorlib]System.IO.TextWriter, class [System]System.CodeDom.Compiler.CodeGeneratorOptions)
0x18cf6b  ldloc.s  5
0x18cf6d  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x18cf72  ldloc.s  4
0x18cf74  ldc.i4.0
0x18cf75  conv.i8
0x18cf76  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x18cf7b  ldloc.s  4
0x18cf7d  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x18cf82  stloc.s  6
0x18cf84  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x18cf89  ldloc.s  6
0x18cf8b  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x18cf90  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x18cf95  leave.s  loc_18CFA3
0x18cf97  ldloc.s  4
0x18cf99  brfalse.s loc_18CFA2
0x18cf9b  ldloc.s  4
0x18cf9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18cfa2  endfinally
0x18cfa3  leave.s  loc_18CFA8
0x18cfa5  pop
0x18cfa6  leave.s  loc_18CFA8
0x18cfa8  ldarg.0
0x18cfa9  ldloc.1
0x18cfaa  ldarg.1
0x18cfab  callvirt instance class Microsoft.ReportingServices.ReportProcessing.CodeClassList Microsoft.ReportingServices.ReportProcessing.Report::get_CodeClasses()
0x18cfb0  call     instance void Microsoft.ReportingServices.ReportProcessing.ReportCompileTime::ParseErrors(class [System]System.CodeDom.Compiler.CompilerResults results, class Microsoft.ReportingServices.ReportProcessing.CodeClassList codeClassInstDecls)
0x18cfb5  ldc.i4.0
0x18cfb6  newarr   [mscorlib]System.Byte
0x18cfbb  stloc.s  7
0x18cfbd  leave.s  loc_18D03A
0x18cfbf  ldloc.1
0x18cfc0  callvirt instance string [System]System.CodeDom.Compiler.CompilerResults::get_PathToAssembly()
0x18cfc5  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x18cfca  stloc.s  8
0x18cfcc  ldloc.s  8
0x18cfce  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x18cfd3  conv.ovf.i
0x18cfd4  newarr   [mscorlib]System.Byte
0x18cfd9  stloc.s  9
0x18cfdb  ldloc.s  8
0x18cfdd  ldloc.s  9
0x18cfdf  ldc.i4.0
0x18cfe0  ldloc.s  8
0x18cfe2  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x18cfe7  conv.i4
0x18cfe8  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x18cfed  stloc.s  0xA
0x18cfef  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x18cff4  ldloc.s  0xA
0x18cff6  conv.i8
0x18cff7  ldloc.s  8
0x18cff9  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x18cffe  ceq
0x18d000  ldstr    aReadFsLength// "(read == fs.Length)"
0x18d005  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x18d00a  ldloc.s  9
0x18d00c  stloc.s  7
0x18d00e  leave.s  loc_18D03A
0x18d010  ldloc.s  8
0x18d012  brfalse.s loc_18D01B
0x18d014  ldloc.s  8
0x18d016  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18d01b  endfinally
0x18d01c  ldloc.1
0x18d01d  brfalse.s loc_18D032
0x18d01f  ldloc.1
0x18d020  callvirt instance string [System]System.CodeDom.Compiler.CompilerResults::get_PathToAssembly()
0x18d025  brfalse.s loc_18D032
0x18d027  ldloc.1
0x18d028  callvirt instance string [System]System.CodeDom.Compiler.CompilerResults::get_PathToAssembly()
0x18d02d  call     void [mscorlib]System.IO.File::Delete(string)
0x18d032  endfinally
0x18d033  ldc.i4.0
0x18d034  newarr   [mscorlib]System.Byte
0x18d039  ret
0x18d03a  ldloc.s  7
0x18d03c  ret
```
