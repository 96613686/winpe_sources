# System.Printing.PrintServer::get_PortThreadPriority

- ea: `0x12240`
- end: `0x1227d`
- name: `System.Printing.PrintServer::get_PortThreadPriority`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x12240`
- `0x13280`
- `0x13340`
- `0x13460`

## string_xrefs

- `0x1225d`: `PortThreadPriority`
- `0x1226b`: `PortThreadPriority`

## pseudocode

```c

```

## disassembly

```asm
0x12240  ldarg.0
0x12241  call     instance void System.Printing.PrintServer::VerifyAccess()
0x12246  ldarg.0
0x12247  ldfld    bool System.Printing.PrintServer::isDelayInitialized
0x1224c  brfalse.s loc_1226A
0x1224e  ldarg.0
0x1224f  dup
0x12250  ldfld    string[] System.Printing.PrintServer::refreshPropertiesFilter
0x12255  call     instance bool System.Printing.PrintServer::GetUnInitializedData([hasfieldmarshal] string[] value)
0x1225a  brtrue.s loc_12276
0x1225c  ldarg.0
0x1225d  ldstr    aPortthreadprio// "PortThreadPriority"
0x12262  ldc.i4.0
0x12263  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x12268  br.s     loc_12276
0x1226a  ldarg.0
0x1226b  ldstr    aPortthreadprio// "PortThreadPriority"
0x12270  ldc.i4.0
0x12271  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x12276  ldarg.0
0x12277  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::portThreadPriority
0x1227c  ret
```
