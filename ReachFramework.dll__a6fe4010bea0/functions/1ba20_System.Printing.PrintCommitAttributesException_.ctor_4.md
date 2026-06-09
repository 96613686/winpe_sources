# System.Printing.PrintCommitAttributesException::.ctor_4

- ea: `0x1ba20`
- end: `0x1ba8c`
- name: `System.Printing.PrintCommitAttributesException::.ctor_4`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1b5b0`

## string_xrefs

- `0x1ba2a`: `CommittedAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x1ba20  ldarg.0
0x1ba21  ldarg.1
0x1ba22  ldarg.2
0x1ba23  call     instance void System.Printing.PrintSystemException::.ctor(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, valuetype [mscorlib]System.Runtime.Serialization.StreamingContext context)
0x1ba28  ldarg.0
0x1ba29  ldarg.1
0x1ba2a  ldstr    aCommittedattri// "CommittedAttributes"
0x1ba2f  ldarg.0
0x1ba30  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::committedAttributes
0x1ba35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ba3a  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x1ba3f  castclass class [mscorlib]System.Collections.ObjectModel.Collection`1<string>
0x1ba44  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::committedAttributes
0x1ba49  ldarg.0
0x1ba4a  ldarg.1
0x1ba4b  ldstr    aFailedattribut// "FailedAttributes"
0x1ba50  ldarg.0
0x1ba51  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::failedAttributes
0x1ba56  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ba5b  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x1ba60  castclass class [mscorlib]System.Collections.ObjectModel.Collection`1<string>
0x1ba65  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::failedAttributes
0x1ba6a  ldarg.0
0x1ba6b  ldarg.1
0x1ba6c  ldstr    aObjectname// "ObjectName"
0x1ba71  ldarg.0
0x1ba72  ldfld    string System.Printing.PrintCommitAttributesException::printObjectName
0x1ba77  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ba7c  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x1ba81  castclass [mscorlib]System.String
0x1ba86  stfld    string System.Printing.PrintCommitAttributesException::printObjectName
0x1ba8b  ret
```
