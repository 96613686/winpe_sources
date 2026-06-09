# System.Printing.PrintServer::get_DefaultSpoolDirectory

- ea: `0x121b0`
- end: `0x121ed`
- name: `System.Printing.PrintServer::get_DefaultSpoolDirectory`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x121b0`
- `0x13280`
- `0x13340`
- `0x13460`

## string_xrefs

- `0x121cd`: `DefaultSpoolDirectory`
- `0x121db`: `DefaultSpoolDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x121b0  ldarg.0
0x121b1  call     instance void System.Printing.PrintServer::VerifyAccess()
0x121b6  ldarg.0
0x121b7  ldfld    bool System.Printing.PrintServer::isDelayInitialized
0x121bc  brfalse.s loc_121DA
0x121be  ldarg.0
0x121bf  dup
0x121c0  ldfld    string[] System.Printing.PrintServer::refreshPropertiesFilter
0x121c5  call     instance bool System.Printing.PrintServer::GetUnInitializedData([hasfieldmarshal] string[] value)
0x121ca  brtrue.s loc_121E6
0x121cc  ldarg.0
0x121cd  ldstr    aDefaultspooldi// "DefaultSpoolDirectory"
0x121d2  ldc.i4.0
0x121d3  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x121d8  br.s     loc_121E6
0x121da  ldarg.0
0x121db  ldstr    aDefaultspooldi// "DefaultSpoolDirectory"
0x121e0  ldc.i4.0
0x121e1  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x121e6  ldarg.0
0x121e7  ldfld    string System.Printing.PrintServer::defaultSpoolDirectory
0x121ec  ret
```
