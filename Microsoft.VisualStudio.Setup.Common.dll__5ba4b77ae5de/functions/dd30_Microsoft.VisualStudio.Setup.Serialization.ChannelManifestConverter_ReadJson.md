# Microsoft.VisualStudio.Setup.Serialization.ChannelManifestConverter::ReadJson

- ea: `0xdd30`
- end: `0xdf81`
- name: `Microsoft.VisualStudio.Setup.Serialization.ChannelManifestConverter::ReadJson`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xdbb0`
- `0xdd30`
- `0xdfa0`
- `0x182a0`
- `0x182c0`
- `0x182e0`
- `0x182f0`
- `0x18360`

## string_xrefs

- `0xdd3d`: `ManifestVersion`
- `0xddcc`: `Expected non-null 'ChannelItems' when deserializing ChannelManifest.`
- `0xde03`: `Expected non-null 'EngineVersion' when deserializing ChannelManifest.`
- `0xde18`: `UpdateUri`
- `0xde3a`: `Expected non-null 'UpdateUri' when deserializing ChannelManifest.`
- `0xde4f`: `InstallCatalogUri`
- `0xde71`: `Expected non-null 'InstallCatalogUri' when deserializing ChannelManifest.`
- `0xde86`: `CanUpdate`
- `0xded0`: `Expected non-null 'Info' when deserializing ChannelManifest.`
- `0xdf07`: `Expected non-null '_buildInfo' when deserializing ChannelManifest.`
- `0xdf3b`: `Expected non-null 'Signature' when deserializing ChannelManifest.`
- `0xdf5b`: `ChannelManifest must not contain a Pacakges property.`

## pseudocode

```c

