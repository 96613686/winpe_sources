# System.Windows.Markup.FilteredXmlReader::CheckForNamespaceRedef

- ea: `0x9bbd0`
- end: `0x9bc18`
- name: `System.Windows.Markup.FilteredXmlReader::CheckForNamespaceRedef`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9bb50`

## callees

- `0x38c40`
- `0x9bbd0`

## string_xrefs

- `0x9bbfb`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x9bbd6`: `xmlns`
- `0x9bc07`: `ParserFilterXmlReaderNoDefinitionPrefixChangeAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x9bbd0  ldarg.0
0x9bbd1  call     instance string [System.Xml]System.Xml.XmlTextReader::get_Prefix()
0x9bbd6  ldstr    aXmlns// "xmlns"
0x9bbdb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bbe0  brfalse.s loc_9BC17
0x9bbe2  ldarg.0
0x9bbe3  call     instance string [System.Xml]System.Xml.XmlTextReader::get_LocalName()
0x9bbe8  ldarg.0
0x9bbe9  ldfld    string System.Windows.Markup.FilteredXmlReader::uidPrefix
0x9bbee  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x9bbf3  brfalse.s loc_9BC17
0x9bbf5  ldarg.0
0x9bbf6  call     instance string [System.Xml]System.Xml.XmlTextReader::get_Value()
0x9bbfb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x9bc00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bc05  brfalse.s loc_9BC17
0x9bc07  ldstr    aParserfilterxm_0// "ParserFilterXmlReaderNoDefinitionPrefix"...
0x9bc0c  call     string System.Windows.SR::Get(string id)
0x9bc11  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9bc16  throw
0x9bc17  ret
```
