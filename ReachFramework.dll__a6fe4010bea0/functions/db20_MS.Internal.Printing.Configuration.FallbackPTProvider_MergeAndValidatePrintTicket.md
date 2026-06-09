# MS.Internal.Printing.Configuration.FallbackPTProvider::MergeAndValidatePrintTicket

- ea: `0xdb20`
- end: `0xdbac`
- name: `MS.Internal.Printing.Configuration.FallbackPTProvider::MergeAndValidatePrintTicket`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0xdb20`
- `0xdd00`
- `0xddb0`
- `0xdde0`
- `0xdeb0`
- `0xdfc0`
- `0x17d80`
- `0x180d0`
- `0x18ec0`
- `0x192b0`
- `0x19310`

## pseudocode

```c

```

## disassembly

```asm
0xdb20  ldarg.0
0xdb21  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::VerifyAccess()
0xdb26  ldc.i4.m1
0xdb27  stloc.0
0xdb28  ldarg.0
0xdb29  ldc.i4.1
0xdb2a  call     instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.FallbackPTProvider::GetDEVMODE(valuetype System.Printing.Interop.BaseDevModeType baseType)
0xdb2f  stloc.1
0xdb30  ldarg.1
0xdb31  brtrue.s loc_DB36
0xdb33  ldnull
0xdb34  br.s     loc_DB3C
0xdb36  ldarg.1
0xdb37  newobj   instance void MS.Internal.Printing.Configuration.InternalPrintTicket::.ctor(class [mscorlib]System.IO.Stream xmlStream)
0xdb3c  stloc.2
0xdb3d  ldloc.1
0xdb3e  callvirt instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.DevMode::Clone()
0xdb43  stloc.3
0xdb44  ldarg.0
0xdb45  ldloc.3
0xdb46  ldloc.2
0xdb47  ldarg.3
0xdb48  ldloc.0
0xdb49  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::PrintTicketToDevMode(class MS.Internal.Printing.Configuration.DevMode devMode, class MS.Internal.Printing.Configuration.InternalPrintTicket ticket, valuetype System.Printing.PrintTicketScope scope, valuetype MS.Internal.Printing.Configuration.DevModeFields supportedFields)
0xdb4e  ldarg.2
0xdb4f  brtrue.s loc_DB54
0xdb51  ldnull
0xdb52  br.s     loc_DB5A
0xdb54  ldarg.2
0xdb55  newobj   instance void MS.Internal.Printing.Configuration.InternalPrintTicket::.ctor(class [mscorlib]System.IO.Stream xmlStream)
0xdb5a  stloc.s  4
0xdb5c  ldloc.1
0xdb5d  callvirt instance class MS.Internal.Printing.Configuration.DevMode MS.Internal.Printing.Configuration.DevMode::Clone()
0xdb62  stloc.s  5
0xdb64  ldarg.0
0xdb65  ldloc.s  5
0xdb67  ldloc.s  4
0xdb69  ldarg.3
0xdb6a  ldloc.0
0xdb6b  call     instance void MS.Internal.Printing.Configuration.FallbackPTProvider::PrintTicketToDevMode(class MS.Internal.Printing.Configuration.DevMode devMode, class MS.Internal.Printing.Configuration.InternalPrintTicket ticket, valuetype System.Printing.PrintTicketScope scope, valuetype MS.Internal.Printing.Configuration.DevModeFields supportedFields)
0xdb70  ldloc.s  5
0xdb72  ldloc.3
0xdb73  ldloc.3
0xdb74  callvirt instance valuetype MS.Internal.Printing.Configuration.DevModeFields MS.Internal.Printing.Configuration.DevMode::get_Fields()
0xdb79  ldloc.s  5
0xdb7b  callvirt instance valuetype MS.Internal.Printing.Configuration.DevModeFields MS.Internal.Printing.Configuration.DevMode::get_Fields()
0xdb80  not
0xdb81  and
0xdb82  callvirt instance void MS.Internal.Printing.Configuration.DevMode::Copy(class MS.Internal.Printing.Configuration.DevMode src, valuetype MS.Internal.Printing.Configuration.DevModeFields fields)
0xdb87  ldarg.s  4
0xdb89  ldarg.0
0xdb8a  ldloc.s  5
0xdb8c  call     instance bool MS.Internal.Printing.Configuration.FallbackPTProvider::Validate(class MS.Internal.Printing.Configuration.DevMode devMode)
0xdb91  brtrue.s loc_DB96
0xdb93  ldc.i4.1
0xdb94  br.s     loc_DB97
0xdb96  ldc.i4.0
0xdb97  stind.i4
0xdb98  ldarg.0
0xdb99  ldloc.s  5
0xdb9b  ldarg.3
0xdb9c  ldloc.0
0xdb9d  call     instance class MS.Internal.Printing.Configuration.InternalPrintTicket MS.Internal.Printing.Configuration.FallbackPTProvider::DevModeToPrintTicket(class MS.Internal.Printing.Configuration.DevMode devmode, valuetype System.Printing.PrintTicketScope scope, valuetype MS.Internal.Printing.Configuration.DevModeFields supportedFields)
0xdba2  stloc.s  6
0xdba4  ldloc.s  6
0xdba6  callvirt instance class [mscorlib]System.IO.MemoryStream MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlStream()
0xdbab  ret
```
