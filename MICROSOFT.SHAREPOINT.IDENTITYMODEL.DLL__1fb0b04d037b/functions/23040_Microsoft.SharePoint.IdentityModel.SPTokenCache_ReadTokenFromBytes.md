# Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenFromBytes

- ea: `0x23040`
- end: `0x23166`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenFromBytes`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21ed0`
- `0x24e00`

## callees

- `0x23040`

## string_xrefs

- `0x23075`: `tokenValue`
- `0x230b8`: `tokenValue`
- `0x2305c`: `Token Cache:  The tokenValue is null. Stack: '{0}'.`
- `0x2309e`: `Token Cache:  The tokenValue is empty. Stack: '{0}'.`
- `0x230fe`: `Token Cache:  Successfully read tokenValue XML.`
- `0x23142`: `Token Cache:  Failed to read tokenValue XML. Exception: '{0}', Stack: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x23040  ldarg.1
0x23041  brtrue.s loc_23080
0x23043  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23048  ldc.i4.s 0xA
0x2304a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x2304f  stloc.0
0x23050  ldc.i4   0x20F88C
0x23055  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2305a  ldc.i4.s 0xA
0x2305c  ldstr    aTokenCacheTheT_0// "Token Cache:  The tokenValue is null. S"...
0x23061  ldc.i4.1
0x23062  newarr   [mscorlib]System.Object
0x23067  stloc.s  7
0x23069  ldloc.s  7
0x2306b  ldc.i4.0
0x2306c  ldloc.0
0x2306d  stelem.ref
0x2306e  ldloc.s  7
0x23070  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23075  ldstr    aTokenvalue// "tokenValue"
0x2307a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2307f  throw
0x23080  ldarg.1
0x23081  ldlen
0x23082  conv.i4
0x23083  brtrue.s loc_230C3
0x23085  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2308a  ldc.i4.s 0xA
0x2308c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x23091  stloc.1
0x23092  ldc.i4   0x20F88D
0x23097  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2309c  ldc.i4.s 0xA
0x2309e  ldstr    aTokenCacheTheT_1// "Token Cache:  The tokenValue is empty. "...
0x230a3  ldc.i4.1
0x230a4  newarr   [mscorlib]System.Object
0x230a9  stloc.s  8
0x230ab  ldloc.s  8
0x230ad  ldc.i4.0
0x230ae  ldloc.1
0x230af  stelem.ref
0x230b0  ldloc.s  8
0x230b2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x230b7  ldnull
0x230b8  ldstr    aTokenvalue// "tokenValue"
0x230bd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x230c2  throw
0x230c3  ldnull
0x230c4  stloc.2
0x230c5  ldarg.1
0x230c6  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_Max()
0x230cb  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateTextReader(unsigned int8[], class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x230d0  stloc.3
0x230d1  ldloc.3
0x230d2  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateDictionaryReader(class [System.Xml]System.Xml.XmlReader)
0x230d7  stloc.s  4
0x230d9  ldloc.s  4
0x230db  ldstr    aSp// "SP"
0x230e0  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string)
0x230e5  brfalse.s loc_23108
0x230e7  ldloc.s  4
0x230e9  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0x230ee  stloc.2
0x230ef  ldc.i4   0x15D681
0x230f4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x230f9  ldc.i4   0xC8
0x230fe  ldstr    aTokenCacheSucc_0// "Token Cache:  Successfully read tokenVa"...
0x23103  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23108  leave.s  loc_23116
0x2310a  ldloc.s  4
0x2310c  brfalse.s loc_23115
0x2310e  ldloc.s  4
0x23110  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23115  endfinally
0x23116  leave.s  loc_23122
0x23118  ldloc.3
0x23119  brfalse.s loc_23121
0x2311b  ldloc.3
0x2311c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23121  endfinally
0x23122  leave.s  loc_23164
0x23124  stloc.s  5
0x23126  ldloc.s  5
0x23128  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2312d  ldc.i4.s 0xA
0x2312f  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x23134  stloc.s  6
0x23136  ldc.i4   0x15D682
0x2313b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23140  ldc.i4.s 0xA
0x23142  ldstr    aTokenCacheFail_0// "Token Cache:  Failed to read tokenValue"...
0x23147  ldc.i4.2
0x23148  newarr   [mscorlib]System.Object
0x2314d  stloc.s  9
0x2314f  ldloc.s  9
0x23151  ldc.i4.0
0x23152  ldloc.s  5
0x23154  stelem.ref
0x23155  ldloc.s  9
0x23157  ldc.i4.1
0x23158  ldloc.s  6
0x2315a  stelem.ref
0x2315b  ldloc.s  9
0x2315d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23162  leave.s  loc_23164
0x23164  ldloc.2
0x23165  ret
```
