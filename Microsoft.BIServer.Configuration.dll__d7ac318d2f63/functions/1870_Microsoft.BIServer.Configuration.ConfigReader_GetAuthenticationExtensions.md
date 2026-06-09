# Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationExtensions

- ea: `0x1870`
- end: `0x197e`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationExtensions`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1870`
- `0x24a0`
- `0x24c0`
- `0x24e0`
- `0x2500`
- `0x2520`
- `0x25f0`
- `0x70e0`

## string_xrefs

- `0x187d`: `/Extensions/Authentication/Extension`
- `0x1901`: `Configuration`

## pseudocode

```c

```

## disassembly

```asm
0x1870  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Extension>::.ctor()
0x1875  stloc.0
0x1876  ldarg.0
0x1877  ldarg.0
0x1878  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x187d  ldstr    aExtensionsAuth// "/Extensions/Authentication/Extension"
0x1882  call     T0x2B00000F
0x1887  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x188c  stloc.1
0x188d  br       loc_1965
0x1892  ldloc.1
0x1893  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x1898  stloc.2
0x1899  newobj   instance void Microsoft.BIServer.Configuration.Extension::.ctor()
0x189e  stloc.3
0x189f  ldloc.2
0x18a0  ldstr    aType// "Type"
0x18a5  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x18aa  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x18af  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x18b4  ldc.i4.1
0x18b5  newarr   [mscorlib]System.Char
0x18ba  dup
0x18bb  ldc.i4.0
0x18bc  ldc.i4.s 0x2C
0x18be  stelem.i2
0x18bf  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x18c4  stloc.s  4
0x18c6  ldloc.3
0x18c7  ldloc.2
0x18c8  ldstr    aName// "Name"
0x18cd  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x18d2  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x18d7  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x18dc  callvirt instance void Microsoft.BIServer.Configuration.Extension::set_Name(string value)
0x18e1  ldloc.3
0x18e2  ldloc.s  4
0x18e4  ldc.i4.0
0x18e5  ldelem.ref
0x18e6  callvirt instance void Microsoft.BIServer.Configuration.Extension::set_Class(string value)
0x18eb  ldloc.3
0x18ec  ldloc.s  4
0x18ee  ldc.i4.1
0x18ef  ldelem.ref
0x18f0  callvirt instance void Microsoft.BIServer.Configuration.Extension::set_Assembly(string value)
0x18f5  ldloc.3
0x18f6  ldstr    aAuthentication_0// "Authentication"
0x18fb  callvirt instance void Microsoft.BIServer.Configuration.Extension::set_Type(string value)
0x1900  ldloc.2
0x1901  ldstr    aConfiguration// "Configuration"
0x1906  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x190b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x1910  stloc.s  5
0x1912  ldloc.s  5
0x1914  call     T0x2B000010
0x1919  brfalse.s loc_195E
0x191b  newobj   instance void <>c__DisplayClass79_0::.ctor()
0x1920  stloc.s  6
0x1922  ldloc.s  6
0x1924  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1929  stfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass79_0::innerXml
0x192e  ldloc.s  5
0x1930  call     T0x2B00001D
0x1935  call     T0x2B00001E
0x193a  ldloc.s  6
0x193c  ldftn    instance void <>c__DisplayClass79_0::<GetAuthenticationExtensions>b__0(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x1942  newobj   instance void class [mscorlib]System.Action`1<class [System.Xml.Linq]System.Xml.Linq.XNode>::.ctor(object, native int)
0x1947  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml.Linq]System.Xml.Linq.XNode>::ForEach(class [mscorlib]System.Action`1<var<u1>>)
0x194c  ldloc.3
0x194d  ldloc.s  6
0x194f  ldfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass79_0::innerXml
0x1954  callvirt instance string [mscorlib]System.Object::ToString()
0x1959  callvirt instance void Microsoft.BIServer.Configuration.Extension::set_Configuration(string value)
0x195e  ldloc.0
0x195f  ldloc.3
0x1960  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Extension>::Add(var<u1>)
0x1965  ldloc.1
0x1966  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x196b  brtrue   loc_1892
0x1970  leave.s  loc_197C
0x1972  ldloc.1
0x1973  brfalse.s loc_197B
0x1975  ldloc.1
0x1976  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x197b  endfinally
0x197c  ldloc.0
0x197d  ret
```
