# <ParseContentToNamespaceElementPair>d__40::MoveNext

- ea: `0x2f3b0`
- end: `0x2f51f`
- name: `<ParseContentToNamespaceElementPair>d__40::MoveNext`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x117a0`
- `0x11f20`
- `0x2ec40`
- `0x2f3b0`

## string_xrefs

- `0x2f4bb`: `XCRInvalidXMLName`

## pseudocode

```c

```

## disassembly

```asm
0x2f3b0  ldarg.0
0x2f3b1  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x2f3b6  stloc.0
0x2f3b7  ldarg.0
0x2f3b8  ldfld    class System.Xaml.XmlCompatibilityReader <ParseContentToNamespaceElementPair>d__40::<>4__this
0x2f3bd  stloc.1
0x2f3be  ldloc.0
0x2f3bf  brfalse.s loc_2F3CA
0x2f3c1  ldloc.0
0x2f3c2  ldc.i4.1
0x2f3c3  beq      loc_2F4EE
0x2f3c8  ldc.i4.0
0x2f3c9  ret
0x2f3ca  ldarg.0
0x2f3cb  ldc.i4.m1
0x2f3cc  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x2f3d1  ldarg.0
0x2f3d2  ldarg.0
0x2f3d3  ldfld    string <ParseContentToNamespaceElementPair>d__40::content
0x2f3d8  callvirt instance string [mscorlib]System.String::Trim()
0x2f3dd  ldc.i4.1
0x2f3de  newarr   [mscorlib]System.Char
0x2f3e3  dup
0x2f3e4  ldc.i4.0
0x2f3e5  ldc.i4.s 0x20
0x2f3e7  stelem.i2
0x2f3e8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2f3ed  stfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x2f3f2  ldarg.0
0x2f3f3  ldc.i4.0
0x2f3f4  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x2f3f9  br       loc_2F503
0x2f3fe  ldarg.0
0x2f3ff  ldfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x2f404  ldarg.0
0x2f405  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x2f40a  ldelem.ref
0x2f40b  stloc.2
0x2f40c  ldloc.2
0x2f40d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f412  brtrue   loc_2F4F5
0x2f417  ldloc.2
0x2f418  ldc.i4.s 0x3A
0x2f41a  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x2f41f  stloc.3
0x2f420  ldloc.2
0x2f421  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f426  stloc.s  4
0x2f428  ldloc.3
0x2f429  ldc.i4.0
0x2f42a  ble.s    loc_2F43E
0x2f42c  ldloc.3
0x2f42d  ldloc.s  4
0x2f42f  ldc.i4.1
0x2f430  sub
0x2f431  bge.s    loc_2F43E
0x2f433  ldloc.3
0x2f434  ldloc.2
0x2f435  ldc.i4.s 0x3A
0x2f437  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x2f43c  beq.s    loc_2F45D
0x2f43e  ldloc.1
0x2f43f  ldstr    aXcrinvalidform// "XCRInvalidFormat"
0x2f444  call     string System.Xaml.SR::Get(string id)
0x2f449  ldc.i4.1
0x2f44a  newarr   [mscorlib]System.Object
0x2f44f  dup
0x2f450  ldc.i4.0
0x2f451  ldarg.0
0x2f452  ldfld    string <ParseContentToNamespaceElementPair>d__40::callerContext
0x2f457  stelem.ref
0x2f458  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x2f45d  ldloc.2
0x2f45e  ldc.i4.0
0x2f45f  ldloc.3
0x2f460  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2f465  stloc.s  5
0x2f467  ldloc.2
0x2f468  ldloc.3
0x2f469  ldc.i4.1
0x2f46a  add
0x2f46b  ldloc.s  4
0x2f46d  ldc.i4.1
0x2f46e  sub
0x2f46f  ldloc.3
0x2f470  sub
0x2f471  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2f476  stloc.s  6
0x2f478  ldloc.1
0x2f479  ldloc.s  5
0x2f47b  callvirt instance string [System.Xml]System.Xml.XmlReader::LookupNamespace(string)
0x2f480  stloc.s  7
0x2f482  ldloc.s  7
0x2f484  brtrue.s loc_2F4A3
0x2f486  ldloc.1
0x2f487  ldstr    aXcrundefinedpr// "XCRUndefinedPrefix"
0x2f48c  call     string System.Xaml.SR::Get(string id)
0x2f491  ldc.i4.1
0x2f492  newarr   [mscorlib]System.Object
0x2f497  dup
0x2f498  ldc.i4.0
0x2f499  ldloc.s  5
0x2f49b  stelem.ref
0x2f49c  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x2f4a1  br.s     loc_2F4F5
0x2f4a3  ldloc.s  6
0x2f4a5  ldstr    asc_3A680// "*"
0x2f4aa  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2f4af  brfalse.s loc_2F4D6
0x2f4b1  ldloc.s  6
0x2f4b3  call     bool [System.Xml]System.Xml.XmlReader::IsName(string)
0x2f4b8  brtrue.s loc_2F4D6
0x2f4ba  ldloc.1
0x2f4bb  ldstr    aXcrinvalidxmln// "XCRInvalidXMLName"
0x2f4c0  call     string System.Xaml.SR::Get(string id)
0x2f4c5  ldc.i4.1
0x2f4c6  newarr   [mscorlib]System.Object
0x2f4cb  dup
0x2f4cc  ldc.i4.0
0x2f4cd  ldloc.2
0x2f4ce  stelem.ref
0x2f4cf  call     instance void System.Xaml.XmlCompatibilityReader::Error(string message, object[] args)
0x2f4d4  br.s     loc_2F4F5
0x2f4d6  ldarg.0
0x2f4d7  ldloc.s  7
0x2f4d9  ldloc.s  6
0x2f4db  newobj   instance void NamespaceElementPair::.ctor(string namespaceName, string itemName)
0x2f4e0  stfld    valuetype NamespaceElementPair <ParseContentToNamespaceElementPair>d__40::<>2__current
0x2f4e5  ldarg.0
0x2f4e6  ldc.i4.1
0x2f4e7  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x2f4ec  ldc.i4.1
0x2f4ed  ret
0x2f4ee  ldarg.0
0x2f4ef  ldc.i4.m1
0x2f4f0  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>1__state
0x2f4f5  ldarg.0
0x2f4f6  ldarg.0
0x2f4f7  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x2f4fc  ldc.i4.1
0x2f4fd  add
0x2f4fe  stfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x2f503  ldarg.0
0x2f504  ldfld    int32 <ParseContentToNamespaceElementPair>d__40::<>7__wrap2
0x2f509  ldarg.0
0x2f50a  ldfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x2f50f  ldlen
0x2f510  conv.i4
0x2f511  blt      loc_2F3FE
0x2f516  ldarg.0
0x2f517  ldnull
0x2f518  stfld    string[] <ParseContentToNamespaceElementPair>d__40::<>7__wrap1
0x2f51d  ldc.i4.0
0x2f51e  ret
```
