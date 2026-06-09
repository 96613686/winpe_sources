# Microsoft.SharePoint.Publishing.DesignPackageServerStub::InvokeStaticMethod_0

- ea: `0x3150`
- end: `0x3235`
- name: `Microsoft.SharePoint.Publishing.DesignPackageServerStub::InvokeStaticMethod_0`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3040`
- `0x3080`
- `0x30b0`
- `0x30e0`
- `0x3110`
- `0x3150`

## string_xrefs

- `0x3171`: `Install`
- `0x31b8`: `Install`
- `0x317e`: `UnInstall`
- `0x31d1`: `UnInstall`

## pseudocode

```c

```

## disassembly

```asm
0x3150  ldarg.3
0x3151  brtrue.s loc_315E
0x3153  ldstr    aProxycontext// "proxyContext"
0x3158  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x315d  throw
0x315e  ldarg.0
0x315f  ldarg.1
0x3160  ldarg.3
0x3161  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3166  starg.s  1
0x3168  ldarg.1
0x3169  dup
0x316a  stloc.0
0x316b  brfalse  loc_322E
0x3170  ldloc.0
0x3171  ldstr    aInstall// "Install"
0x3176  call     bool [mscorlib]System.String::op_Equality(string, string)
0x317b  brtrue.s loc_31B3
0x317d  ldloc.0
0x317e  ldstr    aUninstall// "UnInstall"
0x3183  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3188  brtrue.s loc_31CC
0x318a  ldloc.0
0x318b  ldstr    aApply// "Apply"
0x3190  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3195  brtrue.s loc_31E5
0x3197  ldloc.0
0x3198  ldstr    aExportenterpri// "ExportEnterprise"
0x319d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x31a2  brtrue.s loc_31FE
0x31a4  ldloc.0
0x31a5  ldstr    aExportsmallbus// "ExportSmallBusiness"
0x31aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x31af  brtrue.s loc_3216
0x31b1  br.s     loc_322E
0x31b3  ldarg.s  4
0x31b5  ldc.i4.1
0x31b6  stind.i1
0x31b7  ldarg.0
0x31b8  ldstr    aInstall// "Install"
0x31bd  ldarg.3
0x31be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x31c3  ldarg.2
0x31c4  ldarg.3
0x31c5  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::Install_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x31ca  ldnull
0x31cb  ret
0x31cc  ldarg.s  4
0x31ce  ldc.i4.1
0x31cf  stind.i1
0x31d0  ldarg.0
0x31d1  ldstr    aUninstall// "UnInstall"
0x31d6  ldarg.3
0x31d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x31dc  ldarg.2
0x31dd  ldarg.3
0x31de  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::UnInstall_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x31e3  ldnull
0x31e4  ret
0x31e5  ldarg.s  4
0x31e7  ldc.i4.1
0x31e8  stind.i1
0x31e9  ldarg.0
0x31ea  ldstr    aApply// "Apply"
0x31ef  ldarg.3
0x31f0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x31f5  ldarg.2
0x31f6  ldarg.3
0x31f7  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::Apply_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x31fc  ldnull
0x31fd  ret
0x31fe  ldarg.s  4
0x3200  ldc.i4.0
0x3201  stind.i1
0x3202  ldarg.0
0x3203  ldstr    aExportenterpri// "ExportEnterprise"
0x3208  ldarg.3
0x3209  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x320e  ldarg.2
0x320f  ldarg.3
0x3210  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo Microsoft.SharePoint.Publishing.DesignPackageServerStub::ExportEnterprise_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3215  ret
0x3216  ldarg.s  4
0x3218  ldc.i4.0
0x3219  stind.i1
0x321a  ldarg.0
0x321b  ldstr    aExportsmallbus// "ExportSmallBusiness"
0x3220  ldarg.3
0x3221  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3226  ldarg.2
0x3227  ldarg.3
0x3228  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo Microsoft.SharePoint.Publishing.DesignPackageServerStub::ExportSmallBusiness_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x322d  ret
0x322e  ldarg.1
0x322f  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x3234  throw
```
