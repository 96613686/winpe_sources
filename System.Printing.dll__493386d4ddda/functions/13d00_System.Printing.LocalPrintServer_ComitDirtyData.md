# System.Printing.LocalPrintServer::ComitDirtyData

- ea: `0x13d00`
- end: `0x13d60`
- name: `System.Printing.LocalPrintServer::ComitDirtyData`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x13960`

## callees

- `0x6d50`
- `0xa6f0`
- `0x12a40`
- `0x13d00`
- `0x13db0`
- `0x14540`
- `0x14550`
- `0x17110`
- `0x172a0`

## pseudocode

```c

```

## disassembly

```asm
0x13d00  ldarg.1
0x13d01  brfalse.s loc_13D5F
0x13d03  ldc.i4.0
0x13d04  stloc.0
0x13d05  ldloc.0
0x13d06  ldarg.1
0x13d07  ldlen
0x13d08  bge.s    loc_13D5F
0x13d0a  ldarg.0
0x13d0b  call     instance class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemObject::get_PropertiesCollection()
0x13d10  ldarg.1
0x13d11  ldloc.0
0x13d12  ldelem.ref
0x13d13  call     instance class System.Printing.IndexedProperties.PrintProperty System.Printing.IndexedProperties.PrintPropertyDictionary::GetProperty(string attribName)
0x13d18  stloc.1
0x13d19  ldloc.1
0x13d1a  callvirt instance string System.Printing.IndexedProperties.PrintProperty::get_Name()
0x13d1f  ldstr    aDefaultprintqu// "DefaultPrintQueue"
0x13d24  callvirt instance bool [mscorlib]System.String::Equals(string)
0x13d29  brfalse.s loc_13D59
0x13d2b  ldarg.0
0x13d2c  ldloc.1
0x13d2d  callvirt instance object System.Printing.IndexedProperties.PrintProperty::get_Value()
0x13d32  castclass System.Printing.PrintQueue
0x13d37  call     instance string System.Printing.LocalPrintServer::GetFullPrintQueueName(class System.Printing.PrintQueue queue)
0x13d3c  call     bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetDefaultPrinter([hasfieldmarshal] string value)
0x13d41  pop
0x13d42  leave.s  loc_13D59
0x13d44  stloc.2
0x13d45  ldarg.0
0x13d46  ldloc.2
0x13d47  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x13d4c  ldstr    aPrintsystemexc_20// "PrintSystemException.PrintServer.SetDef"...
0x13d51  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0x13d56  throw
0x13d57  leave.s  loc_13D59
0x13d59  ldloc.0
0x13d5a  ldc.i4.1
0x13d5b  add
0x13d5c  stloc.0
0x13d5d  br.s     loc_13D05
0x13d5f  ret
```
