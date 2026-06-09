# System.Xaml.XamlNodeList::AddLineInfo

- ea: `0x7630`
- end: `0x7672`
- name: `System.Xaml.XamlNodeList::AddLineInfo`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x2140`
- `0x69a0`
- `0x7630`
- `0x8440`
- `0x11f20`

## string_xrefs

- `0x7638`: `CannotWriteClosedWriter`

## pseudocode

```c

```

## disassembly

```asm
0x7630  ldarg.0
0x7631  ldfld    bool System.Xaml.XamlNodeList::_readMode
0x7636  brfalse.s loc_7648
0x7638  ldstr    aCannotwriteclo// "CannotWriteClosedWriter"
0x763d  call     string System.Xaml.SR::Get(string id)
0x7642  newobj   instance void System.Xaml.XamlException::.ctor(string message)
0x7647  throw
0x7648  ldloca.s 0
0x764a  ldarg.1
0x764b  ldarg.2
0x764c  newobj   instance void System.Xaml.LineInfo::.ctor(int32 lineNumber, int32 linePosition)
0x7651  call     instance void System.Xaml.XamlNode::.ctor(class System.Xaml.LineInfo lineInfo)
0x7656  ldarg.0
0x7657  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode> System.Xaml.XamlNodeList::_nodeList
0x765c  ldloc.0
0x765d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Xaml.XamlNode>::Add(var<u1>)
0x7662  ldarg.0
0x7663  ldfld    bool System.Xaml.XamlNodeList::_hasLineInfo
0x7668  brtrue.s loc_7671
0x766a  ldarg.0
0x766b  ldc.i4.1
0x766c  stfld    bool System.Xaml.XamlNodeList::_hasLineInfo
0x7671  ret
```
