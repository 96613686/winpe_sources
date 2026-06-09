# System.Printing.PrintSystemUNCPathResolver::BuildUncPath

- ea: `0x19a00`
- end: `0x19aa7`
- name: `System.Printing.PrintSystemUNCPathResolver::BuildUncPath`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x196d0`

## callees

- `0x19980`
- `0x19a00`

## pseudocode

```c

```

## disassembly

```asm
0x19a00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x19a05  stloc.0
0x19a06  ldarg.0
0x19a07  ldfld    string System.Printing.PrintSystemUNCPathResolver::serverName
0x19a0c  stloc.1
0x19a0d  ldloc.1
0x19a0e  brfalse.s loc_19A5A
0x19a10  ldarg.0
0x19a11  ldfld    string System.Printing.PrintSystemUNCPathResolver::printerName
0x19a16  brfalse.s loc_19A5A
0x19a18  ldloc.1
0x19a19  ldstr    asc_2537E// "\\\\"
0x19a1e  ldc.i4.4
0x19a1f  call     instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x19a24  brfalse.s loc_19A40
0x19a26  ldloc.0
0x19a27  ldstr    a01// "{0}\\{1}"
0x19a2c  ldarg.0
0x19a2d  ldfld    string System.Printing.PrintSystemUNCPathResolver::serverName
0x19a32  ldarg.0
0x19a33  ldfld    string System.Printing.PrintSystemUNCPathResolver::printerName
0x19a38  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x19a3d  pop
0x19a3e  br.s     loc_19A83
0x19a40  ldloc.0
0x19a41  ldstr    a01_0// "\\\\{0}\\{1}"
0x19a46  ldarg.0
0x19a47  ldfld    string System.Printing.PrintSystemUNCPathResolver::serverName
0x19a4c  ldarg.0
0x19a4d  ldfld    string System.Printing.PrintSystemUNCPathResolver::printerName
0x19a52  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x19a57  pop
0x19a58  br.s     loc_19A83
0x19a5a  ldarg.0
0x19a5b  ldfld    string System.Printing.PrintSystemUNCPathResolver::printerName
0x19a60  stloc.3
0x19a61  ldloc.3
0x19a62  brfalse.s loc_19A73
0x19a64  ldloc.0
0x19a65  ldstr    a0_0// "{0}"
0x19a6a  ldloc.3
0x19a6b  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x19a70  pop
0x19a71  br.s     loc_19A83
0x19a73  ldloc.1
0x19a74  brfalse.s loc_19A83
0x19a76  ldloc.0
0x19a77  ldstr    a0_1// "\\\\{0}"
0x19a7c  ldloc.1
0x19a7d  call     instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x19a82  pop
0x19a83  ldloc.0
0x19a84  brfalse.s loc_19AA6
0x19a86  ldloc.0
0x19a87  callvirt instance string [mscorlib]System.Text.StringBuilder::ToString()
0x19a8c  stloc.2
0x19a8d  ldarg.0
0x19a8e  ldloc.2
0x19a8f  stfld    string System.Printing.PrintSystemUNCPathResolver::uncPath
0x19a94  ldloc.2
0x19a95  brfalse.s loc_19AA6
0x19a97  ldarg.0
0x19a98  ldfld    string System.Printing.PrintSystemUNCPathResolver::serverName
0x19a9d  brfalse.s loc_19AA6
0x19a9f  ldloc.2
0x19aa0  call     bool System.Printing.PrintSystemUNCPathResolver::ValidateUNCName([hasfieldmarshal] string value)
0x19aa5  pop
0x19aa6  ret
```
