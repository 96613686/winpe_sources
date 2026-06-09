# System.Web.Configuration.BrowserDefinition::ProcessControlAdaptersNode

- ea: `0x13cb10`
- end: `0x13cbfd`
- name: `System.Web.Configuration.BrowserDefinition::ProcessControlAdaptersNode`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x13c160`

## callees

- `0x34fa0`
- `0x130680`
- `0x13cb10`
- `0x13cc00`
- `0x143ab0`
- `0x143ac0`
- `0x143ae0`

## string_xrefs

- `0x13cb5d`: `Config_base_unrecognized_element`
- `0x13cb11`: `markupTextWriterType`

## pseudocode

```c

```

## disassembly

```asm
0x13cb10  ldarg.1
0x13cb11  ldstr    aMarkuptextwrit// "markupTextWriterType"
0x13cb16  ldarg.0
0x13cb17  ldflda   string System.Web.Configuration.BrowserDefinition::_htmlTextWriterString
0x13cb1c  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13cb21  pop
0x13cb22  ldarg.1
0x13cb23  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x13cb28  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x13cb2d  stloc.0
0x13cb2e  br       loc_13CBDB
0x13cb33  ldloc.0
0x13cb34  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13cb39  castclass [System.Xml]System.Xml.XmlNode
0x13cb3e  stloc.1
0x13cb3f  ldloc.1
0x13cb40  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x13cb45  ldc.i4.1
0x13cb46  bne.un   loc_13CBDB
0x13cb4b  ldloc.1
0x13cb4c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x13cb51  ldstr    aAdapter// "adapter"
0x13cb56  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x13cb5b  brfalse.s loc_13CB6E
0x13cb5d  ldstr    aConfigBaseUnre// "Config_base_unrecognized_element"
0x13cb62  call     string System.Web.SR::GetString(string name)
0x13cb67  ldloc.1
0x13cb68  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x13cb6d  throw
0x13cb6e  ldloc.1
0x13cb6f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x13cb74  stloc.2
0x13cb75  ldnull
0x13cb76  stloc.3
0x13cb77  ldnull
0x13cb78  stloc.s  4
0x13cb7a  ldloc.1
0x13cb7b  ldstr    aControltype// "controlType"
0x13cb80  ldloca.s 3
0x13cb82  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13cb87  pop
0x13cb88  ldloc.1
0x13cb89  ldstr    aAdaptertype// "adapterType"
0x13cb8e  ldloca.s 4
0x13cb90  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13cb95  pop
0x13cb96  ldloc.3
0x13cb97  ldtoken  System.Web.UI.Control
0x13cb9c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13cba1  ldloc.1
0x13cba2  call     class [mscorlib]System.Type System.Web.Configuration.BrowserDefinition::CheckType(string typeName, class [mscorlib]System.Type baseType, class [System.Xml]System.Xml.XmlNode child)
0x13cba7  stloc.s  5
0x13cba9  ldloc.s  5
0x13cbab  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x13cbb0  stloc.3
0x13cbb1  ldloc.s  4
0x13cbb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13cbb8  brtrue.s loc_13CBCD
0x13cbba  ldloc.s  4
0x13cbbc  ldtoken  System.Web.UI.Adapters.ControlAdapter
0x13cbc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13cbc6  ldloc.1
0x13cbc7  call     class [mscorlib]System.Type System.Web.Configuration.BrowserDefinition::CheckType(string typeName, class [mscorlib]System.Type baseType, class [System.Xml]System.Xml.XmlNode child)
0x13cbcc  pop
0x13cbcd  ldarg.0
0x13cbce  ldfld    class System.Web.Configuration.AdapterDictionary System.Web.Configuration.BrowserDefinition::_adapters
0x13cbd3  ldloc.3
0x13cbd4  ldloc.s  4
0x13cbd6  callvirt instance void System.Web.Configuration.AdapterDictionary::set_Item(string key, string value)
0x13cbdb  ldloc.0
0x13cbdc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13cbe1  brtrue   loc_13CB33
0x13cbe6  leave.s  loc_13CBFC
0x13cbe8  ldloc.0
0x13cbe9  isinst   [mscorlib]System.IDisposable
0x13cbee  stloc.s  6
0x13cbf0  ldloc.s  6
0x13cbf2  brfalse.s loc_13CBFB
0x13cbf4  ldloc.s  6
0x13cbf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13cbfb  endfinally
0x13cbfc  ret
```
