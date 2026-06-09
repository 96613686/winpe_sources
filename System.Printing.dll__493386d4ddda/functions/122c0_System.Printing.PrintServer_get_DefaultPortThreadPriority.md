# System.Printing.PrintServer::get_DefaultPortThreadPriority

- ea: `0x122c0`
- end: `0x122fd`
- name: `System.Printing.PrintServer::get_DefaultPortThreadPriority`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x122c0`
- `0x13280`
- `0x13340`
- `0x13460`

## string_xrefs

- `0x122dd`: `DefaultPortThreadPriority`
- `0x122eb`: `DefaultPortThreadPriority`

## pseudocode

```c

```

## disassembly

```asm
0x122c0  ldarg.0
0x122c1  call     instance void System.Printing.PrintServer::VerifyAccess()
0x122c6  ldarg.0
0x122c7  ldfld    bool System.Printing.PrintServer::isDelayInitialized
0x122cc  brfalse.s loc_122EA
0x122ce  ldarg.0
0x122cf  dup
0x122d0  ldfld    string[] System.Printing.PrintServer::refreshPropertiesFilter
0x122d5  call     instance bool System.Printing.PrintServer::GetUnInitializedData([hasfieldmarshal] string[] value)
0x122da  brtrue.s loc_122F6
0x122dc  ldarg.0
0x122dd  ldstr    aDefaultportthr// "DefaultPortThreadPriority"
0x122e2  ldc.i4.0
0x122e3  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x122e8  br.s     loc_122F6
0x122ea  ldarg.0
0x122eb  ldstr    aDefaultportthr// "DefaultPortThreadPriority"
0x122f0  ldc.i4.0
0x122f1  call     instance void System.Printing.PrintServer::GetDataFromServer(string property, [hasfieldmarshal] bool forceRefresh)
0x122f6  ldarg.0
0x122f7  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.PrintServer::defaultPortThreadPriority
0x122fc  ret
```
