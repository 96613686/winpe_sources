# System.Web.Configuration.CompilationSection::GetTempDirectoryErrorInfo

- ea: `0x13ef70`
- end: `0x13efb0`
- name: `System.Web.Configuration.CompilationSection::GetTempDirectoryErrorInfo`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x225b0`
- `0x15ffc0`

## string_xrefs

- `0x13ef71`: `tempDirectory`
- `0x13ef83`: `tempDirectory`
- `0x13ef9f`: `tempDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x13ef70  ldarg.1
0x13ef71  ldstr    aTempdirectory// "tempDirectory"
0x13ef76  stind.ref
0x13ef77  ldarg.2
0x13ef78  ldarg.0
0x13ef79  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13ef7e  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13ef83  ldstr    aTempdirectory// "tempDirectory"
0x13ef88  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13ef8d  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x13ef92  stind.ref
0x13ef93  ldarg.3
0x13ef94  ldarg.0
0x13ef95  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x13ef9a  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x13ef9f  ldstr    aTempdirectory// "tempDirectory"
0x13efa4  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x13efa9  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x13efae  stind.i4
0x13efaf  ret
```
