# Microsoft.VisualStudio.Setup.Serialization.AppliesToConverter::WriteJson

- ea: `0xd600`
- end: `0xd6cc`
- name: `Microsoft.VisualStudio.Setup.Serialization.AppliesToConverter::WriteJson`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x21d0`
- `0x21f0`
- `0x2290`
- `0xc1a0`
- `0xd600`

## string_xrefs

- `0xd601`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xd600  ldarg.1
0xd601  ldstr    aWriter// "writer"
0xd606  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xd60b  ldarg.3
0xd60c  ldstr    aSerializer// "serializer"
0xd611  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xd616  ldarg.2
0xd617  isinst   Microsoft.VisualStudio.Setup.AppliesTo
0xd61c  stloc.0
0xd61d  ldloc.0
0xd61e  brtrue.s loc_D627
0xd620  ldarg.1
0xd621  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteNull()
0xd626  ret
0xd627  ldloc.0
0xd628  callvirt instance bool Microsoft.VisualStudio.Setup.AppliesTo::get_IsSimple()
0xd62d  brfalse.s loc_D646
0xd62f  ldarg.3
0xd630  ldarg.1
0xd631  ldloc.0
0xd632  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.AppliesTo::get_Version()
0xd637  dup
0xd638  brtrue.s loc_D640
0xd63a  pop
0xd63b  ldsfld   object Microsoft.VisualStudio.Setup.Serialization.AppliesToConverter::EmptyObject
0xd640  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xd645  ret
0xd646  ldarg.3
0xd647  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Serialization.IContractResolver [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_ContractResolver()
0xd64c  isinst   [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver
0xd651  stloc.1
0xd652  ldarg.1
0xd653  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0xd658  ldloc.0
0xd659  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.AppliesTo::get_Version()
0xd65e  brfalse.s loc_D68D
0xd660  ldarg.1
0xd661  ldloc.1
0xd662  brtrue.s loc_D667
0xd664  ldnull
0xd665  br.s     loc_D672
0xd667  ldloc.1
0xd668  ldstr    aVersion_1// "Version"
0xd66d  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xd672  dup
0xd673  brtrue.s loc_D67B
0xd675  pop
0xd676  ldstr    aVersion_1// "Version"
0xd67b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xd680  ldarg.3
0xd681  ldarg.1
0xd682  ldloc.0
0xd683  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.AppliesTo::get_Version()
0xd688  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xd68d  ldloc.0
0xd68e  callvirt instance string Microsoft.VisualStudio.Setup.AppliesTo::get_Branch()
0xd693  brfalse.s loc_D6C2
0xd695  ldarg.1
0xd696  ldloc.1
0xd697  brtrue.s loc_D69C
0xd699  ldnull
0xd69a  br.s     loc_D6A7
0xd69c  ldloc.1
0xd69d  ldstr    aBranch_1// "Branch"
0xd6a2  call     instance string [Newtonsoft.Json]Newtonsoft.Json.Serialization.DefaultContractResolver::GetResolvedPropertyName(string)
0xd6a7  dup
0xd6a8  brtrue.s loc_D6B0
0xd6aa  pop
0xd6ab  ldstr    aBranch_1// "Branch"
0xd6b0  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0xd6b5  ldarg.3
0xd6b6  ldarg.1
0xd6b7  ldloc.0
0xd6b8  callvirt instance string Microsoft.VisualStudio.Setup.AppliesTo::get_Branch()
0xd6bd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Serialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter, object)
0xd6c2  leave.s  loc_D6CB
0xd6c4  ldarg.1
0xd6c5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0xd6ca  endfinally
0xd6cb  ret
```
