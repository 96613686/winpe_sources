# System.Web.Compilation.BuildManagerHost::GetGeneratedSourceFile

- ea: `0x177fa0`
- end: `0x177ffb`
- name: `System.Web.Compilation.BuildManagerHost::GetGeneratedSourceFile`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x17c280`

## callees

- `0x30f70`
- `0x30ff0`
- `0x31240`
- `0x34f20`
- `0x174e70`
- `0x177e10`
- `0x177e20`
- `0x177ed0`
- `0x177fa0`

## string_xrefs

- `0x177fc7`: `virtualPath`
- `0x177fae`: `GetGeneratedSourceFile_Directory_Only`

## pseudocode

```c

```

## disassembly

```asm
0x177fa0  ldarg.0
0x177fa1  call     instance void System.Web.Compilation.BuildManagerHost::AddPendingCall()
0x177fa6  ldarg.1
0x177fa7  callvirt instance bool System.Web.VirtualPath::DirectoryExists()
0x177fac  brtrue.s loc_177FD2
0x177fae  ldstr    aGetgeneratedso// "GetGeneratedSourceFile_Directory_Only"
0x177fb3  ldc.i4.1
0x177fb4  newarr   [mscorlib]System.Object
0x177fb9  dup
0x177fba  ldc.i4.0
0x177fbb  ldarg.1
0x177fbc  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x177fc1  stelem.ref
0x177fc2  call     string System.Web.SR::GetString(string name, object[] args)
0x177fc7  ldstr    aVirtualpath_0// "virtualPath"
0x177fcc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x177fd1  throw
0x177fd2  ldarg.0
0x177fd3  ldarg.1
0x177fd4  ldloca.s 0
0x177fd6  ldloca.s 1
0x177fd8  ldloca.s 2
0x177fda  call     instance void System.Web.Compilation.BuildManagerHost::GetCodeDirectoryInformation(class System.Web.VirtualPath virtualCodeDir, [out] class [mscorlib]System.Type& codeDomProviderType, [out] class [System]System.CodeDom.Compiler.CompilerParameters& compParams, [out] string& generatedFilesDir)
0x177fdf  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Web.Compilation.BuildManager::get_GenerateFileTable()
0x177fe4  ldarg.1
0x177fe5  callvirt instance string System.Web.VirtualPath::get_VirtualPathStringNoTrailingSlash()
0x177fea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x177fef  stloc.3
0x177ff0  leave.s  loc_177FF9
0x177ff2  ldarg.0
0x177ff3  call     instance void System.Web.Compilation.BuildManagerHost::RemovePendingCall()
0x177ff8  endfinally
0x177ff9  ldloc.3
0x177ffa  ret
```
