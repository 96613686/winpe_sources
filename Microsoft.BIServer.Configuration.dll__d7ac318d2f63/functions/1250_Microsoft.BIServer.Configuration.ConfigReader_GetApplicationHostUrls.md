# Microsoft.BIServer.Configuration.ConfigReader::GetApplicationHostUrls

- ea: `0x1250`
- end: `0x12a5`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetApplicationHostUrls`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1010`
- `0x1250`
- `0x4770`
- `0x7020`

## pseudocode

```c

```

## disassembly

```asm
0x1250  newobj   instance void <>c__DisplayClass55_0::.ctor()
0x1255  stloc.0
0x1256  ldloc.0
0x1257  ldarg.1
0x1258  stfld    string <>c__DisplayClass55_0::applicationName
0x125d  ldarg.0
0x125e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.Application> Microsoft.BIServer.Configuration.ConfigReader::get_Applications()
0x1263  ldloc.0
0x1264  ldftn    instance bool <>c__DisplayClass55_0::<GetApplicationHostUrls>b__0(class Microsoft.BIServer.Configuration.Application a)
0x126a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.Application, bool>::.ctor(object, native int)
0x126f  call     T0x2B00000D
0x1274  stloc.1
0x1275  ldloc.1
0x1276  brfalse.s loc_12A3
0x1278  ldloc.1
0x1279  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x127e  ldsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.URL, string> <>c::<>9__55_1
0x1283  dup
0x1284  brtrue.s loc_129D
0x1286  pop
0x1287  ldsfld   class <>c <>c::<>9
0x128c  ldftn    instance string <>c::<GetApplicationHostUrls>b__55_1(class Microsoft.BIServer.Configuration.URL url)
0x1292  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.URL, string>::.ctor(object, native int)
0x1297  dup
0x1298  stsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.URL, string> <>c::<>9__55_1
0x129d  call     T0x2B00000E
0x12a2  ret
0x12a3  ldnull
0x12a4  ret
```
