# System.Printing.PrintServer::Commit

- ea: `0x12140`
- end: `0x1216a`
- name: `System.Printing.PrintServer::Commit`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x13960`

## callees

- `0x12140`
- `0x12a40`
- `0x13150`
- `0x13370`
- `0x13460`
- `0x172a0`

## string_xrefs

- `0x1215c`: `PrintSystemException.PrintServer.Commit`

## pseudocode

```c

```

## disassembly

```asm
0x12140  ldarg.0
0x12141  call     instance void System.Printing.PrintServer::VerifyAccess()
0x12146  ldarg.0
0x12147  dup
0x12148  call     instance string[] System.Printing.PrintServer::GetAlteredPropertiesFilter()
0x1214d  call     instance void System.Printing.PrintServer::ComitDirtyData(string[] properties)
0x12152  leave.s  loc_12169
0x12154  stloc.0
0x12155  ldarg.0
0x12156  ldloc.0
0x12157  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x1215c  ldstr    aPrintsystemexc_12// "PrintSystemException.PrintServer.Commit"
0x12161  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0x12166  throw
0x12167  leave.s  loc_12169
0x12169  ret
```
