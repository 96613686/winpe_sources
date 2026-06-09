# Microsoft.BIServer.Configuration.Dumper::DumpHere

- ea: `0x1f20`
- end: `0x1f44`
- name: `Microsoft.BIServer.Configuration.Dumper::DumpHere`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1f20`
- `0x1f90`

## string_xrefs

- `0x1f34`: `Dumper must be created before triggering a dump.`

## pseudocode

```c

```

## disassembly

```asm
0x1f20  ldsfld   class Microsoft.BIServer.Configuration.Dumper Microsoft.BIServer.Configuration.Dumper::_dumper
0x1f25  brfalse.s loc_1F34
0x1f27  ldsfld   class Microsoft.BIServer.Configuration.Dumper Microsoft.BIServer.Configuration.Dumper::_dumper
0x1f2c  ldarg.0
0x1f2d  ldc.i4.0
0x1f2e  callvirt instance void Microsoft.BIServer.Configuration.Dumper::GenerateDump(class [mscorlib]System.Exception optionalException, bool unhandledException)
0x1f33  ret
0x1f34  ldstr    aDumperMustBeCr// "Dumper must be created before triggerin"...
0x1f39  call     T0x2B000015
0x1f3e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x1f43  ret
```
