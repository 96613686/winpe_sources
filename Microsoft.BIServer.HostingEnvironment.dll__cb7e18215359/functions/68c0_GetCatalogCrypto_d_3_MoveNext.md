# <GetCatalogCrypto>d__3::MoveNext

- ea: `0x68c0`
- end: `0x6a58`
- name: `<GetCatalogCrypto>d__3::MoveNext`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x3260`
- `0x35a0`
- `0x35f0`
- `0x3610`
- `0x3cf0`
- `0x4180`
- `0x68c0`

## pseudocode

```c

```

## disassembly

```asm
0x68c0  ldarg.0
0x68c1  ldfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x68c6  stloc.0
0x68c7  ldarg.0
0x68c8  ldfld    class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService <GetCatalogCrypto>d__3::<>4__this
0x68cd  stloc.1
0x68ce  ldloc.0
0x68cf  ldc.i4.1
0x68d0  ble.un.s loc_68E1
0x68d2  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x68d7  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_IsInitialized()
0x68dc  brtrue   loc_6A22
0x68e1  nop
0x68e2  ldloc.0
0x68e3  brfalse.s loc_6928
0x68e5  ldloc.0
0x68e6  ldc.i4.1
0x68e7  beq      loc_6971
0x68ec  ldsfld   class [mscorlib]System.Threading.SemaphoreSlim Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_cryptoSemaphore
0x68f1  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.SemaphoreSlim::WaitAsync()
0x68f6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x68fb  stloc.3
0x68fc  ldloca.s 3
0x68fe  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6903  brtrue.s loc_6944
0x6905  ldarg.0
0x6906  ldc.i4.0
0x6907  dup
0x6908  stloc.0
0x6909  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x690e  ldarg.0
0x690f  ldloc.3
0x6910  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <GetCatalogCrypto>d__3::<>u__1
0x6915  ldarg.0
0x6916  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x691b  ldloca.s 3
0x691d  ldarg.0
0x691e  call     T0x2B00004A
0x6923  leave    loc_6A57
0x6928  ldarg.0
0x6929  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <GetCatalogCrypto>d__3::<>u__1
0x692e  stloc.3
0x692f  ldarg.0
0x6930  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <GetCatalogCrypto>d__3::<>u__1
0x6935  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x693b  ldarg.0
0x693c  ldc.i4.m1
0x693d  dup
0x693e  stloc.0
0x693f  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x6944  ldloca.s 3
0x6946  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x694b  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x6950  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_IsInitialized()
0x6955  brtrue   loc_6A10
0x695a  ldarg.0
0x695b  newobj   instance void [System.Net.Http]System.Net.Http.HttpClientHandler::.ctor()
0x6960  dup
0x6961  ldc.i4.1
0x6962  callvirt instance void [System.Net.Http]System.Net.Http.HttpClientHandler::set_UseDefaultCredentials(bool)
0x6967  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0x696c  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x6971  nop
0x6972  ldloc.0
0x6973  ldc.i4.1
0x6974  beq.s    loc_69C6
0x6976  ldarg.0
0x6977  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x697c  call     void Microsoft.BIServer.HostingEnvironment.Request.RequestContext::PassOnCurrentRequestContext(class [System.Net.Http]System.Net.Http.HttpClient client)
0x6981  ldarg.0
0x6982  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x6987  ldloc.1
0x6988  call     instance class [System]System.Uri Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetEncryptedSymmetricKeyUrl()
0x698d  call     class [mscorlib]System.Threading.Tasks.Task`1<unsigned int8[]> Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetSymmetricKey(class [System.Net.Http]System.Net.Http.HttpClient httpClient, class [System]System.Uri encryptedSymmetricKeyUrl)
0x6992  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<unsigned int8[]>::GetAwaiter()
0x6997  stloc.s  4
0x6999  ldloca.s 4
0x699b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]>::get_IsCompleted()
0x69a0  brtrue.s loc_69E3
0x69a2  ldarg.0
0x69a3  ldc.i4.1
0x69a4  dup
0x69a5  stloc.0
0x69a6  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x69ab  ldarg.0
0x69ac  ldloc.s  4
0x69ae  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]> <GetCatalogCrypto>d__3::<>u__2
0x69b3  ldarg.0
0x69b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x69b9  ldloca.s 4
0x69bb  ldarg.0
0x69bc  call     T0x2B00004B
0x69c1  leave    loc_6A57
0x69c6  ldarg.0
0x69c7  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]> <GetCatalogCrypto>d__3::<>u__2
0x69cc  stloc.s  4
0x69ce  ldarg.0
0x69cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]> <GetCatalogCrypto>d__3::<>u__2
0x69d4  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]>
0x69da  ldarg.0
0x69db  ldc.i4.m1
0x69dc  dup
0x69dd  stloc.0
0x69de  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x69e3  ldloca.s 4
0x69e5  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<unsigned int8[]>::GetResult()
0x69ea  call     void Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::SetPublicEncryptedSymmetricKey(unsigned int8[] symmetricKey)
0x69ef  leave.s  loc_6A09
0x69f1  ldloc.0
0x69f2  ldc.i4.0
0x69f3  bge.s    loc_6A08
0x69f5  ldarg.0
0x69f6  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x69fb  brfalse.s loc_6A08
0x69fd  ldarg.0
0x69fe  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x6a03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a08  endfinally
0x6a09  ldarg.0
0x6a0a  ldnull
0x6a0b  stfld    class [System.Net.Http]System.Net.Http.HttpClient <GetCatalogCrypto>d__3::<httpClient>5__2
0x6a10  leave.s  loc_6A22
0x6a12  ldloc.0
0x6a13  ldc.i4.0
0x6a14  bge.s    loc_6A21
0x6a16  ldsfld   class [mscorlib]System.Threading.SemaphoreSlim Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_cryptoSemaphore
0x6a1b  callvirt instance int32 [mscorlib]System.Threading.SemaphoreSlim::Release()
0x6a20  pop
0x6a21  endfinally
0x6a22  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x6a27  stloc.2
0x6a28  leave.s  loc_6A43
0x6a2a  stloc.s  5
0x6a2c  ldarg.0
0x6a2d  ldc.i4.s 0xFE
0x6a2f  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x6a34  ldarg.0
0x6a35  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x6a3a  ldloc.s  5
0x6a3c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto>::SetException(class [mscorlib]System.Exception)
0x6a41  leave.s  loc_6A57
0x6a43  ldarg.0
0x6a44  ldc.i4.s 0xFE
0x6a46  stfld    int32 <GetCatalogCrypto>d__3::<>1__state
0x6a4b  ldarg.0
0x6a4c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto> <GetCatalogCrypto>d__3::<>t__builder
0x6a51  ldloc.2
0x6a52  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto>::SetResult(var<u1>)
0x6a57  ret
```
