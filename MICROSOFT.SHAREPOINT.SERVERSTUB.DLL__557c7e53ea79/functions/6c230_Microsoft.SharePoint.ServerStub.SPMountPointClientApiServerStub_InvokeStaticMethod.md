# Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::InvokeStaticMethod

- ea: `0x6c230`
- end: `0x6c2c6`
- name: `Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::InvokeStaticMethod`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x6c170`
- `0x6c1d0`
- `0x6c210`
- `0x6c230`

## string_xrefs

- `0x6c24e`: `CreateMountPoint`
- `0x6c27b`: `CreateMountPoint`
- `0x6c25b`: `GetMountedFolderInfo`
- `0x6c294`: `GetMountedFolderInfo`
- `0x6c268`: `GetMountedFolderUrls`
- `0x6c2ac`: `GetMountedFolderUrls`

## pseudocode

```c

```

## disassembly

```asm
0x6c230  ldarg.3
0x6c231  brtrue.s loc_6C23E
0x6c233  ldstr    aProxycontext// "proxyContext"
0x6c238  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6c23d  throw
0x6c23e  ldarg.0
0x6c23f  ldarg.1
0x6c240  ldarg.3
0x6c241  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c246  starg.s  1
0x6c248  ldarg.1
0x6c249  dup
0x6c24a  stloc.0
0x6c24b  brfalse.s loc_6C2BF
0x6c24d  ldloc.0
0x6c24e  ldstr    aCreatemountpoi// "CreateMountPoint"
0x6c253  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c258  brtrue.s loc_6C276
0x6c25a  ldloc.0
0x6c25b  ldstr    aGetmountedfold// "GetMountedFolderInfo"
0x6c260  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c265  brtrue.s loc_6C28F
0x6c267  ldloc.0
0x6c268  ldstr    aGetmountedfold_0// "GetMountedFolderUrls"
0x6c26d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c272  brtrue.s loc_6C2A7
0x6c274  br.s     loc_6C2BF
0x6c276  ldarg.s  4
0x6c278  ldc.i4.1
0x6c279  stind.i1
0x6c27a  ldarg.0
0x6c27b  ldstr    aCreatemountpoi// "CreateMountPoint"
0x6c280  ldarg.3
0x6c281  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c286  ldarg.2
0x6c287  ldarg.3
0x6c288  call     void Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::CreateMountPoint_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c28d  ldnull
0x6c28e  ret
0x6c28f  ldarg.s  4
0x6c291  ldc.i4.0
0x6c292  stind.i1
0x6c293  ldarg.0
0x6c294  ldstr    aGetmountedfold// "GetMountedFolderInfo"
0x6c299  ldarg.3
0x6c29a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c29f  ldarg.2
0x6c2a0  ldarg.3
0x6c2a1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPMountedFolderInfo Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::GetMountedFolderInfo_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c2a6  ret
0x6c2a7  ldarg.s  4
0x6c2a9  ldc.i4.0
0x6c2aa  stind.i1
0x6c2ab  ldarg.0
0x6c2ac  ldstr    aGetmountedfold_0// "GetMountedFolderUrls"
0x6c2b1  ldarg.3
0x6c2b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c2b7  ldarg.2
0x6c2b8  ldarg.3
0x6c2b9  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::GetMountedFolderUrls_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c2be  ret
0x6c2bf  ldarg.1
0x6c2c0  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x6c2c5  throw
```
