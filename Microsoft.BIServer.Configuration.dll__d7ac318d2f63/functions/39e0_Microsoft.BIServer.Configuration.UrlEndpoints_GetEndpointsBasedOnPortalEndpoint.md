# Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsBasedOnPortalEndpoint

- ea: `0x39e0`
- end: `0x3a8d`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsBasedOnPortalEndpoint`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39c0`
- `0x3a90`

## callees

- `0x3850`
- `0x39e0`
- `0x3b00`
- `0x3bc0`
- `0x3c20`
- `0x4770`
- `0x4900`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::.ctor()
0x39e5  stloc.0
0x39e6  ldarg.1
0x39e7  callvirt instance string [mscorlib]System.Object::ToString()
0x39ec  ldstr    aPbirs// "PBIRS"
0x39f1  ldc.i4.5
0x39f2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x39f7  brfalse  loc_3A8B
0x39fc  ldarg.2
0x39fd  ldsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.Application, bool> <>c::<>9__11_0
0x3a02  dup
0x3a03  brtrue.s loc_3A1C
0x3a05  pop
0x3a06  ldsfld   class <>c <>c::<>9
0x3a0b  ldftn    instance bool <>c::<GetEndpointsBasedOnPortalEndpoint>b__11_0(class Microsoft.BIServer.Configuration.Application app)
0x3a11  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.Application, bool>::.ctor(object, native int)
0x3a16  dup
0x3a17  stsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.Application, bool> <>c::<>9__11_0
0x3a1c  call     T0x2B00000D
0x3a21  stloc.1
0x3a22  ldloc.1
0x3a23  brfalse.s loc_3A8B
0x3a25  ldloc.1
0x3a26  callvirt instance class Microsoft.BIServer.Configuration.URL[] Microsoft.BIServer.Configuration.Application::get_URLs()
0x3a2b  call     T0x2B000030
0x3a30  stloc.2
0x3a31  ldloc.2
0x3a32  brfalse.s loc_3A8B
0x3a34  ldc.i4.s 0x18
0x3a36  ldarg.3
0x3a37  or
0x3a38  stloc.3
0x3a39  ldarg.0
0x3a3a  ldloc.3
0x3a3b  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition> Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x3a40  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::GetEnumerator()
0x3a45  stloc.s  4
0x3a47  br.s     loc_3A74
0x3a49  ldloc.s  4
0x3a4b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition>::get_Current()
0x3a50  stloc.s  5
0x3a52  ldloc.s  5
0x3a54  ldloc.2
0x3a55  callvirt instance string Microsoft.BIServer.Configuration.URL::get_UrlString()
0x3a5a  callvirt instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_UrlString(string value)
0x3a5f  ldloc.s  5
0x3a61  ldarg.0
0x3a62  callvirt instance void Microsoft.BIServer.Configuration.UrlEndpointDefinition::set_AccountCredentials(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials value)
0x3a67  ldloc.0
0x3a68  ldloc.s  5
0x3a6a  call     class Microsoft.BIServer.Configuration.Application Microsoft.BIServer.Configuration.UrlEndpoints::CreateApplication(class Microsoft.BIServer.Configuration.UrlEndpointDefinition urlEndpointDefinition)
0x3a6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application>::Add(var<u1>)
0x3a74  ldloc.s  4
0x3a76  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3a7b  brtrue.s loc_3A49
0x3a7d  leave.s  loc_3A8B
0x3a7f  ldloc.s  4
0x3a81  brfalse.s loc_3A8A
0x3a83  ldloc.s  4
0x3a85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3a8a  endfinally
0x3a8b  ldloc.0
0x3a8c  ret
```
