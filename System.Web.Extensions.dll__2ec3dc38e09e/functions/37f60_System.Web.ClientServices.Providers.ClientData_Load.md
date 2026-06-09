# System.Web.ClientServices.Providers.ClientData::Load

- ea: `0x37f60`
- end: `0x38030`
- name: `System.Web.ClientServices.Providers.ClientData::Load`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x380c0`
- `0x380e0`

## callees

- `0x37880`
- `0x378a0`
- `0x37940`
- `0x379f0`
- `0x37f60`

## string_xrefs

- `0x37f67`: `System.Web.Extensions.ClientServices.ClientData\`

## pseudocode

```c

```

## disassembly

```asm
0x37f60  ldnull
0x37f61  stloc.0
0x37f62  ldnull
0x37f63  stloc.1
0x37f64  ldarg.1
0x37f65  brfalse.s loc_37FC7
0x37f67  ldstr    aSystemWebExten_3// "System.Web.Extensions.ClientServices.Cl"...
0x37f6c  ldarg.0
0x37f6d  ldstr    aClientdata_0// ".clientdata"
0x37f72  call     string System.Web.ClientServices.Providers.SqlHelper::GetPartialDBFileName(string username, string extension)
0x37f77  call     string [mscorlib]System.String::Concat(string, string)
0x37f7c  stloc.1
0x37f7d  call     class [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile::GetUserStoreForAssembly()
0x37f82  stloc.2
0x37f83  ldloc.1
0x37f84  ldc.i4.3
0x37f85  ldloc.2
0x37f86  newobj   instance void [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, class [mscorlib]System.IO.IsolatedStorage.IsolatedStorageFile)
0x37f8b  stloc.3
0x37f8c  ldloc.3
0x37f8d  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x37f92  stloc.s  4
0x37f94  ldloc.s  4
0x37f96  newobj   instance void System.Web.ClientServices.Providers.ClientData::.ctor(class [System.Xml]System.Xml.XmlReader reader)
0x37f9b  stloc.0
0x37f9c  leave.s  loc_37FAA
0x37f9e  ldloc.s  4
0x37fa0  brfalse.s loc_37FA9
0x37fa2  ldloc.s  4
0x37fa4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37fa9  endfinally
0x37faa  leave.s  loc_37FB6
0x37fac  ldloc.3
0x37fad  brfalse.s loc_37FB5
0x37faf  ldloc.3
0x37fb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37fb5  endfinally
0x37fb6  leave.s  loc_37FC2
0x37fb8  ldloc.2
0x37fb9  brfalse.s loc_37FC1
0x37fbb  ldloc.2
0x37fbc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37fc1  endfinally
0x37fc2  leave.s  loc_38017
0x37fc4  pop
0x37fc5  leave.s  loc_38017
0x37fc7  ldarg.0
0x37fc8  ldstr    aClientdata_0// ".clientdata"
0x37fcd  call     string System.Web.ClientServices.Providers.SqlHelper::GetFullDBFileName(string username, string extension)
0x37fd2  stloc.1
0x37fd3  ldloc.1
0x37fd4  call     bool [mscorlib]System.IO.File::Exists(string)
0x37fd9  brfalse.s loc_38012
0x37fdb  ldloc.1
0x37fdc  ldc.i4.3
0x37fdd  ldc.i4.1
0x37fde  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x37fe3  stloc.s  5
0x37fe5  ldloc.s  5
0x37fe7  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x37fec  stloc.s  6
0x37fee  ldloc.s  6
0x37ff0  newobj   instance void System.Web.ClientServices.Providers.ClientData::.ctor(class [System.Xml]System.Xml.XmlReader reader)
0x37ff5  stloc.0
0x37ff6  leave.s  loc_38004
0x37ff8  ldloc.s  6
0x37ffa  brfalse.s loc_38003
0x37ffc  ldloc.s  6
0x37ffe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38003  endfinally
0x38004  leave.s  loc_38012
0x38006  ldloc.s  5
0x38008  brfalse.s loc_38011
0x3800a  ldloc.s  5
0x3800c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38011  endfinally
0x38012  leave.s  loc_38017
0x38014  pop
0x38015  leave.s  loc_38017
0x38017  ldloc.0
0x38018  brtrue.s loc_38020
0x3801a  newobj   instance void System.Web.ClientServices.Providers.ClientData::.ctor()
0x3801f  stloc.0
0x38020  ldloc.0
0x38021  ldarg.1
0x38022  stfld    bool System.Web.ClientServices.Providers.ClientData::UsingIsolatedStorage
0x38027  ldloc.0
0x38028  ldloc.1
0x38029  stfld    string System.Web.ClientServices.Providers.ClientData::FileName
0x3802e  ldloc.0
0x3802f  ret
```
