# System.Web.XmlSiteMapProvider::BuildSiteMap

- ea: `0x33020`
- end: `0x3328c`
- name: `System.Web.XmlSiteMapProvider::BuildSiteMap`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x24170`
- `0x2d000`
- `0x2e250`
- `0x30f70`
- `0x311e0`
- `0x31280`
- `0x33020`
- `0x33290`
- `0x33300`
- `0x336b0`
- `0x34f20`
- `0x34fa0`
- `0x143b90`

## string_xrefs

- `0x330c3`: `XmlSiteMapProvider_Error_loading_Config_file`
- `0x330f9`: `XmlSiteMapProvider_Error_loading_Config_file`
- `0x33182`: `XmlSiteMapProvider_Top_Element_Must_Be_SiteMap`
- `0x331eb`: `XmlSiteMapProvider_Only_SiteMapNode_Allowed`
- `0x33201`: `XmlSiteMapProvider_Only_One_SiteMapNode_Required_At_Top`
- `0x3323b`: `XmlSiteMapProvider_Only_One_SiteMapNode_Required_At_Top`

## pseudocode

```c

```

## disassembly

```asm
0x33020  ldarg.0
0x33021  ldfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x33026  stloc.0
0x33027  ldloc.0
0x33028  brfalse.s loc_3302C
0x3302a  ldloc.0
0x3302b  ret
0x3302c  ldarg.0
0x3302d  call     instance class [System.Xml]System.Xml.XmlDocument System.Web.XmlSiteMapProvider::GetConfigDocument()
0x33032  stloc.1
0x33033  ldarg.0
0x33034  ldfld    object System.Web.SiteMapProvider::_lock
0x33039  stloc.2
0x3303a  ldc.i4.0
0x3303b  stloc.3
0x3303c  ldloc.2
0x3303d  ldloca.s 3
0x3303f  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33044  ldarg.0
0x33045  ldfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x3304a  brfalse.s loc_33059
0x3304c  ldarg.0
0x3304d  ldfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x33052  stloc.s  8
0x33054  leave    loc_33289
0x33059  ldarg.0
0x3305a  callvirt instance void System.Web.StaticSiteMapProvider::Clear()
0x3305f  ldarg.0
0x33060  call     instance void System.Web.XmlSiteMapProvider::CheckSiteMapFileExists()
0x33065  ldarg.0
0x33066  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x3306b  callvirt instance class [mscorlib]System.IO.Stream System.Web.VirtualPath::OpenFile()
0x33070  stloc.s  9
0x33072  ldloc.s  9
0x33074  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0x33079  stloc.s  0xA
0x3307b  ldloc.1
0x3307c  ldloc.s  0xA
0x3307e  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0x33083  leave.s  loc_33091
0x33085  ldloc.s  9
0x33087  brfalse.s loc_33090
0x33089  ldloc.s  9
0x3308b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33090  endfinally
0x33091  leave    loc_33124
0x33096  stloc.s  0xB
0x33098  ldarg.0
0x33099  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x3309e  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x330a3  stloc.s  0xC
0x330a5  ldarg.0
0x330a6  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_normalizedVirtualPath
0x330ab  callvirt instance string System.Web.VirtualPath::MapPathInternal()
0x330b0  stloc.s  0xD
0x330b2  ldloc.s  0xD
0x330b4  brfalse.s loc_330C3
0x330b6  ldloc.s  0xD
0x330b8  call     bool System.Web.HttpRuntime::HasPathDiscoveryPermission(string path)
0x330bd  brfalse.s loc_330C3
0x330bf  ldloc.s  0xD
0x330c1  stloc.s  0xC
0x330c3  ldstr    aXmlsitemapprov_2// "XmlSiteMapProvider_Error_loading_Config"...
0x330c8  ldc.i4.2
0x330c9  newarr   [mscorlib]System.Object
0x330ce  dup
0x330cf  ldc.i4.0
0x330d0  ldarg.0
0x330d1  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x330d6  stelem.ref
0x330d7  dup
0x330d8  ldc.i4.1
0x330d9  ldloc.s  0xB
0x330db  callvirt instance string [mscorlib]System.Exception::get_Message()
0x330e0  stelem.ref
0x330e1  call     string System.Web.SR::GetString(string name, object[] args)
0x330e6  ldloc.s  0xB
0x330e8  ldloc.s  0xC
0x330ea  ldloc.s  0xB
0x330ec  callvirt instance int32 [System.Xml]System.Xml.XmlException::get_LineNumber()
0x330f1  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception, string, int32)
0x330f6  throw
0x330f7  stloc.s  0xE
0x330f9  ldstr    aXmlsitemapprov_2// "XmlSiteMapProvider_Error_loading_Config"...
0x330fe  ldc.i4.2
0x330ff  newarr   [mscorlib]System.Object
0x33104  dup
0x33105  ldc.i4.0
0x33106  ldarg.0
0x33107  ldfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x3310c  stelem.ref
0x3310d  dup
0x3310e  ldc.i4.1
0x3310f  ldloc.s  0xE
0x33111  callvirt instance string [mscorlib]System.Exception::get_Message()
0x33116  stelem.ref
0x33117  call     string System.Web.SR::GetString(string name, object[] args)
0x3311c  ldloc.s  0xE
0x3311e  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [mscorlib]System.Exception)
0x33123  throw
0x33124  ldnull
0x33125  stloc.s  4
0x33127  ldloc.1
0x33128  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x3312d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x33132  stloc.s  0xF
0x33134  br.s     loc_3315E
0x33136  ldloc.s  0xF
0x33138  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3313d  castclass [System.Xml]System.Xml.XmlNode
0x33142  stloc.s  0x10
0x33144  ldloc.s  0x10
0x33146  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x3314b  ldstr    aSitemap// "siteMap"
0x33150  ldc.i4.4
0x33151  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x33156  brfalse.s loc_3315E
0x33158  ldloc.s  0x10
0x3315a  stloc.s  4
0x3315c  leave.s  loc_3317E
0x3315e  ldloc.s  0xF
0x33160  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x33165  brtrue.s loc_33136
0x33167  leave.s  loc_3317E
0x33169  ldloc.s  0xF
0x3316b  isinst   [mscorlib]System.IDisposable
0x33170  stloc.s  0x11
0x33172  ldloc.s  0x11
0x33174  brfalse.s loc_3317D
0x33176  ldloc.s  0x11
0x33178  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3317d  endfinally
0x3317e  ldloc.s  4
0x33180  brtrue.s loc_33193
0x33182  ldstr    aXmlsitemapprov_3// "XmlSiteMapProvider_Top_Element_Must_Be_"...
0x33187  call     string System.Web.SR::GetString(string name)
0x3318c  ldloc.1
0x3318d  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x33192  throw
0x33193  ldc.i4.0
0x33194  stloc.s  5
0x33196  ldloc.s  4
0x33198  ldstr    aEnablelocaliza// "enableLocalization"
0x3319d  ldloca.s 5
0x3319f  call     class [System.Xml]System.Xml.XmlNode System.Web.Configuration.HandlerBase::GetAndRemoveBooleanAttribute(class [System.Xml]System.Xml.XmlNode node, string attrib, bool& val)
0x331a4  pop
0x331a5  ldarg.0
0x331a6  ldloc.s  5
0x331a8  call     instance void System.Web.SiteMapProvider::set_EnableLocalization(bool value)
0x331ad  ldnull
0x331ae  stloc.s  6
0x331b0  ldloc.s  4
0x331b2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x331b7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x331bc  stloc.s  0x12
0x331be  br.s     loc_33217
0x331c0  ldloc.s  0x12
0x331c2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x331c7  castclass [System.Xml]System.Xml.XmlNode
0x331cc  stloc.s  0x13
0x331ce  ldloc.s  0x13
0x331d0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x331d5  ldc.i4.1
0x331d6  bne.un.s loc_33217
0x331d8  ldstr    aSitemapnode// "siteMapNode"
0x331dd  ldloc.s  0x13
0x331df  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x331e4  call     instance bool [mscorlib]System.String::Equals(string)
0x331e9  brtrue.s loc_331FD
0x331eb  ldstr    aXmlsitemapprov_4// "XmlSiteMapProvider_Only_SiteMapNode_All"...
0x331f0  call     string System.Web.SR::GetString(string name)
0x331f5  ldloc.s  0x13
0x331f7  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x331fc  throw
0x331fd  ldloc.s  6
0x331ff  brfalse.s loc_33213
0x33201  ldstr    aXmlsitemapprov_5// "XmlSiteMapProvider_Only_One_SiteMapNode"...
0x33206  call     string System.Web.SR::GetString(string name)
0x3320b  ldloc.s  0x13
0x3320d  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x33212  throw
0x33213  ldloc.s  0x13
0x33215  stloc.s  6
0x33217  ldloc.s  0x12
0x33219  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3321e  brtrue.s loc_331C0
0x33220  leave.s  loc_33237
0x33222  ldloc.s  0x12
0x33224  isinst   [mscorlib]System.IDisposable
0x33229  stloc.s  0x11
0x3322b  ldloc.s  0x11
0x3322d  brfalse.s loc_33236
0x3322f  ldloc.s  0x11
0x33231  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33236  endfinally
0x33237  ldloc.s  6
0x33239  brtrue.s loc_3324D
0x3323b  ldstr    aXmlsitemapprov_5// "XmlSiteMapProvider_Only_One_SiteMapNode"...
0x33240  call     string System.Web.SR::GetString(string name)
0x33245  ldloc.s  4
0x33247  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, class [System.Xml]System.Xml.XmlNode)
0x3324c  throw
0x3324d  ldc.i4.s 0x32
0x3324f  newobj   instance void [mscorlib]System.Collections.Queue::.ctor(int32)
0x33254  stloc.s  7
0x33256  ldloc.s  7
0x33258  ldnull
0x33259  callvirt instance void [mscorlib]System.Collections.Queue::Enqueue(object)
0x3325e  ldloc.s  7
0x33260  ldloc.s  6
0x33262  callvirt instance void [mscorlib]System.Collections.Queue::Enqueue(object)
0x33267  ldarg.0
0x33268  ldarg.0
0x33269  ldloc.s  7
0x3326b  call     instance class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::ConvertFromXmlNode(class [mscorlib]System.Collections.Queue queue)
0x33270  stfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x33275  ldarg.0
0x33276  ldfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x3327b  stloc.s  8
0x3327d  leave.s  loc_33289
0x3327f  ldloc.3
0x33280  brfalse.s loc_33288
0x33282  ldloc.2
0x33283  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x33288  endfinally
0x33289  ldloc.s  8
0x3328b  ret
```
