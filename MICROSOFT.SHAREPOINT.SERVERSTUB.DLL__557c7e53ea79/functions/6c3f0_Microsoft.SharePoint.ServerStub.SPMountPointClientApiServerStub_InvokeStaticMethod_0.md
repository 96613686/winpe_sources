# Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::InvokeStaticMethod_0

- ea: `0x6c3f0`
- end: `0x6c486`
- name: `Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::InvokeStaticMethod_0`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x6c330`
- `0x6c390`
- `0x6c3d0`
- `0x6c3f0`

## string_xrefs

- `0x6c40e`: `CreateMountPoint`
- `0x6c43b`: `CreateMountPoint`
- `0x6c41b`: `GetMountedFolderInfo`
- `0x6c454`: `GetMountedFolderInfo`
- `0x6c428`: `GetMountedFolderUrls`
- `0x6c46c`: `GetMountedFolderUrls`

## pseudocode

```c

```

## disassembly

```asm
0x6c3f0  ldarg.3
0x6c3f1  brtrue.s loc_6C3FE
0x6c3f3  ldstr    aProxycontext// "proxyContext"
0x6c3f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6c3fd  throw
0x6c3fe  ldarg.0
0x6c3ff  ldarg.1
0x6c400  ldarg.3
0x6c401  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c406  starg.s  1
0x6c408  ldarg.1
0x6c409  dup
0x6c40a  stloc.0
0x6c40b  brfalse.s loc_6C47F
0x6c40d  ldloc.0
0x6c40e  ldstr    aCreatemountpoi// "CreateMountPoint"
0x6c413  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c418  brtrue.s loc_6C436
0x6c41a  ldloc.0
0x6c41b  ldstr    aGetmountedfold// "GetMountedFolderInfo"
0x6c420  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c425  brtrue.s loc_6C44F
0x6c427  ldloc.0
0x6c428  ldstr    aGetmountedfold_0// "GetMountedFolderUrls"
0x6c42d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c432  brtrue.s loc_6C467
0x6c434  br.s     loc_6C47F
0x6c436  ldarg.s  4
0x6c438  ldc.i4.1
0x6c439  stind.i1
0x6c43a  ldarg.0
0x6c43b  ldstr    aCreatemountpoi// "CreateMountPoint"
0x6c440  ldarg.3
0x6c441  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c446  ldarg.2
0x6c447  ldarg.3
0x6c448  call     void Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::CreateMountPoint_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c44d  ldnull
0x6c44e  ret
0x6c44f  ldarg.s  4
0x6c451  ldc.i4.0
0x6c452  stind.i1
0x6c453  ldarg.0
0x6c454  ldstr    aGetmountedfold// "GetMountedFolderInfo"
0x6c459  ldarg.3
0x6c45a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c45f  ldarg.2
0x6c460  ldarg.3
0x6c461  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPMountedFolderInfo Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::GetMountedFolderInfo_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c466  ret
0x6c467  ldarg.s  4
0x6c469  ldc.i4.0
0x6c46a  stind.i1
0x6c46b  ldarg.0
0x6c46c  ldstr    aGetmountedfold_0// "GetMountedFolderUrls"
0x6c471  ldarg.3
0x6c472  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6c477  ldarg.2
0x6c478  ldarg.3
0x6c479  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.SharePoint.ServerStub.SPMountPointClientApiServerStub::GetMountedFolderUrls_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6c47e  ret
0x6c47f  ldarg.1
0x6c480  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x6c485  throw
```
