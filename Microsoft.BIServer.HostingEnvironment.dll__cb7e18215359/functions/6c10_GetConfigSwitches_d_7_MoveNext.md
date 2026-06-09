# <GetConfigSwitches>d__7::MoveNext

- ea: `0x6c10`
- end: `0x6e56`
- name: `<GetConfigSwitches>d__7::MoveNext`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x15d0`
- `0x3260`
- `0x3510`
- `0x3680`
- `0x6c10`

## string_xrefs

- `0x6cc5`: `Error getting configuration info. Status code {0}`
- `0x6e08`: `Can't read configuration properties`

## pseudocode

```c

```

## disassembly

```asm
0x6c10  ldarg.0
0x6c11  ldfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6c16  stloc.0
0x6c17  ldarg.0
0x6c18  ldfld    class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService <GetConfigSwitches>d__7::<>4__this
0x6c1d  stloc.1
0x6c1e  ldloc.0
0x6c1f  brfalse.s loc_6C3F
0x6c21  ldloc.0
0x6c22  ldc.i4.1
0x6c23  beq      loc_6D0C
0x6c28  ldarg.0
0x6c29  newobj   instance void [System.Net.Http]System.Net.Http.HttpClientHandler::.ctor()
0x6c2e  dup
0x6c2f  ldc.i4.1
0x6c30  callvirt instance void [System.Net.Http]System.Net.Http.HttpClientHandler::set_UseDefaultCredentials(bool)
0x6c35  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0x6c3a  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6c3f  nop
0x6c40  ldloc.0
0x6c41  brfalse.s loc_6C93
0x6c43  ldarg.0
0x6c44  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6c49  call     void Microsoft.BIServer.HostingEnvironment.Request.RequestContext::PassOnCurrentRequestContext(class [System.Net.Http]System.Net.Http.HttpClient client)
0x6c4e  ldarg.0
0x6c4f  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6c54  ldloc.1
0x6c55  call     instance class [System]System.Uri Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetConfigInfo()
0x6c5a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::GetAsync(class [System]System.Uri)
0x6c5f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x6c64  stloc.s  4
0x6c66  ldloca.s 4
0x6c68  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x6c6d  brtrue.s loc_6CB0
0x6c6f  ldarg.0
0x6c70  ldc.i4.0
0x6c71  dup
0x6c72  stloc.0
0x6c73  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6c78  ldarg.0
0x6c79  ldloc.s  4
0x6c7b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetConfigSwitches>d__7::<>u__1
0x6c80  ldarg.0
0x6c81  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x6c86  ldloca.s 4
0x6c88  ldarg.0
0x6c89  call     T0x2B00004E
0x6c8e  leave    loc_6E55
0x6c93  ldarg.0
0x6c94  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetConfigSwitches>d__7::<>u__1
0x6c99  stloc.s  4
0x6c9b  ldarg.0
0x6c9c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetConfigSwitches>d__7::<>u__1
0x6ca1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x6ca7  ldarg.0
0x6ca8  ldc.i4.m1
0x6ca9  dup
0x6caa  stloc.0
0x6cab  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6cb0  ldloca.s 4
0x6cb2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x6cb7  stloc.3
0x6cb8  ldloc.3
0x6cb9  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x6cbe  ldc.i4   0xC8
0x6cc3  beq.s    loc_6CEB
0x6cc5  ldstr    aErrorGettingCo// "Error getting configuration info. Statu"...
0x6cca  ldloc.3
0x6ccb  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x6cd0  box      [System]System.Net.HttpStatusCode
0x6cd5  call     string [mscorlib]System.String::Format(string, object)
0x6cda  dup
0x6cdb  call     T0x2B00000A
0x6ce0  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x6ce5  newobj   instance void Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementException::.ctor(string message)
0x6cea  throw
0x6ceb  leave.s  loc_6D05
0x6ced  ldloc.0
0x6cee  ldc.i4.0
0x6cef  bge.s    loc_6D04
0x6cf1  ldarg.0
0x6cf2  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6cf7  brfalse.s loc_6D04
0x6cf9  ldarg.0
0x6cfa  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6cff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d04  endfinally
0x6d05  ldarg.0
0x6d06  ldnull
0x6d07  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetConfigSwitches>d__7::<httpClient>5__2
0x6d0c  nop
0x6d0d  ldloc.0
0x6d0e  ldc.i4.1
0x6d0f  beq.s    loc_6D50
0x6d11  ldloc.3
0x6d12  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x6d17  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0x6d1c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x6d21  stloc.s  7
0x6d23  ldloca.s 7
0x6d25  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x6d2a  brtrue.s loc_6D6D
0x6d2c  ldarg.0
0x6d2d  ldc.i4.1
0x6d2e  dup
0x6d2f  stloc.0
0x6d30  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6d35  ldarg.0
0x6d36  ldloc.s  7
0x6d38  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfigSwitches>d__7::<>u__2
0x6d3d  ldarg.0
0x6d3e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x6d43  ldloca.s 7
0x6d45  ldarg.0
0x6d46  call     T0x2B00004F
0x6d4b  leave    loc_6E55
0x6d50  ldarg.0
0x6d51  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfigSwitches>d__7::<>u__2
0x6d56  stloc.s  7
0x6d58  ldarg.0
0x6d59  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfigSwitches>d__7::<>u__2
0x6d5e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x6d64  ldarg.0
0x6d65  ldc.i4.m1
0x6d66  dup
0x6d67  stloc.0
0x6d68  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6d6d  ldloca.s 7
0x6d6f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x6d74  ldtoken  Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x6d79  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d7e  call     string[] [mscorlib]System.Enum::GetNames(class [mscorlib]System.Type)
0x6d83  stloc.s  5
0x6d85  call     T0x2B000050
0x6d8a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>::.ctor()
0x6d8f  stloc.s  6
0x6d91  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x6d96  stloc.s  8
0x6d98  br.s     loc_6DE7
0x6d9a  ldloc.s  8
0x6d9c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x6da1  stloc.s  9
0x6da3  ldloc.s  5
0x6da5  ldloca.s 9
0x6da7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6dac  call     T0x2B000032
0x6db1  brfalse.s loc_6DE7
0x6db3  ldloc.s  6
0x6db5  ldtoken  Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x6dba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6dbf  ldloca.s 9
0x6dc1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6dc6  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x6dcb  unbox.any Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x6dd0  ldloca.s 9
0x6dd2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6dd7  ldsfld   string [mscorlib]System.Boolean::TrueString
0x6ddc  ldc.i4.5
0x6ddd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x6de2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>::Add(var<u1>, !!T0)
0x6de7  ldloc.s  8
0x6de9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6dee  brtrue.s loc_6D9A
0x6df0  leave.s  loc_6E02
0x6df2  ldloc.0
0x6df3  ldc.i4.0
0x6df4  bge.s    loc_6E01
0x6df6  ldloc.s  8
0x6df8  brfalse.s loc_6E01
0x6dfa  ldloc.s  8
0x6dfc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e01  endfinally
0x6e02  ldloc.s  6
0x6e04  stloc.2
0x6e05  leave.s  loc_6E41
0x6e07  pop
0x6e08  ldstr    aCanTReadConfig// "Can't read configuration properties"
0x6e0d  call     T0x2B00000A
0x6e12  call     string [mscorlib]System.String::Format(string, object[])
0x6e17  dup
0x6e18  call     T0x2B00000A
0x6e1d  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x6e22  newobj   instance void Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementException::.ctor(string message)
0x6e27  throw
0x6e28  stloc.s  0xA
0x6e2a  ldarg.0
0x6e2b  ldc.i4.s 0xFE
0x6e2d  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6e32  ldarg.0
0x6e33  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x6e38  ldloc.s  0xA
0x6e3a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>>::SetException(class [mscorlib]System.Exception)
0x6e3f  leave.s  loc_6E55
0x6e41  ldarg.0
0x6e42  ldc.i4.s 0xFE
0x6e44  stfld    int32 <GetConfigSwitches>d__7::<>1__state
0x6e49  ldarg.0
0x6e4a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>> <GetConfigSwitches>d__7::<>t__builder
0x6e4f  ldloc.2
0x6e50  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings, bool>>::SetResult(var<u1>)
0x6e55  ret
```
