# Microsoft.BIServer.Configuration.Dumper::ParseFlags

- ea: `0x22b0`
- end: `0x2325`
- name: `Microsoft.BIServer.Configuration.Dumper::ParseFlags`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1e00`

## callees

- `0x22b0`
- `0x2380`

## string_xrefs

- `0x2305`: `No flag is configured for the Dumper. Using Default settings.`

## pseudocode

```c

```

## disassembly

```asm
0x22b0  ldc.i4.0
0x22b1  stloc.0
0x22b2  ldarg.0
0x22b3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x22b8  brtrue.s loc_2305
0x22ba  ldarg.0
0x22bb  ldc.i4.1
0x22bc  newarr   [mscorlib]System.Char
0x22c1  dup
0x22c2  ldc.i4.0
0x22c3  ldc.i4.s 0x2C
0x22c5  stelem.i2
0x22c6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x22cb  stloc.1
0x22cc  ldc.i4.0
0x22cd  stloc.2
0x22ce  br.s     loc_22FD
0x22d0  ldloc.1
0x22d1  ldloc.2
0x22d2  ldelem.ref
0x22d3  stloc.3
0x22d4  ldloc.3
0x22d5  ldloca.s 4
0x22d7  call     T0x2B000024
0x22dc  brfalse.s loc_22E5
0x22de  ldloc.0
0x22df  ldloc.s  4
0x22e1  or
0x22e2  stloc.0
0x22e3  br.s     loc_22F9
0x22e5  ldstr    aInvalidDumperF// "Invalid Dumper flag: {0}"
0x22ea  ldc.i4.1
0x22eb  newarr   [mscorlib]System.Object
0x22f0  dup
0x22f1  ldc.i4.0
0x22f2  ldloc.3
0x22f3  stelem.ref
0x22f4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x22f9  ldloc.2
0x22fa  ldc.i4.1
0x22fb  add
0x22fc  stloc.2
0x22fd  ldloc.2
0x22fe  ldloc.1
0x22ff  ldlen
0x2300  conv.i4
0x2301  blt.s    loc_22D0
0x2303  br.s     loc_2314
0x2305  ldstr    aNoFlagIsConfig// "No flag is configured for the Dumper. U"...
0x230a  call     T0x2B000015
0x230f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2314  call     bool Microsoft.BIServer.Configuration.Dumper::IsPublicBuild()
0x2319  brtrue.s loc_2323
0x231b  ldloc.0
0x231c  ldc.i4   0xFFFFFBFF
0x2321  and
0x2322  stloc.0
0x2323  ldloc.0
0x2324  ret
```
