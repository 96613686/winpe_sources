# EventPropertyDescriptor::SetValue

- ea: `0x10a140`
- end: `0x10a3ed`
- name: `EventPropertyDescriptor::SetValue`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x61060`
- `0x610d0`
- `0x610e0`
- `0x8eec0`
- `0x8ef40`
- `0x10a060`
- `0x10a140`
- `0x128e50`

## string_xrefs

- `0x10a148`: `EventBindingServiceEventReadOnly`
- `0x10a16a`: `EventBindingServiceEventReadOnly`
- `0x10a182`: `EventBindingServiceBadArgType`
- `0x10a1b6`: `EventBindingServiceBadArgType`
- `0x10a22e`: `EventBindingServiceNoSite`
- `0x10a241`: `EventBindingServiceNoSite`
- `0x10a267`: `EventBindingServiceMissingService`
- `0x10a292`: `EventBindingServiceMissingService`
- `0x10a2fc`: `EventBindingServiceSetValue`

## pseudocode

```c

```

## disassembly

```asm
0x10a140  ldarg.0
0x10a141  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x10a146  brfalse.s loc_10A177
0x10a148  ldstr    aEventbindingse// "EventBindingServiceEventReadOnly"
0x10a14d  ldc.i4.1
0x10a14e  newarr   [mscorlib]System.Object
0x10a153  dup
0x10a154  ldc.i4.0
0x10a155  ldarg.0
0x10a156  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0x10a15b  stelem.ref
0x10a15c  call     string System.Design.SR::GetString(string name, object[] args)
0x10a161  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10a166  stloc.s  7
0x10a168  ldloc.s  7
0x10a16a  ldstr    aEventbindingse// "EventBindingServiceEventReadOnly"
0x10a16f  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x10a174  ldloc.s  7
0x10a176  throw
0x10a177  ldarg.2
0x10a178  brfalse.s loc_10A1C3
0x10a17a  ldarg.2
0x10a17b  isinst   [mscorlib]System.String
0x10a180  brtrue.s loc_10A1C3
0x10a182  ldstr    aEventbindingse_0// "EventBindingServiceBadArgType"
0x10a187  ldc.i4.2
0x10a188  newarr   [mscorlib]System.Object
0x10a18d  dup
0x10a18e  ldc.i4.0
0x10a18f  ldarg.0
0x10a190  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0x10a195  stelem.ref
0x10a196  dup
0x10a197  ldc.i4.1
0x10a198  ldtoken  [mscorlib]System.String
0x10a19d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a1a2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10a1a7  stelem.ref
0x10a1a8  call     string System.Design.SR::GetString(string name, object[] args)
0x10a1ad  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10a1b2  stloc.s  8
0x10a1b4  ldloc.s  8
0x10a1b6  ldstr    aEventbindingse_0// "EventBindingServiceBadArgType"
0x10a1bb  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x10a1c0  ldloc.s  8
0x10a1c2  throw
0x10a1c3  ldarg.2
0x10a1c4  castclass [mscorlib]System.String
0x10a1c9  stloc.0
0x10a1ca  ldloc.0
0x10a1cb  brfalse.s loc_10A1D7
0x10a1cd  ldloc.0
0x10a1ce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10a1d3  brtrue.s loc_10A1D7
0x10a1d5  ldnull
0x10a1d6  stloc.0
0x10a1d7  ldnull
0x10a1d8  stloc.1
0x10a1d9  ldarg.1
0x10a1da  isinst   [System]System.ComponentModel.IComponent
0x10a1df  brfalse.s loc_10A1ED
0x10a1e1  ldarg.1
0x10a1e2  castclass [System]System.ComponentModel.IComponent
0x10a1e7  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x10a1ec  stloc.1
0x10a1ed  ldloc.1
0x10a1ee  brtrue.s loc_10A22B
0x10a1f0  ldarg.0
0x10a1f1  ldfld    class System.ComponentModel.Design.EventBindingService EventPropertyDescriptor::_eventSvc
0x10a1f6  ldfld    class [mscorlib]System.IServiceProvider System.ComponentModel.Design.EventBindingService::_provider
0x10a1fb  ldtoken  [System]System.ComponentModel.Design.IReferenceService
0x10a200  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a205  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10a20a  isinst   [System]System.ComponentModel.Design.IReferenceService
0x10a20f  stloc.s  9
0x10a211  ldloc.s  9
0x10a213  brfalse.s loc_10A22B
0x10a215  ldloc.s  9
0x10a217  ldarg.1
0x10a218  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IReferenceService::GetComponent(object)
0x10a21d  stloc.s  0xA
0x10a21f  ldloc.s  0xA
0x10a221  brfalse.s loc_10A22B
0x10a223  ldloc.s  0xA
0x10a225  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x10a22a  stloc.1
0x10a22b  ldloc.1
0x10a22c  brtrue.s loc_10A24E
0x10a22e  ldstr    aEventbindingse_1// "EventBindingServiceNoSite"
0x10a233  call     string System.Design.SR::GetString(string name)
0x10a238  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10a23d  stloc.s  0xB
0x10a23f  ldloc.s  0xB
0x10a241  ldstr    aEventbindingse_1// "EventBindingServiceNoSite"
0x10a246  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x10a24b  ldloc.s  0xB
0x10a24d  throw
0x10a24e  ldloc.1
0x10a24f  ldtoken  [System]System.ComponentModel.Design.IDictionaryService
0x10a254  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a259  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10a25e  isinst   [System]System.ComponentModel.Design.IDictionaryService
0x10a263  stloc.2
0x10a264  ldloc.2
0x10a265  brtrue.s loc_10A29F
0x10a267  ldstr    aEventbindingse_2// "EventBindingServiceMissingService"
0x10a26c  ldc.i4.1
0x10a26d  newarr   [mscorlib]System.Object
0x10a272  dup
0x10a273  ldc.i4.0
0x10a274  ldtoken  [System]System.ComponentModel.Design.IDictionaryService
0x10a279  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a27e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10a283  stelem.ref
0x10a284  call     string System.Design.SR::GetString(string name, object[] args)
0x10a289  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10a28e  stloc.s  0xC
0x10a290  ldloc.s  0xC
0x10a292  ldstr    aEventbindingse_2// "EventBindingServiceMissingService"
0x10a297  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x10a29c  ldloc.s  0xC
0x10a29e  throw
0x10a29f  ldarg.1
0x10a2a0  ldarg.0
0x10a2a1  newobj   instance void ReferenceEventClosure::.ctor(object reference, class EventPropertyDescriptor prop)
0x10a2a6  stloc.3
0x10a2a7  ldloc.2
0x10a2a8  ldloc.3
0x10a2a9  callvirt instance object [System]System.ComponentModel.Design.IDictionaryService::GetValue(object)
0x10a2ae  castclass [mscorlib]System.String
0x10a2b3  stloc.s  4
0x10a2b5  ldloc.s  4
0x10a2b7  ldloc.0
0x10a2b8  bne.un.s loc_10A2BB
0x10a2ba  ret
0x10a2bb  ldloc.s  4
0x10a2bd  brfalse.s loc_10A2CD
0x10a2bf  ldloc.0
0x10a2c0  brfalse.s loc_10A2CD
0x10a2c2  ldloc.s  4
0x10a2c4  ldloc.0
0x10a2c5  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10a2ca  brfalse.s loc_10A2CD
0x10a2cc  ret
0x10a2cd  ldloc.0
0x10a2ce  brfalse.s loc_10A2DC
0x10a2d0  ldarg.0
0x10a2d1  ldfld    class System.ComponentModel.Design.EventBindingService EventPropertyDescriptor::_eventSvc
0x10a2d6  ldloc.0
0x10a2d7  callvirt instance void System.ComponentModel.Design.EventBindingService::ValidateMethodName(string methodName)
0x10a2dc  ldloc.1
0x10a2dd  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x10a2e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a2e7  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10a2ec  isinst   [System]System.ComponentModel.Design.IDesignerHost
0x10a2f1  stloc.s  5
0x10a2f3  ldnull
0x10a2f4  stloc.s  6
0x10a2f6  ldloc.s  5
0x10a2f8  brfalse.s loc_10A320
0x10a2fa  ldloc.s  5
0x10a2fc  ldstr    aEventbindingse_3// "EventBindingServiceSetValue"
0x10a301  ldc.i4.2
0x10a302  newarr   [mscorlib]System.Object
0x10a307  dup
0x10a308  ldc.i4.0
0x10a309  ldloc.1
0x10a30a  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0x10a30f  stelem.ref
0x10a310  dup
0x10a311  ldc.i4.1
0x10a312  ldloc.0
0x10a313  stelem.ref
0x10a314  call     string System.Design.SR::GetString(string name, object[] args)
0x10a319  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x10a31e  stloc.s  6
0x10a320  nop
0x10a321  ldloc.1
0x10a322  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0x10a327  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a32c  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x10a331  isinst   [System]System.ComponentModel.Design.IComponentChangeService
0x10a336  stloc.s  0xD
0x10a338  ldloc.s  0xD
0x10a33a  brfalse.s loc_10A367
0x10a33c  ldloc.s  0xD
0x10a33e  ldarg.1
0x10a33f  ldarg.0
0x10a340  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x10a345  ldloc.s  0xD
0x10a347  ldarg.1
0x10a348  ldarg.0
0x10a349  call     instance class [System]System.ComponentModel.EventDescriptor EventPropertyDescriptor::get_Event()
0x10a34e  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x10a353  leave.s  loc_10A367
0x10a355  stloc.s  0xE
0x10a357  ldloc.s  0xE
0x10a359  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0x10a35e  bne.un.s loc_10A365
0x10a360  leave    loc_10A3EC
0x10a365  rethrow
0x10a367  ldloc.0
0x10a368  brfalse.s loc_10A382
0x10a36a  ldarg.0
0x10a36b  ldfld    class System.ComponentModel.Design.EventBindingService EventPropertyDescriptor::_eventSvc
0x10a370  ldarg.1
0x10a371  castclass [System]System.ComponentModel.IComponent
0x10a376  ldarg.0
0x10a377  ldfld    class [System]System.ComponentModel.EventDescriptor EventPropertyDescriptor::_eventDesc
0x10a37c  ldloc.0
0x10a37d  callvirt instance void System.ComponentModel.Design.EventBindingService::UseMethod(class [System]System.ComponentModel.IComponent component, class [System]System.ComponentModel.EventDescriptor e, string methodName)
0x10a382  ldloc.s  4
0x10a384  brfalse.s loc_10A39F
0x10a386  ldarg.0
0x10a387  ldfld    class System.ComponentModel.Design.EventBindingService EventPropertyDescriptor::_eventSvc
0x10a38c  ldarg.1
0x10a38d  castclass [System]System.ComponentModel.IComponent
0x10a392  ldarg.0
0x10a393  ldfld    class [System]System.ComponentModel.EventDescriptor EventPropertyDescriptor::_eventDesc
0x10a398  ldloc.s  4
0x10a39a  callvirt instance void System.ComponentModel.Design.EventBindingService::FreeMethod(class [System]System.ComponentModel.IComponent component, class [System]System.ComponentModel.EventDescriptor e, string methodName)
0x10a39f  ldloc.2
0x10a3a0  ldloc.3
0x10a3a1  ldloc.0
0x10a3a2  callvirt instance void [System]System.ComponentModel.Design.IDictionaryService::SetValue(object, object)
0x10a3a7  ldloc.s  0xD
0x10a3a9  brfalse.s loc_10A3C7
0x10a3ab  ldloc.s  0xD
0x10a3ad  ldarg.1
0x10a3ae  ldarg.0
0x10a3af  call     instance class [System]System.ComponentModel.EventDescriptor EventPropertyDescriptor::get_Event()
0x10a3b4  ldnull
0x10a3b5  ldnull
0x10a3b6  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0x10a3bb  ldloc.s  0xD
0x10a3bd  ldarg.1
0x10a3be  ldarg.0
0x10a3bf  ldloc.s  4
0x10a3c1  ldloc.0
0x10a3c2  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0x10a3c7  ldarg.0
0x10a3c8  ldarg.1
0x10a3c9  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0x10a3ce  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::OnValueChanged(object, class [mscorlib]System.EventArgs)
0x10a3d3  ldloc.s  6
0x10a3d5  brfalse.s loc_10A3DE
0x10a3d7  ldloc.s  6
0x10a3d9  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0x10a3de  leave.s  loc_10A3EC
0x10a3e0  ldloc.s  6
0x10a3e2  brfalse.s loc_10A3EB
0x10a3e4  ldloc.s  6
0x10a3e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a3eb  endfinally
0x10a3ec  ret
```
