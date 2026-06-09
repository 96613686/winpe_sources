# Microsoft.VisualStudio.Setup.OperationLogger::.ctor

- ea: `0x2950`
- end: `0x297e`
- name: `Microsoft.VisualStudio.Setup.OperationLogger::.ctor`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf0`
- `0x1070`
- `0x3c10`
- `0x5530`
- `0x5920`
- `0x5f80`

## callees

- `0x2950`

## pseudocode

```c

```

## disassembly

```asm
0x2950  ldarg.0
0x2951  call     instance void [mscorlib]System.Object::.ctor()
0x2956  ldarg.0
0x2957  ldarg.1
0x2958  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OperationLogger::logger
0x295d  ldarg.0
0x295e  ldarg.2
0x295f  stfld    string Microsoft.VisualStudio.Setup.OperationLogger::text
0x2964  ldarg.1
0x2965  brfalse.s loc_297D
0x2967  ldarg.1
0x2968  ldstr    aBegin// "BEGIN: "
0x296d  ldarg.2
0x296e  call     string [mscorlib]System.String::Concat(string, string)
0x2973  call     T0x2B00000A
0x2978  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x297d  ret
```
