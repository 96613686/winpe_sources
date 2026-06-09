# System.Xaml.XamlMarkupExtensionWriter::CheckMemberForUniqueness

- ea: `0x9f50`
- end: `0x9fac`
- name: `System.Xaml.XamlMarkupExtensionWriter::CheckMemberForUniqueness`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x285b0`

## callees

- `0x9f50`
- `0xa4c0`
- `0x10170`
- `0x10180`
- `0x10190`
- `0x101c0`
- `0x11f50`
- `0x28210`
- `0x28220`

## string_xrefs

- `0x9f80`: `XamlMarkupExtensionWriterDuplicateMember`

## pseudocode

```c

```

## disassembly

```asm
0x9f50  ldarg.0
0x9f51  ldfld    class System.Xaml.XamlXmlWriterSettings System.Xaml.XamlMarkupExtensionWriter::settings
0x9f56  callvirt instance bool System.Xaml.XamlXmlWriterSettings::get_AssumeValidInput()
0x9f5b  brtrue.s loc_9FAB
0x9f5d  ldarg.1
0x9f5e  callvirt instance class System.Xaml.XamlPropertySet Node::get_Members()
0x9f63  brtrue.s loc_9F72
0x9f65  ldarg.1
0x9f66  newobj   instance void System.Xaml.XamlPropertySet::.ctor()
0x9f6b  callvirt instance void Node::set_Members(class System.Xaml.XamlPropertySet value)
0x9f70  br.s     loc_9F9F
0x9f72  ldarg.1
0x9f73  callvirt instance class System.Xaml.XamlPropertySet Node::get_Members()
0x9f78  ldarg.2
0x9f79  callvirt instance bool System.Xaml.XamlPropertySet::Contains(class System.Xaml.XamlMember member)
0x9f7e  brfalse.s loc_9F9F
0x9f80  ldstr    aXamlmarkupexte// "XamlMarkupExtensionWriterDuplicateMembe"...
0x9f85  ldc.i4.1
0x9f86  newarr   [mscorlib]System.Object
0x9f8b  dup
0x9f8c  ldc.i4.0
0x9f8d  ldarg.2
0x9f8e  callvirt instance string System.Xaml.XamlMember::get_Name()
0x9f93  stelem.ref
0x9f94  call     string System.Xaml.SR::Get(string id, object[] args)
0x9f99  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9f9e  throw
0x9f9f  ldarg.1
0x9fa0  callvirt instance class System.Xaml.XamlPropertySet Node::get_Members()
0x9fa5  ldarg.2
0x9fa6  callvirt instance void System.Xaml.XamlPropertySet::Add(class System.Xaml.XamlMember member)
0x9fab  ret
```
