# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBodyOrQueryString

- ea: `0x25bb0`
- end: `0x25e77`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBodyOrQueryString`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x25580`

## callees

- `0x8cf0`
- `0x8d10`
- `0x8d30`
- `0x8d70`
- `0x8e10`
- `0x8f50`
- `0x98e0`
- `0xe010`
- `0xeea0`
- `0xf0a0`
- `0x12440`
- `0x12e20`
- `0x16f10`
- `0x18130`
- `0x1bd80`
- `0x1bfc0`
- `0x20240`
- `0x21300`
- `0x22170`
- `0x23de0`
- `0x25bb0`
- `0x25e80`
- `0x26190`

## string_xrefs

- `0x25d1b`: `isLeafSegment={0}, queryStringParameterDone={1}, hasUrlPathParameter={2}`

## pseudocode

```c

```

## disassembly

```asm
0x25bb0  ldc.i4.0
0x25bb1  stloc.1
0x25bb2  ldc.i4.0
0x25bb3  stloc.2
0x25bb4  ldc.i4.0
0x25bb5  stloc.3
0x25bb6  br       loc_25CFE
0x25bbb  ldarg.1
0x25bbc  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25bc1  ldloc.3
0x25bc2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x25bc7  stloc.s  4
0x25bc9  ldloc.s  4
0x25bcb  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.ParameterInformation::get_ParameterODataType()
0x25bd0  ldc.i4.3
0x25bd1  bne.un   loc_25C97
0x25bd6  ldloc.s  4
0x25bd8  callvirt instance valuetype Microsoft.SharePoint.Client.RESTfulParameterSource Microsoft.SharePoint.Client.ParameterInformation::get_RESTfulParameterSource()
0x25bdd  ldc.i4.2
0x25bde  bne.un   loc_25C97
0x25be3  ldloc.s  4
0x25be5  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x25bea  ldloca.s 0
0x25bec  call     bool Microsoft.SharePoint.Client.Utility::IsStringKeyDictionary(class [mscorlib]System.Type type, [out] class [mscorlib]System.Type& valueType)
0x25bf1  brfalse  loc_25C97
0x25bf6  ldloc.0
0x25bf7  ldtoken  [mscorlib]System.String
0x25bfc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25c01  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x25c06  brfalse  loc_25C97
0x25c0b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x25c10  stloc.s  5
0x25c12  ldarg.0
0x25c13  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_QueryStrings()
0x25c18  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x25c1d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x25c22  stloc.s  0xD
0x25c24  br.s     loc_25C60
0x25c26  ldloc.s  0xD
0x25c28  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x25c2d  castclass [mscorlib]System.String
0x25c32  stloc.s  6
0x25c34  ldloc.s  6
0x25c36  callvirt instance int32 [mscorlib]System.String::get_Length()
0x25c3b  ldc.i4.1
0x25c3c  ble.s    loc_25C60
0x25c3e  ldloc.s  6
0x25c40  ldc.i4.0
0x25c41  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x25c46  ldc.i4.s 0x24
0x25c48  beq.s    loc_25C60
0x25c4a  ldloc.s  5
0x25c4c  ldloc.s  6
0x25c4e  ldarg.0
0x25c4f  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_QueryStrings()
0x25c54  ldloc.s  6
0x25c56  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25c5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x25c60  ldloc.s  0xD
0x25c62  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25c67  brtrue.s loc_25C26
0x25c69  leave.s  loc_25C80
0x25c6b  ldloc.s  0xD
0x25c6d  isinst   [mscorlib]System.IDisposable
0x25c72  stloc.s  0xE
0x25c74  ldloc.s  0xE
0x25c76  brfalse.s loc_25C7F
0x25c78  ldloc.s  0xE
0x25c7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25c7f  endfinally
0x25c80  ldarg.s  5
0x25c82  ldloc.3
0x25c83  ldarg.0
0x25c84  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25c89  ldloc.s  5
0x25c8b  newobj   instance void Microsoft.SharePoint.Client.ServerObjectClientValue::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext, object value)
0x25c90  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25c95  ldc.i4.1
0x25c96  stloc.1
0x25c97  ldloc.s  4
0x25c99  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x25c9e  ldtoken  [mscorlib]System.IO.Stream
0x25ca3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25ca8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x25cad  brfalse.s loc_25CFA
0x25caf  ldloc.2
0x25cb0  ldc.i4.0
0x25cb1  ble.s    loc_25CD7
0x25cb3  ldstr    aNotsupportedme_0// "NotSupportedMethodWithMultipleStreamPar"...
0x25cb8  ldc.i4.1
0x25cb9  newarr   [mscorlib]System.Object
0x25cbe  stloc.s  0xF
0x25cc0  ldloc.s  0xF
0x25cc2  ldc.i4.0
0x25cc3  ldarg.1
0x25cc4  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x25cc9  stelem.ref
0x25cca  ldloc.s  0xF
0x25ccc  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x25cd1  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x25cd6  throw
0x25cd7  ldloc.2
0x25cd8  ldc.i4.1
0x25cd9  add
0x25cda  stloc.2
0x25cdb  ldarg.2
0x25cdc  brfalse.s loc_25CFA
0x25cde  ldarg.s  5
0x25ce0  ldloc.3
0x25ce1  ldarg.0
0x25ce2  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25ce7  ldarg.0
0x25ce8  call     instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream()
0x25ced  newobj   instance void Microsoft.SharePoint.Client.ServerObjectClientValue::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext, object value)
0x25cf2  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25cf7  ldc.i4.0
0x25cf8  starg.s  2
0x25cfa  ldloc.3
0x25cfb  ldc.i4.1
0x25cfc  add
0x25cfd  stloc.3
0x25cfe  ldloc.3
0x25cff  ldarg.1
0x25d00  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25d05  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Count()
0x25d0a  blt      loc_25BBB
0x25d0f  ldarg.0
0x25d10  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x25d15  ldc.i4   0x3CE899
0x25d1a  ldc.i4.4
0x25d1b  ldstr    aIsleafsegment0// "isLeafSegment={0}, queryStringParameter"...
0x25d20  ldc.i4.3
0x25d21  newarr   [mscorlib]System.Object
0x25d26  stloc.s  0x10
0x25d28  ldloc.s  0x10
0x25d2a  ldc.i4.0
0x25d2b  ldarg.3
0x25d2c  box      [mscorlib]System.Boolean
0x25d31  stelem.ref
0x25d32  ldloc.s  0x10
0x25d34  ldc.i4.1
0x25d35  ldloc.1
0x25d36  box      [mscorlib]System.Boolean
0x25d3b  stelem.ref
0x25d3c  ldloc.s  0x10
0x25d3e  ldc.i4.2
0x25d3f  ldarg.s  4
0x25d41  box      [mscorlib]System.Boolean
0x25d46  stelem.ref
0x25d47  ldloc.s  0x10
0x25d49  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x25d4e  ldarg.3
0x25d4f  brfalse  loc_25E6B
0x25d54  ldloc.1
0x25d55  brtrue   loc_25E6B
0x25d5a  ldarg.s  4
0x25d5c  brtrue   loc_25E6B
0x25d61  ldc.i4.0
0x25d62  stloc.s  7
0x25d64  br       loc_25E59
0x25d69  ldarg.1
0x25d6a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25d6f  ldloc.s  7
0x25d71  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Item(!!T0)
0x25d76  stloc.s  8
0x25d78  ldarg.0
0x25d79  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_QueryStrings()
0x25d7e  ldloc.s  8
0x25d80  callvirt instance string Microsoft.SharePoint.Client.ParameterInformation::get_Name()
0x25d85  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25d8a  stloc.s  9
0x25d8c  ldloc.s  9
0x25d8e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x25d93  brtrue   loc_25E53
0x25d98  ldloc.s  8
0x25d9a  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.ParameterInformation::get_ParameterODataType()
0x25d9f  ldc.i4.1
0x25da0  bne.un.s loc_25DF6
0x25da2  ldloc.s  9
0x25da4  ldloc.s  9
0x25da6  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x25dab  stloc.s  0xB
0x25dad  ldloc.s  0xB
0x25daf  ldloca.s 0xA
0x25db1  callvirt instance bool Microsoft.SharePoint.Client.Rest.EdmExpressionParser::TryParseLiteral([out] class Microsoft.SharePoint.Client.Rest.EdmParserNode& node)
0x25db6  brtrue.s loc_25DDD
0x25db8  ldstr    aInvalidqueryst// "InvalidQueryString"
0x25dbd  ldc.i4.1
0x25dbe  newarr   [mscorlib]System.Object
0x25dc3  stloc.s  0x11
0x25dc5  ldloc.s  0x11
0x25dc7  ldc.i4.0
0x25dc8  ldloc.s  8
0x25dca  callvirt instance string Microsoft.SharePoint.Client.ParameterInformation::get_Name()
0x25dcf  stelem.ref
0x25dd0  ldloc.s  0x11
0x25dd2  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x25dd7  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x25ddc  throw
0x25ddd  ldarg.s  5
0x25ddf  ldloc.s  7
0x25de1  ldarg.0
0x25de2  ldarg.0
0x25de3  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25de8  ldloc.s  0xA
0x25dea  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmClientValue::.ctor(class Microsoft.SharePoint.Client.Rest.RestRequestProcessor requestProcessor, class Microsoft.SharePoint.Client.ProxyContext proxyContext, class Microsoft.SharePoint.Client.Rest.EdmParserNode edmParserNode)
0x25def  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25df4  br.s     loc_25E53
0x25df6  ldloc.s  8
0x25df8  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.ParameterInformation::get_ParameterODataType()
0x25dfd  ldc.i4.2
0x25dfe  beq.s    loc_25E0A
0x25e00  ldloc.s  8
0x25e02  callvirt instance valuetype Microsoft.SharePoint.Client.ODataType Microsoft.SharePoint.Client.ParameterInformation::get_ParameterODataType()
0x25e07  ldc.i4.3
0x25e08  bne.un.s loc_25E24
0x25e0a  ldarg.0
0x25e0b  ldarg.1
0x25e0c  ldloc.s  8
0x25e0e  ldloc.s  9
0x25e10  call     instance class Microsoft.SharePoint.Client.ClientValue Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParameterJsonValue(class Microsoft.SharePoint.Client.MethodInformation methodInfo, class Microsoft.SharePoint.Client.ParameterInformation parameterInfo, string parameterValue)
0x25e15  stloc.s  0xC
0x25e17  ldarg.s  5
0x25e19  ldloc.s  7
0x25e1b  ldloc.s  0xC
0x25e1d  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25e22  br.s     loc_25E53
0x25e24  ldstr    aNotsupportedme// "NotSupportedMethodParameterInQueryStrin"...
0x25e29  ldc.i4.2
0x25e2a  newarr   [mscorlib]System.Object
0x25e2f  stloc.s  0x12
0x25e31  ldloc.s  0x12
0x25e33  ldc.i4.0
0x25e34  ldloc.s  8
0x25e36  callvirt instance string Microsoft.SharePoint.Client.ParameterInformation::get_Name()
0x25e3b  stelem.ref
0x25e3c  ldloc.s  0x12
0x25e3e  ldc.i4.1
0x25e3f  ldarg.1
0x25e40  callvirt instance string Microsoft.SharePoint.Client.MethodInformation::get_Name()
0x25e45  stelem.ref
0x25e46  ldloc.s  0x12
0x25e48  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x25e4d  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x25e52  throw
0x25e53  ldloc.s  7
0x25e55  ldc.i4.1
0x25e56  add
0x25e57  stloc.s  7
0x25e59  ldloc.s  7
0x25e5b  ldarg.1
0x25e5c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25e61  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Count()
0x25e66  blt      loc_25D69
0x25e6b  ldarg.0
0x25e6c  ldarg.1
0x25e6d  ldarg.2
0x25e6e  ldarg.3
0x25e6f  ldarg.s  5
0x25e71  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBody(class Microsoft.SharePoint.Client.MethodInformation methodInfo, bool allowPostBodyAccess, bool isLeafSegment, class Microsoft.SharePoint.Client.ClientValueCollection args)
0x25e76  ret
```
