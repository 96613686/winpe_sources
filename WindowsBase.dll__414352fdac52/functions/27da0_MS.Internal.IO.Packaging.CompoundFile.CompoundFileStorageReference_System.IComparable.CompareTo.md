# MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::System.IComparable.CompareTo

- ea: `0x27da0`
- end: `0x27deb`
- name: `MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::System.IComparable.CompareTo`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x27da0`
- `0x2c100`

## string_xrefs

- `0x27db8`: `CanNotCompareDiffTypes`

## pseudocode

```c

```

## disassembly

```asm
0x27da0  ldarg.1
0x27da1  brtrue.s loc_27DA5
0x27da3  ldc.i4.1
0x27da4  ret
0x27da5  ldarg.1
0x27da6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x27dab  ldarg.0
0x27dac  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x27db1  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27db6  brfalse.s loc_27DC8
0x27db8  ldstr    aCannotcompared// "CanNotCompareDiffTypes"
0x27dbd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x27dc2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x27dc7  throw
0x27dc8  ldarg.1
0x27dc9  castclass MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference
0x27dce  stloc.0
0x27dcf  ldarg.0
0x27dd0  ldfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::_fullName
0x27dd5  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x27dda  ldloc.0
0x27ddb  ldfld    string MS.Internal.IO.Packaging.CompoundFile.CompoundFileStorageReference::_fullName
0x27de0  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x27de5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x27dea  ret
```
