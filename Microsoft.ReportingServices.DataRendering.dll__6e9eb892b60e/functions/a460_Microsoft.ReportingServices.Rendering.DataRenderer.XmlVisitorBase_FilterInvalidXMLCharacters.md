# Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters

- ea: `0xa460`
- end: `0xa4e1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters`
- size: `129`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3e10`
- `0xa4f0`
- `0xa530`
- `0xa570`

## callees

- `0xa460`

## pseudocode

```c

```

## disassembly

```asm
0xa460  ldc.i4.0
0xa461  stloc.0
0xa462  ldc.i4.0
0xa463  stloc.1
0xa464  br.s     loc_A488
0xa466  ldloc.1
0xa467  ldc.i4.s 9
0xa469  beq.s    loc_A484
0xa46b  ldloc.1
0xa46c  ldc.i4.s 0xD
0xa46e  beq.s    loc_A484
0xa470  ldloc.1
0xa471  ldc.i4.s 0xA
0xa473  beq.s    loc_A484
0xa475  ldarg.0
0xa476  ldloc.1
0xa477  conv.u2
0xa478  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xa47d  ldc.i4.m1
0xa47e  beq.s    loc_A484
0xa480  ldc.i4.1
0xa481  stloc.0
0xa482  br.s     loc_A48D
0xa484  ldloc.1
0xa485  ldc.i4.1
0xa486  add
0xa487  stloc.1
0xa488  ldloc.1
0xa489  ldc.i4.s 0x20
0xa48b  blt.s    loc_A466
0xa48d  ldloc.0
0xa48e  brfalse.s loc_A4DF
0xa490  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xa495  stloc.2
0xa496  ldarg.0
0xa497  stloc.3
0xa498  ldc.i4.0
0xa499  stloc.s  4
0xa49b  br.s     loc_A4CE
0xa49d  ldloc.3
0xa49e  ldloc.s  4
0xa4a0  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xa4a5  stloc.s  5
0xa4a7  ldloc.s  5
0xa4a9  ldc.i4.s 9
0xa4ab  beq.s    loc_A4BF
0xa4ad  ldloc.s  5
0xa4af  ldc.i4.s 0xA
0xa4b1  beq.s    loc_A4BF
0xa4b3  ldloc.s  5
0xa4b5  ldc.i4.s 0xD
0xa4b7  beq.s    loc_A4BF
0xa4b9  ldloc.s  5
0xa4bb  ldc.i4.s 0x20
0xa4bd  blt.s    loc_A4C8
0xa4bf  ldloc.2
0xa4c0  ldloc.s  5
0xa4c2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xa4c7  pop
0xa4c8  ldloc.s  4
0xa4ca  ldc.i4.1
0xa4cb  add
0xa4cc  stloc.s  4
0xa4ce  ldloc.s  4
0xa4d0  ldloc.3
0xa4d1  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa4d6  blt.s    loc_A49D
0xa4d8  ldloc.2
0xa4d9  callvirt instance string [mscorlib]System.Object::ToString()
0xa4de  ret
0xa4df  ldarg.0
0xa4e0  ret
```
