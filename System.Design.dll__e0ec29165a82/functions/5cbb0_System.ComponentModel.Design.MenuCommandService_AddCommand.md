# System.ComponentModel.Design.MenuCommandService::AddCommand

- ea: `0x5cbb0`
- end: `0x5cc70`
- name: `System.ComponentModel.Design.MenuCommandService::AddCommand`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5ca60`
- `0x5cbb0`
- `0x5d380`
- `0x8eec0`

## string_xrefs

- `0x5cbb3`: `command`
- `0x5cbcc`: `MenuCommandService_DuplicateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x5cbb0  ldarg.1
0x5cbb1  brtrue.s loc_5CBBE
0x5cbb3  ldstr    aCommand// "command"
0x5cbb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5cbbd  throw
0x5cbbe  ldarg.0
0x5cbbf  ldarg.1
0x5cbc0  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x5cbc5  callvirt instance class [System]System.ComponentModel.Design.MenuCommand [System]System.ComponentModel.Design.IMenuCommandService::FindCommand(class [System]System.ComponentModel.Design.CommandID)
0x5cbca  brfalse.s loc_5CBF0
0x5cbcc  ldstr    aMenucommandser// "MenuCommandService_DuplicateCommand"
0x5cbd1  ldc.i4.1
0x5cbd2  newarr   [mscorlib]System.Object
0x5cbd7  dup
0x5cbd8  ldc.i4.0
0x5cbd9  ldarg.1
0x5cbda  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x5cbdf  callvirt instance string [mscorlib]System.Object::ToString()
0x5cbe4  stelem.ref
0x5cbe5  call     string System.Design.SR::GetString(string name, object[] args)
0x5cbea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x5cbef  throw
0x5cbf0  ldarg.0
0x5cbf1  ldfld    object System.ComponentModel.Design.MenuCommandService::_commandGroupsLock
0x5cbf6  stloc.1
0x5cbf7  ldc.i4.0
0x5cbf8  stloc.2
0x5cbf9  ldloc.1
0x5cbfa  ldloca.s 2
0x5cbfc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5cc01  ldarg.0
0x5cc02  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.ArrayList> System.ComponentModel.Design.MenuCommandService::_commandGroups
0x5cc07  ldarg.1
0x5cc08  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x5cc0d  callvirt instance valuetype [mscorlib]System.Guid [System]System.ComponentModel.Design.CommandID::get_Guid()
0x5cc12  ldloca.s 0
0x5cc14  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.ArrayList>::TryGetValue(var<u1>, !!T0)
0x5cc19  brtrue.s loc_5CC42
0x5cc1b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5cc20  stloc.0
0x5cc21  ldloc.0
0x5cc22  ldarg.1
0x5cc23  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5cc28  pop
0x5cc29  ldarg.0
0x5cc2a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.ArrayList> System.ComponentModel.Design.MenuCommandService::_commandGroups
0x5cc2f  ldarg.1
0x5cc30  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x5cc35  callvirt instance valuetype [mscorlib]System.Guid [System]System.ComponentModel.Design.CommandID::get_Guid()
0x5cc3a  ldloc.0
0x5cc3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.ArrayList>::Add(var<u1>, !!T0)
0x5cc40  leave.s  loc_5CC56
0x5cc42  ldloc.0
0x5cc43  ldarg.1
0x5cc44  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5cc49  pop
0x5cc4a  leave.s  loc_5CC56
0x5cc4c  ldloc.2
0x5cc4d  brfalse.s loc_5CC55
0x5cc4f  ldloc.1
0x5cc50  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5cc55  endfinally
0x5cc56  ldarg.1
0x5cc57  ldarg.0
0x5cc58  ldfld    class [mscorlib]System.EventHandler System.ComponentModel.Design.MenuCommandService::_commandChangedHandler
0x5cc5d  callvirt instance void [System]System.ComponentModel.Design.MenuCommand::add_CommandChanged(class [mscorlib]System.EventHandler)
0x5cc62  ldarg.0
0x5cc63  ldc.i4.0
0x5cc64  ldarg.1
0x5cc65  newobj   instance void System.ComponentModel.Design.MenuCommandsChangedEventArgs::.ctor(valuetype System.ComponentModel.Design.MenuCommandsChangedType changeType, class [System]System.ComponentModel.Design.MenuCommand command)
0x5cc6a  callvirt instance void System.ComponentModel.Design.MenuCommandService::OnCommandsChanged(class System.ComponentModel.Design.MenuCommandsChangedEventArgs e)
0x5cc6f  ret
```
