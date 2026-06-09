# <GetSymmetricKey>d__4::MoveNext

- ea: `0x6a80`
- end: `0x6bed`
- name: `<GetSymmetricKey>d__4::MoveNext`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x15d0`
- `0x3510`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  ldfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6a86  stloc.0
0x6a87  ldloc.0
0x6a88  brfalse.s loc_6AD6
0x6a8a  ldloc.0
0x6a8b  ldc.i4.1
0x6a8c  beq      loc_6B46
0x6a91  ldarg.0
0x6a92  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetSymmetricKey>d__4::httpClient
0x6a97  ldarg.0
0x6a98  ldfld    class [System]System.Uri <GetSymmetricKey>d__4::encryptedSymmetricKeyUrl
0x6a9d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::GetAsync(class [System]System.Uri)
0x6aa2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x6aa7  stloc.s  4
0x6aa9  ldloca.s 4
0x6aab  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x6ab0  brtrue.s loc_6AF3
0x6ab2  ldarg.0
0x6ab3  ldc.i4.0
0x6ab4  dup
0x6ab5  stloc.0
0x6ab6  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6abb  ldarg.0
0x6abc  ldloc.s  4
0x6abe  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetSymmetricKey>d__4::<>u__1
0x6ac3  ldarg.0
0x6ac4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x6ac9  ldloca.s 4
0x6acb  ldarg.0
0x6acc  call     T0x2B00004C
0x6ad1  leave    loc_6BEC
0x6ad6  ldarg.0
0x6ad7  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetSymmetricKey>d__4::<>u__1
0x6adc  stloc.s  4
0x6ade  ldarg.0
0x6adf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <GetSymmetricKey>d__4::<>u__1
0x6ae4  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x6aea  ldarg.0
0x6aeb  ldc.i4.m1
0x6aec  dup
0x6aed  stloc.0
0x6aee  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6af3  ldloca.s 4
0x6af5  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x6afa  stloc.3
0x6afb  ldarg.0
0x6afc  ldloc.3
0x6afd  stfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <GetSymmetricKey>d__4::<response>5__2
0x6b02  ldarg.0
0x6b03  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <GetSymmetricKey>d__4::<response>5__2
0x6b08  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x6b0d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0x6b12  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x6b17  stloc.s  5
0x6b19  ldloca.s 5
0x6b1b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x6b20  brtrue.s loc_6B63
0x6b22  ldarg.0
0x6b23  ldc.i4.1
0x6b24  dup
0x6b25  stloc.0
0x6b26  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6b2b  ldarg.0
0x6b2c  ldloc.s  5
0x6b2e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetSymmetricKey>d__4::<>u__2
0x6b33  ldarg.0
0x6b34  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x6b39  ldloca.s 5
0x6b3b  ldarg.0
0x6b3c  call     T0x2B00004D
0x6b41  leave    loc_6BEC
0x6b46  ldarg.0
0x6b47  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetSymmetricKey>d__4::<>u__2
0x6b4c  stloc.s  5
0x6b4e  ldarg.0
0x6b4f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetSymmetricKey>d__4::<>u__2
0x6b54  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x6b5a  ldarg.0
0x6b5b  ldc.i4.m1
0x6b5c  dup
0x6b5d  stloc.0
0x6b5e  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6b63  ldloca.s 5
0x6b65  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x6b6a  stloc.2
0x6b6b  ldarg.0
0x6b6c  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <GetSymmetricKey>d__4::<response>5__2
0x6b71  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x6b76  ldc.i4   0xC8
0x6b7b  beq.s    loc_6BA8
0x6b7d  ldstr    aErrorGettingSy// "Error getting symmetric key. Status cod"...
0x6b82  ldarg.0
0x6b83  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <GetSymmetricKey>d__4::<response>5__2
0x6b88  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x6b8d  box      [System]System.Net.HttpStatusCode
0x6b92  call     string [mscorlib]System.String::Format(string, object)
0x6b97  dup
0x6b98  call     T0x2B00000A
0x6b9d  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0x6ba2  newobj   instance void Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementException::.ctor(string message)
0x6ba7  throw
0x6ba8  ldloc.2
0x6ba9  ldc.i4.1
0x6baa  ldloc.2
0x6bab  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6bb0  ldc.i4.2
0x6bb1  sub
0x6bb2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6bb7  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x6bbc  stloc.1
0x6bbd  leave.s  loc_6BD8
0x6bbf  stloc.s  6
0x6bc1  ldarg.0
0x6bc2  ldc.i4.s 0xFE
0x6bc4  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6bc9  ldarg.0
0x6bca  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x6bcf  ldloc.s  6
0x6bd1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]>::SetException(class [mscorlib]System.Exception)
0x6bd6  leave.s  loc_6BEC
0x6bd8  ldarg.0
0x6bd9  ldc.i4.s 0xFE
0x6bdb  stfld    int32 <GetSymmetricKey>d__4::<>1__state
0x6be0  ldarg.0
0x6be1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]> <GetSymmetricKey>d__4::<>t__builder
0x6be6  ldloc.1
0x6be7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<unsigned int8[]>::SetResult(var<u1>)
0x6bec  ret
```
