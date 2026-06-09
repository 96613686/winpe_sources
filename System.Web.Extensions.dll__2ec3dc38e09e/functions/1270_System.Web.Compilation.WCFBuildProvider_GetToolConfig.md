# System.Web.Compilation.WCFBuildProvider::GetToolConfig

- ea: `0x1270`
- end: `0x130b`
- name: `System.Web.Compilation.WCFBuildProvider::GetToolConfig`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdd0`

## callees

- `0x1270`
- `0x1ca0`
- `0x1d40`
- `0x20c0`

## string_xrefs

- `0x1296`: `Reference.config`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldnull
0x1271  stloc.0
0x1272  ldarg.1
0x1273  brfalse.s loc_12C4
0x1275  ldarg.2
0x1276  brfalse.s loc_12C4
0x1278  ldarg.1
0x1279  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile> System.Web.Compilation.WCFModel.MapFile::get_Extensions()
0x127e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile>::GetEnumerator()
0x1283  stloc.3
0x1284  br.s     loc_12AB
0x1286  ldloca.s 3
0x1288  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.Compilation.WCFModel.ExtensionFile>::get_Current()
0x128d  stloc.s  4
0x128f  ldloc.s  4
0x1291  callvirt instance string System.Web.Compilation.WCFModel.ExtensionFile::get_Name()
0x1296  ldstr    aReferenceConfi// "Reference.config"
0x129b  ldc.i4.4
0x129c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x12a1  brfalse.s loc_12AB
0x12a3  ldloc.s  4
0x12a5  callvirt instance string System.Web.Compilation.WCFModel.ExternalFile::get_FileName()
0x12aa  stloc.0
0x12ab  ldloca.s 3
0x12ad  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.Compilation.WCFModel.ExtensionFile>::MoveNext()
0x12b2  brtrue.s loc_1286
0x12b4  leave.s  loc_12C4
0x12b6  ldloca.s 3
0x12b8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.Compilation.WCFModel.ExtensionFile>
0x12be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c3  endfinally
0x12c4  newobj   instance void [System.Web]System.Web.Configuration.WebConfigurationFileMap::.ctor()
0x12c9  stloc.1
0x12ca  ldloc.0
0x12cb  brfalse.s loc_12DD
0x12cd  ldarg.2
0x12ce  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x12d3  ldc.i4.1
0x12d4  ldloc.0
0x12d5  newobj   instance void [System.Web]System.Web.Configuration.VirtualDirectoryMapping::.ctor(string, bool, string)
0x12da  stloc.2
0x12db  br.s     loc_12E9
0x12dd  call     string [System.Web]System.Web.Hosting.HostingEnvironment::get_ApplicationPhysicalPath()
0x12e2  ldc.i4.1
0x12e3  newobj   instance void [System.Web]System.Web.Configuration.VirtualDirectoryMapping::.ctor(string, bool)
0x12e8  stloc.2
0x12e9  ldloc.1
0x12ea  callvirt instance class [System.Web]System.Web.Configuration.VirtualDirectoryMappingCollection [System.Web]System.Web.Configuration.WebConfigurationFileMap::get_VirtualDirectories()
0x12ef  ldstr    asc_3D26E// "/"
0x12f4  ldloc.2
0x12f5  callvirt instance void [System.Web]System.Web.Configuration.VirtualDirectoryMappingCollection::Add(string, class [System.Web]System.Web.Configuration.VirtualDirectoryMapping)
0x12fa  ldloc.1
0x12fb  ldstr    asc_3D26E// "/"
0x1300  call     string [System.Web]System.Web.Hosting.HostingEnvironment::get_SiteName()
0x1305  call     class [System.Configuration]System.Configuration.Configuration [System.Web]System.Web.Configuration.WebConfigurationManager::OpenMappedWebConfiguration(class [System.Web]System.Web.Configuration.WebConfigurationFileMap, string, string)
0x130a  ret
```
