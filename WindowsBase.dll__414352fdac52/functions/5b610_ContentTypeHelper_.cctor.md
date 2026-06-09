# ContentTypeHelper::.cctor

- ea: `0x5b610`
- end: `0x5b682`
- name: `ContentTypeHelper::.cctor`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## string_xrefs

- `0x5b64f`: `Extension`
- `0x5b610`: `[Content_Types].xml`
- `0x5b61a`: `[CONTENT_TYPES].XML`
- `0x5b631`: `http://schemas.openxmlformats.org/package/2006/content-types`
- `0x5b677`: `/tempfiles/sample.`

## pseudocode

```c

```

## disassembly

```asm
0x5b610  ldstr    aContentTypesXm// "[Content_Types].xml"
0x5b615  stsfld   string ContentTypeHelper::_contentTypesFile
0x5b61a  ldstr    aContentTypesXm_0// "[CONTENT_TYPES].XML"
0x5b61f  stsfld   string ContentTypeHelper::_contentTypesFileUpperInvariant
0x5b624  ldc.i4.s 0x10
0x5b626  stsfld   int32 ContentTypeHelper::_defaultDictionaryInitialSize
0x5b62b  ldc.i4.8
0x5b62c  stsfld   int32 ContentTypeHelper::_overrideDictionaryInitialSize
0x5b631  ldstr    aHttpSchemasOpe_8// "http://schemas.openxmlformats.org/packa"...
0x5b636  stsfld   string ContentTypeHelper::TypesNamespaceUri
0x5b63b  ldstr    aTypes// "Types"
0x5b640  stsfld   string ContentTypeHelper::TypesTagName
0x5b645  ldstr    aDefault// "Default"
0x5b64a  stsfld   string ContentTypeHelper::DefaultTagName
0x5b64f  ldstr    aExtension// "Extension"
0x5b654  stsfld   string ContentTypeHelper::ExtensionAttributeName
0x5b659  ldstr    aContenttype_1// "ContentType"
0x5b65e  stsfld   string ContentTypeHelper::ContentTypeAttributeName
0x5b663  ldstr    aOverride// "Override"
0x5b668  stsfld   string ContentTypeHelper::OverrideTagName
0x5b66d  ldstr    aPartname_0// "PartName"
0x5b672  stsfld   string ContentTypeHelper::PartNameAttributeName
0x5b677  ldstr    aTempfilesSampl// "/tempfiles/sample."
0x5b67c  stsfld   string ContentTypeHelper::TemporaryPartNameWithoutExtension
0x5b681  ret
```
