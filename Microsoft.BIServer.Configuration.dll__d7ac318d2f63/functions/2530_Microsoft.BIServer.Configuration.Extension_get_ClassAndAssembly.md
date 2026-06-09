# Microsoft.BIServer.Configuration.Extension::get_ClassAndAssembly

- ea: `0x2530`
- end: `0x2547`
- name: `Microsoft.BIServer.Configuration.Extension::get_ClassAndAssembly`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x24b0`
- `0x24d0`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldarg.0
0x2531  call     instance string Microsoft.BIServer.Configuration.Extension::get_Class()
0x2536  ldstr    asc_9430// ","
0x253b  ldarg.0
0x253c  call     instance string Microsoft.BIServer.Configuration.Extension::get_Assembly()
0x2541  call     string [mscorlib]System.String::Concat(string, string, string)
0x2546  ret
```
