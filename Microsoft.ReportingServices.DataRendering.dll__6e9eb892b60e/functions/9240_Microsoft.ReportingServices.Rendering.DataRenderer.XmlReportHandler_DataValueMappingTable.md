# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable

- ea: `0x9240`
- end: `0x93db`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8f00`

## callees

- `0x9240`

## pseudocode

```c

```

## disassembly

```asm
0x9240  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x9245  ldarg.1
0x9246  ldnull
0x9247  cgt.un
0x9249  ldstr    aChartdatapoint// "ChartDataPoint element name cannot be n"...
0x924e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9253  ldc.i4.m1
0x9254  stloc.0
0x9255  ldarg.1
0x9256  brfalse  loc_93D9
0x925b  ldarg.1
0x925c  call     instance int32 [mscorlib]System.String::get_Length()
0x9261  stloc.1
0x9262  ldloc.1
0x9263  ldc.i4.1
0x9264  sub
0x9265  switch   loc_9287, loc_93D9, loc_92C0, loc_92A4, loc_9340, loc_9352
0x9282  br       loc_93D9
0x9287  ldarg.1
0x9288  ldc.i4.0
0x9289  call     instance char [mscorlib]System.String::get_Chars(int32)
0x928e  stloc.2
0x928f  ldloc.2
0x9290  ldc.i4.s 0x58
0x9292  beq      loc_9361
0x9297  ldloc.2
0x9298  ldc.i4.s 0x59
0x929a  beq      loc_936E
0x929f  br       loc_93D9
0x92a4  ldarg.1
0x92a5  ldc.i4.0
0x92a6  call     instance char [mscorlib]System.String::get_Chars(int32)
0x92ab  stloc.2
0x92ac  ldloc.2
0x92ad  ldc.i4.s 0x48
0x92af  beq.s    loc_92EC
0x92b1  ldloc.2
0x92b2  ldc.i4.s 0x4D
0x92b4  beq.s    loc_9301
0x92b6  ldloc.2
0x92b7  ldc.i4.s 0x53
0x92b9  beq.s    loc_92D7
0x92bb  br       loc_93D9
0x92c0  ldarg.1
0x92c1  ldc.i4.0
0x92c2  call     instance char [mscorlib]System.String::get_Chars(int32)
0x92c7  stloc.2
0x92c8  ldloc.2
0x92c9  ldc.i4.s 0x45
0x92cb  beq.s    loc_932B
0x92cd  ldloc.2
0x92ce  ldc.i4.s 0x4C
0x92d0  beq.s    loc_9316
0x92d2  br       loc_93D9
0x92d7  ldarg.1
0x92d8  ldstr    aSize// "Size"
0x92dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92e2  brtrue   loc_9392
0x92e7  br       loc_93D9
0x92ec  ldarg.1
0x92ed  ldstr    aHigh// "High"
0x92f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x92f7  brtrue   loc_939B
0x92fc  br       loc_93D9
0x9301  ldarg.1
0x9302  ldstr    aMean// "Mean"
0x9307  call     bool [mscorlib]System.String::op_Equality(string, string)
0x930c  brtrue   loc_93D9
0x9311  br       loc_93D9
0x9316  ldarg.1
0x9317  ldstr    aLow// "Low"
0x931c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9321  brtrue   loc_93A9
0x9326  br       loc_93D9
0x932b  ldarg.1
0x932c  ldstr    aEnd// "End"
0x9331  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9336  brtrue   loc_93C5
0x933b  br       loc_93D9
0x9340  ldarg.1
0x9341  ldstr    aStart// "Start"
0x9346  call     bool [mscorlib]System.String::op_Equality(string, string)
0x934b  brtrue.s loc_93B7
0x934d  br       loc_93D9
0x9352  ldarg.1
0x9353  ldstr    aMedian// "Median"
0x9358  call     bool [mscorlib]System.String::op_Equality(string, string)
0x935d  brtrue.s loc_93D9
0x935f  br.s     loc_93D9
0x9361  ldarg.2
0x9362  ldc.i4.4
0x9363  beq.s    loc_936A
0x9365  ldarg.3
0x9366  ldc.i4.s 0xB
0x9368  bne.un.s loc_93D9
0x936a  ldc.i4.0
0x936b  stloc.0
0x936c  br.s     loc_93D9
0x936e  ldarg.2
0x936f  brfalse.s loc_9381
0x9371  ldarg.2
0x9372  ldc.i4.1
0x9373  beq.s    loc_9381
0x9375  ldarg.2
0x9376  ldc.i4.2
0x9377  beq.s    loc_9381
0x9379  ldarg.2
0x937a  ldc.i4.5
0x937b  beq.s    loc_9381
0x937d  ldarg.2
0x937e  ldc.i4.3
0x937f  bne.un.s loc_9385
0x9381  ldc.i4.0
0x9382  stloc.0
0x9383  br.s     loc_93D9
0x9385  ldarg.2
0x9386  ldc.i4.4
0x9387  beq.s    loc_938E
0x9389  ldarg.3
0x938a  ldc.i4.s 0xB
0x938c  bne.un.s loc_93D9
0x938e  ldc.i4.1
0x938f  stloc.0
0x9390  br.s     loc_93D9
0x9392  ldarg.3
0x9393  ldc.i4.s 0xB
0x9395  bne.un.s loc_93D9
0x9397  ldc.i4.2
0x9398  stloc.0
0x9399  br.s     loc_93D9
0x939b  ldarg.3
0x939c  ldc.i4.s 0xD
0x939e  beq.s    loc_93A5
0x93a0  ldarg.3
0x93a1  ldc.i4.s 0xC
0x93a3  bne.un.s loc_93D9
0x93a5  ldc.i4.0
0x93a6  stloc.0
0x93a7  br.s     loc_93D9
0x93a9  ldarg.3
0x93aa  ldc.i4.s 0xD
0x93ac  beq.s    loc_93B3
0x93ae  ldarg.3
0x93af  ldc.i4.s 0xC
0x93b1  bne.un.s loc_93D9
0x93b3  ldc.i4.1
0x93b4  stloc.0
0x93b5  br.s     loc_93D9
0x93b7  ldarg.3
0x93b8  ldc.i4.s 0xD
0x93ba  beq.s    loc_93C1
0x93bc  ldarg.3
0x93bd  ldc.i4.s 0xC
0x93bf  bne.un.s loc_93D9
0x93c1  ldc.i4.2
0x93c2  stloc.0
0x93c3  br.s     loc_93D9
0x93c5  ldarg.3
0x93c6  ldc.i4.s 0xD
0x93c8  beq.s    loc_93CF
0x93ca  ldarg.3
0x93cb  ldc.i4.s 0xC
0x93cd  bne.un.s loc_93D9
0x93cf  ldarg.s  4
0x93d1  brfalse.s loc_93D7
0x93d3  ldc.i4.3
0x93d4  stloc.0
0x93d5  br.s     loc_93D9
0x93d7  ldc.i4.2
0x93d8  stloc.0
0x93d9  ldloc.0
0x93da  ret
```
