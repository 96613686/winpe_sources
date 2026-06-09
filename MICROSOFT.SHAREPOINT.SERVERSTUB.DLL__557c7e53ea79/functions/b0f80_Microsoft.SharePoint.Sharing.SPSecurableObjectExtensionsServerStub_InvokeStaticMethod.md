# Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::InvokeStaticMethod

- ea: `0xb0f80`
- end: `0xb1173`
- name: `Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::InvokeStaticMethod`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xb0c80`
- `0xb0cb0`
- `0xb0ce0`
- `0xb0d10`
- `0xb0dd0`
- `0xb0e20`
- `0xb0e50`
- `0xb0ef0`
- `0xb0f10`
- `0xb0f40`
- `0xb0f80`

## string_xrefs

- `0xb0fe4`: `ForwardObjectLink`
- `0xb10df`: `ForwardObjectLink`
- `0xb0ffc`: `UpdateDocumentSharingInfo`
- `0xb110f`: `UpdateDocumentSharingInfo`
- `0xb0fb4`: `ShareLink`
- `0xb107f`: `ShareLink`
- `0xb1014`: `DeleteLinkByKind`
- `0xb113f`: `DeleteLinkByKind`
- `0xb1020`: `UnshareLink`
- `0xb1158`: `UnshareLink`

## pseudocode

```c

