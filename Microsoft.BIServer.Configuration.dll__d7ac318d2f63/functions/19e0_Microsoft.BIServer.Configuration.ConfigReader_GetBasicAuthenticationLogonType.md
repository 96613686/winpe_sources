# Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationLogonType

- ea: `0x19e0`
- end: `0x1a17`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationLogonType`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x19e0`

## pseudocode

```c

```

## disassembly

```asm
0x19e0  ldc.i4.3
0x19e1  stloc.0
0x19e2  ldstr    aAuthentication_2// "/Authentication/AuthenticationTypes/RSW"...
0x19e7  stloc.1
0x19e8  ldarg.0
0x19e9  ldarg.0
0x19ea  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x19ef  ldloc.1
0x19f0  call     T0x2B00000F
0x19f5  stloc.2
0x19f6  ldloc.2
0x19f7  brfalse.s loc_1A15
0x19f9  ldloc.2
0x19fa  call     T0x2B000016
0x19ff  ldc.i4.0
0x1a00  ble.s    loc_1A15
0x1a02  ldloc.2
0x1a03  call     T0x2B000014
0x1a08  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1a0d  ldloca.s 0
0x1a0f  call     T0x2B000020
0x1a14  pop
0x1a15  ldloc.0
0x1a16  ret
```
