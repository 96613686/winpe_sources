# System.Web.HttpRuntime::SetUpCodegenDirectory

- ea: `0x225b0`
- end: `0x226fa`
- name: `System.Web.HttpRuntime::SetUpCodegenDirectory`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x22060`

## callees

- `0x18990`
- `0x225b0`
- `0x24660`
- `0x34f20`
- `0x85000`
- `0x85f30`
- `0x13ef40`
- `0x13ef70`
- `0x15e490`
- `0x161ec0`
- `0x177ca0`

## string_xrefs

- `0x22621`: `Invalid_temp_directory`
- `0x2264c`: `Invalid_temp_directory`
- `0x22672`: `Temporary ASP.NET Files`
- `0x226bc`: `Temporary ASP.NET Files`
- `0x22693`: `No_codegen_access`

## pseudocode

```c

```

## disassembly

```asm
0x225b0  call     class [mscorlib]System.AppDomain [mscorlib]System.Threading.Thread::GetDomain()
0x225b5  stloc.0
0x225b6  call     string System.Web.HttpRuntime::get_AppDomainAppVirtualPath()
0x225bb  call     bool System.Web.Hosting.HostingEnvironment::get_IsDevelopmentEnvironment()
0x225c0  call     string System.Web.Hosting.AppManagerAppDomainFactory::ConstructSimpleAppName(string virtPath, bool isDevEnvironment)
0x225c5  stloc.2
0x225c6  ldnull
0x225c7  stloc.3
0x225c8  ldnull
0x225c9  stloc.s  4
0x225cb  ldnull
0x225cc  stloc.s  5
0x225ce  ldc.i4.0
0x225cf  stloc.s  6
0x225d1  ldarg.1
0x225d2  brfalse.s loc_225F4
0x225d4  ldarg.1
0x225d5  callvirt instance string System.Web.Configuration.CompilationSection::get_TempDirectory()
0x225da  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x225df  brtrue.s loc_225F4
0x225e1  ldarg.1
0x225e2  callvirt instance string System.Web.Configuration.CompilationSection::get_TempDirectory()
0x225e7  stloc.3
0x225e8  ldarg.1
0x225e9  ldloca.s 4
0x225eb  ldloca.s 5
0x225ed  ldloca.s 6
0x225ef  callvirt instance void System.Web.Configuration.CompilationSection::GetTempDirectoryErrorInfo([out] string& tempDirAttribName, [out] string& configFileName, [out] int32& configLineNumber)
0x225f4  ldloc.3
0x225f5  brfalse.s loc_2266D
0x225f7  ldloc.3
0x225f8  callvirt instance string [mscorlib]System.String::Trim()
0x225fd  stloc.3
0x225fe  ldloc.3
0x225ff  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x22604  brtrue.s loc_2260A
0x22606  ldnull
0x22607  stloc.3
0x22608  br.s     loc_2261E
0x2260a  nop
0x2260b  ldloc.3
0x2260c  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x22611  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x22616  stloc.3
0x22617  leave.s  loc_2261E
0x22619  pop
0x2261a  ldnull
0x2261b  stloc.3
0x2261c  leave.s  loc_2261E
0x2261e  ldloc.3
0x2261f  brtrue.s loc_22640
0x22621  ldstr    aInvalidTempDir// "Invalid_temp_directory"
0x22626  ldc.i4.1
0x22627  newarr   [mscorlib]System.Object
0x2262c  dup
0x2262d  ldc.i4.0
0x2262e  ldloc.s  4
0x22630  stelem.ref
0x22631  call     string System.Web.SR::GetString(string name, object[] args)
0x22636  ldloc.s  5
0x22638  ldloc.s  6
0x2263a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x2263f  throw
0x22640  nop
0x22641  ldloc.3
0x22642  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x22647  pop
0x22648  leave.s  loc_2267D
0x2264a  stloc.s  7
0x2264c  ldstr    aInvalidTempDir// "Invalid_temp_directory"
0x22651  ldc.i4.1
0x22652  newarr   [mscorlib]System.Object
0x22657  dup
0x22658  ldc.i4.0
0x22659  ldloc.s  4
0x2265b  stelem.ref
0x2265c  call     string System.Web.SR::GetString(string name, object[] args)
0x22661  ldloc.s  7
0x22663  ldloc.s  5
0x22665  ldloc.s  6
0x22667  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x2266c  throw
0x2266d  ldsfld   string System.Web.HttpRuntime::s_installDirectory
0x22672  ldstr    aTemporaryAspNe// "Temporary ASP.NET Files"
0x22677  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2267c  stloc.3
0x2267d  ldloc.3
0x2267e  call     bool System.Web.UI.Util::HasWriteAccessToDirectory(string dir)
0x22683  brtrue.s loc_226C7
0x22685  call     bool System.Web.Compilation.BuildManagerHost::get_InClientBuildManager()
0x2268a  brtrue.s loc_226B5
0x2268c  call     bool [mscorlib]System.Environment::get_UserInteractive()
0x22691  brtrue.s loc_226B5
0x22693  ldstr    aNoCodegenAcces// "No_codegen_access"
0x22698  ldc.i4.2
0x22699  newarr   [mscorlib]System.Object
0x2269e  dup
0x2269f  ldc.i4.0
0x226a0  call     string System.Web.UI.Util::GetCurrentAccountName()
0x226a5  stelem.ref
0x226a6  dup
0x226a7  ldc.i4.1
0x226a8  ldloc.3
0x226a9  stelem.ref
0x226aa  call     string System.Web.SR::GetString(string name, object[] args)
0x226af  newobj   instance void System.Web.HttpException::.ctor(string message)
0x226b4  throw
0x226b5  call     string [mscorlib]System.IO.Path::GetTempPath()
0x226ba  stloc.3
0x226bb  ldloc.3
0x226bc  ldstr    aTemporaryAspNe// "Temporary ASP.NET Files"
0x226c1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x226c6  stloc.3
0x226c7  ldarg.0
0x226c8  ldloc.3
0x226c9  stfld    string System.Web.HttpRuntime::_tempDir
0x226ce  ldloc.3
0x226cf  ldloc.2
0x226d0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x226d5  stloc.1
0x226d6  ldloc.0
0x226d7  ldloc.1
0x226d8  callvirt instance void [mscorlib]System.AppDomain::SetDynamicBase(string)
0x226dd  ldarg.0
0x226de  call     class [mscorlib]System.AppDomain [mscorlib]System.Threading.Thread::GetDomain()
0x226e3  callvirt instance string [mscorlib]System.AppDomain::get_DynamicDirectory()
0x226e8  stfld    string System.Web.HttpRuntime::_codegenDir
0x226ed  ldarg.0
0x226ee  ldfld    string System.Web.HttpRuntime::_codegenDir
0x226f3  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x226f8  pop
0x226f9  ret
```
