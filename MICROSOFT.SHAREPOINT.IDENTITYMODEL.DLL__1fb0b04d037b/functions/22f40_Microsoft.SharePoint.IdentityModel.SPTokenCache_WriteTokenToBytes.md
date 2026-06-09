# Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenToBytes

- ea: `0x22f40`
- end: `0x23040`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenToBytes`
- size: `256`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22f20`
- `0x24840`
- `0x25570`

## callees

- `0x22f40`

## string_xrefs

- `0x22f5c`: `Token Cache: The tokenValue is null. Stack: '{0}'.`
- `0x22f75`: `tokenValue`
- `0x22fe6`: `Token Cache: Successfully wrote token XML.`
- `0x2301c`: `Token Cache:  Failed to read token XML. Exception: '{0}', Stack: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x22f40  ldarg.1
0x22f41  brtrue.s loc_22F80
0x22f43  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22f48  ldc.i4.s 0xA
0x22f4a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x22f4f  stloc.0
0x22f50  ldc.i4   0x20F88B
0x22f55  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22f5a  ldc.i4.s 0xA
0x22f5c  ldstr    aTokenCacheTheT// "Token Cache: The tokenValue is null. St"...
0x22f61  ldc.i4.1
0x22f62  newarr   [mscorlib]System.Object
0x22f67  stloc.s  7
0x22f69  ldloc.s  7
0x22f6b  ldc.i4.0
0x22f6c  ldloc.0
0x22f6d  stelem.ref
0x22f6e  ldloc.s  7
0x22f70  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x22f75  ldstr    aTokenvalue// "tokenValue"
0x22f7a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22f7f  throw
0x22f80  ldnull
0x22f81  stloc.1
0x22f82  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x22f87  stloc.2
0x22f88  ldloc.2
0x22f89  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream)
0x22f8e  stloc.3
0x22f8f  ldloc.3
0x22f90  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::CreateDictionaryWriter(class [System.Xml]System.Xml.XmlWriter)
0x22f95  stloc.s  4
0x22f97  ldloc.s  4
0x22f99  ldstr    aSp// "SP"
0x22f9e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x22fa3  ldloc.s  4
0x22fa5  ldarg.1
0x22fa6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x22fab  ldloc.s  4
0x22fad  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x22fb2  ldloc.s  4
0x22fb4  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x22fb9  leave.s  loc_22FC7
0x22fbb  ldloc.s  4
0x22fbd  brfalse.s loc_22FC6
0x22fbf  ldloc.s  4
0x22fc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22fc6  endfinally
0x22fc7  leave.s  loc_22FD3
0x22fc9  ldloc.3
0x22fca  brfalse.s loc_22FD2
0x22fcc  ldloc.3
0x22fcd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22fd2  endfinally
0x22fd3  ldloc.2
0x22fd4  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x22fd9  stloc.1
0x22fda  ldc.i4   0x15D663
0x22fdf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x22fe4  ldc.i4.s 0x64
0x22fe6  ldstr    aTokenCacheSucc// "Token Cache: Successfully wrote token X"...
0x22feb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x22ff0  leave.s  loc_22FFC
0x22ff2  ldloc.2
0x22ff3  brfalse.s loc_22FFB
0x22ff5  ldloc.2
0x22ff6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22ffb  endfinally
0x22ffc  leave.s  loc_2303E
0x22ffe  stloc.s  5
0x23000  ldloc.s  5
0x23002  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23007  ldc.i4.s 0xA
0x23009  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x2300e  stloc.s  6
0x23010  ldc.i4   0x15D680
0x23015  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2301a  ldc.i4.s 0xA
0x2301c  ldstr    aTokenCacheFail// "Token Cache:  Failed to read token XML."...
0x23021  ldc.i4.2
0x23022  newarr   [mscorlib]System.Object
0x23027  stloc.s  8
0x23029  ldloc.s  8
0x2302b  ldc.i4.0
0x2302c  ldloc.s  5
0x2302e  stelem.ref
0x2302f  ldloc.s  8
0x23031  ldc.i4.1
0x23032  ldloc.s  6
0x23034  stelem.ref
0x23035  ldloc.s  8
0x23037  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2303c  leave.s  loc_2303E
0x2303e  ldloc.1
0x2303f  ret
```
