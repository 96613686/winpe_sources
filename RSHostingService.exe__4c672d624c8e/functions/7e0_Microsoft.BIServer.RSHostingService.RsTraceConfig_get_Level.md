# Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Level

- ea: `0x7e0`
- end: `0x8a0`
- name: `Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Level`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x12b0`
- `0x2430`

## callees

- `0x760`
- `0x7c0`
- `0x7e0`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldsfld   string [mscorlib]System.String::Empty
0x7e5  stloc.0
0x7e6  ldarg.0
0x7e7  call     instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Components()
0x7ec  ldc.i4.1
0x7ed  newarr   [mscorlib]System.Char
0x7f2  dup
0x7f3  ldc.i4.0
0x7f4  ldc.i4.s 0x2C
0x7f6  stelem.i2
0x7f7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x7fc  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__40_0
0x801  dup
0x802  brtrue.s loc_81B
0x804  pop
0x805  ldsfld   class <>c <>c::<>9
0x80a  ldftn    instance bool <>c::<get_Level>b__40_0(string setting)
0x810  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x815  dup
0x816  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__40_0
0x81b  call     T0x2B000004
0x820  call     T0x2B000005
0x825  stloc.1
0x826  ldloc.1
0x827  brfalse.s loc_83D
0x829  ldloc.1
0x82a  ldc.i4.1
0x82b  newarr   [mscorlib]System.Char
0x830  dup
0x831  ldc.i4.0
0x832  ldc.i4.s 0x3A
0x834  stelem.i2
0x835  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x83a  ldc.i4.1
0x83b  ldelem.ref
0x83c  stloc.0
0x83d  ldloc.0
0x83e  ldsfld   string [mscorlib]System.String::Empty
0x843  call     bool [mscorlib]System.String::op_Equality(string, string)
0x848  brfalse.s loc_851
0x84a  ldarg.0
0x84b  call     instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_DefaultTraceSwitch()
0x850  stloc.0
0x851  ldloc.0
0x852  ldstr    a0// "0"
0x857  call     bool [mscorlib]System.String::op_Equality(string, string)
0x85c  brtrue.s loc_894
0x85e  ldloc.0
0x85f  ldstr    a1// "1"
0x864  call     bool [mscorlib]System.String::op_Equality(string, string)
0x869  brtrue.s loc_896
0x86b  ldloc.0
0x86c  ldstr    a2// "2"
0x871  call     bool [mscorlib]System.String::op_Equality(string, string)
0x876  brtrue.s loc_898
0x878  ldloc.0
0x879  ldstr    a3// "3"
0x87e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x883  brtrue.s loc_89A
0x885  ldloc.0
0x886  ldstr    a4// "4"
0x88b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x890  brtrue.s loc_89C
0x892  br.s     loc_89E
0x894  ldc.i4.0
0x895  ret
0x896  ldc.i4.2
0x897  ret
0x898  ldc.i4.3
0x899  ret
0x89a  ldc.i4.4
0x89b  ret
0x89c  ldc.i4.6
0x89d  ret
0x89e  ldc.i4.6
0x89f  ret
```
