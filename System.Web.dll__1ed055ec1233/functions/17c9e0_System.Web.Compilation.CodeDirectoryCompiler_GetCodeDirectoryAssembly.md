# System.Web.Compilation.CodeDirectoryCompiler::GetCodeDirectoryAssembly

- ea: `0x17c9e0`
- end: `0x17cc2a`
- name: `System.Web.Compilation.CodeDirectoryCompiler::GetCodeDirectoryAssembly`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x175bf0`

## callees

- `0x18990`
- `0x24650`
- `0x302b0`
- `0x30f70`
- `0x31090`
- `0x311d0`
- `0x34f20`
- `0x551b0`
- `0x58b10`
- `0x58f20`
- `0x174c30`
- `0x175fe0`
- `0x176c00`
- `0x176dd0`
- `0x1777c0`
- `0x178b80`
- `0x178c30`
- `0x178ea0`
- `0x179a60`
- `0x179b60`
- `0x179bd0`
- `0x179f40`
- `0x17a180`
- `0x17a200`
- `0x17a3a0`
- `0x17a3f0`
- `0x17c9d0`
- `0x17c9e0`
- `0x17ccb0`
- `0x17cce0`
- `0x1827b0`

## string_xrefs

- `0x17c9f3`: `Bar_dir_in_precompiled_app`
- `0x17cb8e`: `Assembly_already_loaded`

## pseudocode

```c

