# Microsoft.BIServer.Configuration.ConfigReader::GetMachineKeys

- ea: `0x1500`
- end: `0x15a1`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetMachineKeys`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0xbe0`
- `0xc00`
- `0xc20`
- `0xc40`
- `0xc50`
- `0x1500`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldnull
0x1501  stloc.0
0x1502  ldarg.0
0x1503  ldarg.0
0x1504  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1509  ldstr    aMachinekey// "/MachineKey"
0x150e  call     T0x2B00000F
0x1513  call     T0x2B000014
0x1518  stloc.1
0x1519  ldloc.1
0x151a  brfalse  loc_159F
0x151f  newobj   instance void Microsoft.BIServer.Configuration.MachineKeySettings::.ctor()
0x1524  stloc.0
0x1525  ldloc.0
0x1526  ldloc.1
0x1527  ldstr    aValidation// "Validation"
0x152c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1531  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1536  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x153b  callvirt instance void Microsoft.BIServer.Configuration.MachineKeySettings::set_Validation(string value)
0x1540  ldloc.0
0x1541  ldloc.1
0x1542  ldstr    aValidationkey// "ValidationKey"
0x1547  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x154c  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1551  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x1556  callvirt instance void Microsoft.BIServer.Configuration.MachineKeySettings::set_ValidationKey(string value)
0x155b  ldloc.0
0x155c  ldloc.1
0x155d  ldstr    aDecryption// "Decryption"
0x1562  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1567  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x156c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x1571  callvirt instance void Microsoft.BIServer.Configuration.MachineKeySettings::set_Decryption(string value)
0x1576  ldloc.0
0x1577  ldloc.1
0x1578  ldstr    aDecryptionkey// "DecryptionKey"
0x157d  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x1582  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1587  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x158c  callvirt instance void Microsoft.BIServer.Configuration.MachineKeySettings::set_DecryptionKey(string value)
0x1591  leave.s  loc_159F
0x1593  pop
0x1594  ldstr    aUnableToParseM// "Unable to parse MachineKey."
0x1599  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x159e  throw
0x159f  ldloc.0
0x15a0  ret
```
