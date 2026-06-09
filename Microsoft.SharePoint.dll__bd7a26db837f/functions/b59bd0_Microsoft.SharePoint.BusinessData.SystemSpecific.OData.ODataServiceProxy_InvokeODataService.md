# Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataServiceProxy::InvokeODataService

- ea: `0xb59bd0`
- end: `0xb5a04d`
- name: `Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataServiceProxy::InvokeODataService`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0xb59860`

## callees

- `0x93dae0`
- `0x9582b0`
- `0xb58ac0`
- `0xb58be0`
- `0xb58c50`
- `0xb58c70`
- `0xb59bd0`
- `0xb5a050`
- `0xb5a930`
- `0xb5bf80`

## string_xrefs

- `0xb59e5c`: `application/xml`
- `0xb59ead`: `application/xml`
- `0xb59eee`: `application/xml`
- `0xb59f10`: `application/xml`
- `0xb59f61`: `application/xml`
- `0xb59d2c`: `DELETE`
- `0xb59ed2`: `DELETE`
- `0xb59fd0`: `DELETE`
- `0xb59cd6`: `application/atom+xml`
- `0xb59d1d`: `application/atom+xml`
- `0xb59d4d`: `application/atom+xml`
- `0xb59d6f`: `application/atom+xml`
- `0xb59d91`: `application/atom+xml`
- `0xb59de2`: `application/atom+xml`
- `0xb59e0b`: `application/atom+xml`
- `0xb5a00c`: `application/atom+xml`
- `0xb59c22`: `ODataSystemProxy::InvokeODataService for BDC Stereotype : {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb59bd0  ldnull
0xb59bd1  stloc.0
0xb59bd2  ldarg.2
0xb59bd3  callvirt instance valuetype [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance::get_MethodInstanceType()
0xb59bd8  stloc.1
0xb59bd9  ldsfld   string [mscorlib]System.String::Empty
0xb59bde  stloc.2
0xb59bdf  ldc.i4.0
0xb59be0  stloc.3
0xb59be1  ldc.i4.1
0xb59be2  stloc.s  4
0xb59be4  ldc.i4.0
0xb59be5  stloc.s  5
0xb59be7  ldc.i4.0
0xb59be8  stloc.s  6
0xb59bea  ldarg.2
0xb59beb  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance::GetMethod()
0xb59bf0  stloc.s  7
0xb59bf2  ldloc.s  7
0xb59bf4  call     string Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetODataFormat(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method)
0xb59bf9  stloc.s  8
0xb59bfb  ldloc.s  8
0xb59bfd  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xb59c02  brfalse.s loc_B59C16
0xb59c04  ldarg.0
0xb59c05  ldfld    class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ILobSystemInstance Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataServiceProxy::lobSystemInstance
0xb59c0a  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.INamedPropertyDictionary [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject::GetProperties()
0xb59c0f  call     string Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataSystemPropertyParser::GetODataFormat(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.INamedPropertyDictionary lobSystemProperties)
0xb59c14  stloc.s  8
0xb59c16  ldc.i4   0x148D2
0xb59c1b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb59c20  ldc.i4.s 0x32
0xb59c22  ldstr    aOdatasystempro_2// "ODataSystemProxy::InvokeODataService fo"...
0xb59c27  ldc.i4.1
0xb59c28  newarr   [mscorlib]System.Object
0xb59c2d  stloc.s  0xA
0xb59c2f  ldloc.s  0xA
0xb59c31  ldc.i4.0
0xb59c32  ldloc.1
0xb59c33  box      [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.MethodInstanceType
0xb59c38  callvirt instance string [mscorlib]System.Object::ToString()
0xb59c3d  stelem.ref
0xb59c3e  ldloc.s  0xA
0xb59c40  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xb59c45  ldloc.1
0xb59c46  stloc.s  0xB
0xb59c48  ldloc.s  0xB
0xb59c4a  ldc.i4.1
0xb59c4b  sub
0xb59c4c  switch   loc_B59D7E, loc_B59D5C, loc_B5A031, loc_B59F9F, loc_B59DF8, loc_B59EFD, loc_B59F9F, loc_B59CBE, loc_B59CE5, loc_B59D2C, loc_B59E49, loc_B59E49, loc_B59DCF, loc_B59E9A, loc_B59EBC, loc_B59D3A, loc_B59F4E, loc_B5A031, loc_B5A031, loc_B5A02E, loc_B5A031, loc_B5A02E, loc_B5A02E, loc_B5A02E, loc_B59F9F, loc_B59F9F
0xb59cb9  br       loc_B5A031
0xb59cbe  ldstr    aPost// "POST"
0xb59cc3  stloc.2
0xb59cc4  ldc.i4.1
0xb59cc5  stloc.3
0xb59cc6  ldc.i4.0
0xb59cc7  stloc.s  4
0xb59cc9  ldloc.s  8
0xb59ccb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59cd0  brtrue.s loc_B59CD6
0xb59cd2  ldloc.s  8
0xb59cd4  br.s     loc_B59CDB
0xb59cd6  ldstr    aApplicationAto// "application/atom+xml"
0xb59cdb  stloc.s  8
0xb59cdd  ldc.i4.1
0xb59cde  stloc.s  6
0xb59ce0  br       loc_B5A031
0xb59ce5  ldloc.s  7
0xb59ce7  ldc.i4.2
0xb59ce8  newarr   [mscorlib]System.String
0xb59ced  stloc.s  0xC
0xb59cef  ldloc.s  0xC
0xb59cf1  ldc.i4.0
0xb59cf2  ldstr    aPut_0// "PUT"
0xb59cf7  stelem.ref
0xb59cf8  ldloc.s  0xC
0xb59cfa  ldc.i4.1
0xb59cfb  ldstr    aMerge_1// "MERGE"
0xb59d00  stelem.ref
0xb59d01  ldloc.s  0xC
0xb59d03  ldstr    aPut_0// "PUT"
0xb59d08  call     string Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetHttpMethod(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, string[] allowedMethods, [opt] string defaultMethod)
0xb59d0d  stloc.2
0xb59d0e  ldc.i4.1
0xb59d0f  stloc.3
0xb59d10  ldloc.s  8
0xb59d12  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59d17  brtrue.s loc_B59D1D
0xb59d19  ldloc.s  8
0xb59d1b  br.s     loc_B59D22
0xb59d1d  ldstr    aApplicationAto// "application/atom+xml"
0xb59d22  stloc.s  8
0xb59d24  ldc.i4.0
0xb59d25  stloc.s  6
0xb59d27  br       loc_B5A031
0xb59d2c  ldstr    aDelete_0// "DELETE"
0xb59d31  stloc.2
0xb59d32  ldc.i4.0
0xb59d33  stloc.s  6
0xb59d35  br       loc_B5A031
0xb59d3a  ldstr    aGet// "GET"
0xb59d3f  stloc.2
0xb59d40  ldloc.s  8
0xb59d42  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59d47  brtrue.s loc_B59D4D
0xb59d49  ldloc.s  8
0xb59d4b  br.s     loc_B59D52
0xb59d4d  ldstr    aApplicationAto// "application/atom+xml"
0xb59d52  stloc.s  8
0xb59d54  ldc.i4.6
0xb59d55  stloc.s  6
0xb59d57  br       loc_B5A031
0xb59d5c  ldstr    aGet// "GET"
0xb59d61  stloc.2
0xb59d62  ldloc.s  8
0xb59d64  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59d69  brtrue.s loc_B59D6F
0xb59d6b  ldloc.s  8
0xb59d6d  br.s     loc_B59D74
0xb59d6f  ldstr    aApplicationAto// "application/atom+xml"
0xb59d74  stloc.s  8
0xb59d76  ldc.i4.1
0xb59d77  stloc.s  6
0xb59d79  br       loc_B5A031
0xb59d7e  ldstr    aGet// "GET"
0xb59d83  stloc.2
0xb59d84  ldloc.s  8
0xb59d86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59d8b  brtrue.s loc_B59D91
0xb59d8d  ldloc.s  8
0xb59d8f  br.s     loc_B59D96
0xb59d91  ldstr    aApplicationAto// "application/atom+xml"
0xb59d96  stloc.s  8
0xb59d98  ldloc.s  7
0xb59d9a  ldc.i4.2
0xb59d9b  ldc.i4.2
0xb59d9c  newarr   [mscorlib]System.String
0xb59da1  stloc.s  0xD
0xb59da3  ldloc.s  0xD
0xb59da5  ldc.i4.0
0xb59da6  ldc.i4.2
0xb59da7  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59dac  callvirt instance string [mscorlib]System.Object::ToString()
0xb59db1  stelem.ref
0xb59db2  ldloc.s  0xD
0xb59db4  ldc.i4.1
0xb59db5  ldc.i4.5
0xb59db6  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59dbb  callvirt instance string [mscorlib]System.Object::ToString()
0xb59dc0  stelem.ref
0xb59dc1  ldloc.s  0xD
0xb59dc3  call     valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetPayloadKind(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind defaultKind, string[] allowedKind)
0xb59dc8  stloc.s  6
0xb59dca  br       loc_B5A031
0xb59dcf  ldstr    aGet// "GET"
0xb59dd4  stloc.2
0xb59dd5  ldloc.s  8
0xb59dd7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59ddc  brtrue.s loc_B59DE2
0xb59dde  ldloc.s  8
0xb59de0  br.s     loc_B59DE7
0xb59de2  ldstr    aApplicationAto// "application/atom+xml"
0xb59de7  stloc.s  8
0xb59de9  ldarg.0
0xb59dea  ldarg.s  5
0xb59dec  call     instance valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataServiceProxy::GetAssociationPayloadKind(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter returnParameter)
0xb59df1  stloc.s  6
0xb59df3  br       loc_B5A031
0xb59df8  ldstr    aGet// "GET"
0xb59dfd  stloc.2
0xb59dfe  ldloc.s  8
0xb59e00  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59e05  brtrue.s loc_B59E0B
0xb59e07  ldloc.s  8
0xb59e09  br.s     loc_B59E10
0xb59e0b  ldstr    aApplicationAto// "application/atom+xml"
0xb59e10  stloc.s  8
0xb59e12  ldloc.s  7
0xb59e14  ldc.i4.2
0xb59e15  ldc.i4.2
0xb59e16  newarr   [mscorlib]System.String
0xb59e1b  stloc.s  0xE
0xb59e1d  ldloc.s  0xE
0xb59e1f  ldc.i4.0
0xb59e20  ldc.i4.2
0xb59e21  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59e26  callvirt instance string [mscorlib]System.Object::ToString()
0xb59e2b  stelem.ref
0xb59e2c  ldloc.s  0xE
0xb59e2e  ldc.i4.1
0xb59e2f  ldc.i4.5
0xb59e30  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59e35  callvirt instance string [mscorlib]System.Object::ToString()
0xb59e3a  stelem.ref
0xb59e3b  ldloc.s  0xE
0xb59e3d  call     valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetPayloadKind(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind defaultKind, string[] allowedKind)
0xb59e42  stloc.s  6
0xb59e44  br       loc_B5A031
0xb59e49  ldstr    aGet// "GET"
0xb59e4e  stloc.2
0xb59e4f  ldloc.s  8
0xb59e51  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59e56  brtrue.s loc_B59E5C
0xb59e58  ldloc.s  8
0xb59e5a  br.s     loc_B59E61
0xb59e5c  ldstr    aApplicationXml// "application/xml"
0xb59e61  stloc.s  8
0xb59e63  ldloc.s  7
0xb59e65  ldc.i4.5
0xb59e66  ldc.i4.2
0xb59e67  newarr   [mscorlib]System.String
0xb59e6c  stloc.s  0xF
0xb59e6e  ldloc.s  0xF
0xb59e70  ldc.i4.0
0xb59e71  ldc.i4.2
0xb59e72  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59e77  callvirt instance string [mscorlib]System.Object::ToString()
0xb59e7c  stelem.ref
0xb59e7d  ldloc.s  0xF
0xb59e7f  ldc.i4.1
0xb59e80  ldc.i4.5
0xb59e81  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59e86  callvirt instance string [mscorlib]System.Object::ToString()
0xb59e8b  stelem.ref
0xb59e8c  ldloc.s  0xF
0xb59e8e  call     valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetPayloadKind(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind defaultKind, string[] allowedKind)
0xb59e93  stloc.s  6
0xb59e95  br       loc_B5A031
0xb59e9a  ldstr    aPost// "POST"
0xb59e9f  stloc.2
0xb59ea0  ldloc.s  8
0xb59ea2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59ea7  brtrue.s loc_B59EAD
0xb59ea9  ldloc.s  8
0xb59eab  br.s     loc_B59EB2
0xb59ead  ldstr    aApplicationXml// "application/xml"
0xb59eb2  stloc.s  8
0xb59eb4  ldc.i4.0
0xb59eb5  stloc.s  6
0xb59eb7  br       loc_B5A031
0xb59ebc  ldloc.s  7
0xb59ebe  ldc.i4.2
0xb59ebf  newarr   [mscorlib]System.String
0xb59ec4  stloc.s  0x10
0xb59ec6  ldloc.s  0x10
0xb59ec8  ldc.i4.0
0xb59ec9  ldstr    aPost// "POST"
0xb59ece  stelem.ref
0xb59ecf  ldloc.s  0x10
0xb59ed1  ldc.i4.1
0xb59ed2  ldstr    aDelete_0// "DELETE"
0xb59ed7  stelem.ref
0xb59ed8  ldloc.s  0x10
0xb59eda  ldnull
0xb59edb  call     string Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetHttpMethod(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, string[] allowedMethods, [opt] string defaultMethod)
0xb59ee0  stloc.2
0xb59ee1  ldloc.s  8
0xb59ee3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59ee8  brtrue.s loc_B59EEE
0xb59eea  ldloc.s  8
0xb59eec  br.s     loc_B59EF3
0xb59eee  ldstr    aApplicationXml// "application/xml"
0xb59ef3  stloc.s  8
0xb59ef5  ldc.i4.0
0xb59ef6  stloc.s  6
0xb59ef8  br       loc_B5A031
0xb59efd  ldstr    aGet// "GET"
0xb59f02  stloc.2
0xb59f03  ldloc.s  8
0xb59f05  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb59f0a  brtrue.s loc_B59F10
0xb59f0c  ldloc.s  8
0xb59f0e  br.s     loc_B59F15
0xb59f10  ldstr    aApplicationXml// "application/xml"
0xb59f15  stloc.s  8
0xb59f17  ldloc.s  7
0xb59f19  ldc.i4.4
0xb59f1a  ldc.i4.2
0xb59f1b  newarr   [mscorlib]System.String
0xb59f20  stloc.s  0x11
0xb59f22  ldloc.s  0x11
0xb59f24  ldc.i4.0
0xb59f25  ldc.i4.4
0xb59f26  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59f2b  callvirt instance string [mscorlib]System.Object::ToString()
0xb59f30  stelem.ref
0xb59f31  ldloc.s  0x11
0xb59f33  ldc.i4.1
0xb59f34  ldc.i4.3
0xb59f35  box      Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind
0xb59f3a  callvirt instance string [mscorlib]System.Object::ToString()
0xb59f3f  stelem.ref
0xb59f40  ldloc.s  0x11
0xb59f42  call     valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind Microsoft.SharePoint.BusinessData.SystemSpecific.OData.ODataMethodPropertyParser::GetPayloadKind(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethod method, valuetype Microsoft.SharePoint.BusinessData.SystemSpecific.OData.PayloadKind defaultKind, string[] allowedKind)
0xb59f47  stloc.s  6
0xb59f49  br       loc_B5A031
0xb59f4e  ldstr    aGet// "GET"
0xb59f53  stloc.2
0xb59f54  ldloc.s  8
0xb59f56  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
  ... truncated ...
```
