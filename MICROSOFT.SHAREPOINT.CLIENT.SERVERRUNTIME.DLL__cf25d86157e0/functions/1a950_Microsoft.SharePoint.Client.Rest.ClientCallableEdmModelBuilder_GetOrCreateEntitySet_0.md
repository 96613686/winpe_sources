# Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetOrCreateEntitySet_0

- ea: `0x1a950`
- end: `0x1ab03`
- name: `Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetOrCreateEntitySet_0`
- size: `435`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a120`
- `0x1a940`

## callees

- `0x1a340`
- `0x1a950`

## string_xrefs

- `0x1a95a`: `GetOrCreateEntitySetLockKillSwitch`

## pseudocode

```c

```

## disassembly

```asm
0x1a950  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetOrCreateEntitySetLockKillSwitch
0x1a955  ldstr    a03072017// "03/07/2017"
0x1a95a  ldstr    aGetorcreateent// "GetOrCreateEntitySetLockKillSwitch"
0x1a95f  call     bool [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.KillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x1a964  brfalse  loc_1AA0D
0x1a969  ldarg.0
0x1a96a  ldarg.2
0x1a96b  call     instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetLowestBaseNonAbstractEntityType(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType entityType)
0x1a970  starg.s  2
0x1a972  ldarg.0
0x1a973  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMap
0x1a978  ldarg.2
0x1a979  ldloca.s 0
0x1a97b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::TryGetValue(var<u1>, !!T0)
0x1a980  brfalse.s loc_1A984
0x1a982  ldloc.0
0x1a983  ret
0x1a984  ldarg.3
0x1a985  brtrue.s loc_1A99C
0x1a987  ldarg.2
0x1a988  callvirt instance string [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmNamedElement::get_Name()
0x1a98d  starg.s  3
0x1a98f  ldarg.3
0x1a990  ldstr    aS// "s"
0x1a995  call     string [mscorlib]System.String::Concat(string, string)
0x1a99a  starg.s  3
0x1a99c  ldarg.0
0x1a99d  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1a9a2  ldarg.3
0x1a9a3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x1a9a8  brtrue.s loc_1A9B9
0x1a9aa  ldarg.0
0x1a9ab  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1a9b0  ldarg.3
0x1a9b1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1a9b6  pop
0x1a9b7  br.s     loc_1A9EE
0x1a9b9  ldc.i4.1
0x1a9ba  stloc.1
0x1a9bb  ldarg.3
0x1a9bc  ldloca.s 1
0x1a9be  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a9c3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1a9c8  call     string [mscorlib]System.String::Concat(string, string)
0x1a9cd  starg.s  3
0x1a9cf  ldloc.1
0x1a9d0  ldc.i4.1
0x1a9d1  add
0x1a9d2  stloc.1
0x1a9d3  ldarg.0
0x1a9d4  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1a9d9  ldarg.3
0x1a9da  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x1a9df  brtrue.s loc_1A9BB
0x1a9e1  ldarg.0
0x1a9e2  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1a9e7  ldarg.3
0x1a9e8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1a9ed  pop
0x1a9ee  ldarg.1
0x1a9ef  ldarg.3
0x1a9f0  ldarg.2
0x1a9f1  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet::.ctor(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer, string, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType)
0x1a9f6  stloc.2
0x1a9f7  ldarg.0
0x1a9f8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMap
0x1a9fd  ldarg.2
0x1a9fe  ldloc.2
0x1a9ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::set_Item(var<u1>, !!T0)
0x1aa04  ldarg.1
0x1aa05  ldloc.2
0x1aa06  callvirt instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntityContainer::AddElement(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainerElement)
0x1aa0b  ldloc.2
0x1aa0c  ret
0x1aa0d  ldarg.0
0x1aa0e  ldarg.2
0x1aa0f  call     instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetLowestBaseNonAbstractEntityType(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType entityType)
0x1aa14  starg.s  2
0x1aa16  ldarg.0
0x1aa17  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMapConcurrent
0x1aa1c  ldarg.2
0x1aa1d  ldloca.s 3
0x1aa1f  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::TryGetValue(var<u1>, !!T0)
0x1aa24  brfalse.s loc_1AA28
0x1aa26  ldloc.3
0x1aa27  ret
0x1aa28  ldarg.3
0x1aa29  brtrue.s loc_1AA40
0x1aa2b  ldarg.2
0x1aa2c  callvirt instance string [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmNamedElement::get_Name()
0x1aa31  starg.s  3
0x1aa33  ldarg.3
0x1aa34  ldstr    aS// "s"
0x1aa39  call     string [mscorlib]System.String::Concat(string, string)
0x1aa3e  starg.s  3
0x1aa40  ldc.i4.0
0x1aa41  stloc.s  6
0x1aa43  ldarg.0
0x1aa44  ldfld    object Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetLock
0x1aa49  dup
0x1aa4a  stloc.s  8
0x1aa4c  ldloca.s 6
0x1aa4e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1aa53  ldarg.0
0x1aa54  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMapConcurrent
0x1aa59  ldarg.2
0x1aa5a  ldloca.s 3
0x1aa5c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::TryGetValue(var<u1>, !!T0)
0x1aa61  brfalse.s loc_1AA6B
0x1aa63  ldloc.3
0x1aa64  stloc.s  7
0x1aa66  leave    loc_1AB00
0x1aa6b  ldarg.0
0x1aa6c  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1aa71  ldarg.3
0x1aa72  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x1aa77  brtrue.s loc_1AA88
0x1aa79  ldarg.0
0x1aa7a  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1aa7f  ldarg.3
0x1aa80  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1aa85  pop
0x1aa86  br.s     loc_1AAC0
0x1aa88  ldc.i4.1
0x1aa89  stloc.s  4
0x1aa8b  ldarg.3
0x1aa8c  ldloca.s 4
0x1aa8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1aa93  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1aa98  call     string [mscorlib]System.String::Concat(string, string)
0x1aa9d  starg.s  3
0x1aa9f  ldloc.s  4
0x1aaa1  ldc.i4.1
0x1aaa2  add
0x1aaa3  stloc.s  4
0x1aaa5  ldarg.0
0x1aaa6  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1aaab  ldarg.3
0x1aaac  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x1aab1  brtrue.s loc_1AA8B
0x1aab3  ldarg.0
0x1aab4  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entitySetNames
0x1aab9  ldarg.3
0x1aaba  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1aabf  pop
0x1aac0  ldarg.1
0x1aac1  ldarg.3
0x1aac2  ldarg.2
0x1aac3  newobj   instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet::.ctor(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainer, string, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType)
0x1aac8  stloc.s  5
0x1aaca  ldarg.0
0x1aacb  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMapConcurrent
0x1aad0  ldarg.2
0x1aad1  ldloc.s  5
0x1aad3  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::set_Item(var<u1>, !!T0)
0x1aad8  ldarg.0
0x1aad9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet> Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::m_entityTypeToEntitySetMap
0x1aade  ldarg.2
0x1aadf  ldloc.s  5
0x1aae1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType, class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet>::set_Item(var<u1>, !!T0)
0x1aae6  ldarg.1
0x1aae7  ldloc.s  5
0x1aae9  callvirt instance void [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntityContainer::AddElement(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityContainerElement)
0x1aaee  ldloc.s  5
0x1aaf0  stloc.s  7
0x1aaf2  leave.s  loc_1AB00
0x1aaf4  ldloc.s  6
0x1aaf6  brfalse.s loc_1AAFF
0x1aaf8  ldloc.s  8
0x1aafa  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1aaff  endfinally
0x1ab00  ldloc.s  7
0x1ab02  ret
```
