# Microsoft.BIServer.Configuration.ConfigReader::GetAuthPersistence

- ea: `0x1aa0`
- end: `0x1adc`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetAuthPersistence`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1aa0`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  ldc.i4.0
0x1aa1  stloc.0
0x1aa2  ldstr    aAuthentication_5// "/Authentication/EnableAuthPersistence"
0x1aa7  stloc.1
0x1aa8  ldarg.0
0x1aa9  ldarg.0
0x1aaa  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1aaf  ldloc.1
0x1ab0  call     T0x2B00000F
0x1ab5  stloc.2
0x1ab6  ldloc.2
0x1ab7  brfalse.s loc_1ADA
0x1ab9  ldloc.2
0x1aba  call     T0x2B000016
0x1abf  ldc.i4.0
0x1ac0  ble.s    loc_1ADA
0x1ac2  ldloc.2
0x1ac3  call     T0x2B000014
0x1ac8  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1acd  callvirt instance string [mscorlib]System.Object::ToString()
0x1ad2  ldloca.s 0
0x1ad4  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x1ad9  pop
0x1ada  ldloc.0
0x1adb  ret
```
