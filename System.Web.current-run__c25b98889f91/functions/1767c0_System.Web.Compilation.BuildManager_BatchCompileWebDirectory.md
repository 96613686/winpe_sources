# System.Web.Compilation.BuildManager::BatchCompileWebDirectory

- ea: `0x1767c0`
- end: `0x176835`
- name: `System.Web.Compilation.BuildManager::BatchCompileWebDirectory`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1764e0`
- `0x1773d0`

## callees

- `0x31460`
- `0x56d90`
- `0x56e20`
- `0x56f30`
- `0x162510`
- `0x16cc70`
- `0x16ce10`
- `0x16ce20`
- `0x1767c0`
- `0x176840`

## string_xrefs

- `0x1767e1`: `BatchCompileChk`
- `0x1767fa`: `BatchCompileChk`

## pseudocode

```c

```

## disassembly

```asm
0x1767c0  ldarg.2
0x1767c1  ldnull
0x1767c2  call     bool System.Web.VirtualPath::op_Equality(class System.Web.VirtualPath v1, class System.Web.VirtualPath v2)
0x1767c7  brfalse.s loc_1767D1
0x1767c9  ldarg.1
0x1767ca  callvirt instance class System.Web.VirtualPath System.Web.Hosting.VirtualFileBase::get_VirtualPathObject()
0x1767cf  starg.s  2
0x1767d1  ldarg.1
0x1767d2  brtrue.s loc_1767E1
0x1767d4  call     class System.Web.Hosting.VirtualPathProvider System.Web.Hosting.HostingEnvironment::get_VirtualPathProvider()
0x1767d9  ldarg.2
0x1767da  callvirt instance class System.Web.Hosting.VirtualDirectory System.Web.Hosting.VirtualPathProvider::GetDirectory(class System.Web.VirtualPath virtualDir)
0x1767df  starg.s  1
0x1767e1  ldstr    aBatchcompilech// "BatchCompileChk"
0x1767e6  call     object [mscorlib]System.Runtime.Remoting.Messaging.CallContext::GetData(string)
0x1767eb  isinst   System.Web.Util.CaseInsensitiveStringSet
0x1767f0  stloc.0
0x1767f1  ldloc.0
0x1767f2  brtrue.s loc_176805
0x1767f4  newobj   instance void System.Web.Util.CaseInsensitiveStringSet::.ctor()
0x1767f9  stloc.0
0x1767fa  ldstr    aBatchcompilech// "BatchCompileChk"
0x1767ff  ldloc.0
0x176800  call     void [mscorlib]System.Runtime.Remoting.Messaging.CallContext::SetData(string, object)
0x176805  ldloc.0
0x176806  ldarg.1
0x176807  callvirt instance string System.Web.Hosting.VirtualFileBase::get_VirtualPath()
0x17680c  callvirt instance bool System.Web.Util.ObjectSet::Contains(object o)
0x176811  brfalse.s loc_176815
0x176813  ldc.i4.0
0x176814  ret
0x176815  ldloc.0
0x176816  ldarg.1
0x176817  callvirt instance string System.Web.Hosting.VirtualFileBase::get_VirtualPath()
0x17681c  callvirt instance void System.Web.Util.ObjectSet::Add(object o)
0x176821  ldarg.0
0x176822  ldfld    bool System.Web.Compilation.BuildManager::_precompilingApp
0x176827  brfalse.s loc_17682C
0x176829  ldc.i4.0
0x17682a  starg.s  3
0x17682c  ldarg.0
0x17682d  ldarg.1
0x17682e  ldarg.3
0x17682f  call     instance bool System.Web.Compilation.BuildManager::BatchCompileWebDirectoryInternal(class System.Web.Hosting.VirtualDirectory vdir, bool ignoreErrors)
0x176834  ret
```
