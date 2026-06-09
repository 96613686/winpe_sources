# Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::ReadXmlVideoProviders

- ea: `0x3120`
- end: `0x319a`
- name: `Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::ReadXmlVideoProviders`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d30`

## callees

- `0x2da0`
- `0x3120`
- `0x7f50`

## string_xrefs

- `0x312f`: `Invalid videoProviders.xml file detected`

## pseudocode

```c

```

## disassembly

```asm
0x3120  ldarg.0
0x3121  ldstr    aVideoproviders// "//videoProviders"
0x3126  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x312b  stloc.0
0x312c  ldloc.0
0x312d  brtrue.s loc_313A
0x312f  ldstr    aInvalidVideopr// "Invalid videoProviders.xml file detecte"...
0x3134  newobj   instance void Microsoft.SharePoint.Spx.WebSite.Controls.WebSiteException::.ctor(string message)
0x3139  throw
0x313a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider>::.ctor()
0x313f  stloc.1
0x3140  ldarg.0
0x3141  ldstr    aVideoproviders_0// "//videoProviders/provider"
0x3146  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x314b  stloc.2
0x314c  ldloc.2
0x314d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3152  stloc.s  5
0x3154  br.s     loc_3173
0x3156  ldloc.s  5
0x3158  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x315d  castclass [System.Xml]System.Xml.XmlNode
0x3162  stloc.3
0x3163  ldloc.3
0x3164  call     class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::VideoProviderFromXml(class [System.Xml]System.Xml.XmlNode providerNode)
0x3169  stloc.s  4
0x316b  ldloc.1
0x316c  ldloc.s  4
0x316e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider>::Add(var<u1>)
0x3173  ldloc.s  5
0x3175  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x317a  brtrue.s loc_3156
0x317c  leave.s  loc_3193
0x317e  ldloc.s  5
0x3180  isinst   [mscorlib]System.IDisposable
0x3185  stloc.s  6
0x3187  ldloc.s  6
0x3189  brfalse.s loc_3192
0x318b  ldloc.s  6
0x318d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3192  endfinally
0x3193  ldloc.1
0x3194  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider>::ToArray()
0x3199  ret
```
