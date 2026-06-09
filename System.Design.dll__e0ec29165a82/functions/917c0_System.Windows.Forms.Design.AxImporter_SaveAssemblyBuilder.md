# System.Windows.Forms.Design.AxImporter::SaveAssemblyBuilder

- ea: `0x917c0`
- end: `0x918a5`
- name: `System.Windows.Forms.Design.AxImporter::SaveAssemblyBuilder`
- size: `229`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x91210`
- `0x1129f0`

## callees

- `0x8eec0`
- `0x90910`
- `0x90940`
- `0x90a50`
- `0x917c0`

## string_xrefs

- `0x91807`: `AXCannotOverwriteFile`
- `0x91861`: `AXCannotOverwriteFile`
- `0x91831`: `AXReadOnlyFile`

## pseudocode

```c

```

## disassembly

```asm
0x917c0  ldnull
0x917c1  stloc.0
0x917c2  ldarg.3
0x917c3  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x917c8  stloc.1
0x917c9  ldloc.1
0x917ca  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x917cf  stloc.2
0x917d0  ldloc.1
0x917d1  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x917d6  brfalse  loc_91880
0x917db  ldarg.0
0x917dc  ldfld    class Options System.Windows.Forms.Design.AxImporter::options
0x917e1  ldfld    bool Options::overwriteRCW
0x917e6  brfalse  loc_91887
0x917eb  ldarg.0
0x917ec  ldfld    string System.Windows.Forms.Design.AxImporter::typeLibName
0x917f1  brfalse.s loc_91826
0x917f3  ldarg.0
0x917f4  ldfld    string System.Windows.Forms.Design.AxImporter::typeLibName
0x917f9  ldloc.1
0x917fa  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x917ff  ldc.i4.5
0x91800  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x91805  brfalse.s loc_91826
0x91807  ldstr    aAxcannotoverwr// "AXCannotOverwriteFile"
0x9180c  ldc.i4.1
0x9180d  newarr   [mscorlib]System.Object
0x91812  dup
0x91813  ldc.i4.0
0x91814  ldloc.1
0x91815  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x9181a  stelem.ref
0x9181b  call     string System.Design.SR::GetString(string name, object[] args)
0x91820  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x91825  throw
0x91826  ldloc.1
0x91827  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x9182c  ldc.i4.1
0x9182d  and
0x9182e  ldc.i4.1
0x9182f  bne.un.s loc_91850
0x91831  ldstr    aAxreadonlyfile// "AXReadOnlyFile"
0x91836  ldc.i4.1
0x91837  newarr   [mscorlib]System.Object
0x9183c  dup
0x9183d  ldc.i4.0
0x9183e  ldloc.1
0x9183f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x91844  stelem.ref
0x91845  call     string System.Design.SR::GetString(string name, object[] args)
0x9184a  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x9184f  throw
0x91850  nop
0x91851  ldloc.1
0x91852  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x91857  ldarg.2
0x91858  ldloc.2
0x91859  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::Save(string)
0x9185e  leave.s  loc_91887
0x91860  stloc.3
0x91861  ldstr    aAxcannotoverwr// "AXCannotOverwriteFile"
0x91866  ldc.i4.1
0x91867  newarr   [mscorlib]System.Object
0x9186c  dup
0x9186d  ldc.i4.0
0x9186e  ldloc.1
0x9186f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x91874  stelem.ref
0x91875  call     string System.Design.SR::GetString(string name, object[] args)
0x9187a  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x9187f  throw
0x91880  ldarg.2
0x91881  ldloc.2
0x91882  callvirt instance void [mscorlib]System.Reflection.Emit.AssemblyBuilder::Save(string)
0x91887  ldloc.1
0x91888  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x9188d  stloc.0
0x9188e  ldarg.0
0x9188f  ldloc.0
0x91890  call     instance void System.Windows.Forms.Design.AxImporter::AddReferencedAssembly(string assem)
0x91895  ldarg.0
0x91896  ldarg.1
0x91897  call     instance void System.Windows.Forms.Design.AxImporter::AddTypeLibAttr(class [mscorlib]System.Runtime.InteropServices.ComTypes.ITypeLib typeLib)
0x9189c  ldarg.0
0x9189d  ldloc.0
0x9189e  call     instance void System.Windows.Forms.Design.AxImporter::AddGeneratedAssembly(string assem)
0x918a3  ldloc.0
0x918a4  ret
```
