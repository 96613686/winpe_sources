# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::SetProperty

- ea: `0x42fd0`
- end: `0x4337b`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::SetProperty`
- size: `939`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x42fd0`

## string_xrefs

- `0x4304d`: `DocumentTemplate`
- `0x431cc`: `DocumentTemplate`
- `0x43035`: `DisplayFormTemplateName`
- `0x43194`: `DisplayFormTemplateName`
- `0x43059`: `EditFormTemplateName`
- `0x431e8`: `EditFormTemplateName`
- `0x43089`: `JSLink`
- `0x43258`: `JSLink`
- `0x430c9`: `NewFormTemplateName`
- `0x432e4`: `NewFormTemplateName`
- `0x430e3`: `ReadOnly`
- `0x4331c`: `ReadOnly`
- `0x430f0`: `SchemaXmlWithResourceTokens`
- `0x43338`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x42fd0  ldarg.s  4
0x42fd2  brtrue.s loc_42FDF
0x42fd4  ldstr    aProxycontext// "proxyContext"
0x42fd9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42fde  throw
0x42fdf  ldarg.1
0x42fe0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x42fe5  stloc.0
0x42fe6  ldloc.0
0x42fe7  brtrue.s loc_42FF4
0x42fe9  ldstr    aTarget// "target"
0x42fee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42ff3  throw
0x42ff4  ldarg.2
0x42ff5  brtrue.s loc_43002
0x42ff7  ldstr    aPropname// "propName"
0x42ffc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x43001  throw
0x43002  ldarg.0
0x43003  ldarg.2
0x43004  ldarg.s  4
0x43006  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4300b  starg.s  2
0x4300d  ldarg.2
0x4300e  dup
0x4300f  stloc.1
0x43010  brfalse  loc_4336F
0x43015  volatile.
0x43017  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c91-1
0x4301c  brtrue   loc_43110
0x43021  ldc.i4.s 0x12
0x43023  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x43028  dup
0x43029  ldstr    aDescription// "Description"
0x4302e  ldc.i4.0
0x4302f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43034  dup
0x43035  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x4303a  ldc.i4.1
0x4303b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43040  dup
0x43041  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43046  ldc.i4.2
0x43047  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4304c  dup
0x4304d  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x43052  ldc.i4.3
0x43053  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43058  dup
0x43059  ldstr    aEditformtempla// "EditFormTemplateName"
0x4305e  ldc.i4.4
0x4305f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43064  dup
0x43065  ldstr    aEditformurl// "EditFormUrl"
0x4306a  ldc.i4.5
0x4306b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43070  dup
0x43071  ldstr    aGroup// "Group"
0x43076  ldc.i4.6
0x43077  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4307c  dup
0x4307d  ldstr    aHidden// "Hidden"
0x43082  ldc.i4.7
0x43083  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43088  dup
0x43089  ldstr    aJslink// "JSLink"
0x4308e  ldc.i4.8
0x4308f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43094  dup
0x43095  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x4309a  ldc.i4.s 9
0x4309c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430a1  dup
0x430a2  ldstr    aMobileeditform// "MobileEditFormUrl"
0x430a7  ldc.i4.s 0xA
0x430a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430ae  dup
0x430af  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x430b4  ldc.i4.s 0xB
0x430b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430bb  dup
0x430bc  ldstr    aName// "Name"
0x430c1  ldc.i4.s 0xC
0x430c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430c8  dup
0x430c9  ldstr    aNewformtemplat// "NewFormTemplateName"
0x430ce  ldc.i4.s 0xD
0x430d0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430d5  dup
0x430d6  ldstr    aNewformurl// "NewFormUrl"
0x430db  ldc.i4.s 0xE
0x430dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430e2  dup
0x430e3  ldstr    aReadonly// "ReadOnly"
0x430e8  ldc.i4.s 0xF
0x430ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430ef  dup
0x430f0  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x430f5  ldc.i4.s 0x10
0x430f7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x430fc  dup
0x430fd  ldstr    aSealed// "Sealed"
0x43102  ldc.i4.s 0x11
0x43104  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43109  volatile.
0x4310b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c91-1
0x43110  volatile.
0x43112  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c91-1
0x43117  ldloc.1
0x43118  ldloca.s 2
0x4311a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4311f  brfalse  loc_4336F
0x43124  ldloc.2
0x43125  switch   loc_43177, loc_43193, loc_431AF, loc_431CB, loc_431E7, loc_43203, loc_4321F, loc_4323B, loc_43257, loc_43273, loc_4328F, loc_432AB, loc_432C7, loc_432E3, loc_432FF, loc_4331B, loc_43337, loc_43353
0x43172  br       loc_4336F
0x43177  ldarg.0
0x43178  ldstr    aDescription// "Description"
0x4317d  ldarg.s  4
0x4317f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43184  ldloc.0
0x43185  ldarg.3
0x43186  ldarg.s  4
0x43188  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4318d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Description(string)
0x43192  ret
0x43193  ldarg.0
0x43194  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43199  ldarg.s  4
0x4319b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431a0  ldloc.0
0x431a1  ldarg.3
0x431a2  ldarg.s  4
0x431a4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431a9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DisplayFormTemplateName(string)
0x431ae  ret
0x431af  ldarg.0
0x431b0  ldstr    aDisplayformurl// "DisplayFormUrl"
0x431b5  ldarg.s  4
0x431b7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431bc  ldloc.0
0x431bd  ldarg.3
0x431be  ldarg.s  4
0x431c0  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431c5  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DisplayFormUrl(string)
0x431ca  ret
0x431cb  ldarg.0
0x431cc  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x431d1  ldarg.s  4
0x431d3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431d8  ldloc.0
0x431d9  ldarg.3
0x431da  ldarg.s  4
0x431dc  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431e1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DocumentTemplate(string)
0x431e6  ret
0x431e7  ldarg.0
0x431e8  ldstr    aEditformtempla// "EditFormTemplateName"
0x431ed  ldarg.s  4
0x431ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431f4  ldloc.0
0x431f5  ldarg.3
0x431f6  ldarg.s  4
0x431f8  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x431fd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_EditFormTemplateName(string)
0x43202  ret
0x43203  ldarg.0
0x43204  ldstr    aEditformurl// "EditFormUrl"
0x43209  ldarg.s  4
0x4320b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43210  ldloc.0
0x43211  ldarg.3
0x43212  ldarg.s  4
0x43214  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43219  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_EditFormUrl(string)
0x4321e  ret
0x4321f  ldarg.0
0x43220  ldstr    aGroup// "Group"
0x43225  ldarg.s  4
0x43227  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4322c  ldloc.0
0x4322d  ldarg.3
0x4322e  ldarg.s  4
0x43230  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43235  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Group(string)
0x4323a  ret
0x4323b  ldarg.0
0x4323c  ldstr    aHidden// "Hidden"
0x43241  ldarg.s  4
0x43243  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43248  ldloc.0
0x43249  ldarg.3
0x4324a  ldarg.s  4
0x4324c  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43251  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Hidden(bool)
0x43256  ret
0x43257  ldarg.0
0x43258  ldstr    aJslink// "JSLink"
0x4325d  ldarg.s  4
0x4325f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43264  ldloc.0
0x43265  ldarg.3
0x43266  ldarg.s  4
0x43268  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4326d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_JSLink(string)
0x43272  ret
0x43273  ldarg.0
0x43274  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x43279  ldarg.s  4
0x4327b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43280  ldloc.0
0x43281  ldarg.3
0x43282  ldarg.s  4
0x43284  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43289  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileDisplayFormUrl(string)
0x4328e  ret
0x4328f  ldarg.0
0x43290  ldstr    aMobileeditform// "MobileEditFormUrl"
0x43295  ldarg.s  4
0x43297  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4329c  ldloc.0
0x4329d  ldarg.3
0x4329e  ldarg.s  4
0x432a0  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432a5  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileEditFormUrl(string)
0x432aa  ret
0x432ab  ldarg.0
0x432ac  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x432b1  ldarg.s  4
0x432b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432b8  ldloc.0
0x432b9  ldarg.3
0x432ba  ldarg.s  4
0x432bc  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432c1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileNewFormUrl(string)
0x432c6  ret
0x432c7  ldarg.0
0x432c8  ldstr    aName// "Name"
0x432cd  ldarg.s  4
0x432cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432d4  ldloc.0
0x432d5  ldarg.3
0x432d6  ldarg.s  4
0x432d8  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432dd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Name(string)
0x432e2  ret
0x432e3  ldarg.0
0x432e4  ldstr    aNewformtemplat// "NewFormTemplateName"
0x432e9  ldarg.s  4
0x432eb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432f0  ldloc.0
0x432f1  ldarg.3
0x432f2  ldarg.s  4
0x432f4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x432f9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_NewFormTemplateName(string)
0x432fe  ret
0x432ff  ldarg.0
0x43300  ldstr    aNewformurl// "NewFormUrl"
0x43305  ldarg.s  4
0x43307  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4330c  ldloc.0
0x4330d  ldarg.3
0x4330e  ldarg.s  4
0x43310  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43315  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_NewFormUrl(string)
0x4331a  ret
0x4331b  ldarg.0
0x4331c  ldstr    aReadonly// "ReadOnly"
0x43321  ldarg.s  4
0x43323  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43328  ldloc.0
0x43329  ldarg.3
0x4332a  ldarg.s  4
0x4332c  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43331  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_ReadOnly(bool)
0x43336  ret
0x43337  ldarg.0
0x43338  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4333d  ldarg.s  4
0x4333f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43344  ldloc.0
0x43345  ldarg.3
0x43346  ldarg.s  4
0x43348  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4334d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_SchemaXmlWithResourceTokens(string)
0x43352  ret
0x43353  ldarg.0
0x43354  ldstr    aSealed// "Sealed"
0x43359  ldarg.s  4
0x4335b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43360  ldloc.0
0x43361  ldarg.3
0x43362  ldarg.s  4
0x43364  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43369  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Sealed(bool)
0x4336e  ret
0x4336f  ldarg.0
0x43370  ldarg.1
0x43371  ldarg.2
0x43372  ldarg.3
0x43373  ldarg.s  4
  ... truncated ...
```
