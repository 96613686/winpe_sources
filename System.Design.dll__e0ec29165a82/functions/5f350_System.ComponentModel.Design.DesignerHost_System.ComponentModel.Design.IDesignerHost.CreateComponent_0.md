# System.ComponentModel.Design.DesignerHost::System.ComponentModel.Design.IDesignerHost.CreateComponent_0

- ea: `0x5f350`
- end: `0x5f415`
- name: `System.ComponentModel.Design.DesignerHost::System.ComponentModel.Design.IDesignerHost.CreateComponent_0`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x5e160`
- `0x5e250`
- `0x5f350`
- `0x604a0`
- `0x8eec0`

## string_xrefs

- `0x5f359`: `componentType`
- `0x5f3b3`: `DesignerHostFailedComponentCreate`
- `0x5f3d3`: `DesignerHostFailedComponentCreate`

## pseudocode

```c

```

## disassembly

```asm
0x5f350  ldarg.1
0x5f351  ldnull
0x5f352  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f357  brfalse.s loc_5F364
0x5f359  ldstr    aComponenttype// "componentType"
0x5f35e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f363  throw
0x5f364  call     class [System]System.ComponentModel.LicenseContext [System]System.ComponentModel.LicenseManager::get_CurrentContext()
0x5f369  stloc.1
0x5f36a  ldc.i4.0
0x5f36b  stloc.2
0x5f36c  ldloc.1
0x5f36d  ldarg.0
0x5f36e  call     instance class System.ComponentModel.Design.HostDesigntimeLicenseContext System.ComponentModel.Design.DesignerHost::get_LicenseContext()
0x5f373  beq.s    loc_5F38C
0x5f375  ldarg.0
0x5f376  call     instance class System.ComponentModel.Design.HostDesigntimeLicenseContext System.ComponentModel.Design.DesignerHost::get_LicenseContext()
0x5f37b  call     void [System]System.ComponentModel.LicenseManager::set_CurrentContext(class [System]System.ComponentModel.LicenseContext)
0x5f380  ldsfld   object System.ComponentModel.Design.DesignerHost::_selfLock
0x5f385  call     void [System]System.ComponentModel.LicenseManager::LockContext(object)
0x5f38a  ldc.i4.1
0x5f38b  stloc.2
0x5f38c  nop
0x5f38d  ldarg.0
0x5f38e  ldarg.2
0x5f38f  stfld    string System.ComponentModel.Design.DesignerHost::_newComponentName
0x5f394  ldarg.0
0x5f395  ldfld    class System.ComponentModel.Design.DesignSurface System.ComponentModel.Design.DesignerHost::_surface
0x5f39a  ldarg.1
0x5f39b  callvirt instance object System.ComponentModel.Design.DesignSurface::CreateInstance(class [mscorlib]System.Type type)
0x5f3a0  isinst   [System]System.ComponentModel.IComponent
0x5f3a5  stloc.0
0x5f3a6  leave.s  loc_5F3B0
0x5f3a8  ldarg.0
0x5f3a9  ldnull
0x5f3aa  stfld    string System.ComponentModel.Design.DesignerHost::_newComponentName
0x5f3af  endfinally
0x5f3b0  ldloc.0
0x5f3b1  brtrue.s loc_5F3DF
0x5f3b3  ldstr    aDesignerhostfa// "DesignerHostFailedComponentCreate"
0x5f3b8  ldc.i4.1
0x5f3b9  newarr   [mscorlib]System.Object
0x5f3be  dup
0x5f3bf  ldc.i4.0
0x5f3c0  ldarg.1
0x5f3c1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5f3c6  stelem.ref
0x5f3c7  call     string System.Design.SR::GetString(string name, object[] args)
0x5f3cc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5f3d1  stloc.3
0x5f3d2  ldloc.3
0x5f3d3  ldstr    aDesignerhostfa// "DesignerHostFailedComponentCreate"
0x5f3d8  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x5f3dd  ldloc.3
0x5f3de  throw
0x5f3df  ldloc.0
0x5f3e0  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x5f3e5  brfalse.s loc_5F3F5
0x5f3e7  ldloc.0
0x5f3e8  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x5f3ed  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.ISite::get_Container()
0x5f3f2  ldarg.0
0x5f3f3  beq.s    loc_5F3FD
0x5f3f5  ldarg.0
0x5f3f6  ldloc.0
0x5f3f7  ldarg.2
0x5f3f8  call     instance void System.ComponentModel.Design.DesignerHost::PerformAdd(class [System]System.ComponentModel.IComponent component, string name)
0x5f3fd  leave.s  loc_5F413
0x5f3ff  ldloc.2
0x5f400  brfalse.s loc_5F412
0x5f402  ldsfld   object System.ComponentModel.Design.DesignerHost::_selfLock
0x5f407  call     void [System]System.ComponentModel.LicenseManager::UnlockContext(object)
0x5f40c  ldloc.1
0x5f40d  call     void [System]System.ComponentModel.LicenseManager::set_CurrentContext(class [System]System.ComponentModel.LicenseContext)
0x5f412  endfinally
0x5f413  ldloc.0
0x5f414  ret
```
