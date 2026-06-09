# System.Web.Configuration.CompilationSection::LoadAssemblyHelper

- ea: `0x13fa50`
- end: `0x13fb96`
- name: `System.Web.Configuration.CompilationSection::LoadAssemblyHelper`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13f8d0`
- `0x13fba0`

## callees

- `0x34f20`
- `0x130b10`
- `0x13f2b0`
- `0x13fa50`
- `0x1772a0`

## string_xrefs

- `0x13faa9`: `Config_base_file_load_exception_no_message`
- `0x13facd`: `Config_base_bad_image_exception_no_message`
- `0x13fae5`: `Config_base_report_exception_type`

## pseudocode

```c

```

## disassembly

```asm
0x13fa50  ldnull
0x13fa51  stloc.0
0x13fa52  ldarg.1
0x13fa53  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x13fa58  stloc.0
0x13fa59  leave    loc_13FB94
0x13fa5e  stloc.1
0x13fa5f  ldc.i4.0
0x13fa60  stloc.2
0x13fa61  ldarg.2
0x13fa62  brfalse.s loc_13FA75
0x13fa64  ldloc.1
0x13fa65  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x13fa6a  stloc.3
0x13fa6b  ldloc.3
0x13fa6c  ldc.i4   0x80131018
0x13fa71  bne.un.s loc_13FA75
0x13fa73  ldc.i4.1
0x13fa74  stloc.2
0x13fa75  call     bool System.Web.Compilation.BuildManager::get_IgnoreBadImageFormatException()
0x13fa7a  brfalse.s loc_13FA8A
0x13fa7c  ldloc.1
0x13fa7d  isinst   [mscorlib]System.BadImageFormatException
0x13fa82  stloc.s  4
0x13fa84  ldloc.s  4
0x13fa86  brfalse.s loc_13FA8A
0x13fa88  ldc.i4.1
0x13fa89  stloc.2
0x13fa8a  ldloc.2
0x13fa8b  brtrue   loc_13FB92
0x13fa90  ldloc.1
0x13fa91  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13fa96  stloc.s  5
0x13fa98  ldloc.s  5
0x13fa9a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13fa9f  brfalse.s loc_13FB05
0x13faa1  ldloc.1
0x13faa2  isinst   [mscorlib]System.IO.FileLoadException
0x13faa7  brfalse.s loc_13FAC5
0x13faa9  ldstr    aConfigBaseFile// "Config_base_file_load_exception_no_mess"...
0x13faae  ldc.i4.1
0x13faaf  newarr   [mscorlib]System.Object
0x13fab4  dup
0x13fab5  ldc.i4.0
0x13fab6  ldstr    aAssembly// "assembly"
0x13fabb  stelem.ref
0x13fabc  call     string System.Web.SR::GetString(string name, object[] args)
0x13fac1  stloc.s  5
0x13fac3  br.s     loc_13FB05
0x13fac5  ldloc.1
0x13fac6  isinst   [mscorlib]System.BadImageFormatException
0x13facb  brfalse.s loc_13FAE5
0x13facd  ldstr    aConfigBaseBadI// "Config_base_bad_image_exception_no_mess"...
0x13fad2  ldc.i4.1
0x13fad3  newarr   [mscorlib]System.Object
0x13fad8  dup
0x13fad9  ldc.i4.0
0x13fada  ldarg.1
0x13fadb  stelem.ref
0x13fadc  call     string System.Web.SR::GetString(string name, object[] args)
0x13fae1  stloc.s  5
0x13fae3  br.s     loc_13FB05
0x13fae5  ldstr    aConfigBaseRepo// "Config_base_report_exception_type"
0x13faea  ldc.i4.1
0x13faeb  newarr   [mscorlib]System.Object
0x13faf0  dup
0x13faf1  ldc.i4.0
0x13faf2  ldloc.1
0x13faf3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x13faf8  callvirt instance string [mscorlib]System.Object::ToString()
0x13fafd  stelem.ref
0x13fafe  call     string System.Web.SR::GetString(string name, object[] args)
0x13fb03  stloc.s  5
0x13fb05  ldarg.0
0x13fb06  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fb0b  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13fb10  ldstr    aAssemblies// "assemblies"
0x13fb15  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13fb1a  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13fb1f  stloc.s  6
0x13fb21  ldarg.0
0x13fb22  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fb27  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13fb2c  ldstr    aAssemblies// "assemblies"
0x13fb31  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13fb36  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13fb3b  stloc.s  7
0x13fb3d  ldarg.2
0x13fb3e  brfalse.s loc_13FB47
0x13fb40  ldstr    asc_1B483C// "*"
0x13fb45  starg.s  1
0x13fb47  ldarg.0
0x13fb48  call     instance class System.Web.Configuration.AssemblyCollection System.Web.Configuration.CompilationSection::get_Assemblies()
0x13fb4d  ldarg.1
0x13fb4e  callvirt instance class System.Web.Configuration.AssemblyInfo System.Web.Configuration.AssemblyCollection::get_Item(string assemblyName)
0x13fb53  brfalse.s loc_13FB85
0x13fb55  ldarg.0
0x13fb56  call     instance class System.Web.Configuration.AssemblyCollection System.Web.Configuration.CompilationSection::get_Assemblies()
0x13fb5b  ldarg.1
0x13fb5c  callvirt instance class System.Web.Configuration.AssemblyInfo System.Web.Configuration.AssemblyCollection::get_Item(string assemblyName)
0x13fb61  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fb66  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x13fb6b  stloc.s  6
0x13fb6d  ldarg.0
0x13fb6e  call     instance class System.Web.Configuration.AssemblyCollection System.Web.Configuration.CompilationSection::get_Assemblies()
0x13fb73  ldarg.1
0x13fb74  callvirt instance class System.Web.Configuration.AssemblyInfo System.Web.Configuration.AssemblyCollection::get_Item(string assemblyName)
0x13fb79  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13fb7e  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x13fb83  stloc.s  7
0x13fb85  ldloc.s  5
0x13fb87  ldloc.1
0x13fb88  ldloc.s  6
0x13fb8a  ldloc.s  7
0x13fb8c  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x13fb91  throw
0x13fb92  leave.s  loc_13FB94
0x13fb94  ldloc.0
0x13fb95  ret
```
