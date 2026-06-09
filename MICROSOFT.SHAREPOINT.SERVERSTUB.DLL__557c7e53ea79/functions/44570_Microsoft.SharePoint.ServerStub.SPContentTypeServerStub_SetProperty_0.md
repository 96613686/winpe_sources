# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::SetProperty_0

- ea: `0x44570`
- end: `0x448f7`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::SetProperty_0`
- size: `903`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x44570`

## string_xrefs

- `0x445ed`: `DocumentTemplate`
- `0x44766`: `DocumentTemplate`
- `0x445d5`: `DisplayFormTemplateName`
- `0x44732`: `DisplayFormTemplateName`
- `0x445f9`: `EditFormTemplateName`
- `0x44780`: `EditFormTemplateName`
- `0x44629`: `JSLink`
- `0x447e8`: `JSLink`
- `0x44669`: `NewFormTemplateName`
- `0x4486a`: `NewFormTemplateName`
- `0x44683`: `ReadOnly`
- `0x4489e`: `ReadOnly`
- `0x44690`: `SchemaXmlWithResourceTokens`
- `0x448b8`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x44570  ldarg.s  4
0x44572  brtrue.s loc_4457F
0x44574  ldstr    aProxycontext// "proxyContext"
0x44579  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4457e  throw
0x4457f  ldarg.1
0x44580  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x44585  stloc.0
0x44586  ldloc.0
0x44587  brtrue.s loc_44594
0x44589  ldstr    aTarget// "target"
0x4458e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x44593  throw
0x44594  ldarg.2
0x44595  brtrue.s loc_445A2
0x44597  ldstr    aPropname// "propName"
0x4459c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x445a1  throw
0x445a2  ldarg.0
0x445a3  ldarg.2
0x445a4  ldarg.s  4
0x445a6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x445ab  starg.s  2
0x445ad  ldarg.2
0x445ae  dup
0x445af  stloc.1
0x445b0  brfalse  loc_448EB
0x445b5  volatile.
0x445b7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c9f-1
0x445bc  brtrue   loc_446B0
0x445c1  ldc.i4.s 0x12
0x445c3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x445c8  dup
0x445c9  ldstr    aDescription// "Description"
0x445ce  ldc.i4.0
0x445cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x445d4  dup
0x445d5  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x445da  ldc.i4.1
0x445db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x445e0  dup
0x445e1  ldstr    aDisplayformurl// "DisplayFormUrl"
0x445e6  ldc.i4.2
0x445e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x445ec  dup
0x445ed  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x445f2  ldc.i4.3
0x445f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x445f8  dup
0x445f9  ldstr    aEditformtempla// "EditFormTemplateName"
0x445fe  ldc.i4.4
0x445ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44604  dup
0x44605  ldstr    aEditformurl// "EditFormUrl"
0x4460a  ldc.i4.5
0x4460b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44610  dup
0x44611  ldstr    aGroup// "Group"
0x44616  ldc.i4.6
0x44617  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4461c  dup
0x4461d  ldstr    aHidden// "Hidden"
0x44622  ldc.i4.7
0x44623  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44628  dup
0x44629  ldstr    aJslink// "JSLink"
0x4462e  ldc.i4.8
0x4462f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44634  dup
0x44635  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x4463a  ldc.i4.s 9
0x4463c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44641  dup
0x44642  ldstr    aMobileeditform// "MobileEditFormUrl"
0x44647  ldc.i4.s 0xA
0x44649  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4464e  dup
0x4464f  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x44654  ldc.i4.s 0xB
0x44656  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4465b  dup
0x4465c  ldstr    aName// "Name"
0x44661  ldc.i4.s 0xC
0x44663  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44668  dup
0x44669  ldstr    aNewformtemplat// "NewFormTemplateName"
0x4466e  ldc.i4.s 0xD
0x44670  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44675  dup
0x44676  ldstr    aNewformurl// "NewFormUrl"
0x4467b  ldc.i4.s 0xE
0x4467d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x44682  dup
0x44683  ldstr    aReadonly// "ReadOnly"
0x44688  ldc.i4.s 0xF
0x4468a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4468f  dup
0x44690  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x44695  ldc.i4.s 0x10
0x44697  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4469c  dup
0x4469d  ldstr    aSealed// "Sealed"
0x446a2  ldc.i4.s 0x11
0x446a4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x446a9  volatile.
0x446ab  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c9f-1
0x446b0  volatile.
0x446b2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c9f-1
0x446b7  ldloc.1
0x446b8  ldloca.s 2
0x446ba  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x446bf  brfalse  loc_448EB
0x446c4  ldloc.2
0x446c5  switch   loc_44717, loc_44731, loc_4474B, loc_44765, loc_4477F, loc_44799, loc_447B3, loc_447CD, loc_447E7, loc_44801, loc_4481B, loc_44835, loc_4484F, loc_44869, loc_44883, loc_4489D, loc_448B7, loc_448D1
0x44712  br       loc_448EB
0x44717  ldarg.0
0x44718  ldstr    aDescription// "Description"
0x4471d  ldarg.s  4
0x4471f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44724  ldloc.0
0x44725  ldarg.3
0x44726  callvirt T0x2B000008
0x4472b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Description(string)
0x44730  ret
0x44731  ldarg.0
0x44732  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x44737  ldarg.s  4
0x44739  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4473e  ldloc.0
0x4473f  ldarg.3
0x44740  callvirt T0x2B000008
0x44745  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DisplayFormTemplateName(string)
0x4474a  ret
0x4474b  ldarg.0
0x4474c  ldstr    aDisplayformurl// "DisplayFormUrl"
0x44751  ldarg.s  4
0x44753  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44758  ldloc.0
0x44759  ldarg.3
0x4475a  callvirt T0x2B000008
0x4475f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DisplayFormUrl(string)
0x44764  ret
0x44765  ldarg.0
0x44766  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x4476b  ldarg.s  4
0x4476d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44772  ldloc.0
0x44773  ldarg.3
0x44774  callvirt T0x2B000008
0x44779  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_DocumentTemplate(string)
0x4477e  ret
0x4477f  ldarg.0
0x44780  ldstr    aEditformtempla// "EditFormTemplateName"
0x44785  ldarg.s  4
0x44787  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4478c  ldloc.0
0x4478d  ldarg.3
0x4478e  callvirt T0x2B000008
0x44793  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_EditFormTemplateName(string)
0x44798  ret
0x44799  ldarg.0
0x4479a  ldstr    aEditformurl// "EditFormUrl"
0x4479f  ldarg.s  4
0x447a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x447a6  ldloc.0
0x447a7  ldarg.3
0x447a8  callvirt T0x2B000008
0x447ad  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_EditFormUrl(string)
0x447b2  ret
0x447b3  ldarg.0
0x447b4  ldstr    aGroup// "Group"
0x447b9  ldarg.s  4
0x447bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x447c0  ldloc.0
0x447c1  ldarg.3
0x447c2  callvirt T0x2B000008
0x447c7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Group(string)
0x447cc  ret
0x447cd  ldarg.0
0x447ce  ldstr    aHidden// "Hidden"
0x447d3  ldarg.s  4
0x447d5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x447da  ldloc.0
0x447db  ldarg.3
0x447dc  callvirt T0x2B00000A
0x447e1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Hidden(bool)
0x447e6  ret
0x447e7  ldarg.0
0x447e8  ldstr    aJslink// "JSLink"
0x447ed  ldarg.s  4
0x447ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x447f4  ldloc.0
0x447f5  ldarg.3
0x447f6  callvirt T0x2B000008
0x447fb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_JSLink(string)
0x44800  ret
0x44801  ldarg.0
0x44802  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x44807  ldarg.s  4
0x44809  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4480e  ldloc.0
0x4480f  ldarg.3
0x44810  callvirt T0x2B000008
0x44815  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileDisplayFormUrl(string)
0x4481a  ret
0x4481b  ldarg.0
0x4481c  ldstr    aMobileeditform// "MobileEditFormUrl"
0x44821  ldarg.s  4
0x44823  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44828  ldloc.0
0x44829  ldarg.3
0x4482a  callvirt T0x2B000008
0x4482f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileEditFormUrl(string)
0x44834  ret
0x44835  ldarg.0
0x44836  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x4483b  ldarg.s  4
0x4483d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44842  ldloc.0
0x44843  ldarg.3
0x44844  callvirt T0x2B000008
0x44849  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_MobileNewFormUrl(string)
0x4484e  ret
0x4484f  ldarg.0
0x44850  ldstr    aName// "Name"
0x44855  ldarg.s  4
0x44857  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4485c  ldloc.0
0x4485d  ldarg.3
0x4485e  callvirt T0x2B000008
0x44863  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Name(string)
0x44868  ret
0x44869  ldarg.0
0x4486a  ldstr    aNewformtemplat// "NewFormTemplateName"
0x4486f  ldarg.s  4
0x44871  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44876  ldloc.0
0x44877  ldarg.3
0x44878  callvirt T0x2B000008
0x4487d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_NewFormTemplateName(string)
0x44882  ret
0x44883  ldarg.0
0x44884  ldstr    aNewformurl// "NewFormUrl"
0x44889  ldarg.s  4
0x4488b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x44890  ldloc.0
0x44891  ldarg.3
0x44892  callvirt T0x2B000008
0x44897  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_NewFormUrl(string)
0x4489c  ret
0x4489d  ldarg.0
0x4489e  ldstr    aReadonly// "ReadOnly"
0x448a3  ldarg.s  4
0x448a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x448aa  ldloc.0
0x448ab  ldarg.3
0x448ac  callvirt T0x2B00000A
0x448b1  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_ReadOnly(bool)
0x448b6  ret
0x448b7  ldarg.0
0x448b8  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x448bd  ldarg.s  4
0x448bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x448c4  ldloc.0
0x448c5  ldarg.3
0x448c6  callvirt T0x2B000008
0x448cb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_SchemaXmlWithResourceTokens(string)
0x448d0  ret
0x448d1  ldarg.0
0x448d2  ldstr    aSealed// "Sealed"
0x448d7  ldarg.s  4
0x448d9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x448de  ldloc.0
0x448df  ldarg.3
0x448e0  callvirt T0x2B00000A
0x448e5  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::set_Sealed(bool)
0x448ea  ret
0x448eb  ldarg.0
0x448ec  ldarg.1
0x448ed  ldarg.2
0x448ee  ldarg.3
0x448ef  ldarg.s  4
0x448f1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x448f6  ret
```