```

## disassembly

```asm
0x17c9e0  ldarg.0
0x17c9e1  callvirt instance string System.Web.VirtualPath::MapPath()
0x17c9e6  stloc.0
0x17c9e7  ldarg.s  4
0x17c9e9  brtrue.s loc_17CA0D
0x17c9eb  ldloc.0
0x17c9ec  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x17c9f1  brfalse.s loc_17CA0D
0x17c9f3  ldstr    aBarDirInPrecom// "Bar_dir_in_precompiled_app"
0x17c9f8  ldc.i4.1
0x17c9f9  newarr   [mscorlib]System.Object
0x17c9fe  dup
0x17c9ff  ldc.i4.0
0x17ca00  ldarg.0
0x17ca01  stelem.ref
0x17ca02  call     string System.Web.SR::GetString(string name, object[] args)
0x17ca07  newobj   instance void System.Web.HttpException::.ctor(string message)
0x17ca0c  throw
0x17ca0d  ldarg.1
0x17ca0e  call     bool System.Web.Compilation.CodeDirectoryCompiler::IsResourceCodeDirectoryType(valuetype System.Web.Compilation.CodeDirectoryType dirType)
0x17ca13  stloc.1
0x17ca14  ldarg.2
0x17ca15  stloc.2
0x17ca16  ldloc.2
0x17ca17  call     class System.Web.Compilation.BuildResult System.Web.Compilation.BuildManager::GetBuildResultFromCache(string cacheKey)
0x17ca1c  stloc.3
0x17ca1d  ldnull
0x17ca1e  stloc.s  4
0x17ca20  ldloc.3
0x17ca21  brfalse.s loc_17CA7B
0x17ca23  ldloc.3
0x17ca24  isinst   System.Web.Compilation.BuildResultCompiledAssembly
0x17ca29  brfalse.s loc_17CA7B
0x17ca2b  ldloc.3
0x17ca2c  isinst   System.Web.Compilation.BuildResultMainCodeAssembly
0x17ca31  brfalse.s loc_17CA3E
0x17ca33  ldloc.3
0x17ca34  castclass System.Web.Compilation.BuildResultMainCodeAssembly
0x17ca39  stsfld   class System.Web.Compilation.BuildResultMainCodeAssembly System.Web.Compilation.CodeDirectoryCompiler::_mainCodeBuildResult
0x17ca3e  ldloc.3
0x17ca3f  castclass System.Web.Compilation.BuildResultCompiledAssembly
0x17ca44  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.Compilation.BuildResultCompiledAssemblyBase::get_ResultAssembly()
0x17ca49  stloc.s  4
0x17ca4b  ldloc.1
0x17ca4c  brtrue.s loc_17CA51
0x17ca4e  ldloc.s  4
0x17ca50  ret
0x17ca51  ldarg.s  4
0x17ca53  brtrue.s loc_17CA58
0x17ca55  ldloc.s  4
0x17ca57  ret
0x17ca58  ldloc.3
0x17ca59  castclass System.Web.Compilation.BuildResultResourceAssembly
0x17ca5e  stloc.s  0xA
0x17ca60  ldarg.0
0x17ca61  call     string System.Web.Util.HashCodeCombiner::GetDirectoryHash(class System.Web.VirtualPath virtualDir)
0x17ca66  stloc.s  0xB
0x17ca68  ldloc.s  0xB
0x17ca6a  ldloc.s  0xA
0x17ca6c  callvirt instance string System.Web.Compilation.BuildResultResourceAssembly::get_ResourcesDependenciesHash()
0x17ca71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17ca76  brfalse.s loc_17CA7B
0x17ca78  ldloc.s  4
0x17ca7a  ret
0x17ca7b  ldarg.s  4
0x17ca7d  brtrue.s loc_17CA81
0x17ca7f  ldnull
0x17ca80  ret
0x17ca81  ldarg.1
0x17ca82  ldc.i4.3
0x17ca83  beq.s    loc_17CAB1
0x17ca85  ldloc.0
0x17ca86  call     string System.Web.HttpRuntime::get_AppDomainAppPathInternal()
0x17ca8b  call     bool System.Web.Util.StringUtil::StringStartsWithIgnoreCase(string s1, string s2)
0x17ca90  brtrue.s loc_17CAB1
0x17ca92  ldstr    aVirtualCodedir// "Virtual_codedir"
0x17ca97  ldc.i4.1
0x17ca98  newarr   [mscorlib]System.Object
0x17ca9d  dup
0x17ca9e  ldc.i4.0
0x17ca9f  ldarg.0
0x17caa0  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x17caa5  stelem.ref
0x17caa6  call     string System.Web.SR::GetString(string name, object[] args)
0x17caab  newobj   instance void System.Web.HttpException::.ctor(string message)
0x17cab0  throw
0x17cab1  ldloc.0
0x17cab2  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x17cab7  brtrue.s loc_17CAC7
0x17cab9  ldarg.1
0x17caba  brfalse.s loc_17CABE
0x17cabc  ldnull
0x17cabd  ret
0x17cabe  call     bool System.Web.Compilation.ProfileBuildProvider::get_HasCompilableProfile()
0x17cac3  brtrue.s loc_17CAC7
0x17cac5  ldnull
0x17cac6  ret
0x17cac7  ldarg.0
0x17cac8  call     void System.Web.Compilation.BuildManager::ReportDirectoryCompilationProgress(class System.Web.VirtualPath virtualDir)
0x17cacd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17cad2  stloc.s  5
0x17cad4  ldarg.0
0x17cad5  ldarg.1
0x17cad6  ldarg.3
0x17cad7  newobj   instance void System.Web.Compilation.CodeDirectoryCompiler::.ctor(class System.Web.VirtualPath virtualDir, valuetype System.Web.Compilation.CodeDirectoryType dirType, class System.Web.Util.StringSet excludedSubdirectories)
0x17cadc  stloc.s  6
0x17cade  ldnull
0x17cadf  stloc.s  7
0x17cae1  ldloc.s  4
0x17cae3  ldnull
0x17cae4  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x17cae9  brfalse.s loc_17CB03
0x17caeb  ldloc.s  4
0x17caed  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x17caf2  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x17caf7  stloc.s  7
0x17caf9  ldloc.s  6
0x17cafb  ldc.i4.1
0x17cafc  stfld    bool System.Web.Compilation.CodeDirectoryCompiler::_onlyBuildLocalizedResources
0x17cb01  br.s     loc_17CB0B
0x17cb03  ldarg.2
0x17cb04  call     string System.Web.Compilation.BuildManager::GenerateRandomAssemblyName(string baseName)
0x17cb09  stloc.s  7
0x17cb0b  ldarg.0
0x17cb0c  ldloc.1
0x17cb0d  ldloc.s  7
0x17cb0f  newobj   instance void System.Web.Compilation.BuildProvidersCompiler::.ctor(class System.Web.VirtualPath configPath, bool supportLocalization, string outputAssemblyName)
0x17cb14  stloc.s  8
0x17cb16  ldloc.s  6
0x17cb18  ldloc.s  8
0x17cb1a  stfld    class System.Web.Compilation.BuildProvidersCompiler System.Web.Compilation.CodeDirectoryCompiler::_bpc
0x17cb1f  ldloc.s  6
0x17cb21  callvirt instance void System.Web.Compilation.CodeDirectoryCompiler::FindBuildProviders()
0x17cb26  ldloc.s  8
0x17cb28  ldloc.s  6
0x17cb2a  ldfld    class System.Web.Util.BuildProviderSet System.Web.Compilation.CodeDirectoryCompiler::_buildProviders
0x17cb2f  callvirt instance void System.Web.Compilation.BuildProvidersCompiler::SetBuildProviders(class [mscorlib]System.Collections.ICollection buildProviders)
0x17cb34  ldloc.s  8
0x17cb36  callvirt instance class [System]System.CodeDom.Compiler.CompilerResults System.Web.Compilation.BuildProvidersCompiler::PerformBuild()
0x17cb3b  stloc.s  9
0x17cb3d  ldloc.s  9
0x17cb3f  brfalse.s loc_17CBB7
0x17cb41  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17cb46  stloc.s  0xD
0x17cb48  ldloca.s 0xD
0x17cb4a  ldc.r8   3000.0
0x17cb53  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0x17cb58  stloc.s  0xC
0x17cb5a  ldloc.s  9
0x17cb5c  callvirt instance string [System]System.CodeDom.Compiler.CompilerResults::get_PathToAssembly()
0x17cb61  call     native int System.Web.UnsafeNativeMethods::GetModuleHandle(string moduleName)
0x17cb66  stloc.s  0xE
0x17cb68  ldloc.s  0xE
0x17cb6a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x17cb6f  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x17cb74  brtrue.s loc_17CBAE
0x17cb76  ldc.i4   0xFA
0x17cb7b  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x17cb80  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17cb85  ldloc.s  0xC
0x17cb87  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x17cb8c  brfalse.s loc_17CB5A
0x17cb8e  ldstr    aAssemblyAlread// "Assembly_already_loaded"
0x17cb93  ldc.i4.1
0x17cb94  newarr   [mscorlib]System.Object
0x17cb99  dup
0x17cb9a  ldc.i4.0
0x17cb9b  ldloc.s  9
0x17cb9d  callvirt instance string [System]System.CodeDom.Compiler.CompilerResults::get_PathToAssembly()
0x17cba2  stelem.ref
0x17cba3  call     string System.Web.SR::GetString(string name, object[] args)
0x17cba8  newobj   instance void System.Web.HttpException::.ctor(string message)
0x17cbad  throw
0x17cbae  ldloc.s  9
0x17cbb0  callvirt instance class [mscorlib]System.Reflection.Assembly [System]System.CodeDom.Compiler.CompilerResults::get_CompiledAssembly()
0x17cbb5  stloc.s  4
0x17cbb7  ldloc.s  4
0x17cbb9  ldnull
0x17cbba  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x17cbbf  brfalse.s loc_17CBC3
0x17cbc1  ldnull
0x17cbc2  ret
0x17cbc3  ldarg.1
0x17cbc4  brtrue.s loc_17CBDA
0x17cbc6  ldloc.s  4
0x17cbc8  newobj   instance void System.Web.Compilation.BuildResultMainCodeAssembly::.ctor(class [mscorlib]System.Reflection.Assembly a)
0x17cbcd  stsfld   class System.Web.Compilation.BuildResultMainCodeAssembly System.Web.Compilation.CodeDirectoryCompiler::_mainCodeBuildResult
0x17cbd2  ldsfld   class System.Web.Compilation.BuildResultMainCodeAssembly System.Web.Compilation.CodeDirectoryCompiler::_mainCodeBuildResult
0x17cbd7  stloc.3
0x17cbd8  br.s     loc_17CBEF
0x17cbda  ldloc.1
0x17cbdb  brfalse.s loc_17CBE7
0x17cbdd  ldloc.s  4
0x17cbdf  newobj   instance void System.Web.Compilation.BuildResultResourceAssembly::.ctor(class [mscorlib]System.Reflection.Assembly a)
0x17cbe4  stloc.3
0x17cbe5  br.s     loc_17CBEF
0x17cbe7  ldloc.s  4
0x17cbe9  newobj   instance void System.Web.Compilation.BuildResultCompiledAssembly::.ctor(class [mscorlib]System.Reflection.Assembly a)
0x17cbee  stloc.3
0x17cbef  ldloc.3
0x17cbf0  ldarg.0
0x17cbf1  callvirt instance void System.Web.Compilation.BuildResult::set_VirtualPath(class System.Web.VirtualPath value)
0x17cbf6  call     bool System.Web.Compilation.BuildManager::get_OptimizeCompilations()
0x17cbfb  brfalse.s loc_17CC12
0x17cbfd  ldarg.1
0x17cbfe  ldc.i4.3
0x17cbff  beq.s    loc_17CC12
0x17cc01  ldloc.3
0x17cc02  ldarg.0
0x17cc03  callvirt instance string System.Web.VirtualPath::get_AppRelativeVirtualPathString()
0x17cc08  newobj   instance void System.Web.Util.SingleObjectCollection::.ctor(object o)
0x17cc0d  callvirt instance void System.Web.Compilation.BuildResult::AddVirtualPathDependencies(class [mscorlib]System.Collections.ICollection sourceDependencies)
0x17cc12  ldarg.1
0x17cc13  ldc.i4.3
0x17cc14  beq.s    loc_17CC1D
0x17cc16  ldloc.3
0x17cc17  ldc.i4.0
0x17cc18  callvirt instance void System.Web.Compilation.BuildResult::set_CacheToMemory(bool value)
0x17cc1d  ldloc.2
0x17cc1e  ldloc.3
0x17cc1f  ldloc.s  5
0x17cc21  call     bool System.Web.Compilation.BuildManager::CacheBuildResult(string cacheKey, class System.Web.Compilation.BuildResult result, valuetype [mscorlib]System.DateTime utcStart)
0x17cc26  pop
0x17cc27  ldloc.s  4
0x17cc29  ret
```
