# System.Web.Configuration.BrowserDefinition::ProcessIdentificationNode

- ea: `0x13c720`
- end: `0x13c92f`
- name: `System.Web.Configuration.BrowserDefinition::ProcessIdentificationNode`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x13c160`

## callees

- `0x34f20`
- `0x34fa0`
- `0x13c6b0`
- `0x13c6f0`
- `0x13c720`
- `0x13e0e0`
- `0x143ad0`
- `0x143ae0`

## string_xrefs

- `0x13c7d6`: `User-Agent`
- `0x13c766`: `userAgent`
- `0x13c8d5`: `Config_invalid_element`

## pseudocode

```c

```

## disassembly

```asm
0x13c720  ldnull
0x13c721  stloc.0
0x13c722  ldnull
0x13c723  stloc.1
0x13c724  ldc.i4.1
0x13c725  stloc.3
0x13c726  ldarg.1
0x13c727  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x13c72c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x13c731  stloc.s  4
0x13c733  br       loc_13C8F7
0x13c738  ldloc.s  4
0x13c73a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13c73f  castclass [System.Xml]System.Xml.XmlNode
0x13c744  stloc.s  5
0x13c746  ldsfld   string [mscorlib]System.String::Empty
0x13c74b  stloc.0
0x13c74c  ldc.i4.0
0x13c74d  stloc.2
0x13c74e  ldloc.s  5
0x13c750  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x13c755  ldc.i4.1
0x13c756  bne.un   loc_13C8F7
0x13c75b  ldloc.s  5
0x13c75d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x13c762  stloc.s  6
0x13c764  ldloc.s  6
0x13c766  ldstr    aUseragent_0// "userAgent"
0x13c76b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c770  brtrue.s loc_13C796
0x13c772  ldloc.s  6
0x13c774  ldstr    aHeader// "header"
0x13c779  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c77e  brtrue.s loc_13C7FB
0x13c780  ldloc.s  6
0x13c782  ldstr    aCapability// "capability"
0x13c787  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c78c  brtrue   loc_13C86B
0x13c791  br       loc_13C8D5
0x13c796  ldc.i4.0
0x13c797  stloc.3
0x13c798  ldloc.s  5
0x13c79a  ldstr    aMatch// "match"
0x13c79f  ldloca.s 0
0x13c7a1  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c7a6  pop
0x13c7a7  ldloc.0
0x13c7a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c7ad  brfalse.s loc_13C7D0
0x13c7af  ldloc.s  5
0x13c7b1  ldstr    aNonmatch// "nonMatch"
0x13c7b6  ldloca.s 0
0x13c7b8  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c7bd  pop
0x13c7be  ldloc.0
0x13c7bf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c7c4  brfalse.s loc_13C7CE
0x13c7c6  ldarg.0
0x13c7c7  ldloc.s  5
0x13c7c9  call     instance void System.Web.Configuration.BrowserDefinition::HandleMissingMatchAndNonMatchError(class [System.Xml]System.Xml.XmlNode node)
0x13c7ce  ldc.i4.1
0x13c7cf  stloc.2
0x13c7d0  ldarg.0
0x13c7d1  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_idHeaderChecks
0x13c7d6  ldstr    aUserAgent// "User-Agent"
0x13c7db  ldloc.0
0x13c7dc  ldloc.2
0x13c7dd  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match, bool nonMatch)
0x13c7e2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13c7e7  pop
0x13c7e8  ldloc.2
0x13c7e9  brtrue   loc_13C8F7
0x13c7ee  ldarg.0
0x13c7ef  ldloc.s  5
0x13c7f1  call     instance void System.Web.Configuration.BrowserDefinition::DisallowNonMatchAttribute(class [System.Xml]System.Xml.XmlNode node)
0x13c7f6  br       loc_13C8F7
0x13c7fb  ldc.i4.0
0x13c7fc  stloc.3
0x13c7fd  ldloc.s  5
0x13c7ff  ldstr    aName// "name"
0x13c804  ldloca.s 1
0x13c806  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c80b  pop
0x13c80c  ldloc.s  5
0x13c80e  ldstr    aMatch// "match"
0x13c813  ldloca.s 0
0x13c815  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c81a  pop
0x13c81b  ldloc.0
0x13c81c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c821  brfalse.s loc_13C844
0x13c823  ldloc.s  5
0x13c825  ldstr    aNonmatch// "nonMatch"
0x13c82a  ldloca.s 0
0x13c82c  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c831  pop
0x13c832  ldloc.0
0x13c833  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c838  brfalse.s loc_13C842
0x13c83a  ldarg.0
0x13c83b  ldloc.s  5
0x13c83d  call     instance void System.Web.Configuration.BrowserDefinition::HandleMissingMatchAndNonMatchError(class [System.Xml]System.Xml.XmlNode node)
0x13c842  ldc.i4.1
0x13c843  stloc.2
0x13c844  ldarg.0
0x13c845  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_idHeaderChecks
0x13c84a  ldloc.1
0x13c84b  ldloc.0
0x13c84c  ldloc.2
0x13c84d  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match, bool nonMatch)
0x13c852  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13c857  pop
0x13c858  ldloc.2
0x13c859  brtrue   loc_13C8F7
0x13c85e  ldarg.0
0x13c85f  ldloc.s  5
0x13c861  call     instance void System.Web.Configuration.BrowserDefinition::DisallowNonMatchAttribute(class [System.Xml]System.Xml.XmlNode node)
0x13c866  br       loc_13C8F7
0x13c86b  ldc.i4.0
0x13c86c  stloc.3
0x13c86d  ldloc.s  5
0x13c86f  ldstr    aName// "name"
0x13c874  ldloca.s 1
0x13c876  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c87b  pop
0x13c87c  ldloc.s  5
0x13c87e  ldstr    aMatch// "match"
0x13c883  ldloca.s 0
0x13c885  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c88a  pop
0x13c88b  ldloc.0
0x13c88c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c891  brfalse.s loc_13C8B4
0x13c893  ldloc.s  5
0x13c895  ldstr    aNonmatch// "nonMatch"
0x13c89a  ldloca.s 0
0x13c89c  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c8a1  pop
0x13c8a2  ldloc.0
0x13c8a3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c8a8  brfalse.s loc_13C8B2
0x13c8aa  ldarg.0
0x13c8ab  ldloc.s  5
0x13c8ad  call     instance void System.Web.Configuration.BrowserDefinition::HandleMissingMatchAndNonMatchError(class [System.Xml]System.Xml.XmlNode node)
0x13c8b2  ldc.i4.1
0x13c8b3  stloc.2
0x13c8b4  ldarg.0
0x13c8b5  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_idCapabilityChecks
0x13c8ba  ldloc.1
0x13c8bb  ldloc.0
0x13c8bc  ldloc.2
0x13c8bd  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match, bool nonMatch)
0x13c8c2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13c8c7  pop
0x13c8c8  ldloc.2
0x13c8c9  brtrue.s loc_13C8F7
0x13c8cb  ldarg.0
0x13c8cc  ldloc.s  5
0x13c8ce  call     instance void System.Web.Configuration.BrowserDefinition::DisallowNonMatchAttribute(class [System.Xml]System.Xml.XmlNode node)
0x13c8d3  br.s     loc_13C8F7
0x13c8d5  ldstr    aConfigInvalidE// "Config_invalid_element"
0x13c8da  ldc.i4.1
0x13c8db  newarr   [mscorlib]System.Object
0x13c8e0  dup
0x13c8e1  ldc.i4.0
0x13c8e2  ldloc.s  5
0x13c8e4  callvirt instance string [mscorlib]System.Object::ToString()
0x13c8e9  stelem.ref
0x13c8ea  call     string System.Web.SR::GetString(string name, object[] args)
0x13c8ef  ldloc.s  5
0x13c8f1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x13c8f6  throw
0x13c8f7  ldloc.s  4
0x13c8f9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13c8fe  brtrue   loc_13C738
0x13c903  leave.s  loc_13C91A
0x13c905  ldloc.s  4
0x13c907  isinst   [mscorlib]System.IDisposable
0x13c90c  stloc.s  7
0x13c90e  ldloc.s  7
0x13c910  brfalse.s loc_13C919
0x13c912  ldloc.s  7
0x13c914  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13c919  endfinally
0x13c91a  ldloc.3
0x13c91b  brfalse.s loc_13C92E
0x13c91d  ldstr    aBrowserEmptyId// "Browser_empty_identification"
0x13c922  call     string System.Web.SR::GetString(string name)
0x13c927  ldarg.1
0x13c928  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x13c92d  throw
0x13c92e  ret
```
