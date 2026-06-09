# ComponentProperties::WriteXml

- ea: `0x1d50`
- end: `0x1daa`
- name: `ComponentProperties::WriteXml`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1d50`

## pseudocode

```c

```

## disassembly

```asm
0x1d50  ldarg.0
0x1d51  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x1d56  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x1d5b  stloc.0
0x1d5c  br.s     loc_1D90
0x1d5e  ldloca.s 0
0x1d60  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x1d65  stloc.1
0x1d66  ldarg.1
0x1d67  ldstr    aProperty// "Property"
0x1d6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1d71  ldarg.1
0x1d72  ldstr    aName_0// "Name"
0x1d77  ldloc.1
0x1d78  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1d7d  ldarg.1
0x1d7e  ldarg.0
0x1d7f  ldloc.1
0x1d80  call     instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1d85  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x1d8a  ldarg.1
0x1d8b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1d90  ldloca.s 0
0x1d92  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x1d97  brtrue.s loc_1D5E
0x1d99  leave.s  loc_1DA9
0x1d9b  ldloca.s 0
0x1d9d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x1da3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da8  endfinally
0x1da9  ret
```
