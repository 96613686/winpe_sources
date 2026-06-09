# System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::set_PrintTicket

- ea: `0x20ab0`
- end: `0x20b07`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::set_PrintTicket`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1d0c0`
- `0x1ee90`
- `0x1ef70`
- `0x20ab0`

## string_xrefs

- `0x20abb`: `ReachPackaging_PrintTicketAlreadyCommitted`

## pseudocode

```c

```

## disassembly

```asm
0x20ab0  ldarg.1
0x20ab1  brfalse.s loc_20AFF
0x20ab3  ldarg.0
0x20ab4  ldfld    bool System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::_isPrintTicketCommitted
0x20ab9  brfalse.s loc_20ACB
0x20abb  ldstr    aReachpackaging_1// "ReachPackaging_PrintTicketAlreadyCommit"...
0x20ac0  call     string System.Windows.Xps.SR::Get(string id)
0x20ac5  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x20aca  throw
0x20acb  ldarg.1
0x20acc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x20ad1  ldtoken  System.Printing.PrintTicket
0x20ad6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20adb  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x20ae0  brtrue.s loc_20AF2
0x20ae2  ldstr    aReachpackaging_2// "ReachPackaging_NotAPrintTicket"
0x20ae7  call     string System.Windows.Xps.SR::Get(string id)
0x20aec  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x20af1  throw
0x20af2  ldarg.0
0x20af3  ldarg.1
0x20af4  callvirt instance class System.Printing.PrintTicket System.Printing.PrintTicket::Clone()
0x20af9  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::_printTicket
0x20afe  ret
0x20aff  ldarg.0
0x20b00  ldnull
0x20b01  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter::_printTicket
0x20b06  ret
```
