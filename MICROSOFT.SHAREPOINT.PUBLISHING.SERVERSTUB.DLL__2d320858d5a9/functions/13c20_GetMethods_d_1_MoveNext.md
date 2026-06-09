# <GetMethods>d__1::MoveNext

- ea: `0x13c20`
- end: `0x13da0`
- name: `<GetMethods>d__1::MoveNext`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x9d0`
- `0x13c20`
- `0x13dc0`
- `0x13e20`

## pseudocode

```c

```

## disassembly

```asm
0x13c20  ldarg.0
0x13c21  ldfld    int32 <GetMethods>d__1::<>1__state
0x13c26  stloc.1
0x13c27  ldloc.1
0x13c28  switch   loc_13C42, loc_13D93, loc_13CAC, loc_13D8C
0x13c3d  br       loc_13D93
0x13c42  ldarg.0
0x13c43  ldc.i4.m1
0x13c44  stfld    int32 <GetMethods>d__1::<>1__state
0x13c49  ldarg.0
0x13c4a  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__1::proxyContext
0x13c4f  brtrue.s loc_13C5C
0x13c51  ldstr    aProxycontext// "proxyContext"
0x13c56  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13c5b  throw
0x13c5c  ldarg.0
0x13c5d  ldarg.0
0x13c5e  ldfld    class Microsoft.SharePoint.Publishing.AddinPluginServerStub <GetMethods>d__1::<>4__this
0x13c63  ldarg.0
0x13c64  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__1::proxyContext
0x13c69  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> Microsoft.SharePoint.Publishing.AddinPluginServerStub::<>n__FabricatedMethod6(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext target)
0x13c6e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::GetEnumerator()
0x13c73  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1::<>7__wrap4
0x13c78  ldarg.0
0x13c79  ldc.i4.1
0x13c7a  stfld    int32 <GetMethods>d__1::<>1__state
0x13c7f  br.s     loc_13CB3
0x13c81  ldarg.0
0x13c82  ldarg.0
0x13c83  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1::<>7__wrap4
0x13c88  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation>::get_Current()
0x13c8d  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<itemBase>5__2
0x13c92  ldarg.0
0x13c93  ldarg.0
0x13c94  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<itemBase>5__2
0x13c99  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>2__current
0x13c9e  ldarg.0
0x13c9f  ldc.i4.2
0x13ca0  stfld    int32 <GetMethods>d__1::<>1__state
0x13ca5  ldc.i4.1
0x13ca6  stloc.0
0x13ca7  leave    loc_13D9E
0x13cac  ldarg.0
0x13cad  ldc.i4.1
0x13cae  stfld    int32 <GetMethods>d__1::<>1__state
0x13cb3  ldarg.0
0x13cb4  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation> <GetMethods>d__1::<>7__wrap4
0x13cb9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13cbe  brtrue.s loc_13C81
0x13cc0  ldarg.0
0x13cc1  call     instance void <GetMethods>d__1::<>m__Finally5()
0x13cc6  ldarg.0
0x13cc7  ldarg.0
0x13cc8  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::.ctor()
0x13ccd  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13cd2  ldarg.0
0x13cd3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13cd8  ldstr    aCtor// ".ctor"
0x13cdd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_Name(string)
0x13ce2  ldarg.0
0x13ce3  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13ce8  ldc.i4.0
0x13ce9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsStatic(bool)
0x13cee  ldarg.0
0x13cef  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13cf4  ldc.i4.0
0x13cf5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OperationType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.OperationType)
0x13cfa  ldarg.0
0x13cfb  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d00  ldc.i4.7
0x13d01  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ClientLibraryTargets(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientLibraryTargets)
0x13d06  ldarg.0
0x13d07  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d0c  ldstr    aCtor// ".ctor"
0x13d11  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_OriginalName(string)
0x13d16  ldarg.0
0x13d17  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d1c  ldc.i4.0
0x13d1d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_WildcardPath(bool)
0x13d22  ldarg.0
0x13d23  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d28  ldnull
0x13d29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnType(class [mscorlib]System.Type)
0x13d2e  ldarg.0
0x13d2f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d34  ldc.i4.0
0x13d35  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ReturnODataType(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ODataType)
0x13d3a  ldarg.0
0x13d3b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d40  ldc.i4.0
0x13d41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RESTfulExtensionMethod(bool)
0x13d46  ldarg.0
0x13d47  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d4c  ldc.i4.0
0x13d4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_ResourceUsageHints(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceUsageHints)
0x13d52  ldarg.0
0x13d53  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d58  ldc.i4.0
0x13d59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_RequiredRight(valuetype [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ResourceRight)
0x13d5e  ldarg.0
0x13d5f  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d64  ldc.i4.0
0x13d65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation::set_IsBeta(bool)
0x13d6a  ldarg.0
0x13d6b  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>g__initLocal0
0x13d70  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<item>5__3
0x13d75  ldarg.0
0x13d76  ldarg.0
0x13d77  ldfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<item>5__3
0x13d7c  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.MethodInformation <GetMethods>d__1::<>2__current
0x13d81  ldarg.0
0x13d82  ldc.i4.3
0x13d83  stfld    int32 <GetMethods>d__1::<>1__state
0x13d88  ldc.i4.1
0x13d89  stloc.0
0x13d8a  leave.s  loc_13D9E
0x13d8c  ldarg.0
0x13d8d  ldc.i4.m1
0x13d8e  stfld    int32 <GetMethods>d__1::<>1__state
0x13d93  ldc.i4.0
0x13d94  stloc.0
0x13d95  leave.s  loc_13D9E
0x13d97  ldarg.0
0x13d98  call     instance void <GetMethods>d__1::System.IDisposable.Dispose()
0x13d9d  endfinally
0x13d9e  ldloc.0
0x13d9f  ret
```
