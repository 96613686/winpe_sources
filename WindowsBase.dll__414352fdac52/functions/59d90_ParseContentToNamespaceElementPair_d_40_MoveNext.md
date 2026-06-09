# <ParseContentToNamespaceElementPair>d__40::MoveNext

- ea: `0x59d90`
- end: `0x59eff`
- name: `<ParseContentToNamespaceElementPair>d__40::MoveNext`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x2c100`
- `0x445a0`
- `0x59620`
- `0x59d90`

## string_xrefs

- `0x59e9b`: `XCRInvalidXMLName`

## pseudocode

```c

```

## disassembly

```asm
0x59d90  ldarg.0
0x59d91  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x59d96  stloc.0
0x59d97  ldarg.0
0x59d98  ldfld    class System.Windows.Markup.XmlCompatibilityReader <ParseContentToNamespaceElementPair>d__40::<>4__this
0x59d9d  stloc.1
0x59d9e  ldloc.0
0x59d9f  brfalse.s loc_59DAA
0x59da1  ldloc.0
0x59da2  ldc.i4.1
0x59da3  beq      loc_59ECE
0x59da8  ldc.i4.0
0x59da9  ret
0x59daa  ldarg.0
0x59dab  ldc.i4.m1
0x59dac  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x59db1  ldarg.0
0x59db2  ldarg.0
0x59db3  ldfld    string <ParseContentToNamespaceElementPair>d__40::content
0x59db8  callvirt instance string [mscorlib]System.String::Trim()
0x59dbd  ldc.i4.1
0x59dbe  newarr   [mscorlib]System.Char
0x59dc3  dup
0x59dc4  ldc.i4.0
0x59dc5  ldc.i4.s 0x20
0x59dc7  stelem.i2
0x59dc8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x59dcd  stfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x59dd2  ldarg.0
0x59dd3  ldc.i4.0
0x59dd4  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x59dd9  br       loc_59EE3
0x59dde  ldarg.0
0x59ddf  ldfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x59de4  ldarg.0
0x59de5  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x59dea  ldelem.ref
0x59deb  stloc.2
0x59dec  ldloc.2
0x59ded  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x59df2  brtrue   loc_59ED5
0x59df7  ldloc.2
0x59df8  ldc.i4.s 0x3A
0x59dfa  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x59dff  stloc.3
0x59e00  ldloc.2
0x59e01  callvirt instance int32 [mscorlib]System.String::get_Length()
0x59e06  stloc.s  4
0x59e08  ldloc.3
0x59e09  ldc.i4.0
0x59e0a  ble.s    loc_59E1E
0x59e0c  ldloc.3
0x59e0d  ldloc.s  4
0x59e0f  ldc.i4.1
0x59e10  sub
0x59e11  bge.s    loc_59E1E
0x59e13  ldloc.3
0x59e14  ldloc.2
0x59e15  ldc.i4.s 0x3A
0x59e17  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x59e1c  beq.s    loc_59E3D
0x59e1e  ldloc.1
0x59e1f  ldstr    aXcrinvalidform// "XCRInvalidFormat"
0x59e24  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x59e29  ldc.i4.1
0x59e2a  newarr   [mscorlib]System.Object
0x59e2f  dup
0x59e30  ldc.i4.0
0x59e31  ldarg.0
0x59e32  ldfld    string <ParseContentToNamespaceElementPair>d__40::callerContext
0x59e37  stelem.ref
0x59e38  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x59e3d  ldloc.2
0x59e3e  ldc.i4.0
0x59e3f  ldloc.3
0x59e40  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59e45  stloc.s  5
0x59e47  ldloc.2
0x59e48  ldloc.3
0x59e49  ldc.i4.1
0x59e4a  add
0x59e4b  ldloc.s  4
0x59e4d  ldc.i4.1
0x59e4e  sub
0x59e4f  ldloc.3
0x59e50  sub
0x59e51  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59e56  stloc.s  6
0x59e58  ldloc.1
0x59e59  ldloc.s  5
0x59e5b  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x59e60  stloc.s  7
0x59e62  ldloc.s  7
0x59e64  brtrue.s loc_59E83
0x59e66  ldloc.1
0x59e67  ldstr    aXcrundefinedpr// "XCRUndefinedPrefix"
0x59e6c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x59e71  ldc.i4.1
0x59e72  newarr   [mscorlib]System.Object
0x59e77  dup
0x59e78  ldc.i4.0
0x59e79  ldloc.s  5
0x59e7b  stelem.ref
0x59e7c  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x59e81  br.s     loc_59ED5
0x59e83  ldloc.s  6
0x59e85  ldstr    asc_6AE60// "*"
0x59e8a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x59e8f  brfalse.s loc_59EB6
0x59e91  ldloc.s  6
0x59e93  call     bool [System.Xml]System.Xml.XmlReader::IsName(string)
0x59e98  brtrue.s loc_59EB6
0x59e9a  ldloc.1
0x59e9b  ldstr    aXcrinvalidxmln// "XCRInvalidXMLName"
0x59ea0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x59ea5  ldc.i4.1
0x59ea6  newarr   [mscorlib]System.Object
0x59eab  dup
0x59eac  ldc.i4.0
0x59ead  ldloc.2
0x59eae  stelem.ref
0x59eaf  call     instance void System.Windows.Markup.XmlCompatibilityReader::Error(string message, object[] args)
0x59eb4  br.s     loc_59ED5
0x59eb6  ldarg.0
0x59eb7  ldloc.s  7
0x59eb9  ldloc.s  6
0x59ebb  newobj   instance void NamespaceElementPair::.ctor(string namespaceName, string itemName)
0x59ec0  stfld    valuetype NamespaceElementPair <ParseContentToNamespaceElementPair>d__40::<>2__current
0x59ec5  ldarg.0
0x59ec6  ldc.i4.1
0x59ec7  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x59ecc  ldc.i4.1
0x59ecd  ret
0x59ece  ldarg.0
0x59ecf  ldc.i4.m1
0x59ed0  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x59ed5  ldarg.0
0x59ed6  ldarg.0
0x59ed7  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x59edc  ldc.i4.1
0x59edd  add
0x59ede  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x59ee3  ldarg.0
0x59ee4  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x59ee9  ldarg.0
0x59eea  ldfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x59eef  ldlen
0x59ef0  conv.i4
0x59ef1  blt      loc_59DDE
0x59ef6  ldarg.0
0x59ef7  ldnull
0x59ef8  stfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x59efd  ldc.i4.0
0x59efe  ret
```
