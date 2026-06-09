# Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId

- ea: `0xbc60`
- end: `0xbdea`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId`
- size: `394`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb2e0`
- `0xb440`
- `0xb620`
- `0xb6e0`
- `0xb770`
- `0xbc60`
- `0xc040`
- `0x150f0`

## callees

- `0x98e0`
- `0x9e40`
- `0xa9c0`
- `0xbc60`
- `0xbdf0`
- `0xc040`
- `0xe010`
- `0x12e20`
- `0x16f00`

## string_xrefs

- `0xbd0d`: `RequestXml: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xbc60  ldarg.0
0xbc61  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectMap
0xbc66  ldarg.1
0xbc67  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xbc6c  brfalse.s loc_BC7B
0xbc6e  ldarg.0
0xbc6f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectMap
0xbc74  ldarg.1
0xbc75  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xbc7a  ret
0xbc7b  ldarg.0
0xbc7c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectPathMap
0xbc81  ldarg.1
0xbc82  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement>::ContainsKey(var<u1>)
0xbc87  brtrue.s loc_BC99
0xbc89  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbc8e  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbc93  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbc98  throw
0xbc99  ldc.i4.0
0xbc9a  stloc.0
0xbc9b  ldarg.0
0xbc9c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToCalculateStartedMap
0xbca1  ldarg.1
0xbca2  ldloca.s 0
0xbca4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::TryGetValue(var<u1>, !!T0)
0xbca9  brfalse.s loc_BCBE
0xbcab  ldloc.0
0xbcac  brfalse.s loc_BCBE
0xbcae  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbcb3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbcb8  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbcbd  throw
0xbcbe  ldarg.0
0xbcbf  ldfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbcc4  ldc.i4.s 0xA
0xbcc6  ble.s    loc_BD3B
0xbcc8  ldarg.0
0xbcc9  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbcce  ldc.i4   0x810699
0xbcd3  ldc.i4.2
0xbcd4  ldstr    aRecursiveDepth// "Recursive depth exceeds the max value. "...
0xbcd9  ldc.i4.1
0xbcda  newarr   [mscorlib]System.Object
0xbcdf  stloc.s  6
0xbce1  ldloc.s  6
0xbce3  ldc.i4.0
0xbce4  ldarg.0
0xbce5  ldfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbcea  box      [mscorlib]System.Int32
0xbcef  stelem.ref
0xbcf0  ldloc.s  6
0xbcf2  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xbcf7  ldarg.0
0xbcf8  ldfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbcfd  ldc.i4.s 0xB
0xbcff  bne.un.s loc_BD2B
0xbd01  ldarg.0
0xbd02  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbd07  ldc.i4   0x81069A
0xbd0c  ldc.i4.2
0xbd0d  ldstr    aRequestxml0// "RequestXml: {0}"
0xbd12  ldc.i4.1
0xbd13  newarr   [mscorlib]System.Object
0xbd18  stloc.s  7
0xbd1a  ldloc.s  7
0xbd1c  ldc.i4.0
0xbd1d  ldarg.0
0xbd1e  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xbd23  stelem.ref
0xbd24  ldloc.s  7
0xbd26  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xbd2b  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbd30  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbd35  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbd3a  throw
0xbd3b  ldarg.0
0xbd3c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToCalculateStartedMap
0xbd41  ldarg.1
0xbd42  ldc.i4.1
0xbd43  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0xbd48  ldnull
0xbd49  stloc.1
0xbd4a  ldarg.0
0xbd4b  dup
0xbd4c  ldfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbd51  ldc.i4.1
0xbd52  add
0xbd53  stfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbd58  ldarg.0
0xbd59  ldarg.1
0xbd5a  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Client.ClientMethodsProcessor::GetUninitializedParentObjectPathIdsReverseOrder(string objectPathId)
0xbd5f  stloc.2
0xbd60  ldloc.2
0xbd61  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0xbd66  ldc.i4.1
0xbd67  sub
0xbd68  stloc.3
0xbd69  br.s     loc_BD7D
0xbd6b  ldarg.0
0xbd6c  ldloc.2
0xbd6d  ldloc.3
0xbd6e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0xbd73  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId(string objectPathId)
0xbd78  pop
0xbd79  ldloc.3
0xbd7a  ldc.i4.1
0xbd7b  sub
0xbd7c  stloc.3
0xbd7d  ldloc.3
0xbd7e  ldc.i4.0
0xbd7f  bge.s    loc_BD6B
0xbd81  ldarg.0
0xbd82  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectPathMap
0xbd87  ldarg.1
0xbd88  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement>::get_Item(void)
0xbd8d  stloc.s  4
0xbd8f  ldarg.0
0xbd90  ldloc.s  4
0xbd92  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPath(class [System.Xml]System.Xml.XmlElement xe)
0xbd97  stloc.1
0xbd98  ldloc.1
0xbd99  isinst   [mscorlib]System.IDisposable
0xbd9e  stloc.s  5
0xbda0  ldloc.s  5
0xbda2  brfalse.s loc_BDB1
0xbda4  ldarg.0
0xbda5  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pendingDisposableQueue
0xbdaa  ldloc.s  5
0xbdac  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0xbdb1  ldarg.0
0xbdb2  ldloc.1
0xbdb3  call     instance void Microsoft.SharePoint.Client.RequestProcessor::AddRequestedObject(object value)
0xbdb8  ldarg.0
0xbdb9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectMap
0xbdbe  ldarg.1
0xbdbf  ldloc.1
0xbdc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xbdc5  leave.s  loc_BDD7
0xbdc7  pop
0xbdc8  ldarg.0
0xbdc9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToCalculateStartedMap
0xbdce  ldarg.1
0xbdcf  ldc.i4.0
0xbdd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0xbdd5  rethrow
0xbdd7  leave.s  loc_BDE8
0xbdd9  ldarg.0
0xbdda  dup
0xbddb  ldfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbde0  ldc.i4.1
0xbde1  sub
0xbde2  stfld    int32 Microsoft.SharePoint.Client.ClientMethodsProcessor::m_getObjectDepth
0xbde7  endfinally
0xbde8  ldloc.1
0xbde9  ret
```
