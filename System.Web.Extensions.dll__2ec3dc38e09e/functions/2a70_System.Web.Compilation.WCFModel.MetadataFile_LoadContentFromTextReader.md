# System.Web.Compilation.WCFModel.MetadataFile::LoadContentFromTextReader

- ea: `0x2a70`
- end: `0x2ad2`
- name: `System.Web.Compilation.WCFModel.MetadataFile::LoadContentFromTextReader`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2a10`
- `0x2a30`

## callees

- `0x1d30`
- `0x2890`
- `0x2a70`
- `0x2b50`
- `0x39820`

## string_xrefs

- `0x2a73`: `contentReader`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  ldarg.1
0x2a71  brtrue.s loc_2A7E
0x2a73  ldstr    aContentreader// "contentReader"
0x2a78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2a7d  throw
0x2a7e  ldarg.0
0x2a7f  ldnull
0x2a80  call     instance void System.Web.Compilation.WCFModel.ExternalFile::set_ErrorInLoading(class [mscorlib]System.Exception value)
0x2a85  ldarg.0
0x2a86  ldnull
0x2a87  stfld    class MetadataContent System.Web.Compilation.WCFModel.MetadataFile::m_CachedMetadata
0x2a8c  ldarg.1
0x2a8d  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x2a92  stloc.0
0x2a93  ldarg.0
0x2a94  ldfld    valuetype MetadataType System.Web.Compilation.WCFModel.MetadataFile::m_MetadataType
0x2a99  brtrue.s loc_2AC5
0x2a9b  ldarg.0
0x2a9c  ldloc.0
0x2a9d  call     instance valuetype MetadataType System.Web.Compilation.WCFModel.MetadataFile::DetermineFileType(class [System.Xml]System.Xml.XmlReader reader)
0x2aa2  stloc.1
0x2aa3  ldarg.0
0x2aa4  ldarg.0
0x2aa5  ldloc.1
0x2aa6  ldloc.0
0x2aa7  call     instance class MetadataContent System.Web.Compilation.WCFModel.MetadataFile::LoadMetadataContent(valuetype MetadataType fileType, class [System.Xml]System.Xml.XmlTextReader xmlReader)
0x2aac  stfld    class MetadataContent System.Web.Compilation.WCFModel.MetadataFile::m_CachedMetadata
0x2ab1  ldarg.0
0x2ab2  ldfld    class MetadataContent System.Web.Compilation.WCFModel.MetadataFile::m_CachedMetadata
0x2ab7  callvirt instance class [mscorlib]System.Exception MetadataContent::get_MetadataFormatError()
0x2abc  brtrue.s loc_2AC5
0x2abe  ldarg.0
0x2abf  ldloc.1
0x2ac0  stfld    valuetype MetadataType System.Web.Compilation.WCFModel.MetadataFile::m_MetadataType
0x2ac5  leave.s  loc_2AD1
0x2ac7  ldloc.0
0x2ac8  brfalse.s loc_2AD0
0x2aca  ldloc.0
0x2acb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ad0  endfinally
0x2ad1  ret
```
