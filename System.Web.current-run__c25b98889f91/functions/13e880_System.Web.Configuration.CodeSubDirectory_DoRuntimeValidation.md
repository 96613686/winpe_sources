# System.Web.Configuration.CodeSubDirectory::DoRuntimeValidation

- ea: `0x13e880`
- end: `0x13ea0a`
- name: `System.Web.Configuration.CodeSubDirectory::DoRuntimeValidation`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x13e770`

## callees

- `0x24720`
- `0x31160`
- `0x311e0`
- `0x34f20`
- `0x54d20`
- `0x54d50`
- `0x58d50`
- `0x84fa0`
- `0x13e840`
- `0x13e880`
- `0x16cdc0`
- `0x175710`
- `0x177350`

## string_xrefs

- `0x13e8b6`: `directoryName`
- `0x13e8d0`: `directoryName`
- `0x13e918`: `directoryName`
- `0x13e932`: `directoryName`
- `0x13e984`: `directoryName`
- `0x13e99e`: `directoryName`
- `0x13e9da`: `directoryName`
- `0x13e9f4`: `directoryName`
- `0x13e897`: `Invalid_CodeSubDirectory`
- `0x13e965`: `Invalid_CodeSubDirectory`
- `0x13e8f9`: `Invalid_CodeSubDirectory_Not_Exist`

## pseudocode

```c

```

## disassembly

```asm
0x13e880  ldarg.0
0x13e881  call     instance string System.Web.Configuration.CodeSubDirectory::get_DirectoryName()
0x13e886  stloc.0
0x13e887  call     bool System.Web.Compilation.BuildManager::get_IsPrecompiledApp()
0x13e88c  brfalse.s loc_13E88F
0x13e88e  ret
0x13e88f  ldloc.0
0x13e890  call     bool System.Web.UI.Util::IsValidFileName(string fileName)
0x13e895  brtrue.s loc_13E8E5
0x13e897  ldstr    aInvalidCodesub// "Invalid_CodeSubDirectory"
0x13e89c  ldc.i4.1
0x13e89d  newarr   [mscorlib]System.Object
0x13e8a2  dup
0x13e8a3  ldc.i4.0
0x13e8a4  ldloc.0
0x13e8a5  stelem.ref
0x13e8a6  call     string System.Web.SR::GetString(string name, object[] args)
0x13e8ab  ldarg.0
0x13e8ac  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e8b1  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e8b6  ldstr    aDirectoryname// "directoryName"
0x13e8bb  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e8c0  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13e8c5  ldarg.0
0x13e8c6  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e8cb  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e8d0  ldstr    aDirectoryname// "directoryName"
0x13e8d5  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e8da  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13e8df  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13e8e4  throw
0x13e8e5  call     class System.Web.VirtualPath System.Web.HttpRuntime::get_CodeDirectoryVirtualPath()
0x13e8ea  ldloc.0
0x13e8eb  callvirt instance class System.Web.VirtualPath System.Web.VirtualPath::SimpleCombineWithDir(string directoryName)
0x13e8f0  stloc.1
0x13e8f1  ldloc.1
0x13e8f2  call     bool System.Web.Hosting.VirtualPathProvider::DirectoryExistsNoThrow(class System.Web.VirtualPath virtualDir)
0x13e8f7  brtrue.s loc_13E947
0x13e8f9  ldstr    aInvalidCodesub_0// "Invalid_CodeSubDirectory_Not_Exist"
0x13e8fe  ldc.i4.1
0x13e8ff  newarr   [mscorlib]System.Object
0x13e904  dup
0x13e905  ldc.i4.0
0x13e906  ldloc.1
0x13e907  stelem.ref
0x13e908  call     string System.Web.SR::GetString(string name, object[] args)
0x13e90d  ldarg.0
0x13e90e  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e913  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e918  ldstr    aDirectoryname// "directoryName"
0x13e91d  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e922  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13e927  ldarg.0
0x13e928  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e92d  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e932  ldstr    aDirectoryname// "directoryName"
0x13e937  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e93c  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13e941  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13e946  throw
0x13e947  ldloc.1
0x13e948  callvirt instance string System.Web.VirtualPath::MapPathInternal()
0x13e94d  stloc.2
0x13e94e  ldloc.2
0x13e94f  ldloca.s 3
0x13e951  call     int32 System.Web.Util.FindFileData::FindFile(string path, [out] class System.Web.Util.FindFileData& data)
0x13e956  pop
0x13e957  ldloc.0
0x13e958  ldloc.3
0x13e959  callvirt instance string System.Web.Util.FindFileData::get_FileNameLong()
0x13e95e  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x13e963  brtrue.s loc_13E9B3
0x13e965  ldstr    aInvalidCodesub// "Invalid_CodeSubDirectory"
0x13e96a  ldc.i4.1
0x13e96b  newarr   [mscorlib]System.Object
0x13e970  dup
0x13e971  ldc.i4.0
0x13e972  ldloc.0
0x13e973  stelem.ref
0x13e974  call     string System.Web.SR::GetString(string name, object[] args)
0x13e979  ldarg.0
0x13e97a  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e97f  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e984  ldstr    aDirectoryname// "directoryName"
0x13e989  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e98e  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13e993  ldarg.0
0x13e994  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e999  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e99e  ldstr    aDirectoryname// "directoryName"
0x13e9a3  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e9a8  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13e9ad  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13e9b2  throw
0x13e9b3  ldloc.0
0x13e9b4  call     bool System.Web.Compilation.BuildManager::IsReservedAssemblyName(string assemblyName)
0x13e9b9  brfalse.s loc_13EA09
0x13e9bb  ldstr    aReservedAssemb// "Reserved_AssemblyName"
0x13e9c0  ldc.i4.1
0x13e9c1  newarr   [mscorlib]System.Object
0x13e9c6  dup
0x13e9c7  ldc.i4.0
0x13e9c8  ldloc.0
0x13e9c9  stelem.ref
0x13e9ca  call     string System.Web.SR::GetString(string name, object[] args)
0x13e9cf  ldarg.0
0x13e9d0  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e9d5  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e9da  ldstr    aDirectoryname// "directoryName"
0x13e9df  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e9e4  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13e9e9  ldarg.0
0x13e9ea  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13e9ef  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13e9f4  ldstr    aDirectoryname// "directoryName"
0x13e9f9  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13e9fe  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13ea03  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13ea08  throw
0x13ea09  ret
```
