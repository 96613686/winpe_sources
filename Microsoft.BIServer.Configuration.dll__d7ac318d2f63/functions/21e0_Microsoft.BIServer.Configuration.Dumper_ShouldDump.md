# Microsoft.BIServer.Configuration.Dumper::ShouldDump

- ea: `0x21e0`
- end: `0x222e`
- name: `Microsoft.BIServer.Configuration.Dumper::ShouldDump`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f90`

## callees

- `0x21b0`
- `0x21e0`
- `0x2230`

## string_xrefs

- `0x21fb`: `Skipped creating a dump file for the error {0}, because a dump with the identical stack trace (with signature {1}) was already created.`

## pseudocode

```c

```

## disassembly

```asm
0x21e0  ldarg.1
0x21e1  brtrue.s loc_21E5
0x21e3  ldc.i4.1
0x21e4  ret
0x21e5  ldarg.0
0x21e6  ldarg.1
0x21e7  call     instance bool Microsoft.BIServer.Configuration.Dumper::ContainsExcludedException(class [mscorlib]System.Exception root)
0x21ec  brtrue.s loc_222C
0x21ee  ldarg.0
0x21ef  ldarg.1
0x21f0  ldloca.s 0
0x21f2  call     instance bool Microsoft.BIServer.Configuration.Dumper::ExistsInCache(class [mscorlib]System.Exception optionalException, [out] int32& hash)
0x21f7  brtrue.s loc_21FB
0x21f9  ldc.i4.1
0x21fa  ret
0x21fb  ldstr    aSkippedCreatin// "Skipped creating a dump file for the er"...
0x2200  ldc.i4.2
0x2201  newarr   [mscorlib]System.Object
0x2206  dup
0x2207  ldc.i4.0
0x2208  ldarg.1
0x2209  brtrue.s loc_2212
0x220b  ldsfld   string [mscorlib]System.String::Empty
0x2210  br.s     loc_221D
0x2212  ldarg.1
0x2213  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x2218  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x221d  stelem.ref
0x221e  dup
0x221f  ldc.i4.1
0x2220  ldloc.0
0x2221  box      [mscorlib]System.UInt32
0x2226  stelem.ref
0x2227  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x222c  ldc.i4.0
0x222d  ret
```
