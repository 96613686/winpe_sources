# Microsoft.SharePoint.Client.ProxyMap::GetUrlPathPartitionedInfoFromAssembly

- ea: `0x16400`
- end: `0x16752`
- name: `Microsoft.SharePoint.Client.ProxyMap::GetUrlPathPartitionedInfoFromAssembly`
- size: `850`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x15ab0`
- `0x15ff0`
- `0x16310`

## callees

- `0xe010`
- `0x16400`
- `0x16d20`
- `0x16d30`
- `0x16d40`
- `0x16d60`
- `0x16d70`
- `0x16d80`
- `0x16d90`
- `0x16da0`
- `0x16db0`
- `0x16dc0`
- `0x16dd0`
- `0x16de0`
- `0x16df0`
- `0x16e00`
- `0x29c40`
- `0x29c50`
- `0x29c70`
- `0x29c90`

## string_xrefs

- `0x164ae`: `Partition={0}, Assembly={1}, EntityContainerFullName={2}, DefaultODataProtocolVersion={3}`
- `0x16565`: `Incompatible MetadataDocumentName between assemblies. Assembly {0} specifies MetadataDocumentName as '{1}'. Assembly {2} specifies MetadataDocumentName as '{3}'`
- `0x1660e`: `Incompatible EntityContainerFullName between assemblies. Assembly {0} specifies EntityCotnainerFullName as '{1}'. Assembly {2} specifies EntityContainerFullName as '{3}'`
- `0x16663`: `Assembly {0} specifies the DefaultODataProtocolVersion as '{1}'`
- `0x166b7`: `Incompatible DefaultODataProtocolVersion between assemblies. Assembly {0} specifies DefaultODataProtocolVersion as '{1}'. Assembly {2} specifies DefaultODataProtocolVersion as '{3}'`

## pseudocode

```c

