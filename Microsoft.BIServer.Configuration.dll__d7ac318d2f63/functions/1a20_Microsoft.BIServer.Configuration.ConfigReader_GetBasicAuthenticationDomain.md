# Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationDomain

- ea: `0x1a20`
- end: `0x1a59`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationDomain`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldsfld   string [mscorlib]System.String::Empty
0x1a25  stloc.0
0x1a26  ldstr    aAuthentication_3// "/Authentication/AuthenticationTypes/RSW"...
0x1a2b  stloc.1
0x1a2c  ldarg.0
0x1a2d  ldarg.0
0x1a2e  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1a33  ldloc.1
0x1a34  call     T0x2B00000F
0x1a39  stloc.2
0x1a3a  ldloc.2
0x1a3b  brfalse.s loc_1A57
0x1a3d  ldloc.2
0x1a3e  call     T0x2B000016
0x1a43  ldc.i4.0
0x1a44  ble.s    loc_1A57
0x1a46  ldloc.2
0x1a47  call     T0x2B000014
0x1a4c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1a51  callvirt instance string [mscorlib]System.Object::ToString()
0x1a56  stloc.0
0x1a57  ldloc.0
0x1a58  ret
```
