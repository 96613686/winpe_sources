# Microsoft.BIServer.Configuration.ConfigReader::ReadApplications

- ea: `0x13e0`
- end: `0x1426`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadApplications`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b90`

## callees

- `0x13e0`

## pseudocode

```c

```

## disassembly

```asm
0x13e0  ldarg.0
0x13e1  ldarg.0
0x13e2  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x13e7  ldstr    aUrlreservation// "/URLReservations"
0x13ec  call     T0x2B00000F
0x13f1  call     T0x2B000010
0x13f6  brtrue.s loc_13FE
0x13f8  call     T0x2B000011
0x13fd  ret
0x13fe  ldarg.0
0x13ff  ldarg.0
0x1400  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1405  ldstr    aUrlreservation_0// "/URLReservations/Application"
0x140a  ldstr    aApplicationUnd// "Application under URLReservations"
0x140f  call     T0x2B000012
0x1414  ldarg.0
0x1415  ldftn    instance class Microsoft.BIServer.Configuration.Application Microsoft.BIServer.Configuration.ConfigReader::<ReadApplications>b__60_0(class [System.Xml.Linq]System.Xml.Linq.XElement app)
0x141b  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, class Microsoft.BIServer.Configuration.Application>::.ctor(object, native int)
0x1420  call     T0x2B000013
0x1425  ret
```
