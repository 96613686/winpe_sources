# System.Web.Configuration.BrowserDefinition::ProcessCaptureNode

- ea: `0x13c930`
- end: `0x13ca62`
- name: `System.Web.Configuration.BrowserDefinition::ProcessCaptureNode`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x13c160`

## callees

- `0x34f20`
- `0x13c930`
- `0x13e110`
- `0x143ae0`

## string_xrefs

- `0x13c9a8`: `User-Agent`
- `0x13c967`: `userAgent`
- `0x13ca20`: `Config_invalid_element`

## pseudocode

```c

```

## disassembly

```asm
0x13c930  ldnull
0x13c931  stloc.0
0x13c932  ldnull
0x13c933  stloc.1
0x13c934  ldarg.1
0x13c935  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x13c93a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x13c93f  stloc.2
0x13c940  br       loc_13CA40
0x13c945  ldloc.2
0x13c946  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13c94b  castclass [System.Xml]System.Xml.XmlNode
0x13c950  stloc.3
0x13c951  ldloc.3
0x13c952  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x13c957  ldc.i4.1
0x13c958  bne.un   loc_13CA40
0x13c95d  ldloc.3
0x13c95e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x13c963  stloc.s  4
0x13c965  ldloc.s  4
0x13c967  ldstr    aUseragent_0// "userAgent"
0x13c96c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c971  brtrue.s loc_13C994
0x13c973  ldloc.s  4
0x13c975  ldstr    aHeader// "header"
0x13c97a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c97f  brtrue.s loc_13C9BE
0x13c981  ldloc.s  4
0x13c983  ldstr    aCapability// "capability"
0x13c988  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13c98d  brtrue.s loc_13C9EF
0x13c98f  br       loc_13CA20
0x13c994  ldloc.3
0x13c995  ldstr    aMatch// "match"
0x13c99a  ldloca.s 0
0x13c99c  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c9a1  pop
0x13c9a2  ldarg.0
0x13c9a3  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_captureHeaderChecks
0x13c9a8  ldstr    aUserAgent// "User-Agent"
0x13c9ad  ldloc.0
0x13c9ae  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match)
0x13c9b3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13c9b8  pop
0x13c9b9  br       loc_13CA40
0x13c9be  ldloc.3
0x13c9bf  ldstr    aName// "name"
0x13c9c4  ldloca.s 1
0x13c9c6  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c9cb  pop
0x13c9cc  ldloc.3
0x13c9cd  ldstr    aMatch// "match"
0x13c9d2  ldloca.s 0
0x13c9d4  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c9d9  pop
0x13c9da  ldarg.0
0x13c9db  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_captureHeaderChecks
0x13c9e0  ldloc.1
0x13c9e1  ldloc.0
0x13c9e2  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match)
0x13c9e7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13c9ec  pop
0x13c9ed  br.s     loc_13CA40
0x13c9ef  ldloc.3
0x13c9f0  ldstr    aName// "name"
0x13c9f5  ldloca.s 1
0x13c9f7  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13c9fc  pop
0x13c9fd  ldloc.3
0x13c9fe  ldstr    aMatch// "match"
0x13ca03  ldloca.s 0
0x13ca05  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveRequiredNonEmptyStringAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, string& val)
0x13ca0a  pop
0x13ca0b  ldarg.0
0x13ca0c  ldfld    class [mscorlib]System.Collections.ArrayList System.Web.Configuration.BrowserDefinition::_captureCapabilityChecks
0x13ca11  ldloc.1
0x13ca12  ldloc.0
0x13ca13  newobj   instance void System.Web.Configuration.CheckPair::.ctor(string header, string match)
0x13ca18  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x13ca1d  pop
0x13ca1e  br.s     loc_13CA40
0x13ca20  ldstr    aConfigInvalidE// "Config_invalid_element"
0x13ca25  ldc.i4.1
0x13ca26  newarr   [mscorlib]System.Object
0x13ca2b  dup
0x13ca2c  ldc.i4.0
0x13ca2d  ldloc.3
0x13ca2e  callvirt instance string [mscorlib]System.Object::ToString()
0x13ca33  stelem.ref
0x13ca34  call     string System.Web.SR::GetString(string name, object[] args)
0x13ca39  ldloc.3
0x13ca3a  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x13ca3f  throw
0x13ca40  ldloc.2
0x13ca41  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13ca46  brtrue   loc_13C945
0x13ca4b  leave.s  loc_13CA61
0x13ca4d  ldloc.2
0x13ca4e  isinst   [mscorlib]System.IDisposable
0x13ca53  stloc.s  5
0x13ca55  ldloc.s  5
0x13ca57  brfalse.s loc_13CA60
0x13ca59  ldloc.s  5
0x13ca5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13ca60  endfinally
0x13ca61  ret
```
