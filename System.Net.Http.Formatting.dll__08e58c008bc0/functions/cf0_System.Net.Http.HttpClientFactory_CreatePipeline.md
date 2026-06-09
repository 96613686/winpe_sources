# System.Net.Http.HttpClientFactory::CreatePipeline

- ea: `0xcf0`
- end: `0xdb0`
- name: `System.Net.Http.HttpClientFactory::CreatePipeline`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0xce0`

## callees

- `0xcf0`
- `0x3330`
- `0x3350`
- `0xb330`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xcf0  ldarg.0
0xcf1  brtrue.s loc_CFE
0xcf3  ldstr    aInnerhandler// "innerHandler"
0xcf8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xcfd  throw
0xcfe  ldarg.1
0xcff  brtrue.s loc_D03
0xd01  ldarg.0
0xd02  ret
0xd03  ldarg.0
0xd04  stloc.0
0xd05  ldarg.1
0xd06  call     T0x2B00000A
0xd0b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.DelegatingHandler>::GetEnumerator()
0xd10  stloc.1
0xd11  br       loc_D97
0xd16  ldloc.1
0xd17  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.DelegatingHandler>::get_Current()
0xd1c  stloc.2
0xd1d  ldloc.2
0xd1e  brtrue.s loc_D48
0xd20  ldstr    aHandlers// "handlers"
0xd25  call     string System.Net.Http.Properties.Resources::get_DelegatingHandlerArrayContainsNullItem()
0xd2a  ldc.i4.1
0xd2b  newarr   [mscorlib]System.Object
0xd30  dup
0xd31  ldc.i4.0
0xd32  ldtoken  [System.Net.Http]System.Net.Http.DelegatingHandler
0xd37  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd3c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd41  stelem.ref
0xd42  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0xd47  throw
0xd48  ldloc.2
0xd49  callvirt instance class [System.Net.Http]System.Net.Http.HttpMessageHandler [System.Net.Http]System.Net.Http.DelegatingHandler::get_InnerHandler()
0xd4e  brfalse.s loc_D8E
0xd50  ldstr    aHandlers// "handlers"
0xd55  call     string System.Net.Http.Properties.Resources::get_DelegatingHandlerArrayHasNonNullInnerHandler()
0xd5a  ldc.i4.3
0xd5b  newarr   [mscorlib]System.Object
0xd60  dup
0xd61  ldc.i4.0
0xd62  ldtoken  [System.Net.Http]System.Net.Http.DelegatingHandler
0xd67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd6c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd71  stelem.ref
0xd72  dup
0xd73  ldc.i4.1
0xd74  ldstr    aInnerhandler_0// "InnerHandler"
0xd79  stelem.ref
0xd7a  dup
0xd7b  ldc.i4.2
0xd7c  ldloc.2
0xd7d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd82  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd87  stelem.ref
0xd88  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0xd8d  throw
0xd8e  ldloc.2
0xd8f  ldloc.0
0xd90  callvirt instance void [System.Net.Http]System.Net.Http.DelegatingHandler::set_InnerHandler(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0xd95  ldloc.2
0xd96  stloc.0
0xd97  ldloc.1
0xd98  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd9d  brtrue   loc_D16
0xda2  leave.s  loc_DAE
0xda4  ldloc.1
0xda5  brfalse.s loc_DAD
0xda7  ldloc.1
0xda8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdad  endfinally
0xdae  ldloc.0
0xdaf  ret
```
