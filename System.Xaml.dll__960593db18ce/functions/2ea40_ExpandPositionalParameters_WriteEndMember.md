# ExpandPositionalParameters::WriteEndMember

- ea: `0x2ea40`
- end: `0x2ea87`
- name: `ExpandPositionalParameters::WriteEndMember`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x9ec0`
- `0xf380`
- `0x2e4d0`
- `0x2e7b0`
- `0x2e840`
- `0x2ea40`
- `0x2eb90`
- `0x2ebb0`

## string_xrefs

- `0x2ea61`: `WriteEndMember`

## pseudocode

```c

```

## disassembly

```asm
0x2ea40  ldarg.1
0x2ea41  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea46  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2ea4b  callvirt instance void System.Xaml.XamlWriter::WriteEndMember()
0x2ea50  ldarg.0
0x2ea51  ldarg.1
0x2ea52  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea57  callvirt instance class System.Xaml.XamlMarkupExtensionWriter PositionalParameterStateInfo::get_Writer()
0x2ea5c  callvirt instance bool System.Xaml.XamlMarkupExtensionWriter::get_Failed()
0x2ea61  ldstr    aWriteendmember// "WriteEndMember"
0x2ea66  call     instance void ExpandPositionalParameters::ThrowIfFailed(bool fail, string operation)
0x2ea6b  ldarg.1
0x2ea6c  ldfld    class PositionalParameterStateInfo System.Xaml.XamlXmlWriter::ppStateInfo
0x2ea71  callvirt instance int32 PositionalParameterStateInfo::get_CurrentDepth()
0x2ea76  brtrue.s loc_2EA86
0x2ea78  ldarg.0
0x2ea79  ldarg.1
0x2ea7a  call     instance void ExpandPositionalParameters::ExpandPositionalParametersIntoProperties(class System.Xaml.XamlXmlWriter writer)
0x2ea7f  ldarg.0
0x2ea80  ldarg.1
0x2ea81  call     instance void ExpandPositionalParameters::WriteNodes(class System.Xaml.XamlXmlWriter writer)
0x2ea86  ret
```