```

## disassembly

```asm
0xb0f80  ldarg.3
0xb0f81  brtrue.s loc_B0F8E
0xb0f83  ldstr    aProxycontext// "proxyContext"
0xb0f88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb0f8d  throw
0xb0f8e  ldarg.0
0xb0f8f  ldarg.1
0xb0f90  ldarg.3
0xb0f91  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0f96  starg.s  1
0xb0f98  ldarg.1
0xb0f99  dup
0xb0f9a  stloc.0
0xb0f9b  brfalse  loc_B116C
0xb0fa0  volatile.
0xb0fa2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cd6-1
0xb0fa7  brtrue   loc_B1033
0xb0fac  ldc.i4.s 0xA
0xb0fae  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb0fb3  dup
0xb0fb4  ldstr    aSharelink// "ShareLink"
0xb0fb9  ldc.i4.0
0xb0fba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0fbf  dup
0xb0fc0  ldstr    aCheckpermissio_0// "CheckPermissions"
0xb0fc5  ldc.i4.1
0xb0fc6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0fcb  dup
0xb0fcc  ldstr    aGetsharinginfo// "GetSharingInformation"
0xb0fd1  ldc.i4.2
0xb0fd2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0fd7  dup
0xb0fd8  ldstr    aShareobject// "ShareObject"
0xb0fdd  ldc.i4.3
0xb0fde  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0fe3  dup
0xb0fe4  ldstr    aForwardobjectl// "ForwardObjectLink"
0xb0fe9  ldc.i4.4
0xb0fea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0fef  dup
0xb0ff0  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0xb0ff5  ldc.i4.5
0xb0ff6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0ffb  dup
0xb0ffc  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb1001  ldc.i4.6
0xb1002  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1007  dup
0xb1008  ldstr    aUnshareobject// "UnshareObject"
0xb100d  ldc.i4.7
0xb100e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb1013  dup
0xb1014  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0xb1019  ldc.i4.8
0xb101a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb101f  dup
0xb1020  ldstr    aUnsharelink// "UnshareLink"
0xb1025  ldc.i4.s 9
0xb1027  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb102c  volatile.
0xb102e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cd6-1
0xb1033  volatile.
0xb1035  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cd6-1
0xb103a  ldloc.0
0xb103b  ldloca.s 1
0xb103d  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb1042  brfalse  loc_B116C
0xb1047  ldloc.1
0xb1048  switch   loc_B107A, loc_B1092, loc_B10AA, loc_B10C2, loc_B10DA, loc_B10F2, loc_B110A, loc_B1122, loc_B113A, loc_B1153
0xb1075  br       loc_B116C
0xb107a  ldarg.s  4
0xb107c  ldc.i4.0
0xb107d  stind.i1
0xb107e  ldarg.0
0xb107f  ldstr    aSharelink// "ShareLink"
0xb1084  ldarg.3
0xb1085  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb108a  ldarg.2
0xb108b  ldarg.3
0xb108c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.ShareLinkResponse Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ShareLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1091  ret
0xb1092  ldarg.s  4
0xb1094  ldc.i4.0
0xb1095  stind.i1
0xb1096  ldarg.0
0xb1097  ldstr    aCheckpermissio_0// "CheckPermissions"
0xb109c  ldarg.3
0xb109d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb10a2  ldarg.2
0xb10a3  ldarg.3
0xb10a4  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.EntityPermission> Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::CheckPermissions_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb10a9  ret
0xb10aa  ldarg.s  4
0xb10ac  ldc.i4.0
0xb10ad  stind.i1
0xb10ae  ldarg.0
0xb10af  ldstr    aGetsharinginfo// "GetSharingInformation"
0xb10b4  ldarg.3
0xb10b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb10ba  ldarg.2
0xb10bb  ldarg.3
0xb10bc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::GetSharingInformation_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb10c1  ret
0xb10c2  ldarg.s  4
0xb10c4  ldc.i4.0
0xb10c5  stind.i1
0xb10c6  ldarg.0
0xb10c7  ldstr    aShareobject// "ShareObject"
0xb10cc  ldarg.3
0xb10cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb10d2  ldarg.2
0xb10d3  ldarg.3
0xb10d4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ShareObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb10d9  ret
0xb10da  ldarg.s  4
0xb10dc  ldc.i4.0
0xb10dd  stind.i1
0xb10de  ldarg.0
0xb10df  ldstr    aForwardobjectl// "ForwardObjectLink"
0xb10e4  ldarg.3
0xb10e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb10ea  ldarg.2
0xb10eb  ldarg.3
0xb10ec  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::ForwardObjectLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb10f1  ret
0xb10f2  ldarg.s  4
0xb10f4  ldc.i4.0
0xb10f5  stind.i1
0xb10f6  ldarg.0
0xb10f7  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0xb10fc  ldarg.3
0xb10fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1102  ldarg.2
0xb1103  ldarg.3
0xb1104  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::GetObjectSharingSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1109  ret
0xb110a  ldarg.s  4
0xb110c  ldc.i4.0
0xb110d  stind.i1
0xb110e  ldarg.0
0xb110f  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb1114  ldarg.3
0xb1115  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb111a  ldarg.2
0xb111b  ldarg.3
0xb111c  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.UserSharingResult> Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UpdateDocumentSharingInfo_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1121  ret
0xb1122  ldarg.s  4
0xb1124  ldc.i4.0
0xb1125  stind.i1
0xb1126  ldarg.0
0xb1127  ldstr    aUnshareobject// "UnshareObject"
0xb112c  ldarg.3
0xb112d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1132  ldarg.2
0xb1133  ldarg.3
0xb1134  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UnshareObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1139  ret
0xb113a  ldarg.s  4
0xb113c  ldc.i4.1
0xb113d  stind.i1
0xb113e  ldarg.0
0xb113f  ldstr    aDeletelinkbyki// "DeleteLinkByKind"
0xb1144  ldarg.3
0xb1145  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb114a  ldarg.2
0xb114b  ldarg.3
0xb114c  call     void Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::DeleteLinkByKind_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb1151  ldnull
0xb1152  ret
0xb1153  ldarg.s  4
0xb1155  ldc.i4.1
0xb1156  stind.i1
0xb1157  ldarg.0
0xb1158  ldstr    aUnsharelink// "UnshareLink"
0xb115d  ldarg.3
0xb115e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb1163  ldarg.2
0xb1164  ldarg.3
0xb1165  call     void Microsoft.SharePoint.Sharing.SPSecurableObjectExtensionsServerStub::UnshareLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb116a  ldnull
0xb116b  ret
0xb116c  ldarg.1
0xb116d  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb1172  throw
```