```

## disassembly

```asm
0x16400  ldarg.0
0x16401  ldtoken  Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute
0x16406  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1640b  ldc.i4.0
0x1640c  callvirt instance object[] [mscorlib]System.Reflection.Assembly::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x16411  stloc.0
0x16412  ldsfld   string [mscorlib]System.String::Empty
0x16417  stloc.1
0x16418  ldsfld   string [mscorlib]System.String::Empty
0x1641d  stloc.2
0x1641e  ldsfld   string [mscorlib]System.String::Empty
0x16423  stloc.3
0x16424  ldc.i4.0
0x16425  stloc.s  4
0x16427  ldloc.0
0x16428  brfalse.s loc_16489
0x1642a  ldloc.0
0x1642b  stloc.s  7
0x1642d  ldc.i4.0
0x1642e  stloc.s  8
0x16430  br.s     loc_16481
0x16432  ldloc.s  7
0x16434  ldloc.s  8
0x16436  ldelem.ref
0x16437  castclass Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute
0x1643c  stloc.s  5
0x1643e  ldloc.s  5
0x16440  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute::get_Partition()
0x16445  stloc.1
0x16446  ldloc.1
0x16447  brtrue.s loc_1644F
0x16449  ldsfld   string [mscorlib]System.String::Empty
0x1644e  stloc.1
0x1644f  ldloc.s  5
0x16451  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute::get_EntityContainerFullName()
0x16456  stloc.2
0x16457  ldloc.2
0x16458  brtrue.s loc_16460
0x1645a  ldsfld   string [mscorlib]System.String::Empty
0x1645f  stloc.2
0x16460  ldloc.s  5
0x16462  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute::get_MetadataDocumentName()
0x16467  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1646c  brtrue.s loc_16476
0x1646e  ldloc.s  5
0x16470  callvirt instance string Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute::get_MetadataDocumentName()
0x16475  stloc.3
0x16476  ldloc.s  5
0x16478  callvirt instance valuetype Microsoft.SharePoint.Client.ODataProtocolVersion Microsoft.SharePoint.Client.RESTfulRequestPathPartitionAttribute::get_DefaultODataProtocolVersion()
0x1647d  stloc.s  4
0x1647f  br.s     loc_16489
0x16481  ldloc.s  8
0x16483  ldloc.s  7
0x16485  ldlen
0x16486  conv.i4
0x16487  blt.s    loc_16432
0x16489  ldloc.1
0x1648a  callvirt instance string [mscorlib]System.String::Trim()
0x1648f  stloc.1
0x16490  ldloc.1
0x16491  ldc.i4.1
0x16492  newarr   [mscorlib]System.Char
0x16497  stloc.s  9
0x16499  ldloc.s  9
0x1649b  ldc.i4.0
0x1649c  ldc.i4.s 0x2F
0x1649e  stelem.i2
0x1649f  ldloc.s  9
0x164a1  callvirt instance string [mscorlib]System.String::Trim(char[])
0x164a6  stloc.1
0x164a7  ldarg.1
0x164a8  ldc.i4   0x64C553
0x164ad  ldc.i4.3
0x164ae  ldstr    aPartition0Asse// "Partition={0}, Assembly={1}, EntityCont"...
0x164b3  ldc.i4.4
0x164b4  newarr   [mscorlib]System.Object
0x164b9  stloc.s  0xA
0x164bb  ldloc.s  0xA
0x164bd  ldc.i4.0
0x164be  ldloc.1
0x164bf  stelem.ref
0x164c0  ldloc.s  0xA
0x164c2  ldc.i4.1
0x164c3  ldarg.0
0x164c4  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x164c9  stelem.ref
0x164ca  ldloc.s  0xA
0x164cc  ldc.i4.2
0x164cd  ldloc.2
0x164ce  stelem.ref
0x164cf  ldloc.s  0xA
0x164d1  ldc.i4.3
0x164d2  ldloc.s  4
0x164d4  box      Microsoft.SharePoint.Client.ODataProtocolVersion
0x164d9  stelem.ref
0x164da  ldloc.s  0xA
0x164dc  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x164e1  ldloc.1
0x164e2  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x164e7  stloc.1
0x164e8  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class UrlPathPartitionedInfo> Microsoft.SharePoint.Client.ProxyMap::s_urlPathPartitionedInfoMap
0x164ed  ldloc.1
0x164ee  ldloca.s 6
0x164f0  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class UrlPathPartitionedInfo>::TryGetValue(var<u1>, !!T0)
0x164f5  brfalse  loc_16702
0x164fa  ldloc.3
0x164fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16500  brtrue   loc_165A3
0x16505  ldloc.s  6
0x16507  callvirt instance string UrlPathPartitionedInfo::get_MetadataDocumentName()
0x1650c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16511  brfalse.s loc_1654F
0x16513  ldarg.1
0x16514  ldc.i4   0x1006000
0x16519  ldc.i4.3
0x1651a  ldstr    aAssembly0Speci// "Assembly {0} specifies the MetadataDocu"...
0x1651f  ldc.i4.2
0x16520  newarr   [mscorlib]System.Object
0x16525  stloc.s  0xB
0x16527  ldloc.s  0xB
0x16529  ldc.i4.0
0x1652a  ldarg.0
0x1652b  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x16530  stelem.ref
0x16531  ldloc.s  0xB
0x16533  ldc.i4.1
0x16534  ldloc.3
0x16535  stelem.ref
0x16536  ldloc.s  0xB
0x16538  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1653d  ldloc.s  6
0x1653f  ldloc.3
0x16540  callvirt instance void UrlPathPartitionedInfo::set_MetadataDocumentName(string value)
0x16545  ldloc.s  6
0x16547  ldarg.0
0x16548  callvirt instance void UrlPathPartitionedInfo::set_AssemblyDefinesMetadataDocument(class [mscorlib]System.Reflection.Assembly value)
0x1654d  br.s     loc_165A3
0x1654f  ldloc.3
0x16550  ldloc.s  6
0x16552  callvirt instance string UrlPathPartitionedInfo::get_MetadataDocumentName()
0x16557  call     bool [mscorlib]System.String::Equals(string, string)
0x1655c  brtrue.s loc_165A3
0x1655e  ldarg.1
0x1655f  ldc.i4   0x1006001
0x16564  ldc.i4.1
0x16565  ldstr    aIncompatibleMe// "Incompatible MetadataDocumentName betwe"...
0x1656a  ldc.i4.4
0x1656b  newarr   [mscorlib]System.Object
0x16570  stloc.s  0xC
0x16572  ldloc.s  0xC
0x16574  ldc.i4.0
0x16575  ldloc.s  6
0x16577  callvirt instance class [mscorlib]System.Reflection.Assembly UrlPathPartitionedInfo::get_AssemblyDefinesMetadataDocument()
0x1657c  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x16581  stelem.ref
0x16582  ldloc.s  0xC
0x16584  ldc.i4.1
0x16585  ldloc.s  6
0x16587  callvirt instance string UrlPathPartitionedInfo::get_MetadataDocumentName()
0x1658c  stelem.ref
0x1658d  ldloc.s  0xC
0x1658f  ldc.i4.2
0x16590  ldarg.0
0x16591  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x16596  stelem.ref
0x16597  ldloc.s  0xC
0x16599  ldc.i4.3
0x1659a  ldloc.3
0x1659b  stelem.ref
0x1659c  ldloc.s  0xC
0x1659e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x165a3  ldloc.2
0x165a4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x165a9  brtrue   loc_1664C
0x165ae  ldloc.s  6
0x165b0  callvirt instance string UrlPathPartitionedInfo::get_EntityContainerFullName()
0x165b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x165ba  brfalse.s loc_165F8
0x165bc  ldarg.1
0x165bd  ldc.i4   0x6556D1
0x165c2  ldc.i4.3
0x165c3  ldstr    aAssembly0Speci_0// "Assembly {0} specifies the EntityContai"...
0x165c8  ldc.i4.2
0x165c9  newarr   [mscorlib]System.Object
0x165ce  stloc.s  0xD
0x165d0  ldloc.s  0xD
0x165d2  ldc.i4.0
0x165d3  ldarg.0
0x165d4  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x165d9  stelem.ref
0x165da  ldloc.s  0xD
0x165dc  ldc.i4.1
0x165dd  ldloc.2
0x165de  stelem.ref
0x165df  ldloc.s  0xD
0x165e1  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x165e6  ldloc.s  6
0x165e8  ldloc.2
0x165e9  callvirt instance void UrlPathPartitionedInfo::set_EntityContainerFullName(string value)
0x165ee  ldloc.s  6
0x165f0  ldarg.0
0x165f1  callvirt instance void UrlPathPartitionedInfo::set_AssemblyDefinesEntityContainerFullName(class [mscorlib]System.Reflection.Assembly value)
0x165f6  br.s     loc_1664C
0x165f8  ldloc.2
0x165f9  ldloc.s  6
0x165fb  callvirt instance string UrlPathPartitionedInfo::get_EntityContainerFullName()
0x16600  call     bool [mscorlib]System.String::Equals(string, string)
0x16605  brtrue.s loc_1664C
0x16607  ldarg.1
0x16608  ldc.i4   0x6556D2
0x1660d  ldc.i4.1
0x1660e  ldstr    aIncompatibleEn// "Incompatible EntityContainerFullName be"...
0x16613  ldc.i4.4
0x16614  newarr   [mscorlib]System.Object
0x16619  stloc.s  0xE
0x1661b  ldloc.s  0xE
0x1661d  ldc.i4.0
0x1661e  ldloc.s  6
0x16620  callvirt instance class [mscorlib]System.Reflection.Assembly UrlPathPartitionedInfo::get_AssemblyDefinesEntityContainerFullName()
0x16625  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1662a  stelem.ref
0x1662b  ldloc.s  0xE
0x1662d  ldc.i4.1
0x1662e  ldloc.s  6
0x16630  callvirt instance string UrlPathPartitionedInfo::get_EntityContainerFullName()
0x16635  stelem.ref
0x16636  ldloc.s  0xE
0x16638  ldc.i4.2
0x16639  ldarg.0
0x1663a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x1663f  stelem.ref
0x16640  ldloc.s  0xE
0x16642  ldc.i4.3
0x16643  ldloc.2
0x16644  stelem.ref
0x16645  ldloc.s  0xE
0x16647  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1664c  ldloc.s  4
0x1664e  brfalse  loc_1674F
0x16653  ldloc.s  6
0x16655  callvirt instance valuetype Microsoft.SharePoint.Client.ODataProtocolVersion UrlPathPartitionedInfo::get_DefaultODataProtocolVersion()
0x1665a  brtrue.s loc_166A2
0x1665c  ldarg.1
0x1665d  ldc.i4   0x65C84A
0x16662  ldc.i4.3
0x16663  ldstr    aAssembly0Speci_1// "Assembly {0} specifies the DefaultOData"...
0x16668  ldc.i4.2
0x16669  newarr   [mscorlib]System.Object
0x1666e  stloc.s  0xF
0x16670  ldloc.s  0xF
0x16672  ldc.i4.0
0x16673  ldarg.0
0x16674  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x16679  stelem.ref
0x1667a  ldloc.s  0xF
0x1667c  ldc.i4.1
0x1667d  ldloc.s  4
0x1667f  box      Microsoft.SharePoint.Client.ODataProtocolVersion
0x16684  stelem.ref
0x16685  ldloc.s  0xF
0x16687  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x1668c  ldloc.s  6
0x1668e  ldloc.s  4
0x16690  callvirt instance void UrlPathPartitionedInfo::set_DefaultODataProtocolVersion(valuetype Microsoft.SharePoint.Client.ODataProtocolVersion value)
0x16695  ldloc.s  6
0x16697  ldarg.0
0x16698  callvirt instance void UrlPathPartitionedInfo::set_AssemblyDefinesDefaultODataProtocolVersion(class [mscorlib]System.Reflection.Assembly value)
0x1669d  br       loc_1674F
0x166a2  ldloc.s  6
0x166a4  callvirt instance valuetype Microsoft.SharePoint.Client.ODataProtocolVersion UrlPathPartitionedInfo::get_DefaultODataProtocolVersion()
0x166a9  ldloc.s  4
0x166ab  beq      loc_1674F
0x166b0  ldarg.1
0x166b1  ldc.i4   0x65C84B
0x166b6  ldc.i4.1
0x166b7  ldstr    aIncompatibleDe// "Incompatible DefaultODataProtocolVersio"...
0x166bc  ldc.i4.4
0x166bd  newarr   [mscorlib]System.Object
0x166c2  stloc.s  0x10
0x166c4  ldloc.s  0x10
0x166c6  ldc.i4.0
0x166c7  ldloc.s  6
0x166c9  callvirt instance class [mscorlib]System.Reflection.Assembly UrlPathPartitionedInfo::get_AssemblyDefinesDefaultODataProtocolVersion()
0x166ce  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x166d3  stelem.ref
0x166d4  ldloc.s  0x10
0x166d6  ldc.i4.1
0x166d7  ldloc.s  6
0x166d9  callvirt instance valuetype Microsoft.SharePoint.Client.ODataProtocolVersion UrlPathPartitionedInfo::get_DefaultODataProtocolVersion()
0x166de  box      Microsoft.SharePoint.Client.ODataProtocolVersion
0x166e3  stelem.ref
0x166e4  ldloc.s  0x10
0x166e6  ldc.i4.2
0x166e7  ldarg.0
0x166e8  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x166ed  stelem.ref
0x166ee  ldloc.s  0x10
0x166f0  ldc.i4.3
0x166f1  ldloc.s  4
0x166f3  box      Microsoft.SharePoint.Client.ODataProtocolVersion
  ... truncated ...
```
