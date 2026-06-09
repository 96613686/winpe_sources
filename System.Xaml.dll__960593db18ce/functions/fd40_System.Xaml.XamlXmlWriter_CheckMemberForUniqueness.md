# System.Xaml.XamlXmlWriter::CheckMemberForUniqueness

- ea: `0xfd40`
- end: `0xfde1`
- name: `System.Xaml.XamlXmlWriter::CheckMemberForUniqueness`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x2d240`
- `0x2d4c0`

## callees

- `0x8860`
- `0xa4c0`
- `0xfd40`
- `0x10170`
- `0x10180`
- `0x10190`
- `0x101c0`
- `0x11f50`
- `0x2cb50`
- `0x2cb60`
- `0x2cb70`

## string_xrefs

- `0xfdb5`: `XamlXmlWriterDuplicateMember`

## pseudocode

```c

```

## disassembly

```asm
0xfd40  ldarg.0
0xfd41  ldfld    class System.Xaml.XamlXmlWriterSettings System.Xaml.XamlXmlWriter::settings
0xfd46  callvirt instance bool System.Xaml.XamlXmlWriterSettings::get_AssumeValidInput()
0xfd4b  brtrue   loc_FDE0
0xfd50  ldarg.0
0xfd51  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfd56  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0xfd5b  stloc.0
0xfd5c  ldloc.0
0xfd5d  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0xfd62  ldc.i4.1
0xfd63  beq.s    loc_FD92
0xfd65  ldloc.0
0xfd66  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0xfd6b  ldc.i4.2
0xfd6c  beq.s    loc_FD92
0xfd6e  ldarg.0
0xfd6f  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfd74  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0xfd79  stloc.1
0xfd7a  ldarg.0
0xfd7b  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfd80  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0xfd85  stloc.0
0xfd86  ldarg.0
0xfd87  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfd8c  ldloc.1
0xfd8d  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0xfd92  ldloc.0
0xfd93  callvirt instance class System.Xaml.XamlPropertySet Frame::get_Members()
0xfd98  brtrue.s loc_FDA7
0xfd9a  ldloc.0
0xfd9b  newobj   instance void System.Xaml.XamlPropertySet::.ctor()
0xfda0  callvirt instance void Frame::set_Members(class System.Xaml.XamlPropertySet value)
0xfda5  br.s     loc_FDD4
0xfda7  ldloc.0
0xfda8  callvirt instance class System.Xaml.XamlPropertySet Frame::get_Members()
0xfdad  ldarg.1
0xfdae  callvirt instance bool System.Xaml.XamlPropertySet::Contains(class System.Xaml.XamlMember member)
0xfdb3  brfalse.s loc_FDD4
0xfdb5  ldstr    aXamlxmlwriterd// "XamlXmlWriterDuplicateMember"
0xfdba  ldc.i4.1
0xfdbb  newarr   [mscorlib]System.Object
0xfdc0  dup
0xfdc1  ldc.i4.0
0xfdc2  ldarg.1
0xfdc3  callvirt instance string System.Xaml.XamlMember::get_Name()
0xfdc8  stelem.ref
0xfdc9  call     string System.Xaml.SR::Get(string id, object[] args)
0xfdce  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0xfdd3  throw
0xfdd4  ldloc.0
0xfdd5  callvirt instance class System.Xaml.XamlPropertySet Frame::get_Members()
0xfdda  ldarg.1
0xfddb  callvirt instance void System.Xaml.XamlPropertySet::Add(class System.Xaml.XamlMember member)
0xfde0  ret
```
