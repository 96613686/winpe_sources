# System.Web.XmlSiteMapProvider::HandleResourceAttribute

- ea: `0x33a00`
- end: `0x33b27`
- name: `System.Web.XmlSiteMapProvider::HandleResourceAttribute`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x33b30`

## callees

- `0x33a00`
- `0x34f20`
- `0x34fa0`

## string_xrefs

- `0x33a53`: `XmlSiteMapProvider_multiple_resource_definition`
- `0x33a7f`: `XmlSiteMapProvider_resourceKey_cannot_be_empty`
- `0x33aa3`: `XmlSiteMapProvider_invalid_resource_key`

## pseudocode

```c

```

## disassembly

```asm
0x33a00  ldarg.s  4
0x33a02  ldind.ref
0x33a03  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33a08  brfalse.s loc_33A0B
0x33a0a  ret
0x33a0b  ldnull
0x33a0c  stloc.0
0x33a0d  ldarg.s  4
0x33a0f  ldind.ref
0x33a10  ldc.i4.1
0x33a11  newarr   [mscorlib]System.Char
0x33a16  dup
0x33a17  ldc.i4.0
0x33a18  ldc.i4.s 0x20
0x33a1a  stelem.i2
0x33a1b  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0x33a20  stloc.1
0x33a21  ldloc.1
0x33a22  brfalse  loc_33B26
0x33a27  ldloc.1
0x33a28  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33a2d  ldc.i4.s 0xA
0x33a2f  ble      loc_33B26
0x33a34  ldloc.1
0x33a35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33a3a  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x33a3f  ldstr    aResources// "$resources:"
0x33a44  ldc.i4.4
0x33a45  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x33a4a  brfalse  loc_33B26
0x33a4f  ldarg.s  5
0x33a51  brtrue.s loc_33A6E
0x33a53  ldstr    aXmlsitemapprov_13// "XmlSiteMapProvider_multiple_resource_de"...
0x33a58  ldc.i4.1
0x33a59  newarr   [mscorlib]System.Object
0x33a5e  dup
0x33a5f  ldc.i4.0
0x33a60  ldarg.3
0x33a61  stelem.ref
0x33a62  call     string System.Web.SR::GetString(string name, object[] args)
0x33a67  ldarg.1
0x33a68  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x33a6d  throw
0x33a6e  ldloc.1
0x33a6f  ldc.i4.s 0xB
0x33a71  callvirt instance string [mscorlib]System.String::Substring(int32)
0x33a76  stloc.0
0x33a77  ldloc.0
0x33a78  callvirt instance int32 [mscorlib]System.String::get_Length()
0x33a7d  brtrue.s loc_33A90
0x33a7f  ldstr    aXmlsitemapprov_14// "XmlSiteMapProvider_resourceKey_cannot_b"...
0x33a84  call     string System.Web.SR::GetString(string name)
0x33a89  ldarg.1
0x33a8a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x33a8f  throw
0x33a90  ldnull
0x33a91  stloc.2
0x33a92  ldnull
0x33a93  stloc.3
0x33a94  ldloc.0
0x33a95  ldc.i4.s 0x2C
0x33a97  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x33a9c  stloc.s  4
0x33a9e  ldloc.s  4
0x33aa0  ldc.i4.m1
0x33aa1  bne.un.s loc_33ABE
0x33aa3  ldstr    aXmlsitemapprov_15// "XmlSiteMapProvider_invalid_resource_key"
0x33aa8  ldc.i4.1
0x33aa9  newarr   [mscorlib]System.Object
0x33aae  dup
0x33aaf  ldc.i4.0
0x33ab0  ldloc.0
0x33ab1  stelem.ref
0x33ab2  call     string System.Web.SR::GetString(string name, object[] args)
0x33ab7  ldarg.1
0x33ab8  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x33abd  throw
0x33abe  ldloc.0
0x33abf  ldc.i4.0
0x33ac0  ldloc.s  4
0x33ac2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x33ac7  stloc.2
0x33ac8  ldloc.0
0x33ac9  ldloc.s  4
0x33acb  ldc.i4.1
0x33acc  add
0x33acd  callvirt instance string [mscorlib]System.String::Substring(int32)
0x33ad2  stloc.3
0x33ad3  ldloc.3
0x33ad4  ldc.i4.s 0x2C
0x33ad6  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x33adb  stloc.s  5
0x33add  ldloc.s  5
0x33adf  ldc.i4.m1
0x33ae0  beq.s    loc_33AFB
0x33ae2  ldarg.s  4
0x33ae4  ldloc.3
0x33ae5  ldloc.s  5
0x33ae7  ldc.i4.1
0x33ae8  add
0x33ae9  callvirt instance string [mscorlib]System.String::Substring(int32)
0x33aee  stind.ref
0x33aef  ldloc.3
0x33af0  ldc.i4.0
0x33af1  ldloc.s  5
0x33af3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x33af8  stloc.3
0x33af9  br.s     loc_33AFF
0x33afb  ldarg.s  4
0x33afd  ldnull
0x33afe  stind.ref
0x33aff  ldarg.2
0x33b00  ldind.ref
0x33b01  brtrue.s loc_33B0A
0x33b03  ldarg.2
0x33b04  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x33b09  stind.ref
0x33b0a  ldarg.2
0x33b0b  ldind.ref
0x33b0c  ldarg.3
0x33b0d  ldloc.2
0x33b0e  callvirt instance string [mscorlib]System.String::Trim()
0x33b13  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x33b18  ldarg.2
0x33b19  ldind.ref
0x33b1a  ldarg.3
0x33b1b  ldloc.3
0x33b1c  callvirt instance string [mscorlib]System.String::Trim()
0x33b21  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x33b26  ret
```
