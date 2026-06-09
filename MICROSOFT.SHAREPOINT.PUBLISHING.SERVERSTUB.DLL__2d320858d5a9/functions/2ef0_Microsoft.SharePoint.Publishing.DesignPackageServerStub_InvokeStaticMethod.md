# Microsoft.SharePoint.Publishing.DesignPackageServerStub::InvokeStaticMethod

- ea: `0x2ef0`
- end: `0x2fd5`
- name: `Microsoft.SharePoint.Publishing.DesignPackageServerStub::InvokeStaticMethod`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2de0`
- `0x2e20`
- `0x2e50`
- `0x2e80`
- `0x2eb0`
- `0x2ef0`

## string_xrefs

- `0x2f11`: `Install`
- `0x2f58`: `Install`
- `0x2f1e`: `UnInstall`
- `0x2f71`: `UnInstall`

## pseudocode

```c

```

## disassembly

```asm
0x2ef0  ldarg.3
0x2ef1  brtrue.s loc_2EFE
0x2ef3  ldstr    aProxycontext// "proxyContext"
0x2ef8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2efd  throw
0x2efe  ldarg.0
0x2eff  ldarg.1
0x2f00  ldarg.3
0x2f01  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f06  starg.s  1
0x2f08  ldarg.1
0x2f09  dup
0x2f0a  stloc.0
0x2f0b  brfalse  loc_2FCE
0x2f10  ldloc.0
0x2f11  ldstr    aInstall// "Install"
0x2f16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f1b  brtrue.s loc_2F53
0x2f1d  ldloc.0
0x2f1e  ldstr    aUninstall// "UnInstall"
0x2f23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f28  brtrue.s loc_2F6C
0x2f2a  ldloc.0
0x2f2b  ldstr    aApply// "Apply"
0x2f30  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f35  brtrue.s loc_2F85
0x2f37  ldloc.0
0x2f38  ldstr    aExportenterpri// "ExportEnterprise"
0x2f3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f42  brtrue.s loc_2F9E
0x2f44  ldloc.0
0x2f45  ldstr    aExportsmallbus// "ExportSmallBusiness"
0x2f4a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f4f  brtrue.s loc_2FB6
0x2f51  br.s     loc_2FCE
0x2f53  ldarg.s  4
0x2f55  ldc.i4.1
0x2f56  stind.i1
0x2f57  ldarg.0
0x2f58  ldstr    aInstall// "Install"
0x2f5d  ldarg.3
0x2f5e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f63  ldarg.2
0x2f64  ldarg.3
0x2f65  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::Install_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2f6a  ldnull
0x2f6b  ret
0x2f6c  ldarg.s  4
0x2f6e  ldc.i4.1
0x2f6f  stind.i1
0x2f70  ldarg.0
0x2f71  ldstr    aUninstall// "UnInstall"
0x2f76  ldarg.3
0x2f77  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f7c  ldarg.2
0x2f7d  ldarg.3
0x2f7e  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::UnInstall_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2f83  ldnull
0x2f84  ret
0x2f85  ldarg.s  4
0x2f87  ldc.i4.1
0x2f88  stind.i1
0x2f89  ldarg.0
0x2f8a  ldstr    aApply// "Apply"
0x2f8f  ldarg.3
0x2f90  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f95  ldarg.2
0x2f96  ldarg.3
0x2f97  call     void Microsoft.SharePoint.Publishing.DesignPackageServerStub::Apply_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2f9c  ldnull
0x2f9d  ret
0x2f9e  ldarg.s  4
0x2fa0  ldc.i4.0
0x2fa1  stind.i1
0x2fa2  ldarg.0
0x2fa3  ldstr    aExportenterpri// "ExportEnterprise"
0x2fa8  ldarg.3
0x2fa9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fae  ldarg.2
0x2faf  ldarg.3
0x2fb0  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo Microsoft.SharePoint.Publishing.DesignPackageServerStub::ExportEnterprise_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2fb5  ret
0x2fb6  ldarg.s  4
0x2fb8  ldc.i4.0
0x2fb9  stind.i1
0x2fba  ldarg.0
0x2fbb  ldstr    aExportsmallbus// "ExportSmallBusiness"
0x2fc0  ldarg.3
0x2fc1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fc6  ldarg.2
0x2fc7  ldarg.3
0x2fc8  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.DesignPackageInfo Microsoft.SharePoint.Publishing.DesignPackageServerStub::ExportSmallBusiness_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2fcd  ret
0x2fce  ldarg.1
0x2fcf  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x2fd4  throw
```
