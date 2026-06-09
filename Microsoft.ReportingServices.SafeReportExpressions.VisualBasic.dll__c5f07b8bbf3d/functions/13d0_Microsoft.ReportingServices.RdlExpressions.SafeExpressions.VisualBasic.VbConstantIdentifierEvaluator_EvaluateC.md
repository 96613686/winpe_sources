# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.VbConstantIdentifierEvaluator::EvaluateConstant

- ea: `0x13d0`
- end: `0x142e`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.VbConstantIdentifierEvaluator::EvaluateConstant`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x13d0`

## pseudocode

```c

```

## disassembly

```asm
0x13d0  ldarg.1
0x13d1  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x13d6  stloc.1
0x13d7  ldloc.1
0x13d8  ldstr    aVbcrlf// "VBCRLF"
0x13dd  ldc.i4.0
0x13de  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x13e3  brfalse.s loc_1403
0x13e5  ldloc.1
0x13e6  ldstr    aVbcr// "VBCR"
0x13eb  ldc.i4.0
0x13ec  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x13f1  brfalse.s loc_140B
0x13f3  ldloc.1
0x13f4  ldstr    aVblf// "VBLF"
0x13f9  ldc.i4.0
0x13fa  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x13ff  brfalse.s loc_1413
0x1401  br.s     loc_141B
0x1403  ldstr    asc_25D2// "\r\n"
0x1408  stloc.0
0x1409  br.s     loc_142C
0x140b  ldstr    asc_25D8// "\r"
0x1410  stloc.0
0x1411  br.s     loc_142C
0x1413  ldstr    asc_25DC// "\n"
0x1418  stloc.0
0x1419  br.s     loc_142C
0x141b  ldstr    aVisualBasicCon// "Visual Basic constant <{0}> is not supp"...
0x1420  ldarg.1
0x1421  call     string [mscorlib]System.String::Format(string, object)
0x1426  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x142b  throw
0x142c  ldloc.0
0x142d  ret
```
