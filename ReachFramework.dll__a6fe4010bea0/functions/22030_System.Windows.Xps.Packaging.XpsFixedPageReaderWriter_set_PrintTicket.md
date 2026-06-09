# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::set_PrintTicket

- ea: `0x22030`
- end: `0x22087`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::set_PrintTicket`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1d0c0`
- `0x1ee90`
- `0x1ef70`
- `0x22030`

## string_xrefs

- `0x2203b`: `ReachPackaging_PrintTicketAlreadyCommitted`

## pseudocode

```c

```

## disassembly

```asm
0x22030  ldarg.1
0x22031  brfalse.s loc_2207F
0x22033  ldarg.0
0x22034  ldfld    bool System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_isPrintTicketCommitted
0x22039  brfalse.s loc_2204B
0x2203b  ldstr    aReachpackaging_1// "ReachPackaging_PrintTicketAlreadyCommit"...
0x22040  call     string System.Windows.Xps.SR::Get(string id)
0x22045  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x2204a  throw
0x2204b  ldarg.1
0x2204c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22051  ldtoken  System.Printing.PrintTicket
0x22056  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2205b  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x22060  brtrue.s loc_22072
0x22062  ldstr    aReachpackaging_2// "ReachPackaging_NotAPrintTicket"
0x22067  call     string System.Windows.Xps.SR::Get(string id)
0x2206c  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x22071  throw
0x22072  ldarg.0
0x22073  ldarg.1
0x22074  callvirt instance class System.Printing.PrintTicket System.Printing.PrintTicket::Clone()
0x22079  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_printTicket
0x2207e  ret
0x2207f  ldarg.0
0x22080  ldnull
0x22081  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_printTicket
0x22086  ret
```
