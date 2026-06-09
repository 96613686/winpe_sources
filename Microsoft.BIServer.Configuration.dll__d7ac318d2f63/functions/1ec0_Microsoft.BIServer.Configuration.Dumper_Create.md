# Microsoft.BIServer.Configuration.Dumper::Create

- ea: `0x1ec0`
- end: `0x1f1d`
- name: `Microsoft.BIServer.Configuration.Dumper::Create`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1e00`
- `0x1ec0`

## string_xrefs

- `0x1eda`: `config`
- `0x1f01`: `Dumper must not be created multiple times.`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldsfld   object Microsoft.BIServer.Configuration.Dumper::_lockObj
0x1ec5  stloc.0
0x1ec6  ldc.i4.0
0x1ec7  stloc.1
0x1ec8  ldloc.0
0x1ec9  ldloca.s 1
0x1ecb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ed0  ldsfld   class Microsoft.BIServer.Configuration.Dumper Microsoft.BIServer.Configuration.Dumper::_dumper
0x1ed5  brtrue.s loc_1F01
0x1ed7  ldarg.0
0x1ed8  brtrue.s loc_1EE5
0x1eda  ldstr    aConfig// "config"
0x1edf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ee4  throw
0x1ee5  ldarg.1
0x1ee6  brtrue.s loc_1EF3
0x1ee8  ldstr    aDumperadapter// "dumperAdapter"
0x1eed  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ef2  throw
0x1ef3  ldarg.0
0x1ef4  ldarg.1
0x1ef5  newobj   instance void Microsoft.BIServer.Configuration.Dumper::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig config, class Microsoft.BIServer.Configuration.IDumperAdapter dumperAdapter)
0x1efa  stsfld   class Microsoft.BIServer.Configuration.Dumper Microsoft.BIServer.Configuration.Dumper::_dumper
0x1eff  leave.s  loc_1F1C
0x1f01  ldstr    aDumperMustNotB// "Dumper must not be created multiple tim"...
0x1f06  call     T0x2B000015
0x1f0b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x1f10  leave.s  loc_1F1C
0x1f12  ldloc.1
0x1f13  brfalse.s loc_1F1B
0x1f15  ldloc.0
0x1f16  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1f1b  endfinally
0x1f1c  ret
```
