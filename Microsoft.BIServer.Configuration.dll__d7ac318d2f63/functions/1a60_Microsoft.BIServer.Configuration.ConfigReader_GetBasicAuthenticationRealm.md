# Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationRealm

- ea: `0x1a60`
- end: `0x1a99`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationRealm`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1a60`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldsfld   string [mscorlib]System.String::Empty
0x1a65  stloc.0
0x1a66  ldstr    aAuthentication_4// "/Authentication/AuthenticationTypes/RSW"...
0x1a6b  stloc.1
0x1a6c  ldarg.0
0x1a6d  ldarg.0
0x1a6e  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1a73  ldloc.1
0x1a74  call     T0x2B00000F
0x1a79  stloc.2
0x1a7a  ldloc.2
0x1a7b  brfalse.s loc_1A97
0x1a7d  ldloc.2
0x1a7e  call     T0x2B000016
0x1a83  ldc.i4.0
0x1a84  ble.s    loc_1A97
0x1a86  ldloc.2
0x1a87  call     T0x2B000014
0x1a8c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1a91  callvirt instance string [mscorlib]System.Object::ToString()
0x1a96  stloc.0
0x1a97  ldloc.0
0x1a98  ret
```
