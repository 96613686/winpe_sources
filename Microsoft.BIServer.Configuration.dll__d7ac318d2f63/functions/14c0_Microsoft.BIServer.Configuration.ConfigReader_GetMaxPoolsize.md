# Microsoft.BIServer.Configuration.ConfigReader::GetMaxPoolsize

- ea: `0x14c0`
- end: `0x14f5`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetMaxPoolsize`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1430`

## callees

- `0x14c0`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  ldarg.0
0x14c1  ldstr    aMaxcatalogconn// "MaxCatalogConnectionPoolSizePerProcess"
0x14c6  ldarg.1
0x14c7  ldc.i4.0
0x14c8  ldc.i4   0x7FFFFFFF
0x14cd  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, int32 minValue, [opt] int32 maxValue)
0x14d2  stloc.0
0x14d3  ldloc.0
0x14d4  brtrue.s loc_14D9
0x14d6  ldc.i4.s 0x64
0x14d8  stloc.0
0x14d9  ldstr    aCatalogMaxConn// "Catalog max connection pool size: {0}"
0x14de  ldloc.0
0x14df  box      [mscorlib]System.Int32
0x14e4  call     string [mscorlib]System.String::Format(string, object)
0x14e9  call     T0x2B000015
0x14ee  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x14f3  ldloc.0
0x14f4  ret
```
