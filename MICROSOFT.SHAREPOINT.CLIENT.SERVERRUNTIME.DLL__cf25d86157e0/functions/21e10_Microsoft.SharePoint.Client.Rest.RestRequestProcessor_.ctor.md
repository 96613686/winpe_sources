# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::.ctor

- ea: `0x21e10`
- end: `0x2211c`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::.ctor`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x206e0`
- `0x26d30`

## callees

- `0x4d50`
- `0x98e0`
- `0xe010`
- `0xe6a0`
- `0xebb0`
- `0xec00`
- `0xed50`
- `0x12e20`
- `0x14ba0`
- `0x16f10`
- `0x20100`
- `0x20240`
- `0x202f0`
- `0x21e10`
- `0x23e50`
- `0x29b00`
- `0x29b80`
- `0x29ba0`
- `0x29bc0`
- `0x29be0`
- `0x29c00`

## string_xrefs

- `0x21f48`: `DELETE`

## pseudocode

```c

```

## disassembly

```asm
0x21e10  ldarg.0
0x21e11  ldarg.2
0x21e12  ldarg.3
0x21e13  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::.ctor(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x21e18  ldarg.2
0x21e19  brtrue.s loc_21E26
0x21e1b  ldstr    aHost// "host"
0x21e20  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21e25  throw
0x21e26  ldarg.s  4
0x21e28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21e2d  brfalse.s loc_21E3A
0x21e2f  ldstr    aHttpmethod// "httpMethod"
0x21e34  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21e39  throw
0x21e3a  ldarg.s  0xB
0x21e3c  brtrue.s loc_21E49
0x21e3e  ldstr    aPendingdisposa// "pendingDisposableQueue"
0x21e43  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21e48  throw
0x21e49  ldarg.s  4
0x21e4b  ldarg.s  6
0x21e4d  ldarg.s  7
0x21e4f  ldarg.s  0xA
0x21e51  ldarg.1
0x21e52  newobj   instance void Microsoft.SharePoint.Client.RESTfulRequestInfo::.ctor(string method, string path, class [System]System.Collections.Specialized.NameValueCollection queryString, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, class [mscorlib]System.IO.Stream body)
0x21e57  stloc.0
0x21e58  ldarg.2
0x21e59  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler> Microsoft.SharePoint.Client.ClientServiceHost::get_RequestHandlers()
0x21e5e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler>::GetEnumerator()
0x21e63  stloc.s  5
0x21e65  br.s     loc_21ED3
0x21e67  ldloc.s  5
0x21e69  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler>::get_Current()
0x21e6e  stloc.2
0x21e6f  ldloc.2
0x21e70  ldloc.0
0x21e71  ldloca.s 1
0x21e73  callvirt instance bool Microsoft.SharePoint.Client.ClientServiceProcessingHandler::TryNormalizeRESTfulRequest(class Microsoft.SharePoint.Client.RESTfulRequestInfo originalRequest, [out] class Microsoft.SharePoint.Client.RESTfulRequestInfo& normalizedRequest)
0x21e78  brfalse.s loc_21ED3
0x21e7a  ldarg.0
0x21e7b  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x21e80  ldc.i4   0x64E5C9
0x21e85  ldc.i4.3
0x21e86  ldstr    aHandler0Normal// "Handler {0} normalized request"
0x21e8b  ldc.i4.1
0x21e8c  newarr   [mscorlib]System.Object
0x21e91  stloc.s  6
0x21e93  ldloc.s  6
0x21e95  ldc.i4.0
0x21e96  ldloc.2
0x21e97  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x21e9c  callvirt instance string [mscorlib]System.Type::get_FullName()
0x21ea1  stelem.ref
0x21ea2  ldloc.s  6
0x21ea4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x21ea9  ldloc.1
0x21eaa  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestInfo::get_Method()
0x21eaf  starg.s  4
0x21eb1  ldloc.1
0x21eb2  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestInfo::get_Path()
0x21eb7  starg.s  6
0x21eb9  ldloc.1
0x21eba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.RESTfulRequestInfo::get_QueryString()
0x21ebf  starg.s  7
0x21ec1  ldloc.1
0x21ec2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.RESTfulRequestInfo::get_Headers()
0x21ec7  starg.s  0xA
0x21ec9  ldloc.1
0x21eca  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.RESTfulRequestInfo::get_Body()
0x21ecf  starg.s  1
0x21ed1  br.s     loc_21EDC
0x21ed3  ldloc.s  5
0x21ed5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21eda  brtrue.s loc_21E67
0x21edc  leave.s  loc_21EEA
0x21ede  ldloc.s  5
0x21ee0  brfalse.s loc_21EE9
0x21ee2  ldloc.s  5
0x21ee4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21ee9  endfinally
0x21eea  ldarg.s  4
0x21eec  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x21ef1  starg.s  4
0x21ef3  ldarg.s  4
0x21ef5  ldstr    aMerge// "MERGE"
0x21efa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21eff  brfalse.s loc_21F08
0x21f01  ldstr    aPatch// "PATCH"
0x21f06  starg.s  4
0x21f08  ldarg.s  4
0x21f0a  ldstr    aGet_0// "GET"
0x21f0f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f14  brfalse  loc_21FAE
0x21f19  ldarg.s  4
0x21f1b  ldstr    aPost// "POST"
0x21f20  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f25  brfalse  loc_21FAE
0x21f2a  ldarg.s  4
0x21f2c  ldstr    aPut// "PUT"
0x21f31  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f36  brfalse.s loc_21FAE
0x21f38  ldarg.s  4
0x21f3a  ldstr    aPatch// "PATCH"
0x21f3f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f44  brfalse.s loc_21FAE
0x21f46  ldarg.s  4
0x21f48  ldstr    aDelete// "DELETE"
0x21f4d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f52  brfalse.s loc_21FAE
0x21f54  ldarg.s  4
0x21f56  ldstr    aHead// "HEAD"
0x21f5b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x21f60  brfalse.s loc_21FAE
0x21f62  ldarg.0
0x21f63  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x21f68  ldc.i4   0x1C50C5
0x21f6d  ldc.i4.2
0x21f6e  ldstr    aCannotHandleHt// "Cannot handle httpMethod {0}"
0x21f73  ldc.i4.1
0x21f74  newarr   [mscorlib]System.Object
0x21f79  stloc.s  7
0x21f7b  ldloc.s  7
0x21f7d  ldc.i4.0
0x21f7e  ldarg.s  4
0x21f80  stelem.ref
0x21f81  ldloc.s  7
0x21f83  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x21f88  ldstr    aResourcenotsup// "ResourceNotSupportHttpMethod"
0x21f8d  ldc.i4.2
0x21f8e  newarr   [mscorlib]System.Object
0x21f93  stloc.s  8
0x21f95  ldloc.s  8
0x21f97  ldc.i4.0
0x21f98  ldarg.s  6
0x21f9a  stelem.ref
0x21f9b  ldloc.s  8
0x21f9d  ldc.i4.1
0x21f9e  ldarg.s  4
0x21fa0  stelem.ref
0x21fa1  ldloc.s  8
0x21fa3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x21fa8  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x21fad  throw
0x21fae  ldarg.0
0x21faf  ldarg.s  4
0x21fb1  ldstr    aHead// "HEAD"
0x21fb6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21fbb  stfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_suppressEntityBody
0x21fc0  ldarg.0
0x21fc1  ldarg.1
0x21fc2  newobj   instance void Microsoft.SharePoint.Client.PeekableReadonlyStream::.ctor(class [mscorlib]System.IO.Stream stream)
0x21fc7  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_inputStream
0x21fcc  ldarg.0
0x21fcd  ldarg.2
0x21fce  stfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x21fd3  ldarg.0
0x21fd4  ldarg.s  4
0x21fd6  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x21fdb  ldarg.0
0x21fdc  ldarg.s  6
0x21fde  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x21fe3  ldarg.0
0x21fe4  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x21fe9  ldstr    asc_3FC68// "/"
0x21fee  ldc.i4.4
0x21fef  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x21ff4  brfalse.s loc_22008
0x21ff6  ldarg.0
0x21ff7  ldarg.0
0x21ff8  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x21ffd  ldc.i4.1
0x21ffe  callvirt instance string [mscorlib]System.String::Substring(int32)
0x22003  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x22008  ldarg.0
0x22009  ldarg.0
0x2200a  ldarg.0
0x2200b  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x22010  ldarg.2
0x22011  call     instance string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetNormalizedPath(string path, class Microsoft.SharePoint.Client.ClientServiceHost host)
0x22016  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_path
0x2201b  ldarg.0
0x2201c  ldarg.s  5
0x2201e  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_acceptHeaderValue
0x22023  ldarg.0
0x22024  ldarg.s  7
0x22026  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_queryStrings
0x2202b  ldarg.0
0x2202c  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_queryStrings
0x22031  brtrue.s loc_2203E
0x22033  ldarg.0
0x22034  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x22039  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_queryStrings
0x2203e  ldarg.0
0x2203f  ldarg.s  8
0x22041  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfMatch
0x22046  ldarg.0
0x22047  ldarg.s  9
0x22049  stfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_etagIfNoneMatch
0x2204e  ldarg.0
0x2204f  ldarg.s  0xB
0x22051  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_pendingDisposableQueue
0x22056  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x2205b  brfalse.s loc_2206D
0x2205d  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x22062  ldarg.0
0x22063  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22068  callvirt instance void Microsoft.SharePoint.Client.ClientServiceOperationContext::set_ProxyContext(class Microsoft.SharePoint.Client.ProxyContext value)
0x2206d  ldarg.0
0x2206e  newobj   instance void Microsoft.SharePoint.Utilities.ChunkStreamBuilder::.ctor()
0x22073  stfld    class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_sb
0x22078  ldarg.0
0x22079  ldarg.0
0x2207a  ldfld    class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_sb
0x2207f  newobj   instance void Microsoft.SharePoint.Client.Rest.OutputChunkStream::.ctor(class Microsoft.SharePoint.Utilities.ChunkStreamBuilder sb)
0x22084  stfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_outputStream
0x22089  ldarg.0
0x2208a  ldarg.s  0xA
0x2208c  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x22091  ldarg.0
0x22092  ldc.i4.0
0x22093  stfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_enforceDataValidation
0x22098  ldarg.0
0x22099  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x2209e  ldstr    aPrefer// "Prefer"
0x220a3  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x220a8  brfalse.s loc_2211B
0x220aa  ldarg.0
0x220ab  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x220b0  ldstr    aPrefer// "Prefer"
0x220b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x220ba  brfalse.s loc_2211B
0x220bc  ldarg.0
0x220bd  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x220c2  ldstr    aPrefer// "Prefer"
0x220c7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x220cc  ldc.i4.1
0x220cd  newarr   [mscorlib]System.Char
0x220d2  stloc.s  9
0x220d4  ldloc.s  9
0x220d6  ldc.i4.0
0x220d7  ldc.i4.s 0x2C
0x220d9  stelem.i2
0x220da  ldloc.s  9
0x220dc  ldc.i4.1
0x220dd  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x220e2  stloc.3
0x220e3  ldloc.3
0x220e4  stloc.s  0xA
0x220e6  ldc.i4.0
0x220e7  stloc.s  0xB
0x220e9  br.s     loc_22113
0x220eb  ldloc.s  0xA
0x220ed  ldloc.s  0xB
0x220ef  ldelem.ref
0x220f0  stloc.s  4
0x220f2  ldloc.s  4
0x220f4  callvirt instance string [mscorlib]System.String::Trim()
0x220f9  ldstr    aEnforceDataVal// "enforce-data-validation"
0x220fe  ldc.i4.5
0x220ff  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x22104  brfalse.s loc_2210D
0x22106  ldarg.0
0x22107  ldc.i4.1
0x22108  stfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_enforceDataValidation
0x2210d  ldloc.s  0xB
0x2210f  ldc.i4.1
0x22110  add
0x22111  stloc.s  0xB
0x22113  ldloc.s  0xB
0x22115  ldloc.s  0xA
0x22117  ldlen
0x22118  conv.i4
0x22119  blt.s    loc_220EB
0x2211b  ret
```
