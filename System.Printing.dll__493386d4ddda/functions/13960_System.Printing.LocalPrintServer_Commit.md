# System.Printing.LocalPrintServer::Commit

- ea: `0x13960`
- end: `0x13990`
- name: `System.Printing.LocalPrintServer::Commit`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x12140`
- `0x12a40`
- `0x13960`
- `0x13ba0`
- `0x13d00`
- `0x13e10`
- `0x172a0`

## string_xrefs

- `0x13982`: `PrintSystemException.PrintServer.Commit`

## pseudocode

```c

```

## disassembly

```asm
0x13960  ldarg.0
0x13961  call     instance void System.Printing.LocalPrintServer::VerifyAccess()
0x13966  ldarg.0
0x13967  dup
0x13968  call     instance string[] System.Printing.LocalPrintServer::GetAlteredPropertiesFilter()
0x1396d  call     instance void System.Printing.LocalPrintServer::ComitDirtyData(string[] properties)
0x13972  ldarg.0
0x13973  call     instance void System.Printing.PrintServer::Commit()
0x13978  leave.s  loc_1398F
0x1397a  stloc.0
0x1397b  ldarg.0
0x1397c  ldloc.0
0x1397d  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x13982  ldstr    aPrintsystemexc_12// "PrintSystemException.PrintServer.Commit"
0x13987  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0x1398c  throw
0x1398d  leave.s  loc_1398F
0x1398f  ret
```
