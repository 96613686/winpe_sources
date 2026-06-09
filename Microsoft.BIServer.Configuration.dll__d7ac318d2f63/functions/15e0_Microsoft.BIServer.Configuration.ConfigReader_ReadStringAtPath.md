# Microsoft.BIServer.Configuration.ConfigReader::ReadStringAtPath

- ea: `0x15e0`
- end: `0x160a`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadStringAtPath`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b40`
- `0x1b60`

## callees

- `0x15e0`

## pseudocode

```c

```

## disassembly

```asm
0x15e0  ldarg.2
0x15e1  stloc.0
0x15e2  ldarg.0
0x15e3  ldarg.0
0x15e4  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x15e9  ldarg.1
0x15ea  call     T0x2B00000F
0x15ef  stloc.1
0x15f0  ldloc.1
0x15f1  brfalse.s loc_1608
0x15f3  ldloc.1
0x15f4  call     T0x2B000016
0x15f9  ldc.i4.0
0x15fa  ble.s    loc_1608
0x15fc  ldloc.1
0x15fd  call     T0x2B000017
0x1602  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1607  stloc.0
0x1608  ldloc.0
0x1609  ret
```
