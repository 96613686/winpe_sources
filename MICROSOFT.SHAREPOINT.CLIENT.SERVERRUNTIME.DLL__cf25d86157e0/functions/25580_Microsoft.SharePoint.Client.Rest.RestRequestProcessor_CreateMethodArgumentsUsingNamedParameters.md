# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateMethodArgumentsUsingNamedParameters

- ea: `0x25580`
- end: `0x257e3`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateMethodArgumentsUsingNamedParameters`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x24590`
- `0x25360`

## callees

- `0x8b30`
- `0x8b70`
- `0x8bb0`
- `0x8d00`
- `0x8d40`
- `0x8d80`
- `0x8dd0`
- `0x8e10`
- `0x8f50`
- `0x8ff0`
- `0x9030`
- `0x98e0`
- `0xe000`
- `0xe010`
- `0xefc0`
- `0xf0a0`
- `0x12df0`
- `0x12e20`
- `0x16f10`
- `0x1ba30`
- `0x20240`
- `0x254d0`
- `0x25580`
- `0x257f0`
- `0x258f0`
- `0x25bb0`
- `0x260d0`
- `0x26120`

## string_xrefs

- `0x257c3`: `Flatted complext type parameters from URL path`

## pseudocode

```c

```

## disassembly

```asm
0x25580  ldarg.1
0x25581  brtrue.s loc_2558E
0x25583  ldstr    aMethodinfo// "methodInfo"
0x25588  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2558d  throw
0x2558e  ldarg.2
0x2558f  brtrue.s loc_2559C
0x25591  ldstr    aParameterlist// "parameterList"
0x25596  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2559b  throw
0x2559c  ldarg.0
0x2559d  ldarg.1
0x2559e  ldarg.s  4
0x255a0  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ValidateMethodParameterType(class Microsoft.SharePoint.Client.MethodInformation methodInfo, bool allowPostBodyAccess)
0x255a5  ldarg.2
0x255a6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x255ab  ldc.i4.0
0x255ac  cgt
0x255ae  stloc.0
0x255af  ldarg.0
0x255b0  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x255b5  newobj   instance void Microsoft.SharePoint.Client.ClientValueCollection::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x255ba  stloc.1
0x255bb  ldarg.2
0x255bc  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x255c1  ldc.i4.1
0x255c2  bne.un.s loc_2561F
0x255c4  ldarg.1
0x255c5  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x255ca  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Count()
0x255cf  brtrue.s loc_255F5
0x255d1  ldstr    aMethodhasnopar// "MethodHasNoParameter"
0x255d6  ldc.i4.1
0x255d7  newarr   [mscorlib]System.Object
0x255dc  stloc.s  0xC
0x255de  ldloc.s  0xC
0x255e0  ldc.i4.0
0x255e1  ldarg.1
0x255e2  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x255e7  stelem.ref
0x255e8  ldloc.s  0xC
0x255ea  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x255ef  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x255f4  throw
0x255f5  ldarg.0
0x255f6  ldarg.2
0x255f7  ldc.i4.0
0x255f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x255fd  ldarg.1
0x255fe  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25603  ldc.i4.0
0x25604  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x25609  ldarg.1
0x2560a  call     instance class Microsoft.SharePoint.Client.ClientValue Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetClientValueFromEdmParserNode(class Microsoft.SharePoint.Client.Rest.EdmParserNode edmParserNode, class Microsoft.SharePoint.Client.ParameterInformation parameterInfo, class Microsoft.SharePoint.Client.MethodInformation methodInfo)
0x2560f  stloc.2
0x25610  ldloc.1
0x25611  ldc.i4.0
0x25612  ldloc.2
0x25613  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25618  ldc.i4.1
0x25619  stloc.0
0x2561a  br       loc_257CD
0x2561f  ldarg.2
0x25620  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x25625  ldc.i4.2
0x25626  rem
0x25627  brfalse.s loc_2565E
0x25629  ldarg.0
0x2562a  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2562f  ldc.i4   0x1C5103
0x25634  ldc.i4.1
0x25635  ldstr    aTheMethodParam// "The method parameter count is {0} and i"...
0x2563a  ldc.i4.1
0x2563b  newarr   [mscorlib]System.Object
0x25640  stloc.s  0xD
0x25642  ldloc.s  0xD
0x25644  ldc.i4.0
0x25645  ldarg.2
0x25646  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x2564b  box      [mscorlib]System.Int32
0x25650  stelem.ref
0x25651  ldloc.s  0xD
0x25653  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x25658  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2565d  throw
0x2565e  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x25663  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ClientValue>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x25668  stloc.3
0x25669  ldc.i4.0
0x2566a  stloc.s  4
0x2566c  br       loc_25748
0x25671  ldarg.2
0x25672  ldloc.s  4
0x25674  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x25679  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x2567e  stloc.s  5
0x25680  ldloc.3
0x25681  ldloc.s  5
0x25683  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ClientValue>::ContainsKey(var<u1>)
0x25688  brfalse.s loc_256AA
0x2568a  ldstr    aDuplicatededmm// "DuplicatedEdmMethodParameterName"
0x2568f  ldc.i4.1
0x25690  newarr   [mscorlib]System.Object
0x25695  stloc.s  0xE
0x25697  ldloc.s  0xE
0x25699  ldc.i4.0
0x2569a  ldloc.s  5
0x2569c  stelem.ref
0x2569d  ldloc.s  0xE
0x2569f  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x256a4  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x256a9  throw
0x256aa  ldarg.1
0x256ab  ldloc.s  5
0x256ad  callvirt instance int32 Microsoft.SharePoint.Client.MethodInformation::GetParameterIndex(string parameterName)
0x256b2  stloc.s  7
0x256b4  ldloc.s  7
0x256b6  ldc.i4.0
0x256b7  blt.s    loc_256C5
0x256b9  ldarg.1
0x256ba  ldloc.s  5
0x256bc  callvirt instance class Microsoft.SharePoint.Client.ParameterInformation Microsoft.SharePoint.Client.MethodInformation::GetParameter(string parameterName)
0x256c1  stloc.s  6
0x256c3  br.s     loc_25723
0x256c5  ldarg.0
0x256c6  ldarg.1
0x256c7  ldloc.s  5
0x256c9  ldloca.s 8
0x256cb  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::FlattedComplexTypeParameterContains(class Microsoft.SharePoint.Client.MethodInformation methodInfo, string parName, [out] class Microsoft.SharePoint.Client.PropertyInformation& propInfo)
0x256d0  brtrue.s loc_256F2
0x256d2  ldstr    aUnknownedmmeth// "UnknownEdmMethodParameterName"
0x256d7  ldc.i4.1
0x256d8  newarr   [mscorlib]System.Object
0x256dd  stloc.s  0xF
0x256df  ldloc.s  0xF
0x256e1  ldc.i4.0
0x256e2  ldloc.s  5
0x256e4  stelem.ref
0x256e5  ldloc.s  0xF
0x256e7  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x256ec  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x256f1  throw
0x256f2  newobj   instance void Microsoft.SharePoint.Client.ParameterInformation::.ctor()
0x256f7  stloc.s  6
0x256f9  ldloc.s  6
0x256fb  ldloc.s  8
0x256fd  callvirt instance string Microsoft.SharePoint.Client.PropertyInformation::get_Name()
0x25702  callvirt instance void Microsoft.SharePoint.Client.ParameterInformation::set_Name(string value)
0x25707  ldloc.s  6
0x25709  ldloc.s  8
0x2570b  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.PropertyInformation::get_PropertyODataType()
0x25710  callvirt instance void Microsoft.SharePoint.Client.ParameterInformation::set_ParameterODataType(valuetype Microsoft.SharePoint.Client.ODataType value)
0x25715  ldloc.s  6
0x25717  ldloc.s  8
0x25719  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.PropertyInformation::get_PropertyType()
0x2571e  callvirt instance void Microsoft.SharePoint.Client.ParameterInformation::set_ParameterType(class [mscorlib]System.Type value)
0x25723  ldarg.0
0x25724  ldarg.2
0x25725  ldloc.s  4
0x25727  ldc.i4.1
0x25728  add
0x25729  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x2572e  ldloc.s  6
0x25730  ldarg.1
0x25731  call     instance class Microsoft.SharePoint.Client.ClientValue Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetClientValueFromEdmParserNode(class Microsoft.SharePoint.Client.Rest.EdmParserNode edmParserNode, class Microsoft.SharePoint.Client.ParameterInformation parameterInfo, class Microsoft.SharePoint.Client.MethodInformation methodInfo)
0x25736  stloc.s  9
0x25738  ldloc.3
0x25739  ldloc.s  5
0x2573b  ldloc.s  9
0x2573d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ClientValue>::Add(var<u1>, !!T0)
0x25742  ldloc.s  4
0x25744  ldc.i4.2
0x25745  add
0x25746  stloc.s  4
0x25748  ldloc.s  4
0x2574a  ldarg.2
0x2574b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x25750  ldc.i4.1
0x25751  sub
0x25752  blt      loc_25671
0x25757  ldloc.3
0x25758  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ClientValue>::GetEnumerator()
0x2575d  stloc.s  0x10
0x2575f  br.s     loc_2578F
0x25761  ldloca.s 0x10
0x25763  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.SharePoint.Client.ClientValue>::get_Current()
0x25768  stloc.s  0xA
0x2576a  ldarg.1
0x2576b  ldloca.s 0xA
0x2576d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.ClientValue>::get_Key()
0x25772  callvirt instance int32 Microsoft.SharePoint.Client.MethodInformation::GetParameterIndex(string parameterName)
0x25777  stloc.s  0xB
0x25779  ldloc.s  0xB
0x2577b  ldc.i4.0
0x2577c  blt.s    loc_2578F
0x2577e  ldloc.1
0x2577f  ldloc.s  0xB
0x25781  ldloca.s 0xA
0x25783  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.ClientValue>::get_Value()
0x25788  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x2578d  ldc.i4.1
0x2578e  stloc.0
0x2578f  ldloca.s 0x10
0x25791  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.SharePoint.Client.ClientValue>::MoveNext()
0x25796  brtrue.s loc_25761
0x25798  leave.s  loc_257A8
0x2579a  ldloca.s 0x10
0x2579c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.SharePoint.Client.ClientValue>
0x257a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x257a7  endfinally
0x257a8  ldarg.0
0x257a9  ldarg.1
0x257aa  ldloc.3
0x257ab  ldarg.3
0x257ac  ldloc.0
0x257ad  ldloc.1
0x257ae  ldarga.s 4
0x257b0  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseFlattedComplexTypeParameters(class Microsoft.SharePoint.Client.MethodInformation methodInfo, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Client.ClientValue> values, bool isLeafSegment, bool hasUrlPathParameter, class Microsoft.SharePoint.Client.ClientValueCollection args, bool& allowPostBodyAccess)
0x257b5  brfalse.s loc_257CD
0x257b7  ldarg.0
0x257b8  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x257bd  ldc.i4   0x3CE898
0x257c2  ldc.i4.4
0x257c3  ldstr    aFlattedComplex// "Flatted complext type parameters from U"...
0x257c8  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x257cd  ldarg.0
0x257ce  ldarg.1
0x257cf  ldarg.s  4
0x257d1  ldarg.3
0x257d2  ldloc.0
0x257d3  ldloc.1
0x257d4  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBodyOrQueryString(class Microsoft.SharePoint.Client.MethodInformation methodInfo, bool allowPostBodyAccess, bool isLeafSegment, bool hasUrlPathParameter, class Microsoft.SharePoint.Client.ClientValueCollection args)
0x257d9  ldarg.0
0x257da  ldarg.1
0x257db  ldloc.1
0x257dc  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::SetMethodOptionalParameterDefaultValue(class Microsoft.SharePoint.Client.MethodInformation methodInfo, class Microsoft.SharePoint.Client.ClientValueCollection args)
0x257e1  ldloc.1
0x257e2  ret
```
