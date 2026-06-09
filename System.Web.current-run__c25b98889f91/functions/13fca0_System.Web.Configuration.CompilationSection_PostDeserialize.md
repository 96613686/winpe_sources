# System.Web.Configuration.CompilationSection::PostDeserialize

- ea: `0x13fca0`
- end: `0x13fdc4`
- name: `System.Web.Configuration.CompilationSection::PostDeserialize`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x34f20`
- `0x13f2f0`
- `0x13f330`
- `0x13f470`
- `0x13fca0`
- `0x15c490`

## string_xrefs

- `0x13fcd6`: `Config_element_below_app_illegal`
- `0x13fd2b`: `Config_element_below_app_illegal`
- `0x13fd80`: `Config_element_below_app_illegal`

## pseudocode

```c

```

## disassembly

```asm
0x13fca0  ldarg.0
0x13fca1  call     instance class [System.Configuration]System.Configuration.ContextInformation [System.Configuration]System.Configuration.ConfigurationElement::get_EvaluationContext()
0x13fca6  callvirt instance object [System.Configuration]System.Configuration.ContextInformation::get_HostingContext()
0x13fcab  isinst   System.Web.Configuration.WebContext
0x13fcb0  stloc.0
0x13fcb1  ldloc.0
0x13fcb2  brfalse  loc_13FDC3
0x13fcb7  ldloc.0
0x13fcb8  callvirt instance valuetype System.Web.Configuration.WebApplicationLevel System.Web.Configuration.WebContext::get_ApplicationLevel()
0x13fcbd  ldc.i4.s 0x1E
0x13fcbf  bne.un   loc_13FDC3
0x13fcc4  ldarg.0
0x13fcc5  call     instance class System.Web.Configuration.CodeSubDirectoriesCollection System.Web.Configuration.CompilationSection::get_CodeSubDirectories()
0x13fcca  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fccf  callvirt instance bool [System.Configuration]System.Configuration.ElementInformation::get_IsPresent()
0x13fcd4  brfalse.s loc_13FD19
0x13fcd6  ldstr    aConfigElementB// "Config_element_below_app_illegal"
0x13fcdb  ldc.i4.1
0x13fcdc  newarr   [mscorlib]System.Object
0x13fce1  dup
0x13fce2  ldc.i4.0
0x13fce3  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propCodeSubDirs
0x13fce8  callvirt instance string [System.Configuration]System.Configuration.ConfigurationProperty::get_Name()
0x13fced  stelem.ref
0x13fcee  call     string System.Web.SR::GetString(string name, object[] args)
0x13fcf3  ldarg.0
0x13fcf4  call     instance class System.Web.Configuration.CodeSubDirectoriesCollection System.Web.Configuration.CompilationSection::get_CodeSubDirectories()
0x13fcf9  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fcfe  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x13fd03  ldarg.0
0x13fd04  call     instance class System.Web.Configuration.CodeSubDirectoriesCollection System.Web.Configuration.CompilationSection::get_CodeSubDirectories()
0x13fd09  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fd0e  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x13fd13  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13fd18  throw
0x13fd19  ldarg.0
0x13fd1a  call     instance class System.Web.Configuration.BuildProviderCollection System.Web.Configuration.CompilationSection::get_BuildProviders()
0x13fd1f  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fd24  callvirt instance bool [System.Configuration]System.Configuration.ElementInformation::get_IsPresent()
0x13fd29  brfalse.s loc_13FD6E
0x13fd2b  ldstr    aConfigElementB// "Config_element_below_app_illegal"
0x13fd30  ldc.i4.1
0x13fd31  newarr   [mscorlib]System.Object
0x13fd36  dup
0x13fd37  ldc.i4.0
0x13fd38  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propBuildProviders
0x13fd3d  callvirt instance string [System.Configuration]System.Configuration.ConfigurationProperty::get_Name()
0x13fd42  stelem.ref
0x13fd43  call     string System.Web.SR::GetString(string name, object[] args)
0x13fd48  ldarg.0
0x13fd49  call     instance class System.Web.Configuration.BuildProviderCollection System.Web.Configuration.CompilationSection::get_BuildProviders()
0x13fd4e  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fd53  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x13fd58  ldarg.0
0x13fd59  call     instance class System.Web.Configuration.BuildProviderCollection System.Web.Configuration.CompilationSection::get_BuildProviders()
0x13fd5e  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fd63  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x13fd68  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13fd6d  throw
0x13fd6e  ldarg.0
0x13fd6f  call     instance class System.Web.Configuration.FolderLevelBuildProviderCollection System.Web.Configuration.CompilationSection::get_FolderLevelBuildProviders()
0x13fd74  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fd79  callvirt instance bool [System.Configuration]System.Configuration.ElementInformation::get_IsPresent()
0x13fd7e  brfalse.s loc_13FDC3
0x13fd80  ldstr    aConfigElementB// "Config_element_below_app_illegal"
0x13fd85  ldc.i4.1
0x13fd86  newarr   [mscorlib]System.Object
0x13fd8b  dup
0x13fd8c  ldc.i4.0
0x13fd8d  ldsfld   class [System.Configuration]System.Configuration.ConfigurationProperty System.Web.Configuration.CompilationSection::_propFolderLevelBuildProviders
0x13fd92  callvirt instance string [System.Configuration]System.Configuration.ConfigurationProperty::get_Name()
0x13fd97  stelem.ref
0x13fd98  call     string System.Web.SR::GetString(string name, object[] args)
0x13fd9d  ldarg.0
0x13fd9e  call     instance class System.Web.Configuration.FolderLevelBuildProviderCollection System.Web.Configuration.CompilationSection::get_FolderLevelBuildProviders()
0x13fda3  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fda8  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x13fdad  ldarg.0
0x13fdae  call     instance class System.Web.Configuration.FolderLevelBuildProviderCollection System.Web.Configuration.CompilationSection::get_FolderLevelBuildProviders()
0x13fdb3  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fdb8  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x13fdbd  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x13fdc2  throw
0x13fdc3  ret
```
