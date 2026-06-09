# Microsoft.BIServer.HostingEnvironment.Args::SetArgs

- ea: `0x290`
- end: `0x33a`
- name: `Microsoft.BIServer.HostingEnvironment.Args::SetArgs`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1c0`
- `0x250`

## callees

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldc.i4.0
0x291  stloc.0
0x292  br       loc_330
0x297  ldarg.1
0x298  ldloc.0
0x299  ldelem.ref
0x29a  stloc.1
0x29b  ldloc.1
0x29c  ldstr    asc_7010// "-"
0x2a1  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x2a6  brtrue.s loc_2B5
0x2a8  ldloc.1
0x2a9  ldstr    asc_7014// "/"
0x2ae  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x2b3  brfalse.s loc_320
0x2b5  ldloc.1
0x2b6  ldc.i4.1
0x2b7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2bc  stloc.2
0x2bd  ldloc.2
0x2be  ldc.i4.s 0x3D
0x2c0  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x2c5  stloc.3
0x2c6  ldloc.3
0x2c7  brtrue.s loc_2DA
0x2c9  ldstr    aSwitchArgument// "Switch argument {0} cannot begin with '"...
0x2ce  ldloc.2
0x2cf  call     string [mscorlib]System.String::Format(string, object)
0x2d4  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2d9  throw
0x2da  ldloc.3
0x2db  ldc.i4.0
0x2dc  ble.s    loc_311
0x2de  ldloc.2
0x2df  ldc.i4.0
0x2e0  ldloc.3
0x2e1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2e6  stloc.s  4
0x2e8  ldloc.3
0x2e9  ldc.i4.1
0x2ea  add
0x2eb  stloc.s  5
0x2ed  ldloc.2
0x2ee  ldloc.s  5
0x2f0  ldloc.2
0x2f1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f6  ldloc.s  5
0x2f8  sub
0x2f9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2fe  stloc.s  6
0x300  ldarg.0
0x301  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.Args::_switches
0x306  ldloc.s  4
0x308  ldloc.s  6
0x30a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x30f  br.s     loc_32C
0x311  ldarg.0
0x312  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.Args::_switches
0x317  ldloc.2
0x318  ldnull
0x319  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x31e  br.s     loc_32C
0x320  ldarg.0
0x321  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.BIServer.HostingEnvironment.Args::_nonSwitches
0x326  ldloc.1
0x327  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x32c  ldloc.0
0x32d  ldc.i4.1
0x32e  add
0x32f  stloc.0
0x330  ldloc.0
0x331  ldarg.1
0x332  ldlen
0x333  conv.i4
0x334  blt      loc_297
0x339  ret
```
