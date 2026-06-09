# Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::ExtractFromManifest

- ea: `0xe000`
- end: `0xe112`
- name: `Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::ExtractFromManifest`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe000`
- `0x10210`
- `0x11900`
- `0x11970`
- `0x183a0`
- `0x183c0`
- `0x183d0`

## string_xrefs

- `0xe0d4`: `The UpdateUri value is invalid.`

## pseudocode

```c

```

## disassembly

```asm
0xe000  ldarg.0
0xe001  ldfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::fileSystem
0xe006  ldarg.1
0xe007  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0xe00c  brtrue.s loc_E025
0xe00e  ldstr    aFile// "File "
0xe013  ldarg.1
0xe014  ldstr    aDoesNotExist// " does not exist."
0xe019  call     string [mscorlib]System.String::Concat(string, string, string)
0xe01e  ldarg.1
0xe01f  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0xe024  throw
0xe025  ldnull
0xe026  stloc.0
0xe027  ldnull
0xe028  stloc.1
0xe029  ldc.i4.0
0xe02a  stloc.2
0xe02b  ldc.i4.0
0xe02c  stloc.3
0xe02d  ldarg.0
0xe02e  ldfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::fileSystem
0xe033  ldarg.1
0xe034  callvirt instance class [mscorlib]System.IO.TextReader Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string path)
0xe039  stloc.s  4
0xe03b  ldloc.s  4
0xe03d  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.OptimizedJsonTextReader::.ctor(class [mscorlib]System.IO.TextReader reader)
0xe042  stloc.s  5
0xe044  br.s     loc_E0B2
0xe046  ldloc.s  5
0xe048  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe04d  ldc.i4.4
0xe04e  bne.un.s loc_E0B2
0xe050  ldloc.s  5
0xe052  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xe057  isinst   [mscorlib]System.String
0xe05c  stloc.s  7
0xe05e  ldsfld   string Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::UpdateUriKey
0xe063  ldloc.s  7
0xe065  ldc.i4.5
0xe066  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xe06b  brfalse.s loc_E086
0xe06d  ldloc.s  5
0xe06f  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xe074  pop
0xe075  ldloc.s  5
0xe077  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xe07c  isinst   [mscorlib]System.String
0xe081  stloc.0
0xe082  ldc.i4.1
0xe083  stloc.3
0xe084  br.s     loc_E0AD
0xe086  ldsfld   string Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::CatalogInfoKey
0xe08b  ldloc.s  7
0xe08d  ldc.i4.5
0xe08e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xe093  brfalse.s loc_E0AD
0xe095  ldloc.s  5
0xe097  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xe09c  pop
0xe09d  ldarg.0
0xe09e  ldfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.CatalogInfo> Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::serializer
0xe0a3  ldloc.s  5
0xe0a5  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.CatalogInfo>::Deserialize(!!T0)
0xe0aa  stloc.1
0xe0ab  ldc.i4.1
0xe0ac  stloc.2
0xe0ad  ldloc.2
0xe0ae  ldloc.3
0xe0af  and
0xe0b0  brtrue.s loc_E0BB
0xe0b2  ldloc.s  5
0xe0b4  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xe0b9  brtrue.s loc_E046
0xe0bb  ldloc.1
0xe0bc  brtrue.s loc_E0C9
0xe0be  ldstr    aTheCataloginfo// "The CatalogInfo value is null."
0xe0c3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe0c8  throw
0xe0c9  ldloc.0
0xe0ca  ldc.i4.1
0xe0cb  ldloca.s 6
0xe0cd  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xe0d2  brtrue.s loc_E0DF
0xe0d4  ldstr    aTheUpdateuriVa// "The UpdateUri value is invalid."
0xe0d9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe0de  throw
0xe0df  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestInfo::.ctor()
0xe0e4  dup
0xe0e5  ldloc.1
0xe0e6  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestInfo::set_CatalogInfo(class Microsoft.VisualStudio.Setup.CatalogInfo value)
0xe0eb  dup
0xe0ec  ldloc.s  6
0xe0ee  callvirt instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestInfo::set_UpdateUri(class [System]System.Uri value)
0xe0f3  stloc.s  8
0xe0f5  leave.s  loc_E10F
0xe0f7  ldloc.s  5
0xe0f9  brfalse.s loc_E102
0xe0fb  ldloc.s  5
0xe0fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe102  endfinally
0xe103  ldloc.s  4
0xe105  brfalse.s loc_E10E
0xe107  ldloc.s  4
0xe109  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe10e  endfinally
0xe10f  ldloc.s  8
0xe111  ret
```
