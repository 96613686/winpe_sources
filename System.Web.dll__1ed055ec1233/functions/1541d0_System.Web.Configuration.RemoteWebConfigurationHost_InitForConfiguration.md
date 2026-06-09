# System.Web.Configuration.RemoteWebConfigurationHost::InitForConfiguration

- ea: `0x1541d0`
- end: `0x154458`
- name: `System.Web.Configuration.RemoteWebConfigurationHost::InitForConfiguration`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x31460`
- `0x31550`
- `0x31640`
- `0x53a80`
- `0x14b710`
- `0x1541d0`
- `0x154720`
- `0x154760`
- `0x1547a0`
- `0x15a8b0`
- `0x15ad60`
- `0x15af70`
- `0x15b1c0`
- `0x15b250`
- `0x15b270`
- `0x15b2f0`
- `0x15b6e0`
- `0x15b700`
- `0x15b7e0`

## string_xrefs

- `0x1542e5`: `RemoteWebConfigurationHost::InitForConfiguration`
- `0x15430f`: `RemoteWebConfigurationHost::InitForConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1541d0  ldarg.s  5
0x1541d2  ldc.i4.0
0x1541d3  ldelem.ref
0x1541d4  unbox.any System.Web.Configuration.WebLevel
0x1541d9  stloc.0
0x1541da  ldarg.s  5
0x1541dc  ldc.i4.2
0x1541dd  ldelem.ref
0x1541de  castclass [mscorlib]System.String
0x1541e3  stloc.1
0x1541e4  ldarg.s  5
0x1541e6  ldc.i4.3
0x1541e7  ldelem.ref
0x1541e8  castclass [mscorlib]System.String
0x1541ed  stloc.2
0x1541ee  ldarg.1
0x1541ef  ldind.ref
0x1541f0  brtrue.s loc_1541FD
0x1541f2  ldarg.1
0x1541f3  ldarg.s  5
0x1541f5  ldc.i4.4
0x1541f6  ldelem.ref
0x1541f7  castclass [mscorlib]System.String
0x1541fc  stind.ref
0x1541fd  ldarg.s  5
0x1541ff  ldc.i4.5
0x154200  ldelem.ref
0x154201  castclass [mscorlib]System.String
0x154206  stloc.3
0x154207  ldarg.s  5
0x154209  ldc.i4.6
0x15420a  ldelem.ref
0x15420b  castclass [mscorlib]System.String
0x154210  stloc.s  4
0x154212  ldarg.s  5
0x154214  ldc.i4.7
0x154215  ldelem.ref
0x154216  castclass [mscorlib]System.String
0x15421b  stloc.s  5
0x15421d  ldarg.s  5
0x15421f  ldc.i4.8
0x154220  ldelem.ref
0x154221  unbox.any [mscorlib]System.IntPtr
0x154226  stloc.s  6
0x154228  ldarg.2
0x154229  ldnull
0x15422a  stind.ref
0x15422b  ldarg.3
0x15422c  ldnull
0x15422d  stind.ref
0x15422e  ldarg.0
0x15422f  ldloc.3
0x154230  stfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Server
0x154235  ldarg.0
0x154236  ldloc.s  4
0x154238  call     string System.Web.Configuration.RemoteWebConfigurationHost::GetUserNameFromFullName(string fullUserName)
0x15423d  stfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Username
0x154242  ldarg.0
0x154243  ldloc.s  4
0x154245  call     string System.Web.Configuration.RemoteWebConfigurationHost::GetDomainFromFullName(string fullUserName)
0x15424a  stfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Domain
0x15424f  ldarg.0
0x154250  ldloc.s  5
0x154252  stfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Password
0x154257  ldarg.0
0x154258  ldloc.s  6
0x15425a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x15425f  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x154264  brtrue.s loc_15426F
0x154266  ldloc.s  6
0x154268  newobj   instance void [mscorlib]System.Security.Principal.WindowsIdentity::.ctor(native int)
0x15426d  br.s     loc_154270
0x15426f  ldnull
0x154270  stfld    class [mscorlib]System.Security.Principal.WindowsIdentity System.Web.Configuration.RemoteWebConfigurationHost::_Identity
0x154275  ldarg.0
0x154276  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x15427b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x154280  stfld    class [mscorlib]System.Collections.Hashtable System.Web.Configuration.RemoteWebConfigurationHost::_PathMap
0x154285  ldarg.0
0x154286  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity System.Web.Configuration.RemoteWebConfigurationHost::_Identity
0x15428b  brtrue.s loc_154290
0x15428d  ldnull
0x15428e  br.s     loc_15429B
0x154290  ldarg.0
0x154291  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity System.Web.Configuration.RemoteWebConfigurationHost::_Identity
0x154296  callvirt instance class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate()
0x15429b  stloc.s  0xF
0x15429d  ldloc.3
0x15429e  ldarg.0
0x15429f  ldfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Username
0x1542a4  ldarg.0
0x1542a5  ldfld    string System.Web.Configuration.RemoteWebConfigurationHost::_Domain
0x1542aa  ldloc.s  5
0x1542ac  call     class System.Web.Configuration.IRemoteWebConfigurationHostServer System.Web.Configuration.RemoteWebConfigurationHost::CreateRemoteObject(string server, string username, string domain, string password)
0x1542b1  stloc.s  0x10
0x1542b3  ldloc.s  0x10
0x1542b5  ldloc.0
0x1542b6  ldloc.1
0x1542b7  ldloc.2
0x1542b8  ldarg.1
0x1542b9  ldind.ref
0x1542ba  callvirt instance string System.Web.Configuration.IRemoteWebConfigurationHostServer::GetFilePaths(int32 webLevel, string path, string site, string locationSubPath)
0x1542bf  stloc.s  7
0x1542c1  leave.s  loc_1542CE
0x1542c3  ldloc.s  0x10
0x1542c5  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x1542ca  ldc.i4.0
0x1542cb  bgt.s    loc_1542C3
0x1542cd  endfinally
0x1542ce  leave.s  loc_1542DC
0x1542d0  ldloc.s  0xF
0x1542d2  brfalse.s loc_1542DB
0x1542d4  ldloc.s  0xF
0x1542d6  callvirt instance void [mscorlib]System.Security.Principal.WindowsImpersonationContext::Undo()
0x1542db  endfinally
0x1542dc  leave.s  loc_1542E1
0x1542de  pop
0x1542df  rethrow
0x1542e1  ldloc.s  7
0x1542e3  brtrue.s loc_1542F0
0x1542e5  ldstr    aRemotewebconfi_0// "RemoteWebConfigurationHost::InitForConf"...
0x1542ea  call     class [mscorlib]System.InvalidOperationException System.Web.Util.ExceptionUtil::UnexpectedError(string methodName)
0x1542ef  throw
0x1542f0  ldloc.s  7
0x1542f2  ldsfld   char[] System.Web.Configuration.RemoteWebConfigurationHostServer::FilePathsSeparatorParams
0x1542f7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1542fc  stloc.s  8
0x1542fe  ldloc.s  8
0x154300  ldlen
0x154301  conv.i4
0x154302  ldc.i4.7
0x154303  blt.s    loc_15430F
0x154305  ldloc.s  8
0x154307  ldlen
0x154308  conv.i4
0x154309  ldc.i4.5
0x15430a  sub
0x15430b  ldc.i4.2
0x15430c  rem
0x15430d  brfalse.s loc_15431A
0x15430f  ldstr    aRemotewebconfi_0// "RemoteWebConfigurationHost::InitForConf"...
0x154314  call     class [mscorlib]System.InvalidOperationException System.Web.Util.ExceptionUtil::UnexpectedError(string methodName)
0x154319  throw
0x15431a  ldc.i4.0
0x15431b  stloc.s  0x11
0x15431d  br.s     loc_154337
0x15431f  ldloc.s  8
0x154321  ldloc.s  0x11
0x154323  ldelem.ref
0x154324  callvirt instance int32 [mscorlib]System.String::get_Length()
0x154329  brtrue.s loc_154331
0x15432b  ldloc.s  8
0x15432d  ldloc.s  0x11
0x15432f  ldnull
0x154330  stelem.ref
0x154331  ldloc.s  0x11
0x154333  ldc.i4.1
0x154334  add
0x154335  stloc.s  0x11
0x154337  ldloc.s  0x11
0x154339  ldloc.s  8
0x15433b  ldlen
0x15433c  conv.i4
0x15433d  blt.s    loc_15431F
0x15433f  ldloc.s  8
0x154341  ldc.i4.0
0x154342  ldelem.ref
0x154343  stloc.s  9
0x154345  ldloc.s  8
0x154347  ldc.i4.1
0x154348  ldelem.ref
0x154349  stloc.s  0xA
0x15434b  ldloc.s  8
0x15434d  ldc.i4.2
0x15434e  ldelem.ref
0x15434f  stloc.s  0xB
0x154351  ldarg.2
0x154352  ldloc.s  8
0x154354  ldc.i4.3
0x154355  ldelem.ref
0x154356  stind.ref
0x154357  ldarg.3
0x154358  ldloc.s  8
0x15435a  ldc.i4.4
0x15435b  ldelem.ref
0x15435c  stind.ref
0x15435d  ldarg.0
0x15435e  ldarg.2
0x15435f  ldind.ref
0x154360  stfld    string System.Web.Configuration.RemoteWebConfigurationHost::_ConfigPath
0x154365  newobj   instance void System.Web.Configuration.WebConfigurationFileMap::.ctor()
0x15436a  stloc.s  0xC
0x15436c  ldloc.s  9
0x15436e  call     class System.Web.VirtualPath System.Web.VirtualPath::CreateAbsoluteAllowNull(string virtualPath)
0x154373  stloc.s  0xD
0x154375  ldloc.s  0xC
0x154377  ldloc.s  0xB
0x154379  callvirt instance void System.Web.Configuration.WebConfigurationFileMap::set_Site(string value)
0x15437e  ldc.i4.5
0x15437f  stloc.s  0x12
0x154381  br       loc_15440B
0x154386  ldloc.s  8
0x154388  ldloc.s  0x12
0x15438a  ldelem.ref
0x15438b  stloc.s  0x13
0x15438d  ldloc.s  8
0x15438f  ldloc.s  0x12
0x154391  ldc.i4.1
0x154392  add
0x154393  ldelem.ref
0x154394  stloc.s  0x14
0x154396  ldarg.0
0x154397  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Configuration.RemoteWebConfigurationHost::_PathMap
0x15439c  ldloc.s  0x13
0x15439e  ldloc.s  0x14
0x1543a0  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x1543a5  ldloc.s  0x13
0x1543a7  call     bool System.Web.Configuration.WebConfigurationHost::IsMachineConfigPath(string configPath)
0x1543ac  brfalse.s loc_1543B9
0x1543ae  ldloc.s  0xC
0x1543b0  ldloc.s  0x14
0x1543b2  callvirt instance void [System.Configuration]System.Configuration.ConfigurationFileMap::set_MachineConfigFilename(string)
0x1543b7  br.s     loc_154405
0x1543b9  ldloc.s  0x13
0x1543bb  call     bool System.Web.Configuration.WebConfigurationHost::IsRootWebConfigPath(string configPath)
0x1543c0  brfalse.s loc_1543CA
0x1543c2  ldnull
0x1543c3  stloc.s  0x15
0x1543c5  ldc.i4.0
0x1543c6  stloc.s  0x16
0x1543c8  br.s     loc_1543E9
0x1543ca  ldloc.s  0x13
0x1543cc  ldloca.s 0x18
0x1543ce  ldloca.s 0x17
0x1543d0  call     void System.Web.Configuration.WebConfigurationHost::GetSiteIDAndVPathFromConfigPath(string configPath, [out] string& siteID, [out] class System.Web.VirtualPath& vpath)
0x1543d5  ldloc.s  0x17
0x1543d7  call     string System.Web.VirtualPath::GetVirtualPathString(class System.Web.VirtualPath virtualPath)
0x1543dc  stloc.s  0x15
0x1543de  ldloc.s  0x17
0x1543e0  ldloc.s  0xD
0x1543e2  call     bool System.Web.VirtualPath::op_Equality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x1543e7  stloc.s  0x16
0x1543e9  ldloc.s  0xC
0x1543eb  callvirt instance class System.Web.Configuration.VirtualDirectoryMappingCollection System.Web.Configuration.WebConfigurationFileMap::get_VirtualDirectories()
0x1543f0  ldloc.s  0x15
0x1543f2  ldloc.s  0x14
0x1543f4  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1543f9  ldloc.s  0x16
0x1543fb  newobj   instance void System.Web.Configuration.VirtualDirectoryMapping::.ctor(string physicalDirectory, bool isAppRoot)
0x154400  callvirt instance void System.Web.Configuration.VirtualDirectoryMappingCollection::Add(string virtualDirectory, class System.Web.Configuration.VirtualDirectoryMapping mapping)
0x154405  ldloc.s  0x12
0x154407  ldc.i4.2
0x154408  add
0x154409  stloc.s  0x12
0x15440b  ldloc.s  0x12
0x15440d  ldloc.s  8
0x15440f  ldlen
0x154410  conv.i4
0x154411  blt      loc_154386
0x154416  newobj   instance void System.Web.Configuration.WebConfigurationHost::.ctor()
0x15441b  stloc.s  0xE
0x15441d  ldloc.s  0xE
0x15441f  ldarg.s  4
0x154421  ldc.i4.6
0x154422  newarr   [mscorlib]System.Object
0x154427  dup
0x154428  ldc.i4.0
0x154429  ldc.i4.1
0x15442a  box      [mscorlib]System.Boolean
0x15442f  stelem.ref
0x154430  dup
0x154431  ldc.i4.1
0x154432  ldloc.s  0xC
0x154434  ldc.i4.0
0x154435  newobj   instance void System.Web.Configuration.UserMapPath::.ctor(class [System.Configuration]System.Configuration.ConfigurationFileMap fileMap, bool pathsAreLocal)
0x15443a  stelem.ref
0x15443b  dup
0x15443c  ldc.i4.3
0x15443d  ldloc.s  9
0x15443f  stelem.ref
0x154440  dup
0x154441  ldc.i4.4
0x154442  ldloc.s  0xA
0x154444  stelem.ref
0x154445  dup
0x154446  ldc.i4.5
0x154447  ldloc.s  0xB
0x154449  stelem.ref
0x15444a  callvirt instance void [System.Configuration]System.Configuration.Internal.DelegatingConfigHost::Init(class [System.Configuration]System.Configuration.Internal.IInternalConfigRoot, object[])
0x15444f  ldarg.0
0x154450  ldloc.s  0xE
0x154452  call     instance void [System.Configuration]System.Configuration.Internal.DelegatingConfigHost::set_Host(class [System.Configuration]System.Configuration.Internal.IInternalConfigHost)
0x154457  ret
```
