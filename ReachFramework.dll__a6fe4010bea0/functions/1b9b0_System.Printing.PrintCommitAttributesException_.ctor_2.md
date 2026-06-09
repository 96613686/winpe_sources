# System.Printing.PrintCommitAttributesException::.ctor_2

- ea: `0x1b9b0`
- end: `0x1b9d2`
- name: `System.Printing.PrintCommitAttributesException::.ctor_2`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1b550`

## string_xrefs

- `0x1b9b2`: `PrintSystemException.CommitPrintSystemAttributesException`

## pseudocode

```c

```

## disassembly

```asm
0x1b9b0  ldarg.0
0x1b9b1  ldarg.1
0x1b9b2  ldstr    aPrintsystemexc_2// "PrintSystemException.CommitPrintSystemA"...
0x1b9b7  call     instance void System.Printing.PrintSystemException::.ctor(int32 errorCode, string message)
0x1b9bc  ldarg.0
0x1b9bd  ldarg.2
0x1b9be  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::committedAttributes
0x1b9c3  ldarg.0
0x1b9c4  ldarg.3
0x1b9c5  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::failedAttributes
0x1b9ca  ldarg.0
0x1b9cb  ldnull
0x1b9cc  stfld    string System.Printing.PrintCommitAttributesException::printObjectName
0x1b9d1  ret
```
