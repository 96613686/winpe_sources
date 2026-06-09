# Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationTypes

- ea: `0x1980`
- end: `0x19dd`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationTypes`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1360`
- `0x1c00`

## callees

- `0x1980`

## string_xrefs

- `0x19bc`: `Extension not supported.`

## pseudocode

```c

```

## disassembly

```asm
0x1980  ldc.i4.0
0x1981  stloc.0
0x1982  ldarg.0
0x1983  ldarg.0
0x1984  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1989  ldstr    aAuthentication_1// "/Authentication/AuthenticationTypes/*"
0x198e  call     T0x2B00000F
0x1993  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x1998  stloc.1
0x1999  br.s     loc_19C7
0x199b  ldloc.1
0x199c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x19a1  ldc.i4.0
0x19a2  stloc.2
0x19a3  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x19a8  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x19ad  ldloca.s 2
0x19af  call     T0x2B00001F
0x19b4  brfalse.s loc_19BC
0x19b6  ldloc.0
0x19b7  ldloc.2
0x19b8  or
0x19b9  stloc.0
0x19ba  br.s     loc_19C7
0x19bc  ldstr    aExtensionNotSu// "Extension not supported."
0x19c1  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x19c6  throw
0x19c7  ldloc.1
0x19c8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19cd  brtrue.s loc_199B
0x19cf  leave.s  loc_19DB
0x19d1  ldloc.1
0x19d2  brfalse.s loc_19DA
0x19d4  ldloc.1
0x19d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19da  endfinally
0x19db  ldloc.0
0x19dc  ret
```
