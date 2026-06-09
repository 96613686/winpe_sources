# System.Web.Hosting.ApplicationManager::GetPartialTrustPolicyLevel

- ea: `0x15ffc0`
- end: `0x1603cc`
- name: `System.Web.Hosting.ApplicationManager::GetPartialTrustPolicyLevel`
- size: `1036`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x15f4b0`

## callees

- `0x18990`
- `0x24cf0`
- `0x24d00`
- `0x31570`
- `0x34f20`
- `0x548e0`
- `0x54970`
- `0x85000`
- `0x85f30`
- `0x13ef40`
- `0x13ef70`
- `0x156ef0`
- `0x159ec0`
- `0x15a090`
- `0x15a2d0`
- `0x15a300`
- `0x15e490`
- `0x15ffc0`

## string_xrefs

- `0x1600b2`: `Invalid_temp_directory`
- `0x1600de`: `Invalid_temp_directory`
- `0x160104`: `Temporary ASP.NET Files`
- `0x16014c`: `Temporary ASP.NET Files`
- `0x160120`: `No_codegen_access`

## pseudocode

```c

```

## disassembly

```asm
0x15ffc0  ldarg.1
0x15ffc1  brfalse.s loc_15FFD6
0x15ffc3  ldarg.1
0x15ffc4  callvirt instance class System.Web.Configuration.TrustLevelCollection System.Web.Configuration.SecurityPolicySection::get_TrustLevels()
0x15ffc9  ldarg.0
0x15ffca  callvirt instance string System.Web.Configuration.TrustSection::get_Level()
0x15ffcf  callvirt instance class System.Web.Configuration.TrustLevel System.Web.Configuration.TrustLevelCollection::get_Item(string key)
0x15ffd4  brtrue.s loc_15FFFB
0x15ffd6  ldstr    aUnableToGetPol// "Unable_to_get_policy_file"
0x15ffdb  ldc.i4.1
0x15ffdc  newarr   [mscorlib]System.Object
0x15ffe1  dup
0x15ffe2  ldc.i4.0
0x15ffe3  ldarg.0
0x15ffe4  callvirt instance string System.Web.Configuration.TrustSection::get_Level()
0x15ffe9  stelem.ref
0x15ffea  call     string System.Web.SR::GetString(string name, object[] args)
0x15ffef  ldsfld   string [mscorlib]System.String::Empty
0x15fff4  ldc.i4.0
0x15fff5  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x15fffa  throw
0x15fffb  ldarg.1
0x15fffc  callvirt instance class System.Web.Configuration.TrustLevelCollection System.Web.Configuration.SecurityPolicySection::get_TrustLevels()
0x160001  ldarg.0
0x160002  callvirt instance string System.Web.Configuration.TrustSection::get_Level()
0x160007  callvirt instance class System.Web.Configuration.TrustLevel System.Web.Configuration.TrustLevelCollection::get_Item(string key)
0x16000c  callvirt instance string System.Web.Configuration.TrustLevel::get_PolicyFileExpanded()
0x160011  stloc.0
0x160012  ldloc.0
0x160013  brfalse.s loc_16001D
0x160015  ldloc.0
0x160016  call     bool System.Web.Util.FileUtil::FileExists(string filename)
0x16001b  brtrue.s loc_16003C
0x16001d  ldstr    aUnableToGetPol// "Unable_to_get_policy_file"
0x160022  ldc.i4.1
0x160023  newarr   [mscorlib]System.Object
0x160028  dup
0x160029  ldc.i4.0
0x16002a  ldarg.0
0x16002b  callvirt instance string System.Web.Configuration.TrustSection::get_Level()
0x160030  stelem.ref
0x160031  call     string System.Web.SR::GetString(string name, object[] args)
0x160036  newobj   instance void System.Web.HttpException::.ctor(string message)
0x16003b  throw
0x16003c  ldnull
0x16003d  stloc.1
0x16003e  ldarg.3
0x16003f  call     string System.Web.Util.FileUtil::RemoveTrailingDirectoryBackSlash(string path)
0x160044  stloc.2
0x160045  ldloc.2
0x160046  call     string System.Web.HttpRuntime::MakeFileUrl(string path)
0x16004b  stloc.3
0x16004c  ldnull
0x16004d  stloc.s  4
0x16004f  ldnull
0x160050  stloc.s  5
0x160052  ldnull
0x160053  stloc.s  6
0x160055  ldc.i4.0
0x160056  stloc.s  7
0x160058  ldarg.2
0x160059  brfalse.s loc_16007C
0x16005b  ldarg.2
0x16005c  callvirt instance string System.Web.Configuration.CompilationSection::get_TempDirectory()
0x160061  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x160066  brtrue.s loc_16007C
0x160068  ldarg.2
0x160069  callvirt instance string System.Web.Configuration.CompilationSection::get_TempDirectory()
0x16006e  stloc.s  4
0x160070  ldarg.2
0x160071  ldloca.s 5
0x160073  ldloca.s 6
0x160075  ldloca.s 7
0x160077  callvirt instance void System.Web.Configuration.CompilationSection::GetTempDirectoryErrorInfo([out] string& tempDirAttribName, [out] string& configFileName, [out] int32& configLineNumber)
0x16007c  ldloc.s  4
0x16007e  brfalse.s loc_1600FF
0x160080  ldloc.s  4
0x160082  callvirt instance string [mscorlib]System.String::Trim()
0x160087  stloc.s  4
0x160089  ldloc.s  4
0x16008b  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x160090  brtrue.s loc_160097
0x160092  ldnull
0x160093  stloc.s  4
0x160095  br.s     loc_1600AE
0x160097  nop
0x160098  ldloc.s  4
0x16009a  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x16009f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1600a4  stloc.s  4
0x1600a6  leave.s  loc_1600AE
0x1600a8  pop
0x1600a9  ldnull
0x1600aa  stloc.s  4
0x1600ac  leave.s  loc_1600AE
0x1600ae  ldloc.s  4
0x1600b0  brtrue.s loc_1600D1
0x1600b2  ldstr    aInvalidTempDir// "Invalid_temp_directory"
0x1600b7  ldc.i4.1
0x1600b8  newarr   [mscorlib]System.Object
0x1600bd  dup
0x1600be  ldc.i4.0
0x1600bf  ldloc.s  5
0x1600c1  stelem.ref
0x1600c2  call     string System.Web.SR::GetString(string name, object[] args)
0x1600c7  ldloc.s  6
0x1600c9  ldloc.s  7
0x1600cb  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x1600d0  throw
0x1600d1  nop
0x1600d2  ldloc.s  4
0x1600d4  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x1600d9  pop
0x1600da  leave.s  loc_160110
0x1600dc  stloc.s  0x10
0x1600de  ldstr    aInvalidTempDir// "Invalid_temp_directory"
0x1600e3  ldc.i4.1
0x1600e4  newarr   [mscorlib]System.Object
0x1600e9  dup
0x1600ea  ldc.i4.0
0x1600eb  ldloc.s  5
0x1600ed  stelem.ref
0x1600ee  call     string System.Web.SR::GetString(string name, object[] args)
0x1600f3  ldloc.s  0x10
0x1600f5  ldloc.s  6
0x1600f7  ldloc.s  7
0x1600f9  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x1600fe  throw
0x1600ff  call     string [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeDirectory()
0x160104  ldstr    aTemporaryAspNe// "Temporary ASP.NET Files"
0x160109  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x16010e  stloc.s  4
0x160110  ldloc.s  4
0x160112  call     bool System.Web.UI.Util::HasWriteAccessToDirectory(string dir)
0x160117  brtrue.s loc_160158
0x160119  call     bool [mscorlib]System.Environment::get_UserInteractive()
0x16011e  brtrue.s loc_160143
0x160120  ldstr    aNoCodegenAcces// "No_codegen_access"
0x160125  ldc.i4.2
0x160126  newarr   [mscorlib]System.Object
0x16012b  dup
0x16012c  ldc.i4.0
0x16012d  call     string System.Web.UI.Util::GetCurrentAccountName()
0x160132  stelem.ref
0x160133  dup
0x160134  ldc.i4.1
0x160135  ldloc.s  4
0x160137  stelem.ref
0x160138  call     string System.Web.SR::GetString(string name, object[] args)
0x16013d  newobj   instance void System.Web.HttpException::.ctor(string message)
0x160142  throw
0x160143  call     string [mscorlib]System.IO.Path::GetTempPath()
0x160148  stloc.s  4
0x16014a  ldloc.s  4
0x16014c  ldstr    aTemporaryAspNe// "Temporary ASP.NET Files"
0x160151  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x160156  stloc.s  4
0x160158  ldarg.s  4
0x16015a  call     string System.Web.VirtualPath::GetVirtualPathStringNoTrailingSlash(class System.Web.VirtualPath virtualPath)
0x16015f  ldarg.s  5
0x160161  call     string System.Web.Hosting.AppManagerAppDomainFactory::ConstructSimpleAppName(string virtPath, bool isDevEnvironment)
0x160166  stloc.s  8
0x160168  ldloc.s  4
0x16016a  ldloc.s  8
0x16016c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x160171  stloc.s  9
0x160173  ldloc.s  9
0x160175  call     string System.Web.Util.FileUtil::RemoveTrailingDirectoryBackSlash(string path)
0x16017a  stloc.s  9
0x16017c  ldloc.s  9
0x16017e  call     string System.Web.HttpRuntime::MakeFileUrl(string path)
0x160183  stloc.s  0xA
0x160185  ldarg.0
0x160186  callvirt instance string System.Web.Configuration.TrustSection::get_OriginUrl()
0x16018b  stloc.s  0xB
0x16018d  ldloc.0
0x16018e  ldc.i4.3
0x16018f  ldc.i4.1
0x160190  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x160195  stloc.s  0xC
0x160197  ldloc.s  0xC
0x160199  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x16019e  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x1601a3  stloc.s  0xD
0x1601a5  ldloc.s  0xD
0x1601a7  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x1601ac  stloc.s  0xE
0x1601ae  ldloc.s  0xD
0x1601b0  callvirt instance void [mscorlib]System.IO.TextReader::Close()
0x1601b5  ldloc.s  0xE
0x1601b7  ldstr    aAppdir// "$AppDir$"
0x1601bc  ldloc.2
0x1601bd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1601c2  stloc.s  0xE
0x1601c4  ldloc.s  0xE
0x1601c6  ldstr    aAppdirurl// "$AppDirUrl$"
0x1601cb  ldloc.3
0x1601cc  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1601d1  stloc.s  0xE
0x1601d3  ldloc.s  0xE
0x1601d5  ldstr    aCodegen// "$CodeGen$"
0x1601da  ldloc.s  0xA
0x1601dc  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1601e1  stloc.s  0xE
0x1601e3  ldloc.s  0xB
0x1601e5  brtrue.s loc_1601EE
0x1601e7  ldsfld   string [mscorlib]System.String::Empty
0x1601ec  stloc.s  0xB
0x1601ee  ldloc.s  0xE
0x1601f0  ldstr    aOriginhost// "$OriginHost$"
0x1601f5  ldloc.s  0xB
0x1601f7  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1601fc  stloc.s  0xE
0x1601fe  ldnull
0x1601ff  stloc.s  0xF
0x160201  ldloc.s  0xE
0x160203  ldstr    aGac// "$Gac$"
0x160208  ldc.i4.4
0x160209  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16020e  ldc.i4.m1
0x16020f  beq.s    loc_160240
0x160211  call     string System.Web.HttpRuntime::GetGacLocation()
0x160216  stloc.s  0xF
0x160218  ldloc.s  0xF
0x16021a  brfalse.s loc_160225
0x16021c  ldloc.s  0xF
0x16021e  call     string System.Web.HttpRuntime::MakeFileUrl(string path)
0x160223  stloc.s  0xF
0x160225  ldloc.s  0xF
0x160227  brtrue.s loc_160230
0x160229  ldsfld   string [mscorlib]System.String::Empty
0x16022e  stloc.s  0xF
0x160230  ldloc.s  0xE
0x160232  ldstr    aGac// "$Gac$"
0x160237  ldloc.s  0xF
0x160239  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x16023e  stloc.s  0xE
0x160240  ldloc.s  0xE
0x160242  ldc.i4.3
0x160243  call     class [mscorlib]System.Security.Policy.PolicyLevel [mscorlib]System.Security.SecurityManager::LoadPolicyLevelFromString(string, valuetype [mscorlib]System.Security.PolicyLevelType)
0x160248  stloc.1
0x160249  ldloc.1
0x16024a  brtrue.s loc_16026B
0x16024c  ldstr    aUnableToGetPol// "Unable_to_get_policy_file"
0x160251  ldc.i4.1
0x160252  newarr   [mscorlib]System.Object
0x160257  dup
0x160258  ldc.i4.0
0x160259  ldarg.0
0x16025a  callvirt instance string System.Web.Configuration.TrustSection::get_Level()
0x16025f  stelem.ref
0x160260  call     string System.Web.SR::GetString(string name, object[] args)
0x160265  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x16026a  throw
0x16026b  ldloc.s  0xF
0x16026d  brfalse  loc_1603CA
0x160272  ldloc.1
0x160273  callvirt instance class [mscorlib]System.Security.Policy.CodeGroup [mscorlib]System.Security.Policy.PolicyLevel::get_RootCodeGroup()
0x160278  stloc.s  0x11
0x16027a  ldc.i4.0
0x16027b  stloc.s  0x12
0x16027d  ldloc.s  0x11
0x16027f  callvirt instance class [mscorlib]System.Collections.IList [mscorlib]System.Security.Policy.CodeGroup::get_Children()
0x160284  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x160289  stloc.s  0x13
0x16028b  br.s     loc_1602AE
0x16028d  ldloc.s  0x13
0x16028f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x160294  castclass [mscorlib]System.Security.Policy.CodeGroup
0x160299  stloc.s  0x14
0x16029b  ldloc.s  0x14
0x16029d  callvirt instance class [mscorlib]System.Security.Policy.IMembershipCondition [mscorlib]System.Security.Policy.CodeGroup::get_MembershipCondition()
0x1602a2  isinst   [mscorlib]System.Security.Policy.GacMembershipCondition
0x1602a7  brfalse.s loc_1602AE
0x1602a9  ldc.i4.1
0x1602aa  stloc.s  0x12
0x1602ac  leave.s  loc_1602CE
0x1602ae  ldloc.s  0x13
0x1602b0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1602b5  brtrue.s loc_16028D
0x1602b7  leave.s  loc_1602CE
0x1602b9  ldloc.s  0x13
0x1602bb  isinst   [mscorlib]System.IDisposable
0x1602c0  stloc.s  0x15
0x1602c2  ldloc.s  0x15
0x1602c4  brfalse.s loc_1602CD
0x1602c6  ldloc.s  0x15
0x1602c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1602cd  endfinally
0x1602ce  ldloc.s  0x12
0x1602d0  brtrue   loc_1603CA
0x1602d5  ldloc.s  0x11
0x1602d7  isinst   [mscorlib]System.Security.Policy.FirstMatchCodeGroup
0x1602dc  brfalse  loc_1603CA
0x1602e1  ldloc.s  0x11
0x1602e3  castclass [mscorlib]System.Security.Policy.FirstMatchCodeGroup
0x1602e8  stloc.s  0x16
0x1602ea  ldloc.s  0x16
0x1602ec  callvirt instance class [mscorlib]System.Security.Policy.IMembershipCondition [mscorlib]System.Security.Policy.CodeGroup::get_MembershipCondition()
0x1602f1  isinst   [mscorlib]System.Security.Policy.AllMembershipCondition
  ... truncated ...
```
