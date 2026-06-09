# Microsoft.BIServer.Configuration.ConfigReader::GetApplicationVirtualServerDirectory

- ea: `0x12b0`
- end: `0x12e1`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetApplicationVirtualServerDirectory`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1010`
- `0x12b0`
- `0x4750`
- `0x7060`

## pseudocode

```c

```

## disassembly

```asm
0x12b0  newobj   instance void <>c__DisplayClass56_0::.ctor()
0x12b5  stloc.0
0x12b6  ldloc.0
0x12b7  ldarg.1
0x12b8  stfld    string <>c__DisplayClass56_0::applicationName
0x12bd  ldarg.0
0x12be  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.ConfigReader::get_Applications()
0x12c3  ldloc.0
0x12c4  ldftn    instance bool <>c__DisplayClass56_0::<GetApplicationVirtualServerDirectory>b__0(class Microsoft.BIServer.Configuration.Application a)
0x12ca  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.Application, bool>::.ctor(object, native int)
0x12cf  call     T0x2B00000D
0x12d4  stloc.1
0x12d5  ldloc.1
0x12d6  brfalse.s loc_12DF
0x12d8  ldloc.1
0x12d9  callvirt instance string Microsoft.BIServer.Configuration.Application::get_VirtualDirectory()
0x12de  ret
0x12df  ldnull
0x12e0  ret
```
