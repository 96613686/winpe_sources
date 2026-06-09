# System.Windows.Markup.XmlAttributeProperties::.cctor

- ea: `0xb3570`
- end: `0xb3647`
- name: `System.Windows.Markup.XmlAttributeProperties::.cctor`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x159e0`
- `0x15a40`

## string_xrefs

- `0xb3605`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0xb3584`: `xmlns`
- `0xb3570`: `xml:space`
- `0xb357a`: `xml:lang`
- `0xb3594`: `XmlSpace`
- `0xb35c1`: `XmlnsDictionary`
- `0xb35ec`: `XmlnsDefinition`
- `0xb361b`: `XmlNamespaceMaps`

## pseudocode

```c

```

## disassembly

```asm
0xb3570  ldstr    aXmlSpace// "xml:space"
0xb3575  stsfld   string System.Windows.Markup.XmlAttributeProperties::XmlSpaceString
0xb357a  ldstr    aXmlLang// "xml:lang"
0xb357f  stsfld   string System.Windows.Markup.XmlAttributeProperties::XmlLangString
0xb3584  ldstr    aXmlns// "xmlns"
0xb3589  stsfld   string System.Windows.Markup.XmlAttributeProperties::XmlnsDefinitionString
0xb358e  ldnull
0xb358f  stsfld   class [mscorlib]System.Reflection.MethodInfo System.Windows.Markup.XmlAttributeProperties::_xmlSpaceSetter
0xb3594  ldstr    aXmlspace// "XmlSpace"
0xb3599  ldtoken  [mscorlib]System.String
0xb359e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35a3  ldtoken  System.Windows.Markup.XmlAttributeProperties
0xb35a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35ad  ldstr    aDefault// "default"
0xb35b2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0xb35b7  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xb35bc  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.XmlAttributeProperties::XmlSpaceProperty
0xb35c1  ldstr    aXmlnsdictionar// "XmlnsDictionary"
0xb35c6  ldtoken  System.Windows.Markup.XmlnsDictionary
0xb35cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35d0  ldtoken  System.Windows.Markup.XmlAttributeProperties
0xb35d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35da  ldnull
0xb35db  ldc.i4.s 0x20
0xb35dd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0xb35e2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xb35e7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.XmlAttributeProperties::XmlnsDictionaryProperty
0xb35ec  ldstr    aXmlnsdefinitio// "XmlnsDefinition"
0xb35f1  ldtoken  [mscorlib]System.String
0xb35f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb35fb  ldtoken  System.Windows.Markup.XmlAttributeProperties
0xb3600  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3605  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0xb360a  ldc.i4.s 0x20
0xb360c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0xb3611  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xb3616  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.XmlAttributeProperties::XmlnsDefinitionProperty
0xb361b  ldstr    aXmlnamespacema_2// "XmlNamespaceMaps"
0xb3620  ldtoken  [mscorlib]System.Collections.Hashtable
0xb3625  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb362a  ldtoken  System.Windows.Markup.XmlAttributeProperties
0xb362f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3634  ldnull
0xb3635  ldc.i4.s 0x20
0xb3637  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0xb363c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0xb3641  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.XmlAttributeProperties::XmlNamespaceMapsProperty
0xb3646  ret
```
