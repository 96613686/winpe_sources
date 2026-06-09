# Microsoft.EventViewer.SnapIn.ViewerRootNode::RestoreViewDescription

- ea: `0x1960`
- end: `0x19f1`
- name: `Microsoft.EventViewer.SnapIn.ViewerRootNode::RestoreViewDescription`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x20e0`
- `0x9350`
- `0x93b0`

## callees

- `0x1960`

## pseudocode

```c

```

## disassembly

```asm
0x1960  ldarg.0
0x1961  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription Microsoft.EventViewer.SnapIn.ViewerRootNode::_savedViewDescription
0x1966  brfalse  loc_19EF
0x196b  ldarg.0
0x196c  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x1971  ldc.i4.0
0x1972  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::get_Item(int32)
0x1977  brfalse.s loc_19EF
0x1979  ldarg.0
0x197a  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x197f  ldc.i4.0
0x1980  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::get_Item(int32)
0x1985  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.MessageViewDescription
0x198a  brfalse.s loc_19EF
0x198c  ldarg.0
0x198d  ldnull
0x198e  ldstr    aChangeFromMvdB// "Change from MVD back to: type: {0}, nam"...
0x1993  ldc.i4.2
0x1994  newarr   [mscorlib]System.Object
0x1999  dup
0x199a  ldc.i4.0
0x199b  ldarg.0
0x199c  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription Microsoft.EventViewer.SnapIn.ViewerRootNode::_savedViewDescription
0x19a1  callvirt instance class [mscorlib]System.Type [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::get_ViewType()
0x19a6  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x19ab  stelem.ref
0x19ac  dup
0x19ad  ldc.i4.1
0x19ae  ldarg.0
0x19af  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription Microsoft.EventViewer.SnapIn.ViewerRootNode::_savedViewDescription
0x19b4  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription::get_DisplayName()
0x19b9  stelem.ref
0x19ba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19bf  call     void [System]System.Diagnostics.Trace::WriteLine(object, string)
0x19c4  ldarg.0
0x19c5  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x19ca  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x19cf  ldarg.0
0x19d0  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x19d5  ldarg.0
0x19d6  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription Microsoft.EventViewer.SnapIn.ViewerRootNode::_savedViewDescription
0x19db  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescription)
0x19e0  pop
0x19e1  ldarg.0
0x19e2  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0x19e7  ldc.i4.0
0x19e8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ViewDescriptionCollection::set_DefaultIndex(int32)
0x19ed  ldc.i4.1
0x19ee  ret
0x19ef  ldc.i4.0
0x19f0  ret
```
