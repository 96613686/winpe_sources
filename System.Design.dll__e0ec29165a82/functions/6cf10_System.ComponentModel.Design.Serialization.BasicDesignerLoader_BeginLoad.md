# System.ComponentModel.Design.Serialization.BasicDesignerLoader::BeginLoad

- ea: `0x6cf10`
- end: `0x6d0eb`
- name: `System.ComponentModel.Design.Serialization.BasicDesignerLoader::BeginLoad`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x60f80`
- `0x6cf10`
- `0x6d300`
- `0x6d320`
- `0x6d350`
- `0x6d680`
- `0x6d990`
- `0x6dac0`
- `0x6f7f0`
- `0x8ef40`

## string_xrefs

- `0x6cf30`: `BasicDesignerLoaderAlreadyLoaded`
- `0x6cf41`: `BasicDesignerLoaderAlreadyLoaded`

## pseudocode

```c

```

## disassembly

```asm
0x6cf10  ldarg.1
0x6cf11  brtrue.s loc_6CF1E
0x6cf13  ldstr    aHost// "host"
0x6cf18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6cf1d  throw
0x6cf1e  ldarg.0
0x6cf1f  ldflda   valuetype [System]System.Collections.Specialized.BitVector32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::_state
0x6cf24  ldsfld   int32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::StateLoaded
0x6cf29  call     instance bool [System]System.Collections.Specialized.BitVector32::get_Item(int32)
0x6cf2e  brfalse.s loc_6CF4D
0x6cf30  ldstr    aBasicdesignerl_0// "BasicDesignerLoaderAlreadyLoaded"
0x6cf35  call     string System.Design.SR::GetString(string name)
0x6cf3a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6cf3f  stloc.3
0x6cf40  ldloc.3
0x6cf41  ldstr    aBasicdesignerl_0// "BasicDesignerLoaderAlreadyLoaded"
0x6cf46  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6cf4b  ldloc.3
0x6cf4c  throw
0x6cf4d  ldarg.0
0x6cf4e  ldfld    class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::_host
0x6cf53  brfalse.s loc_6CF7E
0x6cf55  ldarg.0
0x6cf56  ldfld    class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::_host
0x6cf5b  ldarg.1
0x6cf5c  beq.s    loc_6CF7E
0x6cf5e  ldstr    aBasicdesignerl_1// "BasicDesignerLoaderDifferentHost"
0x6cf63  call     string System.Design.SR::GetString(string name)
0x6cf68  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6cf6d  stloc.s  4
0x6cf6f  ldloc.s  4
0x6cf71  ldstr    aBasicdesignerl_1// "BasicDesignerLoaderDifferentHost"
0x6cf76  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6cf7b  ldloc.s  4
0x6cf7d  throw
0x6cf7e  ldarg.0
0x6cf7f  ldflda   valuetype [System]System.Collections.Specialized.BitVector32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::_state
0x6cf84  ldsfld   int32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::StateLoaded
0x6cf89  ldsfld   int32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::StateLoadFailed
0x6cf8e  or
0x6cf8f  ldc.i4.0
0x6cf90  call     instance void [System]System.Collections.Specialized.BitVector32::set_Item(int32, bool)
0x6cf95  ldarg.0
0x6cf96  ldc.i4.0
0x6cf97  stfld    int32 System.ComponentModel.Design.Serialization.BasicDesignerLoader::_loadDependencyCount
0x6cf9c  ldarg.0
0x6cf9d  ldfld    class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::_host
0x6cfa2  brtrue   loc_6D066
0x6cfa7  ldarg.0
0x6cfa8  ldarg.1
0x6cfa9  stfld    class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::_host
0x6cfae  ldarg.0
0x6cfaf  ldc.i4.1
0x6cfb0  stfld    bool System.ComponentModel.Design.Serialization.BasicDesignerLoader::_hostInitialized
0x6cfb5  ldarg.0
0x6cfb6  ldarg.0
0x6cfb7  ldfld    class [System]System.ComponentModel.Design.Serialization.IDesignerLoaderHost System.ComponentModel.Design.Serialization.BasicDesignerLoader::_host
0x6cfbc  newobj   instance void System.ComponentModel.Design.Serialization.DesignerSerializationManager::.ctor(class [mscorlib]System.IServiceProvider provider)
0x6cfc1  stfld    class System.ComponentModel.Design.Serialization.DesignerSerializationManager System.ComponentModel.Design.Serialization.BasicDesignerLoader::_serializationManager
0x6cfc6  ldarg.0
0x6cfc7  ldtoken  System.ComponentModel.Design.DesignSurfaceServiceContainer
0x6cfcc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6cfd1  call     instance object System.ComponentModel.Design.Serialization.BasicDesignerLoader::GetService(class [mscorlib]System.Type serviceType)
0x6cfd6  isinst   System.ComponentModel.Design.DesignSurfaceServiceContainer
0x6cfdb  stloc.s  5
0x6cfdd  ldloc.s  5
0x6cfdf  brfalse.s loc_6CFFA
0x6cfe1  ldloc.s  5
0x6cfe3  ldtoken  [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager
0x6cfe8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6cfed  ldarg.0
0x6cfee  ldfld    class System.ComponentModel.Design.Serialization.DesignerSerializationManager System.ComponentModel.Design.Serialization.BasicDesignerLoader::_serializationManager
0x6cff3  callvirt instance void System.ComponentModel.Design.DesignSurfaceServiceContainer::AddFixedService(class [mscorlib]System.Type serviceType, object serviceInstance)
0x6cff8  br.s     loc_6D03C
0x6cffa  ldarg.0
0x6cffb  ldtoken  [System]System.ComponentModel.Design.IServiceContainer
0x6d000  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d005  call     instance object System.ComponentModel.Design.Serialization.BasicDesignerLoader::GetService(class [mscorlib]System.Type serviceType)
0x6d00a  isinst   [System]System.ComponentModel.Design.IServiceContainer
0x6d00f  stloc.s  6
0x6d011  ldloc.s  6
0x6d013  brtrue.s loc_6D025
0x6d015  ldarg.0
0x6d016  ldtoken  [System]System.ComponentModel.Design.IServiceContainer
0x6d01b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d020  call     instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::ThrowMissingService(class [mscorlib]System.Type serviceType)
0x6d025  ldloc.s  6
0x6d027  ldtoken  [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager
0x6d02c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d031  ldarg.0
0x6d032  ldfld    class System.ComponentModel.Design.Serialization.DesignerSerializationManager System.ComponentModel.Design.Serialization.BasicDesignerLoader::_serializationManager
0x6d037  callvirt instance void [System]System.ComponentModel.Design.IServiceContainer::AddService(class [mscorlib]System.Type, object)
0x6d03c  ldarg.0
0x6d03d  callvirt instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::Initialize()
0x6d042  ldarg.1
0x6d043  ldarg.0
0x6d044  ldftn    instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::OnDesignerActivate(object sender, class [mscorlib]System.EventArgs e)
0x6d04a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d04f  callvirt instance void [System]System.ComponentModel.Design.IDesignerHost::add_Activated(class [mscorlib]System.EventHandler)
0x6d054  ldarg.1
0x6d055  ldarg.0
0x6d056  ldftn    instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::OnDesignerDeactivate(object sender, class [mscorlib]System.EventArgs e)
0x6d05c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d061  callvirt instance void [System]System.ComponentModel.Design.IDesignerHost::add_Deactivated(class [mscorlib]System.EventHandler)
0x6d066  ldc.i4.1
0x6d067  stloc.0
0x6d068  ldnull
0x6d069  stloc.1
0x6d06a  ldarg.0
0x6d06b  ldtoken  [System]System.ComponentModel.Design.Serialization.IDesignerLoaderService
0x6d070  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d075  call     instance object System.ComponentModel.Design.Serialization.BasicDesignerLoader::GetService(class [mscorlib]System.Type serviceType)
0x6d07a  isinst   [System]System.ComponentModel.Design.Serialization.IDesignerLoaderService
0x6d07f  stloc.2
0x6d080  ldloc.2
0x6d081  brfalse.s loc_6D08B
0x6d083  ldloc.2
0x6d084  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerLoaderService::AddLoadDependency()
0x6d089  br.s     loc_6D098
0x6d08b  ldarg.0
0x6d08c  ldc.i4.1
0x6d08d  stfld    bool System.ComponentModel.Design.Serialization.BasicDesignerLoader::_loading
0x6d092  ldarg.0
0x6d093  callvirt instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::OnBeginLoad()
0x6d098  ldarg.0
0x6d099  ldarg.0
0x6d09a  ldfld    class System.ComponentModel.Design.Serialization.DesignerSerializationManager System.ComponentModel.Design.Serialization.BasicDesignerLoader::_serializationManager
0x6d09f  callvirt instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::PerformLoad(class [System]System.ComponentModel.Design.Serialization.IDesignerSerializationManager serializationManager)
0x6d0a4  leave.s  loc_6D0CF
0x6d0a6  stloc.s  7
0x6d0a8  br.s     loc_6D0B3
0x6d0aa  ldloc.s  7
0x6d0ac  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x6d0b1  stloc.s  7
0x6d0b3  ldloc.s  7
0x6d0b5  isinst   [mscorlib]System.Reflection.TargetInvocationException
0x6d0ba  brtrue.s loc_6D0AA
0x6d0bc  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x6d0c1  stloc.1
0x6d0c2  ldloc.1
0x6d0c3  ldloc.s  7
0x6d0c5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x6d0ca  pop
0x6d0cb  ldc.i4.0
0x6d0cc  stloc.0
0x6d0cd  leave.s  loc_6D0CF
0x6d0cf  ldloc.2
0x6d0d0  brfalse.s loc_6D0DB
0x6d0d2  ldloc.2
0x6d0d3  ldloc.0
0x6d0d4  ldloc.1
0x6d0d5  callvirt instance void [System]System.ComponentModel.Design.Serialization.IDesignerLoaderService::DependentLoadComplete(bool, class [mscorlib]System.Collections.ICollection)
0x6d0da  ret
0x6d0db  ldarg.0
0x6d0dc  ldloc.0
0x6d0dd  ldloc.1
0x6d0de  callvirt instance void System.ComponentModel.Design.Serialization.BasicDesignerLoader::OnEndLoad(bool successful, class [mscorlib]System.Collections.ICollection errors)
0x6d0e3  ldarg.0
0x6d0e4  ldc.i4.0
0x6d0e5  stfld    bool System.ComponentModel.Design.Serialization.BasicDesignerLoader::_loading
0x6d0ea  ret
```
