# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::EvaluatePreconditions

- ea: `0x23a20`
- end: `0x23c45`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::EvaluatePreconditions`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x222f0`

## callees

- `0xab0`
- `0x2c20`
- `0x98e0`
- `0xe010`
- `0xe930`
- `0xe940`
- `0xe9d0`
- `0x12440`
- `0x124d0`
- `0x124e0`
- `0x12e70`
- `0x16f10`
- `0x23a20`
- `0x23d20`
- `0x29560`
- `0x29590`
- `0x295b0`

## string_xrefs

- `0x23a56`: `DELETE`

## pseudocode

```c

```

## disassembly

```asm
0x23a20  ldarg.2
0x23a21  brtrue.s loc_23A26
0x23a23  ldc.i4.0
0x23a24  br.s     loc_23A2C
0x23a26  ldarg.2
0x23a27  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_TreatNoIfMatchAsWildcard()
0x23a2c  stloc.0
0x23a2d  ldarg.0
0x23a2e  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x23a33  dup
0x23a34  stloc.s  0xF
0x23a36  brfalse.s loc_23A91
0x23a38  ldloc.s  0xF
0x23a3a  ldstr    aGet_0// "GET"
0x23a3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23a44  brtrue.s loc_23A7F
0x23a46  ldloc.s  0xF
0x23a48  ldstr    aHead// "HEAD"
0x23a4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23a52  brtrue.s loc_23A7F
0x23a54  ldloc.s  0xF
0x23a56  ldstr    aDelete// "DELETE"
0x23a5b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23a60  brtrue.s loc_23A89
0x23a62  ldloc.s  0xF
0x23a64  ldstr    aPatch// "PATCH"
0x23a69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23a6e  brtrue.s loc_23A89
0x23a70  ldloc.s  0xF
0x23a72  ldstr    aPut// "PUT"
0x23a77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23a7c  brtrue.s loc_23A89
0x23a7e  ret
0x23a7f  ldc.i4   0x130
0x23a84  stloc.1
0x23a85  ldc.i4.1
0x23a86  stloc.0
0x23a87  br.s     loc_23A92
0x23a89  ldc.i4   0x19C
0x23a8e  stloc.1
0x23a8f  br.s     loc_23A92
0x23a91  ret
0x23a92  ldc.i4.0
0x23a93  stloc.2
0x23a94  ldc.i4.0
0x23a95  stloc.3
0x23a96  ldnull
0x23a97  stloc.s  4
0x23a99  ldnull
0x23a9a  stloc.s  5
0x23a9c  ldnull
0x23a9d  stloc.s  6
0x23a9f  ldarg.0
0x23aa0  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfMatch
0x23aa5  brfalse.s loc_23AF6
0x23aa7  ldarg.0
0x23aa8  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfMatch
0x23aad  ldstr    asc_4532A// "*"
0x23ab2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x23ab7  brfalse.s loc_23AF6
0x23ab9  ldarg.1
0x23aba  isinst   Microsoft.SharePoint.Client.IEntityTagComparer
0x23abf  stloc.s  8
0x23ac1  ldloc.s  8
0x23ac3  brfalse.s loc_23AF6
0x23ac5  ldc.i4.1
0x23ac6  stloc.3
0x23ac7  ldloc.s  8
0x23ac9  ldarg.0
0x23aca  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfMatch
0x23acf  ldloca.s 7
0x23ad1  callvirt instance bool Microsoft.SharePoint.Client.IEntityTagComparer::Matches(string currentETag, [out] string& expectedETag)
0x23ad6  ldc.i4.0
0x23ad7  ceq
0x23ad9  stloc.2
0x23ada  ldloc.2
0x23adb  brfalse.s loc_23AF6
0x23add  ldloc.s  7
0x23adf  stloc.s  4
0x23ae1  ldstr    aDidNotMatch// "did not match"
0x23ae6  stloc.s  5
0x23ae8  ldarg.0
0x23ae9  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfMatch
0x23aee  stloc.s  6
0x23af0  ldc.i4   0x19C
0x23af5  stloc.1
0x23af6  ldloc.3
0x23af7  brtrue.s loc_23B05
0x23af9  ldarg.2
0x23afa  brfalse.s loc_23B05
0x23afc  ldarg.0
0x23afd  ldarg.1
0x23afe  ldarg.2
0x23aff  ldloc.0
0x23b00  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::LegacyCheckETag(object entity, class Microsoft.SharePoint.Client.ServerStub serverStub, bool treatNoIfMatchAsWildcard)
0x23b05  ldloc.2
0x23b06  brtrue.s loc_23B7F
0x23b08  ldarg.0
0x23b09  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x23b0e  brfalse.s loc_23B7F
0x23b10  ldstr    aIrrelevant// "<irrelevant>"
0x23b15  stloc.s  9
0x23b17  ldarg.0
0x23b18  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x23b1d  ldstr    asc_4532A// "*"
0x23b22  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23b27  brfalse.s loc_23B2D
0x23b29  ldc.i4.1
0x23b2a  stloc.2
0x23b2b  br.s     loc_23B69
0x23b2d  ldarg.1
0x23b2e  isinst   Microsoft.SharePoint.Client.IEntityTagComparer
0x23b33  stloc.s  0xA
0x23b35  ldloc.s  0xA
0x23b37  brfalse.s loc_23B4B
0x23b39  ldloc.s  0xA
0x23b3b  ldarg.0
0x23b3c  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x23b41  ldloca.s 9
0x23b43  callvirt instance bool Microsoft.SharePoint.Client.IEntityTagComparer::Matches(string currentETag, [out] string& expectedETag)
0x23b48  stloc.2
0x23b49  br.s     loc_23B69
0x23b4b  ldarg.2
0x23b4c  brfalse.s loc_23B69
0x23b4e  ldarg.2
0x23b4f  ldarg.1
0x23b50  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x23b55  stloc.s  9
0x23b57  ldloc.s  9
0x23b59  brfalse.s loc_23B69
0x23b5b  ldarg.0
0x23b5c  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x23b61  ldloc.s  9
0x23b63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23b68  stloc.2
0x23b69  ldloc.2
0x23b6a  brfalse.s loc_23B7F
0x23b6c  ldloc.s  9
0x23b6e  stloc.s  4
0x23b70  ldstr    aMatched// "matched"
0x23b75  stloc.s  5
0x23b77  ldarg.0
0x23b78  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x23b7d  stloc.s  6
0x23b7f  ldloc.2
0x23b80  brfalse  loc_23C44
0x23b85  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x23b8a  stloc.s  0xB
0x23b8c  ldloc.s  0xB
0x23b8e  brfalse.s loc_23BA9
0x23b90  ldloc.s  0xB
0x23b92  ldnull
0x23b93  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_Location(class [System]System.Uri value)
0x23b98  ldloc.s  0xB
0x23b9a  ldloca.s 0x10
0x23b9c  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>
0x23ba2  ldloc.s  0x10
0x23ba4  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_StatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x23ba9  ldstr    aEtagnotmatch// "ETagNotMatch"
0x23bae  ldc.i4.2
0x23baf  newarr   [mscorlib]System.Object
0x23bb4  stloc.s  0x11
0x23bb6  ldloc.s  0x11
0x23bb8  ldc.i4.0
0x23bb9  ldloc.s  6
0x23bbb  stelem.ref
0x23bbc  ldloc.s  0x11
0x23bbe  ldc.i4.1
0x23bbf  ldloc.s  4
0x23bc1  stelem.ref
0x23bc2  ldloc.s  0x11
0x23bc4  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x23bc9  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x23bce  stloc.s  0xD
0x23bd0  ldloc.s  0xD
0x23bd2  newobj   instance void Microsoft.SharePoint.Client.ErrorInformation::.ctor()
0x23bd7  stloc.s  0xE
0x23bd9  ldloc.s  0xE
0x23bdb  ldloc.1
0x23bdc  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x23be1  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x23be6  ldloc.s  0xE
0x23be8  callvirt instance void Microsoft.SharePoint.Client.ClientServiceException::set_ErrorInformation(class Microsoft.SharePoint.Client.ErrorInformation value)
0x23bed  ldloc.s  0xD
0x23bef  stloc.s  0xC
0x23bf1  ldarg.0
0x23bf2  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x23bf7  ldc.i4   0x10D56E0
0x23bfc  ldc.i4.1
0x23bfd  ldstr    aTheEntityTag01// "The entity tag '{0}' {1} the actual ent"...
0x23c02  ldc.i4.4
0x23c03  newarr   [mscorlib]System.Object
0x23c08  stloc.s  0x12
0x23c0a  ldloc.s  0x12
0x23c0c  ldc.i4.0
0x23c0d  ldloc.s  6
0x23c0f  stelem.ref
0x23c10  ldloc.s  0x12
0x23c12  ldc.i4.1
0x23c13  ldloc.s  5
0x23c15  stelem.ref
0x23c16  ldloc.s  0x12
0x23c18  ldc.i4.2
0x23c19  ldloc.s  4
0x23c1b  stelem.ref
0x23c1c  ldloc.s  0x12
0x23c1e  ldc.i4.3
0x23c1f  ldloc.s  0xC
0x23c21  callvirt instance class Microsoft.SharePoint.Client.ErrorInformation Microsoft.SharePoint.Client.ClientServiceException::get_ErrorInformation()
0x23c26  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0x23c2b  stloc.s  0x13
0x23c2d  ldloca.s 0x13
0x23c2f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::GetValueOrDefault()
0x23c34  box      [System]System.Net.HttpStatusCode
0x23c39  stelem.ref
0x23c3a  ldloc.s  0x12
0x23c3c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x23c41  ldloc.s  0xC
0x23c43  throw
0x23c44  ret
```