```

## disassembly

```asm
0xdd30  ldarg.1
0xdd31  ldloca.s 0
0xdd33  call     bool Microsoft.VisualStudio.Setup.Serialization.ChannelManifestConverter::TryReadPropertyName(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader reader, [out] string& propertyName)
0xdd38  brfalse  loc_DF7B
0xdd3d  ldstr    aManifestversio// "ManifestVersion"
0xdd42  ldloc.0
0xdd43  ldc.i4.5
0xdd44  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdd49  brfalse  loc_DF7B
0xdd4e  ldarg.1
0xdd4f  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.JsonReader::ReadAsString()
0xdd54  ldloca.s 1
0xdd56  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xdd5b  brfalse  loc_DF7B
0xdd60  ldloc.1
0xdd61  ldnull
0xdd62  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xdd67  brfalse  loc_DF7B
0xdd6c  ldloc.1
0xdd6d  ldsfld   class [mscorlib]System.Version Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::CurrentVersion
0xdd72  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xdd77  brfalse  loc_DF7B
0xdd7c  ldarg.s  4
0xdd7e  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonConverterCollection [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_Converters()
0xdd83  ldarg.0
0xdd84  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Serialization.ChannelManifestConverter::services
0xdd89  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.ChannelItemConverter::.ctor(class [mscorlib]System.IServiceProvider services)
0xdd8e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Newtonsoft.Json]Newtonsoft.Json.JsonConverter>::Add(var<u1>)
0xdd93  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::.ctor()
0xdd98  dup
0xdd99  ldloc.1
0xdd9a  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem>::set_ManifestVersion(class [mscorlib]System.Version)
0xdd9f  stloc.2
0xdda0  br       loc_DF6C
0xdda5  ldstr    aChannelitems// "ChannelItems"
0xddaa  ldloc.0
0xddab  ldc.i4.5
0xddac  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xddb1  brfalse.s loc_DDE1
0xddb3  ldarg.1
0xddb4  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xddb9  pop
0xddba  ldloc.2
0xddbb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem> Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::get_ChannelItems()
0xddc0  ldarg.s  4
0xddc2  ldarg.1
0xddc3  callvirt T0x2B000065
0xddc8  dup
0xddc9  brtrue.s loc_DDD7
0xddcb  pop
0xddcc  ldstr    aExpectedNonNul_9// "Expected non-null 'ChannelItems' when d"...
0xddd1  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xddd6  throw
0xddd7  call     T0x2B000066
0xdddc  br       loc_DF6C
0xdde1  ldstr    aEngineversion// "EngineVersion"
0xdde6  ldloc.0
0xdde7  ldc.i4.5
0xdde8  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdded  brfalse.s loc_DE18
0xddef  ldarg.1
0xddf0  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xddf5  pop
0xddf6  ldloc.2
0xddf7  ldarg.s  4
0xddf9  ldarg.1
0xddfa  callvirt T0x2B00005C
0xddff  dup
0xde00  brtrue.s loc_DE0E
0xde02  pop
0xde03  ldstr    aExpectedNonNul_10// "Expected non-null 'EngineVersion' when "...
0xde08  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xde0d  throw
0xde0e  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem>::set_EngineVersion(class [mscorlib]System.Version)
0xde13  br       loc_DF6C
0xde18  ldstr    aUpdateuri// "UpdateUri"
0xde1d  ldloc.0
0xde1e  ldc.i4.5
0xde1f  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde24  brfalse.s loc_DE4F
0xde26  ldarg.1
0xde27  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xde2c  pop
0xde2d  ldloc.2
0xde2e  ldarg.s  4
0xde30  ldarg.1
0xde31  callvirt T0x2B000067
0xde36  dup
0xde37  brtrue.s loc_DE45
0xde39  pop
0xde3a  ldstr    aExpectedNonNul_11// "Expected non-null 'UpdateUri' when dese"...
0xde3f  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xde44  throw
0xde45  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::set_UpdateUri(class [System]System.Uri value)
0xde4a  br       loc_DF6C
0xde4f  ldstr    aInstallcatalog// "InstallCatalogUri"
0xde54  ldloc.0
0xde55  ldc.i4.5
0xde56  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde5b  brfalse.s loc_DE86
0xde5d  ldarg.1
0xde5e  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xde63  pop
0xde64  ldloc.2
0xde65  ldarg.s  4
0xde67  ldarg.1
0xde68  callvirt T0x2B000067
0xde6d  dup
0xde6e  brtrue.s loc_DE7C
0xde70  pop
0xde71  ldstr    aExpectedNonNul_12// "Expected non-null 'InstallCatalogUri' w"...
0xde76  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xde7b  throw
0xde7c  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::set_InstallCatalogUri(class [System]System.Uri value)
0xde81  br       loc_DF6C
0xde86  ldstr    aCanupdate// "CanUpdate"
0xde8b  ldloc.0
0xde8c  ldc.i4.5
0xde8d  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde92  brfalse.s loc_DEAE
0xde94  ldarg.1
0xde95  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xde9a  pop
0xde9b  ldloc.2
0xde9c  ldarg.s  4
0xde9e  ldarg.1
0xde9f  callvirt T0x2B000068
0xdea4  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::set_CanUpdate(bool value)
0xdea9  br       loc_DF6C
0xdeae  ldstr    aInfo_0// "Info"
0xdeb3  ldloc.0
0xdeb4  ldc.i4.5
0xdeb5  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdeba  brfalse.s loc_DEE5
0xdebc  ldarg.1
0xdebd  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xdec2  pop
0xdec3  ldloc.2
0xdec4  ldarg.s  4
0xdec6  ldarg.1
0xdec7  callvirt T0x2B00005D
0xdecc  dup
0xdecd  brtrue.s loc_DEDB
0xdecf  pop
0xded0  ldstr    aExpectedNonNul_13// "Expected non-null 'Info' when deseriali"...
0xded5  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xdeda  throw
0xdedb  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem>::set_Info(class Microsoft.VisualStudio.Setup.CatalogInfo)
0xdee0  br       loc_DF6C
0xdee5  ldstr    aBuildinfo// "_buildInfo"
0xdeea  ldloc.0
0xdeeb  ldc.i4.5
0xdeec  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdef1  brfalse.s loc_DF19
0xdef3  ldarg.1
0xdef4  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xdef9  pop
0xdefa  ldloc.2
0xdefb  ldarg.s  4
0xdefd  ldarg.1
0xdefe  callvirt T0x2B00005E
0xdf03  dup
0xdf04  brtrue.s loc_DF12
0xdf06  pop
0xdf07  ldstr    aExpectedNonNul_14// "Expected non-null '_buildInfo' when des"...
0xdf0c  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xdf11  throw
0xdf12  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem>::set_BuildInformation(class Microsoft.VisualStudio.Setup.CatalogBuildInformation)
0xdf17  br.s     loc_DF6C
0xdf19  ldstr    aSignature// "Signature"
0xdf1e  ldloc.0
0xdf1f  ldc.i4.5
0xdf20  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdf25  brfalse.s loc_DF4D
0xdf27  ldarg.1
0xdf28  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xdf2d  pop
0xdf2e  ldloc.2
0xdf2f  ldarg.s  4
0xdf31  ldarg.1
0xdf32  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::Deserialize(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader)
0xdf37  dup
0xdf38  brtrue.s loc_DF46
0xdf3a  pop
0xdf3b  ldstr    aExpectedNonNul_15// "Expected non-null 'Signature' when dese"...
0xdf40  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xdf45  throw
0xdf46  callvirt instance void class Microsoft.VisualStudio.Setup.Manifest`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem>::set_Signature(object)
0xdf4b  br.s     loc_DF6C
0xdf4d  ldstr    aPackages// "Packages"
0xdf52  ldloc.0
0xdf53  ldc.i4.5
0xdf54  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdf59  brfalse.s loc_DF66
0xdf5b  ldstr    aChannelmanifes// "ChannelManifest must not contain a Paca"...
0xdf60  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xdf65  throw
0xdf66  ldarg.1
0xdf67  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Skip()
0xdf6c  ldarg.1
0xdf6d  ldloca.s 0
0xdf6f  call     bool Microsoft.VisualStudio.Setup.Serialization.ChannelManifestConverter::TryReadPropertyName(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader reader, [out] string& propertyName)
0xdf74  brtrue   loc_DDA5
0xdf79  ldloc.2
0xdf7a  ret
0xdf7b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xdf80  throw
```
