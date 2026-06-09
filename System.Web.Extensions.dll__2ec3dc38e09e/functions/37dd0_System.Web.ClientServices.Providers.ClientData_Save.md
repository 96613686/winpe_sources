# System.Web.ClientServices.Providers.ClientData::Save

- ea: `0x37dd0`
- end: `0x37e53`
- name: `System.Web.ClientServices.Providers.ClientData::Save`
- size: `131`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x340f0`
- `0x34280`
- `0x34c20`
- `0x34d20`
- `0x36150`
- `0x36480`
- `0x36530`
- `0x38170`

## callees

- `0x37dd0`
- `0x37e60`

## string_xrefs

- `0x37dfe`: `System.Web.Extensions.ClientServices.ClientData`
- `0x37e0c`: `System.Web.Extensions.ClientServices.ClientData`

## pseudocode

```c

```

## disassembly

```asm
0x37dd0  ldarg.0
0x37dd1  ldfld    bool System.Web.ClientServices.Providers.ClientData::UsingIsolatedStorage
0x37dd6  brtrue.s loc_37DF7
0x37dd8  ldarg.0
0x37dd9  ldfld    string System.Web.ClientServices.Providers.ClientData::FileName
0x37dde  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(string)
0x37de3  stloc.0
0x37de4  ldarg.0
0x37de5  ldloc.0
0x37de6  call     instance void System.Web.ClientServices.Providers.ClientData::Save(class [System.Xml]System.Xml.XmlWriter writer)
0x37deb  leave.s  loc_37E52
0x37ded  ldloc.0
0x37dee  brfalse.s loc_37DF6
0x37df0  ldloc.0
0x37df1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37df6  endfinally
0x37df7  call     class [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile::GetUserStoreForAssembly()
0x37dfc  stloc.1
0x37dfd  ldloc.1
0x37dfe  ldstr    aSystemWebExten_2// "System.Web.Extensions.ClientServices.Cl"...
0x37e03  callvirt instance string[] [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile::GetDirectoryNames(string)
0x37e08  ldlen
0x37e09  brtrue.s loc_37E16
0x37e0b  ldloc.1
0x37e0c  ldstr    aSystemWebExten_2// "System.Web.Extensions.ClientServices.Cl"...
0x37e11  callvirt instance void [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile::CreateDirectory(string)
0x37e16  ldarg.0
0x37e17  ldfld    string System.Web.ClientServices.Providers.ClientData::FileName
0x37e1c  ldc.i4.2
0x37e1d  ldloc.1
0x37e1e  newobj   instance void [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, class [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile)
0x37e23  stloc.2
0x37e24  ldloc.2
0x37e25  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream)
0x37e2a  stloc.3
0x37e2b  ldarg.0
0x37e2c  ldloc.3
0x37e2d  call     instance void System.Web.ClientServices.Providers.ClientData::Save(class [System.Xml]System.Xml.XmlWriter writer)
0x37e32  leave.s  loc_37E52
0x37e34  ldloc.3
0x37e35  brfalse.s loc_37E3D
0x37e37  ldloc.3
0x37e38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37e3d  endfinally
0x37e3e  ldloc.2
0x37e3f  brfalse.s loc_37E47
0x37e41  ldloc.2
0x37e42  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37e47  endfinally
0x37e48  ldloc.1
0x37e49  brfalse.s loc_37E51
0x37e4b  ldloc.1
0x37e4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37e51  endfinally
0x37e52  ret
```
