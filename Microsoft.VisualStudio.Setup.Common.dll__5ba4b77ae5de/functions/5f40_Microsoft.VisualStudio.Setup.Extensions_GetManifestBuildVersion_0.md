# Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion_0

- ea: `0x5f40`
- end: `0x5faa`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion_0`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x2970`
- `0x5e80`

## callees

- `0x2db0`
- `0x2dd0`
- `0x2e90`
- `0x5f40`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x5f40  ldarg.0
0x5f41  ldstr    aInfo// "info"
0x5f46  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5f4b  ldarg.0
0x5f4c  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CatalogInfo::get_BuildVersion()
0x5f51  ldnull
0x5f52  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x5f57  brfalse.s loc_5F60
0x5f59  ldarg.0
0x5f5a  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CatalogInfo::get_BuildVersion()
0x5f5f  ret
0x5f60  ldarg.0
0x5f61  callvirt instance string Microsoft.VisualStudio.Setup.CatalogInfo::get_BuildNumber()
0x5f66  dup
0x5f67  brtrue.s loc_5F6F
0x5f69  pop
0x5f6a  ldsfld   string [mscorlib]System.String::Empty
0x5f6f  dup
0x5f70  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CatalogInfo::ParseVersionOrNull(string value)
0x5f75  dup
0x5f76  brtrue.s loc_5F7E
0x5f78  pop
0x5f79  ldsfld   class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Utilities::DefaultManifestVersion
0x5f7e  stloc.0
0x5f7f  ldc.i4.1
0x5f80  newarr   [mscorlib]System.Char
0x5f85  dup
0x5f86  ldc.i4.0
0x5f87  ldc.i4.s 0x2E
0x5f89  stelem.i2
0x5f8a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x5f8f  ldlen
0x5f90  conv.i4
0x5f91  ldc.i4.2
0x5f92  bne.un.s loc_5FA8
0x5f94  ldc.i4.0
0x5f95  ldc.i4.0
0x5f96  ldloc.0
0x5f97  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x5f9c  ldloc.0
0x5f9d  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x5fa2  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x5fa7  stloc.0
0x5fa8  ldloc.0
0x5fa9  ret
```
