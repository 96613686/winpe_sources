# Microsoft.BIServer.Configuration.ConfigReader::Convert

- ea: `0x1030`
- end: `0x10ff`
- name: `Microsoft.BIServer.Configuration.ConfigReader::Convert`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1030`

## pseudocode

```c

```

## disassembly

```asm
0x1030  ldtoken  Microsoft.BIServer.Configuration.AuthenticationTypes
0x1035  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x103a  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x103f  call     T0x2B00000A
0x1044  call     T0x2B00000B
0x1049  ldsfld   class [mscorlib]System.Func`2<valuetype Microsoft.BIServer.Configuration.AuthenticationTypes, int32> <>c::<>9__51_0
0x104e  dup
0x104f  brtrue.s loc_1068
0x1051  pop
0x1052  ldsfld   class <>c <>c::<>9
0x1057  ldftn    instance int32 <>c::<Convert>b__51_0(valuetype Microsoft.BIServer.Configuration.AuthenticationTypes t)
0x105d  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.BIServer.Configuration.AuthenticationTypes, int32>::.ctor(object, native int)
0x1062  dup
0x1063  stsfld   class [mscorlib]System.Func`2<valuetype Microsoft.BIServer.Configuration.AuthenticationTypes, int32> <>c::<>9__51_0
0x1068  call     T0x2B00000C
0x106d  stloc.0
0x106e  ldc.i4.0
0x106f  stloc.1
0x1070  br       loc_10F7
0x1075  ldarg.0
0x1076  ldloc.0
0x1077  and
0x1078  stloc.2
0x1079  ldloc.2
0x107a  ldc.i4.s 0x10
0x107c  bgt.s    loc_10AF
0x107e  ldloc.2
0x107f  switch   loc_10F3, loc_10BB, loc_10BB, loc_10DD, loc_10C1, loc_10DD, loc_10DD, loc_10DD, loc_10C7
0x10a8  ldloc.2
0x10a9  ldc.i4.s 0x10
0x10ab  beq.s    loc_10CD
0x10ad  br.s     loc_10DD
0x10af  ldloc.2
0x10b0  ldc.i4.s 0x20
0x10b2  beq.s    loc_10D7
0x10b4  ldloc.2
0x10b5  ldc.i4.s 0x40
0x10b7  beq.s    loc_10CD
0x10b9  br.s     loc_10DD
0x10bb  ldloc.1
0x10bc  ldc.i4.2
0x10bd  or
0x10be  stloc.1
0x10bf  br.s     loc_10F3
0x10c1  ldloc.1
0x10c2  ldc.i4.4
0x10c3  or
0x10c4  stloc.1
0x10c5  br.s     loc_10F3
0x10c7  ldloc.1
0x10c8  ldc.i4.8
0x10c9  or
0x10ca  stloc.1
0x10cb  br.s     loc_10F3
0x10cd  ldloc.1
0x10ce  ldc.i4   0x8000
0x10d3  or
0x10d4  stloc.1
0x10d5  br.s     loc_10F3
0x10d7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x10dc  throw
0x10dd  ldstr    aAuthentication// "authenticationTypes"
0x10e2  ldloc.2
0x10e3  box      Microsoft.BIServer.Configuration.AuthenticationTypes
0x10e8  ldstr    aUnknownAuthent// "Unknown Authentication Type"
0x10ed  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, object, string)
0x10f2  throw
0x10f3  ldloc.0
0x10f4  ldc.i4.1
0x10f5  shr
0x10f6  stloc.0
0x10f7  ldloc.0
0x10f8  brtrue   loc_1075
0x10fd  ldloc.1
0x10fe  ret
```
