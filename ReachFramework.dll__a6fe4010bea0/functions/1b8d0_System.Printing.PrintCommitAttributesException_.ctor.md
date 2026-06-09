# System.Printing.PrintCommitAttributesException::.ctor

- ea: `0x1b8d0`
- end: `0x1b8f9`
- name: `System.Printing.PrintCommitAttributesException::.ctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1b4e0`

## string_xrefs

- `0x1b8d1`: `PrintSystemException.CommitPrintSystemAttributesException`

## pseudocode

```c

```

## disassembly

```asm
0x1b8d0  ldarg.0
0x1b8d1  ldstr    aPrintsystemexc_2// "PrintSystemException.CommitPrintSystemA"...
0x1b8d6  call     instance void System.Printing.PrintSystemException::.ctor(string message)
0x1b8db  ldarg.0
0x1b8dc  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x1b8e1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::committedAttributes
0x1b8e6  ldarg.0
0x1b8e7  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x1b8ec  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<string> System.Printing.PrintCommitAttributesException::failedAttributes
0x1b8f1  ldarg.0
0x1b8f2  ldnull
0x1b8f3  stfld    string System.Printing.PrintCommitAttributesException::printObjectName
0x1b8f8  ret
```
