# System.Xaml.XamlNodeList::Add

- ea: `0x75f0`
- end: `0x7629`
- name: `System.Xaml.XamlNodeList::Add`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x2100`
- `0x75f0`
- `0x8440`
- `0x11f20`

## string_xrefs

- `0x7619`: `CannotWriteClosedWriter`

## pseudocode

```c

```

## disassembly

```asm
0x75f0  ldarg.0
0x75f1  ldfld    bool System.Xaml.XamlNodeList::_readMode
0x75f6  brtrue.s loc_7619
0x75f8  ldarg.1
0x75f9  brfalse.s loc_7611
0x75fb  ldloca.s 0
0x75fd  ldarg.1
0x75fe  ldarg.2
0x75ff  call     instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x7604  ldarg.0
0x7605  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> System.Xaml.XamlNodeList::_nodeList
0x760a  ldloc.0
0x760b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x7610  ret
0x7611  ldarg.0
0x7612  ldc.i4.1
0x7613  stfld    bool System.Xaml.XamlNodeList::_readMode
0x7618  ret
0x7619  ldstr    aCannotwriteclo// "CannotWriteClosedWriter"
0x761e  call     string System.Xaml.SR::Get(string id)
0x7623  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x7628  throw
```
