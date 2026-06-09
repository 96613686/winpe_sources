# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::set_PrintTicket

- ea: `0x211e0`
- end: `0x21237`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::set_PrintTicket`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1d0c0`
- `0x1ee90`
- `0x1ef70`
- `0x211e0`

## string_xrefs

- `0x211eb`: `ReachPackaging_PrintTicketAlreadyCommitted`

## pseudocode

```c

```

## disassembly

```asm
0x211e0  ldarg.1
0x211e1  brfalse.s loc_2122F
0x211e3  ldarg.0
0x211e4  ldfld    bool System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_isPrintTicketCommitted
0x211e9  brfalse.s loc_211FB
0x211eb  ldstr    aReachpackaging_1// "ReachPackaging_PrintTicketAlreadyCommit"...
0x211f0  call     string System.Windows.Xps.SR::Get(string id)
0x211f5  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x211fa  throw
0x211fb  ldarg.1
0x211fc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x21201  ldtoken  System.Printing.PrintTicket
0x21206  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2120b  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x21210  brtrue.s loc_21222
0x21212  ldstr    aReachpackaging_2// "ReachPackaging_NotAPrintTicket"
0x21217  call     string System.Windows.Xps.SR::Get(string id)
0x2121c  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x21221  throw
0x21222  ldarg.0
0x21223  ldarg.1
0x21224  callvirt instance class System.Printing.PrintTicket System.Printing.PrintTicket::Clone()
0x21229  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_printTicket
0x2122e  ret
0x2122f  ldarg.0
0x21230  ldnull
0x21231  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_printTicket
0x21236  ret
```
