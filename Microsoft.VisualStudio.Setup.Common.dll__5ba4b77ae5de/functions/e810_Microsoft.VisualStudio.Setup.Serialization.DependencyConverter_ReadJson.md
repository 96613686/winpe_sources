# Microsoft.VisualStudio.Setup.Serialization.DependencyConverter::ReadJson

- ea: `0xe810`
- end: `0xe8c6`
- name: `Microsoft.VisualStudio.Setup.Serialization.DependencyConverter::ReadJson`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4140`
- `0x4190`
- `0x41a0`
- `0x41b0`
- `0x41c0`
- `0x41d0`
- `0x41e0`
- `0x41f0`
- `0x4200`
- `0x4210`
- `0xc1a0`
- `0xe810`
- `0x10900`

## string_xrefs

- `0xe811`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xe810  ldarg.1
0xe811  ldstr    aReader// "reader"
0xe816  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe81b  ldarg.s  4
0xe81d  ldstr    aSerializer// "serializer"
0xe822  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe827  ldarg.1
0xe828  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe82d  ldc.i4.s 0xB
0xe82f  bne.un.s loc_E833
0xe831  ldnull
0xe832  ret
0xe833  ldarg.1
0xe834  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe839  ldc.i4.s 9
0xe83b  bne.un.s loc_E862
0xe83d  ldarg.s  4
0xe83f  ldarg.1
0xe840  callvirt T0x2B000057
0xe845  dup
0xe846  brtrue.s loc_E854
0xe848  pop
0xe849  ldstr    aExpectedNonNul_17// "Expected non-null 'Version' when deseri"...
0xe84e  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xe853  throw
0xe854  stloc.0
0xe855  newobj   instance void Microsoft.VisualStudio.Setup.Dependency::.ctor()
0xe85a  dup
0xe85b  ldloc.0
0xe85c  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Version(class Microsoft.VisualStudio.Setup.VersionRange value)
0xe861  ret
0xe862  ldarg.1
0xe863  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe868  ldc.i4.1
0xe869  bne.un.s loc_E8C0
0xe86b  newobj   instance void Microsoft.VisualStudio.Setup.Dependency::.ctor()
0xe870  stloc.1
0xe871  ldarg.s  4
0xe873  ldarg.1
0xe874  ldloc.1
0xe875  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Populate(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader, object)
0xe87a  ldloc.1
0xe87b  ldloc.1
0xe87c  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Chip()
0xe881  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xe886  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Chip(string value)
0xe88b  ldloc.1
0xe88c  ldloc.1
0xe88d  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Language()
0xe892  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xe897  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Language(string value)
0xe89c  ldloc.1
0xe89d  ldloc.1
0xe89e  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Branch()
0xe8a3  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xe8a8  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Branch(string value)
0xe8ad  ldloc.1
0xe8ae  ldloc.1
0xe8af  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_MachineArch()
0xe8b4  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0xe8b9  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_MachineArch(string value)
0xe8be  ldloc.1
0xe8bf  ret
0xe8c0  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xe8c5  throw
```
