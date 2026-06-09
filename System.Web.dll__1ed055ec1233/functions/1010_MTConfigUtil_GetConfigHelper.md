# MTConfigUtil::GetConfigHelper

- ea: `0x1010`
- end: `0x110c`
- name: `MTConfigUtil::GetConfigHelper`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1010`
- `0x1150`
- `0x31240`
- `0x312b0`
- `0x313d0`
- `0x31460`
- `0x34f20`
- `0x161dd0`
- `0x161e00`
- `0x162230`

## string_xrefs

- `0x106d`: `system.web/compilation`
- `0x10e4`: `Config_section_not_supported`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldnull
0x1011  stloc.0
0x1012  ldarg.0
0x1013  ldnull
0x1014  call     bool System.Web.VirtualPath::op_Equality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x1019  brtrue.s loc_1023
0x101b  ldarg.0
0x101c  callvirt instance bool System.Web.VirtualPath::get_IsWithinAppRoot()
0x1021  brtrue.s loc_1032
0x1023  call     class System.Web.VirtualPath System.Web.Hosting.HostingEnvironment::get_ApplicationVirtualPathObject()
0x1028  starg.s  0
0x102a  call     string System.Web.Hosting.HostingEnvironment::get_ApplicationPhysicalPath()
0x102f  stloc.0
0x1030  br.s     loc_1049
0x1032  ldarg.0
0x1033  callvirt instance bool System.Web.VirtualPath::DirectoryExists()
0x1038  brtrue.s loc_1042
0x103a  ldarg.0
0x103b  callvirt instance class System.Web.VirtualPath System.Web.VirtualPath::get_Parent()
0x1040  starg.s  0
0x1042  ldarg.0
0x1043  call     string System.Web.Hosting.HostingEnvironment::MapPath(class System.Web.VirtualPath virtualPath)
0x1048  stloc.0
0x1049  ldarg.0
0x104a  ldloc.0
0x104b  call     class [System.Configuration]System.Configuration.Configuration MTConfigUtil::GetConfiguration(class System.Web.VirtualPath vpath, string physicalPath)
0x1050  stloc.1
0x1051  ldtoken  mvar<u1>
0x1056  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x105b  ldtoken  System.Web.Configuration.CompilationSection
0x1060  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1065  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x106a  brfalse.s loc_1082
0x106c  ldloc.1
0x106d  ldstr    aSystemWebCompi// "system.web/compilation"
0x1072  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x1077  isinst   mvar<u1>
0x107c  unbox.any mvar<u1>
0x1081  ret
0x1082  ldtoken  mvar<u1>
0x1087  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x108c  ldtoken  System.Web.Configuration.PagesSection
0x1091  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1096  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x109b  brfalse.s loc_10B3
0x109d  ldloc.1
0x109e  ldstr    aSystemWebPages// "system.web/pages"
0x10a3  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x10a8  isinst   mvar<u1>
0x10ad  unbox.any mvar<u1>
0x10b2  ret
0x10b3  ldtoken  mvar<u1>
0x10b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bd  ldtoken  System.Web.Configuration.ProfileSection
0x10c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10c7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x10cc  brfalse.s loc_10E4
0x10ce  ldloc.1
0x10cf  ldstr    aSystemWebProfi// "system.web/profile"
0x10d4  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x10d9  isinst   mvar<u1>
0x10de  unbox.any mvar<u1>
0x10e3  ret
0x10e4  ldstr    aConfigSectionN// "Config_section_not_supported"
0x10e9  ldc.i4.1
0x10ea  newarr   [mscorlib]System.Object
0x10ef  dup
0x10f0  ldc.i4.0
0x10f1  ldtoken  mvar<u1>
0x10f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10fb  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1100  stelem.ref
0x1101  call     string System.Web.SR::GetString(string name, object[] args)
0x1106  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x110b  throw
```
