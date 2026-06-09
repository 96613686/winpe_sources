# System.Xaml.XamlObjectWriter::GetKeyFromInstance

- ea: `0x3b20`
- end: `0x3b6d`
- name: `System.Xaml.XamlObjectWriter::GetKeyFromInstance`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x4940`
- `0x5a20`

## callees

- `0x2870`
- `0x3b20`
- `0x8590`
- `0x8b40`
- `0xb280`
- `0xd070`
- `0xd500`
- `0x11f50`
- `0x201c0`
- `0x202a0`

## pseudocode

```c

```

## disassembly

```asm
0x3b20  ldarg.2
0x3b21  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x3b26  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetAliasedProperty(class System.Xaml.XamlDirective directive)
0x3b2b  stloc.0
0x3b2c  ldloc.0
0x3b2d  ldnull
0x3b2e  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x3b33  brtrue.s loc_3B38
0x3b35  ldarg.1
0x3b36  brtrue.s loc_3B5D
0x3b38  ldarg.3
0x3b39  ldstr    aMissingkey// "MissingKey"
0x3b3e  ldc.i4.1
0x3b3f  newarr   [mscorlib]System.Object
0x3b44  dup
0x3b45  ldc.i4.0
0x3b46  ldarg.2
0x3b47  callvirt instance string System.Xaml.XamlType::get_Name()
0x3b4c  stelem.ref
0x3b4d  call     string System.Xaml.SR::Get(string id, object[] args)
0x3b52  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message)
0x3b57  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Runtime.IAddLineInfo::WithLineInfo(class System.Xaml.XamlException ex)
0x3b5c  throw
0x3b5d  ldarg.0
0x3b5e  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x3b63  ldarg.1
0x3b64  ldloc.0
0x3b65  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property)
0x3b6a  stloc.1
0x3b6b  ldloc.1
0x3b6c  ret
```
