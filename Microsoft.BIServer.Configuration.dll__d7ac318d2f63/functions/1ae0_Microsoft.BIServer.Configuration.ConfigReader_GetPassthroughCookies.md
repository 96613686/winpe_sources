# Microsoft.BIServer.Configuration.ConfigReader::GetPassthroughCookies

- ea: `0x1ae0`
- end: `0x1b35`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetPassthroughCookies`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1ae0  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x1ae5  stloc.0
0x1ae6  ldarg.0
0x1ae7  ldarg.0
0x1ae8  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1aed  ldstr    aUiCustomauthen// "/UI/CustomAuthenticationUI/PassThroughC"...
0x1af2  call     T0x2B00000F
0x1af7  stloc.1
0x1af8  ldloc.1
0x1af9  call     T0x2B000010
0x1afe  brtrue.s loc_1B02
0x1b00  ldloc.0
0x1b01  ret
0x1b02  ldloc.1
0x1b03  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x1b08  stloc.2
0x1b09  br.s     loc_1B1F
0x1b0b  ldloc.2
0x1b0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x1b11  stloc.3
0x1b12  ldloc.0
0x1b13  ldloc.3
0x1b14  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x1b19  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x1b1e  pop
0x1b1f  ldloc.2
0x1b20  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b25  brtrue.s loc_1B0B
0x1b27  leave.s  loc_1B33
0x1b29  ldloc.2
0x1b2a  brfalse.s loc_1B32
0x1b2c  ldloc.2
0x1b2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b32  endfinally
0x1b33  ldloc.0
0x1b34  ret
```
